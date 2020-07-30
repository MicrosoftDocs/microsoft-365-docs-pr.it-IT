---
title: Introduzione alla prevenzione della perdita di dati degli endpoint di Microsoft 365 (anteprima)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Configurare la prevenzione della perdita di dati degli endpoint di Microsoft 365 per monitorare le attività dei file e implementare azioni di protezione per questi file negli endpoint.
ms.openlocfilehash: 67bd00a83314590d1ca1ab71c32d5a325686dc46
ms.sourcegitcommit: f3a02584c9354a46c082f8f948b34a177adf65bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/29/2020
ms.locfileid: "46514779"
---
# <a name="get-started-with-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="02513-103">Introduzione alla prevenzione della perdita di dati degli endpoint (anteprima)</span><span class="sxs-lookup"><span data-stu-id="02513-103">Get started with Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="02513-104">Microsoft Endpoint Data Loss Prevention (Endpoint DLP) fa parte della famiglia di funzionalità di prevenzione della perdita dei dati (DLP) di Microsoft 365 che è possibile usare per individuare e proteggere gli elementi sensibili nei servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02513-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="02513-105">Per altre informazioni su tutte le offerte DLP di Microsoft, vedere [Panoramica sulla prevenzione della perdita dei dati](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="02513-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="02513-106">Per altre informazioni su Endpoint DLP, vedere [Informazioni sulla prevenzione della perdita di dati degli endpoint (anteprima)](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="02513-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention (preview)](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="02513-107">Microsoft Endpoint DLP consente di monitorare i dispositivi Windows 10 e rilevare l'uso e la condivisione di elementi sensibili.</span><span class="sxs-lookup"><span data-stu-id="02513-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="02513-108">In questo modo si ottengono la visibilità e il controllo necessari per assicurarsi che vengano usati e protetti correttamente e per evitare comportamenti rischiosi che potrebbero comprometterli.</span><span class="sxs-lookup"><span data-stu-id="02513-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="02513-109">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="02513-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="02513-110">Licenze per SKU/abbonamenti</span><span class="sxs-lookup"><span data-stu-id="02513-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="02513-111">Prima di iniziare a usare Endpoint DLP, è necessario confermare l'[abbonamento a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e gli eventuali componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="02513-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="02513-112">Per accedere e usare le funzionalità di Endpoint DLP, è necessario disporre di uno di questi abbonamenti o componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="02513-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="02513-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="02513-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="02513-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="02513-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="02513-115">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="02513-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="02513-116">Microsoft 365 A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="02513-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="02513-117">Microsoft 365 E5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="02513-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="02513-118">Microsoft 365 A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="02513-118">Microsoft 365 A5 information protection and governance</span></span>

### <a name="permissions"></a><span data-ttu-id="02513-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="02513-119">Permissions</span></span>

<span data-ttu-id="02513-120">Per abilitare la gestione dei dispositivi, l'account in uso deve essere membro di uno di questi ruoli:</span><span class="sxs-lookup"><span data-stu-id="02513-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="02513-121">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="02513-121">Global admin</span></span>
- <span data-ttu-id="02513-122">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="02513-122">Security admin</span></span>
- <span data-ttu-id="02513-123">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="02513-123">Compliance admin</span></span>

<span data-ttu-id="02513-124">Se si vuole usare un account personalizzato per vedere le impostazioni di gestione dei dispositivi, deve essere in uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="02513-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="02513-125">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="02513-125">Global admin</span></span>
- <span data-ttu-id="02513-126">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="02513-126">Compliance admin</span></span>
- <span data-ttu-id="02513-127">Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="02513-127">Compliance data admin</span></span>
- <span data-ttu-id="02513-128">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="02513-128">Global reader</span></span>

<span data-ttu-id="02513-129">Se si vuole usare un account personalizzato per accedere alla pagina di onboarding/offboarding, deve essere in uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="02513-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="02513-130">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="02513-130">Global admin</span></span>
- <span data-ttu-id="02513-131">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="02513-131">Compliance admin</span></span>

<span data-ttu-id="02513-132">Se si vuole usare un account personalizzato per attivare o disattivare il monitoraggio dei dispositivi, deve essere in uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="02513-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="02513-133">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="02513-133">Global admin</span></span>
- <span data-ttu-id="02513-134">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="02513-134">Compliance admin</span></span>

<span data-ttu-id="02513-135">I dati provenienti da Endpoint DLP possono essere visualizzati in [Esplora attività](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="02513-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="02513-136">Sono disponibili quattro ruoli che concedono l'autorizzazione per Esplora attività, l'account usato per accedere ai dati deve essere membro di uno di essi.</span><span class="sxs-lookup"><span data-stu-id="02513-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="02513-137">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="02513-137">Global admin</span></span>
- <span data-ttu-id="02513-138">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="02513-138">Compliance admin</span></span>
- <span data-ttu-id="02513-139">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="02513-139">Security admin</span></span>
- <span data-ttu-id="02513-140">Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="02513-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="02513-141">Preparare gli endpoint</span><span class="sxs-lookup"><span data-stu-id="02513-141">Prepare your endpoints</span></span>

<span data-ttu-id="02513-142">Verificare che i dispositivi Windows 10 in cui si prevede di distribuire Endpoint DLP soddisfino questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="02513-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="02513-143">Devono eseguire Windows 10 build 1809 o superiore.</span><span class="sxs-lookup"><span data-stu-id="02513-143">Must be running Windows 10 build 1809 or up.</span></span>
2. <span data-ttu-id="02513-144">Tutti i dispositivi devono essere [aggiunti ad Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) o aggiunto ad Azure AD ibrido.</span><span class="sxs-lookup"><span data-stu-id="02513-144">All devices must be [Azure Active Directory (AAD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>
3. <span data-ttu-id="02513-145">Installare il browser Microsoft Edge Chromium nel dispositivo endpoint per applicare azioni dei criteri per l'attività di caricamento nel cloud.</span><span class="sxs-lookup"><span data-stu-id="02513-145">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the the upload to cloud activity.</span></span> <span data-ttu-id="02513-146">Vedere [Scaricare il nuovo Microsoft Edge basato su Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="02513-146">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="02513-147">Onboarding di dispositivi nella gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="02513-147">Onboarding devices into device management</span></span>

 <span data-ttu-id="02513-148">Per poter monitorare e proteggere gli elementi sensibili in un dispositivo, è necessario abilitare il monitoraggio dei dispositivi ed eseguire l'onboarding degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="02513-148">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="02513-149">Entrambe le azioni vengono eseguite nel portale Conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02513-149">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="02513-150">Quando si vuole eseguire l'onboarding di nuovi dispositivi, si scarica lo script appropriato e lo si distribuisce in questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="02513-150">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="02513-151">Seguire la [procedura di onboarding dei dispositivi](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="02513-151">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="02513-152">Se i dispositivi sono già presenti in [Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/), verranno già visualizzati nell'elenco dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="02513-152">If you already have devices onboarded into [Microsoft Defender Advanced Threat Protection (MDATP)](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="02513-153">Seguire la procedura [Con i dispositivi caricati in MDATP](endpoint-dlp-getting-started.md#with-devices-onboarded-into-mdatp).</span><span class="sxs-lookup"><span data-stu-id="02513-153">Follow the [With devices onboarded into MDATP procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-mdatp).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="02513-154">Onboarding dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="02513-154">Onboarding devices</span></span>

<span data-ttu-id="02513-155">In questo scenario di distribuzione si esegue l'onboarding di dispositivi non ancora caricati e si vogliono soltanto monitorare e proteggere gli elementi sensibili dalla condivisione involontaria nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="02513-155">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="02513-156">Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="02513-156">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="02513-157">Aprire la pagina delle impostazioni del Centro conformità e scegliere **Onboarding di dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="02513-157">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

![abilitare la gestione dei dispositivi](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

> [!NOTE]
> <span data-ttu-id="02513-159">Anche se in genere sono necessari circa 60 secondi perché l'onboarding dei dispositivi sia abilitato, attendere fino a 30 minuti prima di contattare il supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="02513-159">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="02513-160">Scegliere **Gestione dispositivi** per aprire l'elenco **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="02513-160">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="02513-161">L'elenco sarà vuoto finché non si caricano dispositivi.</span><span class="sxs-lookup"><span data-stu-id="02513-161">The list will be empty until you onboard devices.</span></span>
4. <span data-ttu-id="02513-162">Scegliere **Onboarding** per avviare il processo di onboarding.</span><span class="sxs-lookup"><span data-stu-id="02513-162">Choose **Onboarding** to begin the onboarding process.</span></span>
5. <span data-ttu-id="02513-163">Scegliere il modo in cui si vogliono distribuire questi altri dispositivi dall'elenco **Metodo di distribuzione** e quindi **scaricare il pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="02513-163">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

![metodo di distribuzione](../media/endpoint-dlp-getting-started-3-deployment-method.png)
1. <span data-ttu-id="02513-165">Seguire le procedure appropriate in [Strumenti e metodi di onboarding per i dispositivi Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="02513-165">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="02513-166">Questo collegamento porta a una pagina di destinazione in cui è possibile accedere alle procedure di MDATP che corrispondono al pacchetto di distribuzione selezionato nel passaggio 5:</span><span class="sxs-lookup"><span data-stu-id="02513-166">This link take you to a landing page where you can access MDATP procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="02513-167">Onboarding di dispositivi Windows 10 con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="02513-167">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="02513-168">Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="02513-168">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="02513-169">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="02513-169">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="02513-170">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="02513-170">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="02513-171">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.</span><span class="sxs-lookup"><span data-stu-id="02513-171">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="02513-172">Una volta completata l'operazione di onboarding, l'endpoint sarà visibile nell'elenco dei dispositivi e inizierà anche a inviare log di controllo delle attività a Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="02513-172">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="02513-173">Questa esperienza richiede la licenza.</span><span class="sxs-lookup"><span data-stu-id="02513-173">This experience is under license enforcement.</span></span> <span data-ttu-id="02513-174">Se non si ha la licenza necessaria, i dati non saranno visibili o accessibili.</span><span class="sxs-lookup"><span data-stu-id="02513-174">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-mdatp"></a><span data-ttu-id="02513-175">Con i dispositivi caricati in MDATP</span><span class="sxs-lookup"><span data-stu-id="02513-175">With devices onboarded into MDATP</span></span>

<span data-ttu-id="02513-176">In questo scenario, MDATP è già distribuito e ci sono endpoint per cui vengono creati report.</span><span class="sxs-lookup"><span data-stu-id="02513-176">In this scenario, MDATP is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="02513-177">Tutti questi endpoint compariranno nell'elenco dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="02513-177">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="02513-178">È possibile continuare a eseguire l'onboarding di nuovi dispositivi in Endpoint DLP per ampliare la copertura usando la [procedura di onboarding dei dispositivi](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="02513-178">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="02513-179">Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="02513-179">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="02513-180">Aprire la pagina delle impostazioni del Centro conformità e scegliere **Abilita monitoraggio dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="02513-180">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>
3. <span data-ttu-id="02513-181">Scegliere **Gestione dispositivi** per aprire l'elenco **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="02513-181">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="02513-182">Dovrebbe essere visualizzato l'elenco dei dispositivi che già inviano report a MDATP.</span><span class="sxs-lookup"><span data-stu-id="02513-182">You should see the list of devices that are already reporting in to MDATP.</span></span> <span data-ttu-id="02513-183">![gestione dispositivi](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="02513-183">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
4. <span data-ttu-id="02513-184">Scegliere **Onboarding** se è necessario aggiungere altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="02513-184">Choose **Onboarding** if you need to onboard additional devices.</span></span>
5. <span data-ttu-id="02513-185">Scegliere il modo in cui si vogliono distribuire questi altri dispositivi dall'elenco **Metodo di distribuzione** e quindi **Scarica pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="02513-185">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>
6. <span data-ttu-id="02513-186">Seguire le procedure appropriate in [Strumenti e metodi di onboarding per i dispositivi Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="02513-186">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="02513-187">Questo collegamento porta a una pagina di destinazione in cui è possibile accedere alle procedure di MDATP che corrispondono al pacchetto di distribuzione selezionato nel passaggio 5:</span><span class="sxs-lookup"><span data-stu-id="02513-187">This link take you to a landing page where you can access MDATP procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="02513-188">Onboarding di dispositivi Windows 10 con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="02513-188">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="02513-189">Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="02513-189">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="02513-190">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="02513-190">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="02513-191">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="02513-191">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="02513-192">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.</span><span class="sxs-lookup"><span data-stu-id="02513-192">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="02513-193">Una volta completata l'operazione di onboarding, l'endpoint sarà visibile nell'elenco **Dispositivi** e inizierà anche a inviare log di controllo a **Esplora attività**.</span><span class="sxs-lookup"><span data-stu-id="02513-193">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="02513-194">Questa esperienza richiede la licenza.</span><span class="sxs-lookup"><span data-stu-id="02513-194">This experience is under license enforcement.</span></span> <span data-ttu-id="02513-195">Se non si ha la licenza necessaria, i dati non saranno visibili o accessibili.</span><span class="sxs-lookup"><span data-stu-id="02513-195">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="02513-196">Visualizzazione dei dati di Endpoint DLP in Esplora attività</span><span class="sxs-lookup"><span data-stu-id="02513-196">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="02513-197">Aprire la pagina [Classificazione dei dati](https://compliance.microsoft.com/dataclassification?viewid=overview) per il dominio nel Centro conformità Microsoft 365 e scegliere Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="02513-197">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>
2. <span data-ttu-id="02513-198">Vedere le procedure in [Introduzione a Esplora attività](data-classification-activity-explorer.md) per accedere a tutti i dati relativi ai dispositivi endpoint e filtrarli.</span><span class="sxs-lookup"><span data-stu-id="02513-198">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

![filtro di Esplora attività per i dispositivi endpoint](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a><span data-ttu-id="02513-200">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="02513-200">Next steps</span></span>
<span data-ttu-id="02513-201">Ora che si è eseguito l'onboarding dei dispositivi e che è possibile visualizzare i dati sulle attività in Esplora attività, è possibile procedere con il passaggio successivo, in cui si creano criteri di prevenzione della perdita dei dati per proteggere gli elementi sensibili.</span><span class="sxs-lookup"><span data-stu-id="02513-201">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

1) [<span data-ttu-id="02513-202">Uso della prevenzione della perdita di dati degli endpoint (anteprima)</span><span class="sxs-lookup"><span data-stu-id="02513-202">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="02513-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02513-203">See also</span></span>

- [<span data-ttu-id="02513-204">Informazioni sulla prevenzione della perdita di dati degli endpoint (anteprima)</span><span class="sxs-lookup"><span data-stu-id="02513-204">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="02513-205">Uso della prevenzione della perdita di dati degli endpoint (anteprima)</span><span class="sxs-lookup"><span data-stu-id="02513-205">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="02513-206">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="02513-206">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="02513-207">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="02513-207">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="02513-208">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="02513-208">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="02513-209">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="02513-209">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="02513-210">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="02513-210">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="02513-211">Abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="02513-211">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="02513-212">Dispositivi aggiunti ad Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="02513-212">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="02513-213">Scaricare il nuovo Microsoft Edge basato su Chromium</span><span class="sxs-lookup"><span data-stu-id="02513-213">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)