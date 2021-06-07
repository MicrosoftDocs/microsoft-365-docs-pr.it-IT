---
title: Elencare il software
description: Recupera un elenco di inventario software
keywords: api, api del grafico, api supportate, ottenere, elenco, file, informazioni, inventario software, api & gestione delle vulnerabilità minacce, Api di Microsoft Defender per Endpoint tvm
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f7e71c58396fd4b3ed40ba88aab5c2757ae41a41
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771082"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="e76a8-104">API di inventario software elenco</span><span class="sxs-lookup"><span data-stu-id="e76a8-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e76a8-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e76a8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="e76a8-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="e76a8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e76a8-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="e76a8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="e76a8-108">Recupera l'inventario software dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e76a8-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="e76a8-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="e76a8-109">Permissions</span></span>
<span data-ttu-id="e76a8-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e76a8-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e76a8-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="e76a8-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="e76a8-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e76a8-112">Permission type</span></span> |   <span data-ttu-id="e76a8-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e76a8-113">Permission</span></span>  |   <span data-ttu-id="e76a8-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e76a8-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e76a8-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="e76a8-115">Application</span></span> |<span data-ttu-id="e76a8-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="e76a8-116">Software.Read.All</span></span> |    <span data-ttu-id="e76a8-117">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="e76a8-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="e76a8-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="e76a8-118">Delegated (work or school account)</span></span> | <span data-ttu-id="e76a8-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="e76a8-119">Software.Read</span></span> |    <span data-ttu-id="e76a8-120">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="e76a8-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="e76a8-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="e76a8-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="e76a8-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="e76a8-122">Request headers</span></span>

<span data-ttu-id="e76a8-123">Name</span><span class="sxs-lookup"><span data-stu-id="e76a8-123">Name</span></span> | <span data-ttu-id="e76a8-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="e76a8-124">Type</span></span> | <span data-ttu-id="e76a8-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e76a8-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="e76a8-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="e76a8-126">Authorization</span></span> | <span data-ttu-id="e76a8-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="e76a8-127">String</span></span> | <span data-ttu-id="e76a8-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e76a8-128">Bearer {token}.</span></span> <span data-ttu-id="e76a8-129">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="e76a8-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="e76a8-130">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="e76a8-130">Request body</span></span>
<span data-ttu-id="e76a8-131">Vuoto</span><span class="sxs-lookup"><span data-stu-id="e76a8-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e76a8-132">Risposta</span><span class="sxs-lookup"><span data-stu-id="e76a8-132">Response</span></span>
<span data-ttu-id="e76a8-133">Se ha esito positivo, questo metodo restituisce 200 OK con l'inventario software nel corpo.</span><span class="sxs-lookup"><span data-stu-id="e76a8-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="e76a8-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="e76a8-134">Example</span></span>

<span data-ttu-id="e76a8-135">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="e76a8-135">**Request**</span></span>

<span data-ttu-id="e76a8-136">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="e76a8-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="e76a8-137">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="e76a8-137">**Response**</span></span>

<span data-ttu-id="e76a8-138">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="e76a8-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="e76a8-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e76a8-139">Related topics</span></span>
- [<span data-ttu-id="e76a8-140">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="e76a8-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="e76a8-141">Threat & Vulnerability software inventory</span><span class="sxs-lookup"><span data-stu-id="e76a8-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
