---
title: Quote avanzate di caccia e parametri di utilizzo in Microsoft Threat Protection
description: Comprendere le varie quote e i parametri di utilizzo (limiti di servizio) che mantengono attivo il servizio di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, schema, kusto, limite della CPU, limite di query, risorse, risultati massimi, quota, parametri, allocazione
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 192fb47aafdd20bd5e1f0774a64ec3215f1203d1
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636906"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="af7e5-104">Quote avanzate di caccia e parametri di utilizzo</span><span class="sxs-lookup"><span data-stu-id="af7e5-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="af7e5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="af7e5-105">**Applies to:**</span></span>
- <span data-ttu-id="af7e5-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="af7e5-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="af7e5-107">Per mantenere l'esecuzione del servizio e rispondere, Advanced Hunting imposta varie quote e parametri di utilizzo (noti anche come "limiti del servizio").</span><span class="sxs-lookup"><span data-stu-id="af7e5-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="af7e5-108">Queste quote e parametri si applicano alle query eseguite manualmente e tramite [regole di rilevamento personalizzate](custom-detection-rules.md).</span><span class="sxs-lookup"><span data-stu-id="af7e5-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="af7e5-109">I clienti che eseguono più query regolarmente devono tenere conto dei consumi e [applicare le procedure consigliate](advanced-hunting-best-practices.md) per ridurre al minimo le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="af7e5-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="af7e5-110">Fare riferimento alla tabella seguente per comprendere le quote esistenti e i parametri di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="af7e5-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="af7e5-111">Quota o parametro</span><span class="sxs-lookup"><span data-stu-id="af7e5-111">Quota or parameter</span></span> | <span data-ttu-id="af7e5-112">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="af7e5-112">Size</span></span> | <span data-ttu-id="af7e5-113">Ciclo di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="af7e5-113">Refresh cycle</span></span> | <span data-ttu-id="af7e5-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="af7e5-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="af7e5-115">DataRange</span><span class="sxs-lookup"><span data-stu-id="af7e5-115">Data range</span></span> | <span data-ttu-id="af7e5-116">30 giorni</span><span class="sxs-lookup"><span data-stu-id="af7e5-116">30 days</span></span> | <span data-ttu-id="af7e5-117">Ogni query</span><span class="sxs-lookup"><span data-stu-id="af7e5-117">Every query</span></span> | <span data-ttu-id="af7e5-118">Ogni query può cercare i dati da un massimo di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="af7e5-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="af7e5-119">Set di risultati</span><span class="sxs-lookup"><span data-stu-id="af7e5-119">Result set</span></span> | <span data-ttu-id="af7e5-120">10.000 righe</span><span class="sxs-lookup"><span data-stu-id="af7e5-120">10,000 rows</span></span> | <span data-ttu-id="af7e5-121">Ogni query</span><span class="sxs-lookup"><span data-stu-id="af7e5-121">Every query</span></span> | <span data-ttu-id="af7e5-122">Ogni query può restituire fino a 10.000 record.</span><span class="sxs-lookup"><span data-stu-id="af7e5-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="af7e5-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="af7e5-123">Timeout</span></span> | <span data-ttu-id="af7e5-124">10 minuti</span><span class="sxs-lookup"><span data-stu-id="af7e5-124">10 minutes</span></span> | <span data-ttu-id="af7e5-125">Ogni query</span><span class="sxs-lookup"><span data-stu-id="af7e5-125">Every query</span></span> | <span data-ttu-id="af7e5-126">Ogni query può essere eseguita per un massimo di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="af7e5-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="af7e5-127">Se il servizio non viene completato entro 10 minuti, verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="af7e5-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="af7e5-128">Risorse della CPU</span><span class="sxs-lookup"><span data-stu-id="af7e5-128">CPU resources</span></span> | <span data-ttu-id="af7e5-129">In base alle dimensioni del tenant</span><span class="sxs-lookup"><span data-stu-id="af7e5-129">Based on tenant size</span></span> | <span data-ttu-id="af7e5-130">-All'ora e quindi ogni 15 minuti</span><span class="sxs-lookup"><span data-stu-id="af7e5-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="af7e5-131">-Ogni giorno a mezzanotte</span><span class="sxs-lookup"><span data-stu-id="af7e5-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="af7e5-132">Il servizio impone la quota giornaliera e quella di 15 minuti separatamente.</span><span class="sxs-lookup"><span data-stu-id="af7e5-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="af7e5-133">Per ogni quota, nel [portale viene visualizzato un errore](advanced-hunting-errors.md) ogni volta che viene eseguita una query e il tenant ha consumato più del 10% delle risorse allocate.</span><span class="sxs-lookup"><span data-stu-id="af7e5-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="af7e5-134">Le query vengono bloccate se il tenant ha raggiunto il 100% fino al successivo ciclo giornaliero o di 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="af7e5-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="af7e5-135">Un insieme separato di quote e parametri si applica alle query di ricerca avanzate eseguite tramite l'API.</span><span class="sxs-lookup"><span data-stu-id="af7e5-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="af7e5-136">Leggere le API di caccia avanzate</span><span class="sxs-lookup"><span data-stu-id="af7e5-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="af7e5-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="af7e5-137">Related topics</span></span>

- [<span data-ttu-id="af7e5-138">Procedure consigliate per la ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="af7e5-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="af7e5-139">Gestire gli errori di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="af7e5-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="af7e5-140">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="af7e5-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="af7e5-141">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="af7e5-141">Custom detections overview</span></span>](custom-detections-overview.md)