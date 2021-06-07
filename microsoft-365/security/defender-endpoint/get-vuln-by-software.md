---
title: Elencare le vulnerabilità per software
description: Recuperare un elenco di vulnerabilità nel software installato.
keywords: api, api del grafico, api supportate, get, elenco delle vulnerabilità, Api di Microsoft Defender per Endpoint tvm
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
ms.openlocfilehash: 18a2cf87cd0e6b898a9f2aa4d6ecd47a86a8c7f6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769918"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="101a6-104">Elencare le vulnerabilità per software</span><span class="sxs-lookup"><span data-stu-id="101a6-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="101a6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="101a6-105">**Applies to:**</span></span>
- [<span data-ttu-id="101a6-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="101a6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="101a6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="101a6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="101a6-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="101a6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="101a6-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="101a6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="101a6-110">Recuperare un elenco di vulnerabilità nel software installato.</span><span class="sxs-lookup"><span data-stu-id="101a6-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="101a6-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="101a6-111">Permissions</span></span>
<span data-ttu-id="101a6-112">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="101a6-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="101a6-113">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="101a6-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="101a6-114">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="101a6-114">Permission type</span></span> |   <span data-ttu-id="101a6-115">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="101a6-115">Permission</span></span>  |   <span data-ttu-id="101a6-116">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="101a6-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="101a6-117">Applicazione</span><span class="sxs-lookup"><span data-stu-id="101a6-117">Application</span></span> | <span data-ttu-id="101a6-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="101a6-118">Software.Read.All</span></span> | <span data-ttu-id="101a6-119">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="101a6-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="101a6-120">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="101a6-120">Delegated (work or school account)</span></span> | <span data-ttu-id="101a6-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="101a6-121">Software.Read</span></span> | <span data-ttu-id="101a6-122">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="101a6-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="101a6-123">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="101a6-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="101a6-124">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="101a6-124">Request headers</span></span>

| <span data-ttu-id="101a6-125">Name</span><span class="sxs-lookup"><span data-stu-id="101a6-125">Name</span></span>        | <span data-ttu-id="101a6-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="101a6-126">Type</span></span> | <span data-ttu-id="101a6-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="101a6-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="101a6-128">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="101a6-128">Authorization</span></span> | <span data-ttu-id="101a6-129">Stringa</span><span class="sxs-lookup"><span data-stu-id="101a6-129">String</span></span> | <span data-ttu-id="101a6-130">Bearer {token}. **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="101a6-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="101a6-131">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="101a6-131">Request body</span></span>
<span data-ttu-id="101a6-132">Vuoto</span><span class="sxs-lookup"><span data-stu-id="101a6-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="101a6-133">Risposta</span><span class="sxs-lookup"><span data-stu-id="101a6-133">Response</span></span>
<span data-ttu-id="101a6-134">Se ha esito positivo, questo metodo restituisce 200 OK con un elenco delle vulnerabilità esposte dal software specificato.</span><span class="sxs-lookup"><span data-stu-id="101a6-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="101a6-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="101a6-135">Example</span></span>

<span data-ttu-id="101a6-136">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="101a6-136">**Request**</span></span>

<span data-ttu-id="101a6-137">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="101a6-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="101a6-138">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="101a6-138">**Response**</span></span>

<span data-ttu-id="101a6-139">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="101a6-139">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
            {
                "id": "CVE-2017-0140",
                "name": "CVE-2017-0140",
                "description": "A security feature bypass vulnerability exists when Microsoft Edge improperly handles requests of different origins. The vulnerability allows Microsoft Edge to bypass Same-Origin Policy (SOP) restrictions, and to allow requests that should otherwise be ignored. An attacker who successfully exploited the vulnerability could force the browser to send data that would otherwise be restricted.In a web-based attack scenario, an attacker could host a specially crafted website that is designed to exploit the vulnerability through Microsoft Edge and then convince a user to view the website. The attacker could also take advantage of compromised websites, and websites that accept or host user-provided content or advertisements. These websites could contain specially crafted content that could exploit the vulnerability.The security update addresses the vulnerability by modifying how affected Microsoft Edge handles different-origin requests.",
                "severity": "Medium",
                "cvssV3": 4.2,
                "exposedMachines": 1,
                "publishedOn": "2017-03-14T00:00:00Z",
                "updatedOn": "2019-10-03T00:03:00Z",
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

