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
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245601"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="37998-104">Quote di ricerca avanzate e parametri di utilizzo</span><span class="sxs-lookup"><span data-stu-id="37998-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="37998-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="37998-105">**Applies to:**</span></span>
- <span data-ttu-id="37998-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37998-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="37998-107">Per mantenere il servizio efficiente e reattivo, la ricerca avanzata imposta diverse quote e parametri di utilizzo (noti anche come "limiti del servizio").</span><span class="sxs-lookup"><span data-stu-id="37998-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="37998-108">Queste quote e parametri si applicano separatamente alle query eseguite manualmente e alle query eseguite utilizzando [regole di rilevamento personalizzate.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="37998-108">These quotas and parameters apply separately to queries run manually and to queries run using [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="37998-109">I clienti che eseguono regolarmente più query devono tenere conto di questi limiti e applicare le procedure consigliate di ottimizzazione [per](advanced-hunting-best-practices.md) ridurre al minimo le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="37998-109">Customers who run multiple queries regularly should be mindful of these limits and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="37998-110">Fare riferimento alla tabella seguente per comprendere le quote esistenti e i parametri di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="37998-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="37998-111">Quota o parametro</span><span class="sxs-lookup"><span data-stu-id="37998-111">Quota or parameter</span></span> | <span data-ttu-id="37998-112">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="37998-112">Size</span></span> | <span data-ttu-id="37998-113">Ciclo di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="37998-113">Refresh cycle</span></span> | <span data-ttu-id="37998-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37998-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="37998-115">DataRange</span><span class="sxs-lookup"><span data-stu-id="37998-115">Data range</span></span> | <span data-ttu-id="37998-116">30 giorni</span><span class="sxs-lookup"><span data-stu-id="37998-116">30 days</span></span> | <span data-ttu-id="37998-117">Ogni query</span><span class="sxs-lookup"><span data-stu-id="37998-117">Every query</span></span> | <span data-ttu-id="37998-118">Ogni query può cercare dati fino agli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="37998-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="37998-119">Set di risultati</span><span class="sxs-lookup"><span data-stu-id="37998-119">Result set</span></span> | <span data-ttu-id="37998-120">10.000 righe</span><span class="sxs-lookup"><span data-stu-id="37998-120">10,000 rows</span></span> | <span data-ttu-id="37998-121">Ogni query</span><span class="sxs-lookup"><span data-stu-id="37998-121">Every query</span></span> | <span data-ttu-id="37998-122">Ogni query può restituire fino a 10.000 record.</span><span class="sxs-lookup"><span data-stu-id="37998-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="37998-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="37998-123">Timeout</span></span> | <span data-ttu-id="37998-124">10 minuti</span><span class="sxs-lookup"><span data-stu-id="37998-124">10 minutes</span></span> | <span data-ttu-id="37998-125">Ogni query</span><span class="sxs-lookup"><span data-stu-id="37998-125">Every query</span></span> | <span data-ttu-id="37998-126">Ogni query può essere eseguita per un massimo di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="37998-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="37998-127">Se non viene completato entro 10 minuti, il servizio visualizza un errore.</span><span class="sxs-lookup"><span data-stu-id="37998-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="37998-128">Risorse CPU</span><span class="sxs-lookup"><span data-stu-id="37998-128">CPU resources</span></span> | <span data-ttu-id="37998-129">In base alle dimensioni del tenant</span><span class="sxs-lookup"><span data-stu-id="37998-129">Based on tenant size</span></span> | <span data-ttu-id="37998-130">Ogni 15 minuti</span><span class="sxs-lookup"><span data-stu-id="37998-130">Every 15 minutes</span></span> | <span data-ttu-id="37998-131">Il [portale visualizza un errore ogni](advanced-hunting-errors.md) volta che viene eseguita una query e il tenant ha utilizzato più del 10% delle risorse allocate.</span><span class="sxs-lookup"><span data-stu-id="37998-131">The [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="37998-132">Le query vengono bloccate se il tenant ha raggiunto il 100% fino al successivo ciclo di 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="37998-132">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="37998-133">Un set separato di quote e parametri si applica alle query di ricerca avanzate eseguite tramite l'API.</span><span class="sxs-lookup"><span data-stu-id="37998-133">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="37998-134">Informazioni sulle API di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="37998-134">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="37998-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="37998-135">Related topics</span></span>

- [<span data-ttu-id="37998-136">Procedure consigliate per la ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="37998-136">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="37998-137">Gestire gli errori di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="37998-137">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="37998-138">Panoramica della rilevazione avanzata</span><span class="sxs-lookup"><span data-stu-id="37998-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="37998-139">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="37998-139">Custom detections overview</span></span>](custom-detections-overview.md)