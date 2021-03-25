---
title: Ottenere informazioni sull'utente correlate all'avviso
description: Scopri come usare l'API Ottieni informazioni utente correlate agli avvisi per recuperare l'utente correlato a un avviso specifico in Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, ottenere, avviso, informazioni, correlate, utente
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: aee3c6fb381341c6823fbcb6766c0b761cb3413d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166982"
---
# <a name="get-alert-related-user-information-api"></a><span data-ttu-id="7b24e-104">API per ottenere informazioni utente correlate agli avvisi</span><span class="sxs-lookup"><span data-stu-id="7b24e-104">Get alert related user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7b24e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7b24e-105">**Applies to:**</span></span>
- [<span data-ttu-id="7b24e-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="7b24e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7b24e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b24e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="7b24e-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7b24e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7b24e-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="7b24e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="7b24e-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="7b24e-110">API description</span></span>
<span data-ttu-id="7b24e-111">Recupera l'oggetto User correlato a un avviso specifico.</span><span class="sxs-lookup"><span data-stu-id="7b24e-111">Retrieves the User related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="7b24e-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="7b24e-112">Limitations</span></span>
1. <span data-ttu-id="7b24e-113">È possibile eseguire query sugli avvisi aggiornati per l'ultimo aggiornamento in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="7b24e-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="7b24e-114">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="7b24e-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="7b24e-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7b24e-115">Permissions</span></span>
<span data-ttu-id="7b24e-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="7b24e-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7b24e-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7b24e-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="7b24e-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7b24e-118">Permission type</span></span> |   <span data-ttu-id="7b24e-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7b24e-119">Permission</span></span>  |   <span data-ttu-id="7b24e-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7b24e-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7b24e-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="7b24e-121">Application</span></span> |   <span data-ttu-id="7b24e-122">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="7b24e-122">User.Read.All</span></span> | <span data-ttu-id="7b24e-123">"Lettura profili utente"</span><span class="sxs-lookup"><span data-stu-id="7b24e-123">'Read user profiles'</span></span>
<span data-ttu-id="7b24e-124">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="7b24e-124">Delegated (work or school account)</span></span> | <span data-ttu-id="7b24e-125">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="7b24e-125">User.Read.All</span></span> | <span data-ttu-id="7b24e-126">"Lettura profili utente"</span><span class="sxs-lookup"><span data-stu-id="7b24e-126">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="7b24e-127">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="7b24e-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="7b24e-128">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="7b24e-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="7b24e-129">L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="7b24e-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="7b24e-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="7b24e-130">HTTP request</span></span>
```
GET /api/alerts/{id}/user
```

## <a name="request-headers"></a><span data-ttu-id="7b24e-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="7b24e-131">Request headers</span></span>

<span data-ttu-id="7b24e-132">Name</span><span class="sxs-lookup"><span data-stu-id="7b24e-132">Name</span></span> | <span data-ttu-id="7b24e-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="7b24e-133">Type</span></span> | <span data-ttu-id="7b24e-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b24e-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="7b24e-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7b24e-135">Authorization</span></span> | <span data-ttu-id="7b24e-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="7b24e-136">String</span></span> | <span data-ttu-id="7b24e-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="7b24e-137">Bearer {token}.</span></span> <span data-ttu-id="7b24e-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="7b24e-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="7b24e-139">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="7b24e-139">Request body</span></span>
<span data-ttu-id="7b24e-140">Vuoto</span><span class="sxs-lookup"><span data-stu-id="7b24e-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="7b24e-141">Risposta</span><span class="sxs-lookup"><span data-stu-id="7b24e-141">Response</span></span>
<span data-ttu-id="7b24e-142">In caso di esito positivo e avviso ed esiste un utente- 200 OK con l'utente nel corpo.</span><span class="sxs-lookup"><span data-stu-id="7b24e-142">If successful and alert and a user exists - 200 OK with user in the body.</span></span> <span data-ttu-id="7b24e-143">Se avviso o utente non trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="7b24e-143">If alert or user not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="7b24e-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="7b24e-144">Example</span></span>

<span data-ttu-id="7b24e-145">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="7b24e-145">**Request**</span></span>

<span data-ttu-id="7b24e-146">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="7b24e-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/user
```

<span data-ttu-id="7b24e-147">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="7b24e-147">**Response**</span></span>

<span data-ttu-id="7b24e-148">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="7b24e-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "contoso\\user1",
    "accountName": "user1",
    "accountDomain": "contoso",
    "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
    "firstSeen": "2019-12-08T06:33:39Z",
    "lastSeen": "2020-01-05T06:58:34Z",
    "mostPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "leastPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "logonTypes": "Network",
    "logOnMachinesCount": 1,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": false
}
```
