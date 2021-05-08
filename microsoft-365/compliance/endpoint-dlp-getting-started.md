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
ms.openlocfilehash: 118c2f3f87df5ac9930bebd1338157d323b1e5e1
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259500"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="ac9f0-103">Introduzione alla prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="ac9f0-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="ac9f0-104">Microsoft Endpoint Data Loss Prevention (Endpoint DLP) fa parte della famiglia di funzionalità di prevenzione della perdita dei dati (DLP) di Microsoft 365 che è possibile usare per individuare e proteggere gli elementi sensibili nei servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="ac9f0-105">Per altre informazioni su tutte le offerte DLP di Microsoft, vedere [Panoramica sulla prevenzione della perdita dei dati](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="ac9f0-105">For more information about all of Microsoft’s DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span> <span data-ttu-id="ac9f0-106">Per altre informazioni sulla perdita dei dati degli endpoint, vedere [Informazioni sulla prevenzione della perdita di dati degli endpoint ](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="ac9f0-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="ac9f0-107">Microsoft Endpoint DLP consente di monitorare i dispositivi Windows 10 e rilevare l'uso e la condivisione di elementi sensibili.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="ac9f0-108">In questo modo si ottengono la visibilità e il controllo necessari per assicurarsi che vengano usati e protetti correttamente e per evitare comportamenti rischiosi che potrebbero comprometterli.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ac9f0-109">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="ac9f0-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="ac9f0-110">Licenze per SKU/abbonamenti</span><span class="sxs-lookup"><span data-stu-id="ac9f0-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="ac9f0-111">Prima di iniziare a usare Endpoint DLP, è necessario confermare l'[abbonamento a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e gli eventuali componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="ac9f0-112">Per accedere e usare le funzionalità di Endpoint DLP, è necessario disporre di uno di questi abbonamenti o componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="ac9f0-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ac9f0-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="ac9f0-114">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="ac9f0-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="ac9f0-115">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="ac9f0-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="ac9f0-116">Microsoft 365 A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="ac9f0-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="ac9f0-117">Microsoft 365 E5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="ac9f0-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="ac9f0-118">Microsoft 365 A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="ac9f0-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="ac9f0-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ac9f0-119">Permissions</span></span>

<span data-ttu-id="ac9f0-120">Per abilitare la gestione dei dispositivi, l'account in uso deve essere membro di uno di questi ruoli:</span><span class="sxs-lookup"><span data-stu-id="ac9f0-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="ac9f0-121">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="ac9f0-121">Global admin</span></span>
- <span data-ttu-id="ac9f0-122">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="ac9f0-122">Security admin</span></span>
- <span data-ttu-id="ac9f0-123">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="ac9f0-123">Compliance admin</span></span>

<span data-ttu-id="ac9f0-124">Se si vuole usare un account personalizzato per vedere le impostazioni di gestione dei dispositivi, deve essere in uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac9f0-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="ac9f0-125">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="ac9f0-125">Global admin</span></span>
- <span data-ttu-id="ac9f0-126">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="ac9f0-126">Compliance admin</span></span>
- <span data-ttu-id="ac9f0-127">Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="ac9f0-127">Compliance data admin</span></span>
- <span data-ttu-id="ac9f0-128">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="ac9f0-128">Global reader</span></span>

<span data-ttu-id="ac9f0-129">Se si vuole usare un account personalizzato per accedere alla pagina di onboarding/offboarding, deve essere in uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac9f0-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="ac9f0-130">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="ac9f0-130">Global admin</span></span>
- <span data-ttu-id="ac9f0-131">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="ac9f0-131">Compliance admin</span></span>

<span data-ttu-id="ac9f0-132">Se si vuole usare un account personalizzato per attivare o disattivare il monitoraggio dei dispositivi, deve essere in uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac9f0-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="ac9f0-133">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="ac9f0-133">Global admin</span></span>
- <span data-ttu-id="ac9f0-134">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="ac9f0-134">Compliance admin</span></span>

<span data-ttu-id="ac9f0-135">I dati provenienti da Endpoint DLP possono essere visualizzati in [Esplora attività](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="ac9f0-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="ac9f0-136">Sono disponibili quattro ruoli che concedono l'autorizzazione per Esplora attività, l'account usato per accedere ai dati deve essere membro di uno di essi.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="ac9f0-137">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="ac9f0-137">Global admin</span></span>
- <span data-ttu-id="ac9f0-138">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="ac9f0-138">Compliance admin</span></span>
- <span data-ttu-id="ac9f0-139">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="ac9f0-139">Security admin</span></span>
- <span data-ttu-id="ac9f0-140">Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="ac9f0-140">Compliance data admin</span></span>
- <span data-ttu-id="ac9f0-141">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="ac9f0-141">Global reader</span></span>
- <span data-ttu-id="ac9f0-142">Amministratore che legge i dati di sicurezza</span><span class="sxs-lookup"><span data-stu-id="ac9f0-142">Security reader</span></span>
- <span data-ttu-id="ac9f0-143">Amministratore che legge i report</span><span class="sxs-lookup"><span data-stu-id="ac9f0-143">Reports reader</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="ac9f0-144">Preparare gli endpoint</span><span class="sxs-lookup"><span data-stu-id="ac9f0-144">Prepare your endpoints</span></span>

<span data-ttu-id="ac9f0-145">Verificare che i dispositivi Windows 10 in cui si prevede di distribuire Endpoint DLP soddisfino questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-145">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="ac9f0-146">Devono eseguire Windows 10 x 64, build 1809 o successiva.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-146">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="ac9f0-147">La versione del client antimalware deve essere 4.18.2009.7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-147">Antimalware Client Version is 4.18.2009.7 or newer.</span></span> <span data-ttu-id="ac9f0-148">Controllare la versione corrente aprendo l'app Sicurezza di Windows e facendo clic sull'icona impostazioni e quindi su Informazioni.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-148">Check your current version by opening Windows Security app, select the Settings icon, and then select About.</span></span> <span data-ttu-id="ac9f0-149">Il numero di versione è elencato in Versione client antimalware.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-149">The version number is listed under Antimalware Client Version.</span></span> <span data-ttu-id="ac9f0-150">Eseguire l'aggiornamento all'ultima versione del client antimalware installando l'aggiornamento di Windows KB4052623.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-150">Update to the latest Antimalware Client Version by installing Windows Update KB4052623.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="ac9f0-151">Nessun componente di Sicurezza di Windows deve essere attivo ed è possibile eseguire Endpoint DLP indipendentemente dallo stato di Sicurezza di Windows, ma il [Controllo in tempo reale della protezione e del comportamento](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) deve essere abilitato. </span><span class="sxs-lookup"><span data-stu-id="ac9f0-151">None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status, but the [Real-time protection and Behavior monitor](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) must be enabled.</span></span>
 
3. <span data-ttu-id="ac9f0-152">Devono essere installati gli aggiornamenti seguenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-152">The following Windows Updates are installed.</span></span> 
 
   > [!NOTE]
   > <span data-ttu-id="ac9f0-153">Questi aggiornamenti non sono prerequisiti per l'onboarding di un dispositivo in Endpoint DLP, ma contengono correzioni per problemi importanti, pertanto vanno installati prima di usare il prodotto.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-153">These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="ac9f0-154">Per Windows 10 1809 - KB4559003, KB4577069, KB4580390</span><span class="sxs-lookup"><span data-stu-id="ac9f0-154">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="ac9f0-155">Per Windows 10 1903 o 1909 - KB4559004, KB4577062, KB4580386</span><span class="sxs-lookup"><span data-stu-id="ac9f0-155">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="ac9f0-156">Per Windows 10 2004 - KB4568831, KB4577063</span><span class="sxs-lookup"><span data-stu-id="ac9f0-156">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="ac9f0-157">Per i dispositivi che eseguono Office 2016 (e non qualsiasi altra versione di Office) - KB4577063</span><span class="sxs-lookup"><span data-stu-id="ac9f0-157">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="ac9f0-158">Tutti i dispositivi devono essere [aggiunti ad Azure Active Directory (Azure AD)](/azure/active-directory/devices/concept-azure-ad-join), aggiunti ad Active Directory, aggiunti a Azure AD ibrido o registrati a AAD.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-158">All devices must be [Azure Active Directory (Azure AD) joined](/azure/active-directory/devices/concept-azure-ad-join), AD joined, Hybrid Azure AD joined, or AAD registered.</span></span>

5. <span data-ttu-id="ac9f0-159">Installare il browser Microsoft Edge Chromium nel dispositivo endpoint per applicare azioni dei criteri per l'attività di caricamento nel cloud.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-159">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="ac9f0-160">Vedere [Scaricare il nuovo Microsoft Edge basato su Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="ac9f0-160">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="ac9f0-161">Se si usa il Canale Enterprise mensile di Microsoft 365 Apps versioni 2004-2008, esiste un problema noto con Endpoint DLP che classifica il contenuto di Office ed è necessario eseguire l'aggiornamento alla versione 2009 o successiva.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-161">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later.</span></span> <span data-ttu-id="ac9f0-162">Vedere [Cronologia degli aggiornamenti per Microsoft 365 Apps (elencati in ordine cronologico)](/officeupdates/update-history-microsoft365-apps-by-date) per le versioni correnti.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-162">See [Update history for Microsoft 365 Apps (listed by date)](/officeupdates/update-history-microsoft365-apps-by-date) for current versions.</span></span> <span data-ttu-id="ac9f0-163">Per altre informazioni su questo problema, vedere la sezione relativa alle famiglia di prodotti di Office di [Note sulla versione del Canale corrente nel 2020](/officeupdates/current-channel#version-2010-october-27).</span><span class="sxs-lookup"><span data-stu-id="ac9f0-163">To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](/officeupdates/current-channel#version-2010-october-27).</span></span>

7. <span data-ttu-id="ac9f0-164">Se sono presenti endpoint che usano un proxy per la connessione a Internet, seguire le procedure in [Configurare il proxy del dispositivo e le impostazioni di connessione Internet per la Prevenzione della perdita dei dati degli endpoint](endpoint-dlp-configure-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="ac9f0-164">If you have endpoints that use a device proxy to connect to the internet, follow the procedures in [Configure device proxy and internet connection settings for Endpoint DLP](endpoint-dlp-configure-proxy.md).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="ac9f0-165">Onboarding di dispositivi nella gestione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="ac9f0-165">Onboarding devices into device management</span></span>

<span data-ttu-id="ac9f0-166">Per poter monitorare e proteggere gli elementi sensibili in un dispositivo, è necessario abilitare il monitoraggio dei dispositivi ed eseguire l'onboarding degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-166">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="ac9f0-167">Entrambe le azioni vengono eseguite nel portale Conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-167">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="ac9f0-168">Quando si vuole eseguire l'onboarding di nuovi dispositivi, si scarica lo script appropriato e lo si distribuisce in questi dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-168">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="ac9f0-169">Seguire la [procedura di onboarding dei dispositivi](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="ac9f0-169">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="ac9f0-170">Se i dispositivi sono già presenti in [Microsoft Defender per endpoint](/windows/security/threat-protection/), verranno visualizzati nell'elenco dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-170">If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="ac9f0-171">Seguire la [Procedura con dispositivi già presenti in Microsoft Defender per endpoint](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span><span class="sxs-lookup"><span data-stu-id="ac9f0-171">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="ac9f0-172">Onboarding dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="ac9f0-172">Onboarding devices</span></span>

<span data-ttu-id="ac9f0-173">In questo scenario di distribuzione si esegue l'onboarding di dispositivi non ancora caricati e si vogliono soltanto monitorare e proteggere gli elementi sensibili dalla condivisione involontaria nei dispositivi Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-173">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="ac9f0-174">Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="ac9f0-174">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="ac9f0-175">Aprire la pagina delle impostazioni del Centro conformità e scegliere **Onboarding di dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-175">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac9f0-176">![abilitare la gestione dei dispositivi](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="ac9f0-176">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="ac9f0-177">Anche se in genere sono necessari circa 60 secondi perché l'onboarding dei dispositivi sia abilitato, attendere fino a 30 minuti prima di contattare il supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-177">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="ac9f0-178">Scegliere **Gestione dispositivi** per aprire l'elenco **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-178">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="ac9f0-179">L'elenco sarà vuoto finché non si caricano dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-179">The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="ac9f0-180">Scegliere **Onboarding** per avviare il processo di onboarding.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-180">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="ac9f0-181">Scegliere il modo in cui si vogliono distribuire questi altri dispositivi dall'elenco **Metodo di distribuzione** e quindi **scaricare il pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-181">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac9f0-182">![metodo di distribuzione](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="ac9f0-182">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="ac9f0-183">Seguire le procedure appropriate in [Strumenti e metodi di onboarding per i dispositivi Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="ac9f0-183">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="ac9f0-184">Questo collegamento porta a una pagina di destinazione in cui è possibile accedere alle procedure di Microsoft Defender per endpoint che corrispondono al pacchetto di distribuzione selezionato nel passaggio 5:</span><span class="sxs-lookup"><span data-stu-id="ac9f0-184">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="ac9f0-185">Onboarding di dispositivi Windows 10 con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="ac9f0-185">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="ac9f0-186">Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ac9f0-186">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="ac9f0-187">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="ac9f0-187">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="ac9f0-188">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="ac9f0-188">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="ac9f0-189">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-189">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="ac9f0-190">Una volta completata l'operazione di onboarding, l'endpoint sarà visibile nell'elenco dei dispositivi e inizierà anche a inviare log di controllo delle attività a Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-190">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="ac9f0-191">Questa esperienza richiede la licenza.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-191">This experience is under license enforcement.</span></span> <span data-ttu-id="ac9f0-192">Se non si ha la licenza necessaria, i dati non saranno visibili o accessibili.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-192">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="ac9f0-193">Con dispositivi già presenti in Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="ac9f0-193">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="ac9f0-194">In questo scenario, Microsoft Defender per endpoint è già distribuito e ci sono endpoint per cui vengono creati report.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-194">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="ac9f0-195">Tutti questi endpoint compariranno nell'elenco dei dispositivi gestiti.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-195">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="ac9f0-196">È possibile continuare a eseguire l'onboarding di nuovi dispositivi in Endpoint DLP per ampliare la copertura usando la [procedura di onboarding dei dispositivi](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="ac9f0-196">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="ac9f0-197">Aprire il [Centro conformità Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="ac9f0-197">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="ac9f0-198">Aprire la pagina delle impostazioni del Centro conformità e scegliere **Abilita monitoraggio dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-198">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="ac9f0-199">Scegliere **Gestione dispositivi** per aprire l'elenco **Dispositivi**.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-199">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="ac9f0-200">Dovrebbe essere visualizzato l'elenco dei dispositivi che già inviano report a Microsoft Defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-200">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac9f0-201">![gestione dispositivi](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="ac9f0-201">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="ac9f0-202">Scegliere **Onboarding** se è necessario aggiungere altri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-202">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="ac9f0-203">Scegliere il modo in cui si vogliono distribuire questi altri dispositivi dall'elenco **Metodo di distribuzione** e quindi **Scarica pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-203">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="ac9f0-204">Seguire le procedure appropriate in [Strumenti e metodi di onboarding per i dispositivi Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="ac9f0-204">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="ac9f0-205">Questo collegamento porta a una pagina di destinazione in cui è possibile accedere alle procedure di Microsoft Defender per endpoint che corrispondono al pacchetto di distribuzione selezionato nel passaggio 5:</span><span class="sxs-lookup"><span data-stu-id="ac9f0-205">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="ac9f0-206">Onboarding di dispositivi Windows 10 con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="ac9f0-206">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="ac9f0-207">Onboarding di dispositivi Windows 10 con Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ac9f0-207">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="ac9f0-208">Onboarding di dispositivi Windows 10 con gli strumenti di Gestione dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="ac9f0-208">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="ac9f0-209">Onboarding di dispositivi Windows 10 con uno script locale</span><span class="sxs-lookup"><span data-stu-id="ac9f0-209">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="ac9f0-210">Onboarding di dispositivi VDI (Virtual Desktop Infrastructure) non persistenti.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-210">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="ac9f0-211">Una volta completata l'operazione di onboarding, l'endpoint sarà visibile nell'elenco **Dispositivi** e inizierà anche a inviare log di controllo a **Esplora attività**.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-211">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="ac9f0-212">Questa esperienza richiede la licenza.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-212">This experience is under license enforcement.</span></span> <span data-ttu-id="ac9f0-213">Se non si ha la licenza necessaria, i dati non saranno visibili o accessibili.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-213">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="ac9f0-214">Visualizzazione degli avvisi sulla perdita dei dati degli endpoint nel dashboard di gestione degli avvisi prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="ac9f0-214">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="ac9f0-215">Aprire la pagina Prevenzione della perdita dei dati nel centro conformità Microsoft 365 e scegliere Avvisi.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-215">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="ac9f0-216">Fare riferimento alle procedure in [Come configurare e visualizzare gli avvisi per i criteri di prevenzione della perdita dei dati](dlp-configure-view-alerts-policies.md) per visualizzare gli avvisi per i criteri di Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-216">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="ac9f0-217">Visualizzazione dei dati di Endpoint DLP in Esplora attività</span><span class="sxs-lookup"><span data-stu-id="ac9f0-217">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="ac9f0-218">Aprire la pagina [Classificazione dei dati](https://compliance.microsoft.com/dataclassification?viewid=overview) per il dominio nel Centro conformità Microsoft 365 e scegliere Esplora attività.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-218">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="ac9f0-219">Vedere le procedure in [Introduzione a Esplora attività](data-classification-activity-explorer.md) per accedere a tutti i dati relativi ai dispositivi endpoint e filtrarli.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-219">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ac9f0-220">![filtro di Esplora attività per i dispositivi endpoint](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="ac9f0-220">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="ac9f0-221">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ac9f0-221">Next steps</span></span>
<span data-ttu-id="ac9f0-222">Ora che si è eseguito l'onboarding dei dispositivi e che è possibile visualizzare i dati sulle attività in Esplora attività, è possibile procedere con il passaggio successivo, in cui si creano criteri di prevenzione della perdita dei dati per proteggere gli elementi sensibili.</span><span class="sxs-lookup"><span data-stu-id="ac9f0-222">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="ac9f0-223">Uso di Prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="ac9f0-223">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="ac9f0-224">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac9f0-224">See also</span></span>

- [<span data-ttu-id="ac9f0-225">Informazioni sulla prevenzione della perdita di dati degli endpoint </span><span class="sxs-lookup"><span data-stu-id="ac9f0-225">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="ac9f0-226">Uso della Prevenzione della perdita di dati degli endpoint </span><span class="sxs-lookup"><span data-stu-id="ac9f0-226">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="ac9f0-227">Informazioni sulla prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="ac9f0-227">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="ac9f0-228">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="ac9f0-228">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="ac9f0-229">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="ac9f0-229">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="ac9f0-230">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ac9f0-230">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="ac9f0-231">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="ac9f0-231">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="ac9f0-232">Abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac9f0-232">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="ac9f0-233">Dispositivi aggiunti ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="ac9f0-233">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="ac9f0-234">Scaricare il nuovo Microsoft Edge basato su Chromium</span><span class="sxs-lookup"><span data-stu-id="ac9f0-234">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)