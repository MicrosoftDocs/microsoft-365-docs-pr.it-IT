---
title: Risolvere i problemi di AzCopy in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Risolvere gli errori per Azure AzCopy durante il caricamento di dati non di Office 365 per la correzione degli errori in Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919292"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="8a48f-103">Risolvere i problemi di AzCopy in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8a48f-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="8a48f-104">Quando si caricano dati o documenti non Di Microsoft 365 per la correzione degli errori in Advanced eDiscovery, l'interfaccia utente fornisce un comando Azure AzCopy che contiene i parametri con il percorso in cui vengono archiviati i file che si desidera caricare e il percorso di archiviazione di Azure in cui verranno caricati i file.</span><span class="sxs-lookup"><span data-stu-id="8a48f-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="8a48f-105">Per caricare i documenti, copiare questo comando ed eseguirlo in un prompt dei comandi nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="8a48f-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="8a48f-106">Lo screenshot seguente mostra un esempio di comando AzCopy:</span><span class="sxs-lookup"><span data-stu-id="8a48f-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Caricare file non Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="8a48f-108">In genere, il comando fornito funziona quando viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="8a48f-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="8a48f-109">Tuttavia, in alcuni casi il comando visualizzato non verrà eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8a48f-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="8a48f-110">Ecco alcuni possibili motivi.</span><span class="sxs-lookup"><span data-stu-id="8a48f-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="8a48f-111">La versione supportata di AzCopy non è installata nel computer locale</span><span class="sxs-lookup"><span data-stu-id="8a48f-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="8a48f-112">Al momento, è necessario utilizzare AzCopy v8.1 per caricare dati non Microsoft 365 in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="8a48f-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="8a48f-113">Il comando AzCopy visualizzato nella  pagina Carica file visualizzata nello screenshot precedente restituisce un errore se non si utilizza AzCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="8a48f-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="8a48f-114">Per installare questa versione, vedi [Trasferire dati con AzCopy v8.1 in Windows.](/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="8a48f-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="8a48f-115">AzCopy non è installato nel computer locale o non è installato nel percorso predefinito</span><span class="sxs-lookup"><span data-stu-id="8a48f-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="8a48f-116">Se AzCopy non è installato o è installato in un percorso diverso da quello di installazione predefinito (ovvero ), è possibile che venga visualizzato il seguente errore quando si esegue il `%ProgramFiles(x86)%` comando AzCopy:</span><span class="sxs-lookup"><span data-stu-id="8a48f-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="8a48f-117">Impossibile trovare il percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="8a48f-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="8a48f-118">Se AzCopy non è installato nel computer locale, è possibile trovare informazioni sull'installazione in Trasferire dati [con AzCopy v8.1 in Windows](/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="8a48f-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="8a48f-119">Assicurarsi di installarlo nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="8a48f-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="8a48f-120">Se AzCopy è installato, ma è installato in un percorso diverso da quello predefinito, è possibile copiare il comando, incollarlo in un file di testo e quindi modificare il percorso nel percorso in cui è installato AzCopy.</span><span class="sxs-lookup"><span data-stu-id="8a48f-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="8a48f-121">Ad esempio, se Azcopy si trova in , è possibile modificare la prima parte del `%ProgramFiles%` comando da `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` a `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` .</span><span class="sxs-lookup"><span data-stu-id="8a48f-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="8a48f-122">Dopo aver apportato questa modifica, copiarla dal file di testo ed eseguirla al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="8a48f-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="8a48f-123">Se AzCopy è installato in un percorso diverso, è consigliabile disinstallarlo e quindi reinstallarlo nel percorso predefinito.</span><span class="sxs-lookup"><span data-stu-id="8a48f-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="8a48f-124">Ciò consente di evitare questo problema in futuro.</span><span class="sxs-lookup"><span data-stu-id="8a48f-124">This will help prevent this issue in the future.</span></span>