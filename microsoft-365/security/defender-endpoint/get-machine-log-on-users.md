---
title: API Per ottenere gli utenti di accesso al computer
description: Scopri come usare l'API Get machine logon users per recuperare una raccolta di utenti connessi in un dispositivo in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, get, dispositivo, accesso, utenti
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 634a381ca862dc7580d82168a4b9540acc0cd394
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229024"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="ba023-104">API Per ottenere gli utenti di accesso al computer</span><span class="sxs-lookup"><span data-stu-id="ba023-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ba023-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ba023-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="ba023-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ba023-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ba023-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="ba023-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="ba023-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="ba023-108">API description</span></span>
<span data-ttu-id="ba023-109">Recupera una raccolta di utenti connessi in un dispositivo specifico.</span><span class="sxs-lookup"><span data-stu-id="ba023-109">Retrieves a collection of logged on users on a specific device.</span></span>

## <a name="limitations"></a><span data-ttu-id="ba023-110">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="ba023-110">Limitations</span></span>
1. <span data-ttu-id="ba023-111">È possibile eseguire query sugli avvisi aggiornati per l'ultimo aggiornamento in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="ba023-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="ba023-112">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="ba023-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="ba023-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ba023-113">Permissions</span></span>
<span data-ttu-id="ba023-114">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="ba023-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ba023-115">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ba023-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ba023-116">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ba023-116">Permission type</span></span> |<span data-ttu-id="ba023-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ba023-117">Permission</span></span>|<span data-ttu-id="ba023-118">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ba023-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ba023-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="ba023-119">Application</span></span> |<span data-ttu-id="ba023-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="ba023-120">User.Read.All</span></span> |<span data-ttu-id="ba023-121">"Lettura profili utente"</span><span class="sxs-lookup"><span data-stu-id="ba023-121">'Read user profiles'</span></span>
<span data-ttu-id="ba023-122">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="ba023-122">Delegated (work or school account)</span></span> | <span data-ttu-id="ba023-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="ba023-123">User.Read.All</span></span> | <span data-ttu-id="ba023-124">"Lettura profili utente"</span><span class="sxs-lookup"><span data-stu-id="ba023-124">'Read user profiles'</span></span>

> [!NOTE]
> <span data-ttu-id="ba023-125">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="ba023-125">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="ba023-126">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: "Visualizza dati".</span><span class="sxs-lookup"><span data-stu-id="ba023-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="ba023-127">Per ulteriori informazioni, vedere [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ba023-127">For more information, see [Create and manage roles](user-roles.md)).</span></span>
> - <span data-ttu-id="ba023-128">La risposta includerà gli utenti solo se il dispositivo è visibile all'utente, in base alle impostazioni del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ba023-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="ba023-129">Per altre informazioni, vedi [Creare e gestire gruppi di dispositivi.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="ba023-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="ba023-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="ba023-130">HTTP request</span></span>

```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="ba023-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="ba023-131">Request headers</span></span>

<span data-ttu-id="ba023-132">Nome</span><span class="sxs-lookup"><span data-stu-id="ba023-132">Name</span></span> | <span data-ttu-id="ba023-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="ba023-133">Type</span></span> | <span data-ttu-id="ba023-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba023-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="ba023-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ba023-135">Authorization</span></span> | <span data-ttu-id="ba023-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="ba023-136">String</span></span> | <span data-ttu-id="ba023-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ba023-137">Bearer {token}.</span></span> <span data-ttu-id="ba023-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="ba023-138">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ba023-139">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="ba023-139">Request body</span></span>

<span data-ttu-id="ba023-140">Vuoto</span><span class="sxs-lookup"><span data-stu-id="ba023-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ba023-141">Risposta</span><span class="sxs-lookup"><span data-stu-id="ba023-141">Response</span></span>

<span data-ttu-id="ba023-142">Se l'operazione ha esito positivo e [](user.md) il dispositivo esiste: 200 OK con l'elenco delle entità utente nel corpo.</span><span class="sxs-lookup"><span data-stu-id="ba023-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="ba023-143">Se il dispositivo non è stato trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="ba023-143">If device was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="ba023-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="ba023-144">Example</span></span>

### <a name="request"></a><span data-ttu-id="ba023-145">Richiesta</span><span class="sxs-lookup"><span data-stu-id="ba023-145">Request</span></span>

<span data-ttu-id="ba023-146">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="ba023-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

### <a name="response"></a><span data-ttu-id="ba023-147">Risposta</span><span class="sxs-lookup"><span data-stu-id="ba023-147">Response</span></span>

<span data-ttu-id="ba023-148">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="ba023-148">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
