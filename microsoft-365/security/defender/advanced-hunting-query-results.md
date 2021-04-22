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
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="fc6f0-104">Utilizzare i risultati delle query di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="fc6f0-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fc6f0-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-105">**Applies to:**</span></span>
- <span data-ttu-id="fc6f0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc6f0-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="fc6f0-107">Sebbene sia possibile [](advanced-hunting-overview.md) creare query di ricerca avanzate per restituire informazioni molto precise, è anche possibile utilizzare i risultati della query per ottenere ulteriori informazioni e analizzare attività e indicatori specifici.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-107">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="fc6f0-108">È possibile eseguire le azioni seguenti sui risultati della query:</span><span class="sxs-lookup"><span data-stu-id="fc6f0-108">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="fc6f0-109">Visualizzare i risultati come tabella o grafico</span><span class="sxs-lookup"><span data-stu-id="fc6f0-109">View results as a table or chart</span></span>
- <span data-ttu-id="fc6f0-110">Esportare tabelle e grafici</span><span class="sxs-lookup"><span data-stu-id="fc6f0-110">Export tables and charts</span></span>
- <span data-ttu-id="fc6f0-111">Drill-down per informazioni dettagliate sulle entità</span><span class="sxs-lookup"><span data-stu-id="fc6f0-111">Drill down to detailed entity information</span></span>
- <span data-ttu-id="fc6f0-112">Modificare le query direttamente dai risultati o applicare filtri</span><span class="sxs-lookup"><span data-stu-id="fc6f0-112">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="fc6f0-113">Visualizzare i risultati della query come tabella o grafico</span><span class="sxs-lookup"><span data-stu-id="fc6f0-113">View query results as a table or chart</span></span>
<span data-ttu-id="fc6f0-114">Per impostazione predefinita, la ricerca avanzata visualizza i risultati delle query come dati tabulari.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-114">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="fc6f0-115">È inoltre possibile visualizzare gli stessi dati di un grafico.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-115">You can also display the same data as a chart.</span></span> <span data-ttu-id="fc6f0-116">La ricerca avanzata supporta le visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc6f0-116">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="fc6f0-117">Tipo visualizzazione</span><span class="sxs-lookup"><span data-stu-id="fc6f0-117">View type</span></span> | <span data-ttu-id="fc6f0-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fc6f0-118">Description</span></span> |
| -- | -- |
| <span data-ttu-id="fc6f0-119">**tavolo**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-119">**Table**</span></span> | <span data-ttu-id="fc6f0-120">Visualizza i risultati della query in formato tabulare</span><span class="sxs-lookup"><span data-stu-id="fc6f0-120">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="fc6f0-121">**Istogramma**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-121">**Column chart**</span></span> | <span data-ttu-id="fc6f0-122">Esegue il rendering di una serie di elementi univoci sull'asse x come barre verticali le cui altezze rappresentano valori numerici di un altro campo</span><span class="sxs-lookup"><span data-stu-id="fc6f0-122">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="fc6f0-123">**Istogramma in pila**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-123">**Stacked column chart**</span></span> | <span data-ttu-id="fc6f0-124">Esegue il rendering di una serie di elementi univoci sull'asse x come barre verticali in pila le cui altezze rappresentano valori numerici di uno o più campi</span><span class="sxs-lookup"><span data-stu-id="fc6f0-124">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="fc6f0-125">**Grafico a torta**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-125">**Pie chart**</span></span> | <span data-ttu-id="fc6f0-126">Esegue il rendering delle torta di sezione che rappresentano elementi univoci.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-126">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="fc6f0-127">Le dimensioni di ogni torta rappresentano valori numerici di un altro campo.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-127">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="fc6f0-128">**Grafico ad anello**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-128">**Donut chart**</span></span> | <span data-ttu-id="fc6f0-129">Esegue il rendering di archi di sezione che rappresentano elementi univoci.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-129">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="fc6f0-130">La lunghezza di ogni arco rappresenta valori numerici di un altro campo.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-130">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="fc6f0-131">**Grafico a linee**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-131">**Line chart**</span></span> | <span data-ttu-id="fc6f0-132">Traccia valori numerici per una serie di elementi univoci e connette i valori tracciati</span><span class="sxs-lookup"><span data-stu-id="fc6f0-132">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="fc6f0-133">**Grafico a dispersione**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-133">**Scatter chart**</span></span> | <span data-ttu-id="fc6f0-134">Traccia valori numerici per una serie di elementi univoci</span><span class="sxs-lookup"><span data-stu-id="fc6f0-134">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="fc6f0-135">**Grafico ad area**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-135">**Area chart**</span></span> | <span data-ttu-id="fc6f0-136">Traccia valori numerici per una serie di elementi univoci e riempie le sezioni sotto i valori tracciati</span><span class="sxs-lookup"><span data-stu-id="fc6f0-136">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="fc6f0-137">Creare query per grafici efficaci</span><span class="sxs-lookup"><span data-stu-id="fc6f0-137">Construct queries for effective charts</span></span>
<span data-ttu-id="fc6f0-138">Durante il rendering dei grafici, la ricerca avanzata identifica automaticamente le colonne di interesse e i valori numerici da aggregare.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-138">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="fc6f0-139">Per ottenere grafici significativi, creare le query per restituire i valori specifici che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-139">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="fc6f0-140">Ecco alcune query di esempio e i grafici risultanti.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-140">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="fc6f0-141">Avvisi per gravità</span><span class="sxs-lookup"><span data-stu-id="fc6f0-141">Alerts by severity</span></span>
<span data-ttu-id="fc6f0-142">Utilizzare `summarize` l'operatore per ottenere un conteggio numerico dei valori che si desidera creare nel grafico.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-142">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="fc6f0-143">La query seguente utilizza `summarize` l'operatore per ottenere il numero di avvisi in base alla gravità.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-143">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="fc6f0-144">Quando si esegue il rendering dei risultati, un istogramma visualizza ogni valore di gravità come colonna separata:</span><span class="sxs-lookup"><span data-stu-id="fc6f0-144">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="fc6f0-145">![Immagine dei risultati delle query di ricerca avanzata visualizzati come istogramma Risultati query per avvisi per ](../../media/advanced-hunting-column-chart.jpg)
 *gravità visualizzati come istogramma*</span><span class="sxs-lookup"><span data-stu-id="fc6f0-145">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="fc6f0-146">Gravità dell'avviso in base al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="fc6f0-146">Alert severity by operating system</span></span>
<span data-ttu-id="fc6f0-147">È inoltre possibile utilizzare `summarize` l'operatore per preparare i risultati per la creazione di grafici di valori da più campi.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-147">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="fc6f0-148">Ad esempio, potrebbe essere necessario comprendere in che modo le gravità degli avvisi vengono distribuite tra sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-148">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="fc6f0-149">Nella query seguente viene utilizzato un operatore per estrarre le informazioni sul sistema operativo dalla tabella e quindi viene utilizzato per contare i valori `join` `DeviceInfo` nelle colonne e `summarize` `OSPlatform` `Severity` :</span><span class="sxs-lookup"><span data-stu-id="fc6f0-149">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="fc6f0-150">Questi risultati sono visualizzati meglio usando un istogramma in pila:</span><span class="sxs-lookup"><span data-stu-id="fc6f0-150">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="fc6f0-151">![Immagine dei risultati delle query di ricerca avanzata visualizzati come grafico in pila Risultati della query per gli avvisi del sistema operativo e gravità visualizzati come ](../../media/advanced-hunting-stacked-chart.jpg)
 *grafico in pila*</span><span class="sxs-lookup"><span data-stu-id="fc6f0-151">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="fc6f0-152">Messaggi di posta elettronica di phishing nei dieci domini dei mittenti principali</span><span class="sxs-lookup"><span data-stu-id="fc6f0-152">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="fc6f0-153">Se si ha a che fare con un elenco di valori non finiti, è possibile utilizzare l'operatore per creare un grafico solo dei valori con la maggior `Top` parte delle istanze.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-153">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="fc6f0-154">Ad esempio, per ottenere i primi dieci domini di mittente con il maggior numero di messaggi di posta elettronica di phishing, utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="fc6f0-154">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
<span data-ttu-id="fc6f0-155">Usa la visualizzazione grafico a torta per mostrare in modo efficace la distribuzione tra i domini principali:</span><span class="sxs-lookup"><span data-stu-id="fc6f0-155">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="fc6f0-156">![Immagine dei risultati delle query di ricerca avanzata visualizzati come grafico a torta Grafico a torta che mostra la distribuzione dei messaggi di posta elettronica ](../../media/advanced-hunting-pie-chart.jpg)
 *di phishing nei domini dei mittenti principali*</span><span class="sxs-lookup"><span data-stu-id="fc6f0-156">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="fc6f0-157">Attività sui file nel tempo</span><span class="sxs-lookup"><span data-stu-id="fc6f0-157">File activities over time</span></span>
<span data-ttu-id="fc6f0-158">Utilizzando `summarize` l'operatore con `bin()` la funzione, è possibile verificare la presenza di eventi che coinvolgono un determinato indicatore nel tempo.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-158">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="fc6f0-159">La query seguente conta gli eventi che coinvolgono il file a intervalli di 30 minuti per mostrare picchi di attività `invoice.doc` correlati al file:</span><span class="sxs-lookup"><span data-stu-id="fc6f0-159">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="fc6f0-160">Il grafico a linee seguente evidenzia chiaramente i periodi di tempo con più attività che `invoice.doc` coinvolgono:</span><span class="sxs-lookup"><span data-stu-id="fc6f0-160">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="fc6f0-161">![Immagine dei risultati delle query di ricerca avanzata visualizzati come grafico a linee Grafico a linee che mostra il numero di eventi che coinvolgono ](../../media/advanced-hunting-line-chart.jpg)
 *un file nel tempo*</span><span class="sxs-lookup"><span data-stu-id="fc6f0-161">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="fc6f0-162">Esportare tabelle e grafici</span><span class="sxs-lookup"><span data-stu-id="fc6f0-162">Export tables and charts</span></span>
<span data-ttu-id="fc6f0-163">Dopo aver eseguito una query, selezionare **Esporta** per salvare i risultati nel file locale.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-163">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="fc6f0-164">La visualizzazione scelta determina la modalità di esportazione dei risultati:</span><span class="sxs-lookup"><span data-stu-id="fc6f0-164">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="fc6f0-165">**Visualizzazione tabella:** i risultati della query vengono esportati in formato tabulare come cartella di lavoro di Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="fc6f0-165">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="fc6f0-166">**Qualsiasi grafico:** i risultati della query vengono esportati come immagine JPEG del grafico sottoposto a rendering</span><span class="sxs-lookup"><span data-stu-id="fc6f0-166">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="fc6f0-167">Eseguire il drill-down dai risultati della query</span><span class="sxs-lookup"><span data-stu-id="fc6f0-167">Drill down from query results</span></span>
<span data-ttu-id="fc6f0-168">Per esaminare rapidamente un record nei risultati della query, selezionare la riga corrispondente per aprire il **pannello Esamina record.**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-168">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="fc6f0-169">Il pannello fornisce le informazioni seguenti in base al record selezionato:</span><span class="sxs-lookup"><span data-stu-id="fc6f0-169">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="fc6f0-170">**Asset:** visualizzazione riepilogata degli asset principali (cassette postali, dispositivi e utenti) presenti nel record, arricchita da informazioni disponibili, ad esempio livelli di rischio ed esposizione</span><span class="sxs-lookup"><span data-stu-id="fc6f0-170">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="fc6f0-171">**Albero dei processi:** generato per i record con informazioni sul processo e arricchito usando le informazioni contestuali disponibili; in generale, le query che restituiscono più colonne possono comportare alberi di processo più ricchi.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-171">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="fc6f0-172">**Tutti i** dettagli: tutti i valori delle colonne del record</span><span class="sxs-lookup"><span data-stu-id="fc6f0-172">**All details** — all the values from the columns in the record</span></span>  

![Immagine del record selezionato con il pannello per l'ispezione del record](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="fc6f0-174">Per visualizzare ulteriori informazioni su un'entità specifica nei risultati della query, ad esempio un computer, un file, un utente, un indirizzo IP o un URL, selezionare l'identificatore dell'entità per aprire una pagina del profilo dettagliata per tale entità.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-174">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="fc6f0-175">Perfezionare le query dai risultati</span><span class="sxs-lookup"><span data-stu-id="fc6f0-175">Tweak your queries from the results</span></span>
<span data-ttu-id="fc6f0-176">Fare clic con il pulsante destro del mouse su un valore nel set di risultati per migliorare rapidamente la query.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-176">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="fc6f0-177">È possibile usare le opzioni per:</span><span class="sxs-lookup"><span data-stu-id="fc6f0-177">You can use the options to:</span></span>

- <span data-ttu-id="fc6f0-178">Cercare in modo esplicito il valore selezionato (`==`)</span><span class="sxs-lookup"><span data-stu-id="fc6f0-178">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="fc6f0-179">Escludere il valore selezionato dalla query (`!=`)</span><span class="sxs-lookup"><span data-stu-id="fc6f0-179">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="fc6f0-180">Per aggiungere il valore alla query, è possibile usare gli operatori più avanzati, come `contains`, `starts with` e `ends with`</span><span class="sxs-lookup"><span data-stu-id="fc6f0-180">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Immagine del set di risultati di ricerca avanzata](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="fc6f0-182">Filtrare i risultati della query</span><span class="sxs-lookup"><span data-stu-id="fc6f0-182">Filter the query results</span></span>
<span data-ttu-id="fc6f0-183">I filtri visualizzati a destra forniscono un riepilogo del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-183">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="fc6f0-184">Ogni colonna ha una propria sezione in cui sono elencati i valori distinti individuati per quella colonna e il numero di istanze.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-184">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="fc6f0-185">Per affinare la query, selezionare i pulsanti o sui valori che si desidera includere o escludere e quindi `+` `-` selezionare Esegui **query.**</span><span class="sxs-lookup"><span data-stu-id="fc6f0-185">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Immagine del filtro di ricerca avanzata](../../media/advanced-hunting-filter.png)

<span data-ttu-id="fc6f0-187">Dopo avere applicato il filtro per modificare la query e aver eseguito la query, i risultati vengono aggiornati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="fc6f0-187">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc6f0-188">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fc6f0-188">Related topics</span></span>
- [<span data-ttu-id="fc6f0-189">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="fc6f0-189">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="fc6f0-190">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="fc6f0-190">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="fc6f0-191">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="fc6f0-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="fc6f0-192">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="fc6f0-192">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="fc6f0-193">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="fc6f0-193">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="fc6f0-194">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="fc6f0-194">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="fc6f0-195">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="fc6f0-195">Custom detections overview</span></span>](custom-detections-overview.md)
