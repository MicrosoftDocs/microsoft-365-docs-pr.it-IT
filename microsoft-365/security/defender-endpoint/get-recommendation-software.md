---
title: Ottenere consigli in base al software
description: Recupera un suggerimento di sicurezza relativo a un software specifico.
keywords: api, api del grafico, api supportate, ottenere, suggerimenti per la sicurezza, suggerimenti per la sicurezza per software, gestione di minacce e vulnerabilità, gestione di minacce e vulnerabilità api
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
ms.openlocfilehash: 9227987544e1cee1eeb4b65b5ae6bbf719558dd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845211"
---
# <a name="get-recommendation-by-software"></a><span data-ttu-id="0bfbb-104">Ottenere consigli in base al software</span><span class="sxs-lookup"><span data-stu-id="0bfbb-104">Get recommendation by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0bfbb-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0bfbb-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="0bfbb-106">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0bfbb-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0bfbb-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0bfbb-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="0bfbb-108">Recupera un suggerimento di sicurezza relativo a un software specifico.</span><span class="sxs-lookup"><span data-stu-id="0bfbb-108">Retrieves a security recommendation related to a specific software.</span></span>

## <a name="permissions"></a><span data-ttu-id="0bfbb-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="0bfbb-109">Permissions</span></span>
<span data-ttu-id="0bfbb-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="0bfbb-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0bfbb-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="0bfbb-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="0bfbb-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="0bfbb-112">Permission type</span></span> |   <span data-ttu-id="0bfbb-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="0bfbb-113">Permission</span></span>  |   <span data-ttu-id="0bfbb-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="0bfbb-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0bfbb-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="0bfbb-115">Application</span></span> |   <span data-ttu-id="0bfbb-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="0bfbb-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="0bfbb-117">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="0bfbb-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="0bfbb-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="0bfbb-118">Delegated (work or school account)</span></span> | <span data-ttu-id="0bfbb-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="0bfbb-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="0bfbb-120">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="0bfbb-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="0bfbb-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="0bfbb-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/software
```

## <a name="request-headers"></a><span data-ttu-id="0bfbb-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="0bfbb-122">Request headers</span></span>

<span data-ttu-id="0bfbb-123">Name</span><span class="sxs-lookup"><span data-stu-id="0bfbb-123">Name</span></span> | <span data-ttu-id="0bfbb-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="0bfbb-124">Type</span></span> | <span data-ttu-id="0bfbb-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0bfbb-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="0bfbb-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="0bfbb-126">Authorization</span></span> | <span data-ttu-id="0bfbb-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="0bfbb-127">String</span></span> | <span data-ttu-id="0bfbb-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="0bfbb-128">Bearer {token}.</span></span> <span data-ttu-id="0bfbb-129">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="0bfbb-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0bfbb-130">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="0bfbb-130">Request body</span></span>
<span data-ttu-id="0bfbb-131">Vuoto</span><span class="sxs-lookup"><span data-stu-id="0bfbb-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0bfbb-132">Risposta</span><span class="sxs-lookup"><span data-stu-id="0bfbb-132">Response</span></span>
<span data-ttu-id="0bfbb-133">Se ha esito positivo, questo metodo restituisce 200 OK con il software associato ai consigli di sicurezza nel corpo.</span><span class="sxs-lookup"><span data-stu-id="0bfbb-133">If successful, this method returns 200 OK with the software associated with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="0bfbb-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="0bfbb-134">Example</span></span>

<span data-ttu-id="0bfbb-135">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="0bfbb-135">**Request**</span></span>

<span data-ttu-id="0bfbb-136">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="0bfbb-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/software 
```

<span data-ttu-id="0bfbb-137">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="0bfbb-137">**Response**</span></span>

<span data-ttu-id="0bfbb-138">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="0bfbb-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Analytics.Contracts.PublicAPI.PublicProductDto",
    "id": "google-_-chrome",
    "name": "chrome",
    "vendor": "google",
    "weaknesses": 38,
    "publicExploit": false,
    "activeAlert": false,
    "exposedMachines": 5,
    "impactScore": 3.94418621
}
```

## <a name="related-topics"></a><span data-ttu-id="0bfbb-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0bfbb-139">Related topics</span></span>
- [<span data-ttu-id="0bfbb-140">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="0bfbb-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="0bfbb-141">Raccomandazione per la sicurezza & rischio di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="0bfbb-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
