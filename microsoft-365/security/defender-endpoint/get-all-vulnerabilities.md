---
title: Ottenere tutte le vulnerabilità
description: Recupera un elenco di tutte le vulnerabilità che interessano l'organizzazione
keywords: api, api del grafico, api supportate, ottenere, informazioni sulla vulnerabilità, Api di Microsoft Defender per Endpoint tvm
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
ms.openlocfilehash: bfce003f586c5bfa32d65c834bb244ac13f6cf31
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935090"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="89694-104">Elencare vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="89694-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="89694-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="89694-105">**Applies to:**</span></span>
- [<span data-ttu-id="89694-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="89694-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="89694-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89694-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="89694-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="89694-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="89694-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="89694-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="89694-110">Recupera un elenco di tutte le vulnerabilità che interessano l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="89694-110">Retrieves a list of all the vulnerabilities affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="89694-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="89694-111">Permissions</span></span>
<span data-ttu-id="89694-112">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="89694-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="89694-113">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="89694-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="89694-114">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="89694-114">Permission type</span></span> |   <span data-ttu-id="89694-115">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="89694-115">Permission</span></span>  |   <span data-ttu-id="89694-116">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="89694-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="89694-117">Applicazione</span><span class="sxs-lookup"><span data-stu-id="89694-117">Application</span></span> |   <span data-ttu-id="89694-118">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="89694-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="89694-119">"Leggere le informazioni sulla vulnerabilità di Gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="89694-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="89694-120">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="89694-120">Delegated (work or school account)</span></span> | <span data-ttu-id="89694-121">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="89694-121">Vulnerability.Read</span></span> |   <span data-ttu-id="89694-122">"Leggere le informazioni sulla vulnerabilità di Gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="89694-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="89694-123">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="89694-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="89694-124">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="89694-124">Request headers</span></span>

<span data-ttu-id="89694-125">Name</span><span class="sxs-lookup"><span data-stu-id="89694-125">Name</span></span> | <span data-ttu-id="89694-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="89694-126">Type</span></span> | <span data-ttu-id="89694-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89694-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="89694-128">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="89694-128">Authorization</span></span> | <span data-ttu-id="89694-129">Stringa</span><span class="sxs-lookup"><span data-stu-id="89694-129">String</span></span> | <span data-ttu-id="89694-130">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="89694-130">Bearer {token}.</span></span> <span data-ttu-id="89694-131">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="89694-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="89694-132">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="89694-132">Request body</span></span>
<span data-ttu-id="89694-133">Vuoto</span><span class="sxs-lookup"><span data-stu-id="89694-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="89694-134">Risposta</span><span class="sxs-lookup"><span data-stu-id="89694-134">Response</span></span>
<span data-ttu-id="89694-135">Se ha esito positivo, questo metodo restituisce 200 OK con l'elenco delle vulnerabilità nel corpo.</span><span class="sxs-lookup"><span data-stu-id="89694-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="89694-136">Esempio</span><span class="sxs-lookup"><span data-stu-id="89694-136">Example</span></span>

<span data-ttu-id="89694-137">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="89694-137">**Request**</span></span>

<span data-ttu-id="89694-138">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="89694-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="89694-139">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="89694-139">**Response**</span></span>

<span data-ttu-id="89694-140">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="89694-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Vulnerabilities",
    "value": [
        {
            "id": "CVE-2019-0608",
            "name": "CVE-2019-0608",
            "description": "A spoofing vulnerability exists when Microsoft Browsers does not properly parse HTTP content. An attacker who successfully exploited this vulnerability could impersonate a user request by crafting HTTP queries. The specially crafted website could either spoof content or serve as a pivot to chain an attack with other vulnerabilities in web services.To exploit the vulnerability, the user must click a specially crafted URL. In an email attack scenario, an attacker could send an email message containing the specially crafted URL to the user in an attempt to convince the user to click it.In a web-based attack scenario, an attacker could host a specially crafted website designed to appear as a legitimate website to the user. However, the attacker would have no way to force the user to visit the specially crafted website. The attacker would have to convince the user to visit the specially crafted website, typically by way of enticement in an email or instant message, and then convince the user to interact with content on the website.The update addresses the vulnerability by correcting how Microsoft Browsers parses HTTP responses.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 4,
            "publishedOn": "2019-10-08T00:00:00Z",
            "updatedOn": "2019-12-16T16:20:00Z",
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

## <a name="see-also"></a><span data-ttu-id="89694-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89694-141">See also</span></span>
- [<span data-ttu-id="89694-142">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="89694-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="89694-143">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="89694-143">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
