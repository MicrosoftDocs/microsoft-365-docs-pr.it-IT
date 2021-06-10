---
title: Configurare Antivirus Microsoft Defender esclusioni in Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows Il server include esclusioni automatiche in base al ruolo del server. Puoi anche aggiungere esclusioni personalizzate.
keywords: esclusioni, server, esclusioni automatiche, automatiche, personalizzate, analisi, Antivirus Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.topic: article
ms.openlocfilehash: f82da8eb0dcba39404c2b7f191e166aa78357cee
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274761"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a><span data-ttu-id="530b8-105">Configurare Antivirus Microsoft Defender esclusioni in Windows Server</span><span class="sxs-lookup"><span data-stu-id="530b8-105">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="530b8-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="530b8-106">**Applies to:**</span></span>

- [<span data-ttu-id="530b8-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="530b8-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="530b8-108">Antivirus Microsoft Defender in Windows Server 2016 e Windows Server 2019 si registra automaticamente in determinate esclusioni, come definito dal ruolo del server specificato.</span><span class="sxs-lookup"><span data-stu-id="530b8-108">Microsoft Defender Antivirus on Windows Server 2016 and Windows Server 2019 automatically enrolls you in certain exclusions, as defined by your specified server role.</span></span> <span data-ttu-id="530b8-109">Queste esclusioni non vengono visualizzate negli elenchi di esclusione standard visualizzati [nell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="530b8-109">These exclusions do not appear in the standard exclusion lists that are shown in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="530b8-110">Le esclusioni automatiche si applicano solo all'analisi RTP (Real-Time Protection).</span><span class="sxs-lookup"><span data-stu-id="530b8-110">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="530b8-111">Le esclusioni automatiche non vengono rispettate durante un'analisi completa/rapida o su richiesta.</span><span class="sxs-lookup"><span data-stu-id="530b8-111">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>

<span data-ttu-id="530b8-112">Oltre alle esclusioni automatiche definite dal ruolo del server, è possibile aggiungere o rimuovere esclusioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="530b8-112">In addition to server role-defined automatic exclusions, you can add or remove custom exclusions.</span></span> <span data-ttu-id="530b8-113">A tale scopo, fare riferimento a questi articoli:</span><span class="sxs-lookup"><span data-stu-id="530b8-113">To do that, refer to these articles:</span></span>
- [<span data-ttu-id="530b8-114">Configurare e convalidare le esclusioni in base al nome file, all'estensione e al percorso della cartella</span><span class="sxs-lookup"><span data-stu-id="530b8-114">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="530b8-115">Configurare e convalidare le esclusioni per i file aperti dai processi</span><span class="sxs-lookup"><span data-stu-id="530b8-115">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a><span data-ttu-id="530b8-116">Alcuni punti da tenere presenti</span><span class="sxs-lookup"><span data-stu-id="530b8-116">A few points to keep in mind</span></span>

<span data-ttu-id="530b8-117">Tenere presenti i seguenti punti importanti:</span><span class="sxs-lookup"><span data-stu-id="530b8-117">Keep the following important points in mind:</span></span>

- <span data-ttu-id="530b8-118">Le esclusioni personalizzate hanno la precedenza rispetto alle esclusioni automatiche.</span><span class="sxs-lookup"><span data-stu-id="530b8-118">Custom exclusions take precedence over automatic exclusions.</span></span>
- <span data-ttu-id="530b8-119">Le esclusioni automatiche si applicano solo all'analisi RTP (Real-Time Protection).</span><span class="sxs-lookup"><span data-stu-id="530b8-119">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="530b8-120">Le esclusioni automatiche non vengono rispettate durante un'analisi completa/rapida o su richiesta.</span><span class="sxs-lookup"><span data-stu-id="530b8-120">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>
- <span data-ttu-id="530b8-121">Le esclusioni personalizzate e duplicate non sono in conflitto con le esclusioni automatiche.</span><span class="sxs-lookup"><span data-stu-id="530b8-121">Custom and duplicate exclusions do not conflict with automatic exclusions.</span></span>
- <span data-ttu-id="530b8-122">Antivirus Microsoft Defender vengono utilizzati gli strumenti Dism (Deployment Image Servicing and Management) per determinare quali ruoli sono installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="530b8-122">Microsoft Defender Antivirus uses the Deployment Image Servicing and Management (DISM) tools to determine which roles are installed on your computer.</span></span>

## <a name="opt-out-of-automatic-exclusions"></a><span data-ttu-id="530b8-123">Rifiutare esplicitamente le esclusioni automatiche</span><span class="sxs-lookup"><span data-stu-id="530b8-123">Opt out of automatic exclusions</span></span>

<span data-ttu-id="530b8-124">In Windows Server 2016 e Windows Server 2019, le esclusioni predefinite recapitate dagli aggiornamenti di Security Intelligence escludono solo i percorsi predefiniti per un ruolo o una funzionalità.</span><span class="sxs-lookup"><span data-stu-id="530b8-124">In Windows Server 2016 and Windows Server 2019, the predefined exclusions delivered by Security intelligence updates only exclude the default paths for a role or feature.</span></span> <span data-ttu-id="530b8-125">Se è stato installato un ruolo o una funzionalità in un percorso personalizzato o si desidera controllare manualmente il set di esclusioni, assicurarsi di rifiutare esplicitamente le esclusioni automatiche recapitate negli aggiornamenti di Security intelligence.</span><span class="sxs-lookup"><span data-stu-id="530b8-125">If you installed a role or feature in a custom path, or you want to manually control the set of exclusions, make sure to opt out of the automatic exclusions delivered in Security intelligence updates.</span></span> <span data-ttu-id="530b8-126">Tieni però presente che le esclusioni che vengono recapitate automaticamente sono ottimizzate per i ruoli Windows Server 2016 2019.</span><span class="sxs-lookup"><span data-stu-id="530b8-126">But keep in mind that the exclusions that are delivered automatically are optimized for Windows Server 2016 and 2019 roles.</span></span> <span data-ttu-id="530b8-127">Vedere [Consigli per definire le esclusioni prima](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) di definire gli elenchi di esclusione.</span><span class="sxs-lookup"><span data-stu-id="530b8-127">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

> [!WARNING]
> <span data-ttu-id="530b8-128">Il rifiuto esplicito delle esclusioni automatiche può influire negativamente sulle prestazioni o causare il danneggiamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="530b8-128">Opting out of automatic exclusions may adversely impact performance, or result in data corruption.</span></span> <span data-ttu-id="530b8-129">Le esclusioni che vengono recapitate automaticamente sono ottimizzate per Windows Server 2016 e Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="530b8-129">The exclusions that are delivered automatically are optimized for Windows Server 2016 and Windows Server 2019 roles.</span></span>

<span data-ttu-id="530b8-130">Poiché le esclusioni predefinite escludono solo i percorsi **predefiniti,** se si spostaNO NTDS e SYSVOL in un'altra unità o percorso diverso dal percorso *originale,* è necessario aggiungere le esclusioni manualmente utilizzando le informazioni [riportate qui.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)</span><span class="sxs-lookup"><span data-stu-id="530b8-130">Because predefined exclusions only exclude **default paths**, if you move NTDS and SYSVOL to another drive or path that is *different from the original path*, you must add exclusions manually using the information [here](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span></span>

<span data-ttu-id="530b8-131">È possibile disabilitare gli elenchi di esclusione automatica con Criteri di gruppo, cmdlet di PowerShell e WMI.</span><span class="sxs-lookup"><span data-stu-id="530b8-131">You can disable the automatic exclusion lists with Group Policy, PowerShell cmdlets, and WMI.</span></span>

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="530b8-132">Utilizzare Criteri di gruppo per disabilitare l'elenco delle esclusioni Windows Server 2016 e Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="530b8-132">Use Group Policy to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

1. <span data-ttu-id="530b8-133">Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="530b8-133">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span></span> <span data-ttu-id="530b8-134">Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="530b8-134">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>
2. <span data-ttu-id="530b8-135">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e quindi fare clic su **Modelli amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="530b8-135">In the **Group Policy Management Editor** go to **Computer configuration**, and then click **Administrative templates**.</span></span>
3. <span data-ttu-id="530b8-136">Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **esclusioni**.</span><span class="sxs-lookup"><span data-stu-id="530b8-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>
4. <span data-ttu-id="530b8-137">Fare doppio clic **su Disattiva esclusioni automatici** e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="530b8-137">Double-click **Turn off Auto Exclusions**, and set the option to **Enabled**.</span></span> <span data-ttu-id="530b8-138">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="530b8-138">Then click **OK**.</span></span> 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a><span data-ttu-id="530b8-139">Utilizzare i cmdlet di PowerShell per disabilitare l'elenco di esclusioni Windows Server 2016 2019</span><span class="sxs-lookup"><span data-stu-id="530b8-139">Use PowerShell cmdlets to disable the auto-exclusions list on Windows Server 2016 and 2019</span></span>

<span data-ttu-id="530b8-140">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="530b8-140">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

<span data-ttu-id="530b8-141">Per altre informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="530b8-141">To learn more, see the following resources:</span></span>

- <span data-ttu-id="530b8-142">[Utilizzare i cmdlet di PowerShell per configurare ed eseguire Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="530b8-142">[Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>
- <span data-ttu-id="530b8-143">[Usare PowerShell con Antivirus Microsoft Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="530b8-143">[Use PowerShell with Microsoft Defender Antivirus](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="530b8-144">Utilizzare Windows Management Instruction (WMI) per disabilitare l'elenco delle esclusioni automatici in Windows Server 2016 e Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="530b8-144">Use Windows Management Instruction (WMI) to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

<span data-ttu-id="530b8-145">Utilizzare il **metodo Set** della [classe MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="530b8-145">Use the **Set** method of the [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) class for the following properties:</span></span>

```WMI
DisableAutoExclusions
```

<span data-ttu-id="530b8-146">Per ulteriori informazioni e parametri consentiti, vedere:</span><span class="sxs-lookup"><span data-stu-id="530b8-146">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="530b8-147">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="530b8-147">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a><span data-ttu-id="530b8-148">Elenco delle esclusioni automatiche</span><span class="sxs-lookup"><span data-stu-id="530b8-148">List of automatic exclusions</span></span>

<span data-ttu-id="530b8-149">Le sezioni seguenti contengono le esclusioni che vengono recapitate con percorsi di file e tipi di file esclusioni automatiche.</span><span class="sxs-lookup"><span data-stu-id="530b8-149">The following sections contain the exclusions that are delivered with automatic exclusions file paths and file types.</span></span>

### <a name="default-exclusions-for-all-roles"></a><span data-ttu-id="530b8-150">Esclusioni predefinite per tutti i ruoli</span><span class="sxs-lookup"><span data-stu-id="530b8-150">Default exclusions for all roles</span></span>

<span data-ttu-id="530b8-151">In questa sezione sono elencate le esclusioni predefinite per tutti i ruoli Windows Server 2016 2019.</span><span class="sxs-lookup"><span data-stu-id="530b8-151">This section lists the default exclusions for all Windows Server 2016 and 2019 roles.</span></span>

> [!NOTE]
> <span data-ttu-id="530b8-152">I percorsi predefiniti potrebbero essere diversi da quelli elencati in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="530b8-152">The default locations could be different than what's listed in this article.</span></span>

#### <a name="windows-tempedb-files"></a><span data-ttu-id="530b8-153">Windows File "temp.edb"</span><span class="sxs-lookup"><span data-stu-id="530b8-153">Windows "temp.edb" files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a><span data-ttu-id="530b8-154">Windows Aggiornare i file o i file di aggiornamento automatico</span><span class="sxs-lookup"><span data-stu-id="530b8-154">Windows Update files or Automatic Update files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a><span data-ttu-id="530b8-155">Sicurezza di Windows file</span><span class="sxs-lookup"><span data-stu-id="530b8-155">Windows Security files</span></span>

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a><span data-ttu-id="530b8-156">File di Criteri di gruppo</span><span class="sxs-lookup"><span data-stu-id="530b8-156">Group Policy files</span></span>

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a><span data-ttu-id="530b8-157">File WINS</span><span class="sxs-lookup"><span data-stu-id="530b8-157">WINS files</span></span>

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a><span data-ttu-id="530b8-158">Esclusioni del servizio Replica file</span><span class="sxs-lookup"><span data-stu-id="530b8-158">File Replication Service (FRS) exclusions</span></span>

- <span data-ttu-id="530b8-159">File nella cartella di lavoro del servizio Replica file (FRS).</span><span class="sxs-lookup"><span data-stu-id="530b8-159">Files in the File Replication Service (FRS) working folder.</span></span> <span data-ttu-id="530b8-160">La cartella di lavoro FRS è specificata nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span><span class="sxs-lookup"><span data-stu-id="530b8-160">The FRS working folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span></span>

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- <span data-ttu-id="530b8-161">File di registro del database FRS.</span><span class="sxs-lookup"><span data-stu-id="530b8-161">FRS Database log files.</span></span> <span data-ttu-id="530b8-162">La cartella del file di registro del database FRS è specificata nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span><span class="sxs-lookup"><span data-stu-id="530b8-162">The FRS Database log file folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span></span>

  - `%windir%\Ntfrs\*\Edb\*.log`

- <span data-ttu-id="530b8-163">Cartella di gestione temporanea FRS.</span><span class="sxs-lookup"><span data-stu-id="530b8-163">The FRS staging folder.</span></span> <span data-ttu-id="530b8-164">La cartella di gestione temporanea è specificata nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span><span class="sxs-lookup"><span data-stu-id="530b8-164">The staging folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span></span>

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- <span data-ttu-id="530b8-165">Cartella di preinstallazione frs.</span><span class="sxs-lookup"><span data-stu-id="530b8-165">The FRS preinstall folder.</span></span> <span data-ttu-id="530b8-166">Questa cartella è specificata dalla cartella `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span><span class="sxs-lookup"><span data-stu-id="530b8-166">This folder is specified by the folder `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span></span>

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- <span data-ttu-id="530b8-167">Database DFSR (Distributed File System Replication) e cartelle di lavoro.</span><span class="sxs-lookup"><span data-stu-id="530b8-167">The Distributed File System Replication (DFSR) database and working folders.</span></span> <span data-ttu-id="530b8-168">Queste cartelle sono specificate dalla chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span><span class="sxs-lookup"><span data-stu-id="530b8-168">These folders are specified by the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span></span>

  > [!NOTE]
  > <span data-ttu-id="530b8-169">Per le posizioni personalizzate, vedi [Rifiutare esplicitamente le esclusioni automatiche.](#opt-out-of-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="530b8-169">For custom locations, see [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span></span>

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a><span data-ttu-id="530b8-170">Esclusioni di processi</span><span class="sxs-lookup"><span data-stu-id="530b8-170">Process exclusions</span></span>

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a><span data-ttu-id="530b8-171">Esclusioni Hyper-V</span><span class="sxs-lookup"><span data-stu-id="530b8-171">Hyper-V exclusions</span></span>

<span data-ttu-id="530b8-172">Nella tabella seguente sono elencate le esclusioni dei tipi di file, le esclusioni di cartelle e le esclusioni di processo che vengono recapitate automaticamente quando si installa il ruolo Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="530b8-172">The following table lists the file type exclusions, folder exclusions, and process exclusions that are delivered automatically when you install the Hyper-V role.</span></span>

|<span data-ttu-id="530b8-173">Esclusioni di tipi di file</span><span class="sxs-lookup"><span data-stu-id="530b8-173">File type exclusions</span></span> |<span data-ttu-id="530b8-174">Esclusioni di cartelle</span><span class="sxs-lookup"><span data-stu-id="530b8-174">Folder exclusions</span></span>  | <span data-ttu-id="530b8-175">Esclusioni di processi</span><span class="sxs-lookup"><span data-stu-id="530b8-175">Process exclusions</span></span> |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a><span data-ttu-id="530b8-176">File SYSVOL</span><span class="sxs-lookup"><span data-stu-id="530b8-176">SYSVOL files</span></span>

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a><span data-ttu-id="530b8-177">Esclusioni di Active Directory</span><span class="sxs-lookup"><span data-stu-id="530b8-177">Active Directory exclusions</span></span>

<span data-ttu-id="530b8-178">In questa sezione vengono elencate le esclusioni che vengono recapitate automaticamente quando si installa Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="530b8-178">This section lists the exclusions that are delivered automatically when you install Active Directory Domain Services.</span></span>

#### <a name="ntds-database-files"></a><span data-ttu-id="530b8-179">File di database NTDS</span><span class="sxs-lookup"><span data-stu-id="530b8-179">NTDS database files</span></span>

<span data-ttu-id="530b8-180">I file di database vengono specificati nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span><span class="sxs-lookup"><span data-stu-id="530b8-180">The database files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span></span>

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a><span data-ttu-id="530b8-181">File di registro delle transazioni di Servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="530b8-181">The AD DS transaction log files</span></span>

<span data-ttu-id="530b8-182">I file di registro delle transazioni sono specificati nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span><span class="sxs-lookup"><span data-stu-id="530b8-182">The transaction log files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span></span>

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a><span data-ttu-id="530b8-183">Cartella di lavoro NTDS</span><span class="sxs-lookup"><span data-stu-id="530b8-183">The NTDS working folder</span></span>

<span data-ttu-id="530b8-184">Questa cartella è specificata nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span><span class="sxs-lookup"><span data-stu-id="530b8-184">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span></span>

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a><span data-ttu-id="530b8-185">Esclusioni di processo per i file di supporto correlati a Servizi di dominio Active Directory e Servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="530b8-185">Process exclusions for AD DS and AD DS-related support files</span></span>

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a><span data-ttu-id="530b8-186">Esclusioni server DHCP</span><span class="sxs-lookup"><span data-stu-id="530b8-186">DHCP Server exclusions</span></span>

<span data-ttu-id="530b8-187">In questa sezione sono elencate le esclusioni che vengono recapitate automaticamente quando si installa il ruolo server DHCP.</span><span class="sxs-lookup"><span data-stu-id="530b8-187">This section lists the exclusions that are delivered automatically when you install the DHCP Server role.</span></span> <span data-ttu-id="530b8-188">I percorsi dei file del server DHCP sono specificati dai *parametri DatabasePath,* *DhcpLogFilePath* e *BackupDatabasePath* nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span><span class="sxs-lookup"><span data-stu-id="530b8-188">The DHCP Server file locations are specified by the *DatabasePath*, *DhcpLogFilePath*, and *BackupDatabasePath* parameters in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span></span>

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a><span data-ttu-id="530b8-189">Esclusioni server DNS</span><span class="sxs-lookup"><span data-stu-id="530b8-189">DNS Server exclusions</span></span>

<span data-ttu-id="530b8-190">In questa sezione sono elencate le esclusioni di file e cartelle e le esclusioni di processo che vengono recapitate automaticamente quando si installa il ruolo Server DNS.</span><span class="sxs-lookup"><span data-stu-id="530b8-190">This section lists the file and folder exclusions and the process exclusions that are delivered automatically when you install the DNS Server role.</span></span>

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a><span data-ttu-id="530b8-191">Esclusioni di file e cartelle per il ruolo Server DNS</span><span class="sxs-lookup"><span data-stu-id="530b8-191">File and folder exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a><span data-ttu-id="530b8-192">Elaborare le esclusioni per il ruolo server DNS</span><span class="sxs-lookup"><span data-stu-id="530b8-192">Process exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a><span data-ttu-id="530b8-193">Esclusioni di file e Archiviazione Services</span><span class="sxs-lookup"><span data-stu-id="530b8-193">File and Storage Services exclusions</span></span>

<span data-ttu-id="530b8-194">In questa sezione vengono elencate le esclusioni di file e cartelle che vengono recapitate automaticamente quando si installa il ruolo File e Archiviazione Services.</span><span class="sxs-lookup"><span data-stu-id="530b8-194">This section lists the file and folder exclusions that are delivered automatically when you install the File and Storage Services role.</span></span> <span data-ttu-id="530b8-195">Le esclusioni elencate di seguito non includono le esclusioni per il ruolo Clustering.</span><span class="sxs-lookup"><span data-stu-id="530b8-195">The exclusions listed below do not include exclusions for the Clustering role.</span></span>

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a><span data-ttu-id="530b8-196">Esclusioni server di stampa</span><span class="sxs-lookup"><span data-stu-id="530b8-196">Print Server exclusions</span></span>

<span data-ttu-id="530b8-197">In questa sezione sono elencate le esclusioni dei tipi di file, le esclusioni di cartelle e le esclusioni di processo che vengono recapitate automaticamente quando si installa il ruolo Server di stampa.</span><span class="sxs-lookup"><span data-stu-id="530b8-197">This section lists the file type exclusions, folder exclusions, and the process exclusions that are delivered automatically when you install the Print Server role.</span></span>

#### <a name="file-type-exclusions"></a><span data-ttu-id="530b8-198">Esclusioni di tipi di file</span><span class="sxs-lookup"><span data-stu-id="530b8-198">File type exclusions</span></span>

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a><span data-ttu-id="530b8-199">Esclusioni di cartelle</span><span class="sxs-lookup"><span data-stu-id="530b8-199">Folder exclusions</span></span>

<span data-ttu-id="530b8-200">Questa cartella è specificata nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span><span class="sxs-lookup"><span data-stu-id="530b8-200">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span></span>

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a><span data-ttu-id="530b8-201">Esclusioni di processi</span><span class="sxs-lookup"><span data-stu-id="530b8-201">Process exclusions</span></span>

- `spoolsv.exe`

### <a name="web-server-exclusions"></a><span data-ttu-id="530b8-202">Esclusioni server Web</span><span class="sxs-lookup"><span data-stu-id="530b8-202">Web Server exclusions</span></span>

<span data-ttu-id="530b8-203">In questa sezione vengono elencate le esclusioni di cartelle e le esclusioni di processo che vengono recapitate automaticamente quando si installa il ruolo server Web.</span><span class="sxs-lookup"><span data-stu-id="530b8-203">This section lists the folder exclusions and the process exclusions that are delivered automatically when you install the Web Server role.</span></span>

#### <a name="folder-exclusions"></a><span data-ttu-id="530b8-204">Esclusioni di cartelle</span><span class="sxs-lookup"><span data-stu-id="530b8-204">Folder exclusions</span></span>

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a><span data-ttu-id="530b8-205">Esclusioni di processi</span><span class="sxs-lookup"><span data-stu-id="530b8-205">Process exclusions</span></span>

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a><span data-ttu-id="530b8-206">Disattivazione dell'analisi dei file nella cartella Sysvol\Sysvol o nella cartella SYSVOL_DFSR\Sysvol</span><span class="sxs-lookup"><span data-stu-id="530b8-206">Turning off scanning of files in the Sysvol\Sysvol folder or the SYSVOL_DFSR\Sysvol folder</span></span>

<span data-ttu-id="530b8-207">Il percorso corrente della cartella o e di tutte le sottocartelle è la destinazione di analisi del file system della radice del `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` set di repliche.</span><span class="sxs-lookup"><span data-stu-id="530b8-207">The current location of the `Sysvol\Sysvol` or `SYSVOL_DFSR\Sysvol` folder and all the subfolders is the file system reparse target of the replica set root.</span></span> <span data-ttu-id="530b8-208">Per `Sysvol\Sysvol` impostazione predefinita, le cartelle e `SYSVOL_DFSR\Sysvol` utilizzano i percorsi seguenti:</span><span class="sxs-lookup"><span data-stu-id="530b8-208">The `Sysvol\Sysvol` and `SYSVOL_DFSR\Sysvol` folders use the following locations by default:</span></span>

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

<span data-ttu-id="530b8-209">Il percorso dell'oggetto attualmente attivo fa riferimento alla condivisione NETLOGON e può essere determinato dal nome del valore `SYSVOL` SysVol nella sottochiave seguente: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span><span class="sxs-lookup"><span data-stu-id="530b8-209">The path to the currently active `SYSVOL` is referenced by the NETLOGON share and can be determined by the SysVol value name in the following subkey: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span></span>

<span data-ttu-id="530b8-210">Escludere i file seguenti da questa cartella e da tutte le relative sottocartelle:</span><span class="sxs-lookup"><span data-stu-id="530b8-210">Exclude the following files from this folder and all its subfolders:</span></span>

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a><span data-ttu-id="530b8-211">Windows Server Update Services esclusioni</span><span class="sxs-lookup"><span data-stu-id="530b8-211">Windows Server Update Services exclusions</span></span>

<span data-ttu-id="530b8-212">In questa sezione vengono elencate le esclusioni di cartelle che vengono recapitate automaticamente quando si installa il ruolo Windows Server Update Services (WSUS).</span><span class="sxs-lookup"><span data-stu-id="530b8-212">This section lists the folder exclusions that are delivered automatically when you install the Windows Server Update Services (WSUS) role.</span></span> <span data-ttu-id="530b8-213">La cartella WSUS è specificata nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span><span class="sxs-lookup"><span data-stu-id="530b8-213">The WSUS folder is specified in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span></span>

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a><span data-ttu-id="530b8-214">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="530b8-214">See also</span></span>

- [<span data-ttu-id="530b8-215">Configurare e convalidare le esclusioni per Antivirus Microsoft Defender analisi</span><span class="sxs-lookup"><span data-stu-id="530b8-215">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="530b8-216">Configurare e convalidare le esclusioni in base al nome file, all'estensione e al percorso della cartella</span><span class="sxs-lookup"><span data-stu-id="530b8-216">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="530b8-217">Configurare e convalidare le esclusioni per i file aperti dai processi</span><span class="sxs-lookup"><span data-stu-id="530b8-217">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="530b8-218">Errori comuni da evitare quando si definiscono le esclusioni</span><span class="sxs-lookup"><span data-stu-id="530b8-218">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="530b8-219">Personalizzare, avviare ed esaminare i risultati di Antivirus Microsoft Defender analisi e correzione</span><span class="sxs-lookup"><span data-stu-id="530b8-219">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="530b8-220">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="530b8-220">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)