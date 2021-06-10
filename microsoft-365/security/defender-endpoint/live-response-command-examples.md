---
title: Esempi di comandi di Live response
description: Scopri come eseguire comandi di risposta in tempo reale di base o avanzati per Microsoft Defender per Endpoint e vedere esempi su come viene usato.
keywords: ad esempio, command, cli, remote, shell, connection, live, response, real-time, command, script, remediate, hunt, export, log, drop, download, file
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f08f20753a1f0926abbbce01fe97f20ef1c07f2c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689090"
---
# <a name="live-response-command-examples"></a><span data-ttu-id="4b053-104">Esempi di comandi di Live response</span><span class="sxs-lookup"><span data-stu-id="4b053-104">Live response command examples</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4b053-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4b053-105">**Applies to:**</span></span>
- [<span data-ttu-id="4b053-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="4b053-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4b053-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4b053-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4b053-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4b053-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4b053-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="4b053-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="4b053-110">Informazioni sui comandi comuni usati in risposta in tempo reale e vedere esempi su come vengono utilizzati in genere.</span><span class="sxs-lookup"><span data-stu-id="4b053-110">Learn about common commands used in live response and see examples on how they are typically used.</span></span>

<span data-ttu-id="4b053-111">A seconda del ruolo che ti è stato concesso, puoi eseguire comandi di risposta in tempo reale di base o avanzati.</span><span class="sxs-lookup"><span data-stu-id="4b053-111">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="4b053-112">Per altre informazioni sui comandi di base e avanzati, vedi [Analizzare le entità nei dispositivi che usano la risposta in tempo reale.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="4b053-112">For more information on basic and advanced commands, see [Investigate entities on devices using live response](live-response.md).</span></span>


## <a name="analyze"></a><span data-ttu-id="4b053-113">analizzare</span><span class="sxs-lookup"><span data-stu-id="4b053-113">analyze</span></span> 

```
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a><span data-ttu-id="4b053-114">connessioni</span><span class="sxs-lookup"><span data-stu-id="4b053-114">connections</span></span>

```
# List active connections in json format using parameter name
connections -output json
```

```
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a><span data-ttu-id="4b053-115">dir</span><span class="sxs-lookup"><span data-stu-id="4b053-115">dir</span></span>

```
# List files and sub-folders in the current folder
dir
```

```
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a><span data-ttu-id="4b053-116">fileinfo</span><span class="sxs-lookup"><span data-stu-id="4b053-116">fileinfo</span></span>

```
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a><span data-ttu-id="4b053-117">findfile</span><span class="sxs-lookup"><span data-stu-id="4b053-117">findfile</span></span>

```
# Find file by name
findfile test.txt
```

## <a name="getfile"></a><span data-ttu-id="4b053-118">getfile</span><span class="sxs-lookup"><span data-stu-id="4b053-118">getfile</span></span>

```
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> <span data-ttu-id="4b053-119">I tipi di file seguenti **non possono** essere scaricati con questo comando da Live Response:</span><span class="sxs-lookup"><span data-stu-id="4b053-119">The following file types **cannot** be downloaded using this command from within Live Response:</span></span>
>
> * [<span data-ttu-id="4b053-120">File di reparse point</span><span class="sxs-lookup"><span data-stu-id="4b053-120">Reparse point files</span></span>](/windows/desktop/fileio/reparse-points/)
> * [<span data-ttu-id="4b053-121">File sparse</span><span class="sxs-lookup"><span data-stu-id="4b053-121">Sparse files</span></span>](/windows/desktop/fileio/sparse-files/)
> * <span data-ttu-id="4b053-122">File vuoti</span><span class="sxs-lookup"><span data-stu-id="4b053-122">Empty files</span></span>
> * <span data-ttu-id="4b053-123">File virtuali o file non completamente presenti in locale</span><span class="sxs-lookup"><span data-stu-id="4b053-123">Virtual files, or files that are not fully present locally</span></span>
>
> <span data-ttu-id="4b053-124">Questi tipi di file **sono** supportati da [PowerShell.](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="4b053-124">These file types **are** supported by [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).</span></span>
>
> <span data-ttu-id="4b053-125">Utilizzare PowerShell in alternativa, in caso di problemi durante l'utilizzo di questo comando da Live Response.</span><span class="sxs-lookup"><span data-stu-id="4b053-125">Use PowerShell as an alternative, if you have problems using this command from within Live Response.</span></span>

## <a name="processes"></a><span data-ttu-id="4b053-126">processi</span><span class="sxs-lookup"><span data-stu-id="4b053-126">processes</span></span>
```
# Show all processes
processes
```

```
# Get process by pid
processes 123
```

```
# Get process by pid with argument name
processes -pid 123
```

```
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a><span data-ttu-id="4b053-127">putfile</span><span class="sxs-lookup"><span data-stu-id="4b053-127">putfile</span></span>

```
# Upload file from library
putfile get-process-by-name.ps1
```

```
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a><span data-ttu-id="4b053-128">registro di sistema</span><span class="sxs-lookup"><span data-stu-id="4b053-128">registry</span></span>

```
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a><span data-ttu-id="4b053-129">correzione</span><span class="sxs-lookup"><span data-stu-id="4b053-129">remediate</span></span>

```
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```
# Remediate process with specific PID
remediate process 7960
```

```
# See list of all remediated entities
remediate list
```

## <a name="run"></a><span data-ttu-id="4b053-130">Correre</span><span class="sxs-lookup"><span data-stu-id="4b053-130">run</span></span>

```
# Run PowerShell script from the library without arguments
run script.ps1
```

```
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```
>[!NOTE]
>
> <span data-ttu-id="4b053-131">Per i comandi a esecuzione lunga, ad esempio '**run**' o '**getfile**', è possibile utilizzare il simbolo ' ' alla fine del comando per eseguire l'azione **&** in background.</span><span class="sxs-lookup"><span data-stu-id="4b053-131">For long running commands such as '**run**' or '**getfile**', you may want to use the '**&**' symbol at the end of the command to perform that action in the background.</span></span>
> <span data-ttu-id="4b053-132">In questo modo sarà possibile continuare a analizzare il computer e tornare al comando in background al termine dell'uso del comando di base '**fg** ['.](live-response.md#basic-commands)</span><span class="sxs-lookup"><span data-stu-id="4b053-132">This will allow you to continue investigating the machine and return to the background command when done using '**fg**' [basic command](live-response.md#basic-commands).</span></span>
>
## <a name="scheduledtask"></a><span data-ttu-id="4b053-133">scheduledtask</span><span class="sxs-lookup"><span data-stu-id="4b053-133">scheduledtask</span></span>

```
# Get all scheduled tasks
scheduledtasks
```

```
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```


## <a name="undo"></a><span data-ttu-id="4b053-134">annulla</span><span class="sxs-lookup"><span data-stu-id="4b053-134">undo</span></span>

```
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```

