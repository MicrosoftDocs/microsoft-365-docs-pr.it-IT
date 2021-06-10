---
title: Get CVE-KB map API
description: Scopri come usare l'API di mapping Get CVE-KB per recuperare una mappa dei dettagli di CVE a KB e CVE in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, get, cve, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166889"
---
# <a name="get-cve-kb-map-api"></a><span data-ttu-id="08ccd-104">Get CVE-KB map API</span><span class="sxs-lookup"><span data-stu-id="08ccd-104">Get CVE-KB map API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="08ccd-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="08ccd-105">**Applies to:**</span></span>
- [<span data-ttu-id="08ccd-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="08ccd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="08ccd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08ccd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="08ccd-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="08ccd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="08ccd-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="08ccd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="08ccd-110">Recupera una mappa dei dettagli di CVE a KB e CVE.</span><span class="sxs-lookup"><span data-stu-id="08ccd-110">Retrieves a map of CVE's to KB's and CVE details.</span></span>

## <a name="permissions"></a><span data-ttu-id="08ccd-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="08ccd-111">Permissions</span></span>
<span data-ttu-id="08ccd-112">L'utente necessita delle autorizzazioni di lettura.</span><span class="sxs-lookup"><span data-stu-id="08ccd-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="08ccd-113">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="08ccd-113">HTTP request</span></span>
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a><span data-ttu-id="08ccd-114">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="08ccd-114">Request headers</span></span>

<span data-ttu-id="08ccd-115">Intestazione</span><span class="sxs-lookup"><span data-stu-id="08ccd-115">Header</span></span> | <span data-ttu-id="08ccd-116">Valore</span><span class="sxs-lookup"><span data-stu-id="08ccd-116">Value</span></span> 
:---|:---
<span data-ttu-id="08ccd-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="08ccd-117">Authorization</span></span> | <span data-ttu-id="08ccd-118">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="08ccd-118">Bearer {token}.</span></span> <span data-ttu-id="08ccd-119">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="08ccd-119">**Required**.</span></span>
<span data-ttu-id="08ccd-120">Tipo di contenuto</span><span class="sxs-lookup"><span data-stu-id="08ccd-120">Content type</span></span> | <span data-ttu-id="08ccd-121">application/json</span><span class="sxs-lookup"><span data-stu-id="08ccd-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="08ccd-122">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="08ccd-122">Request body</span></span>
<span data-ttu-id="08ccd-123">Vuoto</span><span class="sxs-lookup"><span data-stu-id="08ccd-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="08ccd-124">Risposta</span><span class="sxs-lookup"><span data-stu-id="08ccd-124">Response</span></span>
<span data-ttu-id="08ccd-125">Se l'operazione ha esito positivo e la mappa esiste- 200 OK.</span><span class="sxs-lookup"><span data-stu-id="08ccd-125">If successful and map exists - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="08ccd-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="08ccd-126">Example</span></span>

<span data-ttu-id="08ccd-127">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="08ccd-127">**Request**</span></span>

<span data-ttu-id="08ccd-128">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="08ccd-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

<span data-ttu-id="08ccd-129">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="08ccd-129">**Response**</span></span>

<span data-ttu-id="08ccd-130">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="08ccd-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
