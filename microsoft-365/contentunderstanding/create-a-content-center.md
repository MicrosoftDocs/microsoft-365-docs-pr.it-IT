---
title: Creare un centro contenuti in Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Informazioni su come creare un centro contenuti.
ms.openlocfilehash: f65b542dfe9cbb945f347323053cee582deef25b
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321834"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="d344d-103">Creare un centro contenuti in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="d344d-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="d344d-104">Per creare e gestire i modelli di analisi del documento, è necessario prima di tutto un centro contenuti.</span><span class="sxs-lookup"><span data-stu-id="d344d-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="d344d-105">Il centro contenuti è l'interfaccia per la creazione di modelli e include anche informazioni sulle raccolte documenti a cui sono stati applicati i modelli pubblicati.</span><span class="sxs-lookup"><span data-stu-id="d344d-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Selezionare una raccolta documenti](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="d344d-107">È possibile creare un centro contenuti predefinito durante la [configurazione](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="d344d-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="d344d-108">Ma un amministratore di SharePoint può anche scegliere di creare altri centri, se necessario.</span><span class="sxs-lookup"><span data-stu-id="d344d-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="d344d-109">Anche se un singolo centro contenuti può essere utile per gli ambienti in cui si vuole eseguire un rollup di tutte le attività del modello, è consigliabile avere altri centri per più reparti all'interno dell'organizzazione, che possono avere esigenze e requisiti di autorizzazione diversi per i propri modelli.</span><span class="sxs-lookup"><span data-stu-id="d344d-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="d344d-110">Un amministratore di SharePoint può creare un sito del centro contenuti come [creerebbe qualsiasi altro sito di SharePoint](https://docs.microsoft.com/sharepoint/create-site-collection) tramite il pannello di provisioning del sito dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d344d-110">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="d344d-111">Per creare un nuovo centro contenuti:</span><span class="sxs-lookup"><span data-stu-id="d344d-111">To create a new content center:</span></span>

1. <span data-ttu-id="d344d-112">Nell'interfaccia di amministrazione di Microsoft 365, passare all’interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d344d-112">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="d344d-113">Nella interfaccia di amministrazione di SharePoint selezionare **Siti attivi** in **Siti**.</span><span class="sxs-lookup"><span data-stu-id="d344d-113">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="d344d-114">Nella pagina **Siti attivi** fare clic su **Creare**e quindi selezionare **Altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="d344d-114">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="d344d-115">Nel menu **Scegliere un modello**, selezionare **Centro contenuti**.</span><span class="sxs-lookup"><span data-stu-id="d344d-115">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="d344d-116">Per il nuovo sito, fornire un **nome del sito**, un **amministratore principale** e una **lingua**.</span><span class="sxs-lookup"><span data-stu-id="d344d-116">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="d344d-117">È possibile selezionare un sito del centro contenuti per il rendering in una qualsiasi delle lingue disponibili, ma si noti che attualmente i modelli possono essere creati solo per i file in inglese.</span><span class="sxs-lookup"><span data-stu-id="d344d-117">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="d344d-118">Si noti anche che, come altri modelli di sito, la lingua del sito predefinita non è modificabile dopo la creazione del sito.</span><span class="sxs-lookup"><span data-stu-id="d344d-118">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="d344d-119">Selezionare **Completato**.</span><span class="sxs-lookup"><span data-stu-id="d344d-119">Select **Finished**.</span></span>
 
<span data-ttu-id="d344d-120">Dopo aver creato un sito del centro contenuti, questo verrà elencato nella pagina **Siti attivi** nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d344d-120">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="d344d-121">Assegnare l'accesso ad altri utenti</span><span class="sxs-lookup"><span data-stu-id="d344d-121">Give access to additional users</span></span>
 
<span data-ttu-id="d344d-122">Dopo aver creato il sito, è possibile concedere ad altri utenti l'accesso al sito tramite il [modello di autorizzazioni del sito di SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)standard.</span><span class="sxs-lookup"><span data-stu-id="d344d-122">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="d344d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d344d-123">See Also</span></span>
[<span data-ttu-id="d344d-124">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="d344d-124">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="d344d-125">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="d344d-125">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="d344d-126">Creare un centro contenuti</span><span class="sxs-lookup"><span data-stu-id="d344d-126">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="d344d-127">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="d344d-127">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="d344d-128">Creare un modello di elaborazione moduli</span><span class="sxs-lookup"><span data-stu-id="d344d-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="d344d-129">Applicare un modello</span><span class="sxs-lookup"><span data-stu-id="d344d-129">Apply a model</span></span>](apply-a-model.md)    
