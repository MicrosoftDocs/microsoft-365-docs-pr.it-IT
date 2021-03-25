---
title: API per ottenere informazioni utente
description: Scopri come usare l'API Get user information per recuperare un'entità Utente in base alla chiave o al nome utente in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, ottenere, informazioni utente, utente
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 1c5b8fa6e0f1fd887c857bd4e6451a5e59b708af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198542"
---
# <a name="get-user-information-api"></a><span data-ttu-id="a393a-104">API per ottenere informazioni utente</span><span class="sxs-lookup"><span data-stu-id="a393a-104">Get user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a393a-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a393a-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="a393a-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a393a-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a393a-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a393a-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> <span data-ttu-id="a393a-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="a393a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a393a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="a393a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)
<span data-ttu-id="a393a-110">Recuperare un'entità User in base alla chiave (nome utente).</span><span class="sxs-lookup"><span data-stu-id="a393a-110">Retrieve a User entity by key (user name).</span></span>

## <a name="permissions"></a><span data-ttu-id="a393a-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a393a-111">Permissions</span></span>
<span data-ttu-id="a393a-112">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a393a-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a393a-113">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a393a-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a393a-114">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a393a-114">Permission type</span></span> |   <span data-ttu-id="a393a-115">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a393a-115">Permission</span></span>  |   <span data-ttu-id="a393a-116">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a393a-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a393a-117">Applicazione</span><span class="sxs-lookup"><span data-stu-id="a393a-117">Application</span></span> |   <span data-ttu-id="a393a-118">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="a393a-118">User.Read.All</span></span> | <span data-ttu-id="a393a-119">"Leggi tutti i profili utente"</span><span class="sxs-lookup"><span data-stu-id="a393a-119">'Read all user profiles'</span></span>

## <a name="http-request"></a><span data-ttu-id="a393a-120">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="a393a-120">HTTP request</span></span>
```
GET /api/users/{id}/
```

## <a name="request-headers"></a><span data-ttu-id="a393a-121">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="a393a-121">Request headers</span></span>

<span data-ttu-id="a393a-122">Name</span><span class="sxs-lookup"><span data-stu-id="a393a-122">Name</span></span> | <span data-ttu-id="a393a-123">Tipo</span><span class="sxs-lookup"><span data-stu-id="a393a-123">Type</span></span> | <span data-ttu-id="a393a-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a393a-124">Description</span></span>
:---|:---|:---
<span data-ttu-id="a393a-125">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a393a-125">Authorization</span></span> | <span data-ttu-id="a393a-126">Stringa</span><span class="sxs-lookup"><span data-stu-id="a393a-126">String</span></span> | <span data-ttu-id="a393a-127">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="a393a-127">Bearer {token}.</span></span> <span data-ttu-id="a393a-128">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="a393a-128">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="a393a-129">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="a393a-129">Request body</span></span>
<span data-ttu-id="a393a-130">Vuoto</span><span class="sxs-lookup"><span data-stu-id="a393a-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="a393a-131">Risposta</span><span class="sxs-lookup"><span data-stu-id="a393a-131">Response</span></span>
<span data-ttu-id="a393a-132">Se l'operazione ha esito positivo e l'utente esiste: 200 OK con [l'entità](user.md) utente nel corpo.</span><span class="sxs-lookup"><span data-stu-id="a393a-132">If successful and user exists - 200 OK with [user](user.md) entity in the body.</span></span> <span data-ttu-id="a393a-133">Se l'utente non esiste- 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="a393a-133">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="a393a-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="a393a-134">Example</span></span>

<span data-ttu-id="a393a-135">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="a393a-135">**Request**</span></span>

<span data-ttu-id="a393a-136">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="a393a-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/users/user1
Content-type: application/json
```

<span data-ttu-id="a393a-137">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="a393a-137">**Response**</span></span>

<span data-ttu-id="a393a-138">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="a393a-138">Here is an example of the response.</span></span>


```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "user1",
    "firstSeen": "2018-08-02T00:00:00Z",
    "lastSeen": "2018-08-04T00:00:00Z",
    "mostPrevalentMachineId": null,
    "leastPrevalentMachineId": null,
    "logonTypes": "Network",
    "logOnMachinesCount": 3,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": null
}
```
