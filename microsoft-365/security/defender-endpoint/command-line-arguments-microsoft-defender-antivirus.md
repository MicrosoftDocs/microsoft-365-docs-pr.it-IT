---
title: Utilizzare la riga di comando per gestire Antivirus Microsoft Defender
description: Eseguire Antivirus Microsoft Defender analisi e configurare la protezione di nuova generazione con un'utilità della riga di comando dedicata.
keywords: eseguire windows defender scan, eseguire l'analisi antivirus dalla riga di comando, eseguire windows defender scan dalla riga di comando, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/17/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: eb7fa7fdf5b88bd9361176003817116bcbb1a087
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538904"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="9047c-104">Configurare e gestire Antivirus Microsoft Defender con lo mpcmdrun.exe da riga di comando</span><span class="sxs-lookup"><span data-stu-id="9047c-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

<span data-ttu-id="9047c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9047c-105">**Applies to:**</span></span>

- [<span data-ttu-id="9047c-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="9047c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9047c-107">È possibile eseguire varie Antivirus Microsoft Defender con lo strumento da riga di comando dedicato **mpcmdrun.exe**.</span><span class="sxs-lookup"><span data-stu-id="9047c-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="9047c-108">Questa utilità è utile quando si desidera automatizzare l Antivirus Microsoft Defender utilizzarsi.</span><span class="sxs-lookup"><span data-stu-id="9047c-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="9047c-109">È possibile trovare l'utilità in `%ProgramFiles%\Windows Defender\MpCmdRun.exe` .</span><span class="sxs-lookup"><span data-stu-id="9047c-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="9047c-110">È necessario eseguirlo da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9047c-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="9047c-111">Potrebbe essere necessario aprire una versione a livello di amministratore del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="9047c-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="9047c-112">Quando si cerca prompt **dei comandi** dal menu Start, scegliere Esegui **come amministratore.**</span><span class="sxs-lookup"><span data-stu-id="9047c-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="9047c-113">Se si esegue una versione aggiornata di Microsoft Defender Platform, eseguire `**MpCmdRun**` dal percorso seguente: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` .</span><span class="sxs-lookup"><span data-stu-id="9047c-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`.</span></span>
> <span data-ttu-id="9047c-114">Per ulteriori informazioni sulla piattaforma antimalware, vedere Antivirus Microsoft Defender [aggiornamenti e baseline.](manage-updates-baselines-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9047c-114">For more information about the antimalware platform, see [Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="9047c-115">L'utilità MpCmdRun utilizza la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9047c-115">The MpCmdRun utility uses the following syntax:</span></span>

```console
MpCmdRun.exe [command] [-options]
```

<span data-ttu-id="9047c-116">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="9047c-116">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="9047c-117">Comando</span><span class="sxs-lookup"><span data-stu-id="9047c-117">Command</span></span>  | <span data-ttu-id="9047c-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9047c-118">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="9047c-119">`-?`**o**`-h`</span><span class="sxs-lookup"><span data-stu-id="9047c-119">`-?` **or** `-h`</span></span>   | <span data-ttu-id="9047c-120">Visualizza tutte le opzioni disponibili per questo strumento</span><span class="sxs-lookup"><span data-stu-id="9047c-120">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="9047c-121">Esegue la ricerca di software dannoso.</span><span class="sxs-lookup"><span data-stu-id="9047c-121">Scans for malicious software.</span></span> <span data-ttu-id="9047c-122">I valori **per ScanType** sono:</span><span class="sxs-lookup"><span data-stu-id="9047c-122">Values for **ScanType** are:</span></span><p><span data-ttu-id="9047c-123">**0** Impostazione predefinita, in base alla configurazione</span><span class="sxs-lookup"><span data-stu-id="9047c-123">**0** Default, according to your configuration</span></span><p><span data-ttu-id="9047c-124">**-1** Analisi rapida</span><span class="sxs-lookup"><span data-stu-id="9047c-124">**-1** Quick scan</span></span><p><span data-ttu-id="9047c-125">**-2** Analisi completa</span><span class="sxs-lookup"><span data-stu-id="9047c-125">**-2** Full scan</span></span><p><span data-ttu-id="9047c-126">**-3** Analisi personalizzata di file e directory.</span><span class="sxs-lookup"><span data-stu-id="9047c-126">**-3** File and directory custom scan.</span></span><p><span data-ttu-id="9047c-127">CpuThrottling rispetta la limitazione della CPU configurata dal criterio</span><span class="sxs-lookup"><span data-stu-id="9047c-127">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="9047c-128">Avvia l'analisi diagnostica</span><span class="sxs-lookup"><span data-stu-id="9047c-128">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="9047c-129">Raccoglie informazioni di supporto.</span><span class="sxs-lookup"><span data-stu-id="9047c-129">Collects support information.</span></span> <span data-ttu-id="9047c-130">Vedere '[Raccolta di dati di diagnostica](collect-diagnostic-data.md)'</span><span class="sxs-lookup"><span data-stu-id="9047c-130">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="9047c-131">Uguale a `-GetFiles` , ma viene restituito nella cartella Temporanea DiagTrack</span><span class="sxs-lookup"><span data-stu-id="9047c-131">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="9047c-132">Ripristina l'intelligence per la sicurezza installata su una copia di backup precedente o sul set predefinito originale</span><span class="sxs-lookup"><span data-stu-id="9047c-132">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="9047c-133">Rimuove solo l'intelligence per la sicurezza scaricata dinamicamente</span><span class="sxs-lookup"><span data-stu-id="9047c-133">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="9047c-134">Ripristina il motore installato precedente</span><span class="sxs-lookup"><span data-stu-id="9047c-134">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="9047c-135">Controlla la disponibilità di nuovi aggiornamenti di Security intelligence</span><span class="sxs-lookup"><span data-stu-id="9047c-135">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="9047c-136">Ripristina o elenca gli elementi in quarantena</span><span class="sxs-lookup"><span data-stu-id="9047c-136">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="9047c-137">Carica l'intelligence dinamica per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="9047c-137">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="9047c-138">Elenca l'intelligence dinamica per la sicurezza caricata</span><span class="sxs-lookup"><span data-stu-id="9047c-138">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="9047c-139">Rimuove l'intelligence per la sicurezza dinamica</span><span class="sxs-lookup"><span data-stu-id="9047c-139">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="9047c-140">Controlla se un percorso è escluso</span><span class="sxs-lookup"><span data-stu-id="9047c-140">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="9047c-141">Verifica che la rete sia in grado di comunicare con il Antivirus Microsoft Defender cloud.</span><span class="sxs-lookup"><span data-stu-id="9047c-141">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="9047c-142">Questo comando funziona solo su Windows 10 versione 1703 o successiva.</span><span class="sxs-lookup"><span data-stu-id="9047c-142">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="9047c-143">Errori comuni nell'esecuzione di comandi tramite mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="9047c-143">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="9047c-144">Messaggio di errore</span><span class="sxs-lookup"><span data-stu-id="9047c-144">Error message</span></span> | <span data-ttu-id="9047c-145">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="9047c-145">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="9047c-146">Il Antivirus Microsoft Defender è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="9047c-146">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="9047c-147">Abilitare il servizio e riprovare.</span><span class="sxs-lookup"><span data-stu-id="9047c-147">Enable the service and try again.</span></span> <br>   <span data-ttu-id="9047c-148">**Nota:**  In Windows 10 1909 o versioni precedenti e Windows Server 2019 o versioni precedenti, il servizio era denominato Windows Defender Antivirus *servizio.*</span><span class="sxs-lookup"><span data-stu-id="9047c-148">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called the *Windows Defender Antivirus* service.</span></span>|
| `0x80070667` | <span data-ttu-id="9047c-149">Il comando viene eseguito da un computer Windows 10 versione 1607 o precedente o da Windows Server 2016 `-ValidateMapsConnection` o meno recente.</span><span class="sxs-lookup"><span data-stu-id="9047c-149">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="9047c-150">Eseguire il comando da un computer Windows 10 versione 1703 o successiva o Windows Server 2019 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="9047c-150">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="9047c-151">Lo strumento deve essere eseguito da: o (dove gli aggiornamenti della piattaforma sono mensili ad `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` eccezione di `2012.4-0` marzo)</span><span class="sxs-lookup"><span data-stu-id="9047c-151">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="9047c-152">Privilegi insufficienti.</span><span class="sxs-lookup"><span data-stu-id="9047c-152">Not enough privileges.</span></span> <span data-ttu-id="9047c-153">Utilizzare il prompt dei comandi (cmd.exe) come amministratore.</span><span class="sxs-lookup"><span data-stu-id="9047c-153">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="9047c-154">Il firewall blocca la connessione o esegue l'ispezione SSL.</span><span class="sxs-lookup"><span data-stu-id="9047c-154">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="9047c-155">Possibili problemi correlati alla rete, come i problemi di risoluzione dei nomi</span><span class="sxs-lookup"><span data-stu-id="9047c-155">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="9047c-156">Il firewall blocca la connessione o esegue l'ispezione SSL.</span><span class="sxs-lookup"><span data-stu-id="9047c-156">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="9047c-157">Il firewall blocca la connessione o esegue l'ispezione SSL.</span><span class="sxs-lookup"><span data-stu-id="9047c-157">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="9047c-158">Il firewall blocca la connessione o esegue l'ispezione SSL.</span><span class="sxs-lookup"><span data-stu-id="9047c-158">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="9047c-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9047c-159">See also</span></span>

- [<span data-ttu-id="9047c-160">Configurare la funzionalità di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="9047c-160">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="9047c-161">Gestire Antivirus Microsoft Defender nell'azienda</span><span class="sxs-lookup"><span data-stu-id="9047c-161">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9047c-162">Argomenti di riferimento per gli strumenti di gestione e configurazione</span><span class="sxs-lookup"><span data-stu-id="9047c-162">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9047c-163">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="9047c-163">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)