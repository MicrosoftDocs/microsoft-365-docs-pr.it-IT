---
title: Introduzione all'estensione per Conformità Microsoft
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
description: Preparare e distribuire l'estensione per Conformità Microsoft.
ms.openlocfilehash: 5a2fa5958117d14715292245924dce2ff63b09a0
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843831"
---
# <a name="get-started-with-microsoft-compliance-extension"></a><span data-ttu-id="82c8c-103">Introduzione all'estensione per Conformità Microsoft</span><span class="sxs-lookup"><span data-stu-id="82c8c-103">Get started with Microsoft Compliance Extension</span></span>

<span data-ttu-id="82c8c-104">Usare queste procedure per implementare l'estensione di conformità Microsoft.</span><span class="sxs-lookup"><span data-stu-id="82c8c-104">Use these procedures to roll out the Microsoft Compliance Extension.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="82c8c-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="82c8c-105">Before you begin</span></span>

<span data-ttu-id="82c8c-106">Per usare l'estensione per la conformità Microsoft, occorre eseguire l'onboarding del dispositivo nella prevenzione della perdita dei dati degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="82c8c-106">To use Microsoft Compliance Extension, the device must be onboarded into endpoint DLP.</span></span> <span data-ttu-id="82c8c-107">Leggere questi articoli se non si ha familiarità con la prevenzione della perdita dei dati o endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="82c8c-107">Review these articles if you are new to DLP or endpoint DLP</span></span>

- [<span data-ttu-id="82c8c-108">Informazioni sull'estensione per la conformità Microsoft</span><span class="sxs-lookup"><span data-stu-id="82c8c-108">Learn about Microsoft Compliance Extension</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="82c8c-109">Informazioni sulla prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="82c8c-109">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="82c8c-110">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="82c8c-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="82c8c-111">Creare un criterio di prevenzione della perdita dei dati da un modello</span><span class="sxs-lookup"><span data-stu-id="82c8c-111">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="82c8c-112">Informazioni sulla prevenzione della perdita dei dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="82c8c-112">Learn about endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="82c8c-113">Introduzione alla prevenzione della perdita dei dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="82c8c-113">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="82c8c-114">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="82c8c-114">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
- [<span data-ttu-id="82c8c-115">Configurazione del proxy del dispositivo e delle impostazioni di connessione a Internet per la prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="82c8c-115">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)
- [<span data-ttu-id="82c8c-116">Uso della prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="82c8c-116">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="82c8c-117">Licenze per SKU o sottoscrizioni</span><span class="sxs-lookup"><span data-stu-id="82c8c-117">SKU/subscriptions licensing</span></span>

<span data-ttu-id="82c8c-118">Prima di iniziare, è necessario verificare l'[abbonamento a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e gli eventuali componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="82c8c-118">Before you get started, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="82c8c-119">Per accedere e usare le funzionalità di Endpoint DLP, è necessario disporre di uno di questi abbonamenti o componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="82c8c-119">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="82c8c-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="82c8c-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="82c8c-121">Microsoft 365 A5 (EDU)</span><span class="sxs-lookup"><span data-stu-id="82c8c-121">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="82c8c-122">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="82c8c-122">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="82c8c-123">Microsoft 365 A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="82c8c-123">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="82c8c-124">Microsoft 365 E5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="82c8c-124">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="82c8c-125">Microsoft 365 A5 Information Protection and Governance</span><span class="sxs-lookup"><span data-stu-id="82c8c-125">Microsoft 365 A5 information protection and governance</span></span>

<span data-ttu-id="82c8c-126">Per indicazioni dettagliate sulle licenze, vedere [Indicazioni dettagliate sulle licenze di Microsoft 365 per la sicurezza e la conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span><span class="sxs-lookup"><span data-stu-id="82c8c-126">For detailed licensing guidance, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

- <span data-ttu-id="82c8c-127">L'organizzazione deve disporre di una licenza per la prevenzione della perdita dei dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="82c8c-127">Your org must be licensed for Endpoint DLP</span></span>
- <span data-ttu-id="82c8c-128">I dispositivi devono eseguire Windows 10 x64, build 1809 o successiva.</span><span class="sxs-lookup"><span data-stu-id="82c8c-128">Your devices must be running Windows 10 x64 build 1809 or later.</span></span>
- <span data-ttu-id="82c8c-129">Il dispositivo deve disporre della versione client antimalware 4.18.2101.9 o successiva.</span><span class="sxs-lookup"><span data-stu-id="82c8c-129">The device must have Antimalware Client Version is 4.18.2101.9 or later.</span></span> <span data-ttu-id="82c8c-130">Controllare la versione corrente aprendo l'app **Sicurezza di Windows**, selezionando l'icona **Impostazioni** poi **Informazioni su**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-130">Check your current version by opening **Windows Security** app, select the **Settings** icon, and then select **About**.</span></span>


### <a name="permissions"></a><span data-ttu-id="82c8c-131">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="82c8c-131">Permissions</span></span>

<span data-ttu-id="82c8c-132">I dati provenienti dalla prevenzione della perdita dei dati degli endpoint possono essere visualizzati in [Esplora attività](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="82c8c-132">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="82c8c-133">Sono disponibili sette ruoli per l'autorizzazione per Esplora attività, l'account usato per accedere ai dati deve essere membro di uno di essi.</span><span class="sxs-lookup"><span data-stu-id="82c8c-133">There are seven roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="82c8c-134">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="82c8c-134">Global admin</span></span>
- <span data-ttu-id="82c8c-135">Amministratore di conformità</span><span class="sxs-lookup"><span data-stu-id="82c8c-135">Compliance admin</span></span>
- <span data-ttu-id="82c8c-136">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="82c8c-136">Security admin</span></span>
- <span data-ttu-id="82c8c-137">Amministratore dati di conformità</span><span class="sxs-lookup"><span data-stu-id="82c8c-137">Compliance data admin</span></span>
- <span data-ttu-id="82c8c-138">Ruolo con autorizzazioni di lettura globali</span><span class="sxs-lookup"><span data-stu-id="82c8c-138">Global reader</span></span>
- <span data-ttu-id="82c8c-139">Amministratore che legge i dati di sicurezza</span><span class="sxs-lookup"><span data-stu-id="82c8c-139">Security reader</span></span>
- <span data-ttu-id="82c8c-140">Amministratore che legge i report</span><span class="sxs-lookup"><span data-stu-id="82c8c-140">Reports reader</span></span>

### <a name="overall-installation-workflow"></a><span data-ttu-id="82c8c-141">Flusso di lavoro complessivo per l'installazione</span><span class="sxs-lookup"><span data-stu-id="82c8c-141">Overall installation workflow</span></span>

<span data-ttu-id="82c8c-p105">La distribuzione dell'estensione per la conformità Microsoft è un processo in più fasi. È possibile scegliere di eseguire l'installazione in un computer alla volta oppure usare Microsoft Endpoint Manager o Criteri di gruppo per la distribuzione a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="82c8c-p105">Deploying Microsoft Compliance Extension is a multi-phase process. You can choose to install on one machine at a time, or use Microsoft Endpoint Manager or Group Policy for organization-wide deployments.</span></span>

1. <span data-ttu-id="82c8c-144">[Preparazione dei dispositivi](#prepare-your-devices).</span><span class="sxs-lookup"><span data-stu-id="82c8c-144">[Prepare your devices](#prepare-your-devices).</span></span>
2. [<span data-ttu-id="82c8c-145">Configurazione di base SelfHost su un singolo computer</span><span class="sxs-lookup"><span data-stu-id="82c8c-145">Basic Setup Single Machine Selfhost</span></span>](#basic-setup-single-machine-selfhost)
3. [<span data-ttu-id="82c8c-146">Eseguire la distribuzione con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="82c8c-146">Deploy using Microsoft Endpoint Manager</span></span>](#deploy-using-microsoft-endpoint-manager)
4. [<span data-ttu-id="82c8c-147">Eseguire la distribuzione con Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="82c8c-147">Deploy using Group Policy</span></span>](#deploy-using-group-policy)
5. [<span data-ttu-id="82c8c-148">Testare l'estensione</span><span class="sxs-lookup"><span data-stu-id="82c8c-148">Test the Extension</span></span>](#test-the-extension)
6. [<span data-ttu-id="82c8c-149">Usare il dashboard di gestione degli avvisi per visualizzare gli avvisi DLP di Chrome</span><span class="sxs-lookup"><span data-stu-id="82c8c-149">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [<span data-ttu-id="82c8c-150">Visualizzazione dei dati DLP di Chrome in Esplora attività</span><span class="sxs-lookup"><span data-stu-id="82c8c-150">Viewing Chrome DLP data in activity explorer</span></span>](#viewing-chrome-dlp-data-in-activity-explorer) 

### <a name="prepare-infrastructure"></a><span data-ttu-id="82c8c-151">Preparazione dell'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="82c8c-151">Prepare infrastructure</span></span>

<span data-ttu-id="82c8c-152">Se si sta implementando l'estensione per la conformità Microsoft in tutti i dispositivi Windows 10 monitorati, è consigliabile rimuovere Google Chrome dall'elenco delle app e dei browser non consentiti.</span><span class="sxs-lookup"><span data-stu-id="82c8c-152">If you are rolling out the Microsoft Compliance Extension to all your monitored Windows 10 devices, you should remove Google Chrome from the unallowed app and unallowed browser lists.</span></span> <span data-ttu-id="82c8c-153">Per altre informazioni, vedere [Browser non consentiti](endpoint-dlp-using.md#unallowed-browsers).</span><span class="sxs-lookup"><span data-stu-id="82c8c-153">For more information, see [Unallowed browsers](endpoint-dlp-using.md#unallowed-browsers).</span></span> <span data-ttu-id="82c8c-154">Se si sta eseguendo l'implementazione solo in alcuni dispositivi, è possibile lasciare Chrome nell'elenco delle app o dei browser non consentiti.</span><span class="sxs-lookup"><span data-stu-id="82c8c-154">If you are only rolling it out to a few devices, you can leave Chrome on the unallowed browser or unallowed app lists.</span></span> <span data-ttu-id="82c8c-155">L'estensione per la conformità Microsoft ignorerà le restrizioni di entrambi gli elenchi per i computer in cui è installata.</span><span class="sxs-lookup"><span data-stu-id="82c8c-155">The Microsoft Compliance Extension will bypass the restrictions of both lists for those computers where it is installed.</span></span>  

### <a name="prepare-your-devices"></a><span data-ttu-id="82c8c-156">Preparazione dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="82c8c-156">Prepare your devices</span></span>

1. <span data-ttu-id="82c8c-157">Usare le procedure descritte in questi argomenti per eseguire l'onboarding dei dispositivi:</span><span class="sxs-lookup"><span data-stu-id="82c8c-157">Use the procedures in these topics to onboard your devices:</span></span>
    1. [<span data-ttu-id="82c8c-158">Introduzione alla prevenzione della perdita dei dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="82c8c-158">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
    1. [<span data-ttu-id="82c8c-159">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="82c8c-159">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
    1. [<span data-ttu-id="82c8c-160">Configurazione del proxy del dispositivo e delle impostazioni di connessione a Internet per la prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="82c8c-160">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a><span data-ttu-id="82c8c-161">Configurazione di base Selfhost su un singolo computer</span><span class="sxs-lookup"><span data-stu-id="82c8c-161">Basic Setup Single Machine Selfhost</span></span>

<span data-ttu-id="82c8c-162">Si tratta del metodo consigliato.</span><span class="sxs-lookup"><span data-stu-id="82c8c-162">This is the recommended method.</span></span> 

1. <span data-ttu-id="82c8c-163">Accedere al computer Windows 10 in cui si desidera installare l'estensione per la conformità Microsoft ed eseguire lo script di PowerShell come amministratore.</span><span class="sxs-lookup"><span data-stu-id="82c8c-163">Sign in to the Windows 10 computer on which you want to install the Microsoft Compliance Extension on, and run this PowerShell script as an administrator.</span></span> 

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ``` 

2.  <span data-ttu-id="82c8c-164">Passare all'[estensione per la conformità Microsoft - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span><span class="sxs-lookup"><span data-stu-id="82c8c-164">Navigate to [Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span></span>

3.  <span data-ttu-id="82c8c-165">Installare l'estensione usando le istruzioni contenute nella pagina del Chrome Web Store.</span><span class="sxs-lookup"><span data-stu-id="82c8c-165">Install the extension using the instructions on the Chrome Web Store page.</span></span>

### <a name="deploy-using-microsoft-endpoint-manager"></a><span data-ttu-id="82c8c-166">Eseguire la distribuzione con Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="82c8c-166">Deploy using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="82c8c-167">Usare questo metodo di configurazione per le distribuzioni a livello di organizzazione.</span><span class="sxs-lookup"><span data-stu-id="82c8c-167">Use this setup method for organization-wide deployments.</span></span>


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a><span data-ttu-id="82c8c-168">Abilitazione della chiave del Registro di sistema necessaria tramite Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="82c8c-168">Enabling Required Registry Key via Microsoft Endpoint Manager</span></span>

1.  <span data-ttu-id="82c8c-169">Creare uno script di PowerShell con i contenuti seguenti:</span><span class="sxs-lookup"><span data-stu-id="82c8c-169">Create a PowerShell script with the following contents:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  <span data-ttu-id="82c8c-170">Accedere all'[Interfaccia di amministrazione di Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="82c8c-170">Sign in to the [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com).</span></span>

3.  <span data-ttu-id="82c8c-171">Passare a **Dispositivi** > **Script** e selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-171">Navigate to **Devices** > **Scripts** and select **Add**.</span></span>

4.  <span data-ttu-id="82c8c-172">Passare alla posizione dello script creato quando viene richiesto.</span><span class="sxs-lookup"><span data-stu-id="82c8c-172">Browse to the location of the script created when prompted.</span></span>

5.  <span data-ttu-id="82c8c-173">Selezionare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="82c8c-173">Select the following settings:</span></span>
    1. <span data-ttu-id="82c8c-174">Esegui lo script con le credenziali di accesso: SÌ</span><span class="sxs-lookup"><span data-stu-id="82c8c-174">Run this script using the logged-on credentials: YES</span></span>
    1. <span data-ttu-id="82c8c-175">Applica il controllo della firma degli script: NO</span><span class="sxs-lookup"><span data-stu-id="82c8c-175">Enforce script signature check: NO</span></span>
    1. <span data-ttu-id="82c8c-176">Esegui script nell'host PowerShell a 64 bit: SÌ</span><span class="sxs-lookup"><span data-stu-id="82c8c-176">Run script in 64-bit PowerShell Host: YES</span></span>

6.  <span data-ttu-id="82c8c-177">Selezionare i gruppi di dispositivi appropriati e applicare il criterio.</span><span class="sxs-lookup"><span data-stu-id="82c8c-177">Select the proper device groups and apply the policy.</span></span>

#### <a name="microsoft-endpoint-manager-force-install-steps"></a><span data-ttu-id="82c8c-178">Procedura di installazione forzata di Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="82c8c-178">Microsoft Endpoint Manager Force Install Steps</span></span>

<span data-ttu-id="82c8c-179">Prima di aggiungere l'estensione per la conformità Microsoft all'elenco delle estensioni con installazione forzata, è importante inserire il file ADMX di Chrome.</span><span class="sxs-lookup"><span data-stu-id="82c8c-179">Before adding the Microsoft Compliance Extension to the list of force-installed extensions, it is important to ingest the Chrome ADMX.</span></span> <span data-ttu-id="82c8c-180">I passaggi per questo processo in Microsoft Endpoint Manager sono documentate da Google: [Gestisci browser Chrome con Microsoft Intune - Guida di Google Chrome Enterprise](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span><span class="sxs-lookup"><span data-stu-id="82c8c-180">Steps for this process in Microsoft Endpoint Manager are documented by Google: [Manage Chrome Browser with Microsoft Intune - Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span></span>

 <span data-ttu-id="82c8c-181">Dopo l'inserimento del file ADMX, è possibile seguire questa procedura per creare un profilo di configurazione per l'estensione.</span><span class="sxs-lookup"><span data-stu-id="82c8c-181">After ingesting the ADMX, the steps below can be followed to create a configuration profile for this extension.</span></span>

1.  <span data-ttu-id="82c8c-182">Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager (https://endpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="82c8c-182">Sign in to the Microsoft Endpoint Manager Admin Center (https://endpoint.microsoft.com).</span></span>

2.  <span data-ttu-id="82c8c-183">Passare a Profili di configurazione.</span><span class="sxs-lookup"><span data-stu-id="82c8c-183">Navigate to Configuration Profiles.</span></span>

3.  <span data-ttu-id="82c8c-184">Selezionare **Crea profilo**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-184">Select **Create Profile**.</span></span>

4.  <span data-ttu-id="82c8c-185">Selezionare **Windows 10** come piattaforma.</span><span class="sxs-lookup"><span data-stu-id="82c8c-185">Select **Windows 10** as the platform.</span></span>

5.  <span data-ttu-id="82c8c-186">Selezionare **Personalizza** come tipo di profilo.</span><span class="sxs-lookup"><span data-stu-id="82c8c-186">Select **Custom** as profile type.</span></span>

6.  <span data-ttu-id="82c8c-187">Selezionare la scheda **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-187">Select the **Settings** tab.</span></span>

7.  <span data-ttu-id="82c8c-188">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-188">Select **Add**.</span></span>

8.  <span data-ttu-id="82c8c-189">Immettere le informazioni sui criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="82c8c-189">Enter the following policy information.</span></span>
    
    <span data-ttu-id="82c8c-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span><span class="sxs-lookup"><span data-stu-id="82c8c-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span></span><br/>
    <span data-ttu-id="82c8c-191">Tipo di dati:`String`</span><span class="sxs-lookup"><span data-stu-id="82c8c-191">Data type: `String`</span></span><br/>
    <span data-ttu-id="82c8c-192">Valore: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span><span class="sxs-lookup"><span data-stu-id="82c8c-192">Value: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span></span>

9.  <span data-ttu-id="82c8c-193">Fare clic su Crea.</span><span class="sxs-lookup"><span data-stu-id="82c8c-193">Click create.</span></span>

### <a name="deploy-using-group-policy"></a><span data-ttu-id="82c8c-194">Eseguire la distribuzione tramite Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="82c8c-194">Deploy using Group Policy</span></span>

<span data-ttu-id="82c8c-195">Se non si desidera usare Microsoft Endpoint Manager, è possibile usare i criteri di gruppo per distribuire l'estensione per la conformità Microsoft nell'intera organizzazione</span><span class="sxs-lookup"><span data-stu-id="82c8c-195">If you don't want to use Microsoft Endpoint Manager, you can use group policies to deploy the Microsoft Compliance Extension across your organization</span></span>

1. <span data-ttu-id="82c8c-196">I dispositivi devono essere gestibili tramite Criteri di gruppo e occorre importare tutti i file ADMX di Chrome nell'archivio centrale dei Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="82c8c-196">Your devices must be manageable via Group Policy, and you need to import all Chrome ADMXs into the Group Policy Central Store.</span></span> <span data-ttu-id="82c8c-197">Per altre informazioni, vedere [Come creare e gestire l'archivio centrale per i modelli amministrativi di Criteri di gruppo in Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span><span class="sxs-lookup"><span data-stu-id="82c8c-197">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span></span>

2.  <span data-ttu-id="82c8c-198">Creare uno script di PowerShell con il comando PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82c8c-198">Create a PowerShell script using this PowerShell command:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  <span data-ttu-id="82c8c-199">Aprire la **console di gestione di Criteri di gruppo** e passare all'unità organizzativa (OU).</span><span class="sxs-lookup"><span data-stu-id="82c8c-199">Open the **Group Policy Management Console** and navigate to your organizational unit (OU).</span></span>

4.  <span data-ttu-id="82c8c-200">Fare clic con il pulsante destro del mouse e selezionare **Crea oggetto Criteri di gruppo in questo dominio e collegalo qui**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-200">Right-click and select **Create a GPO in this domain and Link it here**.</span></span> <span data-ttu-id="82c8c-201">Quando viene richiesto, assegnare un nome descrittivo a questo oggetto Criteri di gruppo e completare la creazione.</span><span class="sxs-lookup"><span data-stu-id="82c8c-201">When prompted, assign a descriptive name to this group policy object (GPO) and finish creating it.</span></span>

5.  <span data-ttu-id="82c8c-202">Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-202">Right-click the GPO and select **Edit**.</span></span>

6.  <span data-ttu-id="82c8c-203">Passare a **Configurazione computer** > **Preferenze** > **Impostazioni Pannello di controllo** > **Attività pianificate**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-203">Go to **Computer Configuration** > **Preferences** > **Control Panel Settings** > **Scheduled Tasks**.</span></span>

7.  <span data-ttu-id="82c8c-204">Per creare una nuova attività immediata, selezionare tramite il pulsante destro del mouse **Nuova** > **Nuova attività immediata (in Windows 7)**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-204">Create a new immediate task by selecting right-clicking and selecting **New** > **Immediate Task (At least Windows 7)**.</span></span>

8.  <span data-ttu-id="82c8c-205">Assegnare un nome e una descrizione all'attività.</span><span class="sxs-lookup"><span data-stu-id="82c8c-205">Give the task a name & description.</span></span>

9.  <span data-ttu-id="82c8c-206">Scegliere l'account corrispondente per eseguire l'attività immediata, ad esempio NT Authority</span><span class="sxs-lookup"><span data-stu-id="82c8c-206">Choose the corresponding account to run the immediate task, for example NT Authority</span></span>

10. <span data-ttu-id="82c8c-207">Selezionare **Esegui con i privilegi più elevati**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-207">Select **Run with highest privileges**.</span></span>

11. <span data-ttu-id="82c8c-208">Configurare i criteri per Windows 10.</span><span class="sxs-lookup"><span data-stu-id="82c8c-208">Configure the policy for Windows 10.</span></span>

12. <span data-ttu-id="82c8c-209">Nella scheda **Azioni**, selezionare l'azione **Avvia un programma**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-209">In the **Actions** tab, select the action **Start a program**.</span></span>

13. <span data-ttu-id="82c8c-210">Immettere il percorso del programma o dello script creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="82c8c-210">Enter the path to the Program/Script created in Step 1.</span></span>

14. <span data-ttu-id="82c8c-211">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-211">Select **Apply**.</span></span>

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a><span data-ttu-id="82c8c-212">Aggiunta dell'estensione di Chrome all'elenco ForceInstall</span><span class="sxs-lookup"><span data-stu-id="82c8c-212">Adding the Chrome Extension to the ForceInstall List</span></span>

1.  <span data-ttu-id="82c8c-213">Nell'editor di gestione di Criteri di gruppo passare all'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="82c8c-213">In the Group Policy Management Editor, navigate to your OU.</span></span>

2.  <span data-ttu-id="82c8c-214">Espandere il percorso seguente **Configurazione computer/utente** > **Criteri** > **Modelli amministrativi** > **Modelli amministrativi classici** > **Google** > **Google Chrome** > **Estensioni**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-214">Expand the following path **Computer/User configuration** > **Policies** > **Administrative templates** > **Classic administrative templates** > **Google** > **Google Chrome** > **Extensions**.</span></span> <span data-ttu-id="82c8c-215">Questo percorso può variare a seconda della configurazione.</span><span class="sxs-lookup"><span data-stu-id="82c8c-215">This path may vary depending on your configuration.</span></span>

3.  <span data-ttu-id="82c8c-216">Selezionare **Configura l'elenco delle estensioni con installazione forzata**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-216">Select **Configure the list of force-installed extensions**.</span></span>

4.  <span data-ttu-id="82c8c-217">Fare clic con il pulsante destro del mouse e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-217">Right click and select **Edit**.</span></span>

5.  <span data-ttu-id="82c8c-218">Selezionare **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-218">Select **Enabled**.</span></span>

6.  <span data-ttu-id="82c8c-219">Selezionare **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-219">Select **Show**.</span></span>

7.  <span data-ttu-id="82c8c-220">In **Valore**, aggiungere la voce seguente: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span><span class="sxs-lookup"><span data-stu-id="82c8c-220">Under **Value**, add the following entry: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span></span>

8.  <span data-ttu-id="82c8c-221">Selezionare **OK**, poi **Applica**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-221">Select **OK** and then **Apply**.</span></span>

### <a name="test-the-extension"></a><span data-ttu-id="82c8c-222">Testare l'estensione</span><span class="sxs-lookup"><span data-stu-id="82c8c-222">Test the Extension</span></span>

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a><span data-ttu-id="82c8c-223">Caricare nel servizio cloud o accedere tramite browser non consentiti a Uscita cloud</span><span class="sxs-lookup"><span data-stu-id="82c8c-223">Upload to cloud service, or access by unallowed browsers Cloud Egress</span></span>  

1. <span data-ttu-id="82c8c-224">Creare o recuperare un elemento sensibile e provare a caricare un file in un dominio dei servizi con restrizioni dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="82c8c-224">Create or get a sensitive item and, try to upload a file to one of your organization’s restricted service domains.</span></span> <span data-ttu-id="82c8c-225">I dati riservati devono corrispondere a uno dei [tipi di informazioni sensibili](sensitive-information-type-entity-definitions.md) predefiniti o a uno dei tipi di informazioni sensibili dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="82c8c-225">The sensitive data must match one of our built-in [Sensitive Info Types](sensitive-information-type-entity-definitions.md), or one of your organization’s sensitive information types.</span></span> <span data-ttu-id="82c8c-226">Si dovrebbe ricevere una notifica di tipo avviso popup di DLP dal dispositivo che si sta testando, che informa che questa azione non è consentita quando il file è aperto.</span><span class="sxs-lookup"><span data-stu-id="82c8c-226">You should get a DLP toast notification on the device you are testing from that shows that this action is not allowed when the file is open.</span></span>

#### <a name="testing-other-dlp-scenarios-in-chrome"></a><span data-ttu-id="82c8c-227">Test di altri scenari di prevenzione della perdita dei dati in Chrome</span><span class="sxs-lookup"><span data-stu-id="82c8c-227">Testing other DLP scenarios in Chrome</span></span> 

<span data-ttu-id="82c8c-228">Dopo aver rimosso Chrome dall'elenco di browser o app non autorizzati, è possibile testare gli scenari seguenti per verificare che il comportamento soddisfi i requisiti dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="82c8c-228">Now that you’ve removed Chrome from the disallowed browsers/apps list, you can test the scenarios below to confirm the behavior meets your organization’s requirements:</span></span>

- <span data-ttu-id="82c8c-229">Copiare dati da un elemento sensibile a un altro documento tramite gli Appunti</span><span class="sxs-lookup"><span data-stu-id="82c8c-229">Copy data from a sensitive item to another document using the Clipboard</span></span>
    - <span data-ttu-id="82c8c-230">Per eseguire il test, aprire un file protetto da azioni di copia negli Appunti nel browser Chrome e provare a copiare i dati dal file.</span><span class="sxs-lookup"><span data-stu-id="82c8c-230">To test, open a file that is protected against copy to clipboard actions in the Chrome browser and attempt to copy data from the file.</span></span>
    - <span data-ttu-id="82c8c-231">Risultato previsto: notifica di avviso popup di DLP che comunica che questa azione non è consentita quando il file è aperto.</span><span class="sxs-lookup"><span data-stu-id="82c8c-231">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="82c8c-232">Stampa di un documento</span><span class="sxs-lookup"><span data-stu-id="82c8c-232">Print a document</span></span>
    - <span data-ttu-id="82c8c-233">Per eseguire il test, aprire un file protetto dalle azioni di stampa nel browser Chrome e provare a stampare il file.</span><span class="sxs-lookup"><span data-stu-id="82c8c-233">To test, open a file that is protected against print actions in the Chrome browser and attempt to print the file.</span></span>
    - <span data-ttu-id="82c8c-234">Risultato previsto: notifica di avviso popup di DLP che comunica che questa azione non è consentita quando il file è aperto.</span><span class="sxs-lookup"><span data-stu-id="82c8c-234">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="82c8c-235">Copia in supporti rimovibili USB</span><span class="sxs-lookup"><span data-stu-id="82c8c-235">Copy to USB Removeable Media</span></span>
    - <span data-ttu-id="82c8c-236">Per eseguire un test, provare a salvare il file in un archivio multimediale rimovibile.</span><span class="sxs-lookup"><span data-stu-id="82c8c-236">To test, try to save the file to a removeable media storage.</span></span>
    - <span data-ttu-id="82c8c-237">Risultato previsto: notifica di avviso popup di DLP che comunica che questa azione non è consentita quando il file è aperto.</span><span class="sxs-lookup"><span data-stu-id="82c8c-237">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="82c8c-238">Copia in condivisione di rete</span><span class="sxs-lookup"><span data-stu-id="82c8c-238">Copy to Network Share</span></span>
    - <span data-ttu-id="82c8c-239">Per eseguire un test, provare a salvare il file in una condivisione di rete.</span><span class="sxs-lookup"><span data-stu-id="82c8c-239">To test, try to save the file to a network share.</span></span>
    - <span data-ttu-id="82c8c-240">Risultato previsto: notifica di avviso popup di DLP che comunica che questa azione non è consentita quando il file è aperto.</span><span class="sxs-lookup"><span data-stu-id="82c8c-240">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a><span data-ttu-id="82c8c-241">Usare il dashboard di gestione degli avvisi per visualizzare gli avvisi di DLP di Chrome</span><span class="sxs-lookup"><span data-stu-id="82c8c-241">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>

1. <span data-ttu-id="82c8c-242">Aprire la pagina di **Prevenzione della perdita dei dati** nel **Centro conformità Microsoft 365** e scegliere [Avvisi](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="82c8c-242">Open the **Data loss prevention** page in the [Microsoft 365 Compliance center](https://compliance.microsoft.com) and select **Alerts**.</span></span>

2. <span data-ttu-id="82c8c-243">Fare riferimento alle procedure in [Come configurare e visualizzare gli avvisi per i criteri di prevenzione della perdita dei dati](dlp-configure-view-alerts-policies.md) per visualizzare gli avvisi per i criteri di prevenzione della perdita dei dati degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="82c8c-243">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a><span data-ttu-id="82c8c-244">Visualizzazione dei dati DLP di Chrome in Esplora attività</span><span class="sxs-lookup"><span data-stu-id="82c8c-244">Viewing Chrome DLP data in activity explorer</span></span>

1. <span data-ttu-id="82c8c-245">Aprire la [pagina Classificazione dei dati](https://compliance.microsoft.com/dataclassification?viewid=overview) per il dominio nel Centro conformità Microsoft 365 e scegliere **Esplora attività**.</span><span class="sxs-lookup"><span data-stu-id="82c8c-245">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose **Activity explorer**.</span></span>

2. <span data-ttu-id="82c8c-246">Vedere le procedure in [Introduzione a Esplora attività](data-classification-activity-explorer.md) per accedere a tutti i dati relativi ai dispositivi endpoint e filtrarli.</span><span class="sxs-lookup"><span data-stu-id="82c8c-246">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="82c8c-247">![filtro di Esplora attività per i dispositivi endpoint](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="82c8c-247">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

### <a name="known-issues-and-limitations"></a><span data-ttu-id="82c8c-248">Problemi noti e limitazioni</span><span class="sxs-lookup"><span data-stu-id="82c8c-248">Known Issues and Limitations</span></span>

1. <span data-ttu-id="82c8c-249">L'imposizione del blocco override per l’uscita dal cloud non è supportata.</span><span class="sxs-lookup"><span data-stu-id="82c8c-249">Block Override enforcement for cloud egress is not supported.</span></span>
2. <span data-ttu-id="82c8c-250">La modalità Incognito non è supportata e deve essere disabilitata.</span><span class="sxs-lookup"><span data-stu-id="82c8c-250">Incognito mode is not supported and must be disabled.</span></span>

## <a name="next-steps"></a><span data-ttu-id="82c8c-251">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="82c8c-251">Next steps</span></span>
<span data-ttu-id="82c8c-252">Ora che si è eseguito l'onboarding dei dispositivi e che è possibile visualizzare i dati sulle attività in Esplora attività, è possibile procedere con il passaggio successivo, in cui si creano criteri di prevenzione della perdita dei dati per proteggere gli elementi sensibili.</span><span class="sxs-lookup"><span data-stu-id="82c8c-252">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="82c8c-253">Uso di Prevenzione della perdita di dati degli endpoint</span><span class="sxs-lookup"><span data-stu-id="82c8c-253">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="82c8c-254">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82c8c-254">See also</span></span>

- [<span data-ttu-id="82c8c-255">Informazioni sulla prevenzione della perdita di dati degli endpoint </span><span class="sxs-lookup"><span data-stu-id="82c8c-255">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="82c8c-256">Uso della Prevenzione della perdita di dati degli endpoint </span><span class="sxs-lookup"><span data-stu-id="82c8c-256">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="82c8c-257">Informazioni sulla prevenzione della perdita di dati</span><span class="sxs-lookup"><span data-stu-id="82c8c-257">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="82c8c-258">Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="82c8c-258">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="82c8c-259">Introduzione a Esplora attività</span><span class="sxs-lookup"><span data-stu-id="82c8c-259">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="82c8c-260">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="82c8c-260">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="82c8c-261">Strumenti e metodi di onboarding per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="82c8c-261">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="82c8c-262">Abbonamento a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="82c8c-262">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="82c8c-263">Dispositivi aggiunti ad Azure AD</span><span class="sxs-lookup"><span data-stu-id="82c8c-263">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="82c8c-264">Scaricare il nuovo Microsoft Edge basato su Chromium</span><span class="sxs-lookup"><span data-stu-id="82c8c-264">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
