---
title: Panoramica dei rilevamenti personalizzati in Microsoft 365 Defender
description: Informazioni su come usare la ricerca avanzata per creare rilevamenti personalizzati e generare avvisi
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, rilevamenti personalizzati, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 748b3534ef1f6ca5736667fc3910bb9fa96d23ff
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952537"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="e8567-104">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="e8567-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e8567-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="e8567-105">**Applies to:**</span></span>
- <span data-ttu-id="e8567-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8567-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="e8567-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="e8567-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="e8567-108">Con i rilevamenti personalizzati, è possibile monitorare e rispondere in modo proattivo a vari eventi e stati di sistema, tra cui attività di violazione sospetta ed endpoint non configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="e8567-108">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="e8567-109">Ciò è reso possibile da regole di rilevamento personalizzabili che attivano automaticamente avvisi e azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="e8567-109">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="e8567-110">I rilevamenti personalizzati funzionano con [la](advanced-hunting-overview.md)ricerca avanzata, che fornisce un linguaggio di query potente e flessibile che copre un'ampia gamma di informazioni sugli eventi e sul sistema dalla rete.</span><span class="sxs-lookup"><span data-stu-id="e8567-110">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="e8567-111">Puoi impostarli per l'esecuzione a intervalli regolari, generando avvisi ed eseguire azioni di risposta ogni volta che ci sono corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="e8567-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="e8567-112">I rilevamenti personalizzati forniscono:</span><span class="sxs-lookup"><span data-stu-id="e8567-112">Custom detections provide:</span></span>
- <span data-ttu-id="e8567-113">Avvisi per i rilevamenti basati su regole creati da query di ricerca avanzate</span><span class="sxs-lookup"><span data-stu-id="e8567-113">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="e8567-114">Azioni di risposta automatica</span><span class="sxs-lookup"><span data-stu-id="e8567-114">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="e8567-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8567-115">See also</span></span>
- [<span data-ttu-id="e8567-116">Creare e gestire regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="e8567-116">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="e8567-117">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="e8567-117">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e8567-118">Eseguire la migrazione di query di ricerca avanzate da Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="e8567-118">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
