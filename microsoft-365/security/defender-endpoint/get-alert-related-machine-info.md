---
title: Ottenere informazioni sul computer correlate agli avvisi
description: Recupera tutti i dispositivi correlati a un avviso specifico usando Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, ottenere informazioni sugli avvisi, informazioni sugli avvisi, dispositivo correlato
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
ms.openlocfilehash: 70ce6adce3e14be7ee440b96587b8f9402c0b99f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166985"
---
# <a name="get-alert-related-machine-information-api"></a><span data-ttu-id="aeb70-104">API per ottenere informazioni sul computer correlate agli avvisi</span><span class="sxs-lookup"><span data-stu-id="aeb70-104">Get alert related machine information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aeb70-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="aeb70-105">**Applies to:**</span></span>
- [<span data-ttu-id="aeb70-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="aeb70-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aeb70-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aeb70-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="aeb70-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="aeb70-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aeb70-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="aeb70-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="aeb70-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="aeb70-110">API description</span></span>
<span data-ttu-id="aeb70-111">Recupera [l'oggetto Device](machine.md) correlato a un avviso specifico.</span><span class="sxs-lookup"><span data-stu-id="aeb70-111">Retrieves [Device](machine.md) related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="aeb70-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="aeb70-112">Limitations</span></span>
1. <span data-ttu-id="aeb70-113">È possibile eseguire query sugli avvisi aggiornati per l'ultimo aggiornamento in base al periodo di conservazione configurato.</span><span class="sxs-lookup"><span data-stu-id="aeb70-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="aeb70-114">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="aeb70-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="aeb70-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="aeb70-115">Permissions</span></span>
<span data-ttu-id="aeb70-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="aeb70-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="aeb70-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="aeb70-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="aeb70-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aeb70-118">Permission type</span></span> |   <span data-ttu-id="aeb70-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aeb70-119">Permission</span></span>  |   <span data-ttu-id="aeb70-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aeb70-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="aeb70-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="aeb70-121">Application</span></span> |   <span data-ttu-id="aeb70-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="aeb70-122">Machine.Read.All</span></span> |  <span data-ttu-id="aeb70-123">"Leggi tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="aeb70-123">'Read all machine information'</span></span>
<span data-ttu-id="aeb70-124">Applicazione</span><span class="sxs-lookup"><span data-stu-id="aeb70-124">Application</span></span> |   <span data-ttu-id="aeb70-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="aeb70-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="aeb70-126">"Leggere e scrivere tutte le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="aeb70-126">'Read and write all machine information'</span></span>
<span data-ttu-id="aeb70-127">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="aeb70-127">Delegated (work or school account)</span></span> | <span data-ttu-id="aeb70-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="aeb70-128">Machine.Read</span></span> | <span data-ttu-id="aeb70-129">"Leggere le informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="aeb70-129">'Read machine information'</span></span>
<span data-ttu-id="aeb70-130">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="aeb70-130">Delegated (work or school account)</span></span> | <span data-ttu-id="aeb70-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="aeb70-131">Machine.ReadWrite</span></span> | <span data-ttu-id="aeb70-132">"Leggere e scrivere informazioni sul computer"</span><span class="sxs-lookup"><span data-stu-id="aeb70-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="aeb70-133">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="aeb70-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="aeb70-134">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="aeb70-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="aeb70-135">L'utente deve avere accesso al dispositivo associato all'avviso, in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="aeb70-135">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="aeb70-136">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="aeb70-136">HTTP request</span></span>

```http
GET /api/alerts/{id}/machine
```

## <a name="request-headers"></a><span data-ttu-id="aeb70-137">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="aeb70-137">Request headers</span></span>

<span data-ttu-id="aeb70-138">Name</span><span class="sxs-lookup"><span data-stu-id="aeb70-138">Name</span></span> | <span data-ttu-id="aeb70-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="aeb70-139">Type</span></span> | <span data-ttu-id="aeb70-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aeb70-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="aeb70-141">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="aeb70-141">Authorization</span></span> | <span data-ttu-id="aeb70-142">Stringa</span><span class="sxs-lookup"><span data-stu-id="aeb70-142">String</span></span> | <span data-ttu-id="aeb70-143">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="aeb70-143">Bearer {token}.</span></span> <span data-ttu-id="aeb70-144">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="aeb70-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="aeb70-145">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="aeb70-145">Request body</span></span>
<span data-ttu-id="aeb70-146">Vuoto</span><span class="sxs-lookup"><span data-stu-id="aeb70-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="aeb70-147">Risposta</span><span class="sxs-lookup"><span data-stu-id="aeb70-147">Response</span></span>
<span data-ttu-id="aeb70-148">Se l'operazione ha esito positivo e l'avviso e il dispositivo esistono: 200 OK.</span><span class="sxs-lookup"><span data-stu-id="aeb70-148">If successful and alert and device exist - 200 OK.</span></span> <span data-ttu-id="aeb70-149">Se l'avviso non viene trovato o il dispositivo non viene trovato - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="aeb70-149">If alert not found or device not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="aeb70-150">Esempio</span><span class="sxs-lookup"><span data-stu-id="aeb70-150">Example</span></span>

<span data-ttu-id="aeb70-151">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="aeb70-151">**Request**</span></span>

<span data-ttu-id="aeb70-152">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="aeb70-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/machine
```

<span data-ttu-id="aeb70-153">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="aeb70-153">**Response**</span></span>

<span data-ttu-id="aeb70-154">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="aeb70-154">Here is an example of the response.</span></span>


```json
{
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2021-01-25T07:27:36.052313Z",
    "osPlatform": "Windows10",
    "osProcessor": "x64",
    "version": "1901",
    "lastIpAddress": "10.166.113.46",
    "lastExternalIpAddress": "167.220.203.175",
    "osBuild": 19042,
    "healthStatus": "Active",
    "deviceValue": "Normal",
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Low",
    "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
    "machineTags": [
        "Tag1",
        "Tag2"
    ],
    "ipAddresses": [
        {
            "ipAddress": "10.166.113.47",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        },
        {
            "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        }
    ]
}
```