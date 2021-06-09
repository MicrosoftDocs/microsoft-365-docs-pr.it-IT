---
title: List Investigations API
description: Usa questa API per creare chiamate correlate al get investigations collection
keywords: api, api del grafico, api supportate, raccolta Investigations
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
ms.openlocfilehash: 38485a5028626153c26cd1e11537ef7a2daf5296
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770146"
---
# <a name="list-investigations-api"></a><span data-ttu-id="94ea7-104">List Investigations API</span><span class="sxs-lookup"><span data-stu-id="94ea7-104">List Investigations API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="94ea7-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="94ea7-105">**Applies to:**</span></span>
- [<span data-ttu-id="94ea7-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="94ea7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="94ea7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94ea7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="94ea7-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="94ea7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="94ea7-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="94ea7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="94ea7-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="94ea7-110">API description</span></span>
<span data-ttu-id="94ea7-111">Recupera un insieme [di oggetti Investigations.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="94ea7-111">Retrieves a collection of [Investigations](investigation.md).</span></span>
<br><span data-ttu-id="94ea7-112">Supporta le [query OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="94ea7-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="94ea7-113">La query di OData ```$filter``` è supportata su: ```startTime``` , e sulle ```state``` ```machineId``` ```triggeringAlertId``` proprietà.</span><span class="sxs-lookup"><span data-stu-id="94ea7-113">The OData's ```$filter``` query is supported on: ```startTime```, ```state```, ```machineId``` and ```triggeringAlertId``` properties.</span></span>
<br><span data-ttu-id="94ea7-114">Vedi esempi in [Query OData con Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="94ea7-114">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="94ea7-115">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="94ea7-115">Limitations</span></span>
1. <span data-ttu-id="94ea7-116">Le dimensioni massime della pagina sono 10.000.</span><span class="sxs-lookup"><span data-stu-id="94ea7-116">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="94ea7-117">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="94ea7-117">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="94ea7-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="94ea7-118">Permissions</span></span>
<span data-ttu-id="94ea7-119">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="94ea7-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="94ea7-120">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="94ea7-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="94ea7-121">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="94ea7-121">Permission type</span></span> |   <span data-ttu-id="94ea7-122">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="94ea7-122">Permission</span></span>  |   <span data-ttu-id="94ea7-123">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="94ea7-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="94ea7-124">Applicazione</span><span class="sxs-lookup"><span data-stu-id="94ea7-124">Application</span></span> |   <span data-ttu-id="94ea7-125">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="94ea7-125">Alert.Read.All</span></span> |    <span data-ttu-id="94ea7-126">"Leggi tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="94ea7-126">'Read all alerts'</span></span>
<span data-ttu-id="94ea7-127">Applicazione</span><span class="sxs-lookup"><span data-stu-id="94ea7-127">Application</span></span> |   <span data-ttu-id="94ea7-128">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="94ea7-128">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="94ea7-129">"Lettura e scrittura di tutti gli avvisi"</span><span class="sxs-lookup"><span data-stu-id="94ea7-129">'Read and write all alerts'</span></span>
<span data-ttu-id="94ea7-130">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="94ea7-130">Delegated (work or school account)</span></span> | <span data-ttu-id="94ea7-131">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="94ea7-131">Alert.Read</span></span> | <span data-ttu-id="94ea7-132">"Avvisi di lettura"</span><span class="sxs-lookup"><span data-stu-id="94ea7-132">'Read alerts'</span></span>
<span data-ttu-id="94ea7-133">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="94ea7-133">Delegated (work or school account)</span></span> | <span data-ttu-id="94ea7-134">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="94ea7-134">Alert.ReadWrite</span></span> | <span data-ttu-id="94ea7-135">"Avvisi di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="94ea7-135">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="94ea7-136">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="94ea7-136">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="94ea7-137">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="94ea7-137">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="94ea7-138">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="94ea7-138">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations
```

## <a name="request-headers"></a><span data-ttu-id="94ea7-139">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="94ea7-139">Request headers</span></span>

<span data-ttu-id="94ea7-140">Name</span><span class="sxs-lookup"><span data-stu-id="94ea7-140">Name</span></span> | <span data-ttu-id="94ea7-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="94ea7-141">Type</span></span> | <span data-ttu-id="94ea7-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="94ea7-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="94ea7-143">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="94ea7-143">Authorization</span></span> | <span data-ttu-id="94ea7-144">Stringa</span><span class="sxs-lookup"><span data-stu-id="94ea7-144">String</span></span> | <span data-ttu-id="94ea7-145">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="94ea7-145">Bearer {token}.</span></span> <span data-ttu-id="94ea7-146">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="94ea7-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="94ea7-147">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="94ea7-147">Request body</span></span>
<span data-ttu-id="94ea7-148">Vuoto</span><span class="sxs-lookup"><span data-stu-id="94ea7-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="94ea7-149">Risposta</span><span class="sxs-lookup"><span data-stu-id="94ea7-149">Response</span></span>
<span data-ttu-id="94ea7-150">Se ha esito positivo, questo metodo restituisce 200 codice di risposta Ok con una raccolta [di entità Investigations.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="94ea7-150">If successful, this method returns 200, Ok response code with a collection of [Investigations](investigation.md) entities.</span></span>


## <a name="example"></a><span data-ttu-id="94ea7-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="94ea7-151">Example</span></span>

<span data-ttu-id="94ea7-152">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="94ea7-152">**Request**</span></span>

<span data-ttu-id="94ea7-153">Ecco un esempio di richiesta di ottenere tutte le indagini:</span><span class="sxs-lookup"><span data-stu-id="94ea7-153">Here is an example of a request to get all investigations:</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/investigations
```

<span data-ttu-id="94ea7-154">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="94ea7-154">**Response**</span></span>

<span data-ttu-id="94ea7-155">Ecco un esempio di risposta:</span><span class="sxs-lookup"><span data-stu-id="94ea7-155">Here is an example of the response:</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Investigations",
    "value": [
        {
            "id": "63017",
            "startTime": "2020-01-06T14:11:34Z",
            "endTime": null,
            "state": "Running",
            "cancelledBy": null,
            "statusDetails": null,
            "machineId": "a69a22debe5f274d8765ea3c368d00762e057b30",
            "computerDnsName": "desktop-gtrcon0",
            "triggeringAlertId": "da637139166940871892_-598649278"
        }
        ...
    ]
}
```
