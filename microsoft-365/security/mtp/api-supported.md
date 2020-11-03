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
ms.openlocfilehash: b7c0accf2d649d4ad6177260294922ee17783f2c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844961"
---
# <a name="supported-microsoft-365-defender-apis"></a><span data-ttu-id="0a02f-104">API supportate di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a02f-104">Supported Microsoft 365 Defender APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0a02f-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0a02f-105">**Applies to:**</span></span>
- <span data-ttu-id="0a02f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a02f-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="0a02f-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="0a02f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0a02f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="0a02f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="0a02f-109">URI del punto finale:</span><span class="sxs-lookup"><span data-stu-id="0a02f-109">End Point URIs:</span></span>

- <span data-ttu-id="0a02f-110">L'URI di base del servizio è il seguente: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0a02f-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="0a02f-111">Per ottenere prestazioni migliori, è possibile utilizzare il server più vicino alla posizione geografica:</span><span class="sxs-lookup"><span data-stu-id="0a02f-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="0a02f-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0a02f-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="0a02f-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0a02f-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="0a02f-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0a02f-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="0a02f-115">La risorsa per l'acquisizione di token dovrebbe essere la seguente: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="0a02f-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="0a02f-116">Tutte le API in ```/api``` path sono API OData.</span><span class="sxs-lookup"><span data-stu-id="0a02f-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="0a02f-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="0a02f-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="0a02f-118">Elenco delle API disponibili:</span><span class="sxs-lookup"><span data-stu-id="0a02f-118">List of available APIs:</span></span>

<span data-ttu-id="0a02f-119">Argomento</span><span class="sxs-lookup"><span data-stu-id="0a02f-119">Topic</span></span> | <span data-ttu-id="0a02f-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a02f-120">Description</span></span>
:---|:---
[<span data-ttu-id="0a02f-121">Rilevazione avanzata API</span><span class="sxs-lookup"><span data-stu-id="0a02f-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="0a02f-122">Eseguire query di ricerca avanzate dall'API.</span><span class="sxs-lookup"><span data-stu-id="0a02f-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="0a02f-123">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="0a02f-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="0a02f-124">Eseguire le chiamate API correlate agli incidenti, ad esempio: eventi di elenco, incidenti di aggiornamento e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="0a02f-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
