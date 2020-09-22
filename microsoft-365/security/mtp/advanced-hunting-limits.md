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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: aaba01f5970c9abf55f5fae760d1ba1fed8ba914
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199878"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="d1cee-104">Limiti avanzati del servizio di caccia</span><span class="sxs-lookup"><span data-stu-id="d1cee-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d1cee-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d1cee-105">**Applies to:**</span></span>
- <span data-ttu-id="d1cee-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d1cee-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d1cee-107">Per mantenere l'esecuzione del servizio e rispondere, Advanced Hunting imposta vari limiti per le query eseguite manualmente e tramite [le regole di rilevamento personalizzate](custom-detection-rules.md).</span><span class="sxs-lookup"><span data-stu-id="d1cee-107">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="d1cee-108">Per informazioni sui limiti, vedere la tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d1cee-108">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="d1cee-109">Limite</span><span class="sxs-lookup"><span data-stu-id="d1cee-109">Limit</span></span> | <span data-ttu-id="d1cee-110">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="d1cee-110">Size</span></span> | <span data-ttu-id="d1cee-111">Ciclo di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d1cee-111">Refresh cycle</span></span> | <span data-ttu-id="d1cee-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d1cee-112">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="d1cee-113">DataRange</span><span class="sxs-lookup"><span data-stu-id="d1cee-113">Data range</span></span> | <span data-ttu-id="d1cee-114">30 giorni</span><span class="sxs-lookup"><span data-stu-id="d1cee-114">30 days</span></span> | <span data-ttu-id="d1cee-115">Ogni query</span><span class="sxs-lookup"><span data-stu-id="d1cee-115">Every query</span></span> | <span data-ttu-id="d1cee-116">Ogni query può cercare i dati da un massimo di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="d1cee-116">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="d1cee-117">Set di risultati</span><span class="sxs-lookup"><span data-stu-id="d1cee-117">Result set</span></span> | <span data-ttu-id="d1cee-118">10.000 righe</span><span class="sxs-lookup"><span data-stu-id="d1cee-118">10,000 rows</span></span> | <span data-ttu-id="d1cee-119">Ogni query</span><span class="sxs-lookup"><span data-stu-id="d1cee-119">Every query</span></span> | <span data-ttu-id="d1cee-120">Ogni query può restituire fino a 10.000 record.</span><span class="sxs-lookup"><span data-stu-id="d1cee-120">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="d1cee-121">Timeout</span><span class="sxs-lookup"><span data-stu-id="d1cee-121">Timeout</span></span> | <span data-ttu-id="d1cee-122">10 minuti</span><span class="sxs-lookup"><span data-stu-id="d1cee-122">10 minutes</span></span> | <span data-ttu-id="d1cee-123">Ogni query</span><span class="sxs-lookup"><span data-stu-id="d1cee-123">Every query</span></span> | <span data-ttu-id="d1cee-124">Ogni query può essere eseguita per un massimo di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="d1cee-124">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="d1cee-125">Se il servizio non viene completato entro 10 minuti, verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="d1cee-125">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="d1cee-126">Risorse della CPU</span><span class="sxs-lookup"><span data-stu-id="d1cee-126">CPU resources</span></span> | <span data-ttu-id="d1cee-127">In base alle dimensioni del tenant</span><span class="sxs-lookup"><span data-stu-id="d1cee-127">Based on tenant size</span></span> | <span data-ttu-id="d1cee-128">-All'ora e quindi ogni 15 minuti</span><span class="sxs-lookup"><span data-stu-id="d1cee-128">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="d1cee-129">-Ogni giorno a mezzanotte</span><span class="sxs-lookup"><span data-stu-id="d1cee-129">- Daily at 12 midnight</span></span> | <span data-ttu-id="d1cee-130">Il servizio applica i limiti giornalieri e di 15 minuti separatamente.</span><span class="sxs-lookup"><span data-stu-id="d1cee-130">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="d1cee-131">Per ogni limite, il [portale Visualizza un errore](advanced-hunting-errors.md) ogni volta che viene eseguita una query e il tenant ha consumato più del 10% delle risorse allocate.</span><span class="sxs-lookup"><span data-stu-id="d1cee-131">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="d1cee-132">Le query vengono bloccate se il tenant ha raggiunto il 100% fino al successivo ciclo giornaliero o di 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="d1cee-132">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="d1cee-133">Un set di limiti separato si applica alle query di ricerca avanzate eseguite tramite l'API.</span><span class="sxs-lookup"><span data-stu-id="d1cee-133">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="d1cee-134">Leggere le API di caccia avanzate</span><span class="sxs-lookup"><span data-stu-id="d1cee-134">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

<span data-ttu-id="d1cee-135">I clienti che eseguono più query regolarmente devono tenere conto dei consumi e [applicare le procedure consigliate](advanced-hunting-best-practices.md) per l'ottimizzazione per ridurre al minimo il disturbo risultante dal superamento di tali limiti.</span><span class="sxs-lookup"><span data-stu-id="d1cee-135">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d1cee-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d1cee-136">Related topics</span></span>

- [<span data-ttu-id="d1cee-137">Procedure consigliate per la ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="d1cee-137">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d1cee-138">Gestire gli errori di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="d1cee-138">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="d1cee-139">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="d1cee-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d1cee-140">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="d1cee-140">Custom detections overview</span></span>](custom-detections-overview.md)
