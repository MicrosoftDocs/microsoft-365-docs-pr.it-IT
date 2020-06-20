---
title: Aggiungere dati da un set di revisione a un altro set di Revisione
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
description: Informazioni su come selezionare i documenti da un set di revisione e utilizzarli singolarmente in un altro set in un caso di eDiscovery avanzato.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 433e59629ec40dbdf66b8daf6437ce84e41a3a33
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818603"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="79354-103">Aggiungere dati a un set di revisione da un altro set di Revisione</span><span class="sxs-lookup"><span data-stu-id="79354-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="79354-104">In alcuni casi, potrebbe essere necessario selezionare i documenti da un set di revisione e utilizzarli singolarmente in un altro set di revisione.</span><span class="sxs-lookup"><span data-stu-id="79354-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="79354-105">Questo è particolarmente utile se si è abbattuti contenuti in un set di revisione e si vuole eseguire l'analisi del sottoinsieme di dati.</span><span class="sxs-lookup"><span data-stu-id="79354-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="79354-106">Seguire il flusso di lavoro in questo articolo per aggiungere contenuto da un set di revisione a un altro.</span><span class="sxs-lookup"><span data-stu-id="79354-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="79354-107">Creare un set di Revisione</span><span class="sxs-lookup"><span data-stu-id="79354-107">Create a review set</span></span>

<span data-ttu-id="79354-108">Prima di iniziare, è necessario creare un set di revisione a cui aggiungere i dati.</span><span class="sxs-lookup"><span data-stu-id="79354-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="79354-109">È possibile aggiungere un nuovo set di revisione nella scheda **revisione dei set** del caso.</span><span class="sxs-lookup"><span data-stu-id="79354-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="79354-110">Per ulteriori informazioni, vedere [creare un set di revisione](managing-review-sets.md#create-a-review-set).</span><span class="sxs-lookup"><span data-stu-id="79354-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="79354-111">Passaggio 1: identificare il contenuto da aggiungere a un altro set di Revisione</span><span class="sxs-lookup"><span data-stu-id="79354-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="79354-112">È possibile aggiungere contenuto da un set di revisione a un altro selezionando documenti specifici nel set di revisione del codice sorgente o selezionando tutti gli elementi restituiti dalla query set di revisione.</span><span class="sxs-lookup"><span data-stu-id="79354-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="79354-113">Se si aggiungono elementi selezionati, selezionare gli elementi, fare clic su **azione**, quindi selezionare **Aggiungi a un altro set di revisione**.</span><span class="sxs-lookup"><span data-stu-id="79354-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Aggiungi a un altro set di Revisione](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="79354-115">Passaggio 2: specificare le opzioni per l'aggiunta a un altro set di Revisione</span><span class="sxs-lookup"><span data-stu-id="79354-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="79354-116">Nella pagina **Aggiungi a un altro** riquadro a comparsa Opzioni del set di revisione scegliere il set di revisione a cui si desidera aggiungere gli elementi.</span><span class="sxs-lookup"><span data-stu-id="79354-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="79354-117">Scegliere se aggiungere **tutti i risultati di ricerca** o **gli elementi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="79354-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="79354-118">**Altre informazioni** forniscono opzioni per includere tutti i metadati dagli elementi e se includere i tag (selezionando la casella di controllo **etichette** ) dal set di revisione di origine quando i documenti vengono aggiunti al nuovo set di revisione.</span><span class="sxs-lookup"><span data-stu-id="79354-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Aggiungi a un altro set di Revisione](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="79354-120">Dopo aver fatto clic su **OK**, viene creato un nuovo processo (denominato **aggiunta di dati a un altro set di revisione**) per aggiungere il contenuto a un altro set di revisione.</span><span class="sxs-lookup"><span data-stu-id="79354-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="79354-121">È possibile passare alla scheda **processi** e monitorare lo stato di avanzamento del processo.</span><span class="sxs-lookup"><span data-stu-id="79354-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="79354-122">Per ulteriori informazioni, vedere [gestire i processi](managing-jobs-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="79354-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
