---
title: Configurare le esclusioni per Antivirus Microsoft Defender analisi
description: È possibile escludere i file (inclusi i file modificati da processi specificati) e le cartelle dall'analisi da Antivirus Microsoft Defender. Convalidare le esclusioni con PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275121"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="9dbb4-104">Configurare e convalidare le esclusioni per Antivirus Microsoft Defender analisi</span><span class="sxs-lookup"><span data-stu-id="9dbb4-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9dbb4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9dbb4-105">**Applies to:**</span></span>

- [<span data-ttu-id="9dbb4-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="9dbb4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9dbb4-107">È possibile escludere determinati file, cartelle, processi e file aperti dal processo Antivirus Microsoft Defender analisi.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="9dbb4-108">Tali esclusioni si applicano [](run-scan-microsoft-defender-antivirus.md)alle analisi [pianificate,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)alle analisi su richiesta e alla protezione e al monitoraggio sempre in tempo [reale.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9dbb4-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="9dbb4-109">Le esclusioni per i file aperti dal processo si applicano solo alla protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="9dbb4-110">Configurare e convalidare le esclusioni</span><span class="sxs-lookup"><span data-stu-id="9dbb4-110">Configure and validate exclusions</span></span>

<span data-ttu-id="9dbb4-111">Per configurare e convalidare le esclusioni, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9dbb4-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="9dbb4-112">[Configurare e convalidare le esclusioni in base al nome file, all'estensione e al percorso della cartella.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="9dbb4-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="9dbb4-113">È possibile escludere i file dalle Antivirus Microsoft Defender in base all'estensione, al nome file o al percorso.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-113">You can exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="9dbb4-114">[Configurare e convalidare le esclusioni per i file aperti dai processi](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="9dbb4-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="9dbb4-115">È possibile escludere i file dalle analisi aperte da un processo specifico.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-115">You can exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="9dbb4-116">Consigli per la definizione delle esclusioni</span><span class="sxs-lookup"><span data-stu-id="9dbb4-116">Recommendations for defining exclusions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9dbb4-117">Antivirus Microsoft Defender include molte esclusioni automatiche basate su comportamenti noti del sistema operativo e file di gestione tipici, ad esempio quelli utilizzati nella gestione aziendale, nella gestione dei database e in altri scenari e situazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
> 
> <span data-ttu-id="9dbb4-118">La definizione delle esclusioni riduce la protezione offerta da Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="9dbb4-119">È consigliabile valutare sempre i rischi associati all'implementazione delle esclusioni e escludere solo i file che si è certi non siano dannosi.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="9dbb4-120">Quando si definiscono le esclusioni, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9dbb4-120">Keep the following points in mind when you are defining exclusions:</span></span>  

- <span data-ttu-id="9dbb4-121">Le esclusioni sono tecnicamente un gap di protezione.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-121">Exclusions are technically a protection gap.</span></span> <span data-ttu-id="9dbb4-122">Considerare sempre le mitigazioni quando si definiscono le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-122">Always consider mitigations when defining exclusions.</span></span> <span data-ttu-id="9dbb4-123">Altre misure di prevenzione possono essere semplici come assicurarsi che la posizione esclusa abbia gli elenchi di controllo di accesso (ACL) appropriati, i criteri di controllo, sia elaborato da un software aggiornato e così via.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-123">Other mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="9dbb4-124">Esaminare periodicamente le esclusioni.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-124">Review the exclusions periodically.</span></span> <span data-ttu-id="9dbb4-125">Ricontrollare e applicare di nuovo le mitigazioni nell'ambito del processo di revisione.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-125">Recheck and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="9dbb4-126">Idealmente, evitare di definire esclusioni che intendono essere proattive.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-126">Ideally, avoid defining exclusions intending to be proactive.</span></span> <span data-ttu-id="9dbb4-127">Ad esempio, non escludere qualcosa solo perché si pensa che potrebbe essere un problema in futuro.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-127">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="9dbb4-128">Utilizzare le esclusioni solo per problemi specifici, ad esempio quelli relativi alle prestazioni o alla compatibilità delle applicazioni che le esclusioni potrebbero ridurre.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-128">Use exclusions only for specific issues, such as those pertaining to performance or application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="9dbb4-129">Controllare le modifiche all'elenco di esclusione.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-129">Audit the exclusion list changes.</span></span> <span data-ttu-id="9dbb4-130">L'amministratore della sicurezza deve conservare un contesto sufficiente per il motivo per cui è stata aggiunta una determinata esclusione.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-130">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="9dbb4-131">Dovresti essere in grado di rispondere con un ragionamento specifico sul motivo per cui un determinato percorso è stato escluso.</span><span class="sxs-lookup"><span data-stu-id="9dbb4-131">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9dbb4-132">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="9dbb4-132">Related articles</span></span>

- [<span data-ttu-id="9dbb4-133">Antivirus Microsoft Defender esclusioni in Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="9dbb4-133">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="9dbb4-134">Errori comuni da evitare quando si definiscono le esclusioni</span><span class="sxs-lookup"><span data-stu-id="9dbb4-134">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
