---
title: Panoramica dei rilevamenti personalizzati in Microsoft 365 Defender
description: Informazioni su come usare la ricerca avanzata per creare rilevamenti personalizzati e generare avvisi
keywords: ricerca avanzata, ricerca delle minacce, ricerca delle minacce informatiche, protezione dalle minacce Microsoft, Microsoft 365, mtp, m365, ricerca, query, telemetria, rilevamenti personalizzati, schema, kusto, Microsoft 365, Microsoft Threat Protection
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: de9fb28f09b88cf1730f3bb3539234f6a03ec2e3
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080714"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="73db6-104">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="73db6-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="73db6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="73db6-105">**Applies to:**</span></span>
- <span data-ttu-id="73db6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73db6-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="73db6-107">Con i rilevamenti personalizzati, è possibile monitorare e rispondere in modo proattivo a vari eventi e stati di sistema, tra cui attività di violazione sospetta e endpoint non configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="73db6-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="73db6-108">Ciò è reso possibile da regole di rilevamento personalizzabili che attivano automaticamente avvisi e azioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="73db6-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="73db6-109">I rilevamenti personalizzati funzionano con [la](advanced-hunting-overview.md)ricerca avanzata, che offre un linguaggio di query potente e flessibile che copre un'ampia gamma di informazioni sugli eventi e sul sistema dalla rete.</span><span class="sxs-lookup"><span data-stu-id="73db6-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="73db6-110">Puoi impostarli per l'esecuzione a intervalli regolari, generando avvisi ed eseguire azioni di risposta ogni volta che sono presenti corrispondenze.</span><span class="sxs-lookup"><span data-stu-id="73db6-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="73db6-111">I rilevamenti personalizzati forniscono:</span><span class="sxs-lookup"><span data-stu-id="73db6-111">Custom detections provide:</span></span>
- <span data-ttu-id="73db6-112">Avvisi per i rilevamenti basati su regole creati da query di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="73db6-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="73db6-113">Azioni di risposta automatica</span><span class="sxs-lookup"><span data-stu-id="73db6-113">Automatic response actions</span></span>

## <a name="see-also"></a><span data-ttu-id="73db6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73db6-114">See also</span></span>
- [<span data-ttu-id="73db6-115">Creare e gestire regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="73db6-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="73db6-116">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="73db6-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="73db6-117">Eseguire la migrazione di query di ricerca avanzata da Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="73db6-117">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mdatp.md)
