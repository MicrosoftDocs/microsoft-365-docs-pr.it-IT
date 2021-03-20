---
title: Introduzione all'estensione per la conformità Microsoft (anteprima)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: Preparare e distribuire l'estensione per la conformità Microsoft.
ms.openlocfilehash: c6f56c65de6428374d912545db38337d34720c94
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838349"
---
# <a name="get-started-with-microsoft-compliance-extension-preview"></a><span data-ttu-id="355e6-103">Introduzione all'estensione per la conformità Microsoft (anteprima)</span><span class="sxs-lookup"><span data-stu-id="355e6-103">Get started with Microsoft Compliance Extension (preview)</span></span>

<span data-ttu-id="355e6-104">Usare queste procedure per implementare l'estensione di conformità Microsoft.</span><span class="sxs-lookup"><span data-stu-id="355e6-104">Use these procedures to roll out the Microsoft Compliance Extension.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="355e6-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="355e6-105">Before you begin</span></span>

<span data-ttu-id="355e6-106">Per usare l'estensione per la conformità Microsoft, occorre eseguire l'onboarding del dispositivo nella prevenzione della perdita dei dati degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="355e6-106">To use Microsoft Compliance Extension, the device must be onboarded into endpoint DLP.</span></span> <span data-ttu-id="355e6-107">Leggere questi articoli se non si ha familiarità con la prevenzione della perdita dei dati o endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="355e6-107">Review these articles if you are new to DLP or endpoint DLP</span></span>

- [<span data-ttu-id="355e6-108">Informazioni sull'estensione per la conformità Microsoft</span><span class="sxs-lookup"><span data-stu-id="355e6-108">Learn about Microsoft Compliance Extension</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="355e6-109">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="355e6-109">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="355e6-110">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="355e6-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="355e6-111">Creare un criterio di prevenzione della perdita dei dati da un modello</span><span class="sxs-lookup"><span data-stu-id="355e6-111">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="355e6-112">Informazioni sulla prevenzione della perdita dei dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="355e6-112">Learn about endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="355e6-113">Introduzione alla prevenzione della perdita dei dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="355e6-113">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="355e6-114">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="355e6-114">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
- [<span data-ttu-id="355e6-115">Configurazione del proxy del dispositivo e delle impostazioni di connessione a Internet per la prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="355e6-115">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)
- [<span data-ttu-id="355e6-116">Uso della prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="355e6-116">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="355e6-117">Licenze per SKU o sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="355e6-117">SKU/subscriptions licensing</span></span>

<span data-ttu-id="355e6-118">Prima di iniziare, è necessario verificare l'[abbonamento a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e gli eventuali componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="355e6-118">Before you get started, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="355e6-119">Per accedere e usare le funzionalità di Endpoint DLP, è necessario disporre di uno di questi abbonamenti o componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="355e6-119">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="355e6-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="355e6-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="355e6-121">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="355e6-121">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="355e6-122">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="355e6-122">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="355e6-123">Microsoft 365 A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="355e6-123">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="355e6-124">Microsoft 365 E5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="355e6-124">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="355e6-125">Microsoft 365 A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="355e6-125">Microsoft 365 A5 information protection and governance</span></span>

<span data-ttu-id="355e6-126">Per indicazioni dettagliate sulle licenze, vedere [Indicazioni dettagliate sulle licenze di Microsoft 365 per la sicurezza e la conformità](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="355e6-126">For detailed licensing guidance, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

- <span data-ttu-id="355e6-127">L'organizzazione deve disporre di una licenza per la prevenzione della perdita dei dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="355e6-127">Your org must be licensed for Endpoint DLP</span></span>
- <span data-ttu-id="355e6-128">I dispositivi devono eseguire Windows 10 x64, build 1809 o successiva.</span><span class="sxs-lookup"><span data-stu-id="355e6-128">Your devices must be running Windows 10 x64 build 1809 or later.</span></span>
- <span data-ttu-id="355e6-129">Il dispositivo deve disporre della versione client antimalware 4.18.2101.9 o successiva.</span><span class="sxs-lookup"><span data-stu-id="355e6-129">The device must have Antimalware Client Version is 4.18.2101.9 or later.</span></span> <span data-ttu-id="355e6-130">Controllare la versione corrente aprendo l'app **Sicurezza di Windows**, selezionando l'icona **Impostazioni** poi **Informazioni su**.</span><span class="sxs-lookup"><span data-stu-id="355e6-130">Check your current version by opening **Windows Security** app, select the **Settings** icon, and then select **About**.</span></span>


### <a name="permissions"></a><span data-ttu-id="355e6-131">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="355e6-131">Permissions</span></span>

<span data-ttu-id="355e6-132">I dati provenienti dalla prevenzione della perdita dei dati degli endpoint possono essere visualizzati in [Esplora attività](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="355e6-132">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="355e6-133">Sono disponibili sette ruoli per l'autorizzazione per Esplora attività, l'account usato per accedere ai dati deve essere membro di uno di essi.</span><span class="sxs-lookup"><span data-stu-id="355e6-133">There are seven roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="355e6-134">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="355e6-134">Global admin</span></span>
- <span data-ttu-id="355e6-135">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="355e6-135">Compliance admin</span></span>
- <span data-ttu-id="355e6-136">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="355e6-136">Security admin</span></span>
- <span data-ttu-id="355e6-137">Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="355e6-137">Compliance data admin</span></span>
- <span data-ttu-id="355e6-138">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="355e6-138">Global reader</span></span>
- <span data-ttu-id="355e6-139">Amministratore che legge i dati di sicurezza</span><span class="sxs-lookup"><span data-stu-id="355e6-139">Security reader</span></span>
- <span data-ttu-id="355e6-140">Amministratore che legge i report</span><span class="sxs-lookup"><span data-stu-id="355e6-140">Reports reader</span></span>

### <a name="overall-installation-workflow"></a><span data-ttu-id="355e6-141">Flusso di lavoro complessivo per l'installazione</span><span class="sxs-lookup"><span data-stu-id="355e6-141">Overall installation workflow</span></span>

<span data-ttu-id="355e6-142">La distribuzione dell'estensione per la conformità Microsoft è un processo in più fasi.</span><span class="sxs-lookup"><span data-stu-id="355e6-142">Deploying Microsoft Compliance Extension is a multi-phase process.</span></span> <span data-ttu-id="355e6-143">È possibile scegliere di eseguire l'installazione in un computer alla volta oppure usare Microsoft Endpoint Manager o Criteri di gruppo per la distribuzione a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="355e6-143">You can choose to install on one machine at a time, or use Microsoft Endpoint Manager or Group Policy for organization-wide deployments.</span></span>

1. <span data-ttu-id="355e6-144">[Preparazione dei dispositivi](#prepare-your-devices).</span><span class="sxs-lookup"><span data-stu-id="355e6-144">[Prepare your devices](#prepare-your-devices).</span></span>
2. [<span data-ttu-id="355e6-145">Configurazione di base SelfHost su un singolo computer</span><span class="sxs-lookup"><span data-stu-id="355e6-145">Basic Setup Single Machine Selfhost</span></span>](#basic-setup-single-machine-selfhost)
3. [<span data-ttu-id="355e6-146">Eseguire la distribuzione con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="355e6-146">Deploy using Microsoft Endpoint Manager</span></span>](#deploy-using-microsoft-endpoint-manager)
4. [<span data-ttu-id="355e6-147">Eseguire la distribuzione con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="355e6-147">Deploy using Group Policy</span></span>](#deploy-using-group-policy)
5. [<span data-ttu-id="355e6-148">Testare l'estensione</span><span class="sxs-lookup"><span data-stu-id="355e6-148">Test the Extension</span></span>](#test-the-extension)
6. [<span data-ttu-id="355e6-149">Usare il dashboard di gestione degli avvisi per visualizzare gli avvisi DLP di Chrome</span><span class="sxs-lookup"><span data-stu-id="355e6-149">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [<span data-ttu-id="355e6-150">Visualizzazione dei dati DLP di Chrome in Esplora attività</span><span class="sxs-lookup"><span data-stu-id="355e6-150">Viewing Chrome DLP data in activity explorer</span></span>](#viewing-chrome-dlp-data-in-activity-explorer) 

### <a name="prepare-infrastructure"></a><span data-ttu-id="355e6-151">Preparazione dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="355e6-151">Prepare infrastructure</span></span>

<span data-ttu-id="355e6-152">Se si sta implementando l'estensione per la conformità Microsoft in tutti i dispositivi Windows 10 monitorati, è consigliabile rimuovere Google Chrome dall'elenco delle app e dei browser non consentiti.</span><span class="sxs-lookup"><span data-stu-id="355e6-152">If you are rolling out the Microsoft Compliance Extension to all your monitored Windows 10 devices, you should remove Google Chrome from the unallowed app and unallowed browser lists.</span></span> <span data-ttu-id="355e6-153">Per altre informazioni, vedere [Browser non consentiti](endpoint-dlp-using.md#unallowed-browsers).</span><span class="sxs-lookup"><span data-stu-id="355e6-153">For more information, see [Unallowed browsers](endpoint-dlp-using.md#unallowed-browsers).</span></span> <span data-ttu-id="355e6-154">Se si sta eseguendo l'implementazione solo in alcuni dispositivi, è possibile lasciare Chrome nell'elenco delle app o dei browser non consentiti.</span><span class="sxs-lookup"><span data-stu-id="355e6-154">If you are only rolling it out to a few devices, you can leave Chrome on the unallowed browser or unallowed app lists.</span></span> <span data-ttu-id="355e6-155">L'estensione per la conformità Microsoft ignorerà le restrizioni di entrambi gli elenchi per i computer in cui è installata.</span><span class="sxs-lookup"><span data-stu-id="355e6-155">The Microsoft Compliance Extension will bypass the restrictions of both lists for those computers where it is installed.</span></span>  

### <a name="prepare-your-devices"></a><span data-ttu-id="355e6-156">Preparazione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="355e6-156">Prepare your devices</span></span>

1. <span data-ttu-id="355e6-157">Usare le procedure descritte in questi argomenti per eseguire l'onboarding dei dispositivi:</span><span class="sxs-lookup"><span data-stu-id="355e6-157">Use the procedures in these topics to onboard your devices:</span></span>
    1. [<span data-ttu-id="355e6-158">Introduzione alla prevenzione della perdita dei dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="355e6-158">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
    1. [<span data-ttu-id="355e6-159">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="355e6-159">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
    1. [<span data-ttu-id="355e6-160">Configurazione del proxy del dispositivo e delle impostazioni di connessione a Internet per la prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="355e6-160">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a><span data-ttu-id="355e6-161">Configurazione di base Selfhost su un singolo computer</span><span class="sxs-lookup"><span data-stu-id="355e6-161">Basic Setup Single Machine Selfhost</span></span>

<span data-ttu-id="355e6-162">Si tratta del metodo consigliato.</span><span class="sxs-lookup"><span data-stu-id="355e6-162">This is the recommended method.</span></span> 

1. <span data-ttu-id="355e6-163">Accedere al computer Windows 10 in cui si desidera installare l'estensione per la conformità Microsoft ed eseguire lo script di PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="355e6-163">Sign in to the Windows 10 computer on which you want to install the Microsoft Compliance Extension on, and run this PowerShell script as an administrator.</span></span> 

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ``` 

2.  <span data-ttu-id="355e6-164">Passare all'[estensione per la conformità Microsoft - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span><span class="sxs-lookup"><span data-stu-id="355e6-164">Navigate to [Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span></span>

3.  <span data-ttu-id="355e6-165">Installare l'estensione usando le istruzioni contenute nella pagina del Chrome Web Store.</span><span class="sxs-lookup"><span data-stu-id="355e6-165">Install the extension using the instructions on the Chrome Web Store page.</span></span>

### <a name="deploy-using-microsoft-endpoint-manager"></a><span data-ttu-id="355e6-166">Eseguire la distribuzione con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="355e6-166">Deploy using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="355e6-167">Usare questo metodo di configurazione per le distribuzioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="355e6-167">Use this setup method for organization-wide deployments.</span></span>


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a><span data-ttu-id="355e6-168">Abilitazione della chiave del Registro di sistema necessaria tramite Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="355e6-168">Enabling Required Registry Key via Microsoft Endpoint Manager</span></span>

1.  <span data-ttu-id="355e6-169">Creare uno script di PowerShell con i contenuti seguenti:</span><span class="sxs-lookup"><span data-stu-id="355e6-169">Create a PowerShell script with the following contents:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  <span data-ttu-id="355e6-170">Accedere all'[Interfaccia di amministrazione di Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="355e6-170">Sign in to the [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com).</span></span>

3.  <span data-ttu-id="355e6-171">Passare a **Dispositivi** > **Script** e selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="355e6-171">Navigate to **Devices** > **Scripts** and select **Add**.</span></span>

4.  <span data-ttu-id="355e6-172">Passare alla posizione dello script creato quando viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="355e6-172">Browse to the location of the script created when prompted.</span></span>

5.  <span data-ttu-id="355e6-173">Selezionare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="355e6-173">Select the following settings:</span></span>
    1. <span data-ttu-id="355e6-174">Esegui lo script con le credenziali di accesso: SÌ</span><span class="sxs-lookup"><span data-stu-id="355e6-174">Run this script using the logged-on credentials: YES</span></span>
    1. <span data-ttu-id="355e6-175">Applica il controllo della firma degli script: NO</span><span class="sxs-lookup"><span data-stu-id="355e6-175">Enforce script signature check: NO</span></span>
    1. <span data-ttu-id="355e6-176">Esegui script nell'host PowerShell a 64 bit: SÌ</span><span class="sxs-lookup"><span data-stu-id="355e6-176">Run script in 64-bit PowerShell Host: YES</span></span>

6.  <span data-ttu-id="355e6-177">Selezionare i gruppi di dispositivi appropriati e applicare il criterio.</span><span class="sxs-lookup"><span data-stu-id="355e6-177">Select the proper device groups and apply the policy.</span></span>

#### <a name="microsoft-endpoint-manager-force-install-steps"></a><span data-ttu-id="355e6-178">Procedura di installazione forzata di Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="355e6-178">Microsoft Endpoint Manager Force Install Steps</span></span>

<span data-ttu-id="355e6-179">Prima di aggiungere l'estensione per la conformità Microsoft all'elenco delle estensioni con installazione forzata, è importante inserire il file ADMX di Chrome.</span><span class="sxs-lookup"><span data-stu-id="355e6-179">Before adding the Microsoft Compliance Extension to the list of force-installed extensions, it is important to ingest the Chrome ADMX.</span></span> <span data-ttu-id="355e6-180">I passaggi per questo processo in Microsoft Endpoint Manager sono documentate da Google: [Gestisci browser Chrome con Microsoft Intune - Guida di Google Chrome Enterprise](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span><span class="sxs-lookup"><span data-stu-id="355e6-180">Steps for this process in Microsoft Endpoint Manager are documented by Google: [Manage Chrome Browser with Microsoft Intune - Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span></span>

 <span data-ttu-id="355e6-181">Dopo l'inserimento del file ADMX, è possibile seguire questa procedura per creare un profilo di configurazione per l'estensione.</span><span class="sxs-lookup"><span data-stu-id="355e6-181">After ingesting the ADMX, the steps below can be followed to create a configuration profile for this extension.</span></span>

1.  <span data-ttu-id="355e6-182">Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager (https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="355e6-182">Sign in to the Microsoft Endpoint Manager Admin Center (https://endpoint.microsoft.com).</span></span>

2.  <span data-ttu-id="355e6-183">Passare a Profili di configurazione.</span><span class="sxs-lookup"><span data-stu-id="355e6-183">Navigate to Configuration Profiles.</span></span>

3.  <span data-ttu-id="355e6-184">Selezionare **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="355e6-184">Select **Create Profile**.</span></span>

4.  <span data-ttu-id="355e6-185">Selezionare **Windows 10** come piattaforma.</span><span class="sxs-lookup"><span data-stu-id="355e6-185">Select **Windows 10** as the platform.</span></span>

5.  <span data-ttu-id="355e6-186">Selezionare **Personalizza** come tipo di profilo.</span><span class="sxs-lookup"><span data-stu-id="355e6-186">Select **Custom** as profile type.</span></span>

6.  <span data-ttu-id="355e6-187">Selezionare la scheda **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="355e6-187">Select the **Settings** tab.</span></span>

7.  <span data-ttu-id="355e6-188">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="355e6-188">Select **Add**.</span></span>

8.  <span data-ttu-id="355e6-189">Immettere le informazioni sui criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="355e6-189">Enter the following policy information.</span></span>
    
    <span data-ttu-id="355e6-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span><span class="sxs-lookup"><span data-stu-id="355e6-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span></span><br/>
    <span data-ttu-id="355e6-191">Tipo di dati:`String`</span><span class="sxs-lookup"><span data-stu-id="355e6-191">Data type: `String`</span></span><br/>
    <span data-ttu-id="355e6-192">Valore: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span><span class="sxs-lookup"><span data-stu-id="355e6-192">Value: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span></span>

9.  <span data-ttu-id="355e6-193">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="355e6-193">Click create.</span></span>

### <a name="deploy-using-group-policy"></a><span data-ttu-id="355e6-194">Eseguire la distribuzione tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="355e6-194">Deploy using Group Policy</span></span>

<span data-ttu-id="355e6-195">Se non si desidera usare Microsoft Endpoint Manager, è possibile usare i criteri di gruppo per distribuire l'estensione per la conformità Microsoft nell'intera organizzazione</span><span class="sxs-lookup"><span data-stu-id="355e6-195">If you don't want to use Microsoft Endpoint Manager, you can use group policies to deploy the Microsoft Compliance Extension across your organization</span></span>

1. <span data-ttu-id="355e6-196">I dispositivi devono essere gestibili tramite Criteri di gruppo e occorre importare tutti i file ADMX di Chrome nell'archivio centrale dei Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="355e6-196">Your devices must be manageable via Group Policy, and you need to import all Chrome ADMXs into the Group Policy Central Store.</span></span> <span data-ttu-id="355e6-197">Per altre informazioni, vedere [Come creare e gestire l'archivio centrale per i modelli amministrativi di Criteri di gruppo in Windows](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span><span class="sxs-lookup"><span data-stu-id="355e6-197">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span></span>

2.  <span data-ttu-id="355e6-198">Creare uno script di PowerShell con il comando PowerShell:</span><span class="sxs-lookup"><span data-stu-id="355e6-198">Create a PowerShell script using this PowerShell command:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  <span data-ttu-id="355e6-199">Aprire la **console di gestione di Criteri di gruppo** e passare all'unità organizzativa (OU).</span><span class="sxs-lookup"><span data-stu-id="355e6-199">Open the **Group Policy Management Console** and navigate to your organizational unit (OU).</span></span>

4.  <span data-ttu-id="355e6-200">Fare clic con il pulsante destro del mouse e selezionare **Crea oggetto Criteri di gruppo in questo dominio e collegalo qui**.</span><span class="sxs-lookup"><span data-stu-id="355e6-200">Right-click and select **Create a GPO in this domain and Link it here**.</span></span> <span data-ttu-id="355e6-201">Quando viene richiesto, assegnare un nome descrittivo a questo oggetto Criteri di gruppo e completare la creazione.</span><span class="sxs-lookup"><span data-stu-id="355e6-201">When prompted, assign a descriptive name to this group policy object (GPO) and finish creating it.</span></span>

5.  <span data-ttu-id="355e6-202">Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="355e6-202">Right-click the GPO and select **Edit**.</span></span>

6.  <span data-ttu-id="355e6-203">Passare a **Configurazione computer** > **Preferenze** > **Impostazioni Pannello di controllo** > **Attività pianificate**.</span><span class="sxs-lookup"><span data-stu-id="355e6-203">Go to **Computer Configuration** > **Preferences** > **Control Panel Settings** > **Scheduled Tasks**.</span></span>

7.  <span data-ttu-id="355e6-204">Per creare una nuova attività immediata, selezionare tramite il pulsante destro del mouse **Nuova** > **Nuova attività immediata (in Windows 7)**.</span><span class="sxs-lookup"><span data-stu-id="355e6-204">Create a new immediate task by selecting right-clicking and selecting **New** > **Immediate Task (At least Windows 7)**.</span></span>

8.  <span data-ttu-id="355e6-205">Assegnare un nome e una descrizione all'attività.</span><span class="sxs-lookup"><span data-stu-id="355e6-205">Give the task a name & description.</span></span>

9.  <span data-ttu-id="355e6-206">Scegliere l'account corrispondente per eseguire l'attività immediata, ad esempio NT Authority</span><span class="sxs-lookup"><span data-stu-id="355e6-206">Choose the corresponding account to run the immediate task, for example NT Authority</span></span>

10. <span data-ttu-id="355e6-207">Selezionare **Esegui con i privilegi più elevati**.</span><span class="sxs-lookup"><span data-stu-id="355e6-207">Select **Run with highest privileges**.</span></span>

11. <span data-ttu-id="355e6-208">Configurare i criteri per Windows 10.</span><span class="sxs-lookup"><span data-stu-id="355e6-208">Configure the policy for Windows 10.</span></span>

12. <span data-ttu-id="355e6-209">Nella scheda **Azioni**, selezionare l'azione **Avvia un programma**.</span><span class="sxs-lookup"><span data-stu-id="355e6-209">In the **Actions** tab, select the action **Start a program**.</span></span>

13. <span data-ttu-id="355e6-210">Immettere il percorso del programma o dello script creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="355e6-210">Enter the path to the Program/Script created in Step 1.</span></span>

14. <span data-ttu-id="355e6-211">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="355e6-211">Select **Apply**.</span></span>

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a><span data-ttu-id="355e6-212">Aggiunta dell'estensione di Chrome all'elenco ForceInstall</span><span class="sxs-lookup"><span data-stu-id="355e6-212">Adding the Chrome Extension to the ForceInstall List</span></span>

1.  <span data-ttu-id="355e6-213">Nell'editor di gestione di Criteri di gruppo passare all'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="355e6-213">In the Group Policy Management Editor, navigate to your OU.</span></span>

2.  <span data-ttu-id="355e6-214">Espandere il percorso seguente **Configurazione computer/utente** > **Criteri** > **Modelli amministrativi** > **Modelli amministrativi classici** > **Google** > **Google Chrome** > **Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="355e6-214">Expand the following path **Computer/User configuration** > **Policies** > **Administrative templates** > **Classic administrative templates** > **Google** > **Google Chrome** > **Extensions**.</span></span> <span data-ttu-id="355e6-215">Questo percorso può variare a seconda della configurazione.</span><span class="sxs-lookup"><span data-stu-id="355e6-215">This path may vary depending on your configuration.</span></span>

3.  <span data-ttu-id="355e6-216">Selezionare **Configura l'elenco delle estensioni con installazione forzata**.</span><span class="sxs-lookup"><span data-stu-id="355e6-216">Select **Configure the list of force-installed extensions**.</span></span>

4.  <span data-ttu-id="355e6-217">Fare clic con il pulsante destro del mouse e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="355e6-217">Right click and select **Edit**.</span></span>

5.  <span data-ttu-id="355e6-218">Selezionare **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="355e6-218">Select **Enabled**.</span></span>

6.  <span data-ttu-id="355e6-219">Selezionare **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="355e6-219">Select **Show**.</span></span>

7.  <span data-ttu-id="355e6-220">In **Valore**, aggiungere la voce seguente: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span><span class="sxs-lookup"><span data-stu-id="355e6-220">Under **Value**, add the following entry: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span></span>

8.  <span data-ttu-id="355e6-221">Selezionare **OK**, poi **Applica**.</span><span class="sxs-lookup"><span data-stu-id="355e6-221">Select **OK** and then **Apply**.</span></span>

### <a name="test-the-extension"></a><span data-ttu-id="355e6-222">Testare l'estensione</span><span class="sxs-lookup"><span data-stu-id="355e6-222">Test the Extension</span></span>

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a><span data-ttu-id="355e6-223">Caricare nel servizio cloud o accedere tramite browser non consentiti a Uscita cloud</span><span class="sxs-lookup"><span data-stu-id="355e6-223">Upload to cloud service, or access by unallowed browsers Cloud Egress</span></span>  

1. <span data-ttu-id="355e6-224">Creare o recuperare un elemento sensibile e provare a caricare un file in un dominio dei servizi con restrizioni dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="355e6-224">Create or get a sensitive item and, try to upload a file to one of your organization’s restricted service domains.</span></span> <span data-ttu-id="355e6-225">I dati riservati devono corrispondere a uno dei [tipi di informazioni sensibili](sensitive-information-type-entity-definitions.md) predefiniti o a uno dei tipi di informazioni sensibili dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="355e6-225">The sensitive data must match one of our built-in [Sensitive Info Types](sensitive-information-type-entity-definitions.md), or one of your organization’s sensitive information types.</span></span> <span data-ttu-id="355e6-226">Si dovrebbe ricevere una notifica di tipo avviso popup di DLP dal dispositivo che si sta testando, che informa che questa azione non è consentita quando il file è aperto.</span><span class="sxs-lookup"><span data-stu-id="355e6-226">You should get a DLP toast notification on the device you are testing from that shows that this action is not allowed when the file is open.</span></span>

#### <a name="testing-other-dlp-scenarios-in-chrome"></a><span data-ttu-id="355e6-227">Test di altri scenari di prevenzione della perdita dei dati in Chrome</span><span class="sxs-lookup"><span data-stu-id="355e6-227">Testing other DLP scenarios in Chrome</span></span> 

<span data-ttu-id="355e6-228">Dopo aver rimosso Chrome dall'elenco di browser o app non autorizzati, è possibile testare gli scenari seguenti per verificare che il comportamento soddisfi i requisiti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="355e6-228">Now that you’ve removed Chrome from the disallowed browsers/apps list, you can test the scenarios below to confirm the behavior meets your organization’s requirements:</span></span>

- <span data-ttu-id="355e6-229">Copiare dati da un elemento sensibile a un altro documento tramite gli Appunti</span><span class="sxs-lookup"><span data-stu-id="355e6-229">Copy data from a sensitive item to another document using the Clipboard</span></span>
    - <span data-ttu-id="355e6-230">Per eseguire il test, aprire un file protetto da azioni di copia negli Appunti nel browser Chrome e provare a copiare i dati dal file.</span><span class="sxs-lookup"><span data-stu-id="355e6-230">To test, open a file that is protected against copy to clipboard actions in the Chrome browser and attempt to copy data from the file.</span></span>
    - <span data-ttu-id="355e6-231">Risultato previsto: notifica di avviso popup di DLP che comunica che questa azione non è consentita quando il file è aperto.</span><span class="sxs-lookup"><span data-stu-id="355e6-231">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="355e6-232">Stampa di un documento</span><span class="sxs-lookup"><span data-stu-id="355e6-232">Print a document</span></span>
    - <span data-ttu-id="355e6-233">Per eseguire il test, aprire un file protetto dalle azioni di stampa nel browser Chrome e provare a stampare il file.</span><span class="sxs-lookup"><span data-stu-id="355e6-233">To test, open a file that is protected against print actions in the Chrome browser and attempt to print the file.</span></span>
    - <span data-ttu-id="355e6-234">Risultato previsto: notifica di avviso popup di DLP che comunica che questa azione non è consentita quando il file è aperto.</span><span class="sxs-lookup"><span data-stu-id="355e6-234">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="355e6-235">Copia in supporti rimovibili USB</span><span class="sxs-lookup"><span data-stu-id="355e6-235">Copy to USB Removeable Media</span></span>
    - <span data-ttu-id="355e6-236">Per eseguire un test, provare a salvare il file in un archivio multimediale rimovibile.</span><span class="sxs-lookup"><span data-stu-id="355e6-236">To test, try to save the file to a removeable media storage.</span></span>
    - <span data-ttu-id="355e6-237">Risultato previsto: notifica di avviso popup di DLP che comunica che questa azione non è consentita quando il file è aperto.</span><span class="sxs-lookup"><span data-stu-id="355e6-237">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="355e6-238">Copia in condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="355e6-238">Copy to Network Share</span></span>
    - <span data-ttu-id="355e6-239">Per eseguire un test, provare a salvare il file in una condivisione di rete.</span><span class="sxs-lookup"><span data-stu-id="355e6-239">To test, try to save the file to a network share.</span></span>
    - <span data-ttu-id="355e6-240">Risultato previsto: notifica di avviso popup di DLP che comunica che questa azione non è consentita quando il file è aperto.</span><span class="sxs-lookup"><span data-stu-id="355e6-240">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a><span data-ttu-id="355e6-241">Usare il dashboard di gestione degli avvisi per visualizzare gli avvisi di DLP di Chrome</span><span class="sxs-lookup"><span data-stu-id="355e6-241">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>

1. <span data-ttu-id="355e6-242">Aprire la pagina di **Prevenzione della perdita dei dati** nel **Centro conformità Microsoft 365** e scegliere [Avvisi](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="355e6-242">Open the **Data loss prevention** page in the [Microsoft 365 Compliance center](https://compliance.microsoft.com) and select **Alerts**.</span></span>

2. <span data-ttu-id="355e6-243">Fare riferimento alle procedure in [Come configurare e visualizzare gli avvisi per i criteri di prevenzione della perdita dei dati](dlp-configure-view-alerts-policies.md) per visualizzare gli avvisi per i criteri di prevenzione della perdita dei dati degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="355e6-243">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a><span data-ttu-id="355e6-244">Visualizzazione dei dati DLP di Chrome in Esplora attività</span><span class="sxs-lookup"><span data-stu-id="355e6-244">Viewing Chrome DLP data in activity explorer</span></span>

1. <span data-ttu-id="355e6-245">Aprire la [pagina Classificazione dei dati](https://compliance.microsoft.com/dataclassification?viewid=overview) per il dominio nel Centro conformità Microsoft 365 e scegliere **Esplora attività**.</span><span class="sxs-lookup"><span data-stu-id="355e6-245">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose **Activity explorer**.</span></span>

2. <span data-ttu-id="355e6-246">Vedere le procedure in [Introduzione a Esplora attività](data-classification-activity-explorer.md) per accedere a tutti i dati relativi ai dispositivi endpoint e filtrarli.</span><span class="sxs-lookup"><span data-stu-id="355e6-246">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="355e6-247">![filtro di Esplora attività per i dispositivi endpoint](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="355e6-247">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

### <a name="known-issues-and-limitations"></a><span data-ttu-id="355e6-248">Problemi noti e limitazioni</span><span class="sxs-lookup"><span data-stu-id="355e6-248">Known Issues and Limitations</span></span>

1. <span data-ttu-id="355e6-249">L’imposizione del trascinamento della selezione per il caricamento della cartella non è supportato.</span><span class="sxs-lookup"><span data-stu-id="355e6-249">Drag & Drop enforcement for folder upload is not supported.</span></span>
2. <span data-ttu-id="355e6-250">L'imposizione del blocco override per l’uscita dal cloud non è supportata.</span><span class="sxs-lookup"><span data-stu-id="355e6-250">Block Override enforcement for cloud egress is not supported.</span></span>
3. <span data-ttu-id="355e6-251">La modalità Incognito non è supportata e deve essere disabilitata.</span><span class="sxs-lookup"><span data-stu-id="355e6-251">Incognito mode is not supported and must be disabled.</span></span>

## <a name="next-steps"></a><span data-ttu-id="355e6-252">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="355e6-252">Next steps</span></span>
<span data-ttu-id="355e6-253">Ora che si è eseguito l'onboarding dei dispositivi e che è possibile visualizzare i dati sulle attività in Esplora attività, è possibile procedere con il passaggio successivo, in cui si creano criteri di prevenzione della perdita dei dati per proteggere gli elementi sensibili.</span><span class="sxs-lookup"><span data-stu-id="355e6-253">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="355e6-254">Uso di Prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="355e6-254">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="355e6-255">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="355e6-255">See also</span></span>

- [<span data-ttu-id="355e6-256">Informazioni sulla prevenzione della perdita di dati degli endpoint </span><span class="sxs-lookup"><span data-stu-id="355e6-256">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="355e6-257">Uso della Prevenzione della perdita di dati degli endpoint </span><span class="sxs-lookup"><span data-stu-id="355e6-257">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="355e6-258">Panoramica sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="355e6-258">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="355e6-259">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="355e6-259">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="355e6-260">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="355e6-260">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="355e6-261">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="355e6-261">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="355e6-262">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="355e6-262">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="355e6-263">Abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="355e6-263">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="355e6-264">Dispositivi aggiunti ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="355e6-264">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="355e6-265">Scaricare il nuovo Microsoft Edge basato su Chromium</span><span class="sxs-lookup"><span data-stu-id="355e6-265">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)