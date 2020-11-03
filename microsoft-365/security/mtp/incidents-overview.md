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
ms.openlocfilehash: e5ac3e9a02c333d3168c328aa6ad5532c48af99e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846689"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a><span data-ttu-id="e31e8-104">Panoramica degli incidenti in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e31e8-104">Incidents overview in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e31e8-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e31e8-105">**Applies to:**</span></span>
- <span data-ttu-id="e31e8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e31e8-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="e31e8-107">Gli eventi non consentiti sono basati su avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="e31e8-107">Incidents are based on related alerts.</span></span> <span data-ttu-id="e31e8-108">Gli avvisi vengono creati quando un'attività o un evento dannoso viene visualizzato nella rete.</span><span class="sxs-lookup"><span data-stu-id="e31e8-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="e31e8-109">Gli avvisi singoli forniscono indizi utili su un attacco in uscita.</span><span class="sxs-lookup"><span data-stu-id="e31e8-109">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="e31e8-110">Tuttavia, gli attacchi in genere utilizzano vettori e tecniche diverse per eseguire una violazione.</span><span class="sxs-lookup"><span data-stu-id="e31e8-110">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="e31e8-111">Il riattacco di singoli indizi può essere impegnativo e richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="e31e8-111">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="e31e8-112">In questo breve video viene fornita una panoramica delle operazioni non consentite in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e31e8-112">This short video gives an overview of incidents in Microsoft 365 Defender.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="e31e8-113">Un evento imprevisto è una raccolta di avvisi correlati che compongono la storia di un attacco.</span><span class="sxs-lookup"><span data-stu-id="e31e8-113">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="e31e8-114">Gli eventi dannosi e sospetti che si trovano in diverse entità del dispositivo, degli utenti e delle cassette postali nella rete vengono aggregati automaticamente da Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e31e8-114">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="e31e8-115">Raggruppare gli avvisi correlati in un evento imprevisto fornisce ai difensori della sicurezza una panoramica complessiva di un attacco.</span><span class="sxs-lookup"><span data-stu-id="e31e8-115">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="e31e8-116">Ad esempio, i difensori della sicurezza possono vedere dove è iniziato l'attacco, quali tattiche sono state utilizzate e in che misura l'attacco è andato in rete.</span><span class="sxs-lookup"><span data-stu-id="e31e8-116">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="e31e8-117">È inoltre possibile visualizzare l'ambito dell'attacco, ad esempio il numero di dispositivi, utenti e cassette postali a cui è stato applicato un impatto, la gravità dell'impatto e altre informazioni sulle entità interessate.</span><span class="sxs-lookup"><span data-stu-id="e31e8-117">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="e31e8-118">Se abilitato, Microsoft 365 Defender può analizzare e risolvere automaticamente i singoli avvisi tramite l'automazione e l'intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="e31e8-118">If enabled, Microsoft 365 Defender can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="e31e8-119">I difensori della sicurezza possono inoltre eseguire ulteriori passaggi di correzione per risolvere l'attacco direttamente dalla visualizzazione eventi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="e31e8-119">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="e31e8-120">Gli incidenti degli ultimi 30 giorni sono visualizzati nella coda degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="e31e8-120">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="e31e8-121">Da qui, i difensori della sicurezza possono vedere quali incidenti devono essere classificati in base al livello di rischio e ad altri fattori.</span><span class="sxs-lookup"><span data-stu-id="e31e8-121">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="e31e8-122">I difensori della sicurezza possono anche rinominare gli incidenti, assegnarli a singoli analisti, classificare e aggiungere tag agli incidenti per una migliore e più personalizzata esperienza di gestione degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="e31e8-122">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="e31e8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e31e8-123">See also</span></span>
- [<span data-ttu-id="e31e8-124">Assegnare priorità agli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="e31e8-124">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="e31e8-125">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="e31e8-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="e31e8-126">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="e31e8-126">Manage incidents</span></span>](manage-incidents.md)
