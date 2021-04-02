---
title: Procedure consigliate per le query per la ricerca avanzata
description: Come creare query di ricerca delle minacce veloci, efficienti e senza errori quando in Ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, rilevamenti personalizzati, schema, kusto, evitare timeout, righe di comando, ID processo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b65adbc968e095a6845f27ae1ae859830e4065c4
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499263"
---
# <a name="advanced-hunting-query-best-practices"></a>Procedure consigliate per query in Ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a>Ottimizzare le prestazioni delle query

Applicare questi suggerimenti per ottenere risultati più veloci ed evitare timeout durante l'esecuzione di query complesse.

- Quando si provano nuove query, usare sempre `limit` per evitare set di risultati molto grandi. È anche possibile determinare all'inizio le dimensioni del set di risultati usando `count`.
- Usare prima i filtri del periodo. Idealmente, limitare le query a sette giorni.
- Inserire i filtri che si prevede rimuovano la maggior parte dei dati all'inizio della query, subito dopo il filtro del periodo.
- Usare l'operatore `has` su `contains` quando si cercano token completi.
- Individuare una colonna specifica invece di eseguire le ricerche in tutte le colonne.
- Quando si uniscono le tabelle, specificare prima la tabella con meno righe.
- `project` solo le colonne necessarie dalle tabelle che sono state unite.

>[!TIP]
>Per altre informazioni su come migliorare le prestazioni della query, vedere [procedure consigliate per le query di Esplora dati](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="query-tips-and-pitfalls"></a>Suggerimenti e insidie per le query

### <a name="queries-with-process-ids"></a>Query con ID processo

Gli ID processo (PID) sono riciclati in Windows e riutilizzati per i nuovi processi. Di per sé, non possono servire come identificatori univoci per processi specifici. Per ottenere un identificatore univoco per un processo in un dispositivo specifico, usa l'ID processo insieme al tempo di creazione del processo. Quando si uniscono o riepilogano i dati relativi ai processi, includere colonne per l'identificatore del dispositivo (o ), l'ID processo ( o ) e il tempo di creazione `DeviceId` del processo ( o `DeviceName` `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` ).

La seguente query di esempio trova i processi che accedono a più di 10 indirizzi IP dalla porta 445 (SMB), possibilmente analizzando le condivisioni file.

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

La query riepiloga sia `InitiatingProcessId` che `InitiatingProcessCreationTime` in modo da visualizzare un singolo processo, senza combinare più processi con lo stesso ID processo.

### <a name="queries-with-command-lines"></a>Query con righe di comando

Le righe di comando possono variare. Se applicabile, filtrare i nomi dei file ed eseguire una corrispondenza fuzzy.

Esistono diversi modi per creare una riga di comando per eseguire un'attività. Ad esempio, un utente malintenzionato può fare riferimento a un file di immagine con o senza un percorso, senza un'estensione di file, con variabili di ambiente o con virgolette. Inoltre, l'utente malintenzionato può anche cambiare l'ordine dei parametri o aggiungere più citazioni e spazi.

Per creare query più durevoli usando le righe di comando, applicare le procedure seguenti:

- Identificare i processi noti (ad esempio *NET. exe* o *psexec. exe*) confrontando i campi filename (nome file), anziché filtrare nel campo della riga di comando.
- Quando si eseguono query per gli argomenti della riga di comando, non cercare una corrispondenza esatta su più argomenti non correlati in un determinato ordine. Usare invece espressioni regolari o utilizzare più operatori distinti.
- Usare corrispondenza maiuscole/minuscole. Ad esempio, utilizzare `=~` , , e invece di , `in~` `contains` `==` `in` e `contains_cs`
- Per migrare tecniche di offuscamento di linee di domando DOS, provare a rimuovere virgolette, sostituire virgole con spazi e sostituire doppi spazi con uno spazio singolo. Tenere presente che esistono tecniche di offuscamento DOS ancora più complesse che richiedono altri approcci, tuttavia queste possono aiutare a gestire i casi più comuni.

I seguenti esempi mostrano diversi modi di creare una query per cercare il file *net.exe* che blocca il servizio Windows Defender Firewall:

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Comprendere lo schema](advanced-hunting-schema-reference.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Panoramica dei rilevamenti personalizzati](overview-custom-detections.md)
