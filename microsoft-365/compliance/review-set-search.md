---
title: Eseguire query sui dati in un insieme da rivedere
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Informazioni su come creare ed eseguire una query in un set di revisione per organizzare i dati per una revisione più efficiente in un caso avanzato di eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ead897d412af2356d8b57ab8494539a5ed9a019
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816569"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="5bbe8-103">Eseguire query sui dati in un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="5bbe8-103">Query the data in a review set</span></span>

<span data-ttu-id="5bbe8-104">Nella maggior parte dei casi, sarà utile essere in grado di approfondire i dati in un set di revisione e organizzare tali dati per facilitare una revisione più efficiente.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="5bbe8-105">L'utilizzo di query in un set di revisione consente di concentrarsi su un sottoinsieme di documenti che soddisfano i criteri della revisione.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="5bbe8-106">Creazione e esecuzione di una query in un set di Revisione</span><span class="sxs-lookup"><span data-stu-id="5bbe8-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="5bbe8-107">Per creare ed eseguire una query sui documenti in un set di revisione, selezionare **nuova query** nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="5bbe8-108">Dopo aver denominato la query e aver definito le condizioni, selezionare **Salva** per salvare ed eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="5bbe8-109">Per eseguire una query salvata in precedenza, selezionare una query salvata.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-109">To run a query that has been previously saved, select a saved query.</span></span>

![Esaminare le query di set](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="5bbe8-111">Creazione di una query del set di Revisione</span><span class="sxs-lookup"><span data-stu-id="5bbe8-111">Building a review set query</span></span>

<span data-ttu-id="5bbe8-112">È possibile creare una query utilizzando una combinazione di parole chiave, proprietà e condizioni nella condizione keywords.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="5bbe8-113">È inoltre possibile raggruppare le condizioni come blocco (denominato *gruppo di condizioni* ) per creare una query più complessa.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-113">You can also group conditions as a block (called a *condition group* ) to build a more complex query.</span></span> <span data-ttu-id="5bbe8-114">Per un elenco e una descrizione delle proprietà dei metadati di cui è possibile eseguire la ricerca, vedere [Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="5bbe8-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="5bbe8-115">Condizioni</span><span class="sxs-lookup"><span data-stu-id="5bbe8-115">Conditions</span></span>

<span data-ttu-id="5bbe8-116">Tutti i campi ricercabili in un set di revisione dispongono di una condizione corrispondente che è possibile utilizzare per creare la query.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="5bbe8-117">Sono disponibili più tipi di condizioni:</span><span class="sxs-lookup"><span data-stu-id="5bbe8-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="5bbe8-118">FREETEXT: viene utilizzata una condizione FREETEXT per i campi di testo, ad esempio subject.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="5bbe8-119">È possibile elencare più termini di ricerca separandoli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="5bbe8-120">Data: viene utilizzata una condizione data per i campi data, ad esempio la data dell'Ultima modifica.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="5bbe8-121">Opzioni di ricerca: una condizione per le opzioni di ricerca fornirà un elenco di valori possibili per il campo specifico del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="5bbe8-122">Viene utilizzato per i campi, ad esempio sender, in cui è presente un numero finito di valori possibili nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="5bbe8-123">Keyword: una condizione di parola chiave è un'istanza specifica della condizione di FREETEXT che è possibile utilizzare per cercare i termini oppure utilizzare la lingua di query simile a KQL.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="5bbe8-124">Per ulteriori informazioni, vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="5bbe8-125">Lingua query</span><span class="sxs-lookup"><span data-stu-id="5bbe8-125">Query language</span></span>

<span data-ttu-id="5bbe8-126">Oltre alle condizioni, è possibile utilizzare un linguaggio di query simile a KQL nella condizione keywords per creare la query.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="5bbe8-127">Il linguaggio di query per le query dei set di revisione supporta gli operatori booleani standard, ad esempio **e** , **o** , **non** e **vicino** .</span><span class="sxs-lookup"><span data-stu-id="5bbe8-127">The query language for review set queries supports standard Boolean operators, such as **AND** , **OR** , **NOT** , and **NEAR** .</span></span> <span data-ttu-id="5bbe8-128">Supporta anche un carattere jolly con caratteri singoli (?) e un carattere jolly a più caratteri (\*).</span><span class="sxs-lookup"><span data-stu-id="5bbe8-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="5bbe8-129">Filtri</span><span class="sxs-lookup"><span data-stu-id="5bbe8-129">Filters</span></span>

<span data-ttu-id="5bbe8-130">Oltre alle query che è possibile salvare, è possibile utilizzare i filtri set di revisione per applicare rapidamente condizioni aggiuntive a una query del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="5bbe8-131">L'utilizzo dei filtri consente di affinare ulteriormente i risultati visualizzati da una query del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![Esaminare i filtri impostati](../media/AeDReviewSetFilters.png)

<span data-ttu-id="5bbe8-133">I filtri differiscono dalle query in due modi significativi:</span><span class="sxs-lookup"><span data-stu-id="5bbe8-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="5bbe8-134">I filtri sono transitori.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-134">Filters are transient.</span></span> <span data-ttu-id="5bbe8-135">Non vengono mantenuti oltre la sessione esistente.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="5bbe8-136">In altre parole, non è possibile salvare un filtro.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="5bbe8-137">Le query vengono salvate nel set di revisione e vengono accessibili ogni volta che si apre il set di revisione.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-137">Queries are saved to the review set, and access them whenever open the review set.</span></span>

- <span data-ttu-id="5bbe8-138">I filtri sono sempre additivi.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-138">Filters are always additive.</span></span> <span data-ttu-id="5bbe8-139">I filtri vengono applicati oltre alla query del set di revisione corrente.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="5bbe8-140">L'applicazione di una query diversa sostituirà i risultati restituiti dalla query corrente.</span><span class="sxs-lookup"><span data-stu-id="5bbe8-140">Applying a different query will replace the results returned by the current query.</span></span>
