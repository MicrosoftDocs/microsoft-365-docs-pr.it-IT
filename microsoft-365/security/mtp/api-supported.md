---
title: API di Microsoft Threat Protection supportate
description: API di Microsoft Threat Protection supportate
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
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650354"
---
# <a name="supported-microsoft-threat-protection-apis"></a><span data-ttu-id="c90bb-104">API di Microsoft Threat Protection supportate</span><span class="sxs-lookup"><span data-stu-id="c90bb-104">Supported Microsoft Threat Protection APIs</span></span> 
<span data-ttu-id="c90bb-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c90bb-105">**Applies to:**</span></span>
- <span data-ttu-id="c90bb-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c90bb-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="c90bb-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="c90bb-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c90bb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="c90bb-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


### <a name="end-point-uris"></a><span data-ttu-id="c90bb-109">URI del punto finale:</span><span class="sxs-lookup"><span data-stu-id="c90bb-109">End Point URIs:</span></span>

- <span data-ttu-id="c90bb-110">L'URI di base del servizio è il seguente: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c90bb-110">The service base URI is: https://api.security.microsoft.com</span></span> <br>

>[!NOTE]
><span data-ttu-id="c90bb-111">Per ottenere prestazioni migliori, è possibile utilizzare il server più vicino alla posizione geografica:</span><span class="sxs-lookup"><span data-stu-id="c90bb-111">For better performance, you can use server closer to your Geo location:</span></span>
> - <span data-ttu-id="c90bb-112">api-us.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c90bb-112">api-us.security.microsoft.com</span></span>
> - <span data-ttu-id="c90bb-113">api-eu.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c90bb-113">api-eu.security.microsoft.com</span></span>
> - <span data-ttu-id="c90bb-114">api-uk.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c90bb-114">api-uk.security.microsoft.com</span></span>

 - <span data-ttu-id="c90bb-115">La risorsa per l'acquisizione di token dovrebbe essere la seguente: https://api.security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c90bb-115">The resource for token acquisition should be: https://api.security.microsoft.com</span></span>

 - <span data-ttu-id="c90bb-116">Tutte le API in ```/api``` path sono API OData.</span><span class="sxs-lookup"><span data-stu-id="c90bb-116">All the APIs under ```/api``` path are OData APIs.</span></span> <span data-ttu-id="c90bb-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span><span class="sxs-lookup"><span data-stu-id="c90bb-117">e.g. ```https://api.security.microsoft.com/api/incidents```</span></span>

## <a name="list-of-available-apis"></a><span data-ttu-id="c90bb-118">Elenco delle API disponibili:</span><span class="sxs-lookup"><span data-stu-id="c90bb-118">List of available APIs:</span></span>

<span data-ttu-id="c90bb-119">Argomento</span><span class="sxs-lookup"><span data-stu-id="c90bb-119">Topic</span></span> | <span data-ttu-id="c90bb-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c90bb-120">Description</span></span>
:---|:---
[<span data-ttu-id="c90bb-121">API di caccia avanzata</span><span class="sxs-lookup"><span data-stu-id="c90bb-121">Advanced Hunting API</span></span>](api-advanced-hunting.md) | <span data-ttu-id="c90bb-122">Eseguire query di ricerca avanzate dall'API.</span><span class="sxs-lookup"><span data-stu-id="c90bb-122">Run Advanced Hunting queries from API.</span></span>
[<span data-ttu-id="c90bb-123">API Incident</span><span class="sxs-lookup"><span data-stu-id="c90bb-123">Incident APIs</span></span>](api-incident.md) | <span data-ttu-id="c90bb-124">Eseguire le chiamate API correlate agli incidenti, ad esempio: eventi di elenco, incidenti di aggiornamento e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="c90bb-124">Run incident related API calls such as: list incidents, update incident and more.</span></span>
