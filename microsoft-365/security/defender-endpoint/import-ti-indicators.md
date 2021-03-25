---
title: API Indicatori di importazione
description: Scopri come usare il batch di importazione dell'API indicatore in Microsoft Defender per Endpoint.
keywords: api, api supportate, invio, ti, indicatore, aggiornamento
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
ms.openlocfilehash: b1777adf7b97083fae2daf4213a4bda742ba097d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198246"
---
# <a name="import-indicators-api"></a><span data-ttu-id="5f0e4-104">API Indicatori di importazione</span><span class="sxs-lookup"><span data-stu-id="5f0e4-104">Import Indicators API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5f0e4-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5f0e4-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5f0e4-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5f0e4-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5f0e4-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5f0e4-108">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="5f0e4-108">API description</span></span>
<span data-ttu-id="5f0e4-109">Invia o aggiorna il batch [di entità](ti-indicator.md) Indicatore.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-109">Submits or Updates batch of [Indicator](ti-indicator.md) entities.</span></span>
<br><span data-ttu-id="5f0e4-110">La notazione CIDR per gli IP non è supportata.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-110">CIDR notation for IPs is not supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="5f0e4-111">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="5f0e4-111">Limitations</span></span>
1. <span data-ttu-id="5f0e4-112">I limiti di frequenza per questa API sono di 30 chiamate al minuto.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-112">Rate limitations for this API are 30 calls per minute.</span></span>
2. <span data-ttu-id="5f0e4-113">Esiste un limite di 15.000 [indicatori](ti-indicator.md) attivi per tenant.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-113">There is a limit of 15,000 active [Indicators](ti-indicator.md) per tenant.</span></span> 
3. <span data-ttu-id="5f0e4-114">La dimensione massima del batch per una chiamata API è 500.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-114">Maximum batch size for one API call is 500.</span></span>

## <a name="permissions"></a><span data-ttu-id="5f0e4-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5f0e4-115">Permissions</span></span>
<span data-ttu-id="5f0e4-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5f0e4-117">Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Introduzione](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5f0e4-117">To learn more, including how to choose permissions, see [Get started](apis-intro.md)</span></span>

<span data-ttu-id="5f0e4-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5f0e4-118">Permission type</span></span> |   <span data-ttu-id="5f0e4-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5f0e4-119">Permission</span></span>  |   <span data-ttu-id="5f0e4-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5f0e4-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5f0e4-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="5f0e4-121">Application</span></span> |   <span data-ttu-id="5f0e4-122">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5f0e4-122">Ti.ReadWrite</span></span> |  <span data-ttu-id="5f0e4-123">"Indicatori di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="5f0e4-123">'Read and write Indicators'</span></span>
<span data-ttu-id="5f0e4-124">Applicazione</span><span class="sxs-lookup"><span data-stu-id="5f0e4-124">Application</span></span> |   <span data-ttu-id="5f0e4-125">Ti.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5f0e4-125">Ti.ReadWrite.All</span></span> |  <span data-ttu-id="5f0e4-126">"Lettura e scrittura di tutti gli indicatori"</span><span class="sxs-lookup"><span data-stu-id="5f0e4-126">'Read and write All Indicators'</span></span>
<span data-ttu-id="5f0e4-127">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="5f0e4-127">Delegated (work or school account)</span></span> |    <span data-ttu-id="5f0e4-128">Ti.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5f0e4-128">Ti.ReadWrite</span></span> |  <span data-ttu-id="5f0e4-129">"Indicatori di lettura e scrittura"</span><span class="sxs-lookup"><span data-stu-id="5f0e4-129">'Read and write Indicators'</span></span>


## <a name="http-request"></a><span data-ttu-id="5f0e4-130">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="5f0e4-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

## <a name="request-headers"></a><span data-ttu-id="5f0e4-131">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="5f0e4-131">Request headers</span></span>

<span data-ttu-id="5f0e4-132">Name</span><span class="sxs-lookup"><span data-stu-id="5f0e4-132">Name</span></span> | <span data-ttu-id="5f0e4-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="5f0e4-133">Type</span></span> | <span data-ttu-id="5f0e4-134">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f0e4-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="5f0e4-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="5f0e4-135">Authorization</span></span> | <span data-ttu-id="5f0e4-136">Stringa</span><span class="sxs-lookup"><span data-stu-id="5f0e4-136">String</span></span> | <span data-ttu-id="5f0e4-137">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-137">Bearer {token}.</span></span> <span data-ttu-id="5f0e4-138">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-138">**Required**.</span></span>
<span data-ttu-id="5f0e4-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="5f0e4-139">Content-Type</span></span> | <span data-ttu-id="5f0e4-140">stringa</span><span class="sxs-lookup"><span data-stu-id="5f0e4-140">string</span></span> | <span data-ttu-id="5f0e4-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-141">application/json.</span></span> <span data-ttu-id="5f0e4-142">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5f0e4-143">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="5f0e4-143">Request body</span></span>
<span data-ttu-id="5f0e4-144">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f0e4-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="5f0e4-145">Parametro</span><span class="sxs-lookup"><span data-stu-id="5f0e4-145">Parameter</span></span> | <span data-ttu-id="5f0e4-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="5f0e4-146">Type</span></span>    | <span data-ttu-id="5f0e4-147">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5f0e4-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="5f0e4-148">Indicatori</span><span class="sxs-lookup"><span data-stu-id="5f0e4-148">Indicators</span></span> | <span data-ttu-id="5f0e4-149">Indicatore<[elenco](ti-indicator.md)></span><span class="sxs-lookup"><span data-stu-id="5f0e4-149">List<[Indicator](ti-indicator.md)></span></span> | <span data-ttu-id="5f0e4-150">Elenco di [indicatori](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="5f0e4-150">List of [Indicators](ti-indicator.md).</span></span> <span data-ttu-id="5f0e4-151">**Obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="5f0e4-151">**Required**</span></span>


## <a name="response"></a><span data-ttu-id="5f0e4-152">Risposta</span><span class="sxs-lookup"><span data-stu-id="5f0e4-152">Response</span></span>
- <span data-ttu-id="5f0e4-153">Se ha esito positivo, questo metodo restituisce 200 - OK codice di risposta con un elenco di risultati di importazione per indicatore, vedi l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-153">If successful, this method returns 200 - OK response code with a list of import results per indicator, see example below.</span></span>
- <span data-ttu-id="5f0e4-154">In caso di esito negativo: questo metodo restituisce 400 - Richiesta non valida.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-154">If not successful: this method return 400 - Bad Request.</span></span> <span data-ttu-id="5f0e4-155">La richiesta non valida in genere indica un corpo errato.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-155">Bad request usually indicates incorrect body.</span></span>

## <a name="example"></a><span data-ttu-id="5f0e4-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f0e4-156">Example</span></span>

<span data-ttu-id="5f0e4-157">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="5f0e4-157">**Request**</span></span>

<span data-ttu-id="5f0e4-158">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/indicators/import
```

```json
{
    "Indicators":
    [
        {
            "indicatorValue": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "indicatorType": "FileSha1",
            "title": "demo",
            "application": "demo-test",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Informational",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": ["group1", "group2"]
        },
        {
            "indicatorValue": "2233223322332233223322332233223322332233223322332233223322332222",
            "indicatorType": "FileSha256",
            "title": "demo2",
            "application": "demo-test2",
            "expirationTime": "2021-12-12T00:00:00Z",
            "action": "Alert",
            "severity": "Medium",
            "description": "demo2",
            "recommendedActions": "nothing",
            "rbacGroupNames": []
        }
    ]
}
```

<span data-ttu-id="5f0e4-159">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="5f0e4-159">**Response**</span></span>

<span data-ttu-id="5f0e4-160">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="5f0e4-160">Here is an example of the response.</span></span>

```json
{
    "value": [
        {
            "id": "2841",
            "indicator": "220e7d15b011d7fac48f2bd61114db1022197f7f",
            "isFailed": false,
            "failureReason": null
        },
        {
            "id": "2842",
            "indicator": "2233223322332233223322332233223322332233223322332233223322332222",
            "isFailed": false,
            "failureReason": null
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="5f0e4-161">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="5f0e4-161">Related topic</span></span>
- [<span data-ttu-id="5f0e4-162">Gestire gli indicatori</span><span class="sxs-lookup"><span data-stu-id="5f0e4-162">Manage indicators</span></span>](manage-indicators.md)
