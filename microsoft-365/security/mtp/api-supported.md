---
title: API supportate di Microsoft 365 Defender
description: API supportate di Microsoft 365 Defender
keywords: MTP, API, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719323"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="1df39-104">API supportate di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1df39-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1df39-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="1df39-105">**Applies to:**</span></span>
- <span data-ttu-id="1df39-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1df39-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1df39-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="1df39-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1df39-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="1df39-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="1df39-109">Elenco delle API disponibili</span><span class="sxs-lookup"><span data-stu-id="1df39-109">List of available APIs</span></span>

<span data-ttu-id="1df39-110">Articolo</span><span class="sxs-lookup"><span data-stu-id="1df39-110">Article</span></span> | <span data-ttu-id="1df39-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1df39-111">Description</span></span>
-|-
[<span data-ttu-id="1df39-112">Rilevazione avanzata API</span><span class="sxs-lookup"><span data-stu-id="1df39-112">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="1df39-113">Eseguire query di ricerca avanzate.</span><span class="sxs-lookup"><span data-stu-id="1df39-113">Run Advanced Hunting queries.</span></span>
[<span data-ttu-id="1df39-114">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="1df39-114">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="1df39-115">Elencare e aggiornare gli incidenti, insieme ad altre attività pratiche.</span><span class="sxs-lookup"><span data-stu-id="1df39-115">List and update incidents, along with other practical tasks.</span></span>

### <a name="endpoint-uris"></a><span data-ttu-id="1df39-116">URI dell'endpoint</span><span class="sxs-lookup"><span data-stu-id="1df39-116">Endpoint URIs</span></span>

<span data-ttu-id="1df39-117">L'URI di base per entrambe le API principali è: https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="1df39-117">The base URI for both of the main APIs is: https://api.security.microsoft.com.</span></span> <span data-ttu-id="1df39-118">Per migliorare le prestazioni, utilizzare un server più vicino alla propria geolocalizzazione:</span><span class="sxs-lookup"><span data-stu-id="1df39-118">For better performance, use a server closer to your geolocation:</span></span>

- <span data-ttu-id="1df39-119">Stati Uniti: api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1df39-119">The United States: api-us.security.microsoft.com</span></span>
- <span data-ttu-id="1df39-120">Europa: api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1df39-120">Europe: api-eu.security.microsoft.com</span></span>
- <span data-ttu-id="1df39-121">Regno Unito: api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1df39-121">The United Kingdom: api-uk.security.microsoft.com</span></span>

<span data-ttu-id="1df39-122">I token possono essere acquisiti tramite l'accesso https://api.security.microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="1df39-122">Tokens can be acquired by accessing https://api.security.microsoft.com.</span></span>

<span data-ttu-id="1df39-123">Tutte le API lungo il `/api` percorso utilizzano il protocollo [OData](https://docs.microsoft.com/odata/overview) , ad esempio, https://api.security.microsoft.com/api/incidents .</span><span class="sxs-lookup"><span data-stu-id="1df39-123">All APIs along the `/api` path use the [OData](https://docs.microsoft.com/odata/overview) Protocol; for example, https://api.security.microsoft.com/api/incidents.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1df39-124">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="1df39-124">Related articles</span></span>

- [<span data-ttu-id="1df39-125">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1df39-125">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="1df39-126">Accedere alle API di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1df39-126">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="1df39-127">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="1df39-127">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="1df39-128">Informazioni sui codici di errore</span><span class="sxs-lookup"><span data-stu-id="1df39-128">Understand error codes</span></span>](api-error-codes.md)
