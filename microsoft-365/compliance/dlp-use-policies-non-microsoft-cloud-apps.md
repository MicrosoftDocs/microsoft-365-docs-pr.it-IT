---
title: Utilizzare i criteri di prevenzione della perdita dei dati per le app Cloud non Microsoft (anteprima)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come utilizzare i criteri DLP per le app Cloud non Microsoft.
ms.openlocfilehash: dd5a7a4bc0725d0785daec6b7635047cd91f20a2
ms.sourcegitcommit: 39af527404cb06e05c5aa4550dbec39aec133016
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2020
ms.locfileid: "48422758"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="4ff80-103">Utilizzare i criteri di prevenzione della perdita dei dati per le app Cloud non Microsoft (anteprima)</span><span class="sxs-lookup"><span data-stu-id="4ff80-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="4ff80-104">I criteri di prevenzione della perdita di dati (DLP, Data Loss Prevention) per le app Cloud non Microsoft fanno parte della famiglia di caratteristiche Microsoft 365 DLP. utilizzando queste funzionalità, è possibile individuare e proteggere gli elementi sensibili nei servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ff80-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="4ff80-105">Per ulteriori informazioni su tutte le offerte DLP Microsoft, vedere [Overview of Data Loss Prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="4ff80-105">For more information about all Microsoft DLP offerings, see [Overview of data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="4ff80-106">È possibile utilizzare i criteri DLP per le app Cloud non Microsoft per monitorare e rilevare quando gli elementi sensibili vengono utilizzati e condivisi tramite le app Cloud non Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ff80-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="4ff80-107">L'utilizzo di questi criteri garantisce la visibilità e il controllo necessari per garantire la corretta utilizzazione e protezione e consente di evitare comportamenti rischiosi che potrebbero comprometterli.</span><span class="sxs-lookup"><span data-stu-id="4ff80-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4ff80-108">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="4ff80-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="4ff80-109">Licenze per SKU/abbonamenti</span><span class="sxs-lookup"><span data-stu-id="4ff80-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="4ff80-110">Prima di iniziare a utilizzare i criteri DLP per le app Cloud non Microsoft, confermare la [sottoscrizione microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e gli eventuali componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="4ff80-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="4ff80-111">Per accedere e utilizzare questa funzionalità, è necessario disporre di una delle sottoscrizioni o dei componenti aggiuntivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ff80-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="4ff80-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4ff80-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="4ff80-113">Conformità Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4ff80-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="4ff80-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="4ff80-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="4ff80-115">Preparare l'ambiente di protezione delle app Cloud</span><span class="sxs-lookup"><span data-stu-id="4ff80-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="4ff80-116">I criteri DLP per le app Cloud non Microsoft utilizzano le funzionalità di protezione DLP di cloud app.</span><span class="sxs-lookup"><span data-stu-id="4ff80-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="4ff80-117">Per utilizzarlo, è necessario preparare l'ambiente di protezione delle app cloud.</span><span class="sxs-lookup"><span data-stu-id="4ff80-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="4ff80-118">Per istruzioni, vedere [set isntant Visibility, Protection, and Governance actions for your Apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span><span class="sxs-lookup"><span data-stu-id="4ff80-118">For instructions, see [Set isntant visibility, protection, and governance actions for your apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="4ff80-119">Connettere un'app Cloud non Microsoft</span><span class="sxs-lookup"><span data-stu-id="4ff80-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="4ff80-120">Per utilizzare i criteri DLP per un'app Cloud non Microsoft specifica, è necessario che l'app sia connessa a cloud app Security.</span><span class="sxs-lookup"><span data-stu-id="4ff80-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="4ff80-121">Per informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="4ff80-121">For information, see:</span></span>

- [<span data-ttu-id="4ff80-122">Casella Connetti</span><span class="sxs-lookup"><span data-stu-id="4ff80-122">Connect Box</span></span>](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="4ff80-123">Connettere Dropbox</span><span class="sxs-lookup"><span data-stu-id="4ff80-123">Connect Dropbox</span></span>](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="4ff80-124">Connettere G-Suite</span><span class="sxs-lookup"><span data-stu-id="4ff80-124">Connect G-Suite</span></span>](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="4ff80-125">Connettere Salesforce</span><span class="sxs-lookup"><span data-stu-id="4ff80-125">Connect Salesforce</span></span>](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="4ff80-126">Connettere Cisco WebEx</span><span class="sxs-lookup"><span data-stu-id="4ff80-126">Connect Cisco Webex</span></span>](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="4ff80-127">Dopo aver collegato le app Cloud alla sicurezza delle app Cloud, è possibile creare i criteri di Microsoft 365 DLP.</span><span class="sxs-lookup"><span data-stu-id="4ff80-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="4ff80-128">È anche possibile usare Microsoft cloud app Security per creare criteri DLP per le app cloud di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ff80-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="4ff80-129">Tuttavia, si consiglia di utilizzare Microsoft 365 per creare e gestire i criteri DLP per le app cloud di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ff80-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="4ff80-130">Creare un criterio DLP in un'app Cloud non Microsoft</span><span class="sxs-lookup"><span data-stu-id="4ff80-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="4ff80-131">Quando si seleziona un percorso per il criterio DLP, accendere il percorso di **sicurezza di Microsoft cloud app** .</span><span class="sxs-lookup"><span data-stu-id="4ff80-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="4ff80-132">Per selezionare un'applicazione o un'istanza specifica, selezionare **Scegli istanza**.</span><span class="sxs-lookup"><span data-stu-id="4ff80-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="4ff80-133">Se non si seleziona un'istanza, il criterio utilizza tutte le app connesse nel tenant di sicurezza di Microsoft cloud app.</span><span class="sxs-lookup"><span data-stu-id="4ff80-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Posizioni in cui applicare il criterio](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Casella-Stati Uniti e Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="4ff80-136">È possibile scegliere varie azioni per ogni app Cloud non Microsoft supportata.</span><span class="sxs-lookup"><span data-stu-id="4ff80-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="4ff80-137">Per ogni app, esistono diverse azioni possibili (dipende dall'API delle app Cloud).</span><span class="sxs-lookup"><span data-stu-id="4ff80-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Crea regola](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="4ff80-139">Quando si crea una regola nei criteri DLP, è possibile selezionare un'azione per le app Cloud non Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4ff80-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="4ff80-140">Per limitare le app di terze parti, seleziona **Impedisci app**di terze parti.</span><span class="sxs-lookup"><span data-stu-id="4ff80-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Limitare le app di terze parti](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="4ff80-142">Per informazioni sulla creazione e sulla configurazione dei criteri DLP, vedere [create test and Tune a DLP Policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="4ff80-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="4ff80-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ff80-143">See Also</span></span>

- [<span data-ttu-id="4ff80-144">Creare test e ottimizzare un criterio DLP</span><span class="sxs-lookup"><span data-stu-id="4ff80-144">Create test and tune a DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="4ff80-145">Cominciare con il criterio di prevenzione della perdita dei dati predefinito</span><span class="sxs-lookup"><span data-stu-id="4ff80-145">Get started with the default DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="4ff80-146">Creare un criterio di prevenzione della perdita dei dati da un modello</span><span class="sxs-lookup"><span data-stu-id="4ff80-146">Create a DLP policy from a template</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
