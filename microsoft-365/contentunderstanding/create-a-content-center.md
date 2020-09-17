---
title: Creare un centro contenuto (anteprima)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come creare un centro contenuto.
ms.openlocfilehash: ae10cdae2fe84abf72cf09141798b628d88a504a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950097"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="61940-103">Creare un centro contenuto (anteprima)</span><span class="sxs-lookup"><span data-stu-id="61940-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="61940-104">Il contenuto di questo articolo è relativo all'anteprima privata di Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="61940-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="61940-105">[Per ulteriori informazioni, vedere Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="61940-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="61940-106">Per creare e gestire i modelli di comprensione del documento, è necessario innanzitutto un Content Center.</span><span class="sxs-lookup"><span data-stu-id="61940-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="61940-107">Content Center è l'interfaccia di creazione del modello e contiene anche informazioni sui modelli pubblicati dalle raccolte documenti.</span><span class="sxs-lookup"><span data-stu-id="61940-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![Selezionare una raccolta documenti](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="61940-109">Viene creato un centro contenuto iniziale durante l' [installazione](set-up-content-understanding.md), ma un amministratore di SharePoint può scegliere di crearne di nuovi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="61940-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="61940-110">Anche se un singolo centro contenuto può andare bene per gli ambienti in cui si desidera visualizzare un rollup di tutte le attività del modello, è possibile che si desideri aggiungere altre informazioni, se si dispone di più reparti all'interno dell'organizzazione, che potrebbero avere esigenze e requisiti diversi per i propri modelli.</span><span class="sxs-lookup"><span data-stu-id="61940-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="61940-111">Un amministratore di SharePoint può creare un sito Centro contenuto come [creare qualsiasi altro](https://docs.microsoft.com/sharepoint/create-site-collection) sito di SharePoint tramite un modello di sito.</span><span class="sxs-lookup"><span data-stu-id="61940-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="61940-112">Per creare un nuovo centro contenuto:</span><span class="sxs-lookup"><span data-stu-id="61940-112">To create a new content center:</span></span>

1. <span data-ttu-id="61940-113">Nell'interfaccia di amministrazione di Microsoft 365 passare all'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="61940-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="61940-114">Nell'interfaccia di amministrazione di SharePoint, in **siti**, selezionare **siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="61940-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="61940-115">Nella pagina **siti attivi** fare clic su **Crea**e quindi selezionare **altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="61940-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="61940-116">Scegliere **centro contenuto**dal menu **Scegli modello** .</span><span class="sxs-lookup"><span data-stu-id="61940-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="61940-117">Per il nuovo sito, specificare il **nome**di un sito, l' **amministratore principale**e una **lingua**.</span><span class="sxs-lookup"><span data-stu-id="61940-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="61940-118">È possibile selezionare un sito Centro contenuto per il rendering in una qualsiasi delle lingue disponibili, ma si noti che attualmente i modelli possono essere creati solo per i file in lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="61940-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="61940-119">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="61940-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="61940-120">Consentire l'accesso ad altri utenti</span><span class="sxs-lookup"><span data-stu-id="61940-120">Give access to additional users</span></span>
 
<span data-ttu-id="61940-121">Dopo la creazione del sito, è possibile concedere agli utenti ulteriori accesso al sito tramite il modello di autorizzazioni per il [sito di SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)standard.</span><span class="sxs-lookup"><span data-stu-id="61940-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="61940-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61940-122">See Also</span></span>
[<span data-ttu-id="61940-123">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="61940-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="61940-124">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="61940-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="61940-125">[Creare un centro contenuto](create-a-content-center.md) 
 [Panoramica della comprensione del documento](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="61940-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="61940-126">Creare un modello di elaborazione dei moduli</span><span class="sxs-lookup"><span data-stu-id="61940-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="61940-127">Applicazione di un modello</span><span class="sxs-lookup"><span data-stu-id="61940-127">Apply a model</span></span>](apply-a-model.md)    




