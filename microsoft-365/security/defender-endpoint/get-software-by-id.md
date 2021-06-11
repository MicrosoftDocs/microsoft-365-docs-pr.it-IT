---
title: Ottenere il software in base all'ID
description: Recupera un elenco di punteggi di esposizione per gruppo di dispositivi.
keywords: api, api graph, api supportate, get, software, Microsoft Defender for Endpoint tvm api
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
ms.openlocfilehash: d9a7d97cea96f919f1ec7cd1e37e7a8f27042c79
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845091"
---
# <a name="get-software-by-id"></a><span data-ttu-id="dd600-104">Ottenere il software in base all'ID</span><span class="sxs-lookup"><span data-stu-id="dd600-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dd600-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="dd600-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="dd600-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="dd600-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dd600-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="dd600-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="dd600-108">Recupera i dettagli del software in base all'ID.</span><span class="sxs-lookup"><span data-stu-id="dd600-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="dd600-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="dd600-109">Permissions</span></span>
<span data-ttu-id="dd600-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="dd600-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="dd600-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="dd600-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="dd600-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dd600-112">Permission type</span></span> |   <span data-ttu-id="dd600-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dd600-113">Permission</span></span>  |   <span data-ttu-id="dd600-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dd600-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="dd600-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="dd600-115">Application</span></span> | <span data-ttu-id="dd600-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="dd600-116">Software.Read.All</span></span> | <span data-ttu-id="dd600-117">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="dd600-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="dd600-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="dd600-118">Delegated (work or school account)</span></span> | <span data-ttu-id="dd600-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="dd600-119">Software.Read</span></span> | <span data-ttu-id="dd600-120">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="dd600-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="dd600-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="dd600-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="dd600-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="dd600-122">Request headers</span></span>

| <span data-ttu-id="dd600-123">Name</span><span class="sxs-lookup"><span data-stu-id="dd600-123">Name</span></span>        | <span data-ttu-id="dd600-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="dd600-124">Type</span></span> | <span data-ttu-id="dd600-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd600-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="dd600-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="dd600-126">Authorization</span></span> | <span data-ttu-id="dd600-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="dd600-127">String</span></span> | <span data-ttu-id="dd600-128">Bearer {token}. **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="dd600-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="dd600-129">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="dd600-129">Request body</span></span>
<span data-ttu-id="dd600-130">Vuoto</span><span class="sxs-lookup"><span data-stu-id="dd600-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="dd600-131">Risposta</span><span class="sxs-lookup"><span data-stu-id="dd600-131">Response</span></span>
<span data-ttu-id="dd600-132">Se ha esito positivo, questo metodo restituisce 200 OK con i dati software specificati nel corpo.</span><span class="sxs-lookup"><span data-stu-id="dd600-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="dd600-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="dd600-133">Example</span></span>

<span data-ttu-id="dd600-134">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="dd600-134">**Request**</span></span>

<span data-ttu-id="dd600-135">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="dd600-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="dd600-136">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="dd600-136">**Response**</span></span>

<span data-ttu-id="dd600-137">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="dd600-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a><span data-ttu-id="dd600-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="dd600-138">Related topics</span></span>
- [<span data-ttu-id="dd600-139">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="dd600-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="dd600-140">Threat & Vulnerability software inventory</span><span class="sxs-lookup"><span data-stu-id="dd600-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
