---
title: API per la raccolta di gruppi di computer RBAC
description: Scopri come usare l'API Per recuperare una raccolta di gruppi di dispositivi RBAC in Microsoft Defender Advanced Threat Protection.
keywords: api, api del grafico, api supportate, get, RBAC, gruppo
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
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167021"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="83859-104">Ottenere l'API di raccolta KB</span><span class="sxs-lookup"><span data-stu-id="83859-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="83859-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="83859-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="83859-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="83859-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="83859-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="83859-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="83859-108">Recupera una raccolta di gruppi di dispositivi RBAC.</span><span class="sxs-lookup"><span data-stu-id="83859-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="83859-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="83859-109">Permissions</span></span>
<span data-ttu-id="83859-110">L'utente necessita delle autorizzazioni di lettura.</span><span class="sxs-lookup"><span data-stu-id="83859-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="83859-111">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="83859-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="83859-112">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="83859-112">Request headers</span></span>

<span data-ttu-id="83859-113">Intestazione</span><span class="sxs-lookup"><span data-stu-id="83859-113">Header</span></span> | <span data-ttu-id="83859-114">Valore</span><span class="sxs-lookup"><span data-stu-id="83859-114">Value</span></span> 
:---|:---
<span data-ttu-id="83859-115">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="83859-115">Authorization</span></span> | <span data-ttu-id="83859-116">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="83859-116">Bearer {token}.</span></span> <span data-ttu-id="83859-117">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="83859-117">**Required**.</span></span>
<span data-ttu-id="83859-118">Tipo contenuto</span><span class="sxs-lookup"><span data-stu-id="83859-118">Content type</span></span> | <span data-ttu-id="83859-119">application/json</span><span class="sxs-lookup"><span data-stu-id="83859-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="83859-120">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="83859-120">Request body</span></span>
<span data-ttu-id="83859-121">Vuoto</span><span class="sxs-lookup"><span data-stu-id="83859-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="83859-122">Risposta</span><span class="sxs-lookup"><span data-stu-id="83859-122">Response</span></span>
<span data-ttu-id="83859-123">Se ha esito positivo - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="83859-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="83859-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="83859-124">Example</span></span>

<span data-ttu-id="83859-125">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="83859-125">**Request**</span></span>

<span data-ttu-id="83859-126">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="83859-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="83859-127">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="83859-127">**Response**</span></span>

<span data-ttu-id="83859-128">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="83859-128">Here is an example of the response.</span></span>
<span data-ttu-id="83859-129">L'ID campo contiene **l'ID** del gruppo di dispositivi ed è uguale al **campo rbacGroupId** nelle informazioni sui dispositivi.</span><span class="sxs-lookup"><span data-stu-id="83859-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="83859-130">Il **campo non raggruppato** è true solo per un gruppo per tutti i dispositivi che non sono stati assegnati ad alcun gruppo.</span><span class="sxs-lookup"><span data-stu-id="83859-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="83859-131">Il nome di questo gruppo è "UnassignedGroup".</span><span class="sxs-lookup"><span data-stu-id="83859-131">This group as usual has name "UnassignedGroup".</span></span>

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```