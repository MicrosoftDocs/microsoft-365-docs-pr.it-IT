---
title: Limiti di caccia avanzati in Microsoft Threat Protection
description: Informazioni sui vari limiti di servizio che mantengono attivo il servizio di caccia avanzato
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, schema, kusto, limite della CPU, limite di query, risorse, numero massimo di risultati
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ad21b4241d7cbbcc85639a0a10b47971e5fcebcb
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412695"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="ddfda-104">Limiti avanzati del servizio di caccia</span><span class="sxs-lookup"><span data-stu-id="ddfda-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ddfda-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ddfda-105">**Applies to:**</span></span>
- <span data-ttu-id="ddfda-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ddfda-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="ddfda-107">Per mantenere l'esecuzione del servizio e rispondere, Advanced Hunting imposta vari limiti per le query eseguite manualmente e tramite [le regole di rilevamento personalizzate](custom-detection-rules.md).</span><span class="sxs-lookup"><span data-stu-id="ddfda-107">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="ddfda-108">Per informazioni sui limiti, vedere la tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ddfda-108">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="ddfda-109">Limite</span><span class="sxs-lookup"><span data-stu-id="ddfda-109">Limit</span></span> | <span data-ttu-id="ddfda-110">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="ddfda-110">Size</span></span> | <span data-ttu-id="ddfda-111">Ciclo di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="ddfda-111">Refresh cycle</span></span> | <span data-ttu-id="ddfda-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ddfda-112">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="ddfda-113">DataRange</span><span class="sxs-lookup"><span data-stu-id="ddfda-113">Data range</span></span> | <span data-ttu-id="ddfda-114">30 giorni</span><span class="sxs-lookup"><span data-stu-id="ddfda-114">30 days</span></span> | <span data-ttu-id="ddfda-115">Ogni query</span><span class="sxs-lookup"><span data-stu-id="ddfda-115">Every query</span></span> | <span data-ttu-id="ddfda-116">Ogni query può cercare i dati da un massimo di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="ddfda-116">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="ddfda-117">Set di risultati</span><span class="sxs-lookup"><span data-stu-id="ddfda-117">Result set</span></span> | <span data-ttu-id="ddfda-118">10.000 righe</span><span class="sxs-lookup"><span data-stu-id="ddfda-118">10,000 rows</span></span> | <span data-ttu-id="ddfda-119">Ogni query</span><span class="sxs-lookup"><span data-stu-id="ddfda-119">Every query</span></span> | <span data-ttu-id="ddfda-120">Ogni query può restituire fino a 10.000 record.</span><span class="sxs-lookup"><span data-stu-id="ddfda-120">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="ddfda-121">Timeout</span><span class="sxs-lookup"><span data-stu-id="ddfda-121">Timeout</span></span> | <span data-ttu-id="ddfda-122">10 minuti</span><span class="sxs-lookup"><span data-stu-id="ddfda-122">10 minutes</span></span> | <span data-ttu-id="ddfda-123">Ogni query</span><span class="sxs-lookup"><span data-stu-id="ddfda-123">Every query</span></span> | <span data-ttu-id="ddfda-124">Ogni query può essere eseguita per un massimo di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="ddfda-124">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="ddfda-125">Se il servizio non viene completato entro 10 minuti, verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="ddfda-125">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="ddfda-126">Risorse della CPU</span><span class="sxs-lookup"><span data-stu-id="ddfda-126">CPU resources</span></span> | <span data-ttu-id="ddfda-127">In base alle dimensioni del tenant</span><span class="sxs-lookup"><span data-stu-id="ddfda-127">Based on tenant size</span></span> | <span data-ttu-id="ddfda-128">-All'ora e quindi ogni 15 minuti</span><span class="sxs-lookup"><span data-stu-id="ddfda-128">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="ddfda-129">-Ogni giorno a mezzanotte</span><span class="sxs-lookup"><span data-stu-id="ddfda-129">- Daily at 12 midnight</span></span> | <span data-ttu-id="ddfda-130">Il servizio applica i limiti giornalieri e di 15 minuti separatamente.</span><span class="sxs-lookup"><span data-stu-id="ddfda-130">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="ddfda-131">Per ogni limite, il [portale Visualizza un errore](advanced-hunting-errors.md) ogni volta che viene eseguita una query e il tenant ha consumato più del 10% delle risorse allocate.</span><span class="sxs-lookup"><span data-stu-id="ddfda-131">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="ddfda-132">Le query vengono bloccate se il tenant ha raggiunto il 100% fino al successivo ciclo giornaliero o di 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="ddfda-132">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="ddfda-133">Un set di limiti separato si applica alle query di ricerca avanzate eseguite tramite l'API.</span><span class="sxs-lookup"><span data-stu-id="ddfda-133">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="ddfda-134">Leggere le API di caccia avanzate</span><span class="sxs-lookup"><span data-stu-id="ddfda-134">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

<span data-ttu-id="ddfda-135">I clienti che eseguono più query regolarmente devono tenere conto dei consumi e [applicare le procedure consigliate](advanced-hunting-best-practices.md) per l'ottimizzazione per ridurre al minimo il disturbo risultante dal superamento di tali limiti.</span><span class="sxs-lookup"><span data-stu-id="ddfda-135">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ddfda-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ddfda-136">Related topics</span></span>

- [<span data-ttu-id="ddfda-137">Procedure consigliate per la ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="ddfda-137">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ddfda-138">Gestire gli errori di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="ddfda-138">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="ddfda-139">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="ddfda-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ddfda-140">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="ddfda-140">Custom detections overview</span></span>](custom-detections-overview.md)
