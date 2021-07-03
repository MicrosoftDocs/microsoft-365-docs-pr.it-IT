---
title: List machines API
description: Scopri come usare l'API List machines per recuperare una raccolta di computer che hanno comunicato con Microsoft Defender for Endpoint cloud.
keywords: api, api del grafico, api supportate, get, dispositivi
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
ms.topic: article
ms.collection: M365-security-compliance
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d52e1b69311c26144684b90545e17934d1223332
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287856"
---
# <a name="list-machines-api"></a><span data-ttu-id="74349-104">List machines API</span><span class="sxs-lookup"><span data-stu-id="74349-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="74349-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="74349-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="74349-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="74349-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="74349-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="74349-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="74349-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="74349-108">API description</span></span>
<span data-ttu-id="74349-109">Recupera una raccolta di [computer](machine.md) che hanno comunicato con Microsoft Defender for Endpoint cloud.</span><span class="sxs-lookup"><span data-stu-id="74349-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="74349-110">Supporta le [query OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="74349-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="74349-111">La query di OData `$filter` è supportata in: `computerDnsName` , , , e `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .</span><span class="sxs-lookup"><span data-stu-id="74349-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="74349-112">Vedi esempi in [Query OData con Defender for Endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="74349-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="74349-113">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="74349-113">Limitations</span></span>
1. <span data-ttu-id="74349-114">È possibile visualizzare i dispositivi per l'ultima volta in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="74349-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="74349-115">Le dimensioni massime della pagina sono 10.000.</span><span class="sxs-lookup"><span data-stu-id="74349-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="74349-116">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="74349-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="74349-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="74349-117">Permissions</span></span>

<span data-ttu-id="74349-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="74349-118">Permission type</span></span> |   <span data-ttu-id="74349-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="74349-119">Permission</span></span>  |   <span data-ttu-id="74349-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="74349-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="74349-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="74349-121">Application</span></span> |   <span data-ttu-id="74349-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="74349-122">Machine.Read.All</span></span> |  <span data-ttu-id="74349-123">"Leggi tutti i profili computer"</span><span class="sxs-lookup"><span data-stu-id="74349-123">'Read all machine profiles'</span></span>
<span data-ttu-id="74349-124">Applicazione</span><span class="sxs-lookup"><span data-stu-id="74349-124">Application</span></span> |   <span data-ttu-id="74349-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="74349-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="74349-126">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="74349-126">'Read and write all machine information'</span></span>
<span data-ttu-id="74349-127">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="74349-127">Delegated (work or school account)</span></span> | <span data-ttu-id="74349-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="74349-128">Machine.Read</span></span> | <span data-ttu-id="74349-129">"Leggere le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="74349-129">'Read machine information'</span></span>
<span data-ttu-id="74349-130">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="74349-130">Delegated (work or school account)</span></span> | <span data-ttu-id="74349-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="74349-131">Machine.ReadWrite</span></span> | <span data-ttu-id="74349-132">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="74349-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="74349-133">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="74349-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="74349-134">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="74349-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="74349-135">La risposta includerà solo i dispositivi a cui l'utente ha accesso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="74349-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="74349-136">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="74349-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="74349-137">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="74349-137">Request headers</span></span>

<span data-ttu-id="74349-138">Nome</span><span class="sxs-lookup"><span data-stu-id="74349-138">Name</span></span> | <span data-ttu-id="74349-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="74349-139">Type</span></span> | <span data-ttu-id="74349-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74349-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="74349-141">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="74349-141">Authorization</span></span> | <span data-ttu-id="74349-142">Stringa</span><span class="sxs-lookup"><span data-stu-id="74349-142">String</span></span> | <span data-ttu-id="74349-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="74349-143">Bearer {token}.</span></span> <span data-ttu-id="74349-144">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="74349-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="74349-145">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="74349-145">Request body</span></span>
<span data-ttu-id="74349-146">Vuoto</span><span class="sxs-lookup"><span data-stu-id="74349-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="74349-147">Risposta</span><span class="sxs-lookup"><span data-stu-id="74349-147">Response</span></span>
<span data-ttu-id="74349-148">Se ha esito positivo e i computer [](machine.md) esistono: 200 OK con l'elenco delle entità del computer nel corpo.</span><span class="sxs-lookup"><span data-stu-id="74349-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="74349-149">Se nessun computer recente - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="74349-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="74349-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="74349-150">Example</span></span>

<span data-ttu-id="74349-151">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="74349-151">**Request**</span></span>

<span data-ttu-id="74349-152">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="74349-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="74349-153">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="74349-153">**Response**</span></span>

<span data-ttu-id="74349-154">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="74349-154">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
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
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="74349-155">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="74349-155">Related topics</span></span>
- [<span data-ttu-id="74349-156">Query OData con Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="74349-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
