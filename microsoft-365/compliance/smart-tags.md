---
title: Configurare gli smart tag in Advanced eDiscovery
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
description: Gli smart tag consentono di applicare le funzionalità di machine learning durante la revisione del contenuto in un caso di Advanced eDiscovery. Utilizzare i gruppi di smart tag per visualizzare i risultati dei modelli di rilevamento di machine learning, ad esempio il modello dei privilegi avvocato-client.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081083"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="56052-104">Configurare gli smart tag in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="56052-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="56052-105">Le funzionalità di machine learning (ML) in Advanced eDiscovery consentono di rendere più efficiente il processo decisionale quando si esaminano i documenti dei casi in un insieme da rivedere.</span><span class="sxs-lookup"><span data-stu-id="56052-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="56052-106">Gli smart tag sono un modo per portare le funzionalità ml in cui vengono registrate le decisioni: quando si contrassegnano i documenti durante la revisione.</span><span class="sxs-lookup"><span data-stu-id="56052-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="56052-107">Quando si crea un gruppo di smart tag, le decisioni che sono il risultato del modello ML associato al gruppo di smart tag vengono visualizzate in linea con i tag nel gruppo di tag.</span><span class="sxs-lookup"><span data-stu-id="56052-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="56052-108">Ciò consente di visualizzare le informazioni dei risultati di ML in linea durante la revisione di documenti specifici.</span><span class="sxs-lookup"><span data-stu-id="56052-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="56052-109">Come configurare un gruppo di smart tag</span><span class="sxs-lookup"><span data-stu-id="56052-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="56052-110">In un insieme di recensioni, fare clic **su Gestisci insieme** revisione e quindi su Gestisci **tag.**</span><span class="sxs-lookup"><span data-stu-id="56052-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="56052-111">Fare **clic su Aggiungi gruppo di tag** e quindi selezionare Aggiungi gruppo di smart **tag.**</span><span class="sxs-lookup"><span data-stu-id="56052-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="56052-112">Selezionare il modello ML che si desidera associare al gruppo di tag.</span><span class="sxs-lookup"><span data-stu-id="56052-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="56052-113">In questo modo vengono creati un gruppo di tag *e N* tag figlio, *dove N* è il numero di possibili output del modello.</span><span class="sxs-lookup"><span data-stu-id="56052-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="56052-114">Ad esempio, il [modello di rilevamento dei privilegi avvocato-client](attorney-privilege-detection.md) ha due possibili output:</span><span class="sxs-lookup"><span data-stu-id="56052-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="56052-115">**Positivo:** consente di contrassegnare i documenti che contengono contenuto privilegiato avvocato-client.</span><span class="sxs-lookup"><span data-stu-id="56052-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="56052-116">**Negativo:** consente di contrassegnare i documenti che non contengono contenuto privilegiato avvocato-client.</span><span class="sxs-lookup"><span data-stu-id="56052-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="56052-117">Se si seleziona questo modello, viene creato un gruppo di tag con due tag figlio (un tag figlio denominato **Positivo** e l'altro denominato **Negativo)** per il set di revisioni.</span><span class="sxs-lookup"><span data-stu-id="56052-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="56052-118">In questo esempio, ogni tag figlio corrisponde a uno dei possibili output del modello di rilevamento dei privilegi avvocato-client.</span><span class="sxs-lookup"><span data-stu-id="56052-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="56052-119">Facoltativamente, è possibile rinominare il gruppo di tag e i tag figlio.</span><span class="sxs-lookup"><span data-stu-id="56052-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="56052-120">Ad esempio, è possibile rinominare il tag **Positive** in **Privileged** e il tag **Negative** in **Not privileged.**</span><span class="sxs-lookup"><span data-stu-id="56052-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="56052-121">Come usare gli smart tag</span><span class="sxs-lookup"><span data-stu-id="56052-121">How to use smart tags</span></span>

<span data-ttu-id="56052-122">Durante la revisione di un documento, i risultati del modello vengono visualizzati accanto al tag figlio appropriato.</span><span class="sxs-lookup"><span data-stu-id="56052-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="56052-123">Ad esempio, se si dispone di un gruppo di smart tag per il rilevamento dei privilegi avvocato-client e si esamina un documento potenzialmente privilegiato, il motivo di tale conclusione viene visualizzato accanto al tag appropriato.</span><span class="sxs-lookup"><span data-stu-id="56052-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="56052-124">È importante notare che il tag non viene applicato automaticamente al documento.</span><span class="sxs-lookup"><span data-stu-id="56052-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="56052-125">Il revisore prende la decisione sulla modalità di applicazione di tag al documento.</span><span class="sxs-lookup"><span data-stu-id="56052-125">The reviewer makes the decision about how to tag the document.</span></span>
