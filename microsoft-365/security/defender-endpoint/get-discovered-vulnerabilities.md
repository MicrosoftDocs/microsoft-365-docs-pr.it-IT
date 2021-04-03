---
title: Individuare le vulnerabilità
description: Recupera una raccolta di vulnerabilità individuate correlate a un DETERMINATO ID dispositivo.
keywords: api, api del grafico, api supportate, ottenere, elenco, file, informazioni, vulnerabilità individuate, api di gestione delle minacce &, api di gestione delle vulnerabilità mdatp tvm
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 73b8fe5140ff635791e7d42358024bb7fb4ee926
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570328"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="70a4b-104">Individuare le vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="70a4b-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="70a4b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="70a4b-105">**Applies to:**</span></span>
- [<span data-ttu-id="70a4b-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="70a4b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="70a4b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="70a4b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="70a4b-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="70a4b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="70a4b-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="70a4b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="70a4b-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="70a4b-110">API description</span></span>
<span data-ttu-id="70a4b-111">Recupera una raccolta di vulnerabilità individuate correlate a un DETERMINATO ID dispositivo.</span><span class="sxs-lookup"><span data-stu-id="70a4b-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="70a4b-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="70a4b-112">Limitations</span></span>
1. <span data-ttu-id="70a4b-113">I limiti di frequenza per questa API sono 50 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="70a4b-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="70a4b-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="70a4b-114">Permissions</span></span>

<span data-ttu-id="70a4b-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="70a4b-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="70a4b-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="70a4b-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="70a4b-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="70a4b-117">Permission type</span></span> | <span data-ttu-id="70a4b-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="70a4b-118">Permission</span></span> | <span data-ttu-id="70a4b-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="70a4b-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="70a4b-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="70a4b-120">Application</span></span> |<span data-ttu-id="70a4b-121">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="70a4b-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="70a4b-122">"Leggere le informazioni sulla vulnerabilità di Gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="70a4b-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="70a4b-123">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="70a4b-123">Delegated (work or school account)</span></span> | <span data-ttu-id="70a4b-124">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="70a4b-124">Vulnerability.Read</span></span> | <span data-ttu-id="70a4b-125">"Leggere le informazioni sulla vulnerabilità di Gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="70a4b-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="70a4b-126">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="70a4b-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="70a4b-127">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="70a4b-127">Request headers</span></span>

<span data-ttu-id="70a4b-128">Name</span><span class="sxs-lookup"><span data-stu-id="70a4b-128">Name</span></span> | <span data-ttu-id="70a4b-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="70a4b-129">Type</span></span> | <span data-ttu-id="70a4b-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="70a4b-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="70a4b-131">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="70a4b-131">Authorization</span></span> | <span data-ttu-id="70a4b-132">Stringa</span><span class="sxs-lookup"><span data-stu-id="70a4b-132">String</span></span> | <span data-ttu-id="70a4b-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="70a4b-133">Bearer {token}.</span></span> <span data-ttu-id="70a4b-134">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="70a4b-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="70a4b-135">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="70a4b-135">Request body</span></span>

<span data-ttu-id="70a4b-136">Vuoto</span><span class="sxs-lookup"><span data-stu-id="70a4b-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="70a4b-137">Risposta</span><span class="sxs-lookup"><span data-stu-id="70a4b-137">Response</span></span>

<span data-ttu-id="70a4b-138">Se ha esito positivo, questo metodo restituisce 200 OK con le informazioni sulla vulnerabilità individuate nel corpo.</span><span class="sxs-lookup"><span data-stu-id="70a4b-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="70a4b-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="70a4b-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="70a4b-140">Richiesta</span><span class="sxs-lookup"><span data-stu-id="70a4b-140">Request</span></span>

<span data-ttu-id="70a4b-141">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="70a4b-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="70a4b-142">Risposta</span><span class="sxs-lookup"><span data-stu-id="70a4b-142">Response</span></span>

<span data-ttu-id="70a4b-143">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="70a4b-143">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
}
```

## <a name="see-also"></a><span data-ttu-id="70a4b-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70a4b-144">See also</span></span>

- [<span data-ttu-id="70a4b-145">Gestione delle vulnerabilità basata sui rischi & rischio</span><span class="sxs-lookup"><span data-stu-id="70a4b-145">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="70a4b-146">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="70a4b-146">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
