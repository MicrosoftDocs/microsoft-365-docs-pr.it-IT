---
title: Risoluzione dei problemi relativi a AzCopy in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 3153fc92cfae6e2feba122cc895e787c9b573ef7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080899"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="bb758-102">Risoluzione dei problemi relativi a AzCopy in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bb758-102">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="bb758-103">Quando si caricano dati o documenti non di Office 365 per la correzione degli errori in Advanced eDiscovery, l'interfaccia utente fornisce un comando AzCopy di Azure che contiene parametri con il percorso in cui vengono archiviati i file che si desidera caricare e lo spazio di archiviazione di Azure percorso in cui verranno caricati i file.</span><span class="sxs-lookup"><span data-stu-id="bb758-103">When loading non-Office 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="bb758-104">Per caricare i documenti, è possibile copiare questo comando e quindi eseguirlo in un prompt dei comandi nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="bb758-104">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="bb758-105">Nello screenshot seguente è riportato un esempio di un comando AzCopy:</span><span class="sxs-lookup"><span data-stu-id="bb758-105">The follow screenshot shows an example of an AzCopy command:</span></span>

![Caricare i file non di Office 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="bb758-107">In genere, il comando fornito funziona quando lo si esegue.</span><span class="sxs-lookup"><span data-stu-id="bb758-107">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="bb758-108">Tuttavia, è possibile che i casi in cui il comando visualizzato non venga eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="bb758-108">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="bb758-109">Ecco alcuni possibili motivi.</span><span class="sxs-lookup"><span data-stu-id="bb758-109">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="bb758-110">La versione supportata di AzCopy non è installata nel computer locale</span><span class="sxs-lookup"><span data-stu-id="bb758-110">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="bb758-111">A questo punto, è necessario utilizzare AzCopy v 8.1 per caricare i dati non di Office 365 in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="bb758-111">At this time, you must use AzCopy v8.1 to load non-Office 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="bb758-112">Il comando AzCopy visualizzato nella pagina **Carica file** visualizzata nella schermata precedente restituisce un errore se non si utilizza AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="bb758-112">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="bb758-113">Per installare questa versione, vedere [trasferire dati con AzCopy v 8.1 in Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="bb758-113">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="bb758-114">AzCopy non è installato nel computer locale o non è installato nel percorso predefinito</span><span class="sxs-lookup"><span data-stu-id="bb758-114">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="bb758-115">Se AzCopy non è installato oppure è installato in un percorso diverso da quello predefinito (ovvero `%ProgramFiles(x86)%`), quando si esegue il comando AzCopy è possibile che venga visualizzato il messaggio di errore seguente:</span><span class="sxs-lookup"><span data-stu-id="bb758-115">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

    The system cannot find the path specified.

<span data-ttu-id="bb758-116">Se AzCopy non è installato nel computer locale, è possibile installarlo da [qui](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="bb758-116">If AzCopy isn't installed on the local computer, you can install from [here](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="bb758-117">Assicurarsi di installarlo nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="bb758-117">Be sure to install it in the default location.</span></span>

<span data-ttu-id="bb758-118">Se AzCopy è installato, ma è installato in una posizione diversa da quella predefinita, è possibile copiare il comando, incollarlo in un file di testo e quindi cambiare il percorso in cui è installato AzCopy.</span><span class="sxs-lookup"><span data-stu-id="bb758-118">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="bb758-119">Ad esempio, se si trova Azcopy `%ProgramFiles%`, è possibile modificare la prima parte del comando da `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` a. `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`</span><span class="sxs-lookup"><span data-stu-id="bb758-119">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="bb758-120">Dopo aver apportato questa modifica, copiarla dal file di testo e quindi eseguirla come prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="bb758-120">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="bb758-121">Se AzCopy è installato in un percorso diverso dal percorso di installazione predefinito, è consigliabile disinstallarlo e quindi reinstallarlo nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="bb758-121">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="bb758-122">Ciò consentirà di prevenire questo problema in futuro.</span><span class="sxs-lookup"><span data-stu-id="bb758-122">This will help prevent this issue in the future.</span></span>
