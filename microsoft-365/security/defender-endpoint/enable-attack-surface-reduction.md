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
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.date: 06/02/2021
ms.openlocfilehash: eb4819a1dfad5ce94722d3cb283471a52808a4a7
ms.sourcegitcommit: 5866e45a6a4e90c661e8f90c91550a9872b68e03
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/28/2021
ms.locfileid: "53169605"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="42a57-104">Abilitare regole per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="42a57-104">Enable attack surface reduction rules</span></span>

<span data-ttu-id="42a57-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="42a57-105">**Applies to:**</span></span>

- [<span data-ttu-id="42a57-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="42a57-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="42a57-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42a57-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="42a57-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="42a57-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="42a57-109">[Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="42a57-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="42a57-110">[Le regole di riduzione della superficie](attack-surface-reduction.md) di attacco (regole ASR) consentono di impedire azioni che il malware spesso abuso per compromettere dispositivi e reti.</span><span class="sxs-lookup"><span data-stu-id="42a57-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

## <a name="requirements"></a><span data-ttu-id="42a57-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42a57-111">Requirements</span></span>

<span data-ttu-id="42a57-112">Puoi impostare regole di riduzione della superficie di attacco per i dispositivi che eseguono una delle seguenti edizioni e versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="42a57-112">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="42a57-113">Windows 10 Pro versione [1709](/windows/whats-new/whats-new-windows-10-version-1709) o successiva</span><span class="sxs-lookup"><span data-stu-id="42a57-113">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="42a57-114">Windows 10 Enterprise versione [1709](/windows/whats-new/whats-new-windows-10-version-1709) o successiva</span><span class="sxs-lookup"><span data-stu-id="42a57-114">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="42a57-115">Windows Server, [versione 1803 (Canale semestraale)](/windows-server/get-started/whats-new-in-windows-server-1803) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="42a57-115">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="42a57-116">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="42a57-116">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="42a57-117">Anche se le regole di riduzione della superficie di attacco non richiedono una licenza [Windows E5,](/windows/deployment/deploy-enterprise-licenses)se si dispone di Windows E5, si ottengono funzionalità di gestione avanzate.</span><span class="sxs-lookup"><span data-stu-id="42a57-117">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="42a57-118">Queste funzionalità disponibili solo in Windows E5 includono monitoraggio, analisi e flussi di lavoro disponibili in [Defender for Endpoint,](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true)nonché funzionalità di creazione di report e configurazione nel centro sicurezza [Microsoft 365.](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="42a57-118">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true), as well as reporting and configuration capabilities in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true).</span></span> <span data-ttu-id="42a57-119">Queste funzionalità avanzate non sono disponibili con una licenza Windows Professional o Windows E3. Tuttavia, se si dispone di tali licenze, è possibile utilizzare visualizzatore eventi e registri Antivirus Microsoft Defender per esaminare gli eventi delle regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="42a57-119">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="42a57-120">Ogni regola asr contiene una delle quattro impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42a57-120">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="42a57-121">**Non configurato**: disabilita la regola asr</span><span class="sxs-lookup"><span data-stu-id="42a57-121">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="42a57-122">**Block**: Enable the ASR rule</span><span class="sxs-lookup"><span data-stu-id="42a57-122">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="42a57-123">**Controllo**: valutare l'impatto della regola asr sull'organizzazione se abilitata</span><span class="sxs-lookup"><span data-stu-id="42a57-123">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="42a57-124">**Avviso:** abilitare la regola asr ma consentire all'utente finale di ignorare il blocco</span><span class="sxs-lookup"><span data-stu-id="42a57-124">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42a57-125">Attualmente, la modalità avviso non è supportata per tre regole asr quando si configurano le regole di ripristino asr in Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="42a57-125">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="42a57-126">Per altre informazioni, vedi [Casi in cui la modalità avviso non è supportata.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)</span><span class="sxs-lookup"><span data-stu-id="42a57-126">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="42a57-127">È consigliabile usare le regole asr con una licenza di Windows E5 (o una SKU di licenza simile) per sfruttare le funzionalità avanzate di monitoraggio e creazione di report disponibili in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span><span class="sxs-lookup"><span data-stu-id="42a57-127">It's highly recommended to use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span></span> <span data-ttu-id="42a57-128">Tuttavia, se si dispone di un'altra licenza, ad esempio Windows Professional o Windows E3 che non include funzionalità avanzate di monitoraggio e creazione di report, è possibile sviluppare strumenti di monitoraggio e creazione di report personalizzati oltre agli eventi generati in ogni endpoint quando vengono attivate le regole asr (ad esempio, Inoltro eventi).</span><span class="sxs-lookup"><span data-stu-id="42a57-128">However, if you have another license, such as Windows Professional or Windows E3 that don't include advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (for example, Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="42a57-129">Per ulteriori informazioni sulle licenze Windows, vedere [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) e ottenere la guida per contratti [multilicenza per Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="42a57-129">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="42a57-130">Puoi abilitare le regole di riduzione della superficie di attacco usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="42a57-130">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="42a57-131">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="42a57-131">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="42a57-132">Gestione di dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="42a57-132">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="42a57-133">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="42a57-133">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="42a57-134">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="42a57-134">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="42a57-135">PowerShell</span><span class="sxs-lookup"><span data-stu-id="42a57-135">PowerShell</span></span>](#powershell)

<span data-ttu-id="42a57-136">Enterprise è consigliata la gestione a livello di Microsoft Endpoint Manager, ad esempio Intune.</span><span class="sxs-lookup"><span data-stu-id="42a57-136">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="42a57-137">Enterprise gestione a livello di utente sovrascriverà tutte le impostazioni di Criteri di gruppo o PowerShell in conflitto all'avvio.</span><span class="sxs-lookup"><span data-stu-id="42a57-137">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="42a57-138">Escludere file e cartelle dalle regole asr</span><span class="sxs-lookup"><span data-stu-id="42a57-138">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="42a57-139">È possibile escludere file e cartelle dalla maggior parte delle regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="42a57-139">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="42a57-140">Ciò significa che, anche se una regola asr determina che il file o la cartella contiene comportamenti dannosi, non blocchi l'esecuzione del file.</span><span class="sxs-lookup"><span data-stu-id="42a57-140">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="42a57-141">Ciò potrebbe potenzialmente consentire l'esecuzione di file non sicuri e infettare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="42a57-141">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="42a57-142">Puoi anche escludere le regole asr dall'attivazione in base agli hash di certificati e file consentendo a Defender per gli indicatori di certificato e file dell'endpoint specificati.</span><span class="sxs-lookup"><span data-stu-id="42a57-142">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="42a57-143">(Vedere [Gestire gli indicatori](manage-indicators.md).)</span><span class="sxs-lookup"><span data-stu-id="42a57-143">(See [Manage indicators](manage-indicators.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42a57-144">L'esclusione di file o cartelle può ridurre notevolmente la protezione fornita dalle regole asr.</span><span class="sxs-lookup"><span data-stu-id="42a57-144">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="42a57-145">L'esecuzione dei file esclusi sarà consentita e non verrà registrato alcun report o evento.</span><span class="sxs-lookup"><span data-stu-id="42a57-145">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="42a57-146">Se le regole di ripristino automatico rilevano file che ritieni non debbano essere rilevati, devi prima usare la modalità di controllo per [testare la regola.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="42a57-146">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="42a57-147">È possibile specificare singoli file o cartelle (utilizzando percorsi di cartelle o nomi di risorse completi), ma non è possibile specificare le regole a cui si applicano le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="42a57-147">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="42a57-148">Un'esclusione viene applicata solo all'avvio dell'applicazione o del servizio escluso.</span><span class="sxs-lookup"><span data-stu-id="42a57-148">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="42a57-149">Ad esempio, se si aggiunge un'esclusione per un servizio di aggiornamento già in esecuzione, il servizio di aggiornamento continuerà a attivare eventi finché il servizio non viene arrestato e riavviato.</span><span class="sxs-lookup"><span data-stu-id="42a57-149">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="42a57-150">Le regole asr supportano variabili di ambiente e caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="42a57-150">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="42a57-151">Per informazioni sull'utilizzo dei caratteri jolly, vedere [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span><span class="sxs-lookup"><span data-stu-id="42a57-151">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="42a57-152">Le procedure seguenti per l'abilitazione delle regole asr includono istruzioni su come escludere file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="42a57-152">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="42a57-153">Intune</span><span class="sxs-lookup"><span data-stu-id="42a57-153">Intune</span></span>

1. <span data-ttu-id="42a57-154">Selezionare **Profili di configurazione** del  >  **dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="42a57-154">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="42a57-155">Scegliere un profilo di endpoint protection esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="42a57-155">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="42a57-156">Per crearne uno nuovo, selezionare **Crea profilo** e immettere le informazioni per il profilo.</span><span class="sxs-lookup"><span data-stu-id="42a57-156">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="42a57-157">Per **Tipo di profilo** selezionare Endpoint **protection.**</span><span class="sxs-lookup"><span data-stu-id="42a57-157">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="42a57-158">Se è stato scelto un profilo esistente, selezionare **Proprietà** e quindi selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="42a57-158">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="42a57-159">Nel riquadro **Endpoint protection** seleziona Windows Defender **Exploit Guard,** quindi seleziona **Riduzione della superficie di attacco.**</span><span class="sxs-lookup"><span data-stu-id="42a57-159">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="42a57-160">Selezionare l'impostazione desiderata per ogni regola asr.</span><span class="sxs-lookup"><span data-stu-id="42a57-160">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="42a57-161">In **Eccezioni di riduzione della superficie di attacco** immetti singoli file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="42a57-161">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="42a57-162">È inoltre possibile selezionare **Importa per** importare un file CSV contenente file e cartelle da escludere dalle regole asr.</span><span class="sxs-lookup"><span data-stu-id="42a57-162">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="42a57-163">Ogni riga del file CSV deve essere formattata come segue:</span><span class="sxs-lookup"><span data-stu-id="42a57-163">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="42a57-164">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="42a57-164">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="42a57-165">Selezionare **OK** nei tre riquadri di configurazione.</span><span class="sxs-lookup"><span data-stu-id="42a57-165">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="42a57-166">Seleziona Quindi **Crea** se stai creando un nuovo file di endpoint protection o **Salva** se ne stai modificando uno esistente.</span><span class="sxs-lookup"><span data-stu-id="42a57-166">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mem"></a><span data-ttu-id="42a57-167">MEM</span><span class="sxs-lookup"><span data-stu-id="42a57-167">MEM</span></span>

<span data-ttu-id="42a57-168">Puoi usare l'URI OMA Microsoft Endpoint Manager (MEM) per configurare regole asr personalizzate.</span><span class="sxs-lookup"><span data-stu-id="42a57-168">You can use Microsoft Endpoint Manager (MEM) OMA-URI to configure custom ASR rules.</span></span> <span data-ttu-id="42a57-169">Nella procedura seguente viene utilizzata la regola [Bloccare l'abuso di](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) driver firmati vulnerabili sfruttati per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="42a57-169">The following procedure uses the rule [Block abuse of exploited vulnerable signed drivers](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) for the example.</span></span>

1. <span data-ttu-id="42a57-170">Aprire l'Microsoft Endpoint Manager di amministrazione (MEM).</span><span class="sxs-lookup"><span data-stu-id="42a57-170">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="42a57-171">Nel menu **Home** fare clic su **Dispositivi,** selezionare **Profilo di configurazione** e quindi fare clic su Crea **profilo.**</span><span class="sxs-lookup"><span data-stu-id="42a57-171">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42a57-172">![MEM Create Profile](images/mem01-create-profile.png)</span><span class="sxs-lookup"><span data-stu-id="42a57-172">![MEM Create Profile](images/mem01-create-profile.png)</span></span>

2. <span data-ttu-id="42a57-173">In **Crea profilo** selezionare quanto segue nei due elenchi a discesa seguenti:</span><span class="sxs-lookup"><span data-stu-id="42a57-173">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="42a57-174">In **Piattaforma** selezionare Windows 10 **e versioni successive**</span><span class="sxs-lookup"><span data-stu-id="42a57-174">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="42a57-175">In **Tipo di profilo** selezionare **Modelli**</span><span class="sxs-lookup"><span data-stu-id="42a57-175">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="42a57-176">Selezionare **Personalizzato** e quindi fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="42a57-176">Select **Custom**, and then click **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42a57-177">![Attributi del profilo delle regole MEM](images/mem02-profile-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="42a57-177">![MEM rule profile attributes](images/mem02-profile-attributes.png)</span></span>

3. <span data-ttu-id="42a57-178">Lo strumento Modello personalizzato viene aperto al **passaggio 1 Nozioni di base.**</span><span class="sxs-lookup"><span data-stu-id="42a57-178">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="42a57-179">In **1 Nozioni di** base, in **Nome** digitare un nome per il modello e **in** Descrizione è possibile digitare una descrizione (facoltativa).</span><span class="sxs-lookup"><span data-stu-id="42a57-179">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type a description (optional).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42a57-180">![Attributi di base MEM](images/mem03-1-basics.png)</span><span class="sxs-lookup"><span data-stu-id="42a57-180">![MEM basic attributes](images/mem03-1-basics.png)</span></span>

4. <span data-ttu-id="42a57-181">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="42a57-181">Click **Next**.</span></span> <span data-ttu-id="42a57-182">Step **2 Configuration settings opens.**</span><span class="sxs-lookup"><span data-stu-id="42a57-182">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="42a57-183">Per l'URI OMA Impostazioni, fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="42a57-183">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="42a57-184">Vengono ora visualizzate due opzioni: **Aggiungi** ed **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="42a57-184">Two options now appear: **Add** and **Export**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42a57-185">![Impostazioni di configurazione MEM](images/mem04-2-configuration-settings.png)</span><span class="sxs-lookup"><span data-stu-id="42a57-185">![MEM Configuration settings](images/mem04-2-configuration-settings.png)</span></span>

5. <span data-ttu-id="42a57-186">Fare **di nuovo clic su** Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="42a57-186">Click **Add** again.</span></span> <span data-ttu-id="42a57-187">Verrà visualizzata la finestra di dialogo Aggiungi **URI OMA Impostazioni** riga.</span><span class="sxs-lookup"><span data-stu-id="42a57-187">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="42a57-188">In **Aggiungi riga** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42a57-188">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="42a57-189">In **Nome** digitare un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="42a57-189">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="42a57-190">In **Descrizione** digitare una breve descrizione.</span><span class="sxs-lookup"><span data-stu-id="42a57-190">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="42a57-191">In **URI OMA** digitare o incollare il collegamento URI OMA specifico per la regola che si sta aggiungendo.</span><span class="sxs-lookup"><span data-stu-id="42a57-191">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="42a57-192">In **Tipo di dati** selezionare **String**.</span><span class="sxs-lookup"><span data-stu-id="42a57-192">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="42a57-193">In **Valore** digitare o incollare il valore GUID, il segno e il valore State senza spazi \= (_GUID=StateValue_).</span><span class="sxs-lookup"><span data-stu-id="42a57-193">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="42a57-194">Dove: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span><span class="sxs-lookup"><span data-stu-id="42a57-194">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42a57-195">![Configurazione URI OMA MEM](images/mem05-add-row-oma-uri.png)</span><span class="sxs-lookup"><span data-stu-id="42a57-195">![MEM OMA URI configuration](images/mem05-add-row-oma-uri.png)</span></span>

6. <span data-ttu-id="42a57-196">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="42a57-196">Click **Save**.</span></span> <span data-ttu-id="42a57-197">**Add Row** closes.</span><span class="sxs-lookup"><span data-stu-id="42a57-197">**Add Row** closes.</span></span> <span data-ttu-id="42a57-198">In **Personalizzato** fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="42a57-198">In **Custom**, click **Next**.</span></span> <span data-ttu-id="42a57-199">Nel passaggio **3 Tag ambito** i tag di ambito sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="42a57-199">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="42a57-200">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42a57-200">Do one of the following:</span></span>

   - <span data-ttu-id="42a57-201">Fare **clic su Seleziona tag ambito,** selezionare il tag di ambito (facoltativo) e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="42a57-201">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="42a57-202">Oppure fare clic su **Avanti**</span><span class="sxs-lookup"><span data-stu-id="42a57-202">Or click **Next**</span></span>

7. <span data-ttu-id="42a57-203">Nel passaggio **4 Assegnazioni,** **in** Gruppi inclusi per i gruppi a cui si desidera applicare la regola, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42a57-203">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="42a57-204">**Aggiungere gruppi**</span><span class="sxs-lookup"><span data-stu-id="42a57-204">**Add groups**</span></span>
   - <span data-ttu-id="42a57-205">**Aggiungere tutti gli utenti**</span><span class="sxs-lookup"><span data-stu-id="42a57-205">**Add all users**</span></span>
   - <span data-ttu-id="42a57-206">**Aggiungere tutti i dispositivi**</span><span class="sxs-lookup"><span data-stu-id="42a57-206">**Add all devices**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42a57-207">![Assegnazioni MEM](images/mem06-4-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="42a57-207">![MEM assignments](images/mem06-4-assignments.png)</span></span>

8. <span data-ttu-id="42a57-208">In **Gruppi esclusi** selezionare i gruppi che si desidera escludere dalla regola e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="42a57-208">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="42a57-209">Nel passaggio **5 Regole di applicabilità** per le impostazioni seguenti eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42a57-209">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="42a57-210">In **Regola** selezionare Assegna **profilo se** o Non **assegnare profilo se**</span><span class="sxs-lookup"><span data-stu-id="42a57-210">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="42a57-211">In **Proprietà** selezionare la proprietà a cui si desidera applicare la regola</span><span class="sxs-lookup"><span data-stu-id="42a57-211">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="42a57-212">In **Valore** immettere il valore applicabile o l'intervallo di valori</span><span class="sxs-lookup"><span data-stu-id="42a57-212">In **Value**, enter the applicable value or value range</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="42a57-213">![Regole di applicabilità MEM](images/mem07-5-applicability-rules.png)</span><span class="sxs-lookup"><span data-stu-id="42a57-213">![MEM Applicability rules](images/mem07-5-applicability-rules.png)</span></span>

10. <span data-ttu-id="42a57-214">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="42a57-214">Click **Next**.</span></span> <span data-ttu-id="42a57-215">Nel passaggio **6 Rivedere e creare** esaminare le impostazioni e le informazioni selezionate e immesse e quindi fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="42a57-215">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="42a57-216">![MEM Rivedere e creare](images/mem08-6-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="42a57-216">![MEM Review and create](images/mem08-6-review-create.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="42a57-217">Le regole sono attive e attive in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="42a57-217">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="42a57-218">Gestione dei conflitti:</span><span class="sxs-lookup"><span data-stu-id="42a57-218">Conflict handling:</span></span>
>
> <span data-ttu-id="42a57-219">Se assegni a un dispositivo due criteri asR diversi, il modo in cui viene gestito il conflitto sono le regole a cui vengono assegnati stati diversi, non esiste una gestione dei conflitti e il risultato è un errore.</span><span class="sxs-lookup"><span data-stu-id="42a57-219">If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
>
> <span data-ttu-id="42a57-220">Le regole non in conflitto non restituiranno un errore e la regola verrà applicata correttamente.</span><span class="sxs-lookup"><span data-stu-id="42a57-220">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="42a57-221">Ne risulta che viene applicata la prima regola e le regole successive non in conflitto vengono unite nel criterio.</span><span class="sxs-lookup"><span data-stu-id="42a57-221">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="mdm"></a><span data-ttu-id="42a57-222">MDM</span><span class="sxs-lookup"><span data-stu-id="42a57-222">MDM</span></span>

<span data-ttu-id="42a57-223">Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) per abilitare e impostare singolarmente la modalità per ogni regola.</span><span class="sxs-lookup"><span data-stu-id="42a57-223">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="42a57-224">Di seguito è riportato un esempio di riferimento, utilizzando [i valori GUID per le regole asr.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="42a57-224">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="42a57-225">I valori da abilitare (blocca), disabilitare, avvisare o abilitare in modalità di controllo sono:</span><span class="sxs-lookup"><span data-stu-id="42a57-225">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="42a57-226">0 : Disable (Disable the ASR rule)</span><span class="sxs-lookup"><span data-stu-id="42a57-226">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="42a57-227">1 : Blocca (abilita la regola asr)</span><span class="sxs-lookup"><span data-stu-id="42a57-227">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="42a57-228">2 : Controllo (valutare l'impatto della regola asr sull'organizzazione se abilitata)</span><span class="sxs-lookup"><span data-stu-id="42a57-228">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="42a57-229">6 : avvisa (abilita la regola asr ma consenti all'utente finale di ignorare il blocco).</span><span class="sxs-lookup"><span data-stu-id="42a57-229">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="42a57-230">La modalità avviso è ora disponibile per la maggior parte delle regole asr.</span><span class="sxs-lookup"><span data-stu-id="42a57-230">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="42a57-231">Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) per aggiungere esclusioni.</span><span class="sxs-lookup"><span data-stu-id="42a57-231">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="42a57-232">Esempio:</span><span class="sxs-lookup"><span data-stu-id="42a57-232">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="42a57-233">Assicurati di immettere valori URI OMA senza spazi.</span><span class="sxs-lookup"><span data-stu-id="42a57-233">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="42a57-234">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="42a57-234">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="42a57-235">In Microsoft Endpoint Configuration Manager, andare a **Assets and Compliance**  >  **Endpoint Protection** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="42a57-235">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="42a57-236">Selezionare **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="42a57-236">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="42a57-237">Immetti un nome e una descrizione, seleziona **Riduzione superficie di attacco** e seleziona **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="42a57-237">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="42a57-238">Scegliere le regole che verranno bloccate o le azioni di controllo e selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="42a57-238">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="42a57-239">Rivedere le impostazioni e selezionare **Avanti** per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="42a57-239">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="42a57-240">Dopo la creazione del criterio, **chiudere**.</span><span class="sxs-lookup"><span data-stu-id="42a57-240">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="42a57-241">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="42a57-241">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="42a57-242">Se gestisci i computer e i dispositivi con Intune, Configuration Manager o un'altra piattaforma di gestione a livello aziendale, il software di gestione sovrascriverà tutte le impostazioni di Criteri di gruppo in conflitto all'avvio.</span><span class="sxs-lookup"><span data-stu-id="42a57-242">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="42a57-243">Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](https://technet.microsoft.com/library/cc731212.aspx), fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo da configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="42a57-243">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="42a57-244">Nell **'Editor Gestione Criteri di gruppo** passare a **Configurazione computer** e selezionare **Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="42a57-244">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="42a57-245">Espandere l'albero per **Windows componenti Antivirus Microsoft Defender** Microsoft Defender Exploit Guard riduzione della superficie  >    >    >  **di attacco.**</span><span class="sxs-lookup"><span data-stu-id="42a57-245">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="42a57-246">Selezionare **Configura regole di riduzione della superficie di attacco** e selezionare **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="42a57-246">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="42a57-247">È quindi possibile impostare il singolo stato per ogni regola nella sezione opzioni.</span><span class="sxs-lookup"><span data-stu-id="42a57-247">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="42a57-248">Selezionare **Mostra...** e immettere l'ID regola nella colonna **Nome valore** e lo stato scelto nella colonna **Valore** come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="42a57-248">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="42a57-249">0 : Disable (Disable the ASR rule)</span><span class="sxs-lookup"><span data-stu-id="42a57-249">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="42a57-250">1 : Blocca (abilita la regola asr)</span><span class="sxs-lookup"><span data-stu-id="42a57-250">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="42a57-251">2 : Controllo (valutare l'impatto della regola asr sull'organizzazione se abilitata)</span><span class="sxs-lookup"><span data-stu-id="42a57-251">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="42a57-252">6 : Avvisa (abilita la regola di registrazione asr ma consenti all'utente finale di ignorare il blocco)</span><span class="sxs-lookup"><span data-stu-id="42a57-252">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="Regole asr in Criteri di gruppo":::

5. <span data-ttu-id="42a57-254">Per escludere file e cartelle dalle  regole asr, selezionare l'impostazione Escludi file e percorsi dalle regole di riduzione della superficie di attacco e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="42a57-254">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="42a57-255">Selezionare **Mostra** e immettere ogni file o cartella nella **colonna Nome** valore.</span><span class="sxs-lookup"><span data-stu-id="42a57-255">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="42a57-256">Immettere **0** nella **colonna Valore** per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="42a57-256">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="42a57-257">Non utilizzare le virgolette perché non sono supportate per la colonna **Nome valore** o **Valore.**</span><span class="sxs-lookup"><span data-stu-id="42a57-257">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="42a57-258">PowerShell</span><span class="sxs-lookup"><span data-stu-id="42a57-258">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="42a57-259">Se gestisci i computer e i dispositivi con Intune, Configuration Manager o un'altra piattaforma di gestione a livello aziendale, il software di gestione sovrascriverà tutte le impostazioni di PowerShell in conflitto all'avvio.</span><span class="sxs-lookup"><span data-stu-id="42a57-259">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="42a57-260">Per consentire agli utenti di definire il valore tramite PowerShell, utilizzare l'opzione "Definito dall'utente" per la regola nella piattaforma di gestione.</span><span class="sxs-lookup"><span data-stu-id="42a57-260">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="42a57-261">Digitare **powershell** nella menu Start, fare clic con il pulsante destro **del mouse** Windows PowerShell e selezionare Esegui come **amministratore.**</span><span class="sxs-lookup"><span data-stu-id="42a57-261">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="42a57-262">Digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="42a57-262">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="42a57-263">Per abilitare le regole di registrazione asr in modalità di controllo, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="42a57-263">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="42a57-264">Per abilitare le regole di Registrazione asr in modalità avviso, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="42a57-264">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="42a57-265">Per abilitare AsR Bloccare l'abuso di driver firmati vulnerabili sfruttati, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="42a57-265">To enable ASR Block abuse of exploited vulnerable signed drivers, use the following cmdlet:</span></span>

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    <span data-ttu-id="42a57-266">Per disattivare le regole asr, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="42a57-266">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="42a57-267">È necessario specificare lo stato singolarmente per ogni regola, ma è possibile combinare regole e stati in un elenco delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="42a57-267">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="42a57-268">Nell'esempio seguente verranno abilitate le prime due regole, la terza verrà disabilitata e la quarta verrà abilitata in modalità di controllo:</span><span class="sxs-lookup"><span data-stu-id="42a57-268">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="42a57-269">È inoltre possibile utilizzare il `Add-MpPreference` verbo PowerShell per aggiungere nuove regole all'elenco esistente.</span><span class="sxs-lookup"><span data-stu-id="42a57-269">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="42a57-270">`Set-MpPreference` sovrascriverà sempre il set di regole esistente.</span><span class="sxs-lookup"><span data-stu-id="42a57-270">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="42a57-271">Se vuoi aggiungerlo al set esistente, usa `Add-MpPreference` invece.</span><span class="sxs-lookup"><span data-stu-id="42a57-271">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="42a57-272">È possibile ottenere un elenco di regole e il relativo stato corrente utilizzando `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="42a57-272">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="42a57-273">Per escludere file e cartelle dalle regole asr, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="42a57-273">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="42a57-274">Continuare a utilizzare `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` per aggiungere altri file e cartelle all'elenco.</span><span class="sxs-lookup"><span data-stu-id="42a57-274">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="42a57-275">Usa `Add-MpPreference` per aggiungere o aggiungere app all'elenco.</span><span class="sxs-lookup"><span data-stu-id="42a57-275">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="42a57-276">`Set-MpPreference`L'utilizzo del cmdlet sovrascriverà l'elenco esistente.</span><span class="sxs-lookup"><span data-stu-id="42a57-276">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="42a57-277">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="42a57-277">Related articles</span></span>

- [<span data-ttu-id="42a57-278">Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="42a57-278">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="42a57-279">Valutare la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="42a57-279">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="42a57-280">Domande frequenti per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="42a57-280">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
