---
title: Configurare gli smart tag in Advanced eDiscovery
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
description: Gli smart tag consentono di applicare le funzionalità di apprendimento automatico quando si esaminano i contenuti in un caso avanzato di eDiscovery. Utilizzare i gruppi di smart tag per visualizzare i risultati dei modelli di rilevamento di apprendimento automatico, ad esempio il modello di privilegio avvocato-client.
ms.openlocfilehash: 68b558cc2282cc388387f8d61825b9ee569ff32a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084114"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="9ba57-104">Configurare gli smart tag in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="9ba57-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="9ba57-105">Le funzionalità di apprendimento automatico (ML) in Advanced eDiscovery consentono di rendere il processo decisionale più efficiente quando si esaminano i documenti dei casi in un set di revisione.</span><span class="sxs-lookup"><span data-stu-id="9ba57-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="9ba57-106">Gli smart tag rappresentano un modo per portare le funzionalità ML in cui vengono registrate le decisioni: quando si contrassegnano i documenti durante la revisione.</span><span class="sxs-lookup"><span data-stu-id="9ba57-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="9ba57-107">Quando si crea un gruppo di smart tag, le decisioni che sono il risultato del modello ML associato al gruppo smart tag vengono visualizzate in linea con i tag del gruppo di tag.</span><span class="sxs-lookup"><span data-stu-id="9ba57-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="9ba57-108">Questo consente di visualizzare le informazioni sui risultati in linea quando si stanno esaminando documenti specifici.</span><span class="sxs-lookup"><span data-stu-id="9ba57-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="9ba57-109">Come configurare un gruppo di smart tag</span><span class="sxs-lookup"><span data-stu-id="9ba57-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="9ba57-110">In un set di Revisione fare clic su **Gestisci Revisione set** e quindi su **Gestisci Tag**.</span><span class="sxs-lookup"><span data-stu-id="9ba57-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="9ba57-111">Fare clic su **Aggiungi gruppo Tag** e quindi selezionare **Aggiungi gruppo smart tag**.</span><span class="sxs-lookup"><span data-stu-id="9ba57-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="9ba57-112">Selezionare il modello ML che si desidera associare al gruppo di tag.</span><span class="sxs-lookup"><span data-stu-id="9ba57-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="9ba57-113">In questo modo viene creato un gruppo di tag e *n* tag figlio, dove *n* è il numero di output possibili del modello.</span><span class="sxs-lookup"><span data-stu-id="9ba57-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="9ba57-114">Ad esempio, il [modello di rilevamento dei privilegi avvocato-client](attorney-privilege-detection.md) ha due possibili output:</span><span class="sxs-lookup"><span data-stu-id="9ba57-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="9ba57-115">**Positivo** : consente di contrassegnare i documenti che contengono contenuto privilegiato avvocato-client.</span><span class="sxs-lookup"><span data-stu-id="9ba57-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="9ba57-116">**Negativo** : consente di contrassegnare i documenti che non contengono contenuto privilegiato avvocato-client.</span><span class="sxs-lookup"><span data-stu-id="9ba57-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="9ba57-117">Se si seleziona questo modello, viene creato un gruppo di tag con due tag figlio (un tag figlio con nome **positivo** e l'altro **negativo**) per il set di revisione.</span><span class="sxs-lookup"><span data-stu-id="9ba57-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="9ba57-118">In questo esempio, ogni tag figlio corrisponde a uno dei possibili output del modello di rilevamento dei privilegi avvocato-client.</span><span class="sxs-lookup"><span data-stu-id="9ba57-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="9ba57-119">Facoltativamente, è possibile rinominare il gruppo di tag e i tag figlio.</span><span class="sxs-lookup"><span data-stu-id="9ba57-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="9ba57-120">Ad esempio, è possibile rinominare il tag **positivo** su **Privileged** e il tag **negative** su **not Privileged**.</span><span class="sxs-lookup"><span data-stu-id="9ba57-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="9ba57-121">Come usare gli smart tag</span><span class="sxs-lookup"><span data-stu-id="9ba57-121">How to use smart tags</span></span>

<span data-ttu-id="9ba57-122">Quando si esamina un documento, i risultati del modello vengono visualizzati accanto al tag figlio appropriato.</span><span class="sxs-lookup"><span data-stu-id="9ba57-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="9ba57-123">Ad esempio, se si dispone di un gruppo di smart tag per il rilevamento dei privilegi avvocato-client e si esamina un documento potenzialmente privilegiato, la causa di tale conclusione viene visualizzata accanto al tag appropriato.</span><span class="sxs-lookup"><span data-stu-id="9ba57-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="9ba57-124">È importante tenere presente che il tag non viene applicato automaticamente al documento.</span><span class="sxs-lookup"><span data-stu-id="9ba57-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="9ba57-125">Il revisore prende la decisione su come contrassegnare il documento.</span><span class="sxs-lookup"><span data-stu-id="9ba57-125">The reviewer makes the decision about how to tag the document.</span></span>