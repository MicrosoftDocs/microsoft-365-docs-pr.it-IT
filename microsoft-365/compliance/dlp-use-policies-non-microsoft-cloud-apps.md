---
title: Usare i criteri di prevenzione della perdita di dati per le app cloud non Microsoft (anteprima)
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
description: Informazioni su come usare i criteri dlp per le app cloud non Microsoft.
ms.openlocfilehash: ca522b5accbd2c08e80b0ce63871179ff64bbcc8
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149155"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="289fe-103">Usare i criteri di prevenzione della perdita dei dati per le app cloud non Microsoft (anteprima)</span><span class="sxs-lookup"><span data-stu-id="289fe-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="289fe-104">I criteri di prevenzione della perdita dei dati (DLP) per le app cloud non Microsoft fanno parte della famiglia Microsoft 365 di funzionalità DLP. usando queste funzionalità, è possibile individuare e proteggere gli elementi sensibili tra Microsoft 365 servizi.</span><span class="sxs-lookup"><span data-stu-id="289fe-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="289fe-105">Per ulteriori informazioni su tutte le offerte DLP di Microsoft, vedere [Informazioni sulla prevenzione della perdita dei dati.](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="289fe-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="289fe-106">Puoi usare i criteri DLP per le app cloud non Microsoft per monitorare e rilevare quando gli elementi sensibili vengono usati e condivisi tramite app cloud non Microsoft.</span><span class="sxs-lookup"><span data-stu-id="289fe-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="289fe-107">L'uso di questi criteri offre la visibilità e il controllo necessari per garantire che siano utilizzati e protetti correttamente e consente di evitare comportamenti rischiosi che potrebbero comprometterli.</span><span class="sxs-lookup"><span data-stu-id="289fe-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="289fe-108">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="289fe-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="289fe-109">Licenze per SKU/abbonamenti</span><span class="sxs-lookup"><span data-stu-id="289fe-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="289fe-110">Prima di iniziare a usare i criteri DLP per le app cloud non Microsoft, confermare la sottoscrizione Microsoft 365 [ed](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) eventuali componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="289fe-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="289fe-111">Per accedere a questa funzionalità e utilizzarla, è necessario disporre di uno di questi abbonamenti o componenti aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="289fe-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="289fe-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="289fe-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="289fe-113">Conformità Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="289fe-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="289fe-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="289fe-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="289fe-115">Preparare l'Cloud App Security locale</span><span class="sxs-lookup"><span data-stu-id="289fe-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="289fe-116">I criteri DLP per le app cloud non Microsoft usano Cloud App Security DLP.</span><span class="sxs-lookup"><span data-stu-id="289fe-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="289fe-117">Per usarlo, è consigliabile preparare l'Cloud App Security locale.</span><span class="sxs-lookup"><span data-stu-id="289fe-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="289fe-118">Per istruzioni, vedi [Impostare azioni di visibilità, protezione e governance istantanee per le tue app.](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)</span><span class="sxs-lookup"><span data-stu-id="289fe-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="289fe-119">Connessione un'app cloud non Microsoft</span><span class="sxs-lookup"><span data-stu-id="289fe-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="289fe-120">Per usare i criteri DLP per una specifica app cloud non Microsoft, l'app deve essere connessa a Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="289fe-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="289fe-121">Per informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="289fe-121">For information, see:</span></span>

- [<span data-ttu-id="289fe-122">Connessione Box</span><span class="sxs-lookup"><span data-stu-id="289fe-122">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="289fe-123">Connessione Dropbox</span><span class="sxs-lookup"><span data-stu-id="289fe-123">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="289fe-124">Connessione G-Suite</span><span class="sxs-lookup"><span data-stu-id="289fe-124">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="289fe-125">Connessione Salesforce</span><span class="sxs-lookup"><span data-stu-id="289fe-125">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="289fe-126">Connessione Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="289fe-126">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="289fe-127">Dopo aver connesso le app cloud a Cloud App Security, è possibile creare Microsoft 365 criteri DLP per loro.</span><span class="sxs-lookup"><span data-stu-id="289fe-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="289fe-128">È anche possibile usare le Microsoft Cloud App Security per creare criteri DLP per le app cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="289fe-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="289fe-129">Tuttavia, è consigliabile usare Microsoft 365 per creare e gestire i criteri DLP per le app cloud Microsoft.</span><span class="sxs-lookup"><span data-stu-id="289fe-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="289fe-130">Creare un criterio DLP in un'app cloud non Microsoft</span><span class="sxs-lookup"><span data-stu-id="289fe-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="289fe-131">Quando si seleziona una posizione per il criterio DLP, attivare la posizione **Microsoft Cloud App Security** locale.</span><span class="sxs-lookup"><span data-stu-id="289fe-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="289fe-132">Per selezionare un'app o un'istanza specifica, seleziona **Scegli istanza.**</span><span class="sxs-lookup"><span data-stu-id="289fe-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="289fe-133">Se non si seleziona un'istanza, il criterio usa tutte le app connesse nel tenant Microsoft Cloud App Security tenant.</span><span class="sxs-lookup"><span data-stu-id="289fe-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![Percorsi per l'applicazione del criterio](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US e Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="289fe-136">Puoi scegliere diverse azioni per ogni app cloud non Microsoft supportata.</span><span class="sxs-lookup"><span data-stu-id="289fe-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="289fe-137">Per ogni app, esistono diverse azioni possibili (dipende dall'API dell'app cloud).</span><span class="sxs-lookup"><span data-stu-id="289fe-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![Creare una regola](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="289fe-139">Quando si crea una regola nel criterio DLP, è possibile selezionare un'azione per le app cloud non Microsoft.</span><span class="sxs-lookup"><span data-stu-id="289fe-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="289fe-140">Per limitare le app di terze parti, seleziona **Limita app di terze parti.**</span><span class="sxs-lookup"><span data-stu-id="289fe-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![Limitare le app di terze parti](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

><span data-ttu-id="289fe-142">[NOTA] I criteri DLP applicati alle app non Microsoft usano Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="289fe-142">[NOTE] DLP policies applied to non-Microsoft apps use Microsoft Cloud App Security.</span></span> <span data-ttu-id="289fe-143">Quando viene creato il criterio DLP per un'app non Microsoft, lo stesso criterio verrà creato automaticamente in Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="289fe-143">When the DLP policy for a non-Microsoft app is created, the same policy will be automatically created in Microsoft Cloud App Security.</span></span>

<span data-ttu-id="289fe-144">Per informazioni sulla creazione e la configurazione dei criteri DLP, vedere [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="289fe-144">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="289fe-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="289fe-145">See Also</span></span>

- [<span data-ttu-id="289fe-146">Creare test e ottimizzare un criterio DLP</span><span class="sxs-lookup"><span data-stu-id="289fe-146">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="289fe-147">Cominciare con il criterio di prevenzione della perdita dei dati predefinito</span><span class="sxs-lookup"><span data-stu-id="289fe-147">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="289fe-148">Creare un criterio di prevenzione della perdita dei dati da un modello</span><span class="sxs-lookup"><span data-stu-id="289fe-148">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)
