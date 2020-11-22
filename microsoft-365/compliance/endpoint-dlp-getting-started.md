---
title: Introduzione alla prevenzione della perdita di dati degli endpoint di Microsoft 365
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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Configurare la prevenzione della perdita di dati degli endpoint di Microsoft 365 per monitorare le attività dei file e implementare azioni di protezione per questi file negli endpoint.
ms.openlocfilehash: 8211ffbe3a84c0ee9fb4cb4c22d4dcea7f906a78
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371602"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="e6483-103">Introduzione alla prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="e6483-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="e6483-104">La prevenzione della perdita di dati degli endpoint di Microsoft 365 (Endpoint DLP) fa parte della famiglia di funzionalità di prevenzione della perdita dei dati (DLP) di Microsoft 365 che è possibile usare per individuare e proteggere gli elementi sensibili nei servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6483-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="e6483-105">Per altre informazioni su tutte le offerte DLP Microsoft, vedere [Panoramica della prevenzione della perdita dei dati](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e6483-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="e6483-106">Per altre informazioni sulla perdita dei dati degli endpoint, vedere [Informazioni sulla prevenzione della perdita di dati degli endpoint ](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="e6483-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="e6483-p102">La prevenzione della perdita di dati degli endpoint di Microsoft consente di monitorare i dispositivi Windows 10 e rilevare quando vengono usati e condivisi elementi sensibili. Questo fornisce la visibilità e il controllo necessari per garantire che vengano usati e protetti in modo appropriato e per prevenire comportamenti rischiosi che potrebbero comprometterli.</span><span class="sxs-lookup"><span data-stu-id="e6483-p102">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared. This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e6483-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e6483-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="e6483-110">Licenze per SKU/sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="e6483-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="e6483-p103">Prima di iniziare a usare Endpoint DLP, è necessario confermare [la sottoscrizione a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e a qualsiasi componente aggiuntivo. Per accedere a e usare la funzionalità Endpoint DLP, è necessario disporre di una delle seguenti sottoscrizioni o dei seguenti componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e6483-p103">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons. To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="e6483-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e6483-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="e6483-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="e6483-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="e6483-115">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="e6483-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="e6483-116">Microsoft 365 A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="e6483-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="e6483-117">Microsoft 365 E5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="e6483-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="e6483-118">Microsoft 365 A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="e6483-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="e6483-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e6483-119">Permissions</span></span>

<span data-ttu-id="e6483-120">Per abilitare la gestione dei dispositivi, l'account in uso deve essere membro di uno di questi ruoli:</span><span class="sxs-lookup"><span data-stu-id="e6483-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="e6483-121">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="e6483-121">Global admin</span></span>
- <span data-ttu-id="e6483-122">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="e6483-122">Security admin</span></span>
- <span data-ttu-id="e6483-123">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="e6483-123">Compliance admin</span></span>

<span data-ttu-id="e6483-124">Se si vuole usare un account personalizzato per vedere le impostazioni di gestione dei dispositivi, deve essere in uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6483-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="e6483-125">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="e6483-125">Global admin</span></span>
- <span data-ttu-id="e6483-126">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="e6483-126">Compliance admin</span></span>
- <span data-ttu-id="e6483-127">Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="e6483-127">Compliance data admin</span></span>
- <span data-ttu-id="e6483-128">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="e6483-128">Global reader</span></span>

<span data-ttu-id="e6483-129">Se si vuole usare un account personalizzato per accedere alla pagina di onboarding/offboarding, deve essere in uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6483-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="e6483-130">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="e6483-130">Global admin</span></span>
- <span data-ttu-id="e6483-131">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="e6483-131">Compliance admin</span></span>

<span data-ttu-id="e6483-132">Se si vuole usare un account personalizzato per attivare o disattivare il monitoraggio dei dispositivi, deve essere in uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6483-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="e6483-133">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="e6483-133">Global admin</span></span>
- <span data-ttu-id="e6483-134">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="e6483-134">Compliance admin</span></span>

<span data-ttu-id="e6483-p104">I dati da Endpoint DLP possono essere visualizzati in [Esplora attività](data-classification-activity-explorer.md). Sono disponibili quattro ruoli che concedono l'autorizzazione per Esplora attività e l'account usato per accedere ai dati deve essere membro di uno di essi.</span><span class="sxs-lookup"><span data-stu-id="e6483-p104">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md). There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="e6483-137">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="e6483-137">Global admin</span></span>
- <span data-ttu-id="e6483-138">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="e6483-138">Compliance admin</span></span>
- <span data-ttu-id="e6483-139">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="e6483-139">Security admin</span></span>
- <span data-ttu-id="e6483-140">Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="e6483-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="e6483-141">Preparare gli endpoint</span><span class="sxs-lookup"><span data-stu-id="e6483-141">Prepare your endpoints</span></span>

<span data-ttu-id="e6483-142">Verificare che i dispositivi Windows 10 in cui si prevede di distribuire Endpoint DLP soddisfino questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="e6483-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="e6483-143">Devono eseguire Windows 10 x 64, build 1809 o successiva.</span><span class="sxs-lookup"><span data-stu-id="e6483-143">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="e6483-p105">La versione del client antimalware è 4.18.2009.7 o più recente. Verificare la versione corrente aprendo l'app Sicurezza di Windows, selezionare l'icona Impostazioni, quindi Informazioni. Il numero versione compare sotto Versione client antimalware. Eseguira l'aggiornamento all'ultima versione del client antimalware installando Windows Update KB4052623. Not: nessun componente di Sicurezza di Windows deve essere attivo, è possibile eseguire Endpoint DLP a prescindere dallo stato di Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="e6483-p105">Antimalware Client Version is 4.18.2009.7 or newer. Check your current version by opening Windows Security app, select the Settings icon, and then select About. The version number is listed under Antimalware Client Version. Update to the latest Antimalware Client Version by installing Windows Update KB4052623. Note: None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status.</span></span>

3. <span data-ttu-id="e6483-p106">I seguenti aggiornamenti di Windows sono installati. Nota: questi aggiornamenti non costituiscono un prerequisito per eseguire l'onboarding di un dispositivo a Endpoint DLP, ma contengono correzioni per errori importanti, pertanto devono essere installati prima di usare il prodotto.</span><span class="sxs-lookup"><span data-stu-id="e6483-p106">The following Windows Updates are installed. Note: These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="e6483-151">Per Windows 10 1809 - KB4559003, KB4577069, KB4580390</span><span class="sxs-lookup"><span data-stu-id="e6483-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="e6483-152">Per Windows 10 1903 o 1909 - KB4559004, KB4577062, KB4580386</span><span class="sxs-lookup"><span data-stu-id="e6483-152">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="e6483-153">Per Windows 10 2004 - KB4568831, KB4577063</span><span class="sxs-lookup"><span data-stu-id="e6483-153">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="e6483-154">Per i dispositivi che eseguono Office 2016 (e non qualsiasi altra versione di Office) - KB4577063</span><span class="sxs-lookup"><span data-stu-id="e6483-154">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="e6483-155">Tutti i dispositivi devono essere [aggiunti ad Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) o aggiunti ad Azure AD ibrido.</span><span class="sxs-lookup"><span data-stu-id="e6483-155">All devices must be [Azure Active Directory (Azure AD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>

5. <span data-ttu-id="e6483-p107">Installare il browser Microsoft Chromium Edge sul dispositivo endpoint per applicare le azioni dei criteri per l'attività di caricamento nel cloud. Vedere [Scaricare il nuovo Microsoft Edge basato su Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="e6483-p107">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity. See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="e6483-p108">Se si è in un Canale Enterprise mensile di Microsoft 365 Apps, versioni 2004-2008, è presente un problema noto relativo alla classificazione dei contenuti di Office da parte di Endpoint DLP ed è necessaria la versione 2009 o successiva. Vedere [Aggiornare la cronologia per Microsoft 365 Apps (per data)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) per le versioni correnti. Per ulteriori informazioni in merito a questo problema, vedere la sezione della famiglia di prodotti Office di [Note sulla versione per i rilasci del canale corrente nel 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).</span><span class="sxs-lookup"><span data-stu-id="e6483-p108">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later. See [Update history for Microsoft 365 Apps (listed by date)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date) for current versions. To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](https://docs.microsoft.com/officeupdates/current-channel#version-2010-october-27).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="e6483-161">Onboarding di dispositivi nella gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="e6483-161">Onboarding devices into device management</span></span>

<span data-ttu-id="e6483-p109">Per poter monitorare e proteggere gli elementi riservati in un dispositivo, è necessario abilitare il monitoraggio dei dispositivi ed eseguire l'onboarding degli endpoint. Entrambe queste azioni vengono eseguite nel portale per la conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6483-p109">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device. Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="e6483-p110">Quando si desidera eseguire l'onboarding di nuovi dispositivi, si scarica lo script appropriato e lo si distribuisce in questi dispositivi. Seguire la [Procedura di onboarding dei dispositivi](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="e6483-p110">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices. Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="e6483-p111">Se si dispone già di dispositivi per cui è stato eseguito l'onboarding in [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/), compariranno già nell'elenco dei dispositivi gestiti. Seguire la [Procedura con i dispositivi per cui è stato eseguito l'onboarding in Microsoft ATP](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide&source=docs#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span><span class="sxs-lookup"><span data-stu-id="e6483-p111">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list. Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide&source=docs#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="e6483-168">Onboarding dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="e6483-168">Onboarding devices</span></span>

<span data-ttu-id="e6483-169">In questo scenario di distribuzione si esegue l'onboarding di dispositivi non ancora caricati e si vogliono soltanto monitorare e proteggere gli elementi sensibili dalla condivisione involontaria nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e6483-169">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="e6483-170">Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e6483-170">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="e6483-171">Aprire la pagina delle impostazioni del Centro conformità e scegliere **Onboarding di dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="e6483-171">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6483-172">![abilitare la gestione dei dispositivi](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="e6483-172">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="e6483-173">Anche se in genere sono necessari circa 60 secondi perché l'onboarding dei dispositivi sia abilitato, attendere fino a 30 minuti prima di contattare il supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e6483-173">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="e6483-p112">Scegliere **Gestione dispositivi** per aprire l'elenco dei **Dispositivi**. L'elenco sarà vuoto fino all'onboarding dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e6483-p112">Choose **Device management** to open the **Devices** list. The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="e6483-176">Scegliere **Onboarding** per avviare il processo di onboarding.</span><span class="sxs-lookup"><span data-stu-id="e6483-176">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="e6483-177">Scegliere il modo in cui si vogliono distribuire questi altri dispositivi dall'elenco **Metodo di distribuzione** e quindi **scaricare il pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="e6483-177">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6483-178">![metodo di distribuzione](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="e6483-178">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="e6483-p113">Seguire le procedure appropriate in [Strumenti per l'onboarding e metodi per i computer Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Questo collegamento porta alla pagina di destinazione in cui è possibile accedere alle procedure di Microsoft Defender ATP che corrispondono al pacchetto di distribuzione selezionato al passaggio 5:</span><span class="sxs-lookup"><span data-stu-id="e6483-p113">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="e6483-181">Onboarding di dispositivi Windows 10 con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="e6483-181">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="e6483-182">Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e6483-182">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="e6483-183">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="e6483-183">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="e6483-184">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="e6483-184">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="e6483-185">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.</span><span class="sxs-lookup"><span data-stu-id="e6483-185">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="e6483-186">Una volta completata l'operazione di onboarding, l'endpoint sarà visibile nell'elenco dei dispositivi e inizierà anche a inviare log audit delle attività a Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="e6483-186">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="e6483-p114">Questa esperienza richiede l'applicazione di una licenza. Senza la licenza richiesta, i dati non saranno visibili o accessibili.</span><span class="sxs-lookup"><span data-stu-id="e6483-p114">This experience is under license enforcement. Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="e6483-189">Con dispositivi già presenti in Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="e6483-189">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="e6483-p115">In questo scenario, Microsoft Defender ATP è già stato distribuito e sono presenti endpoint che inviano report a esso. Tutti questi endpoint compariranno nell'elenco dei dispositivi gestiti. È possibile continuare a eseguire l'onboarding di nuovi dispositivi in Endpoint DLP per espandere la copertura tramite la [Procedura di onboarding dei dispositivi](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="e6483-p115">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in. All these endpoints will appear in the managed devices list. You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="e6483-193">Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e6483-193">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="e6483-194">Aprire la pagina delle impostazioni del Centro conformità e scegliere **Abilita monitoraggio dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="e6483-194">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="e6483-p116">Scegliere **Gestione dispositivi** per aprire l'elenco dei **Dispositivi**. Dovrebbe essere visualizzato l'elenco dei dispositivi che inviano già report a Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="e6483-p116">Choose **Device management** to open the **Devices** list. You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6483-197">![gestione dispositivi](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="e6483-197">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="e6483-198">Scegliere **Onboarding** se è necessario aggiungere altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="e6483-198">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="e6483-199">Scegliere il modo in cui si vogliono distribuire questi altri dispositivi dall'elenco **Metodo di distribuzione** e quindi **Scarica pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="e6483-199">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="e6483-p117">Seguire le procedure appropriate in [Strumenti per l'onboarding e metodi per i computer Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Questo collegamento porta alla pagina di destinazione in cui è possibile accedere alle procedure di Microsoft Defender ATP che corrispondono al pacchetto di distribuzione selezionato al passaggio 5:</span><span class="sxs-lookup"><span data-stu-id="e6483-p117">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="e6483-202">Onboarding di dispositivi Windows 10 con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="e6483-202">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="e6483-203">Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e6483-203">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="e6483-204">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="e6483-204">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="e6483-205">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="e6483-205">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="e6483-206">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.</span><span class="sxs-lookup"><span data-stu-id="e6483-206">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="e6483-207">Una volta completata l'operazione di onboarding, l'endpoint sarà visibile nell'elenco **Dispositivi** e inizierà anche a inviare log di controllo a **Esplora attività**.</span><span class="sxs-lookup"><span data-stu-id="e6483-207">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="e6483-p118">Questa esperienza richiede l'applicazione di una licenza. Senza la licenza richiesta, i dati non saranno visibili o accessibili.</span><span class="sxs-lookup"><span data-stu-id="e6483-p118">This experience is under license enforcement. Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="e6483-210">Visualizzazione degli avvisi di Endpoint DLP nel dashboard di gestione degli avvisi DLP</span><span class="sxs-lookup"><span data-stu-id="e6483-210">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="e6483-211">Aprire la pagina Prevenzione della perdita dei dati nel centro conformità Microsoft 365 e scegliere Avvisi.</span><span class="sxs-lookup"><span data-stu-id="e6483-211">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="e6483-212">Fare riferimento alle procedure in [Come configurare e visualizzare gli avvisi per i criteri di prevenzione della perdita dei dati](dlp-configure-view-alerts-policies.md) per visualizzare gli avvisi per i criteri di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="e6483-212">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="e6483-213">Visualizzazione dei dati di Endpoint DLP in Esplora attività</span><span class="sxs-lookup"><span data-stu-id="e6483-213">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="e6483-214">Aprire la pagina [Classificazione dei dati](https://compliance.microsoft.com/dataclassification?viewid=overview) per il dominio nel Centro conformità Microsoft 365 e scegliere Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="e6483-214">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="e6483-215">Vedere le procedure in [Introduzione a Esplora attività](data-classification-activity-explorer.md) per accedere a tutti i dati relativi ai dispositivi endpoint e filtrarli.</span><span class="sxs-lookup"><span data-stu-id="e6483-215">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6483-216">![filtro di Esplora attività per i dispositivi endpoint](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="e6483-216">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="e6483-217">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e6483-217">Next steps</span></span>
<span data-ttu-id="e6483-218">Ora che si è eseguito l'onboarding dei dispositivi e che è possibile visualizzare i dati sulle attività in Esplora attività, è possibile procedere con il passaggio successivo, in cui si creano criteri di prevenzione della perdita dei dati per proteggere gli elementi sensibili.</span><span class="sxs-lookup"><span data-stu-id="e6483-218">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="e6483-219">Uso della prevenzione della perdita di dati degli endpoint (anteprima)</span><span class="sxs-lookup"><span data-stu-id="e6483-219">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="e6483-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6483-220">See also</span></span>

- [<span data-ttu-id="e6483-221">Informazioni sulla prevenzione della perdita di dati degli endpoint (anteprima)</span><span class="sxs-lookup"><span data-stu-id="e6483-221">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="e6483-222">Uso della prevenzione della perdita di dati degli endpoint (anteprima)</span><span class="sxs-lookup"><span data-stu-id="e6483-222">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="e6483-223">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="e6483-223">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="e6483-224">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="e6483-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="e6483-225">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="e6483-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="e6483-226">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="e6483-226">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="e6483-227">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="e6483-227">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="e6483-228">Abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e6483-228">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="e6483-229">Dispositivi aggiunti ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="e6483-229">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="e6483-230">Scaricare il nuovo Microsoft Edge basato su Chromium</span><span class="sxs-lookup"><span data-stu-id="e6483-230">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
