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
ms.date: 05/17/2021
ms.openlocfilehash: d10343538c995534878196cc57092c37fd2dcf7b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538064"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="8f7ce-104">Errori comuni da evitare quando si definiscono le esclusioni</span><span class="sxs-lookup"><span data-stu-id="8f7ce-104">Common mistakes to avoid when defining exclusions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8f7ce-105">È possibile definire un elenco di esclusione per gli elementi che non si desidera Antivirus Microsoft Defender analizzare.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="8f7ce-106">Tali elementi esclusi potrebbero contenere minacce che rendono vulnerabile il dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-106">Such excluded items could contain threats that make your device vulnerable.</span></span> 

<span data-ttu-id="8f7ce-107">In questo articolo vengono descritti alcuni errori comuni da evitare durante la definizione delle esclusioni.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="8f7ce-108">Prima di definire gli elenchi di esclusione, [vedere Consigli per la definizione delle esclusioni.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)</span><span class="sxs-lookup"><span data-stu-id="8f7ce-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="8f7ce-109">Esclusione di determinati elementi attendibili</span><span class="sxs-lookup"><span data-stu-id="8f7ce-109">Excluding certain trusted items</span></span>

<span data-ttu-id="8f7ce-110">Alcuni file, tipi di file, cartelle o processi non devono essere esclusi dall'analisi anche se si considera che non siano dannosi.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="8f7ce-111">Non definire esclusioni per i percorsi delle cartelle, le estensioni di file e i processi elencati nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f7ce-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following sections:</span></span>
- <span data-ttu-id="8f7ce-112">Percorsi delle cartelle</span><span class="sxs-lookup"><span data-stu-id="8f7ce-112">Folder locations</span></span>
- <span data-ttu-id="8f7ce-113">Estensioni file</span><span class="sxs-lookup"><span data-stu-id="8f7ce-113">File extensions</span></span>
- <span data-ttu-id="8f7ce-114">Processi</span><span class="sxs-lookup"><span data-stu-id="8f7ce-114">Processes</span></span>

### <a name="folder-locations"></a><span data-ttu-id="8f7ce-115">Percorsi delle cartelle</span><span class="sxs-lookup"><span data-stu-id="8f7ce-115">Folder locations</span></span>

<span data-ttu-id="8f7ce-116">In generale, non definire esclusioni per i percorsi di cartelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f7ce-116">In general, do not define exclusions for the following folder locations:</span></span>

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

<span data-ttu-id="8f7ce-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Si noti la seguente eccezione per SharePoint**: Non escludere quando si utilizza la protezione antivirus a livello di file in `C:\Users\ServiceAccount\AppData\Local\Temp` [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span><span class="sxs-lookup"><span data-stu-id="8f7ce-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\ServiceAccount\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

<span data-ttu-id="8f7ce-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Si noti la seguente eccezione per SharePoint**: Non escludere quando si utilizza la protezione antivirus a livello di file in `C:\Users\Default\AppData\Local\Temp` [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span><span class="sxs-lookup"><span data-stu-id="8f7ce-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\Default\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

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

### <a name="file-extensions"></a><span data-ttu-id="8f7ce-119">Estensioni file</span><span class="sxs-lookup"><span data-stu-id="8f7ce-119">File extensions</span></span>

<span data-ttu-id="8f7ce-120">In generale, non definire esclusioni per le estensioni di file seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f7ce-120">In general, do not define exclusions for the following file extensions:</span></span>

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

### <a name="processes"></a><span data-ttu-id="8f7ce-121">Processi</span><span class="sxs-lookup"><span data-stu-id="8f7ce-121">Processes</span></span> 

<span data-ttu-id="8f7ce-122">In generale, non definire esclusioni per i processi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f7ce-122">In general, do not define exclusions for the following processes:</span></span>

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
> <span data-ttu-id="8f7ce-123">È possibile scegliere di escludere tipi di file, ad esempio , , o se l'ambiente dispone di un software moderno e aggiornato con criteri di aggiornamento rigorosi per gestire eventuali `.gif` `.jpg` `.jpeg` `.png` vulnerabilità.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-123">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="8f7ce-124">Utilizzo solo del nome file nell'elenco di esclusione</span><span class="sxs-lookup"><span data-stu-id="8f7ce-124">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="8f7ce-125">Un malware può avere lo stesso nome del file che si considera attendibile e che si desidera escludere dall'analisi.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-125">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="8f7ce-126">Pertanto, per evitare di escludere un potenziale malware dall'analisi, utilizzare un percorso completo del file che si desidera escludere invece di utilizzare solo il nome del file.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-126">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="8f7ce-127">Ad esempio, se si desidera escludere `Filename.exe` dall'analisi, utilizzare il percorso completo del file, ad esempio `C:\program files\contoso\Filename.exe` .</span><span class="sxs-lookup"><span data-stu-id="8f7ce-127">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="8f7ce-128">Utilizzo di un singolo elenco di esclusione per più carichi di lavoro del server</span><span class="sxs-lookup"><span data-stu-id="8f7ce-128">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="8f7ce-129">Non utilizzare un singolo elenco di esclusione per definire le esclusioni per più carichi di lavoro del server.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-129">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="8f7ce-130">Suddividere le esclusioni per carichi di lavoro di applicazioni o servizi diversi in più elenchi di esclusione.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-130">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="8f7ce-131">Ad esempio, l'elenco di esclusione per il carico di lavoro del server IIS deve essere diverso dall'elenco di esclusione per il carico SQL Server di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-131">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="8f7ce-132">Utilizzo di variabili di ambiente non corrette come caratteri jolly nel nome file e nel percorso della cartella o negli elenchi di esclusione delle estensioni</span><span class="sxs-lookup"><span data-stu-id="8f7ce-132">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="8f7ce-133">Antivirus Microsoft Defender Il servizio viene eseguito nel contesto di sistema utilizzando l'account LocalSystem, il che significa che ottiene informazioni dalla variabile di ambiente di sistema e non dalla variabile di ambiente utente.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-133">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="8f7ce-134">L'utilizzo delle variabili di ambiente come carattere jolly negli elenchi di esclusione è limitato alle variabili di sistema e a quelle applicabili ai processi in esecuzione come account NT AUTHORITY\SYSTEM.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-134">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="8f7ce-135">Pertanto, non utilizzare variabili di ambiente utente come caratteri jolly quando si aggiungono Antivirus Microsoft Defender cartelle ed esclusioni di processo.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-135">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="8f7ce-136">Per un elenco completo delle [variabili di ambiente di](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) sistema, vedere la tabella in Variabili di ambiente di sistema.</span><span class="sxs-lookup"><span data-stu-id="8f7ce-136">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="8f7ce-137">Per informazioni su come utilizzare i caratteri jolly negli elenchi di esclusione dei nomi di file e dei percorsi delle cartelle o delle estensioni, vedere Use [wildcards in the file name and folder path or extension exclusion lists.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="8f7ce-137">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8f7ce-138">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="8f7ce-138">Related articles</span></span>

- [<span data-ttu-id="8f7ce-139">Configurare e convalidare le esclusioni Antivirus Microsoft Defender analisi</span><span class="sxs-lookup"><span data-stu-id="8f7ce-139">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8f7ce-140">Configurare e convalidare le esclusioni in base all'estensione di file e al percorso della cartella</span><span class="sxs-lookup"><span data-stu-id="8f7ce-140">Configure and validate exclusions based on file extension and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8f7ce-141">Configurare e convalidare le esclusioni per i file aperti dai processi</span><span class="sxs-lookup"><span data-stu-id="8f7ce-141">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8f7ce-142">Configurare Antivirus Microsoft Defender esclusioni in Windows Server</span><span class="sxs-lookup"><span data-stu-id="8f7ce-142">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
