---
title: Elencare le vulnerabilità in base ai suggerimenti
description: Recupera un elenco di vulnerabilità associate al suggerimento per la sicurezza.
keywords: api, api del grafico, api supportate, ottenere, elenco di vulnerabilità, suggerimenti per la sicurezza, consigli per la sicurezza per vulnerabilità, gestione delle minacce e delle vulnerabilità, api di gestione delle minacce e delle vulnerabilità
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
ms.openlocfilehash: b41ee2886d758ab0ab70b78ee6d6d863d0d482a7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198602"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="1c41e-104">Elencare le vulnerabilità in base ai suggerimenti</span><span class="sxs-lookup"><span data-stu-id="1c41e-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1c41e-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="1c41e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="1c41e-106">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="1c41e-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1c41e-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="1c41e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="1c41e-108">Recupera un elenco di vulnerabilità associate al suggerimento per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1c41e-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="1c41e-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1c41e-109">Permissions</span></span>
<span data-ttu-id="1c41e-110">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="1c41e-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1c41e-111">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="1c41e-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="1c41e-112">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1c41e-112">Permission type</span></span> |   <span data-ttu-id="1c41e-113">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1c41e-113">Permission</span></span>  |   <span data-ttu-id="1c41e-114">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1c41e-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1c41e-115">Applicazione</span><span class="sxs-lookup"><span data-stu-id="1c41e-115">Application</span></span> |   <span data-ttu-id="1c41e-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="1c41e-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="1c41e-117">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="1c41e-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="1c41e-118">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="1c41e-118">Delegated (work or school account)</span></span> | <span data-ttu-id="1c41e-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="1c41e-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="1c41e-120">"Leggere le informazioni sui suggerimenti per la sicurezza per la gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="1c41e-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="1c41e-121">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="1c41e-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="1c41e-122">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="1c41e-122">Request headers</span></span>

<span data-ttu-id="1c41e-123">Name</span><span class="sxs-lookup"><span data-stu-id="1c41e-123">Name</span></span> | <span data-ttu-id="1c41e-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="1c41e-124">Type</span></span> | <span data-ttu-id="1c41e-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c41e-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="1c41e-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1c41e-126">Authorization</span></span> | <span data-ttu-id="1c41e-127">Stringa</span><span class="sxs-lookup"><span data-stu-id="1c41e-127">String</span></span> | <span data-ttu-id="1c41e-128">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="1c41e-128">Bearer {token}.</span></span> <span data-ttu-id="1c41e-129">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="1c41e-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="1c41e-130">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="1c41e-130">Request body</span></span>
<span data-ttu-id="1c41e-131">Vuoto</span><span class="sxs-lookup"><span data-stu-id="1c41e-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1c41e-132">Risposta</span><span class="sxs-lookup"><span data-stu-id="1c41e-132">Response</span></span>
<span data-ttu-id="1c41e-133">In caso di esito positivo, questo metodo restituisce 200 OK, con l'elenco delle vulnerabilità associate al suggerimento per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="1c41e-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="1c41e-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c41e-134">Example</span></span>

<span data-ttu-id="1c41e-135">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="1c41e-135">**Request**</span></span>

<span data-ttu-id="1c41e-136">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="1c41e-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="1c41e-137">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="1c41e-137">**Response**</span></span>

<span data-ttu-id="1c41e-138">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="1c41e-138">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="1c41e-139">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1c41e-139">Related topics</span></span>
- [<span data-ttu-id="1c41e-140">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="1c41e-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="1c41e-141">Raccomandazione per la sicurezza & rischio di vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="1c41e-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
