---
title: Elencare distribuzione versione software
description: Recupera un elenco della distribuzione delle versioni software dell'organizzazione
keywords: api, api del grafico, api supportate, get, distribuzione della versione software, Api Di Microsoft Defender per Endpoint tvm
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
ms.openlocfilehash: 7ac7fdf4c38846e2e8be614567ddb87a98e3a96c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772126"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="858ef-104">Elencare distribuzione versione software</span><span class="sxs-lookup"><span data-stu-id="858ef-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="858ef-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="858ef-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="858ef-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="858ef-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="858ef-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="858ef-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="858ef-108">Recupera un elenco della distribuzione delle versioni software dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="858ef-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="858ef-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="858ef-109">Permissions</span></span>
<span data-ttu-id="858ef-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="858ef-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="858ef-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="858ef-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="858ef-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="858ef-112">Permission type</span></span> |   <span data-ttu-id="858ef-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="858ef-113">Permission</span></span>  |   <span data-ttu-id="858ef-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="858ef-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="858ef-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="858ef-115">Application</span></span> | <span data-ttu-id="858ef-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="858ef-116">Software.Read.All</span></span> | <span data-ttu-id="858ef-117">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="858ef-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="858ef-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="858ef-118">Delegated (work or school account)</span></span> | <span data-ttu-id="858ef-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="858ef-119">Software.Read</span></span> | <span data-ttu-id="858ef-120">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="858ef-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="858ef-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="858ef-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="858ef-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="858ef-122">Request headers</span></span>

| <span data-ttu-id="858ef-123">Name</span><span class="sxs-lookup"><span data-stu-id="858ef-123">Name</span></span>        | <span data-ttu-id="858ef-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="858ef-124">Type</span></span> | <span data-ttu-id="858ef-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="858ef-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="858ef-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="858ef-126">Authorization</span></span> | <span data-ttu-id="858ef-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="858ef-127">String</span></span> | <span data-ttu-id="858ef-128">Bearer {token}. **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="858ef-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="858ef-129">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="858ef-129">Request body</span></span>
<span data-ttu-id="858ef-130">Vuoto</span><span class="sxs-lookup"><span data-stu-id="858ef-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="858ef-131">Risposta</span><span class="sxs-lookup"><span data-stu-id="858ef-131">Response</span></span>
<span data-ttu-id="858ef-132">Se ha esito positivo, questo metodo restituisce 200 OK con un elenco di dati delle distribuzioni software nel corpo.</span><span class="sxs-lookup"><span data-stu-id="858ef-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="858ef-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="858ef-133">Example</span></span>

<span data-ttu-id="858ef-134">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="858ef-134">**Request**</span></span>

<span data-ttu-id="858ef-135">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="858ef-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="858ef-136">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="858ef-136">**Response**</span></span>

<span data-ttu-id="858ef-137">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="858ef-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="858ef-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="858ef-138">Related topics</span></span>
- [<span data-ttu-id="858ef-139">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="858ef-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="858ef-140">Threat & Vulnerability software inventory</span><span class="sxs-lookup"><span data-stu-id="858ef-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
