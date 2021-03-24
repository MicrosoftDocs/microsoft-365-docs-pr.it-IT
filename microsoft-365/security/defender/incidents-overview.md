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
localization_priority: Normal
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
ms.openlocfilehash: ef05609da50bc73fa59fb582b77faa5d87b9ece3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060738"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="5b937-104">Panoramica degli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b937-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5b937-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5b937-105">**Applies to:**</span></span>
- <span data-ttu-id="5b937-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b937-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="5b937-107">Vuoi provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="5b937-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="5b937-108">È possibile [valutarlo in un ambiente lab o](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eseguire il progetto pilota in [produzione.](m365d-pilot.md?ocid=cx-evalpilot)</span><span class="sxs-lookup"><span data-stu-id="5b937-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>


<span data-ttu-id="5b937-109">Gli eventi imprevisti si basano su avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="5b937-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="5b937-110">Gli avvisi vengono creati quando un'attività o un evento dannoso viene visualizzato nella rete.</span><span class="sxs-lookup"><span data-stu-id="5b937-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="5b937-111">I singoli avvisi forniscono indicazioni preziose su un attacco in corso.</span><span class="sxs-lookup"><span data-stu-id="5b937-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="5b937-112">Tuttavia, gli attacchi in genere utilizzano vari vettori e tecniche per eseguire una violazione.</span><span class="sxs-lookup"><span data-stu-id="5b937-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="5b937-113">La torta di singoli indizi può essere impegnativa e dispendiosa in termini di tempo.</span><span class="sxs-lookup"><span data-stu-id="5b937-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="5b937-114">Questo breve video offre una panoramica degli eventi imprevisti in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5b937-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="5b937-115">Un evento imprevisto è una raccolta di avvisi correlati che costituiscono la storia di un attacco.</span><span class="sxs-lookup"><span data-stu-id="5b937-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="5b937-116">Gli eventi dannosi e sospetti rilevati in entità di dispositivi, utenti e cassette postali diversi nella rete vengono aggregati automaticamente da Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5b937-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="5b937-117">Il raggruppamento degli avvisi correlati in un evento imprevisto offre ai difensori della sicurezza una visualizzazione completa di un attacco.</span><span class="sxs-lookup"><span data-stu-id="5b937-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="5b937-118">Ad esempio, i difensori della sicurezza possono vedere dove è iniziato l'attacco, quali tattiche sono state usate e quanto l'attacco è andato nella rete.</span><span class="sxs-lookup"><span data-stu-id="5b937-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="5b937-119">Possono inoltre visualizzare l'ambito dell'attacco, ad esempio il numero di dispositivi, utenti e cassette postali interessati, il livello di impatto e altri dettagli sulle entità interessate.</span><span class="sxs-lookup"><span data-stu-id="5b937-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="5b937-120">Se abilitato, Microsoft 365 Defender può analizzare e risolvere automaticamente i singoli avvisi tramite l'automazione e l'intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="5b937-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="5b937-121">I difensori della sicurezza possono anche eseguire ulteriori passaggi di correzione per risolvere l'attacco direttamente dalla vista degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="5b937-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="5b937-122">Gli eventi imprevisti degli ultimi 30 giorni vengono visualizzati nella coda degli eventi imprevisti.</span><span class="sxs-lookup"><span data-stu-id="5b937-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="5b937-123">Da qui, i difensori della sicurezza possono vedere quali incidenti devono essere classificati in base al livello di rischio e ad altri fattori.</span><span class="sxs-lookup"><span data-stu-id="5b937-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="5b937-124">I difensori della sicurezza possono anche rinominare gli incidenti, assegnarli a singoli analisti, classificare e aggiungere tag agli incidenti per un'esperienza di gestione degli eventi imprevisti migliore e più personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5b937-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="5b937-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b937-125">See also</span></span>
- [<span data-ttu-id="5b937-126">Assegnare priorità agli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="5b937-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="5b937-127">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="5b937-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="5b937-128">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="5b937-128">Manage incidents</span></span>](manage-incidents.md)