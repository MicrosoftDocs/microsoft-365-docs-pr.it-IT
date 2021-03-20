---
title: Creare un centro contenuti in Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Informazioni su come creare un centro contenuti.
ms.openlocfilehash: 34ba45cd62214743e5a6784893e0f24e9815fdfb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905825"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="68452-103">Creare un centro contenuti in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="68452-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="68452-104">Per creare e gestire i modelli di analisi del documento, è necessario prima di tutto un centro contenuti.</span><span class="sxs-lookup"><span data-stu-id="68452-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="68452-105">Il centro contenuti è l'interfaccia per la creazione di modelli e include anche informazioni sulle raccolte documenti a cui sono stati applicati i modelli pubblicati.</span><span class="sxs-lookup"><span data-stu-id="68452-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Selezionare una raccolta documenti](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="68452-107">È possibile creare un centro contenuti predefinito durante la [configurazione](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="68452-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="68452-108">Ma un amministratore di SharePoint può anche scegliere di creare altri centri, se necessario.</span><span class="sxs-lookup"><span data-stu-id="68452-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="68452-109">Anche se un singolo centro contenuti può essere utile per gli ambienti in cui si vuole eseguire un rollup di tutte le attività del modello, è consigliabile avere altri centri per più reparti all'interno dell'organizzazione, che possono avere esigenze e requisiti di autorizzazione diversi per i propri modelli.</span><span class="sxs-lookup"><span data-stu-id="68452-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="68452-110">In un [ambiente Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md) se si ha un unico centro contenuti predefinito nella posizione centrale, è possibile fornire un roll-up dell'attività del modello solo dall'interno di tale posizione.</span><span class="sxs-lookup"><span data-stu-id="68452-110">In a [Microsoft 365 Multi-Geo environment](../enterprise/microsoft-365-multi-geo.md), if you have a single default content center in your central location, you can only provide a roll-up of model activity from within that location.</span></span> <span data-ttu-id="68452-111">Attualmente non è possibile ottenere un roll-up dell'attività del modello attraverso i limiti della farm nell'ambiente multi-geografico.</span><span class="sxs-lookup"><span data-stu-id="68452-111">You currently cannot get a roll-up of model activity across farm-boundaries in Multi-Geo environment.</span></span> 


## <a name="create-a-content-center"></a><span data-ttu-id="68452-112">Creare un centro contenuti</span><span class="sxs-lookup"><span data-stu-id="68452-112">Create a content center</span></span>

<span data-ttu-id="68452-113">Un amministratore di SharePoint può creare un sito del centro contenuti come [creerebbe qualsiasi altro sito di SharePoint](/sharepoint/create-site-collection) tramite il pannello di provisioning del sito dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="68452-113">A SharePoint admin can create a content center site like they would [create any other SharePoint site](/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="68452-114">Per creare un nuovo centro contenuti:</span><span class="sxs-lookup"><span data-stu-id="68452-114">To create a new content center:</span></span>

1. <span data-ttu-id="68452-115">Nell'interfaccia di amministrazione di Microsoft 365, passare all’interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="68452-115">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>

2. <span data-ttu-id="68452-116">Nella interfaccia di amministrazione di SharePoint selezionare **Siti attivi** in **Siti**.</span><span class="sxs-lookup"><span data-stu-id="68452-116">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>

3. <span data-ttu-id="68452-117">Nella pagina **Siti attivi** fare clic su **Creare** e quindi selezionare **Altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="68452-117">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>

4. <span data-ttu-id="68452-118">Nel menu **Scegliere un modello**, selezionare **Centro contenuti**.</span><span class="sxs-lookup"><span data-stu-id="68452-118">On the **Choose a template** menu, select **Content Center**.</span></span>

5. <span data-ttu-id="68452-119">Per il nuovo sito, fornire un **nome del sito**, un **amministratore principale** e una **lingua**.</span><span class="sxs-lookup"><span data-stu-id="68452-119">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

   > [!NOTE] 
   > <span data-ttu-id="68452-120">È possibile selezionare un sito del centro contenuti per il rendering in una qualsiasi delle lingue disponibili, ma si noti che attualmente i modelli possono essere creati solo per i file in inglese.</span><span class="sxs-lookup"><span data-stu-id="68452-120">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="68452-121">Si noti anche che, come altri modelli di sito, la lingua del sito predefinita non è modificabile dopo la creazione del sito.</span><span class="sxs-lookup"><span data-stu-id="68452-121">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="68452-122">Selezionare **Completato**.</span><span class="sxs-lookup"><span data-stu-id="68452-122">Select **Finished**.</span></span>
 
<span data-ttu-id="68452-123">Dopo aver creato un sito del centro contenuti, questo verrà elencato nella pagina **Siti attivi** nell'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="68452-123">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="68452-124">Assegnare l'accesso ad altri utenti</span><span class="sxs-lookup"><span data-stu-id="68452-124">Give access to additional users</span></span>
 
<span data-ttu-id="68452-125">Dopo aver creato il sito, è possibile concedere ad altri utenti l'accesso al sito tramite il [modello di autorizzazioni del sito di SharePoint](/sharepoint/modern-experience-sharing-permissions)standard.</span><span class="sxs-lookup"><span data-stu-id="68452-125">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="68452-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68452-126">See Also</span></span>
[<span data-ttu-id="68452-127">Creare un classificatore</span><span class="sxs-lookup"><span data-stu-id="68452-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="68452-128">Creare un estrattore</span><span class="sxs-lookup"><span data-stu-id="68452-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="68452-129">Creare un centro contenuti</span><span class="sxs-lookup"><span data-stu-id="68452-129">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="68452-130">Panoramica sull'analisi dei documenti</span><span class="sxs-lookup"><span data-stu-id="68452-130">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="68452-131">Creare un modello di elaborazione moduli</span><span class="sxs-lookup"><span data-stu-id="68452-131">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="68452-132">Applicare un modello</span><span class="sxs-lookup"><span data-stu-id="68452-132">Apply a model</span></span>](apply-a-model.md)