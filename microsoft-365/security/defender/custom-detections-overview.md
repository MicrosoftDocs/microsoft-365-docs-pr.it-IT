---
title: Panoramica dei rilevamenti personalizzati in Microsoft 365 Defender
description: Informazioni su come usare la ricerca avanzata per creare rilevamenti personalizzati e generare avvisi
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, microsoft threat protection, Microsoft 365, mtp, m365, ricerca, query, telemetria, rilevamenti personalizzati, schema, kusto, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 4a4b601b5f8b9a21d7e7260fcadf9fecd0e37c5b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060797"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="1283e-104">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="1283e-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1283e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1283e-105">**Applies to:**</span></span>
- <span data-ttu-id="1283e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1283e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1283e-107">Con i rilevamenti personalizzati, è possibile monitorare e rispondere in modo proattivo a vari eventi e stati di sistema, tra cui attività di violazione sospetta ed endpoint non configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="1283e-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="1283e-108">Ciò è reso possibile da regole di rilevamento personalizzabili che attivano automaticamente avvisi e azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="1283e-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="1283e-109">I rilevamenti personalizzati funzionano con [la](advanced-hunting-overview.md)ricerca avanzata, che fornisce un linguaggio di query potente e flessibile che copre un'ampia gamma di informazioni sugli eventi e sul sistema dalla rete.</span><span class="sxs-lookup"><span data-stu-id="1283e-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="1283e-110">Puoi impostarli per l'esecuzione a intervalli regolari, generando avvisi ed eseguire azioni di risposta ogni volta che ci sono corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="1283e-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="1283e-111">I rilevamenti personalizzati forniscono:</span><span class="sxs-lookup"><span data-stu-id="1283e-111">Custom detections provide:</span></span>
- <span data-ttu-id="1283e-112">Avvisi per i rilevamenti basati su regole creati da query di ricerca avanzate</span><span class="sxs-lookup"><span data-stu-id="1283e-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="1283e-113">Azioni di risposta automatica</span><span class="sxs-lookup"><span data-stu-id="1283e-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="1283e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1283e-114">See also</span></span>
- [<span data-ttu-id="1283e-115">Creare e gestire regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="1283e-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="1283e-116">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="1283e-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1283e-117">Eseguire la migrazione di query di ricerca avanzate da Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="1283e-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
