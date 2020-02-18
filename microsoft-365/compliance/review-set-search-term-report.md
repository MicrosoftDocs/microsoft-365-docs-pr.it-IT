---
title: Generare il rapporto termini di ricerca per un set di Revisione
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
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: d9c12777669eeb9e723602db20e0827b278c0d9e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081563"
---
# <a name="generate-search-term-report-for-a-review-set"></a><span data-ttu-id="294bb-102">Generare il rapporto termini di ricerca per un set di Revisione</span><span class="sxs-lookup"><span data-stu-id="294bb-102">Generate search term report for a review set</span></span>

<span data-ttu-id="294bb-103">In eDiscovery, una delle condizioni utilizzate più frequentemente per l'esecuzione di query nei documenti è l'utilizzo dei termini di ricerca parole chiave.</span><span class="sxs-lookup"><span data-stu-id="294bb-103">In eDiscovery, one of the most frequently used conditions for querying documents is by using keyword search terms.</span></span> <span data-ttu-id="294bb-104">Identificando i documenti che contengono le parole chiave specifiche (denominate anche *termini*) importanti per un caso, i revisori possono iniziare ad ottenere una comprensione di alto livello di cosa devono affrontare.</span><span class="sxs-lookup"><span data-stu-id="294bb-104">By identifying documents that contain the specific keywords (also referred to as *terms*) that are important to a case, reviewers can begin to get a high-level understanding of what they are facing.</span></span> <span data-ttu-id="294bb-105">In Advanced eDiscovery in Microsoft 365, è possibile eseguire questa operazione generando rapporti termini di ricerca per le query salvate all'interno di un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="294bb-105">In Advanced eDiscovery in Microsoft 365, you can do precisely this by generating search term reports on saved queries within a review set.</span></span>

## <a name="step-1-create-a-saved-query-in-the-review-set"></a><span data-ttu-id="294bb-106">Passaggio 1: creare una query salvata nel set di Revisione</span><span class="sxs-lookup"><span data-stu-id="294bb-106">Step 1: Create a saved query in the review set</span></span>

<span data-ttu-id="294bb-107">Per generare un rapporto di termini di ricerca significativo, creare una query salvata che definisce il set di documenti nel set di revisione per il quale si desidera generare un rapporto di termini di ricerca.</span><span class="sxs-lookup"><span data-stu-id="294bb-107">To generate a meaningful search term report, create a saved query that defines the set of documents in the review set that you want to generate a search term report for.</span></span> <span data-ttu-id="294bb-108">Ad esempio, è possibile utilizzare un intervallo di date o il set effettivo di termini di ricerca (utilizzando la scheda condizione parole chiave) per creare la query.</span><span class="sxs-lookup"><span data-stu-id="294bb-108">For example, you can use a date range or the actual set of search terms (by using the Keywords condition card) to create the query.</span></span> <span data-ttu-id="294bb-109">Per ulteriori informazioni sulle query dei set di revisione, vedere [query sui dati in un set di revisione](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="294bb-109">To learn more about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="step-2-generate-a-search-term-report"></a><span data-ttu-id="294bb-110">Passaggio 2: generare un rapporto di termini di ricerca</span><span class="sxs-lookup"><span data-stu-id="294bb-110">Step 2: Generate a search term report</span></span>

<span data-ttu-id="294bb-111">Esistono due modi diversi per generare un rapporto termini di ricerca: tramite il menu di scelta rapida della query salvata creata al passaggio 1 o tramite la console di gestione dei rapporti termini di ricerca.</span><span class="sxs-lookup"><span data-stu-id="294bb-111">There are two different ways to generate a search term report: through the context menu of the saved query you created in Step 1, or through the search term report management console.</span></span>

- <span data-ttu-id="294bb-112">Per utilizzare il menu di scelta rapida, aprire il menu di scelta rapida della query salvata creata nel passaggio 1, quindi fare clic su **Genera rapporto termini di ricerca**.</span><span class="sxs-lookup"><span data-stu-id="294bb-112">To use the context menu, open the context menu of the saved query you created in Step 1, and click **Generate search term report**.</span></span>

- <span data-ttu-id="294bb-113">Per utilizzare la console di gestione, andare a **Manage Review set > visualizzare i report dei termini di ricerca**, fare clic su **nuovo**e quindi selezionare la query salvata creata al passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="294bb-113">To use the management console, go to **Manage review set > View search term reports**, click **New**, and then select the saved query you created in Step 1.</span></span>

<span data-ttu-id="294bb-114">Immettere quindi i termini che si desidera segnalare, separati da NewLine. Se la query salvata creata al passaggio 1 è stata utilizzata la scheda condizione parola chiave, la pagina del riquadro a comparsa verrà prepopolata con i termini della prima scheda di condizione di parola chiave utilizzata nella query salvata.</span><span class="sxs-lookup"><span data-stu-id="294bb-114">Then, enter the terms you would like to report on, separated by newline; if the saved query that you created in Step 1 used keyword condition card, the flyout page will be pre-populated with the terms from the first keyword condition card used in the saved query.</span></span>

<span data-ttu-id="294bb-115">Selezionare fino a tre pivot per il report e quindi fare clic su **genera**, che avvierà il processo di generazione del rapporto termini di ricerca.</span><span class="sxs-lookup"><span data-stu-id="294bb-115">Then, select up to three pivots to report on, and click on **Generate**, which will start the search term report generation job.</span></span>

### <a name="what-is-a-pivot"></a><span data-ttu-id="294bb-116">Che cos'è un pivot?</span><span class="sxs-lookup"><span data-stu-id="294bb-116">What is a pivot?</span></span>

<span data-ttu-id="294bb-117">Pivot sono la modalità di organizzazione del rapporto.</span><span class="sxs-lookup"><span data-stu-id="294bb-117">Pivots are how the report will be organized.</span></span> <span data-ttu-id="294bb-118">Si consideri l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="294bb-118">Consider the following example.</span></span>

- <span data-ttu-id="294bb-119">La query salvata recupera 10 documenti: doc1 tramite doc10.</span><span class="sxs-lookup"><span data-stu-id="294bb-119">The saved query retrieves 10 documents: doc1 through doc10.</span></span>

- <span data-ttu-id="294bb-120">Doc1, Doc2, DOC3, DOC4, DOC5, DOC6 e DOC7 contengono il termine "eDiscovery".</span><span class="sxs-lookup"><span data-stu-id="294bb-120">doc1, doc2, doc3, doc4, doc5, doc6, and doc7 contain the term "eDiscovery".</span></span>

- <span data-ttu-id="294bb-121">DOC6, DOC7, DOC8, doc9 e doc10 contengono il termine "Investigation".</span><span class="sxs-lookup"><span data-stu-id="294bb-121">doc6, doc7, doc8, doc9, and doc10 contain the term "Investigation".</span></span>

- <span data-ttu-id="294bb-122">Doc1, DOC3, DOC5, DOC7, doc9 sono del custode A.</span><span class="sxs-lookup"><span data-stu-id="294bb-122">doc1, doc3, doc5, doc7, doc9 are from custodian A.</span></span>

- <span data-ttu-id="294bb-123">Doc2, DOC4, DOC6, DOC8, doc10 sono del custode B.</span><span class="sxs-lookup"><span data-stu-id="294bb-123">doc2, doc4, doc6, doc8, doc10 are from custodian B.</span></span>

<span data-ttu-id="294bb-124">In questo caso, se si desidera generare un rapporto sui termini "eDiscovery" e "Investigation" e pivot nei depositari, il report dei termini di ricerca verrebbe organizzato come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="294bb-124">In this case, if you were to generate a search term report on the terms "eDiscovery" and "Investigation" and pivot on custodians, the search term report would be organized as follows:</span></span>

- <span data-ttu-id="294bb-125">"eDiscovery"-custode A: 4 documenti</span><span class="sxs-lookup"><span data-stu-id="294bb-125">"eDiscovery" - custodian A: 4 documents</span></span>

- <span data-ttu-id="294bb-126">"eDiscovery"-custode B: 3 documenti</span><span class="sxs-lookup"><span data-stu-id="294bb-126">"eDiscovery" - custodian B: 3 documents</span></span>

- <span data-ttu-id="294bb-127">"Investigation"-custode A: 2 documenti</span><span class="sxs-lookup"><span data-stu-id="294bb-127">"Investigation" - custodian A: 2 documents</span></span>

- <span data-ttu-id="294bb-128">"Indagine"-custode B: 3 documenti</span><span class="sxs-lookup"><span data-stu-id="294bb-128">"Investigation" - custodian B: 3 documents</span></span>

## <a name="step-3-download-report"></a><span data-ttu-id="294bb-129">Passaggio 3: scaricare il report</span><span class="sxs-lookup"><span data-stu-id="294bb-129">Step 3: Download report</span></span>

<span data-ttu-id="294bb-130">Nella console di gestione dei termini di ricerca è possibile monitorare lo stato di un processo del rapporto termini di ricerca creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="294bb-130">In the search term management console, you can track the status of a previously-created search term report job.</span></span> <span data-ttu-id="294bb-131">Al termine del processo, è possibile fare clic sulla riga per il rapporto termini di ricerca e fare clic su "download", che scaricherà il rapporto termini di ricerca in formato CSV.</span><span class="sxs-lookup"><span data-stu-id="294bb-131">Once the job completes, you can click on the row for the search term report and click "Download", which will download the search term report in a CSV format.</span></span> <span data-ttu-id="294bb-132">Vi sarà una riga per ogni tupla (termine di ricerca, pivot) e ogni riga conterrà le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="294bb-132">There will be one row per (search term, pivots) tuple, and each row will contain the following information:</span></span>

- <span data-ttu-id="294bb-133">Quanti documenti sono stati recuperati?</span><span class="sxs-lookup"><span data-stu-id="294bb-133">How many documents were retrieved?</span></span>

- <span data-ttu-id="294bb-134">Quante volte è stato trovato il termine di ricerca nei documenti?</span><span class="sxs-lookup"><span data-stu-id="294bb-134">How many times was the search term found across the documents?</span></span>

- <span data-ttu-id="294bb-135">Qual è il volume totale dei documenti recuperati?</span><span class="sxs-lookup"><span data-stu-id="294bb-135">What is the total volume of retrieved documents?</span></span>

- <span data-ttu-id="294bb-136">Quante famiglie sono state recuperate?</span><span class="sxs-lookup"><span data-stu-id="294bb-136">How many families were retrieved?</span></span>

- <span data-ttu-id="294bb-137">Qual è il numero totale di documenti di tali famiglie, inclusi i documenti che non hanno il termine di ricerca?</span><span class="sxs-lookup"><span data-stu-id="294bb-137">What is the total document count of those families, including the documents that did not have the search term?</span></span>

- <span data-ttu-id="294bb-138">Qual è il volume totale di quanto sopra?</span><span class="sxs-lookup"><span data-stu-id="294bb-138">What is the total volume of the above?</span></span>
