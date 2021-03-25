---
title: Panoramica delle funzionalità di rilevamento e risposta degli endpoint
ms.reviewer: ''
description: Informazioni sulle funzionalità di rilevamento e risposta degli endpoint in Microsoft Defender ATP
keywords: ''
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0a5a665fac1883016ac222197ba8322f78e2558f
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186174"
---
# <a name="overview-of-endpoint-detection-and-response"></a><span data-ttu-id="6c172-103">Panoramica del rilevamento e della risposta degli endpoint</span><span class="sxs-lookup"><span data-stu-id="6c172-103">Overview of endpoint detection and response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6c172-104">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6c172-104">**Applies to:**</span></span>
- [<span data-ttu-id="6c172-105">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="6c172-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6c172-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c172-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6c172-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6c172-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6c172-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="6c172-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6c172-109">Le funzionalità di risposta e rilevamento degli endpoint di Defender for Endpoint offrono rilevamenti di attacchi avanzati quasi in tempo reale e utilizzabili.</span><span class="sxs-lookup"><span data-stu-id="6c172-109">Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="6c172-110">I responsabili della sicurezza possono assegnare priorità agli avvisi in modo efficace, ottenere una visibilità completa su una violazione e adottare azioni di risposta per correggere le minacce.</span><span class="sxs-lookup"><span data-stu-id="6c172-110">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span>

<span data-ttu-id="6c172-111">Quando viene rilevata una minaccia, il sistema genera un avviso e un analista avvia le indagini.</span><span class="sxs-lookup"><span data-stu-id="6c172-111">When a threat is detected, alerts are created in the system for an analyst to investigate.</span></span> <span data-ttu-id="6c172-112">Gli avvisi che presentano tecniche di attacco simili o che possono essere attribuiti alla stessa persona vengono aggregati in un'entità chiamata _incidente_.</span><span class="sxs-lookup"><span data-stu-id="6c172-112">Alerts with the same attack techniques or attributed to the same attacker are aggregated into an entity called an _incident_.</span></span> <span data-ttu-id="6c172-113">L'aggregazione di avvisi consente di analizzare e rispondere in modo completo alle minacce.</span><span class="sxs-lookup"><span data-stu-id="6c172-113">Aggregating alerts in this manner makes it easy for analysts to collectively investigate and respond to threats.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4o1j5]

<span data-ttu-id="6c172-114">Ispirato dalla mentalità "presupporre violazione", Defender for Endpoint raccoglie continuamente la telemetria cyber comportamentale.</span><span class="sxs-lookup"><span data-stu-id="6c172-114">Inspired by the "assume breach" mindset, Defender for Endpoint continuously collects behavioral cyber telemetry.</span></span> <span data-ttu-id="6c172-115">Tali dati includono le informazioni sui processi, le attività di rete, l’analisi approfondita del kernel e della gestione della memoria, le attività di accesso degli utenti, le modifiche apportate al registro di sistema e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="6c172-115">This includes process information, network activities, deep optics into the kernel and memory manager, user login activities, registry and file system changes, and others.</span></span> <span data-ttu-id="6c172-116">Queste informazioni vengono archiviate per sei mesi, consentendo ai responsabili della sicurezza di identificare l'inizio di un attacco indietro nel tempo.</span><span class="sxs-lookup"><span data-stu-id="6c172-116">The information is stored for six months, enabling an analyst to travel back in time to the start of an attack.</span></span> <span data-ttu-id="6c172-117">In questo modo è possibile eseguire un’analisi da varie angolazioni e iniziare un'indagine attraverso più vettori.</span><span class="sxs-lookup"><span data-stu-id="6c172-117">The analyst can then pivot in various views and approach an investigation through multiple vectors.</span></span>

<span data-ttu-id="6c172-118">Le funzionalità di risposta consentono di correggere tempestivamente le minacce agendo sulle entità interessate.</span><span class="sxs-lookup"><span data-stu-id="6c172-118">The response capabilities give you the power to promptly remediate threats by acting on the affected entities.</span></span>


## <a name="related-topics"></a><span data-ttu-id="6c172-119">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6c172-119">Related topics</span></span>
- [<span data-ttu-id="6c172-120">Dashboard delle operazioni di sicurezza</span><span class="sxs-lookup"><span data-stu-id="6c172-120">Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="6c172-121">Coda eventi imprevisti</span><span class="sxs-lookup"><span data-stu-id="6c172-121">Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="6c172-122">Coda avvisi</span><span class="sxs-lookup"><span data-stu-id="6c172-122">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="6c172-123">Elenco dispositivi</span><span class="sxs-lookup"><span data-stu-id="6c172-123">Devices list</span></span>](machines-view-overview.md)

