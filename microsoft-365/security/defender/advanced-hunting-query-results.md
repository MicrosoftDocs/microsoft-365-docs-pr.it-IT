---
title: Utilizzare i risultati delle query di ricerca avanzata in Microsoft 365 Defender
description: Ottenere il massimo dai risultati delle query restituiti dalla ricerca avanzata in Microsoft 365 Defender
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, rilevamenti personalizzati, schema, kusto, visualizzazione, grafico, filtri, drill-down
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 34880c870cdf398ab1565f7f532ac95a6fde475d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932930"
---
# <a name="work-with-advanced-hunting-query-results"></a>Utilizzare i risultati delle query di ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

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
AlertInfo
| summarize Total = count() by Severity
```
Quando si esegue il rendering dei risultati, un istogramma visualizza ogni valore di gravità come colonna separata:

![Immagine dei risultati delle query di ricerca avanzata visualizzati come istogramma Risultati query per avvisi per ](../../media/advanced-hunting-column-chart.jpg)
 *gravità visualizzati come istogramma*

#### <a name="alert-severity-by-operating-system"></a>Gravità dell'avviso in base al sistema operativo
È inoltre possibile utilizzare `summarize` l'operatore per preparare i risultati per la creazione di grafici di valori da più campi. Ad esempio, potrebbe essere necessario comprendere in che modo le gravità degli avvisi vengono distribuite tra sistemi operativi. 

Nella query seguente viene utilizzato un operatore per estrarre le informazioni sul sistema operativo dalla tabella e quindi viene utilizzato per contare i valori `join` `DeviceInfo` nelle colonne e `summarize` `OSPlatform` `Severity` :

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Questi risultati sono visualizzati meglio usando un istogramma in pila:

![Immagine dei risultati delle query di ricerca avanzata visualizzati come grafico in pila Risultati della query per gli avvisi del sistema operativo e gravità visualizzati come ](../../media/advanced-hunting-stacked-chart.jpg)
 *grafico in pila*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Messaggi di posta elettronica di phishing nei dieci domini dei mittenti principali
Se si ha a che fare con un elenco di valori non finiti, è possibile utilizzare l'operatore per creare un grafico solo dei valori con la maggior `Top` parte delle istanze. Ad esempio, per ottenere i primi dieci domini di mittente con il maggior numero di messaggi di posta elettronica di phishing, utilizzare la query seguente:

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
Usa la visualizzazione grafico a torta per mostrare in modo efficace la distribuzione tra i domini principali:

![Immagine dei risultati delle query di ricerca avanzata visualizzati come grafico a torta Grafico a torta che mostra la distribuzione dei messaggi di posta elettronica ](../../media/advanced-hunting-pie-chart.jpg)
 *di phishing nei domini dei mittenti principali*

#### <a name="file-activities-over-time"></a>Attività sui file nel tempo
Utilizzando `summarize` l'operatore con `bin()` la funzione, è possibile verificare la presenza di eventi che coinvolgono un determinato indicatore nel tempo. La query seguente conta gli eventi che coinvolgono il file a intervalli di 30 minuti per mostrare picchi di attività `invoice.doc` correlati al file:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
Il grafico a linee seguente evidenzia chiaramente i periodi di tempo con più attività che `invoice.doc` coinvolgono: 

![Immagine dei risultati delle query di ricerca avanzata visualizzati come grafico a linee Grafico a linee che mostra il numero di eventi che coinvolgono ](../../media/advanced-hunting-line-chart.jpg)
 *un file nel tempo*


## <a name="export-tables-and-charts"></a>Esportare tabelle e grafici
Dopo aver eseguito una query, selezionare **Esporta** per salvare i risultati nel file locale. La visualizzazione scelta determina la modalità di esportazione dei risultati:

- **Visualizzazione tabella:** i risultati della query vengono esportati in formato tabulare come cartella di lavoro di Microsoft Excel
- **Qualsiasi grafico:** i risultati della query vengono esportati come immagine JPEG del grafico sottoposto a rendering

## <a name="drill-down-from-query-results"></a>Eseguire il drill-down dai risultati della query
Per esaminare rapidamente un record nei risultati della query, selezionare la riga corrispondente per aprire il **pannello Esamina record.** Il pannello fornisce le informazioni seguenti in base al record selezionato:

- **Asset:** visualizzazione riepilogata degli asset principali (cassette postali, dispositivi e utenti) presenti nel record, arricchita da informazioni disponibili, ad esempio livelli di rischio ed esposizione
- **Albero dei processi:** generato per i record con informazioni sul processo e arricchito usando le informazioni contestuali disponibili; in generale, le query che restituiscono più colonne possono comportare alberi di processo più ricchi.
- **Tutti i** dettagli: tutti i valori delle colonne del record  

![Immagine del record selezionato con il pannello per l'ispezione del record](../../media/mtp-ah/inspect-record.png)

Per visualizzare ulteriori informazioni su un'entità specifica nei risultati della query, ad esempio un computer, un file, un utente, un indirizzo IP o un URL, selezionare l'identificatore dell'entità per aprire una pagina del profilo dettagliata per tale entità.

## <a name="tweak-your-queries-from-the-results"></a>Perfezionare le query dai risultati
Fare clic con il pulsante destro del mouse su un valore nel set di risultati per migliorare rapidamente la query. È possibile usare le opzioni per:

- Cercare in modo esplicito il valore selezionato (`==`)
- Escludere il valore selezionato dalla query (`!=`)
- Per aggiungere il valore alla query, è possibile usare gli operatori più avanzati, come `contains`, `starts with` e `ends with` 

![Immagine del set di risultati di ricerca avanzata](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrare i risultati della query
I filtri visualizzati a destra forniscono un riepilogo del set di risultati. Ogni colonna ha una propria sezione in cui sono elencati i valori distinti individuati per quella colonna e il numero di istanze.

Per affinare la query, selezionare i pulsanti o sui valori che si desidera includere o escludere e quindi `+` `-` selezionare Esegui **query.**

![Immagine del filtro di ricerca avanzata](../../media/advanced-hunting-filter.png)

Dopo avere applicato il filtro per modificare la query e aver eseguito la query, i risultati vengono aggiornati di conseguenza.

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della rilevazione avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Utilizzare le query condivise](advanced-hunting-shared-queries.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
- [Panoramica dei rilevamenti personalizzati](custom-detections-overview.md)
