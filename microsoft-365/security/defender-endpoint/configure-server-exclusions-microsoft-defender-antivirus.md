---
title: Configurare Antivirus Microsoft Defender esclusioni in Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows Il server include esclusioni automatiche in base al ruolo del server. Puoi anche aggiungere esclusioni personalizzate.
keywords: esclusioni, server, esclusioni automatiche, automatiche, personalizzate, analisi, Antivirus Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 02/10/2021
ms.openlocfilehash: 31d5c22d11a28c9604b2be3145ebd46715a6e5b3
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925516"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>Configurare Antivirus Microsoft Defender esclusioni in Windows Server


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Antivirus Microsoft Defender in Windows Server 2016 e Windows Server 2019 si registra automaticamente in determinate esclusioni, come definito dal ruolo del server specificato. Queste esclusioni non vengono visualizzate negli elenchi di esclusione standard visualizzati [nell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)

> [!NOTE]
> Le esclusioni automatiche si applicano solo all'analisi RTP (Real-Time Protection). Le esclusioni automatiche non vengono rispettate durante un'analisi completa/rapida o su richiesta.

Oltre alle esclusioni automatiche definite dal ruolo del server, è possibile aggiungere o rimuovere esclusioni personalizzate. A tale scopo, fare riferimento a questi articoli:
- [Configurare e convalidare le esclusioni in base al nome file, all'estensione e al percorso della cartella](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurare e convalidare le esclusioni per i file aperti dai processi](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a>Alcuni punti da tenere presenti

Tenere presenti i seguenti punti importanti:

- Le esclusioni personalizzate hanno la precedenza rispetto alle esclusioni automatiche.
- Le esclusioni automatiche si applicano solo all'analisi RTP (Real-Time Protection). Le esclusioni automatiche non vengono rispettate durante un'analisi completa/rapida o su richiesta.
- Le esclusioni personalizzate e duplicate non sono in conflitto con le esclusioni automatiche.
- Antivirus Microsoft Defender vengono utilizzati gli strumenti Dism (Deployment Image Servicing and Management) per determinare quali ruoli sono installati nel computer.

## <a name="opt-out-of-automatic-exclusions"></a>Rifiutare esplicitamente le esclusioni automatiche

In Windows Server 2016 e Windows Server 2019, le esclusioni predefinite recapitate dagli aggiornamenti di Security Intelligence escludono solo i percorsi predefiniti per un ruolo o una funzionalità. Se è stato installato un ruolo o una funzionalità in un percorso personalizzato o si desidera controllare manualmente il set di esclusioni, assicurarsi di rifiutare esplicitamente le esclusioni automatiche recapitate negli aggiornamenti di Security intelligence. Tieni però presente che le esclusioni che vengono recapitate automaticamente sono ottimizzate per i ruoli Windows Server 2016 2019. Vedere [Consigli per definire le esclusioni prima](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) di definire gli elenchi di esclusione.

> [!WARNING]
> Il rifiuto esplicito delle esclusioni automatiche può influire negativamente sulle prestazioni o causare il danneggiamento dei dati. Le esclusioni che vengono recapitate automaticamente sono ottimizzate per Windows Server 2016 e Windows Server 2019.

Poiché le esclusioni predefinite escludono solo i percorsi **predefiniti,** se si spostaNO NTDS e SYSVOL in un'altra unità o percorso diverso dal percorso *originale,* è necessario aggiungere le esclusioni manualmente utilizzando le informazioni [riportate qui.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)

È possibile disabilitare gli elenchi di esclusione automatica con Criteri di gruppo, cmdlet di PowerShell e WMI.

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Utilizzare Criteri di gruppo per disabilitare l'elenco delle esclusioni Windows Server 2016 e Windows Server 2019

1. Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)). Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.
2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e quindi fare clic su **Modelli amministrativi.**
3. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **esclusioni**.
4. Fare doppio clic **su Disattiva esclusioni automatici** e impostare l'opzione su **Abilitato.** Fare clic su **OK**. 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a>Utilizzare i cmdlet di PowerShell per disabilitare l'elenco di esclusioni Windows Server 2016 2019

Utilizzare i cmdlet seguenti:

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

Per altre informazioni, vedere le risorse seguenti:

- [Utilizzare i cmdlet di PowerShell per configurare ed eseguire Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md).
- [Usare PowerShell con Antivirus Microsoft Defender](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Utilizzare Windows Management Instruction (WMI) per disabilitare l'elenco delle esclusioni automatici in Windows Server 2016 e Windows Server 2019

Utilizzare il **metodo Set** della [classe MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) per le proprietà seguenti:

```WMI
DisableAutoExclusions
```

Per ulteriori informazioni e parametri consentiti, vedere:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a>Elenco delle esclusioni automatiche

Le sezioni seguenti contengono le esclusioni che vengono recapitate con percorsi di file e tipi di file esclusioni automatiche.

### <a name="default-exclusions-for-all-roles"></a>Esclusioni predefinite per tutti i ruoli

In questa sezione sono elencate le esclusioni predefinite per tutti i ruoli Windows Server 2016 2019.

> [!NOTE]
> I percorsi predefiniti potrebbero essere diversi da quelli elencati in questo articolo.

#### <a name="windows-tempedb-files"></a>Windows File "temp.edb"

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a>Windows Aggiornare i file o i file di aggiornamento automatico

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a>Sicurezza di Windows file

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a>File di Criteri di gruppo

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a>File WINS

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a>Esclusioni del servizio Replica file

- File nella cartella di lavoro del servizio Replica file (FRS). La cartella di lavoro FRS è specificata nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- File di registro del database FRS. La cartella del file di registro del database FRS è specificata nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- Cartella di gestione temporanea FRS. La cartella di gestione temporanea è specificata nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- Cartella di preinstallazione frs. Questa cartella è specificata dalla cartella `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- Database DFSR (Distributed File System Replication) e cartelle di lavoro. Queste cartelle sono specificate dalla chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > Per le posizioni personalizzate, vedi [Rifiutare esplicitamente le esclusioni automatiche.](#opt-out-of-automatic-exclusions)

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

#### <a name="process-exclusions"></a>Esclusioni di processi

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a>Esclusioni Hyper-V

Nella tabella seguente sono elencate le esclusioni dei tipi di file, le esclusioni di cartelle e le esclusioni di processo che vengono recapitate automaticamente quando si installa il ruolo Hyper-V.

|Esclusioni di tipi di file |Esclusioni di cartelle  | Esclusioni di processi |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a>File SYSVOL

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a>Esclusioni di Active Directory

In questa sezione vengono elencate le esclusioni che vengono recapitate automaticamente quando si installa Servizi di dominio Active Directory.

#### <a name="ntds-database-files"></a>File di database NTDS

I file di database vengono specificati nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a>File di registro delle transazioni di Servizi di dominio Active Directory

I file di registro delle transazioni sono specificati nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a>Cartella di lavoro NTDS

Questa cartella è specificata nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a>Esclusioni di processo per i file di supporto correlati a Servizi di dominio Active Directory e Servizi di dominio Active Directory

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a>Esclusioni server DHCP

In questa sezione sono elencate le esclusioni che vengono recapitate automaticamente quando si installa il ruolo server DHCP. I percorsi dei file del server DHCP sono specificati dai *parametri DatabasePath,* *DhcpLogFilePath* e *BackupDatabasePath* nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a>Esclusioni server DNS

In questa sezione sono elencate le esclusioni di file e cartelle e le esclusioni di processo che vengono recapitate automaticamente quando si installa il ruolo Server DNS.

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>Esclusioni di file e cartelle per il ruolo Server DNS

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a>Elaborare le esclusioni per il ruolo server DNS

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a>Esclusioni di file e Archiviazione Services

In questa sezione vengono elencate le esclusioni di file e cartelle che vengono recapitate automaticamente quando si installa il ruolo File e Archiviazione Services. Le esclusioni elencate di seguito non includono le esclusioni per il ruolo Clustering.

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a>Esclusioni server di stampa

In questa sezione sono elencate le esclusioni dei tipi di file, le esclusioni di cartelle e le esclusioni di processo che vengono recapitate automaticamente quando si installa il ruolo Server di stampa.

#### <a name="file-type-exclusions"></a>Esclusioni di tipi di file

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a>Esclusioni di cartelle

Questa cartella è specificata nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a>Esclusioni di processi

- `spoolsv.exe`

### <a name="web-server-exclusions"></a>Esclusioni server Web

In questa sezione vengono elencate le esclusioni di cartelle e le esclusioni di processo che vengono recapitate automaticamente quando si installa il ruolo server Web.

#### <a name="folder-exclusions"></a>Esclusioni di cartelle

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a>Esclusioni di processi

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>Disattivazione dell'analisi dei file nella cartella Sysvol\Sysvol o nella cartella SYSVOL_DFSR\Sysvol

Il percorso corrente della cartella o e di tutte le sottocartelle è la destinazione di analisi del file system della radice del `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` set di repliche. Per `Sysvol\Sysvol` impostazione predefinita, le cartelle e `SYSVOL_DFSR\Sysvol` utilizzano i percorsi seguenti:

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

Il percorso dell'oggetto attualmente attivo fa riferimento alla condivisione NETLOGON e può essere determinato dal nome del valore `SYSVOL` SysVol nella sottochiave seguente: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

Escludere i file seguenti da questa cartella e da tutte le relative sottocartelle:

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

### <a name="windows-server-update-services-exclusions"></a>Windows Server Update Services esclusioni

In questa sezione vengono elencate le esclusioni di cartelle che vengono recapitate automaticamente quando si installa il ruolo Windows Server Update Services (WSUS). La cartella WSUS è specificata nella chiave del Registro di sistema `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a>Vedere anche

- [Configurare e convalidare le esclusioni per Antivirus Microsoft Defender analisi](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurare e convalidare le esclusioni in base al nome file, all'estensione e al percorso della cartella](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurare e convalidare le esclusioni per i file aperti dai processi](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Errori comuni da evitare quando si definiscono le esclusioni](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Personalizzare, avviare ed esaminare i risultati di Antivirus Microsoft Defender analisi e correzione](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
