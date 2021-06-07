---
title: API Indicatori elenco
description: Scopri come usare l'API List Indicators per recuperare una raccolta di tutti gli indicatori attivi in Microsoft Defender per Endpoint.
keywords: api, api pubbliche, api supportate, insieme Indicators
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
ms.openlocfilehash: d9ec8610957af0bc7741848e7c7bd4fe850f5e32
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770426"
---
# <a name="list-indicators-api"></a><span data-ttu-id="8aa94-104">API Indicatori elenco</span><span class="sxs-lookup"><span data-stu-id="8aa94-104">List Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8aa94-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="8aa94-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="8aa94-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8aa94-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8aa94-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8aa94-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8aa94-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="8aa94-108">API description</span></span>
<span data-ttu-id="8aa94-109">Recupera un insieme di tutti gli indicatori [attivi.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="8aa94-109">Retrieves a collection of all active [Indicators](ti-indicator.md).</span></span>
<br><span data-ttu-id="8aa94-110">Supporta le [query OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="8aa94-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="8aa94-111">La query di OData ```$filter``` è supportata nelle proprietà , , , e ```indicatorValue``` ```indicatorType``` ```creationTimeDateTimeUtc``` ```createdBy``` ```action``` ```severity``` .</span><span class="sxs-lookup"><span data-stu-id="8aa94-111">The OData's ```$filter``` query is supported on: ```indicatorValue```, ```indicatorType```, ```creationTimeDateTimeUtc```, ```createdBy```, ```action``` and ```severity``` properties.</span></span>
<br><span data-ttu-id="8aa94-112">Vedi esempi in [Query OData con Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="8aa94-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="8aa94-113">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="8aa94-113">Limitations</span></span>
1. <span data-ttu-id="8aa94-114">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="8aa94-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="8aa94-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8aa94-115">Permissions</span></span>
<span data-ttu-id="8aa94-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8aa94-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8aa94-117">Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8aa94-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="8aa94-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8aa94-118">Permission type</span></span> |   <span data-ttu-id="8aa94-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8aa94-119">Permission</span></span>  |   <span data-ttu-id="8aa94-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8aa94-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8aa94-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="8aa94-121">Application</span></span> |   <span data-ttu-id="8aa94-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8aa94-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="8aa94-123">"Indicatori di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="8aa94-123">'Read and write Indicators'</span></span>
<span data-ttu-id="8aa94-124">Applicazione</span><span class="sxs-lookup"><span data-stu-id="8aa94-124">Application</span></span> |   <span data-ttu-id="8aa94-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8aa94-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="8aa94-126">"Lettura e scrittura di tutti gli indicatori"</span><span class="sxs-lookup"><span data-stu-id="8aa94-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="8aa94-127">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="8aa94-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="8aa94-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8aa94-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="8aa94-129">"Indicatori di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="8aa94-129">'Read and write Indicators'</span></span>

## <a name="http-request"></a><span data-ttu-id="8aa94-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="8aa94-130">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/indicators
```

## <a name="request-headers"></a><span data-ttu-id="8aa94-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="8aa94-131">Request headers</span></span>

<span data-ttu-id="8aa94-132">Name</span><span class="sxs-lookup"><span data-stu-id="8aa94-132">Name</span></span> | <span data-ttu-id="8aa94-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="8aa94-133">Type</span></span> | <span data-ttu-id="8aa94-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8aa94-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="8aa94-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8aa94-135">Authorization</span></span> | <span data-ttu-id="8aa94-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="8aa94-136">String</span></span> | <span data-ttu-id="8aa94-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8aa94-137">Bearer {token}.</span></span> <span data-ttu-id="8aa94-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="8aa94-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8aa94-139">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="8aa94-139">Request body</span></span>
<span data-ttu-id="8aa94-140">Vuoto</span><span class="sxs-lookup"><span data-stu-id="8aa94-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8aa94-141">Risposta</span><span class="sxs-lookup"><span data-stu-id="8aa94-141">Response</span></span>
<span data-ttu-id="8aa94-142">Se ha esito positivo, questo metodo restituisce 200 codice di risposta Ok con una raccolta di [entità Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="8aa94-142">If successful, this method returns 200, Ok response code with a collection of [Indicator](ti-indicator.md) entities.</span></span>

>[!Note]
> <span data-ttu-id="8aa94-143">Se l'applicazione dispone dell'autorizzazione 'Ti.ReadWrite.All', verrà esposta a tutti gli indicatori.</span><span class="sxs-lookup"><span data-stu-id="8aa94-143">If the Application has 'Ti.ReadWrite.All' permission, it will be exposed to all Indicators.</span></span> <span data-ttu-id="8aa94-144">In caso contrario, verrà esposto solo agli indicatori creati.</span><span class="sxs-lookup"><span data-stu-id="8aa94-144">Otherwise, it will be exposed only to the Indicators it created.</span></span>

## <a name="example-1"></a><span data-ttu-id="8aa94-145">Esempio 1:</span><span class="sxs-lookup"><span data-stu-id="8aa94-145">Example 1:</span></span>

<span data-ttu-id="8aa94-146">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="8aa94-146">**Request**</span></span>

<span data-ttu-id="8aa94-147">Ecco un esempio di richiesta che ottiene tutti gli indicatori</span><span class="sxs-lookup"><span data-stu-id="8aa94-147">Here is an example of a request that gets all Indicators</span></span>

```
GET https://api.securitycenter.microsoft.com/api/indicators
```

<span data-ttu-id="8aa94-148">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="8aa94-148">**Response**</span></span>

<span data-ttu-id="8aa94-149">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="8aa94-149">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "995",
            "indicatorValue": "12.13.14.15",
            "indicatorType": "IpAddress",
            "action": "Alert",
            "application": "demo-test",
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T11:15:35.3688259Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "test",
            "rbacGroupNames": []
        },
        {
            "id": "996",
            "indicatorValue": "220e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="8aa94-150">Esempio 2:</span><span class="sxs-lookup"><span data-stu-id="8aa94-150">Example 2:</span></span>

<span data-ttu-id="8aa94-151">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="8aa94-151">**Request**</span></span>

<span data-ttu-id="8aa94-152">Ecco un esempio di richiesta che ottiene tutti gli indicatori con azione 'AlertAndBlock'</span><span class="sxs-lookup"><span data-stu-id="8aa94-152">Here is an example of a request that gets all Indicators with 'AlertAndBlock' action</span></span> 

```
GET https://api.securitycenter.microsoft.com/api/indicators?$filter=action+eq+'AlertAndBlock'
```

<span data-ttu-id="8aa94-153">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="8aa94-153">**Response**</span></span>

<span data-ttu-id="8aa94-154">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="8aa94-154">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Indicators",
    "value": [
        {
            "id": "997",
            "indicatorValue": "111e7d15b0b3d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "action": "AlertAndBlock",
            "application": null,
            "source": "TestPrdApp",
            "sourceType": "AadApp",
            "title": "test",
            "creationTimeDateTimeUtc": "2018-10-24T10:54:23.2009016Z",
            "createdBy": "45097602-1234-5678-1234-9f453233e62c",
            "expirationTime": "2020-12-12T00:00:00Z",
            "lastUpdateTime": "2019-10-24T10:54:23.2009016Z",
            "lastUpdatedBy": TestPrdApp,
            "severity": "Informational",
            "description": "test",
            "recommendedActions": "TEST",
            "rbacGroupNames": [ "Group1", "Group2" ]
        }
        ...
    ]
}
```
