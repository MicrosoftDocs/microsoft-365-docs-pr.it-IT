---
title: Ritiro del modulo di pertinenza in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
description: Il modulo Pertinenza in Advanced eDiscovery verrà ritirato il 10 marzo 2021. Questo articolo spiega cosa fare prima che la rilevanza venga ritirata. In particolare, completare tutti i modelli non completati eseguendo il calcolo batch in modo da poter conservare i metadati del modello.
ms.openlocfilehash: 0719c2cb1b6b0d867ffc045fe02d57e1e2f32a61
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821998"
---
# <a name="retirement-of-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="a164c-105">Ritiro del modulo Pertinenza in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a164c-105">Retirement of the Relevance module in Advanced eDiscovery</span></span>

<span data-ttu-id="a164c-106">Il 10 marzo 2021 ritiriamo il modulo Pertinenza in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a164c-106">On March 10, 2021, we are retiring the Relevance module in Advanced eDiscovery.</span></span> <span data-ttu-id="a164c-107">Questo ritiro significa che le organizzazioni non avranno più accesso al modulo Pertinenza (accedendo a Gestisci set di revisione Pertinenza in un caso di Advanced eDiscovery) o potranno accedere ai modelli di pertinenza  >   esistenti.</span><span class="sxs-lookup"><span data-stu-id="a164c-107">This retirement means that organizations will no longer have access to the Relevance module (by going to **Manage review set** > **Relevance** in an Advanced eDiscovery case) or be able to access any existing Relevance models.</span></span> <span data-ttu-id="a164c-108">Il modulo di rilevanza corrente in fase di ritiro verrà sostituito con una nuova soluzione di codifica predittiva nel Q2 CY 2021.</span><span class="sxs-lookup"><span data-stu-id="a164c-108">The current Relevance module that is being retired will be replaced with a new predictive coding solution in Q2 CY 2021.</span></span> <span data-ttu-id="a164c-109">Questa nuova funzionalità consente alle organizzazioni di creare modelli di codifica predittivi personalizzati in un flusso di lavoro più semplice e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="a164c-109">This new functionality will let organizations build their own predictive coding models in an easier and more intuitive workflow.</span></span>

<span data-ttu-id="a164c-110">Per prepararsi a questo ritiro imminente, è consigliabile che le organizzazioni che utilizzano il modulo Pertinenza esportino l'output del modello prima della data di ritiro eseguendo un calcolo batch per tutti i modelli esistenti.</span><span class="sxs-lookup"><span data-stu-id="a164c-110">To prepare for this upcoming retirement, we recommend that organizations who use the Relevance module export their model’s output before the retirement date by running a Batch calculation for all existing models.</span></span> <span data-ttu-id="a164c-111">Tutti i punteggi di pertinenza del modello verranno archiviati in modo permanente nel set di revisione corrispondente e accessibili quando i documenti vengono esportati.</span><span class="sxs-lookup"><span data-stu-id="a164c-111">All Relevance scores from your model will be permanently stored in the corresponding review set and accessible when documents are exported.</span></span> <span data-ttu-id="a164c-112">I punteggi di pertinenza vengono mantenuti anche come metadati nel file di caricamento.</span><span class="sxs-lookup"><span data-stu-id="a164c-112">Relevance scores are also retained as metadata in the load file.</span></span> <span data-ttu-id="a164c-113">Inoltre, sarà comunque possibile filtrare il contenuto nel set di recensioni in base al punteggio di pertinenza e avere accesso a tutti i metadati prodotti dai modelli di pertinenza.</span><span class="sxs-lookup"><span data-stu-id="a164c-113">Also, you will still be able to filter content in the review set based on relevance score and have access to all metadata produced by your Relevance models.</span></span>

## <a name="complete-unfinished-models"></a><span data-ttu-id="a164c-114">Completare i modelli non completati</span><span class="sxs-lookup"><span data-stu-id="a164c-114">Complete unfinished models</span></span>

<span data-ttu-id="a164c-115">Per tutti i modelli di pertinenza non completati, completare la valutazione, la formazione e il calcolo batch in modo da poter applicare il modello ai documenti in un set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="a164c-115">For any unfinished Relevance models, please complete assessment, training, and Batch calculation so that you can apply the model to the documents in a review set.</span></span> <span data-ttu-id="a164c-116">Il completamento del calcolo batch conserverà le informazioni dopo la data di ritiro del modulo Pertinenza.</span><span class="sxs-lookup"><span data-stu-id="a164c-116">Completing the Batch calculation will preserve the information after the retirement date of the Relevance module.</span></span>

<span data-ttu-id="a164c-117">Ecco i passaggi per completare tutti i modelli non completati:</span><span class="sxs-lookup"><span data-stu-id="a164c-117">Here are the steps to complete any unfinished models:</span></span>

1. <span data-ttu-id="a164c-118">Eseguire il training del modello fino a quando non viene stabilizzato e pronto per il calcolo batch.</span><span class="sxs-lookup"><span data-stu-id="a164c-118">Train your model until it is stabilized and ready for Batch calculation.</span></span> <span data-ttu-id="a164c-119">Vedi [Formazione su tagging e pertinenza.](tagging-and-relevance-training-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="a164c-119">See [Tagging and Relevance training](tagging-and-relevance-training-in-advanced-ediscovery.md).</span></span>

   <span data-ttu-id="a164c-120">Lo screenshot seguente mostra un modulo pronto per un calcolo batch.</span><span class="sxs-lookup"><span data-stu-id="a164c-120">The following screenshot shows a module that is ready for a Batch calculation.</span></span> <span data-ttu-id="a164c-121">Si noti che la valutazione e la formazione sono completate e il passaggio successivo consiste nell'eseguire il calcolo batch.</span><span class="sxs-lookup"><span data-stu-id="a164c-121">Notice that the Assessment and Training is complete, and the next step is to run Batch calculation.</span></span>

   ![Screenshot del modello pronto per il calcolo batch](../media/ReadyForBatchCalculation.png)

2. <span data-ttu-id="a164c-123">Eseguire il calcolo batch.</span><span class="sxs-lookup"><span data-stu-id="a164c-123">Run the Batch calculation.</span></span> <span data-ttu-id="a164c-124">Vedere [Esecuzione del calcolo batch](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span><span class="sxs-lookup"><span data-stu-id="a164c-124">See [Performing Batch calculation](track-relevance-analysis-in-advanced-ediscovery.md#performing-batch-calculation).</span></span>

3. <span data-ttu-id="a164c-125">Verificare che il calcolo batch sia stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a164c-125">Verify that Batch calculation was successful.</span></span> <span data-ttu-id="a164c-126">Vedere [Risultati del calcolo batch](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span><span class="sxs-lookup"><span data-stu-id="a164c-126">See [Batch calculation results](track-relevance-analysis-in-advanced-ediscovery.md#batch-calculation-results).</span></span>

<span data-ttu-id="a164c-127">Per assistenza nel completamento dei modelli di pertinenza non completati, contattare il supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a164c-127">For help with completing unfinished Relevance models, contact Microsoft Support.</span></span>
