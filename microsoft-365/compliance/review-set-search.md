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
description: Informazioni su come creare ed eseguire una query in un set di revisione per organizzare i dati per una revisione più efficiente in un Advanced eDiscovery caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345801"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="303ae-103">Eseguire query sui dati in un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="303ae-103">Query the data in a review set</span></span>

<span data-ttu-id="303ae-104">Nella maggior parte dei casi, sarà utile essere in grado di approfondire i dati in un set di recensioni e organizzare tali dati per facilitare una revisione più efficiente.</span><span class="sxs-lookup"><span data-stu-id="303ae-104">In most cases, it will be useful to be able to dig deeper into the data in a review set and organize that data to facilitate a more efficient review.</span></span> <span data-ttu-id="303ae-105">L'utilizzo di query in un set di revisione consente di concentrarsi su un sottoinsieme di documenti che soddisfano i criteri della revisione.</span><span class="sxs-lookup"><span data-stu-id="303ae-105">Using Queries in a review set helps you focus on a subset of documents that meet the criteria of your review.</span></span>

## <a name="creating-and-running-a-query-in-a-review-set"></a><span data-ttu-id="303ae-106">Creazione ed esecuzione di una query in un set di revisione</span><span class="sxs-lookup"><span data-stu-id="303ae-106">Creating and running a query in a review set</span></span>

<span data-ttu-id="303ae-107">Per creare ed eseguire una query sui documenti di un set di revisioni, selezionare **Nuova query** nel set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="303ae-107">To create and run a query on the documents in a review set, select **New query** in the review set.</span></span> <span data-ttu-id="303ae-108">Dopo aver definito la query e aver definito le condizioni, selezionare **Salva** per salvare ed eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="303ae-108">After you name your query and define the conditions, select **Save** to save and run the query.</span></span> <span data-ttu-id="303ae-109">Per eseguire una query salvata in precedenza, selezionare una query salvata.</span><span class="sxs-lookup"><span data-stu-id="303ae-109">To run a query that has been previously saved, select a saved query.</span></span>

![Esaminare le query impostate](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a><span data-ttu-id="303ae-111">Creazione di una query del set di revisione</span><span class="sxs-lookup"><span data-stu-id="303ae-111">Building a review set query</span></span>

<span data-ttu-id="303ae-112">È possibile creare una query utilizzando una combinazione di parole chiave, proprietà e condizioni nella condizione Parole chiave.</span><span class="sxs-lookup"><span data-stu-id="303ae-112">You can build a query by using a combination of keywords, properties, and conditions in the Keywords condition.</span></span> <span data-ttu-id="303ae-113">È inoltre possibile raggruppare le condizioni come blocco ( denominato gruppo *di condizioni*) per creare una query più complessa.</span><span class="sxs-lookup"><span data-stu-id="303ae-113">You can also group conditions as a block (called a *condition group*) to build a more complex query.</span></span> <span data-ttu-id="303ae-114">Per un elenco e una descrizione delle proprietà dei metadati che è possibile cercare, vedere [Campi dei metadati del documento in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="303ae-114">For a list and description of metadata properties that you can search, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span>

### <a name="conditions"></a><span data-ttu-id="303ae-115">Condizioni</span><span class="sxs-lookup"><span data-stu-id="303ae-115">Conditions</span></span>

<span data-ttu-id="303ae-116">Ogni campo ricercabile in un set di revisione ha una condizione corrispondente che è possibile utilizzare per creare la query.</span><span class="sxs-lookup"><span data-stu-id="303ae-116">Every searchable field in a review set has a corresponding condition that you can use to build your query.</span></span>

<span data-ttu-id="303ae-117">Esistono più tipi di condizioni:</span><span class="sxs-lookup"><span data-stu-id="303ae-117">There are multiple types of conditions:</span></span>

- <span data-ttu-id="303ae-118">Testo libero: per i campi di testo, ad esempio l'oggetto, viene utilizzata una condizione di testo libero.</span><span class="sxs-lookup"><span data-stu-id="303ae-118">Freetext: A freetext condition is used for text fields such as subject.</span></span> <span data-ttu-id="303ae-119">È possibile elencare più termini di ricerca separandoli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="303ae-119">You can list multiple search terms by separating them out with a comma.</span></span>

- <span data-ttu-id="303ae-120">Data: per i campi data, ad esempio la data dell'ultima modifica, viene utilizzata una condizione di data.</span><span class="sxs-lookup"><span data-stu-id="303ae-120">Date: A date condition is used for date fields such as last modified date.</span></span>

- <span data-ttu-id="303ae-121">Opzioni di ricerca: una condizione delle opzioni di ricerca fornirà un elenco dei valori possibili per il campo specifico nel set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="303ae-121">Search options: A search options condition will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="303ae-122">Viene utilizzato per i campi, ad esempio il mittente, in cui è presente un numero limitato di valori possibili nel set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="303ae-122">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>

- <span data-ttu-id="303ae-123">Parola chiave: una condizione di parola chiave è un'istanza specifica della condizione di testo libero che puoi usare per cercare termini o usare un linguaggio di query simile a KQL.</span><span class="sxs-lookup"><span data-stu-id="303ae-123">Keyword: A keyword condition is a specific instance of freetext condition that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="303ae-124">Vedi di seguito per altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="303ae-124">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="303ae-125">Linguaggio di query</span><span class="sxs-lookup"><span data-stu-id="303ae-125">Query language</span></span>

<span data-ttu-id="303ae-126">Oltre alle condizioni, è possibile utilizzare un linguaggio di query simile a KQL nella condizione Keywords per creare la query.</span><span class="sxs-lookup"><span data-stu-id="303ae-126">In addition to conditions, you can use a KQL-like query language in the Keywords condition to build your query.</span></span> <span data-ttu-id="303ae-127">Il linguaggio di query per le query di set di revisione supporta gli operatori Boolean standard, ad **esempio AND**, **OR**, **NOT** e **NEAR.**</span><span class="sxs-lookup"><span data-stu-id="303ae-127">The query language for review set queries supports standard Boolean operators, such as **AND**, **OR**, **NOT**, and **NEAR**.</span></span> <span data-ttu-id="303ae-128">Supporta inoltre un carattere jolly a carattere singolo (?) e un carattere jolly a più caratteri (\*).</span><span class="sxs-lookup"><span data-stu-id="303ae-128">It also supports a single-character wildcard (?) and a multi-character wildcard (\*).</span></span>

## <a name="filters"></a><span data-ttu-id="303ae-129">Filtri</span><span class="sxs-lookup"><span data-stu-id="303ae-129">Filters</span></span>

<span data-ttu-id="303ae-130">Oltre alle query che è possibile salvare, è possibile utilizzare i filtri dei set di revisione per applicare rapidamente condizioni aggiuntive a una query del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="303ae-130">In addition to queries that you can save, you can use review set filters to quickly apply additional conditions to a review set query.</span></span> <span data-ttu-id="303ae-131">L'utilizzo dei filtri consente di perfezionare ulteriormente i risultati visualizzati da una query del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="303ae-131">Using filters help you further refine the results displayed by a review set query.</span></span>

![Esaminare i filtri impostati](../media/AeDReviewSetFilters.png)

<span data-ttu-id="303ae-133">I filtri differiscono dalle query in due modi significativi:</span><span class="sxs-lookup"><span data-stu-id="303ae-133">Filters differ from queries in two significant ways:</span></span>

- <span data-ttu-id="303ae-134">I filtri sono temporanei.</span><span class="sxs-lookup"><span data-stu-id="303ae-134">Filters are transient.</span></span> <span data-ttu-id="303ae-135">Non vengono mantenuti oltre la sessione esistente.</span><span class="sxs-lookup"><span data-stu-id="303ae-135">They don't persist beyond the existing session.</span></span> <span data-ttu-id="303ae-136">In altre parole, non è possibile salvare un filtro.</span><span class="sxs-lookup"><span data-stu-id="303ae-136">In other words, you can't save a filter.</span></span> <span data-ttu-id="303ae-137">Le query vengono salvate nel set di revisione e vi accedono ogni volta che si apre il set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="303ae-137">Queries are saved to the review set, and access them whenever you open the review set.</span></span>

- <span data-ttu-id="303ae-138">I filtri sono sempre additivi.</span><span class="sxs-lookup"><span data-stu-id="303ae-138">Filters are always additive.</span></span> <span data-ttu-id="303ae-139">I filtri vengono applicati in aggiunta alla query corrente dell'insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="303ae-139">Filters are applied in addition to the current review set query.</span></span> <span data-ttu-id="303ae-140">L'applicazione di una query diversa sostituirà i risultati restituiti dalla query corrente.</span><span class="sxs-lookup"><span data-stu-id="303ae-140">Applying a different query will replace the results returned by the current query.</span></span>
