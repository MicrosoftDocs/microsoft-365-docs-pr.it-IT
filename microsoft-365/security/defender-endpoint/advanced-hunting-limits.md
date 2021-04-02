---
title: Limiti di ricerca avanzati in Microsoft Defender ATP
description: Comprendere i vari limiti dei servizi che mantengono reattivo il servizio di ricerca avanzato
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, mdatp, microsoft defender atp, wdatp, ricerca, query, telemetria, schema, kusto, limite CPU, limite di query, risorse, risultati massimi
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8a9279d1dd2a6465553b576609bb81cdf4e03fa0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499532"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="10d67-104">Limiti del servizio di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="10d67-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="10d67-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="10d67-105">**Applies to:**</span></span>
- [<span data-ttu-id="10d67-106">Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="10d67-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="10d67-107">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="10d67-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="10d67-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="10d67-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="10d67-109">Per mantenere il servizio efficiente e reattivo, la ricerca avanzata imposta vari limiti per le query eseguite manualmente e tramite [regole di rilevamento personalizzate.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="10d67-109">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="10d67-110">Fare riferimento alla tabella seguente per comprendere questi limiti.</span><span class="sxs-lookup"><span data-stu-id="10d67-110">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="10d67-111">Limite</span><span class="sxs-lookup"><span data-stu-id="10d67-111">Limit</span></span> | <span data-ttu-id="10d67-112">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="10d67-112">Size</span></span> | <span data-ttu-id="10d67-113">Ciclo di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="10d67-113">Refresh cycle</span></span> | <span data-ttu-id="10d67-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10d67-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="10d67-115">DataRange</span><span class="sxs-lookup"><span data-stu-id="10d67-115">Data range</span></span> | <span data-ttu-id="10d67-116">30 giorni</span><span class="sxs-lookup"><span data-stu-id="10d67-116">30 days</span></span> | <span data-ttu-id="10d67-117">Ogni query</span><span class="sxs-lookup"><span data-stu-id="10d67-117">Every query</span></span> | <span data-ttu-id="10d67-118">Ogni query può cercare dati fino agli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="10d67-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="10d67-119">Set di risultati</span><span class="sxs-lookup"><span data-stu-id="10d67-119">Result set</span></span> | <span data-ttu-id="10d67-120">10.000 righe</span><span class="sxs-lookup"><span data-stu-id="10d67-120">10,000 rows</span></span> | <span data-ttu-id="10d67-121">Ogni query</span><span class="sxs-lookup"><span data-stu-id="10d67-121">Every query</span></span> | <span data-ttu-id="10d67-122">Ogni query può restituire fino a 10.000 record.</span><span class="sxs-lookup"><span data-stu-id="10d67-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="10d67-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="10d67-123">Timeout</span></span> | <span data-ttu-id="10d67-124">10 minuti</span><span class="sxs-lookup"><span data-stu-id="10d67-124">10 minutes</span></span> | <span data-ttu-id="10d67-125">Ogni query</span><span class="sxs-lookup"><span data-stu-id="10d67-125">Every query</span></span> | <span data-ttu-id="10d67-126">Ogni query può essere eseguita per un massimo di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="10d67-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="10d67-127">Se non viene completato entro 10 minuti, il servizio visualizza un errore.</span><span class="sxs-lookup"><span data-stu-id="10d67-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="10d67-128">Risorse CPU</span><span class="sxs-lookup"><span data-stu-id="10d67-128">CPU resources</span></span> | <span data-ttu-id="10d67-129">In base alle dimensioni del tenant</span><span class="sxs-lookup"><span data-stu-id="10d67-129">Based on tenant size</span></span> | <span data-ttu-id="10d67-130">- Nell'ora e quindi ogni 15 minuti</span><span class="sxs-lookup"><span data-stu-id="10d67-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="10d67-131">- Ogni giorno alle 12.00</span><span class="sxs-lookup"><span data-stu-id="10d67-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="10d67-132">Il servizio applica separatamente il limite giornaliero e di 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="10d67-132">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="10d67-133">Per ogni limite, il [portale visualizza](advanced-hunting-errors.md) un errore ogni volta che viene eseguita una query e il tenant ha utilizzato più del 10% delle risorse allocate.</span><span class="sxs-lookup"><span data-stu-id="10d67-133">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="10d67-134">Le query vengono bloccate se il tenant ha raggiunto il 100% fino al successivo ciclo giornaliero o di 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="10d67-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="10d67-135">Un set separato di limiti si applica alle query di ricerca avanzate eseguite tramite l'API.</span><span class="sxs-lookup"><span data-stu-id="10d67-135">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="10d67-136">Informazioni sulle API di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="10d67-136">Read about advanced hunting APIs</span></span>](run-advanced-query-api.md)

<span data-ttu-id="10d67-137">I clienti che eseguono più query regolarmente devono tenere traccia del consumo e applicare le [procedure](advanced-hunting-best-practices.md) consigliate di ottimizzazione per ridurre al minimo le interruzioni derivanti dal superamento di questi limiti.</span><span class="sxs-lookup"><span data-stu-id="10d67-137">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="10d67-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="10d67-138">Related topics</span></span>

- [<span data-ttu-id="10d67-139">Procedure consigliate per la ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="10d67-139">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="10d67-140">Gestire gli errori di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="10d67-140">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="10d67-141">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="10d67-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="10d67-142">Regole di rilevamento personalizzate</span><span class="sxs-lookup"><span data-stu-id="10d67-142">Custom detections rules</span></span>](custom-detection-rules.md)
