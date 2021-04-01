---
title: Ottenere tutte le vulnerabilità dal computer e dal software
description: Recupera un elenco di tutte le vulnerabilità che interessano l'organizzazione in base al computer e al software
keywords: api, api del grafico, api supportate, get, informazioni sulla vulnerabilità, api mdatp tvm
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
ms.openlocfilehash: f7d67948e3b3e7a1a878386a397d2f4a6e8e998e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166901"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a><span data-ttu-id="6d705-104">Elencare le vulnerabilità in base al computer e al software</span><span class="sxs-lookup"><span data-stu-id="6d705-104">List vulnerabilities by machine and software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6d705-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="6d705-105">**Applies to:**</span></span>
- [<span data-ttu-id="6d705-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="6d705-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6d705-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d705-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6d705-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="6d705-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6d705-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="6d705-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="6d705-110">Recupera un elenco di tutte le vulnerabilità che interessano l'organizzazione per [computer](machine.md) e [software.](software.md)</span><span class="sxs-lookup"><span data-stu-id="6d705-110">Retrieves a list of all the vulnerabilities affecting the organization per [machine](machine.md) and [software](software.md).</span></span>
- <span data-ttu-id="6d705-111">Se la vulnerabilità ha un KB di correzione, verrà visualizzata nella risposta.</span><span class="sxs-lookup"><span data-stu-id="6d705-111">If the vulnerability has a fixing KB, it will appear in the response.</span></span>
- <span data-ttu-id="6d705-112">Supporta le [query OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="6d705-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
- <span data-ttu-id="6d705-113">OData ```$filter``` è supportato in tutte le proprietà.</span><span class="sxs-lookup"><span data-stu-id="6d705-113">The OData ```$filter``` is supported on all properties.</span></span>

>[!Tip]
><span data-ttu-id="6d705-114">Si tratta di un'API ideale per [l'integrazione di Power BI.](api-power-bi.md)</span><span class="sxs-lookup"><span data-stu-id="6d705-114">This is great API for [Power BI integration](api-power-bi.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="6d705-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="6d705-115">Permissions</span></span>
<span data-ttu-id="6d705-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6d705-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6d705-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint](apis-intro.md) per i dettagli.</span><span class="sxs-lookup"><span data-stu-id="6d705-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="6d705-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6d705-118">Permission type</span></span> |   <span data-ttu-id="6d705-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6d705-119">Permission</span></span>  |   <span data-ttu-id="6d705-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6d705-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="6d705-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="6d705-121">Application</span></span> |   <span data-ttu-id="6d705-122">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="6d705-122">Vulnerability.Read.All</span></span> |    <span data-ttu-id="6d705-123">"Leggere le informazioni sulla vulnerabilità di Gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="6d705-123">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="6d705-124">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="6d705-124">Delegated (work or school account)</span></span> | <span data-ttu-id="6d705-125">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="6d705-125">Vulnerability.Read</span></span> |   <span data-ttu-id="6d705-126">"Leggere le informazioni sulla vulnerabilità di Gestione delle minacce e delle vulnerabilità"</span><span class="sxs-lookup"><span data-stu-id="6d705-126">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="6d705-127">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="6d705-127">HTTP request</span></span>
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="6d705-128">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="6d705-128">Request headers</span></span>

<span data-ttu-id="6d705-129">Name</span><span class="sxs-lookup"><span data-stu-id="6d705-129">Name</span></span> | <span data-ttu-id="6d705-130">Tipo</span><span class="sxs-lookup"><span data-stu-id="6d705-130">Type</span></span> | <span data-ttu-id="6d705-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6d705-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="6d705-132">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6d705-132">Authorization</span></span> | <span data-ttu-id="6d705-133">Stringa</span><span class="sxs-lookup"><span data-stu-id="6d705-133">String</span></span> | <span data-ttu-id="6d705-134">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="6d705-134">Bearer {token}.</span></span> <span data-ttu-id="6d705-135">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="6d705-135">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="6d705-136">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="6d705-136">Request body</span></span>
<span data-ttu-id="6d705-137">Vuoto</span><span class="sxs-lookup"><span data-stu-id="6d705-137">Empty</span></span>

## <a name="response"></a><span data-ttu-id="6d705-138">Risposta</span><span class="sxs-lookup"><span data-stu-id="6d705-138">Response</span></span>
<span data-ttu-id="6d705-139">Se ha esito positivo, questo metodo restituisce 200 OK con l'elenco delle vulnerabilità nel corpo.</span><span class="sxs-lookup"><span data-stu-id="6d705-139">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="6d705-140">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d705-140">Example</span></span>

<span data-ttu-id="6d705-141">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="6d705-141">**Request**</span></span>

<span data-ttu-id="6d705-142">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="6d705-142">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

<span data-ttu-id="6d705-143">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="6d705-143">**Response**</span></span>

<span data-ttu-id="6d705-144">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="6d705-144">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="6d705-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d705-145">See also</span></span>

- [<span data-ttu-id="6d705-146">Gestione delle minacce e delle vulnerabilità basate sui rischi</span><span class="sxs-lookup"><span data-stu-id="6d705-146">Risk-based threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="6d705-147">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="6d705-147">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)