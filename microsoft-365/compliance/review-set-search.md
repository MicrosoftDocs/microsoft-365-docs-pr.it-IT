---
title: Eseguire query sui dati in un insieme da rivedere
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
ms.openlocfilehash: 140ccc3984dc09a794d822eb3ff02f139d87fcd5
ms.sourcegitcommit: ef658406da9d081e5e7a5f3aac8290c2f03f7aff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2020
ms.locfileid: "41004821"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="65476-102">Eseguire query sui dati in un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="65476-102">Query the data in a review set</span></span>

<span data-ttu-id="65476-103">Nella maggior parte dei casi, sarà utile essere in grado di approfondire i dati in un set di revisione e organizzare tali dati per facilitare una revisione più efficiente.</span><span class="sxs-lookup"><span data-stu-id="65476-103">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="65476-104">L'utilizzo di query in un set di revisione consente di concentrarsi su un sottoinsieme di documenti che soddisfano i criteri della revisione.</span><span class="sxs-lookup"><span data-stu-id="65476-104">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="65476-105">Creazione e esecuzione di una query in un set di Revisione</span><span class="sxs-lookup"><span data-stu-id="65476-105">Creating and running a query in a review set</span></span>

<span data-ttu-id="65476-106">Per creare ed eseguire una query sui documenti in un set di revisione, fare clic su **nuova query** nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="65476-106">To create and run a query on the documents in a review set, click **New query** in the review set.</span></span> <span data-ttu-id="65476-107">Dopo aver denominato la query e aver definito le condizioni, fare clic su **Salva** per salvare ed eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="65476-107">After you name your query and define the conditions, click **Save** to save and run the query.</span></span> <span data-ttu-id="65476-108">Per eseguire una query salvata in precedenza, fare clic su una query salvata.</span><span class="sxs-lookup"><span data-stu-id="65476-108">To run a query that has been previously saved, click a saved query.</span></span>

![Esaminare le query di set](media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="65476-110">Creazione di una query del set di Revisione</span><span class="sxs-lookup"><span data-stu-id="65476-110">Building a review set query</span></span>

<span data-ttu-id="65476-111">È possibile creare una query utilizzando una combinazione di schede di condizione e lingua di query nella scheda condizione parole chiave.</span><span class="sxs-lookup"><span data-stu-id="65476-111">You can build a query by using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="65476-112">È inoltre possibile raggruppare le schede delle condizioni insieme come blocco (denominato *gruppo di condizioni*) per creare una query più complessa.</span><span class="sxs-lookup"><span data-stu-id="65476-112">You can also group condition cards together as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="65476-113">Per un elenco e una descrizione delle proprietà dei metadati di cui è possibile eseguire la ricerca, vedere [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="65476-113">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="condition-cards"></a><span data-ttu-id="65476-114">Schede delle condizioni</span><span class="sxs-lookup"><span data-stu-id="65476-114">Condition cards</span></span>

<span data-ttu-id="65476-115">Tutti i campi ricercabili in un set di revisione dispongono di una scheda di condizione corrispondente che è possibile utilizzare per creare la query.</span><span class="sxs-lookup"><span data-stu-id="65476-115">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="65476-116">Sono disponibili più tipi di schede di condizione:</span><span class="sxs-lookup"><span data-stu-id="65476-116">There are multiple types of condition cards:</span></span>

- <span data-ttu-id="65476-117">FREETEXT: viene utilizzata una scheda di condizione FREETEXT per i campi di testo, ad esempio subject.</span><span class="sxs-lookup"><span data-stu-id="65476-117">Freetext: A freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="65476-118">È possibile elencare più termini di ricerca separandoli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="65476-118">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="65476-119">Data: viene utilizzata una scheda condizione data per i campi data, ad esempio la data dell'Ultima modifica.</span><span class="sxs-lookup"><span data-stu-id="65476-119">Date: A date condition card is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="65476-120">Opzioni di ricerca: una scheda condizione opzioni di ricerca fornirà un elenco di valori possibili per il campo specifico del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="65476-120">Search options: A search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="65476-121">Viene utilizzato per i campi, ad esempio sender, in cui è presente un numero finito di valori possibili nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="65476-121">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="65476-122">Keyword: una scheda di condizione di parola chiave è un'istanza specifica di FREETEXT Condition card che è possibile utilizzare per cercare i termini oppure utilizzare la lingua di query KQL-like.</span><span class="sxs-lookup"><span data-stu-id="65476-122">Keyword: A keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="65476-123">Per ulteriori informazioni, vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="65476-123">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="65476-124">Lingua query</span><span class="sxs-lookup"><span data-stu-id="65476-124">Query language</span></span>

<span data-ttu-id="65476-125">Oltre alle schede delle condizioni, è possibile utilizzare un linguaggio di query simile a KQL nella scheda Parole chiave per creare la query.</span><span class="sxs-lookup"><span data-stu-id="65476-125">In addition to condition cards, you can use a KQL-like query language in the Keywords card to build your query.</span></span> <span data-ttu-id="65476-126">Il linguaggio di query per le query dei set di revisione supporta gli operatori booleani standard, ad esempio **e**, **o**, **non**e **vicino**.</span><span class="sxs-lookup"><span data-stu-id="65476-126">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="65476-127">Supporta anche un carattere jolly con caratteri singoli (?) e un carattere jolly a più caratteri (\*).</span><span class="sxs-lookup"><span data-stu-id="65476-127">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="using-filters"></a><span data-ttu-id="65476-128">Utilizzo di filtri</span><span class="sxs-lookup"><span data-stu-id="65476-128">Using filters</span></span>

<span data-ttu-id="65476-129">Oltre alle query che è possibile salvare, è possibile utilizzare i filtri set di revisione per applicare rapidamente condizioni aggiuntive a una query del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="65476-129">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="65476-130">In questo modo è possibile affinare ulteriormente i risultati visualizzati da una query del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="65476-130">This helps you further refine the results displayed by a review set query.</span></span>

![Esaminare i filtri impostati](media/AeDReviewSetFilters.png)

<span data-ttu-id="65476-132">I filtri differiscono dalle query in due modi significativi:</span><span class="sxs-lookup"><span data-stu-id="65476-132">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="65476-133">I filtri sono transitori.</span><span class="sxs-lookup"><span data-stu-id="65476-133">Filters are transient.</span></span> <span data-ttu-id="65476-134">Non vengono mantenuti oltre la sessione esistente.</span><span class="sxs-lookup"><span data-stu-id="65476-134">They don't persist beyond the existing session.</span></span> <span data-ttu-id="65476-135">In altre parole, non è possibile salvare un filtro.</span><span class="sxs-lookup"><span data-stu-id="65476-135">In other words, you can't save a filter.</span></span> <span data-ttu-id="65476-136">Le query vengono salvate nel set di revisione e vengono accessibili ogni volta che si apre il set di revisione.</span><span class="sxs-lookup"><span data-stu-id="65476-136">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="65476-137">I filtri sono sempre additivi.</span><span class="sxs-lookup"><span data-stu-id="65476-137">Filters are always additive.</span></span> <span data-ttu-id="65476-138">I filtri vengono applicati oltre alla query del set di revisione corrente.</span><span class="sxs-lookup"><span data-stu-id="65476-138">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="65476-139">L'applicazione di una query diversa sostituirà i risultati restituiti dalla query corrente.</span><span class="sxs-lookup"><span data-stu-id="65476-139">Applying a different query will replace the results returned by the current query.</span></span>
