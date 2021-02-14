---
title: Aggiungere dati da un insieme di recensioni a un altro insieme da rivedere
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
description: Informazioni su come selezionare i documenti da un insieme da rivedere e lavorarvi singolarmente in un altro set in un caso di Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: e03cd042ac11c36838e712ccd945bc249b849f43
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285180"
---
# <a name="add-data-to-a-review-set-from-another-review-set"></a><span data-ttu-id="420d4-103">Aggiungere dati a un insieme di recensioni da un altro insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="420d4-103">Add data to a review set from another review set</span></span>

<span data-ttu-id="420d4-104">In alcuni casi, potrebbe essere necessario selezionare i documenti da un insieme da rivedere e lavorarvi singolarmente in un altro insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="420d4-104">In some cases, it may be necessary to select documents from one review set and work with them individually in another review set.</span></span> <span data-ttu-id="420d4-105">Ciò è particolarmente utile se hai eseguito ilculled del contenuto in un insieme da rivedere e vuoi eseguire analisi sul sottoinsieme di dati.</span><span class="sxs-lookup"><span data-stu-id="420d4-105">This is especially useful if you've culled content in a review set and want to run analytics on the subset of data.</span></span>

<span data-ttu-id="420d4-106">Seguire il flusso di lavoro in questo articolo per aggiungere contenuto da un insieme da rivedere a un altro.</span><span class="sxs-lookup"><span data-stu-id="420d4-106">Follow the workflow in this article to add content from one review set to another.</span></span>

## <a name="create-a-review-set"></a><span data-ttu-id="420d4-107">Creare un set di recensioni</span><span class="sxs-lookup"><span data-stu-id="420d4-107">Create a review set</span></span>

<span data-ttu-id="420d4-108">Prima di iniziare, dovrai creare un insieme da rivedere a cui aggiungere i dati.</span><span class="sxs-lookup"><span data-stu-id="420d4-108">Before you start, you'll need to create a review set to add the data to.</span></span>  <span data-ttu-id="420d4-109">È possibile aggiungere un nuovo insieme di recensioni nella scheda **Insiemi di recensioni** del caso.</span><span class="sxs-lookup"><span data-stu-id="420d4-109">A new review set can be added on the **Review sets** tab of the case.</span></span> <span data-ttu-id="420d4-110">Per ulteriori informazioni, vedere [Creare un insieme da rivedere.](managing-review-sets.md#create-a-review-set)</span><span class="sxs-lookup"><span data-stu-id="420d4-110">For more information, see [Create a review set](managing-review-sets.md#create-a-review-set).</span></span>

## <a name="step-1-identify-content-to-add-to-another-review-set"></a><span data-ttu-id="420d4-111">Passaggio 1: identificare il contenuto da aggiungere a un altro insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="420d4-111">Step 1: Identify content to add to another review set</span></span>

<span data-ttu-id="420d4-112">È possibile aggiungere contenuto da un insieme da rivedere a un altro selezionando documenti specifici nel set di revisioni di origine o selezionando tutti gli elementi restituiti dalla query del set di recensioni.</span><span class="sxs-lookup"><span data-stu-id="420d4-112">You can add content from one review set to another one by selecting specific documents in the source review set or by selecting all items returned by review set query.</span></span> <span data-ttu-id="420d4-113">Se si aggiungono elementi selezionati, selezionarli, selezionare **Azione** e quindi selezionare **Aggiungi a un altro insieme da rivedere.**</span><span class="sxs-lookup"><span data-stu-id="420d4-113">If you're adding selected items, select the items, select **Action**, and then select **Add to another review set**.</span></span>

![Aggiungi a un altro insieme di recensioni nel menu Azione](../media/64f2a4d4-eba3-4ab3-a3ba-d519feea3142.png)

## <a name="step-2-specify-options-for-adding-to-another-review-set"></a><span data-ttu-id="420d4-115">Passaggio 2: specificare le opzioni per l'aggiunta a un altro insieme da rivedere</span><span class="sxs-lookup"><span data-stu-id="420d4-115">Step 2: Specify options for adding to another review set</span></span>

<span data-ttu-id="420d4-116">Nella pagina **a comparsa Aggiungi a un'altra** revisione imposta opzioni, scegliere il set di recensioni a cui si desidera aggiungere gli elementi.</span><span class="sxs-lookup"><span data-stu-id="420d4-116">In the **Add to another review set options** flyout page, choose the review set you want to add the items to.</span></span> <span data-ttu-id="420d4-117">Scegliere se aggiungere tutti **i risultati della ricerca** o gli elementi **selezionati.**</span><span class="sxs-lookup"><span data-stu-id="420d4-117">Choose whether to add **All search results** or **Selected items**.</span></span>  <span data-ttu-id="420d4-118">**Ulteriori informazioni** forniscono opzioni per includere tutti i metadati degli elementi  e se includere i tag (selezionando la casella di controllo Etichette) dall'insieme di revisione di origine quando i documenti vengono aggiunti al nuovo insieme di revisioni.</span><span class="sxs-lookup"><span data-stu-id="420d4-118">**Additional information** provides options to include all metadata from the items and whether to include the tags (by selecting the **Labels** check box) from the source review set when the documents are added to the new review set.</span></span>  

![Opzioni per l'aggiunta di dati a un altro insieme da rivedere](../media/6440ee44-68fd-44d7-b43a-3a477345525c.png)

<span data-ttu-id="420d4-120">Dopo aver fatto clic su **OK,** viene creato un nuovo processo, denominato Aggiunta di dati a un altro **insieme** da rivedere, per aggiungere il contenuto a un altro insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="420d4-120">After you click **Ok**, a new job (named **Adding data to another review set**) is created to add the content to another review set.</span></span> <span data-ttu-id="420d4-121">È possibile passare alla scheda **Processi** e monitorare lo stato di avanzamento del processo.</span><span class="sxs-lookup"><span data-stu-id="420d4-121">You can go to the **Jobs** tab and monitor the progress of this job.</span></span> <span data-ttu-id="420d4-122">Per ulteriori informazioni, vedere [Manage jobs.](managing-jobs-ediscovery20.md)</span><span class="sxs-lookup"><span data-stu-id="420d4-122">For more information, see [Manage jobs](managing-jobs-ediscovery20.md).</span></span>
