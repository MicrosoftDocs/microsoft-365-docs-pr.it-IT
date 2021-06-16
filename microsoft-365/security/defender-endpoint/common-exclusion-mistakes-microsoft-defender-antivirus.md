---
title: Errori comuni da evitare quando si definiscono le esclusioni
description: Evitare errori comuni durante la definizione delle esclusioni per Antivirus Microsoft Defender analisi.
keywords: esclusioni, file, estensione, tipo di file, nome cartella, nome file, analisi
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
ms.date: 06/15/2021
ms.openlocfilehash: f9ca83fcfba4b79898a0fed527e38947a4c230d6
ms.sourcegitcommit: 959c3c3633e40b7b0f5e2c8372409778005a24db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2021
ms.locfileid: "52950132"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Errori comuni da evitare quando si definiscono le esclusioni

È possibile definire un elenco di esclusione per gli elementi che non si desidera Antivirus Microsoft Defender analizzare. Tali elementi esclusi potrebbero contenere minacce che rendono vulnerabile il dispositivo. In questo articolo vengono descritti alcuni errori comuni da evitare durante la definizione delle esclusioni. 

Prima di definire gli elenchi di esclusione, [vedere Consigli per la definizione delle esclusioni.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)

## <a name="excluding-certain-trusted-items"></a>Esclusione di determinati elementi attendibili

Alcuni file, tipi di file, cartelle o processi non devono essere esclusi dall'analisi anche se si considera che non siano dannosi. 

Non definire esclusioni per i percorsi delle cartelle, le estensioni di file e i processi elencati nelle sezioni seguenti:
- Percorsi delle cartelle
- Estensioni file
- Processi

### <a name="folder-locations"></a>Percorsi delle cartelle

In generale, non definire esclusioni per i percorsi di cartelle seguenti:

`%systemdrive%` 

`C:`

`C:\`

`C:\*`

`%ProgramFiles%\Java`

`C:\Program Files\Java` 

`%ProgramFiles%\Contoso\` 

`C:\Program Files\Contoso\` 

`%ProgramFiles(x86)%\Contoso\` 

`C:\Program Files (x86)\Contoso\`

`C:\Temp`

`C:\Temp\`

`C:\Temp\*`

`C:\Users\`

`C:\Users\*`

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Si noti la seguente eccezione per SharePoint**: Non escludere quando si utilizza la protezione antivirus a livello di file in `C:\Users\ServiceAccount\AppData\Local\Temp` [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Si noti la seguente eccezione per SharePoint**: Non escludere quando si utilizza la protezione antivirus a livello di file in `C:\Users\Default\AppData\Local\Temp` [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).

`%Windir%\Prefetch`

`C:\Windows\Prefetch`

`C:\Windows\Prefetch\`

`C:\Windows\Prefetch\*`

`%Windir%\System32\Spool`

`C:\Windows\System32\Spool`

`C:\Windows\System32\CatRoot2`
`%Windir%\Temp`

`C:\Windows\Temp`

`C:\Windows\Temp\`

`C:\Windows\Temp\*`

### <a name="file-extensions"></a>Estensioni file

In generale, non definire esclusioni per le estensioni di file seguenti:

`.7z`

`.bat`

`.bin`

`.cab`

`.cmd`

`.com` 

`.cpl`

`.dll`

`.exe`

`.fla`

`.gif`

`.gz`

`.hta`

`.inf`

`.java`

`.jar`

`.job`

`.jpeg`

`.jpg`

`.js`

`.ko`

`.ko.gz`

`.msi`

`.ocx`

`.png`

`.ps1`

`.py`

`.rar`

`.reg`

`.scr`

`.sys`

`.tar`

`.tmp`

`.url`

`.vbe`

`.vbs`

`.wsf`

`.zip`

### <a name="processes"></a>Processi 

In generale, non definire esclusioni per i processi seguenti:

`AcroRd32.exe`  

`bitsadmin.exe`  

`excel.exe`  

`iexplore.exe`  

`java.exe`  

`outlook.exe`  

`psexec.exe`  

`powerpnt.exe`  

`powershell.exe`  

`schtasks.exe`

`svchost.exe` 

`wmic.exe`  

`winword.exe`  

`wuauclt.exe`  

`addinprocess.exe`  

`addinprocess32.exe`  

`addinutil.exe`  

`bash.exe`  

`bginfo.exe` 

`cdb.exe`  

`csi.exe`  

`dbghost.exe`  

`dbgsvc.exe`  

`dnx.exe`

`dotnet.exe`

`fsi.exe`  

`fsiAnyCpu.exe`  

`kd.exe`  

`ntkd.exe`  

`lxssmanager.dll`  

`msbuild.exe` 

`mshta.exe`  

`ntsd.exe`  

`rcsi.exe`  

`system.management.automation.dll`  

`windbg.exe`

> [!NOTE]
> È possibile scegliere di escludere tipi di file, ad esempio , , o se l'ambiente dispone di un software moderno e aggiornato con criteri di aggiornamento rigorosi per gestire eventuali `.gif` `.jpg` `.jpeg` `.png` vulnerabilità.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Utilizzo solo del nome file nell'elenco di esclusione

Un malware può avere lo stesso nome del file che si considera attendibile e che si desidera escludere dall'analisi. Pertanto, per evitare di escludere un potenziale malware dall'analisi, utilizzare un percorso completo del file che si desidera escludere invece di utilizzare solo il nome del file. Ad esempio, se si desidera escludere `Filename.exe` dall'analisi, utilizzare il percorso completo del file, ad esempio `C:\program files\contoso\Filename.exe` .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Utilizzo di un singolo elenco di esclusione per più carichi di lavoro del server

Non utilizzare un singolo elenco di esclusione per definire le esclusioni per più carichi di lavoro del server. Suddividere le esclusioni per carichi di lavoro di applicazioni o servizi diversi in più elenchi di esclusione. Ad esempio, l'elenco di esclusione per il carico di lavoro del server IIS deve essere diverso dall'elenco di esclusione per il carico SQL Server di lavoro.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Utilizzo di variabili di ambiente non corrette come caratteri jolly nel nome file e nel percorso della cartella o negli elenchi di esclusione delle estensioni

Antivirus Microsoft Defender Il servizio viene eseguito nel contesto di sistema utilizzando l'account LocalSystem, il che significa che ottiene informazioni dalla variabile di ambiente di sistema e non dalla variabile di ambiente utente. L'utilizzo delle variabili di ambiente come carattere jolly negli elenchi di esclusione è limitato alle variabili di sistema e a quelle applicabili ai processi in esecuzione come account NT AUTHORITY\SYSTEM. Pertanto, non utilizzare variabili di ambiente utente come caratteri jolly quando si aggiungono Antivirus Microsoft Defender cartelle ed esclusioni di processo. Per un elenco completo delle [variabili di ambiente di](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) sistema, vedere la tabella in Variabili di ambiente di sistema.

Per informazioni su come utilizzare i caratteri jolly negli elenchi di esclusione dei nomi di file e dei percorsi delle cartelle o delle estensioni, vedere Use [wildcards in the file name and folder path or extension exclusion lists.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

