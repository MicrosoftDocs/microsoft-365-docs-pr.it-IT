---
title: API supportate per Microsoft Threat Protection
description: API supportate per Microsoft Threat Protection
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
ms.openlocfilehash: fda90945f09abfadfe56ea11469687130d88b2a7
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203696"
---
# <a name="supported-microsoft-threat-protection-apis"></a><span data-ttu-id="b0ace-104">API supportate per Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b0ace-104">Supported Microsoft Threat Protection APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b0ace-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b0ace-105">**Applies to:**</span></span>
- <span data-ttu-id="b0ace-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b0ace-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="b0ace-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="b0ace-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b0ace-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b0ace-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="b0ace-109">URI del punto finale:</span><span class="sxs-lookup"><span data-stu-id="b0ace-109">End Point URIs:</span></span>

- <span data-ttu-id="b0ace-110">L'URI di base del servizio è il seguente: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b0ace-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="b0ace-111">Per ottenere prestazioni migliori, è possibile utilizzare il server più vicino alla posizione geografica:</span><span class="sxs-lookup"><span data-stu-id="b0ace-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="b0ace-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b0ace-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="b0ace-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b0ace-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="b0ace-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b0ace-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="b0ace-115">La risorsa per l'acquisizione di token dovrebbe essere la seguente: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b0ace-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="b0ace-116">Tutte le API in ```/api``` path sono API OData.</span><span class="sxs-lookup"><span data-stu-id="b0ace-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="b0ace-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="b0ace-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="b0ace-118">Elenco delle API disponibili:</span><span class="sxs-lookup"><span data-stu-id="b0ace-118">List of available APIs:</span></span>

<span data-ttu-id="b0ace-119">Argomento</span><span class="sxs-lookup"><span data-stu-id="b0ace-119">Topic</span></span> | <span data-ttu-id="b0ace-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b0ace-120">Description</span></span>
:---|:---
[<span data-ttu-id="b0ace-121">Rilevazione avanzata API</span><span class="sxs-lookup"><span data-stu-id="b0ace-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="b0ace-122">Eseguire query di ricerca avanzate dall'API.</span><span class="sxs-lookup"><span data-stu-id="b0ace-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="b0ace-123">Incidenti delle API</span><span class="sxs-lookup"><span data-stu-id="b0ace-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="b0ace-124">Eseguire le chiamate API correlate agli incidenti, ad esempio: eventi di elenco, incidenti di aggiornamento e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="b0ace-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
