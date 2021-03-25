---
title: Flag di evento della sequenza temporale del dispositivo Microsoft Defender for Endpoint
description: Usare i flag di evento della sequenza temporale di Microsoft Defender per il dispositivo endpoint per
keywords: Defender for Endpoint device timeline, event flags
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165154"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a><span data-ttu-id="7b684-104">Flag di evento della sequenza temporale del dispositivo Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7b684-104">Microsoft Defender for Endpoint device timeline event flags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7b684-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7b684-105">**Applies to:**</span></span>
- [<span data-ttu-id="7b684-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="7b684-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7b684-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b684-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7b684-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7b684-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7b684-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="7b684-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="7b684-110">I flag di evento nella sequenza temporale del dispositivo Defender for Endpoint ti aiutano a filtrare e organizzare eventi specifici quando stai analizzando potenziali attacchi.</span><span class="sxs-lookup"><span data-stu-id="7b684-110">Event flags in the Defender for Endpoint device timeline help you filter and organize specific events when you're  investigate potential attacks.</span></span>

<span data-ttu-id="7b684-111">La sequenza temporale del dispositivo Defender for Endpoint fornisce una visualizzazione cronologica degli eventi e degli avvisi associati osservati in un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b684-111">The Defender for Endpoint device timeline provides a chronological view of the events and associated alerts observed on a device.</span></span> <span data-ttu-id="7b684-112">Questo elenco di eventi offre visibilità completa su eventi, file e indirizzi IP osservati nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b684-112">This list of events provides full visibility into any events, files, and IP addresses observed on the device.</span></span> <span data-ttu-id="7b684-113">L'elenco può talvolta essere lungo.</span><span class="sxs-lookup"><span data-stu-id="7b684-113">The list can sometimes be lengthy.</span></span> <span data-ttu-id="7b684-114">I flag degli eventi della sequenza temporale del dispositivo consentono di tenere traccia degli eventi che potrebbero essere correlati.</span><span class="sxs-lookup"><span data-stu-id="7b684-114">Device timeline event flags help you track events that could be related.</span></span> 

<span data-ttu-id="7b684-115">Dopo aver attraversato una sequenza temporale del dispositivo, puoi ordinare, filtrare ed esportare gli eventi specifici contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="7b684-115">After you've gone through a device timeline, you can sort, filter, and export the specific events that you flagged.</span></span>

<span data-ttu-id="7b684-116">Durante l'esplorazione della sequenza temporale del dispositivo, puoi cercare e filtrare eventi specifici.</span><span class="sxs-lookup"><span data-stu-id="7b684-116">While navigating the device timeline, you can search and filter for specific events.</span></span> <span data-ttu-id="7b684-117">Puoi impostare i flag di evento:</span><span class="sxs-lookup"><span data-stu-id="7b684-117">You can set event flags by:</span></span> 

- <span data-ttu-id="7b684-118">Evidenziazione degli eventi più importanti</span><span class="sxs-lookup"><span data-stu-id="7b684-118">Highlighting the most important events</span></span> 
- <span data-ttu-id="7b684-119">Contrassegno di eventi che richiedono un'immersione approfondita</span><span class="sxs-lookup"><span data-stu-id="7b684-119">Marking events that requires deep dive</span></span> 
- <span data-ttu-id="7b684-120">Creazione di una sequenza temporale di violazione pulita</span><span class="sxs-lookup"><span data-stu-id="7b684-120">Building a clean breach timeline</span></span>



## <a name="flag-an-event"></a><span data-ttu-id="7b684-121">Contrassegnare un evento</span><span class="sxs-lookup"><span data-stu-id="7b684-121">Flag an event</span></span>
1. <span data-ttu-id="7b684-122">Trovare l'evento che si desidera contrassegnare</span><span class="sxs-lookup"><span data-stu-id="7b684-122">Find the event that you want to flag</span></span>
2. <span data-ttu-id="7b684-123">Fare clic sull'icona del contrassegno nella colonna Contrassegno.</span><span class="sxs-lookup"><span data-stu-id="7b684-123">Click the flag icon in the Flag column.</span></span> 
<span data-ttu-id="7b684-124">![Immagine del contrassegno sequenza temporale del dispositivo](images/device-flags.png)</span><span class="sxs-lookup"><span data-stu-id="7b684-124">![Image of device timeline flag](images/device-flags.png)</span></span>

## <a name="view-flagged-events"></a><span data-ttu-id="7b684-125">Visualizzare gli eventi contrassegnati</span><span class="sxs-lookup"><span data-stu-id="7b684-125">View flagged events</span></span>  
1. <span data-ttu-id="7b684-126">Nella sezione Filtri **sequenza temporale** abilita **Eventi contrassegnati.**</span><span class="sxs-lookup"><span data-stu-id="7b684-126">In the timeline **Filters** section, enable **Flagged events**.</span></span>
2. <span data-ttu-id="7b684-127">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="7b684-127">Click **Apply**.</span></span> <span data-ttu-id="7b684-128">Vengono visualizzati solo gli eventi contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="7b684-128">Only flagged events are displayed.</span></span>
<span data-ttu-id="7b684-129">È possibile applicare filtri aggiuntivi facendo clic sulla barra del tempo.</span><span class="sxs-lookup"><span data-stu-id="7b684-129">You can apply additional filters by clicking on the time bar.</span></span> <span data-ttu-id="7b684-130">Verranno visualizzati solo gli eventi prima dell'evento contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="7b684-130">This will only show events prior to the flagged event.</span></span>  
<span data-ttu-id="7b684-131">![Immagine del contrassegno della sequenza temporale del dispositivo con filtro su](images/device-flag-filter.png)</span><span class="sxs-lookup"><span data-stu-id="7b684-131">![Image of device timeline flag with filter on](images/device-flag-filter.png)</span></span>
