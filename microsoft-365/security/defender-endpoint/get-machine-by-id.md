---
title: Get machine by ID API
description: Scopri come usare l'API Get machine by ID per recuperare un computer in base all'ID dispositivo o al nome del computer in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, get, dispositivi, entità, id
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
ms.openlocfilehash: 29423230d0d8d4baaa1acca9a3661dc3436f303d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200096"
---
# <a name="get-machine-by-id-api"></a><span data-ttu-id="5d789-104">Get machine by ID API</span><span class="sxs-lookup"><span data-stu-id="5d789-104">Get machine by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5d789-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5d789-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>


> <span data-ttu-id="5d789-106">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5d789-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5d789-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5d789-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5d789-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="5d789-108">API description</span></span>
<span data-ttu-id="5d789-109">Recupera un computer [specifico in](machine.md) base all'ID dispositivo o al nome del computer.</span><span class="sxs-lookup"><span data-stu-id="5d789-109">Retrieves specific [Machine](machine.md) by its device ID or computer name.</span></span>


## <a name="limitations"></a><span data-ttu-id="5d789-110">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="5d789-110">Limitations</span></span>
1. <span data-ttu-id="5d789-111">È possibile visualizzare i dispositivi per l'ultima volta in base ai criteri di conservazione configurati.</span><span class="sxs-lookup"><span data-stu-id="5d789-111">You can get devices last seen according to your configured retention policy.</span></span>
2. <span data-ttu-id="5d789-112">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="5d789-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5d789-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5d789-113">Permissions</span></span>
<span data-ttu-id="5d789-114">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5d789-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5d789-115">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5d789-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5d789-116">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5d789-116">Permission type</span></span> |   <span data-ttu-id="5d789-117">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5d789-117">Permission</span></span>  |   <span data-ttu-id="5d789-118">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5d789-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5d789-119">Applicazione</span><span class="sxs-lookup"><span data-stu-id="5d789-119">Application</span></span> |   <span data-ttu-id="5d789-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="5d789-120">Machine.Read.All</span></span> |  <span data-ttu-id="5d789-121">"Leggi tutti i profili computer"</span><span class="sxs-lookup"><span data-stu-id="5d789-121">'Read all machine profiles'</span></span>
<span data-ttu-id="5d789-122">Applicazione</span><span class="sxs-lookup"><span data-stu-id="5d789-122">Application</span></span> |   <span data-ttu-id="5d789-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5d789-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="5d789-124">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="5d789-124">'Read and write all machine information'</span></span>
<span data-ttu-id="5d789-125">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="5d789-125">Delegated (work or school account)</span></span> | <span data-ttu-id="5d789-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="5d789-126">Machine.Read</span></span> | <span data-ttu-id="5d789-127">"Leggere le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="5d789-127">'Read machine information'</span></span>
<span data-ttu-id="5d789-128">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="5d789-128">Delegated (work or school account)</span></span> | <span data-ttu-id="5d789-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5d789-129">Machine.ReadWrite</span></span> | <span data-ttu-id="5d789-130">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="5d789-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="5d789-131">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="5d789-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5d789-132">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="5d789-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="5d789-133">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="5d789-133">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="5d789-134">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="5d789-134">HTTP request</span></span>
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a><span data-ttu-id="5d789-135">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="5d789-135">Request headers</span></span>

<span data-ttu-id="5d789-136">Name</span><span class="sxs-lookup"><span data-stu-id="5d789-136">Name</span></span> | <span data-ttu-id="5d789-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="5d789-137">Type</span></span> | <span data-ttu-id="5d789-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d789-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="5d789-139">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5d789-139">Authorization</span></span> | <span data-ttu-id="5d789-140">Stringa</span><span class="sxs-lookup"><span data-stu-id="5d789-140">String</span></span> | <span data-ttu-id="5d789-141">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5d789-141">Bearer {token}.</span></span> <span data-ttu-id="5d789-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="5d789-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5d789-143">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="5d789-143">Request body</span></span>
<span data-ttu-id="5d789-144">Vuoto</span><span class="sxs-lookup"><span data-stu-id="5d789-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5d789-145">Risposta</span><span class="sxs-lookup"><span data-stu-id="5d789-145">Response</span></span>
<span data-ttu-id="5d789-146">Se l'operazione ha esito positivo e il dispositivo esiste: 200 OK con [l'entità](machine.md) computer nel corpo.</span><span class="sxs-lookup"><span data-stu-id="5d789-146">If successful and device exists - 200 OK with the [machine](machine.md) entity in the body.</span></span>
<span data-ttu-id="5d789-147">Se il computer con l'ID specificato non è stato trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="5d789-147">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="5d789-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="5d789-148">Example</span></span>

<span data-ttu-id="5d789-149">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="5d789-149">**Request**</span></span>

<span data-ttu-id="5d789-150">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="5d789-150">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

<span data-ttu-id="5d789-151">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="5d789-151">**Response**</span></span>

<span data-ttu-id="5d789-152">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="5d789-152">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2018-08-02T14:55:03.7791856Z",
    "osPlatform": "Windows10",
    "version": "1709",
    "osProcessor": "x64",
    "lastIpAddress": "172.17.230.209",
    "lastExternalIpAddress": "167.220.196.71",
    "osBuild": 18209,
    "healthStatus": "Active",
    "rbacGroupId": 140,
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Medium",
    "isAadJoined": true,
    "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
    "machineTags": [ "test tag 1", "test tag 2" ]
}

```
