---
title: Ottenere l'API di raccolta KB
description: Recupera una raccolta di informazioni di knowledge base (KB) e dettagli kb con Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, get, kb
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
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167177"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="a4cd4-104">Ottenere l'API di raccolta KB</span><span class="sxs-lookup"><span data-stu-id="a4cd4-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a4cd4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="a4cd4-105">**Applies to:**</span></span>
- [<span data-ttu-id="a4cd4-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="a4cd4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a4cd4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4cd4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a4cd4-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a4cd4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a4cd4-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a4cd4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="a4cd4-110">Recupera una raccolta di dettagli di KB e KB.</span><span class="sxs-lookup"><span data-stu-id="a4cd4-110">Retrieves a collection of KB's and KB details.</span></span>

## <a name="permissions"></a><span data-ttu-id="a4cd4-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a4cd4-111">Permissions</span></span>
<span data-ttu-id="a4cd4-112">L'utente necessita delle autorizzazioni di lettura.</span><span class="sxs-lookup"><span data-stu-id="a4cd4-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="a4cd4-113">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="a4cd4-113">HTTP request</span></span>
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a><span data-ttu-id="a4cd4-114">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="a4cd4-114">Request headers</span></span>

<span data-ttu-id="a4cd4-115">Intestazione</span><span class="sxs-lookup"><span data-stu-id="a4cd4-115">Header</span></span> | <span data-ttu-id="a4cd4-116">Valore</span><span class="sxs-lookup"><span data-stu-id="a4cd4-116">Value</span></span> 
:---|:---
<span data-ttu-id="a4cd4-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a4cd4-117">Authorization</span></span> | <span data-ttu-id="a4cd4-118">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a4cd4-118">Bearer {token}.</span></span> <span data-ttu-id="a4cd4-119">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="a4cd4-119">**Required**.</span></span>
<span data-ttu-id="a4cd4-120">Tipo di contenuto</span><span class="sxs-lookup"><span data-stu-id="a4cd4-120">Content type</span></span> | <span data-ttu-id="a4cd4-121">application/json</span><span class="sxs-lookup"><span data-stu-id="a4cd4-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="a4cd4-122">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="a4cd4-122">Request body</span></span>
<span data-ttu-id="a4cd4-123">Vuoto</span><span class="sxs-lookup"><span data-stu-id="a4cd4-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a4cd4-124">Risposta</span><span class="sxs-lookup"><span data-stu-id="a4cd4-124">Response</span></span>
<span data-ttu-id="a4cd4-125">Se ha esito positivo - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="a4cd4-125">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="a4cd4-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="a4cd4-126">Example</span></span>

<span data-ttu-id="a4cd4-127">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="a4cd4-127">**Request**</span></span>

<span data-ttu-id="a4cd4-128">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="a4cd4-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

<span data-ttu-id="a4cd4-129">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="a4cd4-129">**Response**</span></span>

<span data-ttu-id="a4cd4-130">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="a4cd4-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
