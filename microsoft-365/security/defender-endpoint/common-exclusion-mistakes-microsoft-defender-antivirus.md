---
title: Errori comuni da evitare durante la definizione delle esclusioni
description: Evitare errori comuni durante la definizione delle esclusioni per le analisi di Microsoft Defender Antivirus.
keywords: esclusioni, file, estensione, tipo di file, nome cartella, nome file, analisi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: eb3ac89eb05b39ff3337aa8e9c5ead1c308fbefb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764916"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Errori comuni da evitare durante la definizione delle esclusioni

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

Puoi definire un elenco di esclusione per gli elementi che non vuoi analizzare da Microsoft Defender Antivirus. Tali elementi esclusi potrebbero contenere minacce che rendono vulnerabile il dispositivo. 

In questo articolo vengono descritti alcuni errori comuni da evitare durante la definizione delle esclusioni. 

Prima di definire gli elenchi di esclusione, vedere [Suggerimenti per la definizione delle esclusioni.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)

## <a name="excluding-certain-trusted-items"></a>Esclusione di determinati elementi attendibili

Alcuni file, tipi di file, cartelle o processi non devono essere esclusi dall'analisi anche se si considera che non siano dannosi. 

Non definire esclusioni per i percorsi delle cartelle, le estensioni di file e i processi elencati nella tabella seguente:

| Percorsi delle cartelle | Estensioni file | Processi |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> `bginfo.exe`[1] <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> `msbuild.exe`[2] <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> È possibile scegliere di escludere tipi di file, ad esempio , , o se l'ambiente dispone di un software moderno e aggiornato con criteri di aggiornamento rigorosi per gestire eventuali `.gif` `.jpg` `.jpeg` `.png` vulnerabilità.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Utilizzo solo del nome file nell'elenco di esclusione

Un malware può avere lo stesso nome del file che si considera attendibile e che si desidera escludere dall'analisi. Pertanto, per evitare di escludere un potenziale malware dall'analisi, utilizzare un percorso completo del file che si desidera escludere invece di utilizzare solo il nome del file. Ad esempio, se si desidera escludere `Filename.exe` dall'analisi, utilizzare il percorso completo del file, ad esempio `C:\program files\contoso\Filename.exe` .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Utilizzo di un singolo elenco di esclusione per più carichi di lavoro del server

Non utilizzare un singolo elenco di esclusione per definire le esclusioni per più carichi di lavoro del server. Suddividere le esclusioni per carichi di lavoro di applicazioni o servizi diversi in più elenchi di esclusione. Ad esempio, l'elenco di esclusione per il carico di lavoro del server IIS deve essere diverso dall'elenco di esclusione per il carico SQL Server di lavoro.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Utilizzo di variabili di ambiente non corrette come caratteri jolly nel nome file e nel percorso della cartella o negli elenchi di esclusione delle estensioni

Il servizio Microsoft Defender Antivirus viene eseguito nel contesto di sistema utilizzando l'account LocalSystem, il che significa che ottiene informazioni dalla variabile di ambiente di sistema e non dalla variabile di ambiente utente. L'utilizzo delle variabili di ambiente come carattere jolly negli elenchi di esclusione è limitato alle variabili di sistema e a quelle applicabili ai processi in esecuzione come account NT AUTHORITY\SYSTEM. Pertanto, non utilizzare variabili di ambiente utente come caratteri jolly quando si aggiungono le esclusioni di processi e cartelle di Microsoft Defender Antivirus. Per un elenco completo delle [variabili di ambiente di](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) sistema, vedere la tabella in Variabili di ambiente di sistema.

Per informazioni su come utilizzare i caratteri jolly negli elenchi di esclusione dei nomi di file e dei percorsi delle cartelle o delle estensioni, vedere Use [wildcards in the file name and folder path or extension exclusion lists.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

## <a name="related-articles"></a>Articoli correlati

- [Configurare e convalidare le esclusioni nelle analisi di Microsoft Defender Antivirus](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurare e convalidare le esclusioni in base all'estensione di file e al percorso della cartella](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurare e convalidare le esclusioni per i file aperti dai processi](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Configurare le esclusioni di Microsoft Defender Antivirus in Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
