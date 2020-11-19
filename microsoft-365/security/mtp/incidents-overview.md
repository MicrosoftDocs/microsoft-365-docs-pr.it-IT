---
title: Panoramica degli incidenti in Microsoft 365 Defender
description: Analizzare gli eventi imprevisti visualizzati su dispositivi, utenti e cassette postali.
keywords: eventi, avvisi, analisi, correlazione, attacco, computer, dispositivi, utenti, identità, cassetta postale, posta elettronica, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 6149b6f128b3c96d2338e325caa8df835c292b13
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357612"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="ad67a-104">Panoramica degli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad67a-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ad67a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ad67a-105">**Applies to:**</span></span>
- <span data-ttu-id="ad67a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad67a-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="ad67a-107">Vuoi provare Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="ad67a-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="ad67a-108">È possibile [valutarla in un ambiente lab](https://aka.ms/mtp-trial-lab) o [eseguire il progetto pilota in produzione](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="ad67a-108">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>


<span data-ttu-id="ad67a-109">Gli eventi non consentiti sono basati su avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="ad67a-109">Incidents are based on related alerts.</span></span> <span data-ttu-id="ad67a-110">Gli avvisi vengono creati quando un'attività o un evento dannoso viene visualizzato nella rete.</span><span class="sxs-lookup"><span data-stu-id="ad67a-110">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="ad67a-111">Gli avvisi singoli forniscono indizi utili su un attacco in uscita.</span><span class="sxs-lookup"><span data-stu-id="ad67a-111">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="ad67a-112">Tuttavia, gli attacchi in genere utilizzano vettori e tecniche diverse per eseguire una violazione.</span><span class="sxs-lookup"><span data-stu-id="ad67a-112">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="ad67a-113">Il riattacco di singoli indizi può essere impegnativo e richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="ad67a-113">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="ad67a-114">In questo breve video viene fornita una panoramica delle operazioni non consentite in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ad67a-114">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="ad67a-115">Un evento imprevisto è una raccolta di avvisi correlati che compongono la storia di un attacco.</span><span class="sxs-lookup"><span data-stu-id="ad67a-115">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="ad67a-116">Gli eventi dannosi e sospetti che si trovano in diverse entità del dispositivo, degli utenti e delle cassette postali nella rete vengono aggregati automaticamente da Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ad67a-116">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="ad67a-117">Raggruppare gli avvisi correlati in un evento imprevisto fornisce ai difensori della sicurezza una panoramica complessiva di un attacco.</span><span class="sxs-lookup"><span data-stu-id="ad67a-117">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="ad67a-118">Ad esempio, i difensori della sicurezza possono vedere dove è iniziato l'attacco, quali tattiche sono state utilizzate e in che misura l'attacco è andato in rete.</span><span class="sxs-lookup"><span data-stu-id="ad67a-118">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="ad67a-119">È inoltre possibile visualizzare l'ambito dell'attacco, ad esempio il numero di dispositivi, utenti e cassette postali a cui è stato applicato un impatto, la gravità dell'impatto e altre informazioni sulle entità interessate.</span><span class="sxs-lookup"><span data-stu-id="ad67a-119">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="ad67a-120">Se abilitato, Microsoft 365 Defender può analizzare e risolvere automaticamente i singoli avvisi tramite l'automazione e l'intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="ad67a-120">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="ad67a-121">I difensori della sicurezza possono inoltre eseguire ulteriori passaggi di correzione per risolvere l'attacco direttamente dalla visualizzazione eventi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="ad67a-121">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="ad67a-122">Gli incidenti degli ultimi 30 giorni sono visualizzati nella coda degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="ad67a-122">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="ad67a-123">Da qui, i difensori della sicurezza possono vedere quali incidenti devono essere classificati in base al livello di rischio e ad altri fattori.</span><span class="sxs-lookup"><span data-stu-id="ad67a-123">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="ad67a-124">I difensori della sicurezza possono anche rinominare gli incidenti, assegnarli a singoli analisti, classificare e aggiungere tag agli incidenti per una migliore e più personalizzata esperienza di gestione degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="ad67a-124">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="ad67a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad67a-125">See also</span></span>
- [<span data-ttu-id="ad67a-126">Assegnare priorità agli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="ad67a-126">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="ad67a-127">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="ad67a-127">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="ad67a-128">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="ad67a-128">Manage incidents</span></span>](manage-incidents.md)
