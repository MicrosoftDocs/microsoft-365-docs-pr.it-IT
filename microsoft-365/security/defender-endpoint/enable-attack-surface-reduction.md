---
title: Abilitare regole per la riduzione della superficie di attacco
description: Abilita le regole di riduzione della superficie di attacco (ASR) per proteggere i dispositivi da attacchi che usano macro, script e tecniche di inserimento comuni.
keywords: Riduzione della superficie di attacco, fianchi, sistema di prevenzione delle intrusioni host, regole di protezione, anti-exploit, antiexploit, exploit, prevenzione delle infezioni, abilitare, attivare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: df77a3d6c1f66882600a200b83b3b2585473f42b
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995070"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="2ff20-104">Abilitare regole per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="2ff20-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2ff20-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="2ff20-105">**Applies to:**</span></span>
- [<span data-ttu-id="2ff20-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="2ff20-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2ff20-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2ff20-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="2ff20-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="2ff20-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2ff20-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="2ff20-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="2ff20-110">[Le regole di riduzione della superficie](attack-surface-reduction.md) di attacco (regole ASR) consentono di impedire azioni che il malware spesso abuso per compromettere dispositivi e reti.</span><span class="sxs-lookup"><span data-stu-id="2ff20-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

<span data-ttu-id="2ff20-111">**Requisiti** Puoi impostare regole di riduzione della superficie di attacco per i dispositivi che eseguono una delle seguenti edizioni e versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="2ff20-111">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="2ff20-112">Windows 10 Pro, [versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) o successiva</span><span class="sxs-lookup"><span data-stu-id="2ff20-112">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="2ff20-113">Windows 10 Enterprise, [versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) o successiva</span><span class="sxs-lookup"><span data-stu-id="2ff20-113">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="2ff20-114">Windows Server, [versione 1803 (Canale semestraale)](/windows-server/get-started/whats-new-in-windows-server-1803) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="2ff20-114">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="2ff20-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="2ff20-115">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="2ff20-116">Anche se le regole di riduzione della superficie di attacco non richiedono una licenza di [Windows E5,](/windows/deployment/deploy-enterprise-licenses)se si dispone di Windows E5, si ottengono funzionalità di gestione avanzate.</span><span class="sxs-lookup"><span data-stu-id="2ff20-116">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="2ff20-117">Queste funzionalità disponibili solo in Windows E5 includono monitoraggio, analisi e flussi di lavoro disponibili in [Defender for Endpoint,](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true)nonché funzionalità di creazione di report e configurazione nel Centro sicurezza [Microsoft 365.](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="2ff20-117">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true), as well as reporting and configuration capabilities in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true).</span></span> <span data-ttu-id="2ff20-118">Queste funzionalità avanzate non sono disponibili con una licenza di Windows Professional o Windows E3. Tuttavia, se hai queste licenze, puoi usare il Visualizzatore eventi e i registri di Microsoft Defender Antivirus per esaminare gli eventi delle regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="2ff20-118">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="2ff20-119">Ogni regola asr contiene una delle quattro impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ff20-119">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="2ff20-120">**Non configurato**: disabilita la regola asr</span><span class="sxs-lookup"><span data-stu-id="2ff20-120">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="2ff20-121">**Block**: Enable the ASR rule</span><span class="sxs-lookup"><span data-stu-id="2ff20-121">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="2ff20-122">**Controllo**: valutare l'impatto della regola asr sull'organizzazione se abilitata</span><span class="sxs-lookup"><span data-stu-id="2ff20-122">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="2ff20-123">**Avviso:** abilitare la regola asr ma consentire all'utente finale di ignorare il blocco</span><span class="sxs-lookup"><span data-stu-id="2ff20-123">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ff20-124">Attualmente, la modalità avviso non è supportata per tre regole asr quando si configurano le regole asr in Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="2ff20-124">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="2ff20-125">Per altre informazioni, vedi [Casi in cui la modalità avviso non è supportata.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)</span><span class="sxs-lookup"><span data-stu-id="2ff20-125">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="2ff20-126">È consigliabile usare le regole asr con una licenza di Windows E5 (o una SKU di licenza simile) per sfruttare le funzionalità avanzate di monitoraggio e creazione di report disponibili in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span><span class="sxs-lookup"><span data-stu-id="2ff20-126">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="2ff20-127">Tuttavia, per altre licenze come Windows Professional o E3 che non hanno accesso alle funzionalità avanzate di monitoraggio e creazione di report, è possibile sviluppare strumenti di monitoraggio e creazione di report personalizzati oltre agli eventi generati in ogni endpoint quando vengono attivate le regole di registrazione asr (ad esempio, Inoltro eventi).</span><span class="sxs-lookup"><span data-stu-id="2ff20-127">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="2ff20-128">Per altre informazioni sulle licenze di Windows, vedi [Licenze di Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) e ottieni la guida per i [contratti multilicenza per Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)</span><span class="sxs-lookup"><span data-stu-id="2ff20-128">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="2ff20-129">Puoi abilitare le regole di riduzione della superficie di attacco usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2ff20-129">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="2ff20-130">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2ff20-130">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="2ff20-131">Gestione di dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="2ff20-131">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="2ff20-132">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2ff20-132">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="2ff20-133">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="2ff20-133">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="2ff20-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ff20-134">PowerShell</span></span>](#powershell)

<span data-ttu-id="2ff20-135">È consigliabile gestire a livello aziendale, ad esempio Intune o Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="2ff20-135">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="2ff20-136">La gestione a livello aziendale sovrascriverà tutte le impostazioni di Criteri di gruppo o PowerShell in conflitto all'avvio.</span><span class="sxs-lookup"><span data-stu-id="2ff20-136">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="2ff20-137">Escludere file e cartelle dalle regole asr</span><span class="sxs-lookup"><span data-stu-id="2ff20-137">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="2ff20-138">È possibile escludere file e cartelle dalla maggior parte delle regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="2ff20-138">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="2ff20-139">Ciò significa che, anche se una regola asr determina che il file o la cartella contiene comportamenti dannosi, non blocchi l'esecuzione del file.</span><span class="sxs-lookup"><span data-stu-id="2ff20-139">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="2ff20-140">Ciò potrebbe potenzialmente consentire l'esecuzione di file non sicuri e infettare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="2ff20-140">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="2ff20-141">Puoi anche escludere le regole asr dall'attivazione in base agli hash di certificati e file consentendo a Defender per gli indicatori di certificato e file dell'endpoint specificati.</span><span class="sxs-lookup"><span data-stu-id="2ff20-141">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="2ff20-142">(Vedere [Gestire gli indicatori](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span><span class="sxs-lookup"><span data-stu-id="2ff20-142">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2ff20-143">L'esclusione di file o cartelle può ridurre notevolmente la protezione fornita dalle regole asr.</span><span class="sxs-lookup"><span data-stu-id="2ff20-143">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="2ff20-144">L'esecuzione dei file esclusi sarà consentita e non verrà registrato alcun report o evento.</span><span class="sxs-lookup"><span data-stu-id="2ff20-144">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="2ff20-145">Se le regole di ripristino automatico rilevano file che ritieni non debbano essere rilevati, devi prima usare la modalità di controllo per [testare la regola.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="2ff20-145">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="2ff20-146">È possibile specificare singoli file o cartelle (utilizzando percorsi di cartelle o nomi di risorse completi), ma non è possibile specificare le regole a cui si applicano le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="2ff20-146">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="2ff20-147">Un'esclusione viene applicata solo all'avvio dell'applicazione o del servizio escluso.</span><span class="sxs-lookup"><span data-stu-id="2ff20-147">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="2ff20-148">Ad esempio, se si aggiunge un'esclusione per un servizio di aggiornamento già in esecuzione, il servizio di aggiornamento continuerà a attivare eventi finché il servizio non viene arrestato e riavviato.</span><span class="sxs-lookup"><span data-stu-id="2ff20-148">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="2ff20-149">Le regole asr supportano variabili di ambiente e caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="2ff20-149">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="2ff20-150">Per informazioni sull'utilizzo dei caratteri jolly, vedere [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span><span class="sxs-lookup"><span data-stu-id="2ff20-150">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="2ff20-151">Le procedure seguenti per l'abilitazione delle regole asr includono istruzioni su come escludere file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="2ff20-151">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="2ff20-152">Intune</span><span class="sxs-lookup"><span data-stu-id="2ff20-152">Intune</span></span>

1. <span data-ttu-id="2ff20-153">Selezionare **Profili di configurazione** del  >  **dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="2ff20-153">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="2ff20-154">Scegliere un profilo di endpoint protection esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="2ff20-154">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="2ff20-155">Per crearne uno nuovo, selezionare **Crea profilo** e immettere le informazioni per il profilo.</span><span class="sxs-lookup"><span data-stu-id="2ff20-155">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="2ff20-156">Per **Tipo di profilo** selezionare Endpoint **protection.**</span><span class="sxs-lookup"><span data-stu-id="2ff20-156">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="2ff20-157">Se è stato scelto un profilo esistente, selezionare **Proprietà** e quindi **Impostazioni.**</span><span class="sxs-lookup"><span data-stu-id="2ff20-157">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="2ff20-158">Nel riquadro **Endpoint protection** seleziona Windows Defender **Exploit Guard** e quindi seleziona Riduzione della superficie **di attacco.**</span><span class="sxs-lookup"><span data-stu-id="2ff20-158">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="2ff20-159">Selezionare l'impostazione desiderata per ogni regola asr.</span><span class="sxs-lookup"><span data-stu-id="2ff20-159">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="2ff20-160">In **Eccezioni di riduzione della superficie di attacco** immetti singoli file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="2ff20-160">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="2ff20-161">È inoltre possibile selezionare **Importa per** importare un file CSV contenente file e cartelle da escludere dalle regole asr.</span><span class="sxs-lookup"><span data-stu-id="2ff20-161">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="2ff20-162">Ogni riga del file CSV deve essere formattata come segue:</span><span class="sxs-lookup"><span data-stu-id="2ff20-162">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="2ff20-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="2ff20-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="2ff20-164">Selezionare **OK** nei tre riquadri di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2ff20-164">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="2ff20-165">Seleziona Quindi **Crea** se stai creando un nuovo file di endpoint protection o **Salva** se ne stai modificando uno esistente.</span><span class="sxs-lookup"><span data-stu-id="2ff20-165">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="2ff20-166">MDM</span><span class="sxs-lookup"><span data-stu-id="2ff20-166">MDM</span></span>

<span data-ttu-id="2ff20-167">Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) per abilitare e impostare singolarmente la modalità per ogni regola.</span><span class="sxs-lookup"><span data-stu-id="2ff20-167">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="2ff20-168">Di seguito è riportato un esempio di riferimento, utilizzando [i valori GUID per le regole asr.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="2ff20-168">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="2ff20-169">I valori da abilitare (blocca), disabilitare, avvisare o abilitare in modalità di controllo sono:</span><span class="sxs-lookup"><span data-stu-id="2ff20-169">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="2ff20-170">0 : Disable (Disable the ASR rule)</span><span class="sxs-lookup"><span data-stu-id="2ff20-170">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="2ff20-171">1 : Blocca (abilita la regola asr)</span><span class="sxs-lookup"><span data-stu-id="2ff20-171">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="2ff20-172">2 : Controllo (valutare l'impatto della regola asr sull'organizzazione se abilitata)</span><span class="sxs-lookup"><span data-stu-id="2ff20-172">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="2ff20-173">6 : avvisa (abilita la regola asr ma consenti all'utente finale di ignorare il blocco).</span><span class="sxs-lookup"><span data-stu-id="2ff20-173">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="2ff20-174">La modalità avviso è ora disponibile per la maggior parte delle regole asr.</span><span class="sxs-lookup"><span data-stu-id="2ff20-174">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="2ff20-175">Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) per aggiungere esclusioni.</span><span class="sxs-lookup"><span data-stu-id="2ff20-175">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="2ff20-176">Esempio:</span><span class="sxs-lookup"><span data-stu-id="2ff20-176">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="2ff20-177">Assicurati di immettere valori URI OMA senza spazi.</span><span class="sxs-lookup"><span data-stu-id="2ff20-177">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="2ff20-178">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2ff20-178">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="2ff20-179">In Microsoft Endpoint Configuration Manager, vai a **Assets and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="2ff20-179">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="2ff20-180">Selezionare **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="2ff20-180">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="2ff20-181">Immetti un nome e una descrizione, seleziona **Riduzione superficie di attacco** e seleziona **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="2ff20-181">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="2ff20-182">Scegliere le regole che verranno bloccate o le azioni di controllo e selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="2ff20-182">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="2ff20-183">Rivedere le impostazioni e selezionare **Avanti** per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="2ff20-183">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="2ff20-184">Dopo la creazione del criterio, **chiudere**.</span><span class="sxs-lookup"><span data-stu-id="2ff20-184">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="2ff20-185">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="2ff20-185">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="2ff20-186">Se gestisci i computer e i dispositivi con Intune, Configuration Manager o un'altra piattaforma di gestione a livello aziendale, il software di gestione sovrascriverà tutte le impostazioni di Criteri di gruppo in conflitto all'avvio.</span><span class="sxs-lookup"><span data-stu-id="2ff20-186">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="2ff20-187">Nel computer di gestione di Criteri di gruppo aprire Console Gestione Criteri di [gruppo,](https://technet.microsoft.com/library/cc731212.aspx)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="2ff20-187">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="2ff20-188">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="2ff20-188">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="2ff20-189">Espandi l'albero fino ai **componenti di Windows** Microsoft Defender  >  **Antivirus** Microsoft Defender Exploit Guard Riduzione della  >  **superficie**  >  **di attacco.**</span><span class="sxs-lookup"><span data-stu-id="2ff20-189">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="2ff20-190">Selezionare **Configura regole di riduzione della superficie di attacco** e selezionare **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="2ff20-190">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="2ff20-191">È quindi possibile impostare il singolo stato per ogni regola nella sezione opzioni.</span><span class="sxs-lookup"><span data-stu-id="2ff20-191">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="2ff20-192">Selezionare **Mostra...** e immettere l'ID regola nella colonna **Nome valore** e lo stato scelto nella colonna **Valore** come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2ff20-192">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="2ff20-193">0 : Disable (Disable the ASR rule)</span><span class="sxs-lookup"><span data-stu-id="2ff20-193">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="2ff20-194">1 : Blocca (abilita la regola asr)</span><span class="sxs-lookup"><span data-stu-id="2ff20-194">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="2ff20-195">2 : Controllo (valutare l'impatto della regola asr sull'organizzazione se abilitata)</span><span class="sxs-lookup"><span data-stu-id="2ff20-195">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="2ff20-196">6 : Avvisa (abilita la regola di registrazione asr ma consenti all'utente finale di ignorare il blocco)</span><span class="sxs-lookup"><span data-stu-id="2ff20-196">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="Regole asr in Criteri di gruppo":::

5. <span data-ttu-id="2ff20-198">Per escludere file e cartelle dalle  regole asr, selezionare l'impostazione Escludi file e percorsi dalle regole di riduzione della superficie di attacco e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="2ff20-198">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="2ff20-199">Selezionare **Mostra** e immettere ogni file o cartella nella **colonna Nome** valore.</span><span class="sxs-lookup"><span data-stu-id="2ff20-199">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="2ff20-200">Immettere **0** nella **colonna Valore** per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="2ff20-200">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="2ff20-201">Non utilizzare le virgolette perché non sono supportate per la colonna **Nome valore** o **Valore.**</span><span class="sxs-lookup"><span data-stu-id="2ff20-201">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="2ff20-202">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ff20-202">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="2ff20-203">Se gestisci i computer e i dispositivi con Intune, Configuration Manager o un'altra piattaforma di gestione a livello aziendale, il software di gestione sovrascriverà tutte le impostazioni di PowerShell in conflitto all'avvio.</span><span class="sxs-lookup"><span data-stu-id="2ff20-203">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="2ff20-204">Per consentire agli utenti di definire il valore tramite PowerShell, utilizzare l'opzione "Definito dall'utente" per la regola nella piattaforma di gestione.</span><span class="sxs-lookup"><span data-stu-id="2ff20-204">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="2ff20-205">Digita **powershell** nel menu Start, fai clic con il pulsante destro **del** mouse Windows PowerShell e scegli Esegui **come amministratore.**</span><span class="sxs-lookup"><span data-stu-id="2ff20-205">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="2ff20-206">Digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2ff20-206">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="2ff20-207">Per abilitare le regole di registrazione asr in modalità di controllo, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2ff20-207">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="2ff20-208">Per abilitare le regole di Registrazione asr in modalità avviso, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2ff20-208">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="2ff20-209">Per disattivare le regole asr, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2ff20-209">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="2ff20-210">È necessario specificare lo stato singolarmente per ogni regola, ma è possibile combinare regole e stati in un elenco delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="2ff20-210">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="2ff20-211">Nell'esempio seguente verranno abilitate le prime due regole, la terza verrà disabilitata e la quarta verrà abilitata in modalità di controllo:</span><span class="sxs-lookup"><span data-stu-id="2ff20-211">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="2ff20-212">È inoltre possibile utilizzare il `Add-MpPreference` verbo PowerShell per aggiungere nuove regole all'elenco esistente.</span><span class="sxs-lookup"><span data-stu-id="2ff20-212">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="2ff20-213">`Set-MpPreference` sovrascriverà sempre il set di regole esistente.</span><span class="sxs-lookup"><span data-stu-id="2ff20-213">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="2ff20-214">Se vuoi aggiungerlo al set esistente, usa `Add-MpPreference` invece.</span><span class="sxs-lookup"><span data-stu-id="2ff20-214">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="2ff20-215">È possibile ottenere un elenco di regole e il relativo stato corrente utilizzando `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="2ff20-215">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="2ff20-216">Per escludere file e cartelle dalle regole asr, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2ff20-216">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="2ff20-217">Continuare a utilizzare `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` per aggiungere altri file e cartelle all'elenco.</span><span class="sxs-lookup"><span data-stu-id="2ff20-217">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2ff20-218">Usa `Add-MpPreference` per aggiungere o aggiungere app all'elenco.</span><span class="sxs-lookup"><span data-stu-id="2ff20-218">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="2ff20-219">`Set-MpPreference`L'utilizzo del cmdlet sovrascriverà l'elenco esistente.</span><span class="sxs-lookup"><span data-stu-id="2ff20-219">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2ff20-220">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="2ff20-220">Related articles</span></span>

- [<span data-ttu-id="2ff20-221">Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="2ff20-221">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="2ff20-222">Valutare la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="2ff20-222">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="2ff20-223">FAQ per la riduzione della superficie d'attacco</span><span class="sxs-lookup"><span data-stu-id="2ff20-223">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
