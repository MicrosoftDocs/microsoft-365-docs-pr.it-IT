---
title: Pianificare analisi regolari rapide e complete con Antivirus Microsoft Defender
description: Configurare analisi ricorrenti (pianificate), inclusa la data e l'ora in cui devono essere eseguite e se vengono eseguite come analisi complete o rapide
keywords: analisi rapida, analisi completa, rapida e completa, pianificazione dell'analisi, giornaliera, settimanale, ora, pianificata, ricorrente, regolare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f1344026878b7fbd6242d82b1afb0e6671c32073
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789269"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="23c9a-104">Configurare analisi pianificate rapide o complete di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="23c9a-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="23c9a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="23c9a-105">**Applies to:**</span></span>

- [<span data-ttu-id="23c9a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="23c9a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="23c9a-107">Per impostazione predefinita, Antivirus Microsoft Defender un aggiornamento 15 minuti prima dell'ora di qualsiasi analisi pianificata.</span><span class="sxs-lookup"><span data-stu-id="23c9a-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="23c9a-108">È possibile gestire la pianificazione per il momento in cui gli aggiornamenti di protezione [devono essere scaricati e applicati per](manage-protection-update-schedule-microsoft-defender-antivirus.md) ignorare questa impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="23c9a-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="23c9a-109">Oltre alla protezione sempre in tempo [](run-scan-microsoft-defender-antivirus.md) reale e alle analisi su richiesta, è possibile configurare analisi regolari e pianificate.</span><span class="sxs-lookup"><span data-stu-id="23c9a-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="23c9a-110">È possibile configurare il tipo di analisi, quando deve essere eseguita [](manage-protection-updates-microsoft-defender-antivirus.md) e se l'analisi deve essere eseguita dopo un aggiornamento della protezione o se l'endpoint è in uso.</span><span class="sxs-lookup"><span data-stu-id="23c9a-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="23c9a-111">È inoltre possibile specificare quando eseguire analisi speciali per completare la correzione.</span><span class="sxs-lookup"><span data-stu-id="23c9a-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="23c9a-112">In questo articolo viene descritto come configurare le analisi pianificate con Criteri di gruppo, cmdlet di PowerShell e WMI.</span><span class="sxs-lookup"><span data-stu-id="23c9a-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="23c9a-113">È inoltre possibile configurare le analisi delle pianificazioni [con Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) o [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span><span class="sxs-lookup"><span data-stu-id="23c9a-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="23c9a-114">Per configurare le impostazioni di Criteri di gruppo descritte in questo articolo</span><span class="sxs-lookup"><span data-stu-id="23c9a-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="23c9a-115">Nel computer di gestione di Criteri di gruppo, nell'Editor Criteri di gruppo, passare **a** Configurazione computer Modelli amministrativi  >    >  **Windows Componenti**  >  **Antivirus Microsoft Defender**  >  **Analisi**.</span><span class="sxs-lookup"><span data-stu-id="23c9a-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="23c9a-116">Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="23c9a-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="23c9a-117">Specificare le impostazioni per l'oggetto Criteri di gruppo e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="23c9a-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="23c9a-118">Ripetere i passaggi da 1 a 4 per ogni impostazione che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="23c9a-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="23c9a-119">Distribuire l'oggetto Criteri di gruppo come si fa normalmente.</span><span class="sxs-lookup"><span data-stu-id="23c9a-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="23c9a-120">Per assistenza con gli oggetti Criteri di gruppo, vedere [Create a Group Policy Object.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)</span><span class="sxs-lookup"><span data-stu-id="23c9a-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="23c9a-121">Vedere anche gli [argomenti Gestire quando scaricare e](manage-protection-update-schedule-microsoft-defender-antivirus.md) applicare gli aggiornamenti della protezione e Impedire o consentire agli utenti di modificare [localmente le impostazioni dei](configure-local-policy-overrides-microsoft-defender-antivirus.md) criteri.</span><span class="sxs-lookup"><span data-stu-id="23c9a-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="23c9a-122">Analisi rapida e analisi completa e analisi personalizzata</span><span class="sxs-lookup"><span data-stu-id="23c9a-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="23c9a-123">Quando si configurano analisi pianificate, è possibile specificare se l'analisi deve essere completa o rapida.</span><span class="sxs-lookup"><span data-stu-id="23c9a-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="23c9a-124">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="23c9a-124">Quick scan</span></span>  |<span data-ttu-id="23c9a-125">Analisi completa</span><span class="sxs-lookup"><span data-stu-id="23c9a-125">Full scan</span></span>  | <span data-ttu-id="23c9a-126">Analisi personalizzata</span><span class="sxs-lookup"><span data-stu-id="23c9a-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="23c9a-127">Un'analisi rapida esamina tutti i percorsi in cui potrebbe essere registrato malware per iniziare con il sistema, ad esempio le chiavi del Registro di sistema e le cartelle di avvio Windows note.</span><span class="sxs-lookup"><span data-stu-id="23c9a-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="23c9a-128">Nella maggior parte dei casi, un'analisi rapida è sufficiente ed è consigliata per le analisi pianificate.</span><span class="sxs-lookup"><span data-stu-id="23c9a-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="23c9a-129">Un'analisi completa inizia eseguendo un'analisi rapida e quindi continua con un'analisi sequenziale dei file di tutti i dischi fissi montati e delle unità rimovibili/di rete (se l'analisi completa è configurata per farlo).</span><span class="sxs-lookup"><span data-stu-id="23c9a-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="23c9a-130">Il completamento di un'analisi completa può richiedere alcune ore o giorni, a seconda della quantità e del tipo di dati da analizzare.</span><span class="sxs-lookup"><span data-stu-id="23c9a-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="23c9a-131">Al termine dell'analisi completa, è disponibile una nuova intelligence per la sicurezza ed è necessaria una nuova analisi per assicurarsi che non siano rilevate altre minacce con la nuova intelligence per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="23c9a-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="23c9a-132">Un'analisi personalizzata è un'analisi rapida eseguita sui file e sulle cartelle specificati.</span><span class="sxs-lookup"><span data-stu-id="23c9a-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="23c9a-133">Ad esempio, puoi scegliere di analizzare un'unità USB o una cartella specifica nell'unità locale del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23c9a-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="23c9a-134">Per impostazione predefinita, le analisi rapide vengono eseguite su dispositivi rimovibili montati, ad esempio unità USB.</span><span class="sxs-lookup"><span data-stu-id="23c9a-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="23c9a-135">Come è possibile sapere quale tipo di analisi scegliere?</span><span class="sxs-lookup"><span data-stu-id="23c9a-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="23c9a-136">Utilizzare la tabella seguente per scegliere un tipo di analisi.</span><span class="sxs-lookup"><span data-stu-id="23c9a-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="23c9a-137">Scenario</span><span class="sxs-lookup"><span data-stu-id="23c9a-137">Scenario</span></span>  |<span data-ttu-id="23c9a-138">Tipo di analisi consigliato</span><span class="sxs-lookup"><span data-stu-id="23c9a-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="23c9a-139">Si desidera configurare analisi regolari e pianificate</span><span class="sxs-lookup"><span data-stu-id="23c9a-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="23c9a-140">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="23c9a-140">Quick scan</span></span> <p><span data-ttu-id="23c9a-141">Un'analisi rapida controlla i processi, la memoria, i profili e alcune posizioni nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23c9a-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="23c9a-142">In combinazione con la protezione [in tempo](configure-real-time-protection-microsoft-defender-antivirus.md)reale sempre on, un'analisi rapida consente di fornire una copertura avanzata sia per il malware che inizia con il sistema che con il malware a livello di kernel.</span><span class="sxs-lookup"><span data-stu-id="23c9a-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="23c9a-143">La protezione in tempo reale esamina i file quando vengono aperti e chiusi e ogni volta che un utente passa a una cartella.</span><span class="sxs-lookup"><span data-stu-id="23c9a-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="23c9a-144">Minacce, ad esempio malware, vengono rilevate in un singolo dispositivo</span><span class="sxs-lookup"><span data-stu-id="23c9a-144">Threats, such as malware, are detected on an individual device</span></span>     | <span data-ttu-id="23c9a-145">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="23c9a-145">Quick scan</span></span> <p><span data-ttu-id="23c9a-146">Nella maggior parte dei casi, un'analisi rapida rileva e pulisce il malware rilevato.</span><span class="sxs-lookup"><span data-stu-id="23c9a-146">In most cases, a quick scan will catch and clean up detected malware.</span></span>   |
|<span data-ttu-id="23c9a-147">Si desidera eseguire [un'analisi su richiesta](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="23c9a-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="23c9a-148">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="23c9a-148">Quick scan</span></span>       |
| <span data-ttu-id="23c9a-149">Si desidera verificare che un dispositivo portatile, ad esempio un'unità USB, non contenga malware</span><span class="sxs-lookup"><span data-stu-id="23c9a-149">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="23c9a-150">Analisi personalizzata</span><span class="sxs-lookup"><span data-stu-id="23c9a-150">Custom scan</span></span> <p><span data-ttu-id="23c9a-151">Un'analisi personalizzata consente di selezionare percorsi, cartelle o file specifici ed esegue un'analisi rapida.</span><span class="sxs-lookup"><span data-stu-id="23c9a-151">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="23c9a-152">Altre informazioni sulle analisi rapide e complete</span><span class="sxs-lookup"><span data-stu-id="23c9a-152">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="23c9a-153">I file dannosi possono essere archiviati in posizioni non incluse in un'analisi rapida.</span><span class="sxs-lookup"><span data-stu-id="23c9a-153">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="23c9a-154">Tuttavia, la protezione sempre in tempo reale esamina tutti i file aperti e chiusi e tutti i file presenti in cartelle a cui un utente accede.</span><span class="sxs-lookup"><span data-stu-id="23c9a-154">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="23c9a-155">La combinazione di protezione in tempo reale e analisi rapida consente di garantire una protezione avanzata dal malware.</span><span class="sxs-lookup"><span data-stu-id="23c9a-155">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="23c9a-156">La protezione all'accesso con protezione garantita dal [cloud](cloud-protection-microsoft-defender-antivirus.md) garantisce che tutti i file a cui si accede nel sistema vengano analizzati con i modelli più recenti di security intelligence e machine learning cloud.</span><span class="sxs-lookup"><span data-stu-id="23c9a-156">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="23c9a-157">Quando la protezione in tempo reale rileva malware e l'estensione dei file interessati non viene determinata inizialmente, Antivirus Microsoft Defender avvia un'analisi completa come parte del processo di correzione.</span><span class="sxs-lookup"><span data-stu-id="23c9a-157">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="23c9a-158">Un'analisi completa può rilevare file dannosi non rilevati da altre analisi, ad esempio un'analisi rapida.</span><span class="sxs-lookup"><span data-stu-id="23c9a-158">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="23c9a-159">Tuttavia, un'analisi completa può richiedere un po' di tempo e utilizzare risorse di sistema preziose per il completamento.</span><span class="sxs-lookup"><span data-stu-id="23c9a-159">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="23c9a-160">Se un dispositivo è offline per un lungo periodo di tempo, il completamento di un'analisi completa può richiedere più tempo.</span><span class="sxs-lookup"><span data-stu-id="23c9a-160">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="23c9a-161">Configurare le analisi pianificate</span><span class="sxs-lookup"><span data-stu-id="23c9a-161">Set up scheduled scans</span></span>

<span data-ttu-id="23c9a-162">Le analisi pianificate vengono eseguite il giorno e l'ora specificati.</span><span class="sxs-lookup"><span data-stu-id="23c9a-162">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="23c9a-163">È possibile utilizzare Criteri di gruppo, PowerShell e WMI per configurare le analisi pianificate.</span><span class="sxs-lookup"><span data-stu-id="23c9a-163">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="23c9a-164">Se un dispositivo viene scollegato e in esecuzione a batteria durante un'analisi completa pianificata, l'analisi pianificata verrà interrotta con l'evento 1002, che indica che l'analisi è stata interrotta prima del completamento.</span><span class="sxs-lookup"><span data-stu-id="23c9a-164">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="23c9a-165">Antivirus Microsoft Defender verrà eseguita un'analisi completa alla successiva ora pianificata.</span><span class="sxs-lookup"><span data-stu-id="23c9a-165">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="23c9a-166">Utilizzare Criteri di gruppo per pianificare le analisi</span><span class="sxs-lookup"><span data-stu-id="23c9a-166">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="23c9a-167">Posizione</span><span class="sxs-lookup"><span data-stu-id="23c9a-167">Location</span></span> | <span data-ttu-id="23c9a-168">Impostazione</span><span class="sxs-lookup"><span data-stu-id="23c9a-168">Setting</span></span> | <span data-ttu-id="23c9a-169">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23c9a-169">Description</span></span> | <span data-ttu-id="23c9a-170">Impostazione predefinita (se non configurata)</span><span class="sxs-lookup"><span data-stu-id="23c9a-170">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="23c9a-171">Analisi</span><span class="sxs-lookup"><span data-stu-id="23c9a-171">Scan</span></span> | <span data-ttu-id="23c9a-172">Specificare il tipo di analisi da utilizzare per un'analisi pianificata</span><span class="sxs-lookup"><span data-stu-id="23c9a-172">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="23c9a-173">Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="23c9a-173">Quick scan</span></span> |
|<span data-ttu-id="23c9a-174">Analisi</span><span class="sxs-lookup"><span data-stu-id="23c9a-174">Scan</span></span> | <span data-ttu-id="23c9a-175">Specificare il giorno della settimana per l'esecuzione di un'analisi pianificata</span><span class="sxs-lookup"><span data-stu-id="23c9a-175">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="23c9a-176">Specificare il giorno (o mai) in cui eseguire un'analisi.</span><span class="sxs-lookup"><span data-stu-id="23c9a-176">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="23c9a-177">Mai</span><span class="sxs-lookup"><span data-stu-id="23c9a-177">Never</span></span> |
|<span data-ttu-id="23c9a-178">Analisi</span><span class="sxs-lookup"><span data-stu-id="23c9a-178">Scan</span></span> | <span data-ttu-id="23c9a-179">Specificare l'ora del giorno per l'esecuzione di un'analisi pianificata</span><span class="sxs-lookup"><span data-stu-id="23c9a-179">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="23c9a-180">Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per l'1 di notte).</span><span class="sxs-lookup"><span data-stu-id="23c9a-180">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="23c9a-181">02.00</span><span class="sxs-lookup"><span data-stu-id="23c9a-181">2 a.m.</span></span> |
|<span data-ttu-id="23c9a-182">Radice</span><span class="sxs-lookup"><span data-stu-id="23c9a-182">Root</span></span> | <span data-ttu-id="23c9a-183">Tempo attività programmato casuale</span><span class="sxs-lookup"><span data-stu-id="23c9a-183">Randomize scheduled task times</span></span> |<span data-ttu-id="23c9a-184">In Antivirus Microsoft Defender, randomizzare l'ora di inizio dell'analisi a qualsiasi intervallo da 0 a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="23c9a-184">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="23c9a-185">In [SCEP,](/mem/intune/protect/certificates-scep-configure)esegui analisi casuali a qualsiasi intervallo più o meno 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="23c9a-185">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="23c9a-186">Ciò può essere utile nelle macchine virtuali o nelle distribuzioni VDI.</span><span class="sxs-lookup"><span data-stu-id="23c9a-186">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="23c9a-187">Abilitato</span><span class="sxs-lookup"><span data-stu-id="23c9a-187">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="23c9a-188">Utilizzare i cmdlet di PowerShell per pianificare le analisi</span><span class="sxs-lookup"><span data-stu-id="23c9a-188">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="23c9a-189">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="23c9a-189">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="23c9a-190">Per ulteriori informazioni, vedere [Use PowerShell cmdlets to configure and run Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="23c9a-190">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="23c9a-191">Utilizzare Windows Management Instruction (WMI) per pianificare le analisi</span><span class="sxs-lookup"><span data-stu-id="23c9a-191">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="23c9a-192">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="23c9a-192">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="23c9a-193">Per altre informazioni e parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="23c9a-193">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="23c9a-194">Avviare analisi pianificate solo quando l'endpoint non è in uso</span><span class="sxs-lookup"><span data-stu-id="23c9a-194">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="23c9a-195">È possibile impostare l'analisi pianificata in modo che si verifichi solo quando l'endpoint è attivato ma non in uso con Criteri di gruppo, PowerShell o WMI.</span><span class="sxs-lookup"><span data-stu-id="23c9a-195">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="23c9a-196">Queste analisi non rispettano la configurazione della limitazione della CPU e sfruttano appieno le risorse disponibili per completare l'analisi il più velocemente possibile.</span><span class="sxs-lookup"><span data-stu-id="23c9a-196">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="23c9a-197">Utilizzare Criteri di gruppo per pianificare le analisi</span><span class="sxs-lookup"><span data-stu-id="23c9a-197">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="23c9a-198">Posizione</span><span class="sxs-lookup"><span data-stu-id="23c9a-198">Location</span></span> | <span data-ttu-id="23c9a-199">Impostazione</span><span class="sxs-lookup"><span data-stu-id="23c9a-199">Setting</span></span> | <span data-ttu-id="23c9a-200">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23c9a-200">Description</span></span> | <span data-ttu-id="23c9a-201">Impostazione predefinita (se non configurata)</span><span class="sxs-lookup"><span data-stu-id="23c9a-201">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="23c9a-202">Analisi</span><span class="sxs-lookup"><span data-stu-id="23c9a-202">Scan</span></span> | <span data-ttu-id="23c9a-203">Avviare l'analisi pianificata solo quando il computer è in uso ma non è in uso</span><span class="sxs-lookup"><span data-stu-id="23c9a-203">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="23c9a-204">Le analisi pianificate non verranno eseguite, a meno che il computer non sia in uso</span><span class="sxs-lookup"><span data-stu-id="23c9a-204">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="23c9a-205">Abilitato</span><span class="sxs-lookup"><span data-stu-id="23c9a-205">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="23c9a-206">Utilizzare i cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="23c9a-206">Use PowerShell cmdlets</span></span>

<span data-ttu-id="23c9a-207">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="23c9a-207">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="23c9a-208">Per altre informazioni, vedere [Usare i cmdlet di PowerShell per configurare ed eseguire Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [Cmdlet di Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="23c9a-208">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="23c9a-209">Utilizzare Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="23c9a-209">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="23c9a-210">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="23c9a-210">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="23c9a-211">Per altre informazioni sulle API e sui parametri consentiti, vedi Windows Defender [API WMIv2.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="23c9a-211">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="23c9a-212">Configurare quando eseguire le analisi complete per completare la correzione</span><span class="sxs-lookup"><span data-stu-id="23c9a-212">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="23c9a-213">Alcune minacce potrebbero richiedere un'analisi completa per completare la rimozione e la correzione.</span><span class="sxs-lookup"><span data-stu-id="23c9a-213">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="23c9a-214">È possibile specificare quando eseguire queste analisi con Criteri di gruppo, PowerShell o WMI.</span><span class="sxs-lookup"><span data-stu-id="23c9a-214">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="23c9a-215">Utilizzare Criteri di gruppo per pianificare le analisi necessarie per la correzione</span><span class="sxs-lookup"><span data-stu-id="23c9a-215">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="23c9a-216">Posizione</span><span class="sxs-lookup"><span data-stu-id="23c9a-216">Location</span></span> | <span data-ttu-id="23c9a-217">Impostazione</span><span class="sxs-lookup"><span data-stu-id="23c9a-217">Setting</span></span> | <span data-ttu-id="23c9a-218">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23c9a-218">Description</span></span> | <span data-ttu-id="23c9a-219">Impostazione predefinita (se non configurata)</span><span class="sxs-lookup"><span data-stu-id="23c9a-219">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="23c9a-220">Correzione</span><span class="sxs-lookup"><span data-stu-id="23c9a-220">Remediation</span></span> | <span data-ttu-id="23c9a-221">Specificare il giorno della settimana in cui eseguire un'analisi completa pianificata per completare la correzione</span><span class="sxs-lookup"><span data-stu-id="23c9a-221">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="23c9a-222">Specificare il giorno (o mai) in cui eseguire un'analisi.</span><span class="sxs-lookup"><span data-stu-id="23c9a-222">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="23c9a-223">Mai</span><span class="sxs-lookup"><span data-stu-id="23c9a-223">Never</span></span> |
|<span data-ttu-id="23c9a-224">Correzione</span><span class="sxs-lookup"><span data-stu-id="23c9a-224">Remediation</span></span> | <span data-ttu-id="23c9a-225">Specificare l'ora del giorno in cui eseguire un'analisi completa pianificata per completare la correzione</span><span class="sxs-lookup"><span data-stu-id="23c9a-225">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="23c9a-226">Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per le 13.00)</span><span class="sxs-lookup"><span data-stu-id="23c9a-226">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="23c9a-227">02.00</span><span class="sxs-lookup"><span data-stu-id="23c9a-227">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="23c9a-228">Utilizzare i cmdlet di PowerShell</span><span class="sxs-lookup"><span data-stu-id="23c9a-228">Use PowerShell cmdlets</span></span>

<span data-ttu-id="23c9a-229">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="23c9a-229">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="23c9a-230">Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Use [PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Antivirus Microsoft Defender run Antivirus Microsoft Defender and [Defender cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="23c9a-230">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="23c9a-231">Utilizzare Windows Management Instruction (WMI)</span><span class="sxs-lookup"><span data-stu-id="23c9a-231">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="23c9a-232">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="23c9a-232">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="23c9a-233">Per altre informazioni e parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="23c9a-233">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="23c9a-234">Configurare analisi rapide giornaliere</span><span class="sxs-lookup"><span data-stu-id="23c9a-234">Set up daily quick scans</span></span>

<span data-ttu-id="23c9a-235">È possibile abilitare un'analisi rapida giornaliera che può essere eseguita in aggiunta alle altre analisi pianificate con Criteri di gruppo, PowerShell o WMI.</span><span class="sxs-lookup"><span data-stu-id="23c9a-235">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="23c9a-236">Utilizzare Criteri di gruppo per pianificare le analisi giornaliere</span><span class="sxs-lookup"><span data-stu-id="23c9a-236">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="23c9a-237">Posizione</span><span class="sxs-lookup"><span data-stu-id="23c9a-237">Location</span></span> | <span data-ttu-id="23c9a-238">Impostazione</span><span class="sxs-lookup"><span data-stu-id="23c9a-238">Setting</span></span> | <span data-ttu-id="23c9a-239">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23c9a-239">Description</span></span> | <span data-ttu-id="23c9a-240">Impostazione predefinita (se non configurata)</span><span class="sxs-lookup"><span data-stu-id="23c9a-240">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="23c9a-241">Analisi</span><span class="sxs-lookup"><span data-stu-id="23c9a-241">Scan</span></span> | <span data-ttu-id="23c9a-242">Specificare l'intervallo per l'esecuzione di analisi rapide al giorno</span><span class="sxs-lookup"><span data-stu-id="23c9a-242">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="23c9a-243">Specificare il numero di ore che devono trascorrere prima della successiva analisi rapida.</span><span class="sxs-lookup"><span data-stu-id="23c9a-243">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="23c9a-244">Ad esempio, per eseguire ogni due ore, immettere **2**, per una volta al giorno, **immettere 24**.</span><span class="sxs-lookup"><span data-stu-id="23c9a-244">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="23c9a-245">Immettere **0 per** non eseguire mai un'analisi rapida giornaliera.</span><span class="sxs-lookup"><span data-stu-id="23c9a-245">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="23c9a-246">Mai</span><span class="sxs-lookup"><span data-stu-id="23c9a-246">Never</span></span> |
|<span data-ttu-id="23c9a-247">Analisi</span><span class="sxs-lookup"><span data-stu-id="23c9a-247">Scan</span></span> | <span data-ttu-id="23c9a-248">Specificare l'ora per un'analisi rapida giornaliera</span><span class="sxs-lookup"><span data-stu-id="23c9a-248">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="23c9a-249">Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per le 13.00)</span><span class="sxs-lookup"><span data-stu-id="23c9a-249">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="23c9a-250">02.00</span><span class="sxs-lookup"><span data-stu-id="23c9a-250">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="23c9a-251">Utilizzare i cmdlet di PowerShell per pianificare le analisi giornaliere</span><span class="sxs-lookup"><span data-stu-id="23c9a-251">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="23c9a-252">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="23c9a-252">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="23c9a-253">Per ulteriori informazioni su come utilizzare PowerShell con Antivirus Microsoft Defender, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per configurare ed eseguire Antivirus Microsoft Defender [e i cmdlet defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="23c9a-253">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="23c9a-254">Utilizzare Windows Management Instruction (WMI) per pianificare le analisi giornaliere</span><span class="sxs-lookup"><span data-stu-id="23c9a-254">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="23c9a-255">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="23c9a-255">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="23c9a-256">Per altre informazioni e parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="23c9a-256">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="23c9a-257">Abilitare le analisi dopo gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="23c9a-257">Enable scans after protection updates</span></span>

<span data-ttu-id="23c9a-258">È possibile forzare l'esecuzione di un'analisi dopo ogni [aggiornamento della protezione](manage-protection-updates-microsoft-defender-antivirus.md) con Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="23c9a-258">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="23c9a-259">Utilizzare Criteri di gruppo per pianificare le analisi dopo gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="23c9a-259">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="23c9a-260">Posizione</span><span class="sxs-lookup"><span data-stu-id="23c9a-260">Location</span></span> | <span data-ttu-id="23c9a-261">Impostazione</span><span class="sxs-lookup"><span data-stu-id="23c9a-261">Setting</span></span> | <span data-ttu-id="23c9a-262">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23c9a-262">Description</span></span> | <span data-ttu-id="23c9a-263">Impostazione predefinita (se non configurata)</span><span class="sxs-lookup"><span data-stu-id="23c9a-263">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="23c9a-264">Aggiornamenti delle firme</span><span class="sxs-lookup"><span data-stu-id="23c9a-264">Signature updates</span></span> | <span data-ttu-id="23c9a-265">Attivare l'analisi dopo l'aggiornamento di Security Intelligence</span><span class="sxs-lookup"><span data-stu-id="23c9a-265">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="23c9a-266">Un'analisi verrà eseguita immediatamente dopo il download di un nuovo aggiornamento della protezione</span><span class="sxs-lookup"><span data-stu-id="23c9a-266">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="23c9a-267">Abilitato</span><span class="sxs-lookup"><span data-stu-id="23c9a-267">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="23c9a-268">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23c9a-268">See also</span></span>

- [<span data-ttu-id="23c9a-269">Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri</span><span class="sxs-lookup"><span data-stu-id="23c9a-269">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="23c9a-270">Configurare ed eseguire analisi di Microsoft Defender Antivirus su richiesta</span><span class="sxs-lookup"><span data-stu-id="23c9a-270">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="23c9a-271">Configurare le opzioni di analisi di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="23c9a-271">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="23c9a-272">Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base</span><span class="sxs-lookup"><span data-stu-id="23c9a-272">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="23c9a-273">Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="23c9a-273">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="23c9a-274">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="23c9a-274">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)