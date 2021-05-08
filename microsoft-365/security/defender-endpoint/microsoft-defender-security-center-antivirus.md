---
title: Antivirus Microsoft Defender nell'app Sicurezza di Windows app
description: Con Antivirus Microsoft Defender ora incluso nell'app Sicurezza di Windows, puoi esaminare, confrontare ed eseguire attività comuni.
keywords: wdav, antivirus, firewall, sicurezza, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ccb0d4cf168bbb4d3c1575c1e6611829909d0817
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275409"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="514d7-104">Antivirus Microsoft Defender nell'app Sicurezza di Windows app</span><span class="sxs-lookup"><span data-stu-id="514d7-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="514d7-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="514d7-105">**Applies to:**</span></span>

- [<span data-ttu-id="514d7-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="514d7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="514d7-107">In Windows 10 versione 1703 e successive, l'app Windows Defender app fa parte del Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="514d7-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="514d7-108">Impostazioni che in precedenza erano parte del client Windows Defender e del Windows Impostazioni principale sono stati combinati e spostati nella nuova app, che viene installata per impostazione predefinita come parte di Windows 10, versione 1703.</span><span class="sxs-lookup"><span data-stu-id="514d7-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="514d7-109">La disabilitazione del Sicurezza di Windows Center non disabilita Antivirus Microsoft Defender o [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span><span class="sxs-lookup"><span data-stu-id="514d7-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="514d7-110">Questi vengono disabilitati automaticamente quando viene installato e mantenuto aggiornato un prodotto firewall o antivirus di terze parti.</span><span class="sxs-lookup"><span data-stu-id="514d7-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="514d7-111">Se disabiliti il servizio Sicurezza di Windows Center o ne configura le impostazioni associate per impedirne l'avvio o l'esecuzione, l'app Sicurezza di Windows potrebbe visualizzare informazioni non aggiornate o imprecise su eventuali prodotti antivirus o firewall installati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="514d7-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="514d7-112">Potrebbe anche impedire a Antivirus Microsoft Defender di abilitarsi se si dispone di un antivirus di terze parti precedente o obsoleto o se si disinstallano prodotti antivirus di terze parti che potrebbero essere stati installati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="514d7-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="514d7-113">In questo modo si riduce notevolmente la protezione del dispositivo e potrebbe causare un'infezione da malware.</span><span class="sxs-lookup"><span data-stu-id="514d7-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="514d7-114">Vedi [l'Sicurezza di Windows per](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) altre informazioni su altre Windows di sicurezza che possono essere monitorate nell'app.</span><span class="sxs-lookup"><span data-stu-id="514d7-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="514d7-115">L Sicurezza di Windows app è un'interfaccia client Windows 10 versione 1703 e successive.</span><span class="sxs-lookup"><span data-stu-id="514d7-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="514d7-116">Non è il portale Microsoft Defender Security Center web utilizzato per esaminare e gestire [Microsoft Defender for Endpoint.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="514d7-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="514d7-117">Esaminare le impostazioni di protezione da virus e minacce nell Sicurezza di Windows app</span><span class="sxs-lookup"><span data-stu-id="514d7-117">Review virus and threat protection settings in the Windows Security app</span></span>

![Screenshot dell'etichetta Impostazioni di protezione da & virus nell'app Sicurezza di Windows virus](images/defender/wdav-protection-settings-wdsc.png)

1. <span data-ttu-id="514d7-119">Apri l Sicurezza di Windows app facendo clic sull'icona scudo nella barra delle applicazioni o cercando Defender nel menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="514d7-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="514d7-120">Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).</span><span class="sxs-lookup"><span data-stu-id="514d7-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="514d7-121">Le sezioni seguenti descrivono come eseguire alcune delle attività più comuni durante la revisione o l'interazione con la protezione dalle minacce fornita da Antivirus Microsoft Defender nell'app Sicurezza di Windows sicurezza.</span><span class="sxs-lookup"><span data-stu-id="514d7-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="514d7-122">Se queste impostazioni vengono configurate e distribuite tramite Criteri di gruppo, le impostazioni descritte in questa sezione saranno disattivate e non saranno disponibili per l'utilizzo nei singoli endpoint.</span><span class="sxs-lookup"><span data-stu-id="514d7-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="514d7-123">Le modifiche apportate tramite un oggetto Criteri di gruppo devono prima essere distribuite a singoli endpoint prima che l'impostazione venga aggiornata in Windows Impostazioni.</span><span class="sxs-lookup"><span data-stu-id="514d7-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="514d7-124">[L'argomento Configure end-user interaction with Antivirus Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md) descrive come configurare le impostazioni di sostituzione dei criteri locali.</span><span class="sxs-lookup"><span data-stu-id="514d7-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="514d7-125">Eseguire un'analisi con l Sicurezza di Windows app</span><span class="sxs-lookup"><span data-stu-id="514d7-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="514d7-126">Apri l Sicurezza di Windows app cercando Sicurezza nel menu Start **e** quindi selezionando **Sicurezza di Windows**.</span><span class="sxs-lookup"><span data-stu-id="514d7-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="514d7-127">Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).</span><span class="sxs-lookup"><span data-stu-id="514d7-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="514d7-128">Selezionare **Analisi rapida**.</span><span class="sxs-lookup"><span data-stu-id="514d7-128">Select **Quick scan**.</span></span> <span data-ttu-id="514d7-129">In caso contrario, per eseguire un'analisi completa, selezionare **Opzioni di** analisi e quindi selezionare un'opzione, ad esempio **Analisi completa.**</span><span class="sxs-lookup"><span data-stu-id="514d7-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="514d7-130">Esaminare la versione dell'aggiornamento della sicurezza intelligence e scaricare gli aggiornamenti più recenti nell'app Sicurezza di Windows sicurezza</span><span class="sxs-lookup"><span data-stu-id="514d7-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

![Informazioni sul numero di versione dell'intelligence per la sicurezza](images/defender/wdav-wdsc-defs.png)

1. <span data-ttu-id="514d7-132">Apri l Sicurezza di Windows app cercando Sicurezza nel menu Start *e* quindi selezionando **Sicurezza di Windows**.</span><span class="sxs-lookup"><span data-stu-id="514d7-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="514d7-133">Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).</span><span class="sxs-lookup"><span data-stu-id="514d7-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="514d7-134">Selezionare **Virus & threat protection updates**.</span><span class="sxs-lookup"><span data-stu-id="514d7-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="514d7-135">La versione attualmente installata viene visualizzata insieme ad alcune informazioni sul momento in cui è stata scaricata.</span><span class="sxs-lookup"><span data-stu-id="514d7-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="514d7-136">È possibile verificare la versione corrente rispetto alla versione più recente disponibile per il download manuale oppure esaminare il registro delle modifiche per tale versione.</span><span class="sxs-lookup"><span data-stu-id="514d7-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="514d7-137">Vedi [Aggiornamenti di Intelligence per la sicurezza Antivirus Microsoft Defender e altri antimalware Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="514d7-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="514d7-138">Selezionare **Controlla disponibilità aggiornamenti** per scaricare nuovi aggiornamenti di protezione (se disponibili).</span><span class="sxs-lookup"><span data-stu-id="514d7-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="514d7-139">Assicurati Antivirus Microsoft Defender abilitata nell'app Sicurezza di Windows app</span><span class="sxs-lookup"><span data-stu-id="514d7-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="514d7-140">Apri l Sicurezza di Windows app cercando Sicurezza nel menu Start *e* quindi selezionando **Sicurezza di Windows**.</span><span class="sxs-lookup"><span data-stu-id="514d7-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="514d7-141">Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).</span><span class="sxs-lookup"><span data-stu-id="514d7-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="514d7-142">Selezionare **Impostazioni protezione da & virus**.</span><span class="sxs-lookup"><span data-stu-id="514d7-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="514d7-143">Attiva **l'opzione Protezione in tempo** **reale.**</span><span class="sxs-lookup"><span data-stu-id="514d7-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="514d7-144">Se si disattiva **la protezione in tempo** reale, la protezione verrà automaticamente attivata dopo un breve ritardo.</span><span class="sxs-lookup"><span data-stu-id="514d7-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="514d7-145">Ciò consente di garantire la protezione da malware e minacce.</span><span class="sxs-lookup"><span data-stu-id="514d7-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="514d7-146">Se installi un altro prodotto antivirus, Antivirus Microsoft Defender automaticamente si disabilita e viene indicato come tale nell'app Sicurezza di Windows.</span><span class="sxs-lookup"><span data-stu-id="514d7-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="514d7-147">Verrà visualizzata un'impostazione che consente di abilitare [l'analisi periodica limitata.](limited-periodic-scanning-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="514d7-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="514d7-148">Aggiungere esclusioni per Antivirus Microsoft Defender nell'app Sicurezza di Windows app</span><span class="sxs-lookup"><span data-stu-id="514d7-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="514d7-149">Apri l Sicurezza di Windows app cercando Sicurezza nel menu Start *e* quindi selezionando **Sicurezza di Windows**.</span><span class="sxs-lookup"><span data-stu-id="514d7-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="514d7-150">Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).</span><span class="sxs-lookup"><span data-stu-id="514d7-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="514d7-151">In **Gestisci impostazioni selezionare** Impostazioni protezione da **& virus**.</span><span class="sxs-lookup"><span data-stu-id="514d7-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="514d7-152">**Nell'impostazione Esclusioni** seleziona **Aggiungi o rimuovi esclusioni.**</span><span class="sxs-lookup"><span data-stu-id="514d7-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="514d7-153">Selezionare l'icona più ( **+** ) per scegliere il tipo e impostare le opzioni per ogni esclusione.</span><span class="sxs-lookup"><span data-stu-id="514d7-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="514d7-154">Nella tabella seguente sono riepilogati i tipi di esclusione e cosa accade:</span><span class="sxs-lookup"><span data-stu-id="514d7-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="514d7-155">Tipo di esclusione</span><span class="sxs-lookup"><span data-stu-id="514d7-155">Exclusion type</span></span>  |<span data-ttu-id="514d7-156">Definito da</span><span class="sxs-lookup"><span data-stu-id="514d7-156">Defined by</span></span>  |<span data-ttu-id="514d7-157">Effetto</span><span class="sxs-lookup"><span data-stu-id="514d7-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="514d7-158">**File**</span><span class="sxs-lookup"><span data-stu-id="514d7-158">**File**</span></span> |<span data-ttu-id="514d7-159">Posizione</span><span class="sxs-lookup"><span data-stu-id="514d7-159">Location</span></span> <br/><span data-ttu-id="514d7-160">Esempio: `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="514d7-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="514d7-161">Il file specifico viene ignorato da Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="514d7-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="514d7-162">**Cartella**</span><span class="sxs-lookup"><span data-stu-id="514d7-162">**Folder**</span></span>    |<span data-ttu-id="514d7-163">Posizione</span><span class="sxs-lookup"><span data-stu-id="514d7-163">Location</span></span> <br/><span data-ttu-id="514d7-164">Esempio: `c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="514d7-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="514d7-165">Tutti gli elementi nella cartella specificata vengono ignorati da Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="514d7-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="514d7-166">**Tipo file**</span><span class="sxs-lookup"><span data-stu-id="514d7-166">**File type**</span></span>   |<span data-ttu-id="514d7-167">Estensione del file</span><span class="sxs-lookup"><span data-stu-id="514d7-167">File extension</span></span> <br/><span data-ttu-id="514d7-168">Esempio: `.test`</span><span class="sxs-lookup"><span data-stu-id="514d7-168">Example: `.test`</span></span> |<span data-ttu-id="514d7-169">Tutti i file con `.test` estensione in qualsiasi punto del dispositivo vengono ignorati da Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="514d7-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="514d7-170">**Procedura**</span><span class="sxs-lookup"><span data-stu-id="514d7-170">**Process**</span></span>     |<span data-ttu-id="514d7-171">Percorso file eseguibile</span><span class="sxs-lookup"><span data-stu-id="514d7-171">Executable file path</span></span> <br><span data-ttu-id="514d7-172">Esempio: `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="514d7-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="514d7-173">Il processo specifico e tutti i file aperti da tale processo vengono ignorati da Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="514d7-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="514d7-174">Per altre informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="514d7-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="514d7-175">Configurare e convalidare le esclusioni in base all'estensione di file e al percorso della cartella</span><span class="sxs-lookup"><span data-stu-id="514d7-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="514d7-176">Configurare le esclusioni per i file aperti dai processi</span><span class="sxs-lookup"><span data-stu-id="514d7-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="514d7-177">Esaminare la cronologia del rilevamento delle minacce nell'app centro sicurezza Windows Defender sicurezza</span><span class="sxs-lookup"><span data-stu-id="514d7-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="514d7-178">Apri l Sicurezza di Windows app cercando Sicurezza nel menu Start *e* quindi selezionando **Sicurezza di Windows**.</span><span class="sxs-lookup"><span data-stu-id="514d7-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="514d7-179">Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).</span><span class="sxs-lookup"><span data-stu-id="514d7-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="514d7-180">Selezionare **Cronologia protezione**.</span><span class="sxs-lookup"><span data-stu-id="514d7-180">Select **Protection history**.</span></span> <span data-ttu-id="514d7-181">Vengono elencati tutti gli elementi recenti.</span><span class="sxs-lookup"><span data-stu-id="514d7-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="514d7-182">Impostare le opzioni di protezione e ripristino ransomware</span><span class="sxs-lookup"><span data-stu-id="514d7-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="514d7-183">Apri l Sicurezza di Windows app cercando Sicurezza nel menu Start *e* quindi selezionando **Sicurezza di Windows**.</span><span class="sxs-lookup"><span data-stu-id="514d7-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="514d7-184">Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra).</span><span class="sxs-lookup"><span data-stu-id="514d7-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="514d7-185">In **Protezione ransomware** seleziona Gestisci protezione **ransomware.**</span><span class="sxs-lookup"><span data-stu-id="514d7-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="514d7-186">Per modificare le **impostazioni di accesso controllato** alle cartelle, vedere Protect important folders with Controlled folder [access](/microsoft-365/security/defender-endpoint/controlled-folders).</span><span class="sxs-lookup"><span data-stu-id="514d7-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="514d7-187">Per configurare le opzioni  di ripristino ransomware, selezionare Configura in Ripristino dati **ransomware** e seguire le istruzioni per collegare o configurare l'account OneDrive in modo da poter eseguire facilmente il ripristino da un attacco ransomware.</span><span class="sxs-lookup"><span data-stu-id="514d7-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="514d7-188">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="514d7-188">See also</span></span>
- [<span data-ttu-id="514d7-189">Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="514d7-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)