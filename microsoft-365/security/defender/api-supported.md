---
title: API supportate di Microsoft 365 Defender
description: API supportate di Microsoft 365 Defender
keywords: Microsoft 365 Defender, API, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f2c66dca326589807f5712c5548c177a0d08ade0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935726"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="67862-104">API supportate di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67862-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="67862-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="67862-105">**Applies to:**</span></span>
- <span data-ttu-id="67862-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67862-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67862-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="67862-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="67862-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="67862-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="67862-109">Elenco delle API disponibili</span><span class="sxs-lookup"><span data-stu-id="67862-109">List of available APIs</span></span>

<span data-ttu-id="67862-110">Articolo</span><span class="sxs-lookup"><span data-stu-id="67862-110">Article</span></span> | <span data-ttu-id="67862-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67862-111">Description</span></span>
-|-
[<span data-ttu-id="67862-112">Rilevazione avanzata API</span><span class="sxs-lookup"><span data-stu-id="67862-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="67862-113">Eseguire query di ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="67862-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="67862-114">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="67862-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="67862-115">Elencare e aggiornare gli eventi imprevisti, insieme ad altre attività pratiche.</span><span class="sxs-lookup"><span data-stu-id="67862-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="67862-116">URI endpoint</span><span class="sxs-lookup"><span data-stu-id="67862-116">Endpoint URIs</span></span>

<span data-ttu-id="67862-117">L'URI di base per entrambe le API principali è: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="67862-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="67862-118">Per ottenere prestazioni migliori, utilizzare un server più vicino alla georilevazione:</span><span class="sxs-lookup"><span data-stu-id="67862-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="67862-119">Stati Uniti: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="67862-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="67862-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="67862-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="67862-121">Regno Unito: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="67862-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="67862-122">I token possono essere acquisiti accedendo a https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="67862-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="67862-123">Tutte le API lungo `/api` il percorso usano il protocollo [OData,](/odata/overview) ad esempio https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="67862-123">All APIs along the `/api` path use the [OData](/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="67862-124">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="67862-124">Related articles</span></span>

- [<span data-ttu-id="67862-125">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67862-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="67862-126">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67862-126">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="67862-127">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="67862-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="67862-128">Comprendere i codici di errore</span><span class="sxs-lookup"><span data-stu-id="67862-128">Understand error codes</span></span>](api-error-codes.md)