---
title: Elencare le vulnerabilità in base al software
description: Recuperare un elenco di vulnerabilità nel software installato.
keywords: api, api del grafico, api supportate, get, elenco delle vulnerabilità, api mdatp tvm
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
ms.technology: mde
ms.openlocfilehash: 8f05c1a67c845e7f88cbcb3ee88cf7a664d5a4bf
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167210"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="80b8c-104">Elencare le vulnerabilità in base al software</span><span class="sxs-lookup"><span data-stu-id="80b8c-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="80b8c-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="80b8c-105">**Applies to:**</span></span>
- [<span data-ttu-id="80b8c-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="80b8c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="80b8c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="80b8c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="80b8c-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="80b8c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="80b8c-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="80b8c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="80b8c-110">Recuperare un elenco di vulnerabilità nel software installato.</span><span class="sxs-lookup"><span data-stu-id="80b8c-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="80b8c-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="80b8c-111">Permissions</span></span>
<span data-ttu-id="80b8c-112">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="80b8c-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="80b8c-113">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="80b8c-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="80b8c-114">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="80b8c-114">Permission type</span></span> |   <span data-ttu-id="80b8c-115">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="80b8c-115">Permission</span></span>  |   <span data-ttu-id="80b8c-116">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="80b8c-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="80b8c-117">Applicazione</span><span class="sxs-lookup"><span data-stu-id="80b8c-117">Application</span></span> | <span data-ttu-id="80b8c-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="80b8c-118">Software.Read.All</span></span> | <span data-ttu-id="80b8c-119">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="80b8c-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="80b8c-120">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="80b8c-120">Delegated (work or school account)</span></span> | <span data-ttu-id="80b8c-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="80b8c-121">Software.Read</span></span> | <span data-ttu-id="80b8c-122">"Leggere informazioni sul software di gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="80b8c-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="80b8c-123">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="80b8c-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="80b8c-124">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="80b8c-124">Request headers</span></span>

| <span data-ttu-id="80b8c-125">Name</span><span class="sxs-lookup"><span data-stu-id="80b8c-125">Name</span></span>        | <span data-ttu-id="80b8c-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="80b8c-126">Type</span></span> | <span data-ttu-id="80b8c-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80b8c-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="80b8c-128">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="80b8c-128">Authorization</span></span> | <span data-ttu-id="80b8c-129">Stringa</span><span class="sxs-lookup"><span data-stu-id="80b8c-129">String</span></span> | <span data-ttu-id="80b8c-130">Bearer {token}. **Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="80b8c-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="80b8c-131">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="80b8c-131">Request body</span></span>
<span data-ttu-id="80b8c-132">Vuoto</span><span class="sxs-lookup"><span data-stu-id="80b8c-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="80b8c-133">Risposta</span><span class="sxs-lookup"><span data-stu-id="80b8c-133">Response</span></span>
<span data-ttu-id="80b8c-134">Se ha esito positivo, questo metodo restituisce 200 OK con un elenco delle vulnerabilità esposte dal software specificato.</span><span class="sxs-lookup"><span data-stu-id="80b8c-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="80b8c-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="80b8c-135">Example</span></span>

<span data-ttu-id="80b8c-136">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="80b8c-136">**Request**</span></span>

<span data-ttu-id="80b8c-137">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="80b8c-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="80b8c-138">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="80b8c-138">**Response**</span></span>

<span data-ttu-id="80b8c-139">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="80b8c-139">Here is an example of the response.</span></span>

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
