---
title: Procedure consigliate nella Ricerca avanzata di Microsoft Threat Protection
description: Come creare query di ricerca delle minacce veloci, efficienti e senza errori quando in Ricerca avanzata
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, rilevamenti personalizzati, schema, kusto, evitare il timeout, linee di comando, ID processo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f66b17fbdaaa58cf12bd0373d0fece59349c3a48
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649500"
---
# <a name="advanced-hunting-query-best-practices"></a>Procedure consigliate per query in Ricerca avanzata

**Si applica a:**
- Microsoft Threat Protection



## <a name="optimize-query-performance"></a>Ottimizzare le prestazioni delle query
Applicare questi suggerimenti per ottenere risultati più rapidi ed evitare timeout durante l'esecuzione di query complesse:
- Quando si provano nuove query, usare sempre `limit` per evitare set di risultati molto grandi. È anche possibile determinare all'inizio le dimensioni del set di risultati usando `count`.
- Usare prima i filtri del periodo. Idealmente, è consigliabile limitare le query ai giorni pari.
- Inserire i filtri che si prevede rimuovano la maggior parte dei dati all'inizio della query, subito dopo il filtro del periodo.
- Usare l'operatore `has` su `contains` quando si cercano token completi.
- Individuare una colonna specifica invece di eseguire le ricerche in tutte le colonne.
- Quando si uniscono le tabelle, specificare prima la tabella con meno righe.
- `project` solo le colonne necessarie dalle tabelle che sono state unite.

>[!Tip]
>Per altre informazioni su come migliorare le prestazioni della query, vedere [procedure consigliate per le query di Esplora dati](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="query-tips-and-pitfalls"></a>Suggerimenti e insidie per le query

### <a name="queries-with-process-ids"></a>Query con ID processo
Gli ID processo (PID) sono riciclati in Windows e riutilizzati per i nuovi processi. Di per sé, non possono servire come identificatori univoci per processi specifici.

Per ottenere un identificatore univoco per un computer specifico, usare l'ID processo insieme all'ora di creazione del processo. Quando si uniscono o si riepilogano i dati relativi a processi, includere le colonne per l'identificatore del computer (`DeviceId` o `DeviceName`), l'ID processo (`ProcessId` o `InitiatingProcessId`) e l'ora di creazione del processo (`ProcessCreationTime` o `InitiatingProcessCreationTime`)

La seguente query di esempio trova i processi che accedono a più di 10 indirizzi IP dalla porta 445 (SMB), possibilmente analizzando le condivisioni file.

Query di esempio:
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
- Usare corrispondenza maiuscole/minuscole. Ad esempio, usare `=~`, `in~`e `contains` anziché `==`, `in`e `contains_cs`
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
## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra i dispositivi, i messaggi di posta elettronica, le app e le identità](advanced-hunting-query-emails-devices.md)
- [Comprensione dello schema](advanced-hunting-schema-tables.md)
