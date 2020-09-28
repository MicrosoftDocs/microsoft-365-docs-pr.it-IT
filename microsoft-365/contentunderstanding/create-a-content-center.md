---
title: Creare un centro contenuto in Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come creare un centro contenuto.
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295433"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="7d114-103">Creare un centro contenuto in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="7d114-103">Create a content center in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="7d114-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="7d114-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="7d114-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="7d114-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="7d114-106">Per creare e gestire i modelli di comprensione del documento, è necessario innanzitutto un Content Center.</span><span class="sxs-lookup"><span data-stu-id="7d114-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="7d114-107">Content Center è l'interfaccia di creazione del modello e contiene anche informazioni sui modelli a cui sono state applicate le raccolte documenti.</span><span class="sxs-lookup"><span data-stu-id="7d114-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Selezionare una raccolta documenti](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="7d114-109">È possibile creare un centro contenuto iniziale durante l' [installazione](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="7d114-109">You create an initial content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="7d114-110">Tuttavia, un amministratore di SharePoint può anche scegliere di creare ulteriori centri in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="7d114-110">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="7d114-111">Anche se un singolo centro contenuto può andare bene per gli ambienti per cui si desidera eseguire il rollup di tutte le attività del modello, è possibile che si desideri disporre di ulteriori centri per più reparti all'interno dell'organizzazione, che potrebbero avere esigenze e requisiti diversi per i propri modelli.</span><span class="sxs-lookup"><span data-stu-id="7d114-111">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="7d114-112">Un amministratore di SharePoint può creare un sito Centro contenuto come [creare qualsiasi altro sito di SharePoint](https://docs.microsoft.com/sharepoint/create-site-collection) utilizzando un modello di sito.</span><span class="sxs-lookup"><span data-stu-id="7d114-112">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) by using a site template.</span></span>

<span data-ttu-id="7d114-113">Per creare un nuovo centro contenuto:</span><span class="sxs-lookup"><span data-stu-id="7d114-113">To create a new content center:</span></span>

1. <span data-ttu-id="7d114-114">Nell'interfaccia di amministrazione di Microsoft 365 passare all'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7d114-114">From the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="7d114-115">Nell'interfaccia di amministrazione di SharePoint, in **siti**, selezionare **siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="7d114-115">In the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="7d114-116">Nella pagina **siti attivi** fare clic su **Crea**e quindi selezionare **altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="7d114-116">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="7d114-117">Scegliere **centro contenuto**dal menu **Scegli modello** .</span><span class="sxs-lookup"><span data-stu-id="7d114-117">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="7d114-118">Per il nuovo sito, specificare il **nome**di un sito, l' **amministratore principale**e una **lingua**.</span><span class="sxs-lookup"><span data-stu-id="7d114-118">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="7d114-119">Facoltativamente, è possibile selezionare un sito Centro contenuto per il rendering in una delle lingue disponibili.</span><span class="sxs-lookup"><span data-stu-id="7d114-119">You can optionally select a content center site to render in any of the available languages.</span></span> <span data-ttu-id="7d114-120">Solo i modelli correnti possono essere creati per i file in lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="7d114-120">Only current models can be created for English files.</span></span></br>

6. <span data-ttu-id="7d114-121">Selezionare **completata**.</span><span class="sxs-lookup"><span data-stu-id="7d114-121">Select **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="7d114-122">Consentire l'accesso ad altri utenti</span><span class="sxs-lookup"><span data-stu-id="7d114-122">Give access to additional users</span></span>
 
<span data-ttu-id="7d114-123">Dopo aver creato il sito, è possibile concedere agli utenti ulteriori accesso al sito tramite il modello di autorizzazioni per il [sito di SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)standard.</span><span class="sxs-lookup"><span data-stu-id="7d114-123">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d114-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d114-124">See Also</span></span>
[<span data-ttu-id="7d114-125">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="7d114-125">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="7d114-126">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="7d114-126">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="7d114-127">[Creare un centro contenuto](create-a-content-center.md) 
 [Panoramica della comprensione del documento](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7d114-127">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="7d114-128">Creare un modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="7d114-128">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="7d114-129">Applicazione di un modello</span><span class="sxs-lookup"><span data-stu-id="7d114-129">Apply a model</span></span>](apply-a-model.md)    
