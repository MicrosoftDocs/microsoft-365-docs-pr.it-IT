---
title: Panoramica dei rilevamenti personalizzati in Microsoft 365 Defender
description: Comprendere come è possibile utilizzare la ricerca avanzata per creare rilevamenti personalizzati e generare avvisi
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, rilevamenti personalizzati, schema, kusto, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: fe2b9f1b52fa2c8d9031bb58597992f3dda91520
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843913"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="69a95-104">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="69a95-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="69a95-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="69a95-105">**Applies to:**</span></span>
- <span data-ttu-id="69a95-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69a95-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="69a95-107">Con i rilevamenti personalizzati, è possibile monitorare e rispondere in modo proattivo ai vari eventi e Stati del sistema, tra cui l'attività di violazione sospetta e gli endpoint non configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="69a95-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="69a95-108">Ciò è reso possibile dalle regole di rilevamento personalizzabili che attivano automaticamente gli avvisi e le azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="69a95-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="69a95-109">I rilevamenti personalizzati funzionano con la [ricerca avanzata](advanced-hunting-overview.md), che fornisce un linguaggio di query potente e flessibile che copre un ampio insieme di informazioni di sistema e eventi dalla rete.</span><span class="sxs-lookup"><span data-stu-id="69a95-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="69a95-110">È possibile impostare gli avvisi e le azioni di risposta ogni volta che si verificano delle corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="69a95-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="69a95-111">I rilevamenti personalizzati offrono:</span><span class="sxs-lookup"><span data-stu-id="69a95-111">Custom detections provide:</span></span>
- <span data-ttu-id="69a95-112">Avvisi per i rilevamenti basati su regole creati da query di ricerca avanzate</span><span class="sxs-lookup"><span data-stu-id="69a95-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="69a95-113">Azioni di risposta automatica</span><span class="sxs-lookup"><span data-stu-id="69a95-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="69a95-114">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="69a95-114">Related topic</span></span>
- [<span data-ttu-id="69a95-115">Creare e gestire le regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="69a95-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="69a95-116">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="69a95-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
