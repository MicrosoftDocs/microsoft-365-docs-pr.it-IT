---
title: Panoramica dei rilevamenti personalizzati in Microsoft Threat Protection
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
ms.openlocfilehash: cdbaf9cfd2172656ed75cb3c0a1a9e361070f25b
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498352"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="0e4cb-104">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="0e4cb-104">Custom detections overview</span></span>

<span data-ttu-id="0e4cb-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0e4cb-105">**Applies to:**</span></span>
- <span data-ttu-id="0e4cb-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0e4cb-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0e4cb-107">Con i rilevamenti personalizzati, è possibile monitorare e rispondere in modo proattivo ai vari eventi e Stati del sistema, tra cui l'attività di violazione sospetta e gli endpoint non configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="0e4cb-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="0e4cb-108">Ciò è reso possibile dalle regole di rilevamento personalizzabili che attivano automaticamente gli avvisi e le azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="0e4cb-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="0e4cb-109">I rilevamenti personalizzati funzionano con la [ricerca avanzata](advanced-hunting-overview.md), che fornisce un linguaggio di query potente e flessibile che copre un ampio insieme di informazioni di sistema e eventi dalla rete.</span><span class="sxs-lookup"><span data-stu-id="0e4cb-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="0e4cb-110">È possibile impostare gli avvisi e le azioni di risposta ogni volta che si verificano delle corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="0e4cb-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="0e4cb-111">I rilevamenti personalizzati offrono:</span><span class="sxs-lookup"><span data-stu-id="0e4cb-111">Custom detections provide:</span></span>
- <span data-ttu-id="0e4cb-112">Avvisi per i rilevamenti basati su regole creati da query di ricerca avanzate</span><span class="sxs-lookup"><span data-stu-id="0e4cb-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="0e4cb-113">Azioni di risposta automatica</span><span class="sxs-lookup"><span data-stu-id="0e4cb-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="0e4cb-114">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="0e4cb-114">Related topic</span></span>
- [<span data-ttu-id="0e4cb-115">Creare e gestire le regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="0e4cb-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="0e4cb-116">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="0e4cb-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)