---
title: Ripristinare i file in quarantena in Microsoft Defender AV
description: È possibile ripristinare i file e le cartelle messi in quarantena da Microsoft Defender AV.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/20/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3de9ddfc0cab12d2eea717c5d6b01e5b70b21213
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765792"
---
# <a name="restore-quarantined-files-in-microsoft-defender-av"></a><span data-ttu-id="eddb7-103">Ripristinare i file in quarantena in Microsoft Defender AV</span><span class="sxs-lookup"><span data-stu-id="eddb7-103">Restore quarantined files in Microsoft Defender AV</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="eddb7-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="eddb7-104">**Applies to:**</span></span>

- [<span data-ttu-id="eddb7-105">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="eddb7-105">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="eddb7-106">Se Microsoft Defender Antivirus è configurato per rilevare e correggere le minacce nel dispositivo, Microsoft Defender Antivirus messo in quarantena i file sospetti.</span><span class="sxs-lookup"><span data-stu-id="eddb7-106">If Microsoft Defender Antivirus is configured to detect and remediate threats on your device, Microsoft Defender Antivirus quarantines suspicious files.</span></span> <span data-ttu-id="eddb7-107">Se si è certi che un file in quarantena non sia una minaccia, è possibile ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="eddb7-107">If you are certain a quarantined file is not a threat, you can restore it.</span></span>

1. <span data-ttu-id="eddb7-108">Aprire **Sicurezza di Windows**.</span><span class="sxs-lookup"><span data-stu-id="eddb7-108">Open **Windows Security**.</span></span>
2. <span data-ttu-id="eddb7-109">Selezionare **Protezione da & virus e** quindi fare clic su Cronologia **protezione**.</span><span class="sxs-lookup"><span data-stu-id="eddb7-109">Select **Virus & threat protection** and then click **Protection history**.</span></span>
3. <span data-ttu-id="eddb7-110">Nell'elenco di tutti gli elementi recenti, filtrare in **base a Elementi in quarantena**.</span><span class="sxs-lookup"><span data-stu-id="eddb7-110">In the list of all recent items, filter on **Quarantined Items**.</span></span>
4. <span data-ttu-id="eddb7-111">Selezionare un elemento che si desidera mantenere ed eseguire un'azione, ad esempio il ripristino.</span><span class="sxs-lookup"><span data-stu-id="eddb7-111">Select an item you want to keep, and take an action, such as restore.</span></span>

> [!TIP]
> <span data-ttu-id="eddb7-112">Il ripristino di un file dalla quarantena può essere eseguito anche tramite il prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="eddb7-112">Restoring a file from quarantine can also be done using Command Prompt.</span></span> <span data-ttu-id="eddb7-113">Vedi [Ripristinare un file dalla quarantena.](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine)</span><span class="sxs-lookup"><span data-stu-id="eddb7-113">See [Restore a file from quarantine](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine).</span></span> 

## <a name="related-articles"></a><span data-ttu-id="eddb7-114">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="eddb7-114">Related articles</span></span>

- [<span data-ttu-id="eddb7-115">Configurare la correzione per le analisi</span><span class="sxs-lookup"><span data-stu-id="eddb7-115">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eddb7-116">Esaminare i risultati dell'analisi</span><span class="sxs-lookup"><span data-stu-id="eddb7-116">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eddb7-117">Configurare e convalidare le esclusioni in base al nome file, all'estensione e al percorso della cartella</span><span class="sxs-lookup"><span data-stu-id="eddb7-117">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eddb7-118">Configurare e convalidare le esclusioni per i file aperti dai processi</span><span class="sxs-lookup"><span data-stu-id="eddb7-118">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eddb7-119">Configurare le esclusioni di Microsoft Defender Antivirus in Windows Server</span><span class="sxs-lookup"><span data-stu-id="eddb7-119">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)