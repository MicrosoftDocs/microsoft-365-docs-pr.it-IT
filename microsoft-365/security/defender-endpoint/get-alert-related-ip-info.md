---
title: Ottenere informazioni sugli IP correlati agli avvisi
description: Recupera tutti gli IP correlati a un avviso specifico usando Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, ottenere informazioni sugli avvisi, informazioni sugli avvisi, ip correlati
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b6ac9746ff82f81772505daac7d7f36249687d7d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772330"
---
# <a name="get-alert-related-ips-information-api"></a><span data-ttu-id="3000a-104">API per ottenere informazioni sugli IP correlati agli avvisi</span><span class="sxs-lookup"><span data-stu-id="3000a-104">Get alert related IPs information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3000a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3000a-105">**Applies to:**</span></span>
- [<span data-ttu-id="3000a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="3000a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3000a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3000a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3000a-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="3000a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3000a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="3000a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3000a-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="3000a-110">API description</span></span>
<span data-ttu-id="3000a-111">Recupera tutti gli IP correlati a un avviso specifico.</span><span class="sxs-lookup"><span data-stu-id="3000a-111">Retrieves all IPs related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="3000a-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="3000a-112">Limitations</span></span>
1. <span data-ttu-id="3000a-113">È possibile eseguire query sugli avvisi aggiornati per l'ultimo aggiornamento in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="3000a-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="3000a-114">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="3000a-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3000a-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3000a-115">Permissions</span></span>
<span data-ttu-id="3000a-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3000a-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3000a-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3000a-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3000a-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3000a-118">Permission type</span></span> |   <span data-ttu-id="3000a-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3000a-119">Permission</span></span>  |   <span data-ttu-id="3000a-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3000a-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3000a-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="3000a-121">Application</span></span> |   <span data-ttu-id="3000a-122">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="3000a-122">Ip.Read.All</span></span> |   <span data-ttu-id="3000a-123">"Lettura dei profili degli indirizzi IP"</span><span class="sxs-lookup"><span data-stu-id="3000a-123">'Read IP address profiles'</span></span>
<span data-ttu-id="3000a-124">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="3000a-124">Delegated (work or school account)</span></span> | <span data-ttu-id="3000a-125">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="3000a-125">Ip.Read.All</span></span> |  <span data-ttu-id="3000a-126">"Lettura dei profili degli indirizzi IP"</span><span class="sxs-lookup"><span data-stu-id="3000a-126">'Read IP address profiles'</span></span>

>[!Note]
> <span data-ttu-id="3000a-127">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="3000a-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3000a-128">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="3000a-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="3000a-129">L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="3000a-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="3000a-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="3000a-130">HTTP request</span></span>
```
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a><span data-ttu-id="3000a-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="3000a-131">Request headers</span></span>

<span data-ttu-id="3000a-132">Name</span><span class="sxs-lookup"><span data-stu-id="3000a-132">Name</span></span> | <span data-ttu-id="3000a-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="3000a-133">Type</span></span> | <span data-ttu-id="3000a-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3000a-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="3000a-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3000a-135">Authorization</span></span> | <span data-ttu-id="3000a-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="3000a-136">String</span></span> | <span data-ttu-id="3000a-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="3000a-137">Bearer {token}.</span></span> <span data-ttu-id="3000a-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="3000a-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3000a-139">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="3000a-139">Request body</span></span>
<span data-ttu-id="3000a-140">Vuoto</span><span class="sxs-lookup"><span data-stu-id="3000a-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3000a-141">Risposta</span><span class="sxs-lookup"><span data-stu-id="3000a-141">Response</span></span>
<span data-ttu-id="3000a-142">Se l'operazione ha esito positivo e l'avviso e un indirizzo IP esistono: 200 OK.</span><span class="sxs-lookup"><span data-stu-id="3000a-142">If successful and alert and an IP exist - 200 OK.</span></span> <span data-ttu-id="3000a-143">Se l'avviso non viene trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="3000a-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3000a-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="3000a-144">Example</span></span>

<span data-ttu-id="3000a-145">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="3000a-145">**Request**</span></span>

<span data-ttu-id="3000a-146">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="3000a-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

<span data-ttu-id="3000a-147">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="3000a-147">**Response**</span></span>

<span data-ttu-id="3000a-148">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="3000a-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Ips",    
    "value": [
                {
                    "id": "104.80.104.128"
                },
                {
                    "id": "23.203.232.228   
                }
                ...
    ]
}
 
```
