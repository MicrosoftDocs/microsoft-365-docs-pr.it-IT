---
title: Utilizzare i risultati delle query di ricerca avanzata in Microsoft 365 Defender
description: Utilizzare al meglio i risultati della query restituiti dalla ricerca avanzata in Microsoft 365 Defender
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
ms.openlocfilehash: eccf93b019baa240a46260a28f3f0bc109345dd4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952597"
---
# <a name="work-with-advanced-hunting-query-results"></a><span data-ttu-id="b4e04-104">Utilizzare i risultati delle query di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="b4e04-104">Work with advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b4e04-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b4e04-105">**Applies to:**</span></span>
- <span data-ttu-id="b4e04-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4e04-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="b4e04-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b4e04-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="b4e04-108">Sebbene sia possibile [](advanced-hunting-overview.md) creare query di ricerca avanzate per restituire informazioni molto precise, è anche possibile utilizzare i risultati della query per ottenere ulteriori informazioni e analizzare attività e indicatori specifici.</span><span class="sxs-lookup"><span data-stu-id="b4e04-108">While you can construct your [advanced hunting](advanced-hunting-overview.md) queries to return very precise information, you can also work with the query results to gain further insight and investigate specific activities and indicators.</span></span> <span data-ttu-id="b4e04-109">È possibile eseguire le azioni seguenti sui risultati della query:</span><span class="sxs-lookup"><span data-stu-id="b4e04-109">You can take the following actions on your query results:</span></span>

- <span data-ttu-id="b4e04-110">Visualizzare i risultati come tabella o grafico</span><span class="sxs-lookup"><span data-stu-id="b4e04-110">View results as a table or chart</span></span>
- <span data-ttu-id="b4e04-111">Esportare tabelle e grafici</span><span class="sxs-lookup"><span data-stu-id="b4e04-111">Export tables and charts</span></span>
- <span data-ttu-id="b4e04-112">Drill-down per informazioni dettagliate sulle entità</span><span class="sxs-lookup"><span data-stu-id="b4e04-112">Drill down to detailed entity information</span></span>
- <span data-ttu-id="b4e04-113">Modificare le query direttamente dai risultati o applicare filtri</span><span class="sxs-lookup"><span data-stu-id="b4e04-113">Tweak your queries directly from the results or apply filters</span></span>

## <a name="view-query-results-as-a-table-or-chart"></a><span data-ttu-id="b4e04-114">Visualizzare i risultati della query come tabella o grafico</span><span class="sxs-lookup"><span data-stu-id="b4e04-114">View query results as a table or chart</span></span>
<span data-ttu-id="b4e04-115">Per impostazione predefinita, la ricerca avanzata visualizza i risultati delle query come dati tabulari.</span><span class="sxs-lookup"><span data-stu-id="b4e04-115">By default, advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="b4e04-116">È inoltre possibile visualizzare gli stessi dati di un grafico.</span><span class="sxs-lookup"><span data-stu-id="b4e04-116">You can also display the same data as a chart.</span></span> <span data-ttu-id="b4e04-117">La ricerca avanzata supporta le visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4e04-117">Advanced hunting supports the following views:</span></span>

| <span data-ttu-id="b4e04-118">Tipo visualizzazione</span><span class="sxs-lookup"><span data-stu-id="b4e04-118">View type</span></span> | <span data-ttu-id="b4e04-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4e04-119">Description</span></span> |
| -- | -- |
| <span data-ttu-id="b4e04-120">**tavolo**</span><span class="sxs-lookup"><span data-stu-id="b4e04-120">**Table**</span></span> | <span data-ttu-id="b4e04-121">Visualizza i risultati della query in formato tabulare</span><span class="sxs-lookup"><span data-stu-id="b4e04-121">Displays the query results in tabular format</span></span> |
| <span data-ttu-id="b4e04-122">**Istogramma**</span><span class="sxs-lookup"><span data-stu-id="b4e04-122">**Column chart**</span></span> | <span data-ttu-id="b4e04-123">Esegue il rendering di una serie di elementi univoci sull'asse x come barre verticali le cui altezze rappresentano valori numerici di un altro campo</span><span class="sxs-lookup"><span data-stu-id="b4e04-123">Renders a series of unique items on the x-axis as vertical bars whose heights represent numeric values from another field</span></span> |
| <span data-ttu-id="b4e04-124">**Istogramma in pila**</span><span class="sxs-lookup"><span data-stu-id="b4e04-124">**Stacked column chart**</span></span> | <span data-ttu-id="b4e04-125">Esegue il rendering di una serie di elementi univoci sull'asse x come barre verticali in pila le cui altezze rappresentano valori numerici di uno o più campi</span><span class="sxs-lookup"><span data-stu-id="b4e04-125">Renders a series of unique items on the x-axis as stacked vertical bars whose heights represent numeric values from one or more other fields</span></span> |
| <span data-ttu-id="b4e04-126">**Grafico a torta**</span><span class="sxs-lookup"><span data-stu-id="b4e04-126">**Pie chart**</span></span> | <span data-ttu-id="b4e04-127">Esegue il rendering delle torta di sezione che rappresentano elementi univoci.</span><span class="sxs-lookup"><span data-stu-id="b4e04-127">Renders sectional pies representing unique items.</span></span> <span data-ttu-id="b4e04-128">Le dimensioni di ogni torta rappresentano valori numerici di un altro campo.</span><span class="sxs-lookup"><span data-stu-id="b4e04-128">The size of each pie represents numeric values from another field.</span></span> |
| <span data-ttu-id="b4e04-129">**Grafico ad anello**</span><span class="sxs-lookup"><span data-stu-id="b4e04-129">**Donut chart**</span></span> | <span data-ttu-id="b4e04-130">Esegue il rendering di archi di sezione che rappresentano elementi univoci.</span><span class="sxs-lookup"><span data-stu-id="b4e04-130">Renders sectional arcs representing unique items.</span></span> <span data-ttu-id="b4e04-131">La lunghezza di ogni arco rappresenta valori numerici di un altro campo.</span><span class="sxs-lookup"><span data-stu-id="b4e04-131">The length of each arc represents numeric values from another field.</span></span> |
| <span data-ttu-id="b4e04-132">**Grafico a linee**</span><span class="sxs-lookup"><span data-stu-id="b4e04-132">**Line chart**</span></span> | <span data-ttu-id="b4e04-133">Traccia valori numerici per una serie di elementi univoci e connette i valori tracciati</span><span class="sxs-lookup"><span data-stu-id="b4e04-133">Plots numeric values for a series of unique items and connects the plotted values</span></span> |
| <span data-ttu-id="b4e04-134">**Grafico a dispersione**</span><span class="sxs-lookup"><span data-stu-id="b4e04-134">**Scatter chart**</span></span> | <span data-ttu-id="b4e04-135">Traccia valori numerici per una serie di elementi univoci</span><span class="sxs-lookup"><span data-stu-id="b4e04-135">Plots numeric values for a series of unique items</span></span> |
| <span data-ttu-id="b4e04-136">**Grafico ad area**</span><span class="sxs-lookup"><span data-stu-id="b4e04-136">**Area chart**</span></span> | <span data-ttu-id="b4e04-137">Traccia valori numerici per una serie di elementi univoci e riempie le sezioni sotto i valori tracciati</span><span class="sxs-lookup"><span data-stu-id="b4e04-137">Plots numeric values for a series of unique items and fills the sections below the plotted values</span></span> |

### <a name="construct-queries-for-effective-charts"></a><span data-ttu-id="b4e04-138">Creare query per grafici efficaci</span><span class="sxs-lookup"><span data-stu-id="b4e04-138">Construct queries for effective charts</span></span>
<span data-ttu-id="b4e04-139">Durante il rendering dei grafici, la ricerca avanzata identifica automaticamente le colonne di interesse e i valori numerici da aggregare.</span><span class="sxs-lookup"><span data-stu-id="b4e04-139">When rendering charts, advanced hunting automatically identifies columns of interest and the numeric values to aggregate.</span></span> <span data-ttu-id="b4e04-140">Per ottenere grafici significativi, creare le query per restituire i valori specifici che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="b4e04-140">To get meaningful charts, construct your queries to return the specific values you want to see visualized.</span></span> <span data-ttu-id="b4e04-141">Ecco alcune query di esempio e i grafici risultanti.</span><span class="sxs-lookup"><span data-stu-id="b4e04-141">Here are some sample queries and the resulting charts.</span></span>

#### <a name="alerts-by-severity"></a><span data-ttu-id="b4e04-142">Avvisi per gravità</span><span class="sxs-lookup"><span data-stu-id="b4e04-142">Alerts by severity</span></span>
<span data-ttu-id="b4e04-143">Utilizzare `summarize` l'operatore per ottenere un conteggio numerico dei valori che si desidera creare nel grafico.</span><span class="sxs-lookup"><span data-stu-id="b4e04-143">Use the `summarize` operator to obtain a numeric count of the values you want to chart.</span></span> <span data-ttu-id="b4e04-144">La query seguente utilizza `summarize` l'operatore per ottenere il numero di avvisi in base alla gravità.</span><span class="sxs-lookup"><span data-stu-id="b4e04-144">The query below uses the `summarize` operator to get the number of alerts by severity.</span></span>

```kusto
AlertInfo
| summarize Total = count() by Severity
```
<span data-ttu-id="b4e04-145">Quando si esegue il rendering dei risultati, un istogramma visualizza ogni valore di gravità come colonna separata:</span><span class="sxs-lookup"><span data-stu-id="b4e04-145">When rendering the results, a column chart displays each severity value as a separate column:</span></span>

<span data-ttu-id="b4e04-146">![Immagine dei risultati delle query di ricerca avanzata visualizzati come istogramma Risultati query per avvisi per ](../../media/advanced-hunting-column-chart.jpg)
 *gravità visualizzati come istogramma*</span><span class="sxs-lookup"><span data-stu-id="b4e04-146">![Image of advanced hunting query results displayed as a column chart](../../media/advanced-hunting-column-chart.jpg)
*Query results for alerts by severity displayed as a column chart*</span></span>

#### <a name="alert-severity-by-operating-system"></a><span data-ttu-id="b4e04-147">Gravità dell'avviso in base al sistema operativo</span><span class="sxs-lookup"><span data-stu-id="b4e04-147">Alert severity by operating system</span></span>
<span data-ttu-id="b4e04-148">È inoltre possibile utilizzare `summarize` l'operatore per preparare i risultati per la creazione di grafici di valori da più campi.</span><span class="sxs-lookup"><span data-stu-id="b4e04-148">You could also use the `summarize` operator to prepare results for charting values from multiple fields.</span></span> <span data-ttu-id="b4e04-149">Ad esempio, potrebbe essere necessario comprendere in che modo le gravità degli avvisi vengono distribuite tra sistemi operativi.</span><span class="sxs-lookup"><span data-stu-id="b4e04-149">For example, you might want to understand how alert severities are distributed across operating systems (OS).</span></span> 

<span data-ttu-id="b4e04-150">Nella query seguente viene utilizzato un operatore per estrarre le informazioni sul sistema operativo dalla tabella e quindi viene utilizzato per contare i valori `join` `DeviceInfo` nelle colonne e `summarize` `OSPlatform` `Severity` :</span><span class="sxs-lookup"><span data-stu-id="b4e04-150">The query below uses a `join` operator to pull in OS information from the `DeviceInfo` table, and then uses `summarize` to count values in both the `OSPlatform` and `Severity` columns:</span></span>

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
<span data-ttu-id="b4e04-151">Questi risultati sono visualizzati meglio usando un istogramma in pila:</span><span class="sxs-lookup"><span data-stu-id="b4e04-151">These results are best visualized using a stacked column chart:</span></span>

<span data-ttu-id="b4e04-152">![Immagine dei risultati delle query di ricerca avanzata visualizzati come grafico in pila Risultati della query per gli avvisi del sistema operativo e gravità visualizzati come ](../../media/advanced-hunting-stacked-chart.jpg)
 *grafico in pila*</span><span class="sxs-lookup"><span data-stu-id="b4e04-152">![Image of advanced hunting query results displayed as a stacked chart](../../media/advanced-hunting-stacked-chart.jpg)
*Query results for alerts by OS and severity displayed as a stacked chart*</span></span>

#### <a name="phishing-emails-across-top-ten-sender-domains"></a><span data-ttu-id="b4e04-153">Messaggi di posta elettronica di phishing nei dieci domini dei mittenti principali</span><span class="sxs-lookup"><span data-stu-id="b4e04-153">Phishing emails across top ten sender domains</span></span>
<span data-ttu-id="b4e04-154">Se si ha a che fare con un elenco di valori non finiti, è possibile utilizzare l'operatore per creare un grafico solo dei valori con la maggior `Top` parte delle istanze.</span><span class="sxs-lookup"><span data-stu-id="b4e04-154">If you're dealing with a list of values that isn’t finite, you can use the `Top` operator to chart only the values with the most instances.</span></span> <span data-ttu-id="b4e04-155">Ad esempio, per ottenere i primi dieci domini di mittente con il maggior numero di messaggi di posta elettronica di phishing, utilizzare la query seguente:</span><span class="sxs-lookup"><span data-stu-id="b4e04-155">For example, to get the top ten sender domains with the most phishing emails, use the query below:</span></span>

```kusto
EmailEvents
| where ThreatTypes has "Phish" 
| summarize Count = count() by SenderFromDomain 
| top 10 by Count
```
<span data-ttu-id="b4e04-156">Usa la visualizzazione grafico a torta per mostrare in modo efficace la distribuzione tra i domini principali:</span><span class="sxs-lookup"><span data-stu-id="b4e04-156">Use the pie chart view to effectively show distribution across the top domains:</span></span>

<span data-ttu-id="b4e04-157">![Immagine dei risultati delle query di ricerca avanzata visualizzati come grafico a torta Grafico a torta che mostra la distribuzione dei messaggi di posta elettronica ](../../media/advanced-hunting-pie-chart.jpg)
 *di phishing nei domini dei mittenti principali*</span><span class="sxs-lookup"><span data-stu-id="b4e04-157">![Image of advanced hunting query results displayed as a pie chart](../../media/advanced-hunting-pie-chart.jpg)
*Pie chart showing distribution of phishing emails across top sender domains*</span></span>

#### <a name="file-activities-over-time"></a><span data-ttu-id="b4e04-158">Attività sui file nel tempo</span><span class="sxs-lookup"><span data-stu-id="b4e04-158">File activities over time</span></span>
<span data-ttu-id="b4e04-159">Utilizzando `summarize` l'operatore con `bin()` la funzione, è possibile verificare la presenza di eventi che coinvolgono un determinato indicatore nel tempo.</span><span class="sxs-lookup"><span data-stu-id="b4e04-159">Using the `summarize` operator with the `bin()` function, you can check for events involving a particular indicator over time.</span></span> <span data-ttu-id="b4e04-160">La query seguente conta gli eventi che coinvolgono il file a intervalli di 30 minuti per mostrare picchi di attività `invoice.doc` correlati al file:</span><span class="sxs-lookup"><span data-stu-id="b4e04-160">The query below counts events involving the file `invoice.doc` at 30 minute intervals to show spikes in activity related to that file:</span></span>

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
<span data-ttu-id="b4e04-161">Il grafico a linee seguente evidenzia chiaramente i periodi di tempo con più attività che `invoice.doc` coinvolgono:</span><span class="sxs-lookup"><span data-stu-id="b4e04-161">The line chart below clearly highlights time periods with more activity involving `invoice.doc`:</span></span> 

<span data-ttu-id="b4e04-162">![Immagine dei risultati delle query di ricerca avanzata visualizzati come grafico a linee Grafico a linee che mostra il numero di eventi che coinvolgono ](../../media/advanced-hunting-line-chart.jpg)
 *un file nel tempo*</span><span class="sxs-lookup"><span data-stu-id="b4e04-162">![Image of advanced hunting query results displayed as a line chart](../../media/advanced-hunting-line-chart.jpg)
*Line chart showing the number of events involving a file over time*</span></span>


## <a name="export-tables-and-charts"></a><span data-ttu-id="b4e04-163">Esportare tabelle e grafici</span><span class="sxs-lookup"><span data-stu-id="b4e04-163">Export tables and charts</span></span>
<span data-ttu-id="b4e04-164">Dopo aver eseguito una query, selezionare **Esporta** per salvare i risultati nel file locale.</span><span class="sxs-lookup"><span data-stu-id="b4e04-164">After running a query, select **Export** to save the results to local file.</span></span> <span data-ttu-id="b4e04-165">La visualizzazione scelta determina la modalità di esportazione dei risultati:</span><span class="sxs-lookup"><span data-stu-id="b4e04-165">Your chosen view determines how the results are exported:</span></span>

- <span data-ttu-id="b4e04-166">**Visualizzazione tabella:** i risultati della query vengono esportati in formato tabulare come Microsoft Excel cartella di lavoro</span><span class="sxs-lookup"><span data-stu-id="b4e04-166">**Table view** — the query results are exported in tabular form as a Microsoft Excel workbook</span></span>
- <span data-ttu-id="b4e04-167">**Qualsiasi grafico:** i risultati della query vengono esportati come immagine JPEG del grafico sottoposto a rendering</span><span class="sxs-lookup"><span data-stu-id="b4e04-167">**Any chart** — the query results are exported as a JPEG image of the rendered chart</span></span>

## <a name="drill-down-from-query-results"></a><span data-ttu-id="b4e04-168">Eseguire il drill-down dai risultati della query</span><span class="sxs-lookup"><span data-stu-id="b4e04-168">Drill down from query results</span></span>
<span data-ttu-id="b4e04-169">Per esaminare rapidamente un record nei risultati della query, selezionare la riga corrispondente per aprire il **pannello Esamina record.**</span><span class="sxs-lookup"><span data-stu-id="b4e04-169">To quickly inspect a record in your query results, select the corresponding row to open the **Inspect record** panel.</span></span> <span data-ttu-id="b4e04-170">Il pannello fornisce le informazioni seguenti in base al record selezionato:</span><span class="sxs-lookup"><span data-stu-id="b4e04-170">The panel provides the following information based on the selected record:</span></span>

- <span data-ttu-id="b4e04-171">**Asset:** visualizzazione riepilogata degli asset principali (cassette postali, dispositivi e utenti) presenti nel record, arricchita da informazioni disponibili, ad esempio livelli di rischio ed esposizione</span><span class="sxs-lookup"><span data-stu-id="b4e04-171">**Assets** — summarized view of the main assets (mailboxes, devices, and users) found in the record, enriched with available information, such as risk and exposure levels</span></span>
- <span data-ttu-id="b4e04-172">**Albero dei processi:** generato per i record con informazioni sul processo e arricchito usando le informazioni contestuali disponibili; in generale, le query che restituiscono più colonne possono comportare alberi di processo più ricchi.</span><span class="sxs-lookup"><span data-stu-id="b4e04-172">**Process tree** — generated for records with process information and enriched using available contextual information; in general, queries that return more columns can result in richer process trees.</span></span>
- <span data-ttu-id="b4e04-173">**Tutti i** dettagli: tutti i valori delle colonne del record</span><span class="sxs-lookup"><span data-stu-id="b4e04-173">**All details** — all the values from the columns in the record</span></span>  

![Immagine del record selezionato con il pannello per l'ispezione del record](../../media/mtp-ah/inspect-record.png)

<span data-ttu-id="b4e04-175">Per visualizzare ulteriori informazioni su un'entità specifica nei risultati della query, ad esempio un computer, un file, un utente, un indirizzo IP o un URL, selezionare l'identificatore dell'entità per aprire una pagina del profilo dettagliata per tale entità.</span><span class="sxs-lookup"><span data-stu-id="b4e04-175">To view more information about a specific entity in your query results, such as a machine, file, user, IP address, or URL, select the entity identifier to open a detailed profile page for that entity.</span></span>

## <a name="tweak-your-queries-from-the-results"></a><span data-ttu-id="b4e04-176">Perfezionare le query dai risultati</span><span class="sxs-lookup"><span data-stu-id="b4e04-176">Tweak your queries from the results</span></span>
<span data-ttu-id="b4e04-177">Fare clic con il pulsante destro del mouse su un valore nel set di risultati per migliorare rapidamente la query.</span><span class="sxs-lookup"><span data-stu-id="b4e04-177">Right-click a value in the result set to quickly enhance your query.</span></span> <span data-ttu-id="b4e04-178">È possibile usare le opzioni per:</span><span class="sxs-lookup"><span data-stu-id="b4e04-178">You can use the options to:</span></span>

- <span data-ttu-id="b4e04-179">Cercare in modo esplicito il valore selezionato (`==`)</span><span class="sxs-lookup"><span data-stu-id="b4e04-179">Explicitly look for the selected value (`==`)</span></span>
- <span data-ttu-id="b4e04-180">Escludere il valore selezionato dalla query (`!=`)</span><span class="sxs-lookup"><span data-stu-id="b4e04-180">Exclude the selected value from the query (`!=`)</span></span>
- <span data-ttu-id="b4e04-181">Per aggiungere il valore alla query, è possibile usare gli operatori più avanzati, come `contains`, `starts with` e `ends with`</span><span class="sxs-lookup"><span data-stu-id="b4e04-181">Get more advanced operators for adding the value to your query, such as `contains`, `starts with` and `ends with`</span></span> 

![Immagine del set di risultati di ricerca avanzata](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a><span data-ttu-id="b4e04-183">Filtrare i risultati della query</span><span class="sxs-lookup"><span data-stu-id="b4e04-183">Filter the query results</span></span>
<span data-ttu-id="b4e04-184">I filtri visualizzati a destra forniscono un riepilogo del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="b4e04-184">The filters displayed to the right provide a summary of the result set.</span></span> <span data-ttu-id="b4e04-185">Ogni colonna ha una propria sezione in cui sono elencati i valori distinti individuati per quella colonna e il numero di istanze.</span><span class="sxs-lookup"><span data-stu-id="b4e04-185">Each column has its own section that lists the distinct values found for that column and the number of instances.</span></span>

<span data-ttu-id="b4e04-186">Per affinare la query, selezionare i pulsanti o sui valori che si desidera includere o escludere e quindi `+` `-` selezionare Esegui **query.**</span><span class="sxs-lookup"><span data-stu-id="b4e04-186">Refine your query by selecting the `+` or `-` buttons on the values that you want to include or exclude and then selecting **Run query**.</span></span>

![Immagine del filtro di ricerca avanzata](../../media/advanced-hunting-filter.png)

<span data-ttu-id="b4e04-188">Dopo avere applicato il filtro per modificare la query e aver eseguito la query, i risultati vengono aggiornati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="b4e04-188">Once you apply the filter to modify the query and then run the query, the results are updated accordingly.</span></span>

>[!NOTE]
><span data-ttu-id="b4e04-189">Alcune tabelle di questo articolo potrebbero non essere disponibili in Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="b4e04-189">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b4e04-190">[Attivare Microsoft 365 Defender per](m365d-enable.md) cercare minacce che usano più origini dati.</span><span class="sxs-lookup"><span data-stu-id="b4e04-190">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="b4e04-191">Puoi spostare i flussi di lavoro di ricerca avanzata da Microsoft Defender per Endpoint a Microsoft 365 Defender seguendo la procedura descritta in Eseguire la migrazione di query di ricerca avanzate da [Microsoft Defender per Endpoint.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="b4e04-191">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b4e04-192">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b4e04-192">Related topics</span></span>
- [<span data-ttu-id="b4e04-193">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="b4e04-193">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b4e04-194">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="b4e04-194">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="b4e04-195">Utilizzare le query condivise</span><span class="sxs-lookup"><span data-stu-id="b4e04-195">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="b4e04-196">Cercare tra dispositivi, posta elettronica, app e identità</span><span class="sxs-lookup"><span data-stu-id="b4e04-196">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="b4e04-197">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="b4e04-197">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="b4e04-198">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="b4e04-198">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="b4e04-199">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="b4e04-199">Custom detections overview</span></span>](custom-detections-overview.md)
