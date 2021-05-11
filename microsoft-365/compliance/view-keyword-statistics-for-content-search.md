---
title: Visualizzare le statistiche per i risultati della ricerca eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Informazioni su come utilizzare la funzionalità delle statistiche di ricerca per visualizzare le statistiche per le ricerche di contenuto e le ricerche associate a un caso di eDiscovery di base nel Centro Microsoft 365 conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311114"
---
# <a name="view-statistics-for-ediscovery-search-results"></a><span data-ttu-id="ff463-103">Visualizzare le statistiche per i risultati della ricerca eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ff463-103">View statistics for eDiscovery search results</span></span>

<span data-ttu-id="ff463-104">Dopo aver creato ed eseguito una ricerca contenuto o una ricerca associata a un caso di eDiscovery di base, è possibile visualizzare le statistiche sui risultati della ricerca stimati.</span><span class="sxs-lookup"><span data-stu-id="ff463-104">After you create and run a Content search or a search associated with a Core eDiscovery case, you can view statistics about the estimated search results.</span></span> <span data-ttu-id="ff463-105">Include un riepilogo dei risultati della ricerca (simile al riepilogo dei risultati di ricerca stimati visualizzati nella pagina del riquadro a comparsa di ricerca), le statistiche delle query, ad esempio il numero di percorsi di contenuto con elementi che corrispondono alla query di ricerca e l'identità dei percorsi di contenuto con il maggior numero di elementi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ff463-105">This includes a summary of the search results (similar to the summary of the estimated search results displayed on the search flyout page), the query statistics such as the number of content locations with items that match the search query, and the identity of content locations that have the most matching items.</span></span>
  
<span data-ttu-id="ff463-106">È inoltre possibile utilizzare l'elenco delle parole chiave per configurare una ricerca in modo da restituire statistiche per ogni parola chiave in una query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-106">Additionally, you can use the keywords list to configure a search to return statistics for each keyword in a search query.</span></span> <span data-ttu-id="ff463-107">In questo modo è possibile confrontare il numero di risultati restituiti da ogni parola chiave in una query.</span><span class="sxs-lookup"><span data-stu-id="ff463-107">This lets you compare the number of results returned by each keyword in a query.</span></span>
  
<span data-ttu-id="ff463-108">È inoltre possibile scaricare le statistiche di ricerca in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="ff463-108">You can also download search statistics to a CSV file.</span></span> <span data-ttu-id="ff463-109">Questo consente di usare le funzionalità di filtro e ordinamento di Excel per confrontare i risultati e preparare report per i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-109">This lets you use the filtering and sorting features in Excel to compare results, and prepare reports for your search results.</span></span>
  
## <a name="get-statistics-for-searches"></a><span data-ttu-id="ff463-110">Ottenere statistiche per le ricerche</span><span class="sxs-lookup"><span data-stu-id="ff463-110">Get statistics for searches</span></span>

<span data-ttu-id="ff463-111">Per visualizzare le statistiche per una ricerca contenuto o una ricerca associata a un caso di eDiscovery di base.</span><span class="sxs-lookup"><span data-stu-id="ff463-111">To display statistics for a Content search or a search associated with a Core eDiscovery case.:</span></span>
  
1. <span data-ttu-id="ff463-112">Nel Centro Microsoft 365 conformità fare clic **su Mostra tutto** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ff463-112">In the Microsoft 365 compliance center, click **Show all**, and then do one of the following:</span></span>

   - <span data-ttu-id="ff463-113">Fare **clic su Ricerca** contenuto e quindi selezionare una ricerca per visualizzare la pagina a comparsa.</span><span class="sxs-lookup"><span data-stu-id="ff463-113">Click **Content search** and then select a search to display the flyout page.</span></span>

     <span data-ttu-id="ff463-114">OPPURE</span><span class="sxs-lookup"><span data-stu-id="ff463-114">OR</span></span>

   - <span data-ttu-id="ff463-115">Fare **clic su eDiscovery** Core, selezionare un caso e quindi selezionare una ricerca nella  >   **scheda** Ricerche per visualizzare la pagina a comparsa.</span><span class="sxs-lookup"><span data-stu-id="ff463-115">Click **eDiscovery** > **Core**, select a case, and then select a search on the **Searches** tab to display the flyout page.</span></span>

2. <span data-ttu-id="ff463-116">Nella pagina a comparsa della ricerca selezionata fare clic sulla **scheda Statistiche di** ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-116">On the flyout page of the selected search, click the **Search statistics** tab.</span></span>
  
   ![Scheda Statistiche di ricerca](../media/SearchStatistics1.png)

<span data-ttu-id="ff463-118">La **scheda Statistiche** di ricerca contiene le sezioni seguenti che contengono diversi tipi di statistiche sulla ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-118">The **Search statistics** tab contains for following sections that contain different types of statistics about the search.</span></span>

### <a name="search-content"></a><span data-ttu-id="ff463-119">Ricerca contenuto</span><span class="sxs-lookup"><span data-stu-id="ff463-119">Search content</span></span>

<span data-ttu-id="ff463-120">In questa sezione viene visualizzato un riepilogo grafico degli elementi stimati restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-120">This section displays a graphical summary of the estimated items returned by the search.</span></span> <span data-ttu-id="ff463-121">Indica il numero di elementi che soddisfano i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-121">This indicates the number of items that match the search criteria.</span></span> <span data-ttu-id="ff463-122">Queste informazioni danno un'idea del numero stimato di elementi restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-122">This information gives you an idea about the estimated number of items returned by the search.</span></span>

![Stime di ricerca per una ricerca](../media/SearchContentReport.png)

- <span data-ttu-id="ff463-124">**Elementi stimati in base alle** posizioni : numero totale di elementi stimati restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-124">**Estimated items by locations**: The total number of estimated items returned by the search.</span></span> <span data-ttu-id="ff463-125">Viene inoltre visualizzato il numero specifico di elementi presenti nelle cassette postali e nei siti.</span><span class="sxs-lookup"><span data-stu-id="ff463-125">The specific number of items located in mailboxes and located in sites is also displayed.</span></span>

- <span data-ttu-id="ff463-126">**Posizioni stimate con risultati**: numero totale di percorsi di contenuto che contengono elementi restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-126">**Estimated locations with hits**: The total number of content locations that contain items returned by the search.</span></span> <span data-ttu-id="ff463-127">Viene inoltre visualizzato il numero specifico di posizioni di cassette postali e siti.</span><span class="sxs-lookup"><span data-stu-id="ff463-127">The specific number of mailbox and site locations is also displayed.</span></span>

- <span data-ttu-id="ff463-128">**Volume di dati per posizione (in MB):** dimensione totale di tutti gli elementi stimati restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-128">**Data volume by location (in MB)**: The total size of all estimated items returned by the search.</span></span> <span data-ttu-id="ff463-129">Vengono inoltre visualizzate le dimensioni specifiche degli elementi delle cassette postali e degli elementi del sito.</span><span class="sxs-lookup"><span data-stu-id="ff463-129">The specific size of mailbox items and site items is also displayed.</span></span>

### <a name="condition-report"></a><span data-ttu-id="ff463-130">Rapporto condizioni</span><span class="sxs-lookup"><span data-stu-id="ff463-130">Condition report</span></span>

<span data-ttu-id="ff463-131">In questa sezione vengono visualizzate statistiche sulla query di ricerca e sul numero di elementi stimati corrispondenti a parti diverse della query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-131">This section displays statistics about the search query and the number of estimated items that matched different parts of the search query.</span></span> <span data-ttu-id="ff463-132">È possibile utilizzare queste statistiche per analizzare il numero di elementi che corrispondono a ogni componente della query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-132">You can use these statistics to analyze the number of items that match each component of search query.</span></span> <span data-ttu-id="ff463-133">In questo modo è possibile perfezionare i criteri di ricerca e, se necessario, limitare l'ambito dell'ambito.</span><span class="sxs-lookup"><span data-stu-id="ff463-133">This can help you refine the search criteria and if necessary narrow the scope of the scope.</span></span> <span data-ttu-id="ff463-134">È inoltre possibile scaricare una copia di questo report in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="ff463-134">You can also download a copy of this report in CSV format.</span></span>

![Rapporto condizioni](../media/SearchContentReportNoKeywordList.png)

- <span data-ttu-id="ff463-136">**Tipo di percorso**: Tipo di percorso del contenuto a cui sono applicabili le statistiche della query.</span><span class="sxs-lookup"><span data-stu-id="ff463-136">**Location type**: The type of content location that the query statistics are applicable to.</span></span> <span data-ttu-id="ff463-137">Il valore di **Exchange** indica la posizione di una cassetta postale; il valore **SharePoint** indica la posizione di un sito.</span><span class="sxs-lookup"><span data-stu-id="ff463-137">The value of **Exchange** indicates a mailbox location; a value of **SharePoint** indicates a site location.</span></span>

- <span data-ttu-id="ff463-138">**Parte**: parte della query di ricerca a cui sono applicabili le statistiche.</span><span class="sxs-lookup"><span data-stu-id="ff463-138">**Part**: The part of the search query the statistics are applicable to.</span></span> <span data-ttu-id="ff463-139">**Primary** indica l'intera query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-139">**Primary** indicates the entire search query.</span></span> <span data-ttu-id="ff463-140">**Keyword** indica che le statistiche nella riga sono relative a una parola chiave specifica.</span><span class="sxs-lookup"><span data-stu-id="ff463-140">**Keyword** indicates the statistics in the row are for a specific keyword.</span></span> <span data-ttu-id="ff463-141">Se si utilizza un elenco di parole chiave per la query di ricerca, le statistiche per ogni componente della query vengono incluse in questa tabella.</span><span class="sxs-lookup"><span data-stu-id="ff463-141">If you use a keyword list for search query, statistics for each component of the query are included in this table.</span></span> <span data-ttu-id="ff463-142">Per ulteriori informazioni, vedere [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span><span class="sxs-lookup"><span data-stu-id="ff463-142">For more information, see [Get keyword statistics for searches](#get-keyword-statistics-for-searches).</span></span>

- <span data-ttu-id="ff463-143">**Condizione**: Componente effettivo (parola chiave o condizione) della query di ricerca che ha restituito le statistiche visualizzate nella riga corrispondente.</span><span class="sxs-lookup"><span data-stu-id="ff463-143">**Condition**: The actual component (keyword or condition) of the search query that returned the statistics displayed in the corresponding row.</span></span>

- <span data-ttu-id="ff463-144">**Posizioni con risultati**: Numero delle posizioni  del contenuto (specificate dalla colonna Tipo percorso) che contengono gli elementi che corrispondono alla query principale o parola chiave elencata nella **colonna** Condizione.</span><span class="sxs-lookup"><span data-stu-id="ff463-144">**Locations with hits**: The number of the content locations (specified by the **Location type** column) that contain items that match the primary or keyword query listed in the **Condition** column.</span></span>

- <span data-ttu-id="ff463-145">**Elementi**: numero di elementi (dal percorso di contenuto specificato) che corrispondono alla query elencata nella **colonna** Condizione.</span><span class="sxs-lookup"><span data-stu-id="ff463-145">**Items**: The number of items (from the specified content location) that match the query listed in the **Condition** column.</span></span> <span data-ttu-id="ff463-146">Come spiegato in precedenza, se un elemento contiene più istanze di una parola chiave in fase di ricerca, viene conteggiato una sola volta in questa colonna.</span><span class="sxs-lookup"><span data-stu-id="ff463-146">As previously explained, if an item contains multiple instances of a keyword that is being searched for, it's only counted once in this column.</span></span>

- <span data-ttu-id="ff463-147">**Dimensione (MB):** dimensione totale di tutti gli elementi trovati (nel percorso di contenuto specificato) che corrispondono alla query di ricerca nella **colonna** Condizione.</span><span class="sxs-lookup"><span data-stu-id="ff463-147">**Size (MB)**: The total size of all items that were found (in the specified content location) that match the search query in the **Condition** column.</span></span>

### <a name="top-locations"></a><span data-ttu-id="ff463-148">Posizioni principali</span><span class="sxs-lookup"><span data-stu-id="ff463-148">Top locations</span></span>

<span data-ttu-id="ff463-149">In questa sezione vengono visualizzate le statistiche relative alle posizioni di contenuto specifiche con la maggior parte degli elementi restituiti dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-149">This section displays statistics about the specific content locations with the most items returned by the search.</span></span> <span data-ttu-id="ff463-150">Vengono visualizzati i primi 1.000 percorsi.</span><span class="sxs-lookup"><span data-stu-id="ff463-150">The top 1,000 locations are displayed.</span></span> <span data-ttu-id="ff463-151">È inoltre possibile scaricare una copia di questo report in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="ff463-151">You can also download a copy of this report in CSV format.</span></span>

- <span data-ttu-id="ff463-152">Nome del nome della posizione (l'indirizzo di posta elettronica delle cassette postali e l'URL per i siti).</span><span class="sxs-lookup"><span data-stu-id="ff463-152">The name of the location name (the email address of mailboxes and the URL for sites).</span></span>

- <span data-ttu-id="ff463-153">Tipo di posizione (una cassetta postale o un sito).</span><span class="sxs-lookup"><span data-stu-id="ff463-153">Location type (a mailbox or site).</span></span>

- <span data-ttu-id="ff463-154">Numero stimato di elementi nel percorso del contenuto restituito dalla ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-154">Estimated number of items in the content location returned by the search.</span></span>

- <span data-ttu-id="ff463-155">Dimensione totale degli elementi stimati in ogni percorso di contenuto.</span><span class="sxs-lookup"><span data-stu-id="ff463-155">The total size of estimated items in each content location.</span></span>

## <a name="get-keyword-statistics-for-searches"></a><span data-ttu-id="ff463-156">Ottenere statistiche sulle parole chiave per le ricerche</span><span class="sxs-lookup"><span data-stu-id="ff463-156">Get keyword statistics for searches</span></span>

<span data-ttu-id="ff463-157">Come spiegato in precedenza, nella sezione **Rapporto** condizione vengono mostrati la query di ricerca e il numero (e le dimensioni) degli elementi che corrispondono alla query.</span><span class="sxs-lookup"><span data-stu-id="ff463-157">As previous explained, the **Condition report** section shows the search query and the number (and size) of items that match the query.</span></span> <span data-ttu-id="ff463-158">Se si utilizza un elenco di parole chiave quando si crea o si modifica una query di ricerca, è possibile ottenere statistiche avanzate che mostrano quanti elementi corrispondono a ogni parola chiave o frase chiave.</span><span class="sxs-lookup"><span data-stu-id="ff463-158">If you use a keyword list when you create or edit a search query, you can get enhanced statistics that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="ff463-159">Ciò consente di identificare rapidamente quali parti della query sono più (e meno) efficaci.</span><span class="sxs-lookup"><span data-stu-id="ff463-159">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> <span data-ttu-id="ff463-160">Ad esempio, se una parola chiave restituisce un numero elevato di elementi, è possibile scegliere di perfezionare la query con parole chiave per restringere i risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-160">For example, if a keyword returns a large number of items, you might choose to refine the keyword query to narrow the search results.</span></span>

<span data-ttu-id="ff463-161">Per creare un elenco di parole chiave e visualizzare le statistiche delle parole chiave per una ricerca:</span><span class="sxs-lookup"><span data-stu-id="ff463-161">To create a keyword list and view keyword statistics for a search:</span></span>
  
1. <span data-ttu-id="ff463-162">Nel Centro Microsoft 365 conformità creare una nuova ricerca contenuto o una ricerca associata a un caso di eDiscovery di base.</span><span class="sxs-lookup"><span data-stu-id="ff463-162">In the Microsoft 365 compliance center, create a new Content search or a search associated with a Core eDiscovery case.</span></span>

2. <span data-ttu-id="ff463-163">Nella pagina **Condizioni** della procedura guidata di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-163">On the **Conditions** page of the search wizard.</span></span> <span data-ttu-id="ff463-164">selezionare la **casella di controllo Mostra elenco parole chiave.**</span><span class="sxs-lookup"><span data-stu-id="ff463-164">select the **Show keyword list** checkbox.</span></span>

   ![Casella di controllo Mostra elenco parole chiave](../media/SearchKeywordsList1.png)

3. <span data-ttu-id="ff463-166">Digitare una parola chiave o una fase di parola chiave in una riga della tabella delle parole chiave.</span><span class="sxs-lookup"><span data-stu-id="ff463-166">Type a keyword or keyword phase in a row in the keywords table.</span></span> <span data-ttu-id="ff463-167">Ad esempio, digitare **budget** nella prima riga, digitare **sicurezza** nella seconda riga e **FY2021** nella terza riga.</span><span class="sxs-lookup"><span data-stu-id="ff463-167">For example, type **budget** in the first row, type **security** in the second row, and type **FY2021** in the third row.</span></span>

   ![Digitare fino a 20 parole chiave o frasi chiave nell'elenco](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > <span data-ttu-id="ff463-169">Per ridurre i problemi causati da elenchi di parole chiave di grandi dimensioni, è possibile utilizzare un massimo di 20 righe nell'elenco di parole chiave di una query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-169">To help reduce issues caused by large keyword lists, you're limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

4. <span data-ttu-id="ff463-170">Dopo aver aggiunto le parole chiave all'elenco per cui si desidera cercare e ottenere statistiche, eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-170">After adding the keywords to the list that you want to search and get statistics for, run the search.</span></span>

5. <span data-ttu-id="ff463-171">Al termine della ricerca, selezionarla per visualizzare la pagina a comparsa.</span><span class="sxs-lookup"><span data-stu-id="ff463-171">When the search is completed, select it to display the flyout page.</span></span>

6. <span data-ttu-id="ff463-172">Nella scheda **Statistiche di** ricerca fare clic sul report **Condizione per** visualizzare le statistiche delle parole chiave per la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-172">On the **Search statistics** tab, click the **Condition report** to display the keyword statistics for the search.</span></span>

    ![Vengono visualizzate le statistiche per ogni parola chiave](../media/SearchKeywordsList3.png)
  
    <span data-ttu-id="ff463-174">Come mostrato nella schermata precedente, vengono visualizzate le statistiche per ogni parola chiave. ciò include:</span><span class="sxs-lookup"><span data-stu-id="ff463-174">As shown in the previous screenshot, the statistics for each keyword are displayed; this includes:</span></span>

    - <span data-ttu-id="ff463-175">Statistiche delle parole chiave per ogni tipo di percorso di contenuto incluso nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-175">The keyword statistics for each type of content location included in the search.</span></span>

    - <span data-ttu-id="ff463-176">Numero di elementi della cassetta postale non indicizzati.</span><span class="sxs-lookup"><span data-stu-id="ff463-176">The number of unindexed mailbox items.</span></span>

    - <span data-ttu-id="ff463-177">Query di ricerca effettiva e risultati per ogni parola chiave (identificata come **Parola** chiave nella **colonna Part),** che include tutte le condizioni della query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff463-177">The actual search query and results for each keyword (identified as **Keyword** in the **Part** column), which includes any conditions from the search query.</span></span>

    - <span data-ttu-id="ff463-178">La query di ricerca completa (identificata come **Primaria** nella **colonna Part)** e le statistiche per la query completa per ogni tipo di posizione.</span><span class="sxs-lookup"><span data-stu-id="ff463-178">The complete search query (identified as **Primary** in the **Part** column) and the statistics for the complete query for each location type.</span></span> <span data-ttu-id="ff463-179">Si noti che si tratta delle stesse statistiche visualizzate nella **scheda** Riepilogo.</span><span class="sxs-lookup"><span data-stu-id="ff463-179">Note these are the same statistics displayed on the **Summary** tab.</span></span>
