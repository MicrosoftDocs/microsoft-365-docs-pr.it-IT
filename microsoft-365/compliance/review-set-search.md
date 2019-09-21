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
ms.openlocfilehash: 446f3f2588a79cb328476db490f1f555448b5ce7
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084775"
---
# <a name="query-the-data-in-a-review-set"></a><span data-ttu-id="d169a-102">Eseguire query sui dati in un insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="d169a-102">Query the data in a review set</span></span>

<span data-ttu-id="d169a-103">Nella maggior parte dei casi, sarà utile essere in grado di approfondire gli elementi presenti in un set di revisione e organizzarli per la revisione in modo più efficiente.</span><span class="sxs-lookup"><span data-stu-id="d169a-103">In most cases, it will be useful to be able to dig deeper into what is there in a review set and organize them to review more efficiently.</span></span> <span data-ttu-id="d169a-104">Le query all'interno di un set di revisione consentono di eseguire questa operazione consentendo di concentrarsi su un sottoinsieme di documenti che soddisfano i criteri definiti dall'utente in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="d169a-104">Queries within a review set enables you to do so by letting you focus on a subset of documents that meet the criteria defined by you at once.</span></span>

## <a name="creating-and-running-a-query-within-a-review-set"></a><span data-ttu-id="d169a-105">Creazione e esecuzione di una query all'interno di un set di Revisione</span><span class="sxs-lookup"><span data-stu-id="d169a-105">Creating and running a query within a review set</span></span>

<span data-ttu-id="d169a-106">Per creare ed eseguire una query all'interno del set di recensioni, fare clic su "nuova query" nel set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="d169a-106">In order to create and run a query within your review set, click on "New Query" in your review set.</span></span> <span data-ttu-id="d169a-107">Dopo aver denominati la query e aver definito le condizioni, fare clic su "Salva" per eseguire la query.</span><span class="sxs-lookup"><span data-stu-id="d169a-107">After you name your query and define the conditions, click "Save" to run the query.</span></span> <span data-ttu-id="d169a-108">Per eseguire una query salvata in precedenza, è sufficiente fare clic sulla query salvata.</span><span class="sxs-lookup"><span data-stu-id="d169a-108">To run a query that has been previously saved, simply click on the saved query.</span></span> <span data-ttu-id="d169a-109">Fare riferimento ai [campi dei metadati del documento](document-metadata-fields.md) per un elenco di metadati di cui è possibile eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="d169a-109">Refer to [Document metadata fields](document-metadata-fields.md) for a list of metadata you can search by.</span></span>

## <a name="building-your-query"></a><span data-ttu-id="d169a-110">Creazione di una query</span><span class="sxs-lookup"><span data-stu-id="d169a-110">Building your query</span></span>

<span data-ttu-id="d169a-111">È possibile creare la query utilizzando una combinazione di schede di condizione e lingua di query nella scheda condizione parole chiave.</span><span class="sxs-lookup"><span data-stu-id="d169a-111">You can build your query using a combination of condition cards and query language in the Keywords condition card.</span></span> <span data-ttu-id="d169a-112">È possibile raggruppare le schede delle condizioni insieme come blocco per creare una query più complessa.</span><span class="sxs-lookup"><span data-stu-id="d169a-112">You can group condition cards together as a block to craft a more complex query.</span></span>

### <a name="condition-card"></a><span data-ttu-id="d169a-113">Scheda condizione</span><span class="sxs-lookup"><span data-stu-id="d169a-113">Condition card</span></span>

<span data-ttu-id="d169a-114">Tutti i campi ricercabili in un set di revisione dispongono di una scheda di condizione corrispondente che è possibile utilizzare per creare la query.</span><span class="sxs-lookup"><span data-stu-id="d169a-114">Every searchable field in a review set has a corresponding condition card that you can use to build your query.</span></span>

<span data-ttu-id="d169a-115">Sono disponibili più tipi di schede di condizione:</span><span class="sxs-lookup"><span data-stu-id="d169a-115">There are multiple types of condition cards:</span></span>
- <span data-ttu-id="d169a-116">FREETEXT: la scheda di stato FREETEXT viene utilizzata per i campi di testo, ad esempio subject.</span><span class="sxs-lookup"><span data-stu-id="d169a-116">Freetext: freetext condition card is used for text fields such as subject.</span></span> <span data-ttu-id="d169a-117">È possibile elencare più termini di ricerca separandoli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="d169a-117">You can list multiple search terms by separating them out with a comma.</span></span>
- <span data-ttu-id="d169a-118">Data: la scheda condizione data viene utilizzata per i campi data, ad esempio la data dell'Ultima modifica.</span><span class="sxs-lookup"><span data-stu-id="d169a-118">Date: date condition card is used for date fields such as last modified date.</span></span>
- <span data-ttu-id="d169a-119">Opzioni di ricerca: la scheda delle opzioni di ricerca fornirà un elenco di valori possibili per il campo specifico del set di revisione.</span><span class="sxs-lookup"><span data-stu-id="d169a-119">Search options: search options condition card will provide a list of possible values for the particular field in your review set.</span></span> <span data-ttu-id="d169a-120">Viene utilizzato per i campi, ad esempio sender, in cui è presente un numero finito di valori possibili nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="d169a-120">This is used for fields, such as sender, where there is a finite number of possible values in your review set.</span></span>
- <span data-ttu-id="d169a-121">Keyword: la scheda condizione parola chiave è una specifica istanza della scheda di condizione di FREETEXT che è possibile utilizzare per cercare i termini oppure utilizzare la lingua di query simile a KQL.</span><span class="sxs-lookup"><span data-stu-id="d169a-121">Keyword: keyword condition card is a specific instance of freetext condition card that you can use to search for terms, or use KQL-like query language in.</span></span> <span data-ttu-id="d169a-122">Per ulteriori informazioni, vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="d169a-122">See below for more detail.</span></span>

### <a name="query-language"></a><span data-ttu-id="d169a-123">Lingua query</span><span class="sxs-lookup"><span data-stu-id="d169a-123">Query language</span></span>

<span data-ttu-id="d169a-124">Oltre alle schede delle condizioni, è possibile utilizzare una lingua di query simile a KQL nella scheda Parole chiave per creare la query.</span><span class="sxs-lookup"><span data-stu-id="d169a-124">In addition to condition cards, you can use a KQL-like query language in the Keywords card to craft your query.</span></span> <span data-ttu-id="d169a-125">Il linguaggio di query supporta la sintassi di KQL standard, come e, o, non e vicino (n).</span><span class="sxs-lookup"><span data-stu-id="d169a-125">The query language supports standard KQL syntax like AND, OR, NOT, and NEAR(n).</span></span> <span data-ttu-id="d169a-126">Supporta anche caratteri jolly con caratteri singoli (?) e caratteri jolly (\*).</span><span class="sxs-lookup"><span data-stu-id="d169a-126">It also supports single-character wildcard (?) and multi-character wildcard (\*).</span></span>

## <a name="filter"></a><span data-ttu-id="d169a-127">Filtro</span><span class="sxs-lookup"><span data-stu-id="d169a-127">Filter</span></span>

<span data-ttu-id="d169a-128">Oltre alle query che è possibile salvare, è possibile sovrapporre ulteriori condizioni al volo ai risultati delle query utilizzando filtri.</span><span class="sxs-lookup"><span data-stu-id="d169a-128">In addition to queries that you can save, you can overlay additional conditions on the fly to your query results using filters.</span></span> <span data-ttu-id="d169a-129">I filtri differiscono dalle query in pochi modi significativi:</span><span class="sxs-lookup"><span data-stu-id="d169a-129">Filters differ from queries in a few significant ways:</span></span>
- <span data-ttu-id="d169a-130">I filtri sono transitori (ovvero non sono permanenti su sessioni diverse), mentre le query vengono salvate nel set di revisione.</span><span class="sxs-lookup"><span data-stu-id="d169a-130">Filters are transient (i.e. they do not persist over different sessions), whereas queries are saved to the review set.</span></span>
- <span data-ttu-id="d169a-131">I filtri sono sempre additivi. i filtri verranno applicati in base alla query in vigore al momento, mentre l'applicazione di una query sostituirà la query in effetti.</span><span class="sxs-lookup"><span data-stu-id="d169a-131">Filters are always additive; filters will apply on top of the query you have in effect at the moment, whereas applying a query will replace the query in effect.</span></span>