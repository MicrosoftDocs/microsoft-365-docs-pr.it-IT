---
title: Panoramica degli eventi imprevisti in Microsoft Threat Protection
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c9b495b70c8b61188b4db3175b54e406feb87fc8
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357843"
---
# <a name="incidents-overview-in-microsoft-threat-protection"></a><span data-ttu-id="eae9c-104">Panoramica degli eventi imprevisti in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="eae9c-104">Incidents overview in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="eae9c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="eae9c-105">**Applies to:**</span></span>
- <span data-ttu-id="eae9c-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="eae9c-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="eae9c-107">Gli eventi non consentiti sono basati su avvisi correlati.</span><span class="sxs-lookup"><span data-stu-id="eae9c-107">Incidents are based on related alerts.</span></span> <span data-ttu-id="eae9c-108">Gli avvisi vengono creati quando un'attività o un evento dannoso viene visualizzato nella rete.</span><span class="sxs-lookup"><span data-stu-id="eae9c-108">Alerts are created when a malicious event or activity is seen on your network.</span></span> <span data-ttu-id="eae9c-109">Gli avvisi singoli forniscono indizi utili su un attacco in uscita.</span><span class="sxs-lookup"><span data-stu-id="eae9c-109">Individual alerts provide valuable clues about an on-going attack.</span></span> <span data-ttu-id="eae9c-110">Tuttavia, gli attacchi in genere utilizzano vettori e tecniche diverse per eseguire una violazione.</span><span class="sxs-lookup"><span data-stu-id="eae9c-110">However, attacks typically employ various vectors and techniques to carry out a breach.</span></span> <span data-ttu-id="eae9c-111">Il riattacco di singoli indizi può essere impegnativo e richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="eae9c-111">Piecing individual clues together can be challenging and time-consuming.</span></span>

<span data-ttu-id="eae9c-112">In questo breve video viene fornita una panoramica degli incidenti in Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="eae9c-112">This short video gives an overview of incidents in Microsoft Threat Protection.</span></span>
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="eae9c-113">Un evento imprevisto è una raccolta di avvisi correlati che compongono la storia di un attacco.</span><span class="sxs-lookup"><span data-stu-id="eae9c-113">An incident is a collection of correlated alerts that make up the story of an attack.</span></span> <span data-ttu-id="eae9c-114">Gli eventi dannosi e sospetti che si trovano in diverse entità del dispositivo, degli utenti e delle cassette postali nella rete vengono automaticamente aggregati da Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="eae9c-114">Malicious and suspicious events that are found in different device, user, and mailbox entities in the network are automatically aggregated by Microsoft Threat Protection.</span></span> <span data-ttu-id="eae9c-115">Raggruppare gli avvisi correlati in un evento imprevisto fornisce ai difensori della sicurezza una panoramica complessiva di un attacco.</span><span class="sxs-lookup"><span data-stu-id="eae9c-115">Grouping related alerts into an incident gives security defenders a comprehensive view of an attack.</span></span> 

<span data-ttu-id="eae9c-116">Ad esempio, i difensori della sicurezza possono vedere dove è iniziato l'attacco, quali tattiche sono state utilizzate e in che misura l'attacco è andato in rete.</span><span class="sxs-lookup"><span data-stu-id="eae9c-116">For instance, security defenders can see where the attack started, what tactics were used, and how far the attack has gone into the network.</span></span> <span data-ttu-id="eae9c-117">È inoltre possibile visualizzare l'ambito dell'attacco, ad esempio il numero di dispositivi, utenti e cassette postali a cui è stato applicato un impatto, la gravità dell'impatto e altre informazioni sulle entità interessate.</span><span class="sxs-lookup"><span data-stu-id="eae9c-117">They can also see the scope of the attack, like how many devices, users, and mailboxes were impacted, how severe the impact was, and other details about affected entities.</span></span>

<span data-ttu-id="eae9c-118">Se abilitato, Microsoft Threat Protection è in grado di analizzare e risolvere automaticamente i singoli avvisi tramite l'automazione e l'intelligenza artificiale.</span><span class="sxs-lookup"><span data-stu-id="eae9c-118">If enabled, Microsoft Threat Protection can automatically investigate and resolve the individual alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="eae9c-119">I difensori della sicurezza possono inoltre eseguire ulteriori passaggi di correzione per risolvere l'attacco direttamente dalla visualizzazione eventi non consentiti.</span><span class="sxs-lookup"><span data-stu-id="eae9c-119">Security defenders can also perform additional remediation steps to resolve the attack straight from the incidents view.</span></span> 

<span data-ttu-id="eae9c-120">Gli incidenti degli ultimi 30 giorni sono visualizzati nella coda degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="eae9c-120">Incidents from the last 30 days are shown in the incident queue.</span></span> <span data-ttu-id="eae9c-121">Da qui, i difensori della sicurezza possono vedere quali incidenti devono essere classificati in base al livello di rischio e ad altri fattori.</span><span class="sxs-lookup"><span data-stu-id="eae9c-121">From here, security defenders can see which incidents should be prioritized based on risk level and other factors.</span></span> 

<span data-ttu-id="eae9c-122">I difensori della sicurezza possono anche rinominare gli incidenti, assegnarli a singoli analisti, classificare e aggiungere tag agli incidenti per una migliore e più personalizzata esperienza di gestione degli incidenti.</span><span class="sxs-lookup"><span data-stu-id="eae9c-122">Security defenders can also rename incidents, assign them to individual analysts, classify, and add tags to incidents for a better and more customized incident management experience.</span></span>



## <a name="see-also"></a><span data-ttu-id="eae9c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eae9c-123">See also</span></span>
- [<span data-ttu-id="eae9c-124">Assegnare priorità agli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="eae9c-124">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="eae9c-125">Indagare sugli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="eae9c-125">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="eae9c-126">Gestire gli eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="eae9c-126">Manage incidents</span></span>](manage-incidents.md)
