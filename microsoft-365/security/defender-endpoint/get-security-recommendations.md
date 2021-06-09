---
title: Ottenere consigli sulla sicurezza
description: Recupera una raccolta di suggerimenti per la sicurezza correlati a un DETERMINATO ID dispositivo.
keywords: api, api del grafico, api supportate, ottenere, elenco, file, informazioni, suggerimenti per la sicurezza per dispositivo, api & gestione delle vulnerabilità per le minacce, Api di Microsoft Defender per Endpoint tvm
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
ms.openlocfilehash: 4498761fd21331821cf4676bfe65630be5436ce5
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845133"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="cbedb-104">Ottenere consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="cbedb-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cbedb-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cbedb-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="cbedb-106">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="cbedb-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cbedb-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="cbedb-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="cbedb-108">Recupera una raccolta di suggerimenti per la sicurezza correlati a un DETERMINATO ID dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cbedb-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="cbedb-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="cbedb-109">Permissions</span></span>
<span data-ttu-id="cbedb-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="cbedb-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cbedb-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cbedb-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cbedb-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="cbedb-112">Permission type</span></span> |   <span data-ttu-id="cbedb-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="cbedb-113">Permission</span></span>  |   <span data-ttu-id="cbedb-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="cbedb-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cbedb-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="cbedb-115">Application</span></span> | <span data-ttu-id="cbedb-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="cbedb-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="cbedb-117">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="cbedb-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="cbedb-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="cbedb-118">Delegated (work or school account)</span></span> | <span data-ttu-id="cbedb-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="cbedb-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="cbedb-120">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="cbedb-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="cbedb-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="cbedb-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="cbedb-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="cbedb-122">Request headers</span></span>

<span data-ttu-id="cbedb-123">Name</span><span class="sxs-lookup"><span data-stu-id="cbedb-123">Name</span></span> | <span data-ttu-id="cbedb-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="cbedb-124">Type</span></span> | <span data-ttu-id="cbedb-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cbedb-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="cbedb-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="cbedb-126">Authorization</span></span> | <span data-ttu-id="cbedb-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="cbedb-127">String</span></span> | <span data-ttu-id="cbedb-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="cbedb-128">Bearer {token}.</span></span> <span data-ttu-id="cbedb-129">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="cbedb-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cbedb-130">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="cbedb-130">Request body</span></span>
<span data-ttu-id="cbedb-131">Vuoto</span><span class="sxs-lookup"><span data-stu-id="cbedb-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cbedb-132">Risposta</span><span class="sxs-lookup"><span data-stu-id="cbedb-132">Response</span></span>
<span data-ttu-id="cbedb-133">Se ha esito positivo, questo metodo restituisce 200 OK con le indicazioni di sicurezza nel corpo.</span><span class="sxs-lookup"><span data-stu-id="cbedb-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="cbedb-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="cbedb-134">Example</span></span>

<span data-ttu-id="cbedb-135">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="cbedb-135">**Request**</span></span>

<span data-ttu-id="cbedb-136">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="cbedb-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="cbedb-137">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="cbedb-137">**Response**</span></span>

<span data-ttu-id="cbedb-138">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="cbedb-138">Here is an example of the response.</span></span>


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a><span data-ttu-id="cbedb-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="cbedb-139">Related topics</span></span>
- [<span data-ttu-id="cbedb-140">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="cbedb-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="cbedb-141">Raccomandazione per la sicurezza & rischio di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="cbedb-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
