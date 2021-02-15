---
title: API supportate di Microsoft 365 Defender
description: API supportate di Microsoft 365 Defender
keywords: MTP, API, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ee03e5a255a88c084403842e7bf0319c06c0517b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926199"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="904ad-104">API supportate di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="904ad-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="904ad-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="904ad-105">**Applies to:**</span></span>
- <span data-ttu-id="904ad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="904ad-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="904ad-107">Alcune informazioni riguardano prodotti non rilasciati in precedenza che potrebbero essere sostanzialmente modificati prima del rilascio sul mercato.</span><span class="sxs-lookup"><span data-stu-id="904ad-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="904ad-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="904ad-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="904ad-109">Elenco delle API disponibili</span><span class="sxs-lookup"><span data-stu-id="904ad-109">List of available APIs</span></span>

<span data-ttu-id="904ad-110">Articolo</span><span class="sxs-lookup"><span data-stu-id="904ad-110">Article</span></span> | <span data-ttu-id="904ad-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="904ad-111">Description</span></span>
-|-
[<span data-ttu-id="904ad-112">Rilevazione avanzata API</span><span class="sxs-lookup"><span data-stu-id="904ad-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="904ad-113">Eseguire query di Ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="904ad-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="904ad-114">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="904ad-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="904ad-115">Elencare e aggiornare gli eventi imprevisti, insieme ad altre attività pratiche.</span><span class="sxs-lookup"><span data-stu-id="904ad-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="904ad-116">URI endpoint</span><span class="sxs-lookup"><span data-stu-id="904ad-116">Endpoint URIs</span></span>

<span data-ttu-id="904ad-117">L'URI di base per entrambe le API principali è: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="904ad-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="904ad-118">Per ottenere prestazioni migliori, utilizzare un server più vicino alla georilevazione:</span><span class="sxs-lookup"><span data-stu-id="904ad-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="904ad-119">Stati Uniti: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="904ad-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="904ad-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="904ad-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="904ad-121">Regno Unito: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="904ad-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="904ad-122">I token possono essere acquisiti accedendo https://api.security.microsoft.com a .</span><span class="sxs-lookup"><span data-stu-id="904ad-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="904ad-123">Tutte le API lungo il `/api` percorso usano il protocollo [OData,](https://docs.microsoft.com/odata/overview) ad esempio https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="904ad-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="904ad-124">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="904ad-124">Related articles</span></span>

- [<span data-ttu-id="904ad-125">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="904ad-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="904ad-126">Accedere alle API di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="904ad-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="904ad-127">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="904ad-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="904ad-128">Comprendere i codici di errore</span><span class="sxs-lookup"><span data-stu-id="904ad-128">Understand error codes</span></span>](api-error-codes.md)
