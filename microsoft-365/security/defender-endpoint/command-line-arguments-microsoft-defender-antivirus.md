---
title: Utilizzare la riga di comando per gestire Microsoft Defender Antivirus
description: Eseguire analisi di Microsoft Defender Antivirus e configurare la protezione di nuova generazione con un'utilità della riga di comando dedicata.
keywords: eseguire windows defender scan, eseguire l'analisi antivirus dalla riga di comando, eseguire windows defender scan dalla riga di comando, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 2b20227ac27b90d142d263dfa4522aa41319b9d5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690470"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="836fb-104">Configurare e gestire Microsoft Defender Antivirus con lo mpcmdrun.exe da riga di comando</span><span class="sxs-lookup"><span data-stu-id="836fb-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="836fb-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="836fb-105">**Applies to:**</span></span>

- [<span data-ttu-id="836fb-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="836fb-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="836fb-107">È possibile eseguire varie funzioni di Microsoft Defender Antivirus con lo strumento da riga di comando dedicato **mpcmdrun.exe**.</span><span class="sxs-lookup"><span data-stu-id="836fb-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="836fb-108">Questa utilità è utile quando si desidera automatizzare l'utilizzo di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="836fb-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="836fb-109">È possibile trovare l'utilità in `%ProgramFiles%\Windows Defender\MpCmdRun.exe` .</span><span class="sxs-lookup"><span data-stu-id="836fb-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="836fb-110">È necessario eseguirlo da un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="836fb-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="836fb-111">Potrebbe essere necessario aprire una versione a livello di amministratore del prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="836fb-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="836fb-112">Quando si cerca prompt **dei comandi** dal menu Start, scegliere Esegui **come amministratore.**</span><span class="sxs-lookup"><span data-stu-id="836fb-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="836fb-113">Se si esegue una versione aggiornata di Microsoft Defender Platform, eseguire `**MpCmdRun**` dal percorso seguente: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .</span><span class="sxs-lookup"><span data-stu-id="836fb-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

<span data-ttu-id="836fb-114">L'utilità dispone dei comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="836fb-114">The utility has the following commands:</span></span>

```console
MpCmdRun.exe [command] [-options]
```
<span data-ttu-id="836fb-115">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="836fb-115">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="836fb-116">Comando</span><span class="sxs-lookup"><span data-stu-id="836fb-116">Command</span></span>  | <span data-ttu-id="836fb-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="836fb-117">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="836fb-118">`-?`**o**`-h`</span><span class="sxs-lookup"><span data-stu-id="836fb-118">`-?` **or** `-h`</span></span>   | <span data-ttu-id="836fb-119">Visualizza tutte le opzioni disponibili per questo strumento</span><span class="sxs-lookup"><span data-stu-id="836fb-119">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="836fb-120">Esegue la ricerca di software dannoso.</span><span class="sxs-lookup"><span data-stu-id="836fb-120">Scans for malicious software.</span></span> <span data-ttu-id="836fb-121">I valori **per ScanType** sono: **0** Default, in base alla configurazione, **-1** Analisi rapida, **-2** Analisi completa, **-3** Analisi personalizzata di file e directory.</span><span class="sxs-lookup"><span data-stu-id="836fb-121">Values for **ScanType** are: **0** Default, according to your configuration, **-1** Quick scan, **-2** Full scan, **-3** File and directory custom scan.</span></span>  <span data-ttu-id="836fb-122">CpuThrottling rispetta la limitazione della CPU configurata dal criterio</span><span class="sxs-lookup"><span data-stu-id="836fb-122">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="836fb-123">Avvia l'analisi diagnostica</span><span class="sxs-lookup"><span data-stu-id="836fb-123">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="836fb-124">Raccoglie informazioni di supporto.</span><span class="sxs-lookup"><span data-stu-id="836fb-124">Collects support information.</span></span> <span data-ttu-id="836fb-125">Vedere '[Raccolta di dati di diagnostica](collect-diagnostic-data.md)'</span><span class="sxs-lookup"><span data-stu-id="836fb-125">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="836fb-126">Uguale a `-GetFiles` , ma viene restituito nella cartella Temporanea DiagTrack</span><span class="sxs-lookup"><span data-stu-id="836fb-126">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="836fb-127">Ripristina l'intelligence per la sicurezza installata su una copia di backup precedente o sul set predefinito originale</span><span class="sxs-lookup"><span data-stu-id="836fb-127">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="836fb-128">Rimuove solo l'intelligence per la sicurezza scaricata dinamicamente</span><span class="sxs-lookup"><span data-stu-id="836fb-128">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="836fb-129">Ripristina il motore installato precedente</span><span class="sxs-lookup"><span data-stu-id="836fb-129">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="836fb-130">Controlla la disponibilità di nuovi aggiornamenti di Security intelligence</span><span class="sxs-lookup"><span data-stu-id="836fb-130">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="836fb-131">Ripristina o elenca gli elementi in quarantena</span><span class="sxs-lookup"><span data-stu-id="836fb-131">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="836fb-132">Carica l'intelligence dinamica per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="836fb-132">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="836fb-133">Elenca l'intelligence dinamica per la sicurezza caricata</span><span class="sxs-lookup"><span data-stu-id="836fb-133">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="836fb-134">Rimuove l'intelligence per la sicurezza dinamica</span><span class="sxs-lookup"><span data-stu-id="836fb-134">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="836fb-135">Controlla se un percorso è escluso</span><span class="sxs-lookup"><span data-stu-id="836fb-135">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="836fb-136">Verifica che la rete possa comunicare con il servizio cloud Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="836fb-136">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="836fb-137">Questo comando funzionerà solo in Windows 10 versione 1703 o successiva.</span><span class="sxs-lookup"><span data-stu-id="836fb-137">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="836fb-138">Errori comuni nell'esecuzione di comandi tramite mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="836fb-138">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="836fb-139">Messaggio di errore</span><span class="sxs-lookup"><span data-stu-id="836fb-139">Error message</span></span> | <span data-ttu-id="836fb-140">Motivo possibile</span><span class="sxs-lookup"><span data-stu-id="836fb-140">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="836fb-141">Il servizio Microsoft Defender Antivirus è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="836fb-141">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="836fb-142">Abilitare il servizio e riprovare.</span><span class="sxs-lookup"><span data-stu-id="836fb-142">Enable the service and try again.</span></span> <br>   <span data-ttu-id="836fb-143">**Nota:**  In Windows 10 1909 o versioni precedenti e Windows Server 2019 o versioni precedenti, il servizio era denominato servizio "Windows Defender Antivirus".</span><span class="sxs-lookup"><span data-stu-id="836fb-143">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called "Windows Defender Antivirus" service.</span></span>|
| `0x80070667` | <span data-ttu-id="836fb-144">Il comando viene eseguito da `-ValidateMapsConnection` un computer con Windows 10 versione 1607 o precedente o Windows Server 2016 o versione precedente.</span><span class="sxs-lookup"><span data-stu-id="836fb-144">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="836fb-145">Eseguire il comando da un computer windows 10 versione 1703 o successiva o Windows Server 2019 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="836fb-145">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="836fb-146">Lo strumento deve essere eseguito da: o (dove gli aggiornamenti della piattaforma sono mensili ad `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` eccezione di `2012.4-0` marzo)</span><span class="sxs-lookup"><span data-stu-id="836fb-146">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="836fb-147">Privilegi insufficienti.</span><span class="sxs-lookup"><span data-stu-id="836fb-147">Not enough privileges.</span></span> <span data-ttu-id="836fb-148">Utilizzare il prompt dei comandi (cmd.exe) come amministratore.</span><span class="sxs-lookup"><span data-stu-id="836fb-148">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="836fb-149">Il firewall blocca la connessione o esegue l'ispezione SSL.</span><span class="sxs-lookup"><span data-stu-id="836fb-149">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="836fb-150">Possibili problemi correlati alla rete, come i problemi di risoluzione dei nomi</span><span class="sxs-lookup"><span data-stu-id="836fb-150">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="836fb-151">Il firewall blocca la connessione o esegue l'ispezione SSL.</span><span class="sxs-lookup"><span data-stu-id="836fb-151">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="836fb-152">Il firewall blocca la connessione o esegue l'ispezione SSL.</span><span class="sxs-lookup"><span data-stu-id="836fb-152">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="836fb-153">Il firewall blocca la connessione o esegue l'ispezione SSL.</span><span class="sxs-lookup"><span data-stu-id="836fb-153">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="836fb-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="836fb-154">See also</span></span>

- [<span data-ttu-id="836fb-155">Configurare le funzionalità di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="836fb-155">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="836fb-156">Gestire Microsoft Defender Antivirus nell'azienda</span><span class="sxs-lookup"><span data-stu-id="836fb-156">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="836fb-157">Argomenti di riferimento per gli strumenti di gestione e configurazione</span><span class="sxs-lookup"><span data-stu-id="836fb-157">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="836fb-158">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="836fb-158">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)