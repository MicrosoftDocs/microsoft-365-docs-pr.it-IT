---
title: Elencare il software
description: Recupera un elenco di inventario software
keywords: api, api del grafico, api supportate, ottenere, elenco, file, informazioni, inventario software, api di gestione delle minacce & vulnerabilità, Api di Microsoft Defender for Endpoint tvm
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 6522b546dfde7447a03b3c417be93d288e261908
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934010"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="15fc2-104">API di inventario software elenco</span><span class="sxs-lookup"><span data-stu-id="15fc2-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="15fc2-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="15fc2-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="15fc2-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="15fc2-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="15fc2-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="15fc2-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="15fc2-108">Recupera l'inventario software dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="15fc2-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="15fc2-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="15fc2-109">Permissions</span></span>
<span data-ttu-id="15fc2-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="15fc2-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="15fc2-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="15fc2-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="15fc2-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="15fc2-112">Permission type</span></span> |   <span data-ttu-id="15fc2-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="15fc2-113">Permission</span></span>  |   <span data-ttu-id="15fc2-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="15fc2-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="15fc2-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="15fc2-115">Application</span></span> |<span data-ttu-id="15fc2-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="15fc2-116">Software.Read.All</span></span> |    <span data-ttu-id="15fc2-117">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="15fc2-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="15fc2-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="15fc2-118">Delegated (work or school account)</span></span> | <span data-ttu-id="15fc2-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="15fc2-119">Software.Read</span></span> |    <span data-ttu-id="15fc2-120">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="15fc2-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="15fc2-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="15fc2-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="15fc2-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="15fc2-122">Request headers</span></span>

<span data-ttu-id="15fc2-123">Name</span><span class="sxs-lookup"><span data-stu-id="15fc2-123">Name</span></span> | <span data-ttu-id="15fc2-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="15fc2-124">Type</span></span> | <span data-ttu-id="15fc2-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15fc2-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="15fc2-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="15fc2-126">Authorization</span></span> | <span data-ttu-id="15fc2-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="15fc2-127">String</span></span> | <span data-ttu-id="15fc2-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="15fc2-128">Bearer {token}.</span></span> <span data-ttu-id="15fc2-129">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="15fc2-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="15fc2-130">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="15fc2-130">Request body</span></span>
<span data-ttu-id="15fc2-131">Vuoto</span><span class="sxs-lookup"><span data-stu-id="15fc2-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="15fc2-132">Risposta</span><span class="sxs-lookup"><span data-stu-id="15fc2-132">Response</span></span>
<span data-ttu-id="15fc2-133">Se ha esito positivo, questo metodo restituisce 200 OK con l'inventario software nel corpo.</span><span class="sxs-lookup"><span data-stu-id="15fc2-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="15fc2-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="15fc2-134">Example</span></span>

<span data-ttu-id="15fc2-135">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="15fc2-135">**Request**</span></span>

<span data-ttu-id="15fc2-136">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="15fc2-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="15fc2-137">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="15fc2-137">**Response**</span></span>

<span data-ttu-id="15fc2-138">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="15fc2-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="15fc2-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="15fc2-139">Related topics</span></span>
- [<span data-ttu-id="15fc2-140">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="15fc2-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="15fc2-141">Threat & Vulnerability software inventory</span><span class="sxs-lookup"><span data-stu-id="15fc2-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
