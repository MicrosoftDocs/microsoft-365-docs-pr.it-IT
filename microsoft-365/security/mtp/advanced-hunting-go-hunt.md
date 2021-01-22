---
title: Ottenere informazioni pertinenti su un'entità con risposta
description: Informazioni su come usare lo strumento di ricerca avanzata per eseguire rapidamente query per informazioni pertinenti su un'entità o un evento tramite la ricerca avanzata.
keywords: ricerca avanzata, incidente, pivot, entità, andare a cercare, eventi rilevanti, ricerca delle minacce, ricerca delle minacce informatiche, ricerca, query, telemetria, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e707fe8b3dff40d0698630cd0592b297042e5fb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929506"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Ricerca rapida di informazioni su entità o eventi con risposta

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Con *l'azione di ricerca* in viaggio, è possibile analizzare rapidamente eventi e vari tipi di entità utilizzando potenti funzionalità di ricerca avanzata basate [su](advanced-hunting-overview.md) query. Questa azione esegue automaticamente una query di ricerca avanzata per trovare informazioni rilevanti sull'evento o sull'entità selezionata.

*L'azione di risposta* go è disponibile in varie sezioni del Centro sicurezza ogni volta che vengono visualizzati i dettagli dell'evento o dell'entità. Ad esempio, è possibile utilizzare *la risposta di andare* dalle sezioni seguenti:

- Nella pagina [dell'evento](investigate-incidents.md#incident-overview)imprevisto è possibile esaminare i dettagli relativi a utenti, dispositivi e molte altre entità associate a un evento imprevisto. Quando si seleziona un'entità, si ottengono informazioni aggiuntive e varie azioni che è possibile eseguire su tale entità. Nell'esempio seguente viene selezionata una cassetta postale, che mostra i dettagli della cassetta postale e l'opzione per cercare ulteriori informazioni sulla cassetta postale.

    ![Immagine che mostra i dettagli della cassetta postale con l'opzione di risposta go](../../media/mtp-ah/go-hunt-email.png)

- Nella pagina dell'evento imprevisto puoi anche accedere a un elenco di entità nella scheda delle prove. La selezione di una di queste entità offre un'opzione per cercare rapidamente informazioni su tale entità.

    ![Immagine che mostra il file selezionato con l'opzione vai a risposta nella scheda Prova](../../media/mtp-ah/go-hunt-evidence-file.png)


- Quando visualizzi la sequenza temporale per un dispositivo, puoi selezionare un evento nella sequenza temporale per visualizzare informazioni aggiuntive su tale evento. Dopo aver selezionato un evento, puoi scegliere di cercare altri eventi pertinenti nella ricerca avanzata.

    ![Immagine che mostra i dettagli dell'evento con l'opzione vai a risposta](../../media/mtp-ah/go-hunt-event.png)

Se **si seleziona Vai a ricerca** o Cerca eventi **correlati,** vengono passate query diverse, a seconda che sia stata selezionata un'entità o un evento.

## <a name="query-for-entity-information"></a>Query per informazioni sulle entità
Quando si utilizza *la* ricerca per ricercare informazioni su un utente, un dispositivo o qualsiasi altro tipo di entità, la query controlla in tutte le tabelle dello schema rilevanti gli eventi che coinvolgono tale entità. Per mantenere gestibili i risultati, l'ambito della query è intorno allo stesso periodo di tempo della prima attività degli ultimi 30 giorni che coinvolge l'entità ed è associata all'evento imprevisto.

Ecco un esempio della query di risposta go per un dispositivo:

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a>Tipi di entità supportati
È possibile usare *la risposta dopo* aver selezionato uno di questi tipi di entità:

- File
- Messaggi di posta elettronica
- Cluster di posta elettronica
- Cassette postali
- Utenti
- Dispositivi
- Indirizzi IP
- URL

## <a name="query-for-event-information"></a>Query per informazioni sull'evento
Quando si *utilizza la risposta di* risposta per eseguire una query per ottenere informazioni su un evento della sequenza temporale, la query verifica la presenza di altri eventi in tutte le tabelle di schema rilevanti nel periodo di tempo dell'evento selezionato. Ad esempio, la query seguente elenca gli eventi in varie tabelle dello schema che si sono verificati nello stesso periodo di tempo nello stesso dispositivo:

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a>Modificare la query
Con una certa conoscenza del [linguaggio di query,](advanced-hunting-query-language.md)è possibile modificare la query in base alle proprie preferenze. Ad esempio, è possibile modificare questa riga, che determina le dimensioni dell'intervallo di tempo:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Oltre a modificare la query per ottenere risultati più pertinenti, è anche possibile:
- [Visualizzare i risultati come grafici](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Creare una regola di rilevamento personalizzata](custom-detection-rules.md)

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Regole di rilevamento personalizzate](custom-detection-rules.md)
