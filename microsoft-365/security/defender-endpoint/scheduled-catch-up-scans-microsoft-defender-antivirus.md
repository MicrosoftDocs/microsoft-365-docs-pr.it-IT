---
title: Pianificare analisi regolari rapide e complete con Microsoft Defender Antivirus
description: Configurare analisi ricorrenti (pianificate), inclusa la data e l'ora in cui devono essere eseguite e se vengono eseguite come analisi complete o rapide
keywords: analisi rapida, analisi completa, rapida e completa, pianificazione dell'analisi, giornaliera, settimanale, ora, pianificata, ricorrente, regolare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691305"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="51729-104">Configurare analisi pianificate rapide o complete di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="51729-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="51729-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="51729-105">**Applies to:**</span></span>

- [<span data-ttu-id="51729-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="51729-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="51729-107">Per impostazione predefinita, Microsoft Defender Antivirus verifica la presenza di un aggiornamento 15 minuti prima dell'ora di qualsiasi analisi pianificata.</span><span class="sxs-lookup"><span data-stu-id="51729-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="51729-108">È possibile gestire la pianificazione per il momento in cui gli aggiornamenti di protezione [devono essere scaricati e applicati per](manage-protection-update-schedule-microsoft-defender-antivirus.md) ignorare questa impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="51729-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="51729-109">Oltre alla protezione sempre in tempo [](run-scan-microsoft-defender-antivirus.md) reale e alle analisi su richiesta, è possibile configurare analisi regolari e pianificate.</span><span class="sxs-lookup"><span data-stu-id="51729-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="51729-110">È possibile configurare il tipo di analisi, quando deve essere eseguita [](manage-protection-updates-microsoft-defender-antivirus.md) e se l'analisi deve essere eseguita dopo un aggiornamento della protezione o se l'endpoint è in uso.</span><span class="sxs-lookup"><span data-stu-id="51729-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="51729-111">È inoltre possibile specificare quando eseguire analisi speciali per completare la correzione.</span><span class="sxs-lookup"><span data-stu-id="51729-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="51729-112">In questo articolo viene descritto come configurare le analisi pianificate con Criteri di gruppo, cmdlet di PowerShell e WMI.</span><span class="sxs-lookup"><span data-stu-id="51729-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="51729-113">È inoltre possibile configurare le analisi delle pianificazioni con [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) o Microsoft [Intune.](/mem/intune/configuration/device-restrictions-windows-10)</span><span class="sxs-lookup"><span data-stu-id="51729-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="51729-114">Per configurare le impostazioni di Criteri di gruppo descritte in questo articolo</span><span class="sxs-lookup"><span data-stu-id="51729-114">To configure the Group Policy settings described in this article</span></span>

1.  <span data-ttu-id="51729-115">Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="51729-115">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="51729-116">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="51729-116">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="51729-117">Fare clic **su Modelli amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="51729-117">Click **Administrative templates**.</span></span>

5.  <span data-ttu-id="51729-118">Espandi l'albero **fino ai componenti di Windows > Microsoft Defender Antivirus** e quindi alla **posizione** specificata nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="51729-118">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

6. <span data-ttu-id="51729-119">Fai doppio clic **sull'impostazione del** criterio come specificato nella tabella seguente e imposta l'opzione sulla configurazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="51729-119">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> 

7. <span data-ttu-id="51729-120">Fare **clic su OK** e ripetere l'operazione per tutte le altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="51729-120">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="51729-121">Vedere anche gli [argomenti Gestire quando scaricare e](manage-protection-update-schedule-microsoft-defender-antivirus.md) applicare gli aggiornamenti della protezione e Impedire o consentire agli utenti di modificare [localmente le impostazioni dei](configure-local-policy-overrides-microsoft-defender-antivirus.md) criteri.</span><span class="sxs-lookup"><span data-stu-id="51729-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="51729-122">Analisi rapida e analisi completa e analisi personalizzata</span><span class="sxs-lookup"><span data-stu-id="51729-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="51729-123">Quando si configurano analisi pianificate, è possibile specificare se l'analisi deve essere completa o rapida.</span><span class="sxs-lookup"><span data-stu-id="51729-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>

<span data-ttu-id="51729-124">Le analisi rapide esaminano tutti i percorsi in cui potrebbe essere registrato malware per iniziare con il sistema, ad esempio le chiavi del Registro di sistema e le cartelle di avvio note di Windows.</span><span class="sxs-lookup"><span data-stu-id="51729-124">Quick scans look at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="51729-125">In combinazione con la funzionalità di protezione sempre in tempo [reale,](configure-real-time-protection-microsoft-defender-antivirus.md) che rivede i file quando vengono aperti e chiusi e ogni volta che un utente passa a una cartella, un'analisi rapida consente di fornire una copertura avanzata sia per il malware che inizia con il sistema che con il malware a livello di kernel.</span><span class="sxs-lookup"><span data-stu-id="51729-125">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md) - which reviews files when they are opened and closed, and whenever a user navigates to a folder - a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="51729-126">Nella maggior parte dei casi, ciò significa che un'analisi rapida è adeguata per trovare malware non raccolto dalla protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="51729-126">In most instances, this means a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="51729-127">Un'analisi completa può essere utile negli endpoint che hanno riscontrato una minaccia malware per identificare se sono presenti componenti inattivi che richiedono una pulizia più approfondita.</span><span class="sxs-lookup"><span data-stu-id="51729-127">A full scan can be useful on endpoints that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="51729-128">In questo caso, è possibile utilizzare un'analisi completa quando si esegue [un'analisi](run-scan-microsoft-defender-antivirus.md)su richiesta .</span><span class="sxs-lookup"><span data-stu-id="51729-128">In this instance, you may want to use a full scan when running an [on-demand scan](run-scan-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="51729-129">Un'analisi personalizzata consente di specificare i file e le cartelle da analizzare, ad esempio un'unità USB.</span><span class="sxs-lookup"><span data-stu-id="51729-129">A custom scan allows you to specify the files and folders to scan, such as a USB drive.</span></span> 

>[!NOTE]
><span data-ttu-id="51729-130">Per impostazione predefinita, le analisi rapide vengono eseguite su dispositivi rimovibili montati, ad esempio unità USB.</span><span class="sxs-lookup"><span data-stu-id="51729-130">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="51729-131">Configurare le analisi pianificate</span><span class="sxs-lookup"><span data-stu-id="51729-131">Set up scheduled scans</span></span>

<span data-ttu-id="51729-132">Le analisi pianificate verranno eseguite nel giorno e nell'ora specificate.</span><span class="sxs-lookup"><span data-stu-id="51729-132">Scheduled scans will run at the day and time you specify.</span></span> <span data-ttu-id="51729-133">È possibile utilizzare Criteri di gruppo, PowerShell e WMI per configurare le analisi pianificate.</span><span class="sxs-lookup"><span data-stu-id="51729-133">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

>[!NOTE]
><span data-ttu-id="51729-134">Se un computer viene scollegato e in esecuzione a batteria durante un'analisi completa pianificata, l'analisi pianificata verrà interrotta con l'evento 1002, che indica che l'analisi è stata interrotta prima del completamento.</span><span class="sxs-lookup"><span data-stu-id="51729-134">If a computer is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="51729-135">Microsoft Defender Antivirus eseguirà un'analisi completa alla successiva ora pianificata.</span><span class="sxs-lookup"><span data-stu-id="51729-135">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="51729-136">Utilizzare Criteri di gruppo per pianificare le analisi</span><span class="sxs-lookup"><span data-stu-id="51729-136">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="51729-137">Posizione</span><span class="sxs-lookup"><span data-stu-id="51729-137">Location</span></span> | <span data-ttu-id="51729-138">Impostazione</span><span class="sxs-lookup"><span data-stu-id="51729-138">Setting</span></span> | <span data-ttu-id="51729-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51729-139">Description</span></span> | <span data-ttu-id="51729-140">Impostazione predefinita (se non configurata)</span><span class="sxs-lookup"><span data-stu-id="51729-140">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="51729-141">Analisi</span><span class="sxs-lookup"><span data-stu-id="51729-141">Scan</span></span> | <span data-ttu-id="51729-142">Specificare il tipo di analisi da utilizzare per un'analisi pianificata</span><span class="sxs-lookup"><span data-stu-id="51729-142">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="51729-143">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="51729-143">Quick scan</span></span> |
|<span data-ttu-id="51729-144">Analisi</span><span class="sxs-lookup"><span data-stu-id="51729-144">Scan</span></span> | <span data-ttu-id="51729-145">Specificare il giorno della settimana per l'esecuzione di un'analisi pianificata</span><span class="sxs-lookup"><span data-stu-id="51729-145">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="51729-146">Specificare il giorno (o mai) in cui eseguire un'analisi.</span><span class="sxs-lookup"><span data-stu-id="51729-146">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="51729-147">Mai</span><span class="sxs-lookup"><span data-stu-id="51729-147">Never</span></span> |
|<span data-ttu-id="51729-148">Analisi</span><span class="sxs-lookup"><span data-stu-id="51729-148">Scan</span></span> | <span data-ttu-id="51729-149">Specificare l'ora del giorno per l'esecuzione di un'analisi pianificata</span><span class="sxs-lookup"><span data-stu-id="51729-149">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="51729-150">Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per l'1 di notte).</span><span class="sxs-lookup"><span data-stu-id="51729-150">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="51729-151">02.00</span><span class="sxs-lookup"><span data-stu-id="51729-151">2 a.m.</span></span> |
|<span data-ttu-id="51729-152">Radice</span><span class="sxs-lookup"><span data-stu-id="51729-152">Root</span></span> | <span data-ttu-id="51729-153">Tempo attività programmato casuale</span><span class="sxs-lookup"><span data-stu-id="51729-153">Randomize scheduled task times</span></span> |<span data-ttu-id="51729-154">In Microsoft Defender Antivirus: randomizzare l'ora di inizio dell'analisi a qualsiasi intervallo da 0 a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="51729-154">In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <br><span data-ttu-id="51729-155">In FEP/SCEP: randomizzare a qualsiasi intervallo più o meno 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="51729-155">In FEP/SCEP: randomize to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="51729-156">Ciò può essere utile nelle distribuzioni di vm o VDI.</span><span class="sxs-lookup"><span data-stu-id="51729-156">This can be useful in VM or VDI deployments.</span></span> | <span data-ttu-id="51729-157">Abilitato</span><span class="sxs-lookup"><span data-stu-id="51729-157">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="51729-158">Utilizzare i cmdlet di PowerShell per pianificare le analisi</span><span class="sxs-lookup"><span data-stu-id="51729-158">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="51729-159">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="51729-159">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="51729-160">Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="51729-160">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="51729-161">Utilizzare Windows Management Instruction (WMI) per pianificare le analisi</span><span class="sxs-lookup"><span data-stu-id="51729-161">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="51729-162">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="51729-162">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="51729-163">Per ulteriori informazioni e parametri consentiti, vedere:</span><span class="sxs-lookup"><span data-stu-id="51729-163">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="51729-164">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="51729-164">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="51729-165">Avviare analisi pianificate solo quando l'endpoint non è in uso</span><span class="sxs-lookup"><span data-stu-id="51729-165">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="51729-166">È possibile impostare l'analisi pianificata in modo che si verifichi solo quando l'endpoint è attivato ma non in uso con Criteri di gruppo, PowerShell o WMI.</span><span class="sxs-lookup"><span data-stu-id="51729-166">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="51729-167">Queste analisi non rispettano la configurazione della limitazione della CPU e sfruttano appieno le risorse disponibili per completare l'analisi il più velocemente possibile.</span><span class="sxs-lookup"><span data-stu-id="51729-167">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="51729-168">Utilizzare Criteri di gruppo per pianificare le analisi</span><span class="sxs-lookup"><span data-stu-id="51729-168">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="51729-169">Posizione</span><span class="sxs-lookup"><span data-stu-id="51729-169">Location</span></span> | <span data-ttu-id="51729-170">Impostazione</span><span class="sxs-lookup"><span data-stu-id="51729-170">Setting</span></span> | <span data-ttu-id="51729-171">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51729-171">Description</span></span> | <span data-ttu-id="51729-172">Impostazione predefinita (se non configurata)</span><span class="sxs-lookup"><span data-stu-id="51729-172">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="51729-173">Analisi</span><span class="sxs-lookup"><span data-stu-id="51729-173">Scan</span></span> | <span data-ttu-id="51729-174">Avviare l'analisi pianificata solo quando il computer è in uso ma non è in uso</span><span class="sxs-lookup"><span data-stu-id="51729-174">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="51729-175">Le analisi pianificate non verranno eseguite, a meno che il computer non sia in uso</span><span class="sxs-lookup"><span data-stu-id="51729-175">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="51729-176">Abilitato</span><span class="sxs-lookup"><span data-stu-id="51729-176">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="51729-177">Utilizzare i cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="51729-177">Use PowerShell cmdlets</span></span>

<span data-ttu-id="51729-178">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="51729-178">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="51729-179">Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="51729-179">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="51729-180">Usare Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="51729-180">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="51729-181">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="51729-181">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="51729-182">Per ulteriori informazioni e parametri consentiti, vedere:</span><span class="sxs-lookup"><span data-stu-id="51729-182">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="51729-183">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="51729-183">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="51729-184">Configurare quando eseguire le analisi complete per completare la correzione</span><span class="sxs-lookup"><span data-stu-id="51729-184">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="51729-185">Alcune minacce potrebbero richiedere un'analisi completa per completare la rimozione e la correzione.</span><span class="sxs-lookup"><span data-stu-id="51729-185">Some threats may require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="51729-186">È possibile pianificare quando eseguire queste analisi con Criteri di gruppo, PowerShell o WMI.</span><span class="sxs-lookup"><span data-stu-id="51729-186">You can schedule when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="51729-187">Utilizzare Criteri di gruppo per pianificare le analisi necessarie per la correzione</span><span class="sxs-lookup"><span data-stu-id="51729-187">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="51729-188">Posizione</span><span class="sxs-lookup"><span data-stu-id="51729-188">Location</span></span> | <span data-ttu-id="51729-189">Impostazione</span><span class="sxs-lookup"><span data-stu-id="51729-189">Setting</span></span> | <span data-ttu-id="51729-190">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51729-190">Description</span></span> | <span data-ttu-id="51729-191">Impostazione predefinita (se non configurata)</span><span class="sxs-lookup"><span data-stu-id="51729-191">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="51729-192">Correzione</span><span class="sxs-lookup"><span data-stu-id="51729-192">Remediation</span></span> | <span data-ttu-id="51729-193">Specificare il giorno della settimana in cui eseguire un'analisi completa pianificata per completare la correzione</span><span class="sxs-lookup"><span data-stu-id="51729-193">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="51729-194">Specificare il giorno (o mai) in cui eseguire un'analisi.</span><span class="sxs-lookup"><span data-stu-id="51729-194">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="51729-195">Mai</span><span class="sxs-lookup"><span data-stu-id="51729-195">Never</span></span> |
|<span data-ttu-id="51729-196">Correzione</span><span class="sxs-lookup"><span data-stu-id="51729-196">Remediation</span></span> | <span data-ttu-id="51729-197">Specificare l'ora del giorno in cui eseguire un'analisi completa pianificata per completare la correzione</span><span class="sxs-lookup"><span data-stu-id="51729-197">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="51729-198">Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per le 13.00)</span><span class="sxs-lookup"><span data-stu-id="51729-198">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="51729-199">02.00</span><span class="sxs-lookup"><span data-stu-id="51729-199">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="51729-200">Utilizzare i cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="51729-200">Use PowerShell cmdlets</span></span>

<span data-ttu-id="51729-201">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="51729-201">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="51729-202">Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="51729-202">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="51729-203">Usare Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="51729-203">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="51729-204">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="51729-204">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="51729-205">Per ulteriori informazioni e parametri consentiti, vedere:</span><span class="sxs-lookup"><span data-stu-id="51729-205">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="51729-206">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="51729-206">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="51729-207">Configurare analisi rapide giornaliere</span><span class="sxs-lookup"><span data-stu-id="51729-207">Set up daily quick scans</span></span>

<span data-ttu-id="51729-208">È possibile abilitare un'analisi rapida giornaliera che può essere eseguita in aggiunta alle altre analisi pianificate con Criteri di gruppo, PowerShell o WMI.</span><span class="sxs-lookup"><span data-stu-id="51729-208">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>


### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="51729-209">Utilizzare Criteri di gruppo per pianificare le analisi giornaliere</span><span class="sxs-lookup"><span data-stu-id="51729-209">Use Group Policy to schedule daily scans</span></span>


|<span data-ttu-id="51729-210">Posizione</span><span class="sxs-lookup"><span data-stu-id="51729-210">Location</span></span> | <span data-ttu-id="51729-211">Impostazione</span><span class="sxs-lookup"><span data-stu-id="51729-211">Setting</span></span> | <span data-ttu-id="51729-212">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51729-212">Description</span></span> | <span data-ttu-id="51729-213">Impostazione predefinita (se non configurata)</span><span class="sxs-lookup"><span data-stu-id="51729-213">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="51729-214">Analisi</span><span class="sxs-lookup"><span data-stu-id="51729-214">Scan</span></span> | <span data-ttu-id="51729-215">Specificare l'intervallo per l'esecuzione di analisi rapide al giorno</span><span class="sxs-lookup"><span data-stu-id="51729-215">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="51729-216">Specificare il numero di ore che devono trascorrere prima della successiva analisi rapida.</span><span class="sxs-lookup"><span data-stu-id="51729-216">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="51729-217">Ad esempio, per eseguire ogni due ore, immettere **2**, per una volta al giorno, **immettere 24**.</span><span class="sxs-lookup"><span data-stu-id="51729-217">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="51729-218">Immettere **0 per** non eseguire mai un'analisi rapida giornaliera.</span><span class="sxs-lookup"><span data-stu-id="51729-218">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="51729-219">Mai</span><span class="sxs-lookup"><span data-stu-id="51729-219">Never</span></span> |
|<span data-ttu-id="51729-220">Analisi</span><span class="sxs-lookup"><span data-stu-id="51729-220">Scan</span></span> | <span data-ttu-id="51729-221">Specificare l'ora per un'analisi rapida giornaliera</span><span class="sxs-lookup"><span data-stu-id="51729-221">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="51729-222">Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per le 13.00)</span><span class="sxs-lookup"><span data-stu-id="51729-222">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="51729-223">02.00</span><span class="sxs-lookup"><span data-stu-id="51729-223">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="51729-224">Utilizzare i cmdlet di PowerShell per pianificare le analisi giornaliere</span><span class="sxs-lookup"><span data-stu-id="51729-224">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="51729-225">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="51729-225">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="51729-226">Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="51729-226">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="51729-227">Utilizzare Windows Management Instruction (WMI) per pianificare le analisi giornaliere</span><span class="sxs-lookup"><span data-stu-id="51729-227">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="51729-228">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="51729-228">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="51729-229">Per ulteriori informazioni e parametri consentiti, vedere:</span><span class="sxs-lookup"><span data-stu-id="51729-229">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="51729-230">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="51729-230">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="51729-231">Abilitare le analisi dopo gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="51729-231">Enable scans after protection updates</span></span>

<span data-ttu-id="51729-232">È possibile forzare l'esecuzione di un'analisi dopo ogni [aggiornamento della protezione](manage-protection-updates-microsoft-defender-antivirus.md) con Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="51729-232">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="51729-233">Utilizzare Criteri di gruppo per pianificare le analisi dopo gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="51729-233">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="51729-234">Posizione</span><span class="sxs-lookup"><span data-stu-id="51729-234">Location</span></span> | <span data-ttu-id="51729-235">Impostazione</span><span class="sxs-lookup"><span data-stu-id="51729-235">Setting</span></span> | <span data-ttu-id="51729-236">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51729-236">Description</span></span> | <span data-ttu-id="51729-237">Impostazione predefinita (se non configurata)</span><span class="sxs-lookup"><span data-stu-id="51729-237">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="51729-238">Aggiornamenti delle firme</span><span class="sxs-lookup"><span data-stu-id="51729-238">Signature updates</span></span> | <span data-ttu-id="51729-239">Attivare l'analisi dopo l'aggiornamento di Security Intelligence</span><span class="sxs-lookup"><span data-stu-id="51729-239">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="51729-240">Un'analisi verrà eseguita immediatamente dopo il download di un nuovo aggiornamento della protezione</span><span class="sxs-lookup"><span data-stu-id="51729-240">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="51729-241">Abilitato</span><span class="sxs-lookup"><span data-stu-id="51729-241">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="51729-242">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51729-242">See also</span></span>
- [<span data-ttu-id="51729-243">Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri</span><span class="sxs-lookup"><span data-stu-id="51729-243">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="51729-244">Configurare ed eseguire analisi di Microsoft Defender Antivirus su richiesta</span><span class="sxs-lookup"><span data-stu-id="51729-244">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="51729-245">Configurare le opzioni di analisi di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="51729-245">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="51729-246">Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base</span><span class="sxs-lookup"><span data-stu-id="51729-246">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="51729-247">Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="51729-247">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="51729-248">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="51729-248">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)