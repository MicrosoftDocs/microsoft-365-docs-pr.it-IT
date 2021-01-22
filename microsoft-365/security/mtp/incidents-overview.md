---
title: Panoramica degli eventi imprevisti in Microsoft 365 Defender
description: Analizzare gli eventi imprevisti visualizzati su dispositivi, utenti e cassette postali.
keywords: eventi, avvisi, analisi, correlazione, attacco, computer, dispositivi, utenti, identità, cassetta postale, posta elettronica, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7fcbecddd5e8f83e9c78d6db90939fbfc2f2df07
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929283"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="da17a-104">Panoramica degli eventi imprevisti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da17a-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="da17a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="da17a-105">**Applies to:**</span></span>
- <span data-ttu-id="da17a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da17a-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="da17a-107">Si vuole provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="da17a-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="da17a-108">È possibile [valutarlo in un ambiente lab o](https://aka.ms/mtp-trial-lab) eseguire il progetto pilota in [produzione.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="da17a-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="da17a-109">Gli eventi imprevisti si basano su avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="da17a-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="da17a-110">Gli avvisi vengono creati quando un'attività o un evento dannoso viene visualizzato nella rete.</span><span class="sxs-lookup"><span data-stu-id="da17a-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="da17a-111">I singoli avvisi forniscono preziose indicazioni su un attacco in corso.</span><span class="sxs-lookup"><span data-stu-id="da17a-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="da17a-112">Tuttavia, gli attacchi in genere utilizzano diversi vettori e tecniche per eseguire una violazione.</span><span class="sxs-lookup"><span data-stu-id="da17a-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="da17a-113">La torta di singoli indizi può essere impegnativa e dispendiosa in termini di tempo.</span><span class="sxs-lookup"><span data-stu-id="da17a-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="da17a-114">Questo breve video offre una panoramica degli incidenti in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="da17a-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="da17a-115">Un evento imprevisto è una raccolta di avvisi correlati che costituiscono la storia di un attacco.</span><span class="sxs-lookup"><span data-stu-id="da17a-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="da17a-116">Gli eventi dannosi e sospetti rilevati in entità di dispositivi, utenti e cassette postali diversi nella rete vengono aggregati automaticamente da Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="da17a-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="da17a-117">Il raggruppamento degli avvisi correlati in un evento imprevisto offre ai difensori della sicurezza una visualizzazione completa di un attacco.</span><span class="sxs-lookup"><span data-stu-id="da17a-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="da17a-118">Ad esempio, i difensori della sicurezza possono vedere dove è iniziato l'attacco, quali tattiche sono state usate e quanto l'attacco è passato nella rete.</span><span class="sxs-lookup"><span data-stu-id="da17a-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="da17a-119">Possono inoltre vedere l'ambito dell'attacco, ad esempio il numero di dispositivi, utenti e cassette postali interessati, il livello di impatto e altri dettagli sulle entità interessate.</span><span class="sxs-lookup"><span data-stu-id="da17a-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="da17a-120">Se abilitato, Microsoft 365 Defender può analizzare e risolvere automaticamente i singoli avvisi tramite automazione e intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="da17a-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="da17a-121">I difensori della sicurezza possono anche eseguire ulteriori passaggi di correzione per risolvere l'attacco direttamente dalla vista degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="da17a-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="da17a-122">Gli eventi imprevisti degli ultimi 30 giorni vengono visualizzati nella coda degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="da17a-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="da17a-123">Da qui, i difensori della sicurezza possono vedere quali incidenti devono essere classificati in ordine di priorità in base al livello di rischio e ad altri fattori.</span><span class="sxs-lookup"><span data-stu-id="da17a-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="da17a-124">I difensori della sicurezza possono anche rinominare gli eventi imprevisti, assegnarli a singoli analisti, classificare e aggiungere tag agli eventi imprevisti per un'esperienza di gestione degli eventi imprevisti migliore e più personalizzata.</span><span class="sxs-lookup"><span data-stu-id="da17a-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="da17a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da17a-125">See also</span></span>
- [<span data-ttu-id="da17a-126">Assegnare priorità agli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="da17a-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="da17a-127">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="da17a-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="da17a-128">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="da17a-128">Manage incidents</span></span>](manage-incidents.md)
