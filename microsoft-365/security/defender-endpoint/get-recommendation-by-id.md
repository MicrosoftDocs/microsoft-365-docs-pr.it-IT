---
title: Ottenere suggerimenti tramite ID
description: Recupera un suggerimento di sicurezza in base al relativo ID.
keywords: api, api del grafico, api supportate, ottenere, suggerimenti per la sicurezza, consigli sulla sicurezza per ID, gestione delle minacce e delle vulnerabilità, api di gestione delle minacce e delle vulnerabilità
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
ms.openlocfilehash: 45a151fc5855a4a2b1ba63a50b54737c90e6bdd1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199514"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="576d6-104">Ottenere suggerimenti in base all'ID</span><span class="sxs-lookup"><span data-stu-id="576d6-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="576d6-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="576d6-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="576d6-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="576d6-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="576d6-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="576d6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="576d6-108">Recupera un suggerimento di sicurezza in base al relativo ID.</span><span class="sxs-lookup"><span data-stu-id="576d6-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="576d6-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="576d6-109">Permissions</span></span>
<span data-ttu-id="576d6-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="576d6-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="576d6-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="576d6-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="576d6-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="576d6-112">Permission type</span></span> |   <span data-ttu-id="576d6-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="576d6-113">Permission</span></span>  |   <span data-ttu-id="576d6-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="576d6-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="576d6-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="576d6-115">Application</span></span> |   <span data-ttu-id="576d6-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="576d6-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="576d6-117">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="576d6-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="576d6-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="576d6-118">Delegated (work or school account)</span></span> | <span data-ttu-id="576d6-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="576d6-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="576d6-120">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="576d6-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="576d6-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="576d6-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="576d6-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="576d6-122">Request headers</span></span>

<span data-ttu-id="576d6-123">Name</span><span class="sxs-lookup"><span data-stu-id="576d6-123">Name</span></span> | <span data-ttu-id="576d6-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="576d6-124">Type</span></span> | <span data-ttu-id="576d6-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="576d6-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="576d6-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="576d6-126">Authorization</span></span> | <span data-ttu-id="576d6-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="576d6-127">String</span></span> | <span data-ttu-id="576d6-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="576d6-128">Bearer {token}.</span></span> <span data-ttu-id="576d6-129">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="576d6-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="576d6-130">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="576d6-130">Request body</span></span>
<span data-ttu-id="576d6-131">Vuoto</span><span class="sxs-lookup"><span data-stu-id="576d6-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="576d6-132">Risposta</span><span class="sxs-lookup"><span data-stu-id="576d6-132">Response</span></span>
<span data-ttu-id="576d6-133">Se ha esito positivo, questo metodo restituisce 200 OK con le indicazioni di sicurezza nel corpo.</span><span class="sxs-lookup"><span data-stu-id="576d6-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="576d6-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="576d6-134">Example</span></span>

<span data-ttu-id="576d6-135">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="576d6-135">**Request**</span></span>

<span data-ttu-id="576d6-136">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="576d6-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="576d6-137">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="576d6-137">**Response**</span></span>

<span data-ttu-id="576d6-138">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="576d6-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a><span data-ttu-id="576d6-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="576d6-139">Related topics</span></span>
- [<span data-ttu-id="576d6-140">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="576d6-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="576d6-141">Raccomandazione per la sicurezza & rischio di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="576d6-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
