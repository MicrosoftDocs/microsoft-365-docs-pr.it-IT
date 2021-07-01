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
ms.openlocfilehash: 65215d15e79ab03611bbf28c153d6882fd1c355d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229144"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="8c4a9-104">Abilitare regole per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="8c4a9-104">Enable attack surface reduction rules</span></span>

<span data-ttu-id="8c4a9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-105">**Applies to:**</span></span>

- [<span data-ttu-id="8c4a9-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="8c4a9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8c4a9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c4a9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="8c4a9-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8c4a9-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="8c4a9-109">[Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="8c4a9-110">[Le regole di riduzione della superficie](attack-surface-reduction.md) di attacco (regole ASR) consentono di impedire azioni che il malware spesso abuso per compromettere dispositivi e reti.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

## <a name="requirements"></a><span data-ttu-id="8c4a9-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8c4a9-111">Requirements</span></span>

<span data-ttu-id="8c4a9-112">Funzionalità di riduzione della superficie di attacco Windows versioni</span><span class="sxs-lookup"><span data-stu-id="8c4a9-112">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="8c4a9-113">Puoi impostare regole di riduzione della superficie di attacco per i dispositivi che eseguono una delle seguenti edizioni e versioni di Windows:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-113">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="8c4a9-114">Windows 10 Pro versione [1709](/windows/whats-new/whats-new-windows-10-version-1709) o successiva</span><span class="sxs-lookup"><span data-stu-id="8c4a9-114">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="8c4a9-115">Windows 10 Enterprise versione [1709](/windows/whats-new/whats-new-windows-10-version-1709) o successiva</span><span class="sxs-lookup"><span data-stu-id="8c4a9-115">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="8c4a9-116">Windows Server, [versione 1803 (Canale semestraale)](/windows-server/get-started/whats-new-in-windows-server-1803) o versione successiva</span><span class="sxs-lookup"><span data-stu-id="8c4a9-116">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="8c4a9-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="8c4a9-117">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="8c4a9-118">Per usare l'intero set di funzionalità delle regole di riduzione della superficie di attacco, è necessario:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-118">To use the entire feature-set of attack surface reduction rules, you need:</span></span>

- <span data-ttu-id="8c4a9-119">Windows Defender Antivirus come av primario (protezione in tempo reale)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-119">Windows Defender Antivirus as primary AV (real-time protection on)</span></span>
- <span data-ttu-id="8c4a9-120">[Cloud-Delivery Protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) on (alcune regole lo richiedono)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-120">[Cloud-Delivery Protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) on (some rules require that)</span></span>
- <span data-ttu-id="8c4a9-121">Windows 10 Enterprise Licenza E5 o E3 o Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="8c4a9-121">Windows 10 Enterprise E5 or E3 License or Microsoft 365 Business License</span></span>

<span data-ttu-id="8c4a9-122">Anche se le regole di riduzione della superficie di attacco non richiedono una licenza [E5](/windows/deployment/deploy-enterprise-licenses)di Windows , con una licenza di Windows E5, puoi ottenere funzionalità di gestione avanzate, tra cui monitoraggio, analisi e flussi di lavoro disponibili in Defender for Endpoint, nonché funzionalità di creazione di report e configurazione nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-122">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), with a Windows E5 license, you get advanced management capabilities including monitoring, analytics, and workflows available in Defender for Endpoint, as well as reporting and configuration capabilities in the Microsoft 365 security center.</span></span> <span data-ttu-id="8c4a9-123">Queste funzionalità avanzate non sono disponibili con una licenza E3, ma puoi comunque usare il Visualizzatore eventi per esaminare gli eventi delle regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-123">These advanced capabilities aren't available with an E3 license, but you can still use Event Viewer to review attack surface reduction rule events.</span></span>

<span data-ttu-id="8c4a9-124">Ogni regola asr contiene una delle quattro impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-124">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="8c4a9-125">**Non configurato**: disabilita la regola asr</span><span class="sxs-lookup"><span data-stu-id="8c4a9-125">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="8c4a9-126">**Block**: Enable the ASR rule</span><span class="sxs-lookup"><span data-stu-id="8c4a9-126">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="8c4a9-127">**Controllo**: valutare l'impatto della regola asr sull'organizzazione se abilitata</span><span class="sxs-lookup"><span data-stu-id="8c4a9-127">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="8c4a9-128">**Avviso:** abilitare la regola asr ma consentire all'utente finale di ignorare il blocco</span><span class="sxs-lookup"><span data-stu-id="8c4a9-128">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c4a9-129">Attualmente, la modalità avviso non è supportata per tre regole asr quando si configurano le regole di ripristino asr in Microsoft Endpoint Manager (MEM).</span><span class="sxs-lookup"><span data-stu-id="8c4a9-129">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="8c4a9-130">Per altre informazioni, vedi [Casi in cui la modalità avviso non è supportata.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-130">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="8c4a9-131">È consigliabile usare le regole asr con una licenza di Windows E5 (o una SKU di licenza simile) per sfruttare le funzionalità avanzate di monitoraggio e creazione di report disponibili in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span><span class="sxs-lookup"><span data-stu-id="8c4a9-131">It's highly recommended to use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span></span> <span data-ttu-id="8c4a9-132">Tuttavia, se si dispone di un'altra licenza, ad esempio Windows Professional o Windows E3 che non include funzionalità avanzate di monitoraggio e creazione di report, è possibile sviluppare strumenti di monitoraggio e creazione di report personalizzati oltre agli eventi generati in ogni endpoint quando vengono attivate le regole asr (ad esempio, Inoltro eventi).</span><span class="sxs-lookup"><span data-stu-id="8c4a9-132">However, if you have another license, such as Windows Professional or Windows E3 that don't include advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (for example, Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="8c4a9-133">Per ulteriori informazioni sulle licenze Windows, vedere [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) e ottenere la guida per contratti [multilicenza per Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="8c4a9-133">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="8c4a9-134">Puoi abilitare le regole di riduzione della superficie di attacco usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-134">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="8c4a9-135">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8c4a9-135">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="8c4a9-136">Gestione di dispositivi mobili (MDM)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-136">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="8c4a9-137">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8c4a9-137">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="8c4a9-138">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="8c4a9-138">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="8c4a9-139">PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c4a9-139">PowerShell</span></span>](#powershell)

<span data-ttu-id="8c4a9-140">Enterprise è consigliata la gestione a livello di Microsoft Endpoint Manager, ad esempio Intune.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-140">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="8c4a9-141">Enterprise gestione a livello di utente sovrascriverà tutte le impostazioni di Criteri di gruppo o PowerShell in conflitto all'avvio.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-141">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="8c4a9-142">Escludere file e cartelle dalle regole asr</span><span class="sxs-lookup"><span data-stu-id="8c4a9-142">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="8c4a9-143">È possibile escludere file e cartelle dalla maggior parte delle regole di riduzione della superficie di attacco.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-143">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="8c4a9-144">Ciò significa che, anche se una regola asr determina che il file o la cartella contiene comportamenti dannosi, non blocchi l'esecuzione del file.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-144">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="8c4a9-145">Ciò potrebbe potenzialmente consentire l'esecuzione di file non sicuri e infettare i dispositivi.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-145">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="8c4a9-146">Puoi anche escludere le regole asr dall'attivazione in base agli hash di certificati e file consentendo a Defender per gli indicatori di certificato e file dell'endpoint specificati.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-146">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="8c4a9-147">(Vedere [Gestire gli indicatori](manage-indicators.md).)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-147">(See [Manage indicators](manage-indicators.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c4a9-148">L'esclusione di file o cartelle può ridurre notevolmente la protezione fornita dalle regole asr.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-148">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="8c4a9-149">L'esecuzione dei file esclusi sarà consentita e non verrà registrato alcun report o evento.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-149">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="8c4a9-150">Se le regole di ripristino automatico rilevano file che ritieni non debbano essere rilevati, devi prima usare la modalità di controllo per [testare la regola.](evaluate-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-150">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="8c4a9-151">È possibile specificare singoli file o cartelle (utilizzando percorsi di cartelle o nomi di risorse completi), ma non è possibile specificare le regole a cui si applicano le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-151">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="8c4a9-152">Un'esclusione viene applicata solo all'avvio dell'applicazione o del servizio escluso.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-152">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="8c4a9-153">Ad esempio, se si aggiunge un'esclusione per un servizio di aggiornamento già in esecuzione, il servizio di aggiornamento continuerà a attivare eventi finché il servizio non viene arrestato e riavviato.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-153">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="8c4a9-154">Le regole asr supportano variabili di ambiente e caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-154">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="8c4a9-155">Per informazioni sull'utilizzo dei caratteri jolly, vedere [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span><span class="sxs-lookup"><span data-stu-id="8c4a9-155">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="8c4a9-156">Le procedure seguenti per l'abilitazione delle regole asr includono istruzioni su come escludere file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-156">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="8c4a9-157">Intune</span><span class="sxs-lookup"><span data-stu-id="8c4a9-157">Intune</span></span>

1. <span data-ttu-id="8c4a9-158">Selezionare **Profili di configurazione** del  >  **dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-158">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="8c4a9-159">Scegliere un profilo di endpoint protection esistente o crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-159">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="8c4a9-160">Per crearne uno nuovo, selezionare **Crea profilo** e immettere le informazioni per il profilo.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-160">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="8c4a9-161">Per **Tipo di profilo** selezionare Endpoint **protection.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-161">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="8c4a9-162">Se è stato scelto un profilo esistente, selezionare **Proprietà** e quindi selezionare **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-162">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="8c4a9-163">Nel riquadro **Endpoint protection** seleziona Windows Defender **Exploit Guard,** quindi seleziona **Riduzione della superficie di attacco.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-163">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="8c4a9-164">Selezionare l'impostazione desiderata per ogni regola asr.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-164">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="8c4a9-165">In **Eccezioni di riduzione della superficie di attacco** immetti singoli file e cartelle.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-165">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="8c4a9-166">È inoltre possibile selezionare **Importa per** importare un file CSV contenente file e cartelle da escludere dalle regole asr.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-166">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="8c4a9-167">Ogni riga del file CSV deve essere formattata come segue:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-167">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="8c4a9-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="8c4a9-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="8c4a9-169">Selezionare **OK** nei tre riquadri di configurazione.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-169">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="8c4a9-170">Seleziona Quindi **Crea** se stai creando un nuovo file di endpoint protection o **Salva** se ne stai modificando uno esistente.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-170">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mem"></a><span data-ttu-id="8c4a9-171">MEM</span><span class="sxs-lookup"><span data-stu-id="8c4a9-171">MEM</span></span>

<span data-ttu-id="8c4a9-172">Puoi usare l'URI OMA Microsoft Endpoint Manager (MEM) per configurare regole asr personalizzate.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-172">You can use Microsoft Endpoint Manager (MEM) OMA-URI to configure custom ASR rules.</span></span> <span data-ttu-id="8c4a9-173">Nella procedura seguente viene utilizzata la regola [Bloccare l'abuso di](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) driver firmati vulnerabili sfruttati per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-173">The following procedure uses the rule [Block abuse of exploited vulnerable signed drivers](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) for the example.</span></span>

1. <span data-ttu-id="8c4a9-174">Aprire l'Microsoft Endpoint Manager di amministrazione (MEM).</span><span class="sxs-lookup"><span data-stu-id="8c4a9-174">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="8c4a9-175">Nel menu **Home** fare clic su **Dispositivi,** selezionare **Profilo di configurazione** e quindi fare clic su Crea **profilo.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-175">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8c4a9-176">![MEM Create Profile](images/mem01-create-profile.png)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-176">![MEM Create Profile](images/mem01-create-profile.png)</span></span>

2. <span data-ttu-id="8c4a9-177">In **Crea profilo** selezionare quanto segue nei due elenchi a discesa seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-177">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="8c4a9-178">In **Piattaforma** selezionare Windows 10 **e versioni successive**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-178">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="8c4a9-179">In **Tipo di profilo** selezionare **Modelli**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-179">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="8c4a9-180">Selezionare **Personalizzato** e quindi fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-180">Select **Custom**, and then click **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8c4a9-181">![Attributi del profilo delle regole MEM](images/mem02-profile-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-181">![MEM rule profile attributes](images/mem02-profile-attributes.png)</span></span>

3. <span data-ttu-id="8c4a9-182">Lo strumento Modello personalizzato viene aperto al **passaggio 1 Nozioni di base.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-182">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="8c4a9-183">In **1 Nozioni di** base, in **Nome** digitare un nome per il modello e **in** Descrizione è possibile digitare una descrizione (facoltativa).</span><span class="sxs-lookup"><span data-stu-id="8c4a9-183">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type a description (optional).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8c4a9-184">![Attributi di base MEM](images/mem03-1-basics.png)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-184">![MEM basic attributes](images/mem03-1-basics.png)</span></span>

4. <span data-ttu-id="8c4a9-185">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-185">Click **Next**.</span></span> <span data-ttu-id="8c4a9-186">Step **2 Configuration settings opens.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-186">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="8c4a9-187">Per l'URI OMA Impostazioni, fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-187">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="8c4a9-188">Vengono ora visualizzate due opzioni: **Aggiungi** ed **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-188">Two options now appear: **Add** and **Export**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8c4a9-189">![Impostazioni di configurazione MEM](images/mem04-2-configuration-settings.png)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-189">![MEM Configuration settings](images/mem04-2-configuration-settings.png)</span></span>

5. <span data-ttu-id="8c4a9-190">Fare **di nuovo clic su** Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-190">Click **Add** again.</span></span> <span data-ttu-id="8c4a9-191">Verrà visualizzata la finestra di dialogo Aggiungi **URI OMA Impostazioni** riga.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-191">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="8c4a9-192">In **Aggiungi riga** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-192">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="8c4a9-193">In **Nome** digitare un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-193">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="8c4a9-194">In **Descrizione** digitare una breve descrizione.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-194">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="8c4a9-195">In **URI OMA** digitare o incollare il collegamento URI OMA specifico per la regola che si sta aggiungendo.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-195">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="8c4a9-196">In **Tipo di dati** selezionare **String**.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-196">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="8c4a9-197">In **Valore** digitare o incollare il valore GUID, il segno e il valore State senza spazi \= (_GUID=StateValue_).</span><span class="sxs-lookup"><span data-stu-id="8c4a9-197">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="8c4a9-198">Dove: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span><span class="sxs-lookup"><span data-stu-id="8c4a9-198">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8c4a9-199">![Configurazione URI OMA MEM](images/mem05-add-row-oma-uri.png)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-199">![MEM OMA URI configuration](images/mem05-add-row-oma-uri.png)</span></span>

6. <span data-ttu-id="8c4a9-200">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-200">Click **Save**.</span></span> <span data-ttu-id="8c4a9-201">**Add Row** closes.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-201">**Add Row** closes.</span></span> <span data-ttu-id="8c4a9-202">In **Personalizzato** fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-202">In **Custom**, click **Next**.</span></span> <span data-ttu-id="8c4a9-203">Nel passaggio **3 Tag ambito** i tag di ambito sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-203">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="8c4a9-204">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-204">Do one of the following:</span></span>

   - <span data-ttu-id="8c4a9-205">Fare **clic su Seleziona tag ambito,** selezionare il tag di ambito (facoltativo) e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-205">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="8c4a9-206">Oppure fare clic su **Avanti**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-206">Or click **Next**</span></span>

7. <span data-ttu-id="8c4a9-207">Nel passaggio **4 Assegnazioni,** **in** Gruppi inclusi per i gruppi a cui si desidera applicare la regola, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-207">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="8c4a9-208">**Aggiungere gruppi**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-208">**Add groups**</span></span>
   - <span data-ttu-id="8c4a9-209">**Aggiungere tutti gli utenti**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-209">**Add all users**</span></span>
   - <span data-ttu-id="8c4a9-210">**Aggiungere tutti i dispositivi**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-210">**Add all devices**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8c4a9-211">![Assegnazioni MEM](images/mem06-4-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-211">![MEM assignments](images/mem06-4-assignments.png)</span></span>

8. <span data-ttu-id="8c4a9-212">In **Gruppi esclusi** selezionare i gruppi che si desidera escludere dalla regola e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-212">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="8c4a9-213">Nel passaggio **5 Regole di applicabilità** per le impostazioni seguenti eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-213">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="8c4a9-214">In **Regola** selezionare Assegna **profilo se** o Non **assegnare profilo se**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-214">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="8c4a9-215">In **Proprietà** selezionare la proprietà a cui si desidera applicare la regola</span><span class="sxs-lookup"><span data-stu-id="8c4a9-215">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="8c4a9-216">In **Valore** immettere il valore applicabile o l'intervallo di valori</span><span class="sxs-lookup"><span data-stu-id="8c4a9-216">In **Value**, enter the applicable value or value range</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8c4a9-217">![Regole di applicabilità MEM](images/mem07-5-applicability-rules.png)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-217">![MEM Applicability rules](images/mem07-5-applicability-rules.png)</span></span>

10. <span data-ttu-id="8c4a9-218">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-218">Click **Next**.</span></span> <span data-ttu-id="8c4a9-219">Nel passaggio **6 Rivedere e creare** esaminare le impostazioni e le informazioni selezionate e immesse e quindi fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-219">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8c4a9-220">![MEM Rivedere e creare](images/mem08-6-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-220">![MEM Review and create](images/mem08-6-review-create.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="8c4a9-221">Le regole sono attive e attive in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-221">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="8c4a9-222">Gestione dei conflitti:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-222">Conflict handling:</span></span>
>
> <span data-ttu-id="8c4a9-223">Se assegni a un dispositivo due criteri asR diversi, il modo in cui viene gestito il conflitto sono le regole a cui vengono assegnati stati diversi, non esiste una gestione dei conflitti e il risultato è un errore.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-223">If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
>
> <span data-ttu-id="8c4a9-224">Le regole non in conflitto non restituiranno un errore e la regola verrà applicata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-224">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="8c4a9-225">Ne risulta che viene applicata la prima regola e le regole successive non in conflitto vengono unite nel criterio.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-225">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="mdm"></a><span data-ttu-id="8c4a9-226">MDM</span><span class="sxs-lookup"><span data-stu-id="8c4a9-226">MDM</span></span>

<span data-ttu-id="8c4a9-227">Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) per abilitare e impostare singolarmente la modalità per ogni regola.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-227">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="8c4a9-228">Di seguito è riportato un esempio di riferimento, utilizzando [i valori GUID per le regole asr.](attack-surface-reduction.md#attack-surface-reduction-rules)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-228">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="8c4a9-229">I valori da abilitare (blocca), disabilitare, avvisare o abilitare in modalità di controllo sono:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-229">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="8c4a9-230">0 : Disable (Disable the ASR rule)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-230">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="8c4a9-231">1 : Blocca (abilita la regola asr)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-231">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="8c4a9-232">2 : Controllo (valutare l'impatto della regola asr sull'organizzazione se abilitata)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-232">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="8c4a9-233">6 : avvisa (abilita la regola asr ma consenti all'utente finale di ignorare il blocco).</span><span class="sxs-lookup"><span data-stu-id="8c4a9-233">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="8c4a9-234">La modalità avviso è ora disponibile per la maggior parte delle regole asr.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-234">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="8c4a9-235">Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) per aggiungere esclusioni.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-235">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="8c4a9-236">Esempio:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-236">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="8c4a9-237">Assicurati di immettere valori URI OMA senza spazi.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-237">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="8c4a9-238">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8c4a9-238">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="8c4a9-239">In Microsoft Endpoint Configuration Manager, andare a **Assets and Compliance**  >  **Endpoint Protection** Windows Defender  >  **Exploit Guard**.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-239">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="8c4a9-240">Selezionare **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-240">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="8c4a9-241">Immetti un nome e una descrizione, seleziona **Riduzione superficie di attacco** e seleziona **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-241">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="8c4a9-242">Scegliere le regole che verranno bloccate o le azioni di controllo e selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-242">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="8c4a9-243">Rivedere le impostazioni e selezionare **Avanti** per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-243">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="8c4a9-244">Dopo la creazione del criterio, **chiudere**.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-244">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="8c4a9-245">Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="8c4a9-245">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="8c4a9-246">Se gestisci i computer e i dispositivi con Intune, Configuration Manager o un'altra piattaforma di gestione a livello aziendale, il software di gestione sovrascriverà tutte le impostazioni di Criteri di gruppo in conflitto all'avvio.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-246">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="8c4a9-247">Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](https://technet.microsoft.com/library/cc731212.aspx), fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo da configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-247">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="8c4a9-248">Nell **'Editor Gestione Criteri di gruppo** passare a **Configurazione computer** e selezionare **Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-248">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="8c4a9-249">Espandere l'albero per **Windows componenti Antivirus Microsoft Defender** Microsoft Defender Exploit Guard riduzione della superficie  >    >    >  **di attacco.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-249">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="8c4a9-250">Selezionare **Configura regole di riduzione della superficie di attacco** e selezionare **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-250">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="8c4a9-251">È quindi possibile impostare il singolo stato per ogni regola nella sezione opzioni.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-251">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="8c4a9-252">Selezionare **Mostra...** e immettere l'ID regola nella colonna **Nome valore** e lo stato scelto nella colonna **Valore** come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-252">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="8c4a9-253">0 : Disable (Disable the ASR rule)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-253">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="8c4a9-254">1 : Blocca (abilita la regola asr)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-254">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="8c4a9-255">2 : Controllo (valutare l'impatto della regola asr sull'organizzazione se abilitata)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-255">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="8c4a9-256">6 : Avvisa (abilita la regola di registrazione asr ma consenti all'utente finale di ignorare il blocco)</span><span class="sxs-lookup"><span data-stu-id="8c4a9-256">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="Regole asr in Criteri di gruppo":::

5. <span data-ttu-id="8c4a9-258">Per escludere file e cartelle dalle  regole asr, selezionare l'impostazione Escludi file e percorsi dalle regole di riduzione della superficie di attacco e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-258">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8c4a9-259">Selezionare **Mostra** e immettere ogni file o cartella nella **colonna Nome** valore.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-259">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="8c4a9-260">Immettere **0** nella **colonna Valore** per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-260">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="8c4a9-261">Non utilizzare le virgolette perché non sono supportate per la colonna **Nome valore** o **Valore.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-261">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="8c4a9-262">PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c4a9-262">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="8c4a9-263">Se gestisci i computer e i dispositivi con Intune, Configuration Manager o un'altra piattaforma di gestione a livello aziendale, il software di gestione sovrascriverà tutte le impostazioni di PowerShell in conflitto all'avvio.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-263">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="8c4a9-264">Per consentire agli utenti di definire il valore tramite PowerShell, utilizzare l'opzione "Definito dall'utente" per la regola nella piattaforma di gestione.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-264">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="8c4a9-265">Digitare **powershell** nella menu Start, fare clic con il pulsante destro **del mouse** Windows PowerShell e selezionare Esegui come **amministratore.**</span><span class="sxs-lookup"><span data-stu-id="8c4a9-265">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="8c4a9-266">Digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-266">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="8c4a9-267">Per abilitare le regole di registrazione asr in modalità di controllo, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-267">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="8c4a9-268">Per abilitare le regole di Registrazione asr in modalità avviso, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-268">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="8c4a9-269">Per abilitare AsR Bloccare l'abuso di driver firmati vulnerabili sfruttati, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-269">To enable ASR Block abuse of exploited vulnerable signed drivers, use the following cmdlet:</span></span>

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    <span data-ttu-id="8c4a9-270">Per disattivare le regole asr, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-270">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="8c4a9-271">È necessario specificare lo stato singolarmente per ogni regola, ma è possibile combinare regole e stati in un elenco delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-271">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="8c4a9-272">Nell'esempio seguente verranno abilitate le prime due regole, la terza verrà disabilitata e la quarta verrà abilitata in modalità di controllo:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-272">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="8c4a9-273">È inoltre possibile utilizzare il `Add-MpPreference` verbo PowerShell per aggiungere nuove regole all'elenco esistente.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-273">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="8c4a9-274">`Set-MpPreference` sovrascriverà sempre il set di regole esistente.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-274">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="8c4a9-275">Se vuoi aggiungerlo al set esistente, usa `Add-MpPreference` invece.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-275">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="8c4a9-276">È possibile ottenere un elenco di regole e il relativo stato corrente utilizzando `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="8c4a9-276">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="8c4a9-277">Per escludere file e cartelle dalle regole asr, utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="8c4a9-277">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="8c4a9-278">Continuare a utilizzare `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` per aggiungere altri file e cartelle all'elenco.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-278">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8c4a9-279">Usa `Add-MpPreference` per aggiungere o aggiungere app all'elenco.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-279">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="8c4a9-280">`Set-MpPreference`L'utilizzo del cmdlet sovrascriverà l'elenco esistente.</span><span class="sxs-lookup"><span data-stu-id="8c4a9-280">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8c4a9-281">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="8c4a9-281">Related articles</span></span>

- [<span data-ttu-id="8c4a9-282">Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="8c4a9-282">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="8c4a9-283">Valutare la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="8c4a9-283">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="8c4a9-284">Domande frequenti per la riduzione della superficie di attacco</span><span class="sxs-lookup"><span data-stu-id="8c4a9-284">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
