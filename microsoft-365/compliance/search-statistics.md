---
title: Statistiche della ricerca
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 7c59b36e3594d653f188742890ea849e2595a648
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081374"
---
# <a name="search-statistics"></a><span data-ttu-id="83973-102">Statistiche della ricerca</span><span class="sxs-lookup"><span data-stu-id="83973-102">Search statistics</span></span>

<span data-ttu-id="83973-103">Un modo efficace per convalidare i risultati della ricerca quando si verifica un problema di dati consiste nel visualizzare le statistiche sui risultati della ricerca per assicurarsi che siano allineate alle aspettative.</span><span class="sxs-lookup"><span data-stu-id="83973-103">An effective way to validate your search results when investigation a data incident is to view the statistics about your search results to make sure they align with your expectations.</span></span> <span data-ttu-id="83973-104">Quando una ricerca è terminata, le seguenti statistiche di alto livello vengono visualizzate in **stato** nella pagina riquadro a comparsa dettagli ricerca:</span><span class="sxs-lookup"><span data-stu-id="83973-104">When a search as finished running, the following high-level statistics are displayed under **Status** on the search details flyout page:</span></span>

![Pagina di ricerca statisics nella pagina riquadro a comparsa dettagli ricerca](../media/SearchDetailsFlyout.png)

- <span data-ttu-id="83973-106">Il numero e le dimensioni stimati degli elementi corrispondenti ai criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-106">The estimated number and size of items that matched the search criteria.</span></span>

- <span data-ttu-id="83973-107">Il numero e le dimensioni degli elementi parzialmente indicizzati (denominati anche *elementi non indicizzati*) che non sono disponibili per la ricerca ma che sono stati trovati nei percorsi di contenuto che sono stati inclusi nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-107">The number and size of partially indexed items (also called *unindexed items*) that aren't searchable but that were found in the content locations that were included in the search.</span></span>

- <span data-ttu-id="83973-108">Il numero di cassette postali e i siti di cui è stata eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-108">The number of mailboxes and sites that were searched.</span></span>

<span data-ttu-id="83973-109">Per visualizzare statistiche più dettagliate, fare clic su **statistiche** nella pagina del riquadro a comparsa dettagli ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-109">To view more detailed statistics, click **Statistics** on the search details flyout page.</span></span> <span data-ttu-id="83973-110">Nella pagina **statistiche di ricerca** è possibile visualizzare il riepilogo della ricerca, la posizione principale che conteneva gli elementi corrispondenti ai risultati della ricerca e le statistiche dettagliate sulla query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-110">On the **Search statistics** page, you can view the search summary, the top location that contained items that matched the search results, and detailed statistics about the search query.</span></span>

![Elenco a discesa Statistiche di ricerca](../media/SearchStatisticsDropDownList.png)

## <a name="summary"></a><span data-ttu-id="83973-112">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="83973-112">Summary</span></span>

<span data-ttu-id="83973-113">Nella visualizzazione **Riepilogo** , è possibile visualizzare i risultati della ricerca suddivisi in base al tipo di posizione (ad esempio, le posizioni includono le cassette postali di Exchange e i siti di SharePoint).</span><span class="sxs-lookup"><span data-stu-id="83973-113">In the **Summary** view, you can see the search results broken down by location type (for example, locations include Exchange mailboxes and SharePoint sites).</span></span> <span data-ttu-id="83973-114">Per ogni tipo di percorso vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83973-114">The following information is displayed for each location type:</span></span>

- <span data-ttu-id="83973-115">Il numero di posizioni con elementi che corrispondono ai criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-115">The number of locations that had items that matched the search criteria.</span></span>

- <span data-ttu-id="83973-116">Il numero totale di elementi di ogni tipo di posizione corrispondenti ai criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-116">The total number of items from each location type that matched the search criteria.</span></span>

- <span data-ttu-id="83973-117">La dimensione totale degli elementi di ogni tipo di posizione corrispondenti ai criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-117">The total size of items from each location type that matched the search criteria.</span></span>

## <a name="top-locations"></a><span data-ttu-id="83973-118">Posizioni principali</span><span class="sxs-lookup"><span data-stu-id="83973-118">Top locations</span></span>

<span data-ttu-id="83973-119">Nella visualizzazione **posizioni superiori** , vengono visualizzati i singoli percorsi di contenuto con la maggior parte degli elementi corrispondenti ai criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-119">In the **Top locations** view, you see the individual content locations with the most items that matched the search criteria.</span></span> <span data-ttu-id="83973-120">Per ogni percorso del contenuto, vengono visualizzate le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="83973-120">For each content location, the following information is displayed:</span></span>

- <span data-ttu-id="83973-121">Nome del percorso. l'indirizzo di posta elettronica per le cassette postali e l'URL per i siti di SharePoint</span><span class="sxs-lookup"><span data-stu-id="83973-121">The name of the location; the email address for mailboxes and the URL for SharePoint sites</span></span>

- <span data-ttu-id="83973-122">Tipo di posizione</span><span class="sxs-lookup"><span data-stu-id="83973-122">The location type</span></span>

- <span data-ttu-id="83973-123">Numero di elementi che corrispondono ai criteri di ricerca</span><span class="sxs-lookup"><span data-stu-id="83973-123">Number of items that matched the search criteria</span></span>

- <span data-ttu-id="83973-124">Dimensione totale di tutti gli elementi che corrispondono ai criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-124">The total size of all items that matched the search criteria.</span></span>

## <a name="queries"></a><span data-ttu-id="83973-125">Query</span><span class="sxs-lookup"><span data-stu-id="83973-125">Queries</span></span>

<span data-ttu-id="83973-126">Nella visualizzazione **query** , è possibile visualizzare le statistiche dettagliate per ogni componente della query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-126">In the **Queries** view, you can see detailed statistics for each component of the search query.</span></span> <span data-ttu-id="83973-127">Se è stato utilizzato l'elenco di parole chiave nella query di ricerca, è possibile visualizzare le statistiche avanzate nella visualizzazione **query** che mostrano il numero di elementi che corrispondono a ogni parola chiave o frase di parola chiave.</span><span class="sxs-lookup"><span data-stu-id="83973-127">If you used the keyword list in the search query, you can view enhanced statistics in the **Queries** view  that show how many items match each keyword or keyword phrase.</span></span> <span data-ttu-id="83973-128">In questo modo è possibile identificare rapidamente quali parti della query sono le più (e meno) effettive.</span><span class="sxs-lookup"><span data-stu-id="83973-128">This can help you quickly identify which parts of the query are the most (and least) effective.</span></span> 

<span data-ttu-id="83973-129">Nella visualizzazione **query** vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="83973-129">The following information is displayed in the **Queries** view:</span></span>

 - <span data-ttu-id="83973-130">**Tipo di percorso** : il tipo di percorso del contenuto per le statistiche visualizzate nella riga.</span><span class="sxs-lookup"><span data-stu-id="83973-130">**Location type** - The type of content location for the statistics displayed in the row.</span></span>

- <span data-ttu-id="83973-131">**Part** -questa colonna visualizzerà uno dei seguenti valori: **Primary** o **keyword**.</span><span class="sxs-lookup"><span data-stu-id="83973-131">**Part** - This column will display one of the following values: **Primary** or **Keyword**.</span></span> <span data-ttu-id="83973-132">**Principale** indica che la riga presenta statistiche sull'intera query. **Keyword** significa che le statistiche della riga sono relative a uno dei componenti di query.</span><span class="sxs-lookup"><span data-stu-id="83973-132">**Primary** means the row presents statistics on the entire query; **Keyword** means the statistics in the row are for one of the query components.</span></span>

- <span data-ttu-id="83973-133">**Condition** : il componente di query effettivo della query di ricerca a cui si riferisce la riga.</span><span class="sxs-lookup"><span data-stu-id="83973-133">**Condition** - The actual query component of the search query the row refers to.</span></span> <span data-ttu-id="83973-134">Se il valore nella colonna **parte** è **primario**, vengono visualizzate le statistiche per l'intera query di ricerca. Se il valore è **keyword**, vengono visualizzate le statistiche per il componente della query visualizzata nella colonna **query** .</span><span class="sxs-lookup"><span data-stu-id="83973-134">If the value in the **Part** column is **Primary**, then the statistics for the entire search query are displayed; if the value is **Keyword**, then the statistics for the component of the query shown in the **Query** column are displayed.</span></span> <span data-ttu-id="83973-135">Ad esempio, se è stato utilizzato l'elenco delle parole chiave, vengono visualizzate le statistiche.</span><span class="sxs-lookup"><span data-stu-id="83973-135">For example, if the keyword list was used, then the statistics one of the keywords are displayed.</span></span>

  <span data-ttu-id="83973-136">Di seguito sono riportate alcune altre informazioni relative alle statistiche visualizzate nella colonna **query** :</span><span class="sxs-lookup"><span data-stu-id="83973-136">Here are some other things to know about the statistics displayed in the **Queries** column:</span></span>
  
  - <span data-ttu-id="83973-137">Quando si esegue la ricerca di tutto il contenuto nelle cassette postali (non specificando alcuna parola chiave), la query effettiva è **(dimensioni >= 0)** , in modo che tutti gli elementi vengano restituiti</span><span class="sxs-lookup"><span data-stu-id="83973-137">When you search for all content in mailboxes (by not specifying any keywords), the actual query is **(size >= 0)** so that all items are returned</span></span>
  
  - <span data-ttu-id="83973-138">Quando si eseguono ricerche in siti di SharePoint e OneDrive, nella query di ricerca vengono aggiunti i due componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="83973-138">When you search SharePoint and OneDrive sites, the two following components are added to the search query:</span></span>
    
    <span data-ttu-id="83973-139">**Not IsExternalContent: 1** -questo esclude qualsiasi contenuto di un'organizzazione di SharePoint locale</span><span class="sxs-lookup"><span data-stu-id="83973-139">**NOT IsExternalContent:1** - This excludes any content from an on-premises SharePoint organization</span></span>
    
    <span data-ttu-id="83973-140">**Not isOneNotePage: 1** -questo esclude tutti i file di OneNote, poiché si tratta di duplicati di qualsiasi documento corrispondente alla query di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-140">**NOT isOneNotePage:1** - This excludes all OneNote files because these would be duplicates of any document that matches the search query.</span></span>

- <span data-ttu-id="83973-141">**Posizioni nella ricerca** Il numero di posizioni di contenuto che presentano elementi che corrispondono alla query di ricerca per la parte o la condizione visualizzata nella riga.</span><span class="sxs-lookup"><span data-stu-id="83973-141">**Locations in search** The number of content locations that had items that matched the search query for the part/condition displayed in the row.</span></span> <span data-ttu-id="83973-142">Si noti che le cassette postali di archiviazione vengono contate come percorso separato se contengono elementi che soddisfano i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="83973-142">Note that archive mailboxes are counted as a separate location if they contain items that match the search criteria.</span></span>

- <span data-ttu-id="83973-143">**Elementi** : il numero totale di elementi che corrispondono ai criteri di ricerca per la parte o la condizione visualizzata nella riga.</span><span class="sxs-lookup"><span data-stu-id="83973-143">**Items** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>

- <span data-ttu-id="83973-144">**Dimensione** : il numero totale di elementi che corrispondono ai criteri di ricerca per la parte o la condizione visualizzata nella riga.</span><span class="sxs-lookup"><span data-stu-id="83973-144">**Size** - The total number of items that matched the search criteria for the part/condition displayed in the row.</span></span>

