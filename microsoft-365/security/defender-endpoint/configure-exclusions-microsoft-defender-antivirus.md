---
title: Configurare le esclusioni per le analisi di Microsoft Defender AV
description: Puoi escludere i file (inclusi i file modificati da processi specificati) e le cartelle dall'analisi da Parte di Microsoft Defender AV. Convalidare le esclusioni con PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 47db9b4451a885c92ca4fda0f87f0150415d3338
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691509"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="82a54-104">Configurare e convalidare le esclusioni per le analisi di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="82a54-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="82a54-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="82a54-105">**Applies to:**</span></span>

- [<span data-ttu-id="82a54-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="82a54-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="82a54-107">Puoi escludere determinati file, cartelle, processi e file aperti dal processo dalle analisi di Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="82a54-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="82a54-108">Tali esclusioni si applicano [](run-scan-microsoft-defender-antivirus.md)alle analisi [pianificate,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)alle analisi su richiesta e alla protezione e al monitoraggio sempre in tempo [reale.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="82a54-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="82a54-109">Le esclusioni per i file aperti dal processo si applicano solo alla protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="82a54-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="82a54-110">Configurare e convalidare le esclusioni</span><span class="sxs-lookup"><span data-stu-id="82a54-110">Configure and validate exclusions</span></span>

<span data-ttu-id="82a54-111">Per configurare e convalidare le esclusioni, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="82a54-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="82a54-112">[Configurare e convalidare le esclusioni in base al nome file, all'estensione e al percorso della cartella.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="82a54-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="82a54-113">In questo modo è possibile escludere i file dalle analisi di Microsoft Defender Antivirus in base all'estensione, al nome file o al percorso.</span><span class="sxs-lookup"><span data-stu-id="82a54-113">This enables you to exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="82a54-114">[Configurare e convalidare le esclusioni per i file aperti dai processi](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="82a54-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="82a54-115">In questo modo è possibile escludere i file dalle analisi aperte da un processo specifico.</span><span class="sxs-lookup"><span data-stu-id="82a54-115">This enables you to exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="82a54-116">Suggerimenti per la definizione delle esclusioni</span><span class="sxs-lookup"><span data-stu-id="82a54-116">Recommendations for defining exclusions</span></span>

<span data-ttu-id="82a54-117">La definizione delle esclusioni riduce la protezione offerta da Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="82a54-117">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="82a54-118">È consigliabile valutare sempre i rischi associati all'implementazione delle esclusioni e escludere solo i file che si è certi non siano dannosi.</span><span class="sxs-lookup"><span data-stu-id="82a54-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="82a54-119">Di seguito è riportato un elenco di suggerimenti da tenere presenti quando si definiscono le esclusioni:</span><span class="sxs-lookup"><span data-stu-id="82a54-119">The following is a list of recommendations that you should keep in mind when defining exclusions:</span></span>  

- <span data-ttu-id="82a54-120">Le esclusioni sono tecnicamente una lacuna di protezione, sempre prendere in considerazione misure di prevenzione aggiuntive quando si definiscono le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="82a54-120">Exclusions are technically a protection gap—always consider additional mitigations when defining exclusions.</span></span> <span data-ttu-id="82a54-121">Misure di prevenzione aggiuntive possono essere semplici come assicurarsi che la posizione esclusa abbia gli elenchi di controllo di accesso (ACL) appropriati, i criteri di controllo, sia elaborato da un software aggiornato e così via.</span><span class="sxs-lookup"><span data-stu-id="82a54-121">Additional mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="82a54-122">Esaminare periodicamente le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="82a54-122">Review the exclusions periodically.</span></span> <span data-ttu-id="82a54-123">Rivedere e applicare di nuovo le mitigazioni nell'ambito del processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="82a54-123">Re-check and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="82a54-124">Idealmente, evitare di definire esclusioni proattive.</span><span class="sxs-lookup"><span data-stu-id="82a54-124">Ideally, avoid defining proactive exclusions.</span></span> <span data-ttu-id="82a54-125">Ad esempio, non escludere qualcosa solo perché si pensa che potrebbe essere un problema in futuro.</span><span class="sxs-lookup"><span data-stu-id="82a54-125">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="82a54-126">Utilizzare le esclusioni solo per problemi specifici, principalmente relativi alle prestazioni o a volte alla compatibilità delle applicazioni che le esclusioni potrebbero ridurre.</span><span class="sxs-lookup"><span data-stu-id="82a54-126">Use exclusions only for specific issues—mostly around performance, or sometimes around application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="82a54-127">Controllare le modifiche all'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="82a54-127">Audit the exclusion list changes.</span></span> <span data-ttu-id="82a54-128">L'amministratore della sicurezza deve conservare un contesto sufficiente per il motivo per cui è stata aggiunta una determinata esclusione.</span><span class="sxs-lookup"><span data-stu-id="82a54-128">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="82a54-129">Dovresti essere in grado di rispondere con un ragionamento specifico sul motivo per cui un determinato percorso è stato escluso.</span><span class="sxs-lookup"><span data-stu-id="82a54-129">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="82a54-130">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="82a54-130">Related articles</span></span>

- [<span data-ttu-id="82a54-131">Esclusioni di Microsoft Defender Antivirus in Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="82a54-131">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="82a54-132">Errori comuni da evitare durante la definizione delle esclusioni</span><span class="sxs-lookup"><span data-stu-id="82a54-132">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)