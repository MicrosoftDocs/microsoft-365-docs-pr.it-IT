---
title: Elencare le vulnerabilità per consiglio
description: Recupera un elenco di vulnerabilità associate al suggerimento per la sicurezza.
keywords: api, api del grafico, api supportate, ottenere, elenco di vulnerabilità, suggerimenti per la sicurezza, suggerimenti per la sicurezza per le vulnerabilità, gestione di minacce e vulnerabilità, gestione di minacce e vulnerabilità api
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
ms.openlocfilehash: d5a59c3cd57aa369b1edb46eebddffb84a2b8c78
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845151"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="5c798-104">Elencare le vulnerabilità per consiglio</span><span class="sxs-lookup"><span data-stu-id="5c798-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5c798-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5c798-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="5c798-106">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5c798-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5c798-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5c798-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="5c798-108">Recupera un elenco di vulnerabilità associate al suggerimento per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5c798-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="5c798-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5c798-109">Permissions</span></span>
<span data-ttu-id="5c798-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5c798-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5c798-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="5c798-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="5c798-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5c798-112">Permission type</span></span> |   <span data-ttu-id="5c798-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5c798-113">Permission</span></span>  |   <span data-ttu-id="5c798-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5c798-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5c798-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="5c798-115">Application</span></span> |   <span data-ttu-id="5c798-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="5c798-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="5c798-117">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="5c798-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="5c798-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="5c798-118">Delegated (work or school account)</span></span> | <span data-ttu-id="5c798-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="5c798-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="5c798-120">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="5c798-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="5c798-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="5c798-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="5c798-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="5c798-122">Request headers</span></span>

<span data-ttu-id="5c798-123">Name</span><span class="sxs-lookup"><span data-stu-id="5c798-123">Name</span></span> | <span data-ttu-id="5c798-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="5c798-124">Type</span></span> | <span data-ttu-id="5c798-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5c798-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="5c798-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5c798-126">Authorization</span></span> | <span data-ttu-id="5c798-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="5c798-127">String</span></span> | <span data-ttu-id="5c798-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5c798-128">Bearer {token}.</span></span> <span data-ttu-id="5c798-129">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="5c798-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5c798-130">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="5c798-130">Request body</span></span>
<span data-ttu-id="5c798-131">Vuoto</span><span class="sxs-lookup"><span data-stu-id="5c798-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5c798-132">Risposta</span><span class="sxs-lookup"><span data-stu-id="5c798-132">Response</span></span>
<span data-ttu-id="5c798-133">In caso di esito positivo, questo metodo restituisce 200 OK, con l'elenco delle vulnerabilità associate al suggerimento per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5c798-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="5c798-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c798-134">Example</span></span>

<span data-ttu-id="5c798-135">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="5c798-135">**Request**</span></span>

<span data-ttu-id="5c798-136">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="5c798-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="5c798-137">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="5c798-137">**Response**</span></span>

<span data-ttu-id="5c798-138">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="5c798-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
     ]
}
```

## <a name="related-topics"></a><span data-ttu-id="5c798-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5c798-139">Related topics</span></span>
- [<span data-ttu-id="5c798-140">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="5c798-140">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="5c798-141">Raccomandazione per la sicurezza & rischio di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="5c798-141">Threat & Vulnerability security recommendation</span></span>](/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
