---
title: Quote di ricerca avanzate e parametri di utilizzo in Microsoft 365 Defender
description: Comprendere le varie quote e i parametri di utilizzo (limiti del servizio) che mantengono reattivo il servizio di ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, schema, kusto, limite cpu, limite di query, risorse, risultati massimi, quota, parametri, allocazione
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c9526363b0430514455db1fbdf12cfb7a18229f1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932990"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="53f3a-104">Quote di ricerca avanzate e parametri di utilizzo</span><span class="sxs-lookup"><span data-stu-id="53f3a-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="53f3a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="53f3a-105">**Applies to:**</span></span>
- <span data-ttu-id="53f3a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53f3a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="53f3a-107">Per mantenere il servizio efficiente e reattivo, la ricerca avanzata imposta diverse quote e parametri di utilizzo (noti anche come "limiti del servizio").</span><span class="sxs-lookup"><span data-stu-id="53f3a-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="53f3a-108">Queste quote e questi parametri si applicano alle query eseguite manualmente e tramite [regole di rilevamento personalizzate.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="53f3a-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="53f3a-109">I clienti che eseguono regolarmente più query devono tenere traccia del consumo e applicare le [procedure consigliate di ottimizzazione](advanced-hunting-best-practices.md) per ridurre al minimo le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="53f3a-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="53f3a-110">Fare riferimento alla tabella seguente per comprendere le quote esistenti e i parametri di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="53f3a-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="53f3a-111">Quota o parametro</span><span class="sxs-lookup"><span data-stu-id="53f3a-111">Quota or parameter</span></span> | <span data-ttu-id="53f3a-112">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="53f3a-112">Size</span></span> | <span data-ttu-id="53f3a-113">Ciclo di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="53f3a-113">Refresh cycle</span></span> | <span data-ttu-id="53f3a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53f3a-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="53f3a-115">DataRange</span><span class="sxs-lookup"><span data-stu-id="53f3a-115">Data range</span></span> | <span data-ttu-id="53f3a-116">30 giorni</span><span class="sxs-lookup"><span data-stu-id="53f3a-116">30 days</span></span> | <span data-ttu-id="53f3a-117">Ogni query</span><span class="sxs-lookup"><span data-stu-id="53f3a-117">Every query</span></span> | <span data-ttu-id="53f3a-118">Ogni query può cercare dati fino agli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="53f3a-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="53f3a-119">Set di risultati</span><span class="sxs-lookup"><span data-stu-id="53f3a-119">Result set</span></span> | <span data-ttu-id="53f3a-120">10.000 righe</span><span class="sxs-lookup"><span data-stu-id="53f3a-120">10,000 rows</span></span> | <span data-ttu-id="53f3a-121">Ogni query</span><span class="sxs-lookup"><span data-stu-id="53f3a-121">Every query</span></span> | <span data-ttu-id="53f3a-122">Ogni query può restituire fino a 10.000 record.</span><span class="sxs-lookup"><span data-stu-id="53f3a-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="53f3a-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="53f3a-123">Timeout</span></span> | <span data-ttu-id="53f3a-124">10 minuti</span><span class="sxs-lookup"><span data-stu-id="53f3a-124">10 minutes</span></span> | <span data-ttu-id="53f3a-125">Ogni query</span><span class="sxs-lookup"><span data-stu-id="53f3a-125">Every query</span></span> | <span data-ttu-id="53f3a-126">Ogni query può essere eseguita per un massimo di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="53f3a-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="53f3a-127">Se non viene completato entro 10 minuti, il servizio visualizza un errore.</span><span class="sxs-lookup"><span data-stu-id="53f3a-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="53f3a-128">Risorse CPU</span><span class="sxs-lookup"><span data-stu-id="53f3a-128">CPU resources</span></span> | <span data-ttu-id="53f3a-129">In base alle dimensioni del tenant</span><span class="sxs-lookup"><span data-stu-id="53f3a-129">Based on tenant size</span></span> | <span data-ttu-id="53f3a-130">- Nell'ora e quindi ogni 15 minuti</span><span class="sxs-lookup"><span data-stu-id="53f3a-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="53f3a-131">- Ogni giorno alle 12.00</span><span class="sxs-lookup"><span data-stu-id="53f3a-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="53f3a-132">Il servizio applica separatamente la quota giornaliera e la quota di 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="53f3a-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="53f3a-133">Per ogni quota, il [portale visualizza un](advanced-hunting-errors.md) errore ogni volta che viene eseguita una query e il tenant ha utilizzato più del 10% delle risorse allocate.</span><span class="sxs-lookup"><span data-stu-id="53f3a-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="53f3a-134">Le query vengono bloccate se il tenant ha raggiunto il 100% fino al successivo ciclo giornaliero o di 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="53f3a-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="53f3a-135">Un set separato di quote e parametri si applica alle query di ricerca avanzate eseguite tramite l'API.</span><span class="sxs-lookup"><span data-stu-id="53f3a-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="53f3a-136">Informazioni sulle API di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="53f3a-136">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="53f3a-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="53f3a-137">Related topics</span></span>

- [<span data-ttu-id="53f3a-138">Procedure consigliate per la ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="53f3a-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="53f3a-139">Gestire gli errori di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="53f3a-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="53f3a-140">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="53f3a-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="53f3a-141">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="53f3a-141">Custom detections overview</span></span>](custom-detections-overview.md)