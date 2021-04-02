---
title: Utilizzare i risultati delle query di ricerca avanzata in Microsoft Defender ATP
description: Ottenere il massimo dai risultati delle query restituiti dalla ricerca avanzata in Microsoft Defender ATP
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, ricerca wdatp, query, telemetria, rilevamenti personalizzati, schema, kusto, visualizzazione, grafico, filtri, drill-down
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4abec618a79704804b5e3349f5c4c5a4827d35ef
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499438"
---
# <a name="work-with-advanced-hunting-query-results"></a>Utilizzare i risultati delle query di ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Sebbene sia possibile [](advanced-hunting-overview.md) creare query di ricerca avanzate per restituire informazioni molto precise, è anche possibile utilizzare i risultati della query per ottenere ulteriori informazioni e analizzare attività e indicatori specifici. È possibile eseguire le azioni seguenti sui risultati della query:

- Visualizzare i risultati come tabella o grafico
- Esportare tabelle e grafici
- Drill-down per informazioni dettagliate sulle entità
- Modificare le query direttamente dai risultati o applicare filtri

## <a name="view-query-results-as-a-table-or-chart"></a>Visualizzare i risultati della query come tabella o grafico
Per impostazione predefinita, la ricerca avanzata visualizza i risultati delle query come dati tabulari. È inoltre possibile visualizzare gli stessi dati di un grafico. La ricerca avanzata supporta le visualizzazioni seguenti:

| Tipo visualizzazione | Descrizione |
| -- | -- |
| **tavolo** | Visualizza i risultati della query in formato tabulare |
| **Istogramma** | Esegue il rendering di una serie di elementi univoci sull'asse x come barre verticali le cui altezze rappresentano valori numerici di un altro campo |
| **Istogramma in pila** | Esegue il rendering di una serie di elementi univoci sull'asse x come barre verticali in pila le cui altezze rappresentano valori numerici di uno o più campi |
| **Grafico a torta** | Esegue il rendering delle torta di sezione che rappresentano elementi univoci. Le dimensioni di ogni torta rappresentano valori numerici di un altro campo. |
| **Grafico ad anello** | Esegue il rendering di archi di sezione che rappresentano elementi univoci. La lunghezza di ogni arco rappresenta valori numerici di un altro campo. |
| **Grafico a linee** | Traccia valori numerici per una serie di elementi univoci e connette i valori tracciati |
| **Grafico a dispersione** | Traccia valori numerici per una serie di elementi univoci |
| **Grafico ad area** | Traccia valori numerici per una serie di elementi univoci e riempie le sezioni sotto i valori tracciati |

### <a name="construct-queries-for-effective-charts"></a>Creare query per grafici efficaci
Durante il rendering dei grafici, la ricerca avanzata identifica automaticamente le colonne di interesse e i valori numerici da aggregare. Per ottenere grafici significativi, creare le query per restituire i valori specifici che si desidera visualizzare. Ecco alcune query di esempio e i grafici risultanti.

#### <a name="alerts-by-severity"></a>Avvisi per gravità
Utilizzare `summarize` l'operatore per ottenere un conteggio numerico dei valori che si desidera creare nel grafico. La query seguente utilizza `summarize` l'operatore per ottenere il numero di avvisi in base alla gravità.

```kusto
DeviceAlertEvents
| summarize Total = count() by Severity
```
Quando si esegue il rendering dei risultati, un istogramma visualizza ogni valore di gravità come colonna separata:

![Immagine dei risultati delle query di ricerca avanzata visualizzati come istogramma Risultati query per avvisi per ](images/advanced-hunting-column-chart.jpg)
 *gravità visualizzati come istogramma*

#### <a name="alert-severity-by-operating-system"></a>Gravità dell'avviso in base al sistema operativo
È inoltre possibile utilizzare `summarize` l'operatore per preparare i risultati per la creazione di grafici di valori da più campi. Ad esempio, potrebbe essere necessario comprendere in che modo le gravità degli avvisi vengono distribuite tra sistemi operativi. 

Nella query seguente viene utilizzato un operatore per estrarre le informazioni sul sistema operativo dalla tabella e quindi viene utilizzato per contare i valori `join` `DeviceInfo` nelle colonne e `summarize` `OSPlatform` `Severity` :

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity
```
Questi risultati sono visualizzati meglio usando un istogramma in pila:

![Immagine dei risultati delle query di ricerca avanzata visualizzati come grafico in pila Risultati della query per gli avvisi del sistema operativo e gravità visualizzati come ](images/advanced-hunting-stacked-chart.jpg)
 *grafico in pila*

#### <a name="top-ten-device-groups-with-alerts"></a>Primi dieci gruppi di dispositivi con avvisi
Se si ha a che fare con un elenco di valori non finiti, è possibile utilizzare l'operatore per creare un grafico solo dei valori con la maggior `Top` parte delle istanze. Ad esempio, per ottenere i primi dieci gruppi di dispositivi con il maggior numero di avvisi, usa la query seguente:

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by MachineGroup
| top 10 by Count
```
Usa la visualizzazione grafico a torta per mostrare in modo efficace la distribuzione tra i gruppi principali:

![Immagine dei risultati delle query di ricerca avanzata visualizzati come grafico a torta Grafico a torta che mostra ](images/advanced-hunting-pie-chart.jpg)
 *la distribuzione degli avvisi tra i gruppi di dispositivi*

#### <a name="malware-detections-over-time"></a>Rilevamenti di malware nel tempo
Utilizzando `summarize` l'operatore con `bin()` la funzione, è possibile verificare la presenza di eventi che coinvolgono un determinato indicatore nel tempo. La query seguente conta i rilevamenti di un file di test EICAR a intervalli di 30 minuti per mostrare picchi nei rilevamenti di tale file:

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| where SHA1 == "3395856ce81f2b7382dee72602f798b642f14140"
| summarize Detections = count() by bin(Timestamp, 30m)
```
Il grafico a linee seguente evidenzia chiaramente i periodi di tempo con più rilevamenti del malware di test: 

![Immagine dei risultati delle query di ricerca avanzata visualizzati come grafico a linee Grafico a linee che mostra il numero di rilevamenti di ](images/advanced-hunting-line-chart.jpg)
 *un malware di test nel tempo*


## <a name="export-tables-and-charts"></a>Esportare tabelle e grafici
Dopo aver eseguito una query, selezionare **Esporta** per salvare i risultati nel file locale. La visualizzazione scelta determina la modalità di esportazione dei risultati:

- **Visualizzazione tabella:** i risultati della query vengono esportati in formato tabulare come cartella di lavoro di Microsoft Excel
- **Qualsiasi grafico:** i risultati della query vengono esportati come immagine JPEG del grafico sottoposto a rendering

## <a name="drill-down-from-query-results"></a>Eseguire il drill-down dai risultati della query
Per visualizzare ulteriori informazioni sulle entità, ad esempio dispositivi, file, utenti, indirizzi IP e URL, nei risultati della query fare semplicemente clic sull'identificatore dell'entità. Verrà aperta una pagina del profilo dettagliata per l'entità selezionata.

Per esaminare rapidamente un record nei risultati della query, selezionare la riga corrispondente per aprire il pannello Esamina record. Il pannello fornisce le informazioni seguenti in base al record selezionato:

- **Asset:** visualizzazione riepilogata degli asset principali (cassette postali, dispositivi e utenti) presenti nel record, arricchita da informazioni disponibili, ad esempio livelli di rischio ed esposizione
- **Albero del processo:** grafico generato per i record con informazioni sul processo e arricchito utilizzando le informazioni contestuali disponibili; in generale, le query che restituiscono più colonne possono comportare alberi di processo più ricchi.
- **Tutti i** dettagli: elenca tutti i valori delle colonne del record

## <a name="tweak-your-queries-from-the-results"></a>Perfezionare le query dai risultati
Fare clic con il pulsante destro del mouse su un valore nel set di risultati per migliorare rapidamente la query. È possibile usare le opzioni per:

- Cercare in modo esplicito il valore selezionato (`==`)
- Escludere il valore selezionato dalla query (`!=`)
- Per aggiungere il valore alla query, è possibile usare gli operatori più avanzati, come `contains`, `starts with` e `ends with` 

![Immagine del set di risultati di ricerca avanzata](images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrare i risultati della query
I filtri visualizzati nel riquadro destro forniscono un riepilogo del set di risultati. Ogni colonna ha una propria sezione nel riquadro, ognuna delle quali elenca i valori trovati in tale colonna e il numero di istanze.

Per affinare la query, selezionare i pulsanti o sui valori `+` che si desidera includere o `-` escludere. Selezionare quindi **Esegui query**.

![Immagine del filtro di ricerca avanzata](images/advanced-hunting-filter.png)

Dopo avere applicato il filtro per modificare la query e aver eseguito la query, i risultati vengono aggiornati di conseguenza.

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Comprensione dello schema](advanced-hunting-schema-reference.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica dei rilevamenti personalizzati](overview-custom-detections.md)
