---
title: Panoramica dei rilevamenti personalizzati in Microsoft Defender ATP
ms.reviewer: ''
description: Informazioni su come usare la ricerca avanzata per creare rilevamenti personalizzati e generare avvisi
keywords: rilevamenti personalizzati, avvisi, regole di rilevamento, ricerca avanzata, ricerca, query, azioni di risposta, intervallo, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 20bd70653f535bb732c252224c1e6efd5cf65035
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500645"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="571b3-104">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="571b3-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="571b3-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="571b3-105">**Applies to:**</span></span>
- [<span data-ttu-id="571b3-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="571b3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="571b3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="571b3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="571b3-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="571b3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="571b3-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="571b3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="571b3-110">Con i rilevamenti personalizzati, puoi monitorare e rispondere in modo proattivo a vari eventi e stati di sistema, tra cui attività sospetta di violazione e dispositivi non configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="571b3-110">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="571b3-111">Puoi farlo con regole di rilevamento personalizzabili che attivano automaticamente avvisi e azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="571b3-111">You can do this with customizable detection rules that automatically trigger alerts and response actions.</span></span>

<span data-ttu-id="571b3-112">I rilevamenti personalizzati funzionano con [la](advanced-hunting-overview.md)ricerca avanzata, che fornisce un linguaggio di query potente e flessibile che copre un'ampia gamma di informazioni sugli eventi e sul sistema dalla rete.</span><span class="sxs-lookup"><span data-stu-id="571b3-112">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="571b3-113">Puoi impostarli per l'esecuzione a intervalli regolari, generando avvisi ed eseguire azioni di risposta ogni volta che ci sono corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="571b3-113">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="571b3-114">I rilevamenti personalizzati forniscono:</span><span class="sxs-lookup"><span data-stu-id="571b3-114">Custom detections provide:</span></span>
- <span data-ttu-id="571b3-115">Avvisi per i rilevamenti basati su regole creati da query di ricerca avanzate</span><span class="sxs-lookup"><span data-stu-id="571b3-115">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="571b3-116">Azioni di risposta automatica applicabili a file e dispositivi</span><span class="sxs-lookup"><span data-stu-id="571b3-116">Automatic response actions that apply to files and devices</span></span>

## <a name="related-topics"></a><span data-ttu-id="571b3-117">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="571b3-117">Related topics</span></span>
- [<span data-ttu-id="571b3-118">Creare regole di rilevamento</span><span class="sxs-lookup"><span data-stu-id="571b3-118">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="571b3-119">Visualizzare e gestire le regole di rilevamento</span><span class="sxs-lookup"><span data-stu-id="571b3-119">View and manage detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="571b3-120">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="571b3-120">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
