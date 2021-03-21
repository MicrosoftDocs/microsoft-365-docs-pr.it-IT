---
title: Panoramica degli incidenti in Microsoft 365 Defender
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
ms.openlocfilehash: de3fba2692f5b6df7c7192c328a3911287cd7ce2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928725"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="578fc-104">Panoramica degli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="578fc-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="578fc-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="578fc-105">**Applies to:**</span></span>
- <span data-ttu-id="578fc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="578fc-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="578fc-107">Vuoi provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="578fc-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="578fc-108">È possibile [valutarlo in un ambiente lab o](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) eseguire il progetto pilota in [produzione.](./mtp-pilot.md?ocid=cx-evalpilot)</span><span class="sxs-lookup"><span data-stu-id="578fc-108">You can [evaluate it in a lab environment](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](./mtp-pilot.md?ocid=cx-evalpilot).</span></span>
>


<span data-ttu-id="578fc-109">Gli eventi imprevisti si basano su avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="578fc-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="578fc-110">Gli avvisi vengono creati quando un'attività o un evento dannoso viene visualizzato nella rete.</span><span class="sxs-lookup"><span data-stu-id="578fc-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="578fc-111">I singoli avvisi forniscono indicazioni preziose su un attacco in corso.</span><span class="sxs-lookup"><span data-stu-id="578fc-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="578fc-112">Tuttavia, gli attacchi in genere utilizzano vari vettori e tecniche per eseguire una violazione.</span><span class="sxs-lookup"><span data-stu-id="578fc-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="578fc-113">La torta di singoli indizi può essere impegnativa e dispendiosa in termini di tempo.</span><span class="sxs-lookup"><span data-stu-id="578fc-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="578fc-114">Questo breve video offre una panoramica degli eventi imprevisti in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="578fc-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="578fc-115">Un evento imprevisto è una raccolta di avvisi correlati che costituiscono la storia di un attacco.</span><span class="sxs-lookup"><span data-stu-id="578fc-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="578fc-116">Gli eventi dannosi e sospetti rilevati in entità di dispositivi, utenti e cassette postali diversi nella rete vengono aggregati automaticamente da Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="578fc-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="578fc-117">Il raggruppamento degli avvisi correlati in un evento imprevisto offre ai difensori della sicurezza una visualizzazione completa di un attacco.</span><span class="sxs-lookup"><span data-stu-id="578fc-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="578fc-118">Ad esempio, i difensori della sicurezza possono vedere dove è iniziato l'attacco, quali tattiche sono state usate e quanto l'attacco è andato nella rete.</span><span class="sxs-lookup"><span data-stu-id="578fc-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="578fc-119">Possono inoltre visualizzare l'ambito dell'attacco, ad esempio il numero di dispositivi, utenti e cassette postali interessati, il livello di impatto e altri dettagli sulle entità interessate.</span><span class="sxs-lookup"><span data-stu-id="578fc-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="578fc-120">Se abilitato, Microsoft 365 Defender può analizzare e risolvere automaticamente i singoli avvisi tramite l'automazione e l'intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="578fc-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="578fc-121">I difensori della sicurezza possono anche eseguire ulteriori passaggi di correzione per risolvere l'attacco direttamente dalla vista degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="578fc-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="578fc-122">Gli eventi imprevisti degli ultimi 30 giorni vengono visualizzati nella coda degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="578fc-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="578fc-123">Da qui, i difensori della sicurezza possono vedere quali incidenti devono essere classificati in base al livello di rischio e ad altri fattori.</span><span class="sxs-lookup"><span data-stu-id="578fc-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="578fc-124">I difensori della sicurezza possono anche rinominare gli incidenti, assegnarli a singoli analisti, classificare e aggiungere tag agli incidenti per un'esperienza di gestione degli eventi imprevisti migliore e più personalizzata.</span><span class="sxs-lookup"><span data-stu-id="578fc-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="578fc-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="578fc-125">See also</span></span>
- [<span data-ttu-id="578fc-126">Assegnare priorità agli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="578fc-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="578fc-127">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="578fc-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="578fc-128">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="578fc-128">Manage incidents</span></span>](manage-incidents.md)