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
ms.openlocfilehash: 7d0e38789cfc576c0c3f1a8be352796e674ac13a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845007"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="22854-104">Elencare distribuzione versione software</span><span class="sxs-lookup"><span data-stu-id="22854-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="22854-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="22854-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="22854-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="22854-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="22854-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="22854-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="22854-108">Recupera un elenco della distribuzione delle versioni software dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="22854-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="22854-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="22854-109">Permissions</span></span>
<span data-ttu-id="22854-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="22854-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="22854-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="22854-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="22854-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="22854-112">Permission type</span></span> |   <span data-ttu-id="22854-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="22854-113">Permission</span></span>  |   <span data-ttu-id="22854-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="22854-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="22854-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="22854-115">Application</span></span> | <span data-ttu-id="22854-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="22854-116">Software.Read.All</span></span> | <span data-ttu-id="22854-117">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="22854-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="22854-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="22854-118">Delegated (work or school account)</span></span> | <span data-ttu-id="22854-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="22854-119">Software.Read</span></span> | <span data-ttu-id="22854-120">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="22854-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="22854-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="22854-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="22854-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="22854-122">Request headers</span></span>

| <span data-ttu-id="22854-123">Name</span><span class="sxs-lookup"><span data-stu-id="22854-123">Name</span></span>        | <span data-ttu-id="22854-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="22854-124">Type</span></span> | <span data-ttu-id="22854-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22854-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="22854-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="22854-126">Authorization</span></span> | <span data-ttu-id="22854-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="22854-127">String</span></span> | <span data-ttu-id="22854-128">Bearer {token}. **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="22854-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="22854-129">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="22854-129">Request body</span></span>
<span data-ttu-id="22854-130">Vuoto</span><span class="sxs-lookup"><span data-stu-id="22854-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="22854-131">Risposta</span><span class="sxs-lookup"><span data-stu-id="22854-131">Response</span></span>
<span data-ttu-id="22854-132">Se ha esito positivo, questo metodo restituisce 200 OK con un elenco di dati delle distribuzioni software nel corpo.</span><span class="sxs-lookup"><span data-stu-id="22854-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="22854-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="22854-133">Example</span></span>

<span data-ttu-id="22854-134">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="22854-134">**Request**</span></span>

<span data-ttu-id="22854-135">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="22854-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="22854-136">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="22854-136">**Response**</span></span>

<span data-ttu-id="22854-137">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="22854-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="22854-138">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="22854-138">Related topics</span></span>
- [<span data-ttu-id="22854-139">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="22854-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="22854-140">Threat & Vulnerability software inventory</span><span class="sxs-lookup"><span data-stu-id="22854-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
