---
title: Elencare tutti i consigli
description: Recupera un elenco di tutti i suggerimenti per la sicurezza che interessano l'organizzazione.
keywords: api, api del grafico, api supportate, ottenere, suggerimenti per la sicurezza, Api di Microsoft Defender for Endpoint tvm, gestione di minacce e vulnerabilità, gestione di minacce e vulnerabilità api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: eb009a01e36739ab5e9ec009d053a7bd4e177907
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841535"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="34980-104">Elencare tutti i consigli</span><span class="sxs-lookup"><span data-stu-id="34980-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="34980-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="34980-105">**Applies to:**</span></span>
- [<span data-ttu-id="34980-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="34980-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="34980-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34980-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="34980-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="34980-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="34980-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="34980-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="34980-110">Recupera un elenco di tutti i suggerimenti per la sicurezza che interessano l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="34980-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="34980-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="34980-111">Permissions</span></span>
<span data-ttu-id="34980-112">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="34980-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="34980-113">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="34980-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="34980-114">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="34980-114">Permission type</span></span> |   <span data-ttu-id="34980-115">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="34980-115">Permission</span></span>  |   <span data-ttu-id="34980-116">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="34980-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="34980-117">Applicazione</span><span class="sxs-lookup"><span data-stu-id="34980-117">Application</span></span> |   <span data-ttu-id="34980-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="34980-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="34980-119">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="34980-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="34980-120">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="34980-120">Delegated (work or school account)</span></span> | <span data-ttu-id="34980-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="34980-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="34980-122">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="34980-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="34980-123">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="34980-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="34980-124">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="34980-124">Request headers</span></span>

<span data-ttu-id="34980-125">Name</span><span class="sxs-lookup"><span data-stu-id="34980-125">Name</span></span> | <span data-ttu-id="34980-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="34980-126">Type</span></span> | <span data-ttu-id="34980-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="34980-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="34980-128">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="34980-128">Authorization</span></span> | <span data-ttu-id="34980-129">Stringa</span><span class="sxs-lookup"><span data-stu-id="34980-129">String</span></span> | <span data-ttu-id="34980-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="34980-130">Bearer {token}.</span></span> <span data-ttu-id="34980-131">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="34980-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="34980-132">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="34980-132">Request body</span></span>
<span data-ttu-id="34980-133">Vuoto</span><span class="sxs-lookup"><span data-stu-id="34980-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="34980-134">Risposta</span><span class="sxs-lookup"><span data-stu-id="34980-134">Response</span></span>
<span data-ttu-id="34980-135">Se ha esito positivo, questo metodo restituisce 200 OK con l'elenco dei suggerimenti per la sicurezza nel corpo.</span><span class="sxs-lookup"><span data-stu-id="34980-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="34980-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="34980-136">Example</span></span>

<span data-ttu-id="34980-137">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="34980-137">**Request**</span></span>

<span data-ttu-id="34980-138">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="34980-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="34980-139">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="34980-139">**Response**</span></span>

<span data-ttu-id="34980-140">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="34980-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10",
            "productName": "windows_10",
            "recommendationName": "Update Windows 10",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10"
        }
        ...
     ]
}
```
## <a name="see-also"></a><span data-ttu-id="34980-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34980-141">See also</span></span>
- [<span data-ttu-id="34980-142">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="34980-142">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="34980-143">Raccomandazione per la sicurezza & rischio di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="34980-143">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

