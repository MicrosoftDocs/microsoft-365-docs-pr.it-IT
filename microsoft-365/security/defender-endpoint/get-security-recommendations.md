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
ms.openlocfilehash: 44f64334d08d8d0d6a5ed1e8e06baa2880859ad2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771130"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="80556-104">Ottenere consigli sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="80556-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="80556-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="80556-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="80556-106">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="80556-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="80556-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="80556-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="80556-108">Recupera una raccolta di suggerimenti per la sicurezza correlati a un DETERMINATO ID dispositivo.</span><span class="sxs-lookup"><span data-stu-id="80556-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="80556-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="80556-109">Permissions</span></span>
<span data-ttu-id="80556-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="80556-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="80556-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="80556-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="80556-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="80556-112">Permission type</span></span> |   <span data-ttu-id="80556-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="80556-113">Permission</span></span>  |   <span data-ttu-id="80556-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="80556-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="80556-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="80556-115">Application</span></span> | <span data-ttu-id="80556-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="80556-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="80556-117">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="80556-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="80556-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="80556-118">Delegated (work or school account)</span></span> | <span data-ttu-id="80556-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="80556-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="80556-120">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="80556-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="80556-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="80556-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="80556-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="80556-122">Request headers</span></span>

<span data-ttu-id="80556-123">Name</span><span class="sxs-lookup"><span data-stu-id="80556-123">Name</span></span> | <span data-ttu-id="80556-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="80556-124">Type</span></span> | <span data-ttu-id="80556-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80556-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="80556-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="80556-126">Authorization</span></span> | <span data-ttu-id="80556-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="80556-127">String</span></span> | <span data-ttu-id="80556-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="80556-128">Bearer {token}.</span></span> <span data-ttu-id="80556-129">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="80556-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="80556-130">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="80556-130">Request body</span></span>
<span data-ttu-id="80556-131">Vuoto</span><span class="sxs-lookup"><span data-stu-id="80556-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="80556-132">Risposta</span><span class="sxs-lookup"><span data-stu-id="80556-132">Response</span></span>
<span data-ttu-id="80556-133">Se ha esito positivo, questo metodo restituisce 200 OK con le indicazioni di sicurezza nel corpo.</span><span class="sxs-lookup"><span data-stu-id="80556-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="80556-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="80556-134">Example</span></span>

<span data-ttu-id="80556-135">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="80556-135">**Request**</span></span>

<span data-ttu-id="80556-136">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="80556-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="80556-137">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="80556-137">**Response**</span></span>

<span data-ttu-id="80556-138">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="80556-138">Here is an example of the response.</span></span>


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

## <a name="related-topics"></a><span data-ttu-id="80556-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="80556-139">Related topics</span></span>
- [<span data-ttu-id="80556-140">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="80556-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="80556-141">Raccomandazione per la sicurezza & rischio di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="80556-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
