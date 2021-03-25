---
title: API per la raccolta degli stati di sicurezza dei computer
description: Recupera una raccolta di stati di sicurezza dei dispositivi usando Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, get, dispositivo, sicurezza, stato
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200366"
---
# <a name="get-machines-security-states-collection-api"></a><span data-ttu-id="aed63-104">API per la raccolta degli stati di sicurezza get machines</span><span class="sxs-lookup"><span data-stu-id="aed63-104">Get Machines security states collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aed63-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="aed63-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="aed63-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="aed63-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aed63-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="aed63-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="aed63-108">Recupera una raccolta di stati di sicurezza dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="aed63-108">Retrieves a collection of devices security states.</span></span>

## <a name="permissions"></a><span data-ttu-id="aed63-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="aed63-109">Permissions</span></span>
<span data-ttu-id="aed63-110">L'utente necessita delle autorizzazioni di lettura.</span><span class="sxs-lookup"><span data-stu-id="aed63-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="aed63-111">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="aed63-111">HTTP request</span></span>
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a><span data-ttu-id="aed63-112">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="aed63-112">Request headers</span></span>

<span data-ttu-id="aed63-113">Intestazione</span><span class="sxs-lookup"><span data-stu-id="aed63-113">Header</span></span> | <span data-ttu-id="aed63-114">Valore</span><span class="sxs-lookup"><span data-stu-id="aed63-114">Value</span></span> 
:---|:---
<span data-ttu-id="aed63-115">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aed63-115">Authorization</span></span> | <span data-ttu-id="aed63-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="aed63-116">Bearer {token}.</span></span> <span data-ttu-id="aed63-117">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="aed63-117">**Required**.</span></span>
<span data-ttu-id="aed63-118">Tipo contenuto</span><span class="sxs-lookup"><span data-stu-id="aed63-118">Content type</span></span> | <span data-ttu-id="aed63-119">application/json</span><span class="sxs-lookup"><span data-stu-id="aed63-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="aed63-120">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="aed63-120">Request body</span></span>
<span data-ttu-id="aed63-121">Vuoto</span><span class="sxs-lookup"><span data-stu-id="aed63-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="aed63-122">Risposta</span><span class="sxs-lookup"><span data-stu-id="aed63-122">Response</span></span>
<span data-ttu-id="aed63-123">Se ha esito positivo - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="aed63-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="aed63-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="aed63-124">Example</span></span>

<span data-ttu-id="aed63-125">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="aed63-125">**Request**</span></span>

<span data-ttu-id="aed63-126">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="aed63-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

<span data-ttu-id="aed63-127">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="aed63-127">**Response**</span></span>

<span data-ttu-id="aed63-128">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="aed63-128">Here is an example of the response.</span></span>
<span data-ttu-id="aed63-129">*L'ID* campo contiene l'ID del dispositivo ed è uguale all'ID *campo*\* nelle informazioni sui dispositivi.</span><span class="sxs-lookup"><span data-stu-id="aed63-129">Field *id* contains device id and equal to the field *id*\* in devices info.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
