---
title: API per ottenere le statistiche del dominio
description: Scopri come usare l'API Get domain statistics per recuperare le statistiche sul dominio specificato in Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, get, dominio, dispositivi correlati al dominio
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
ms.openlocfilehash: d2edc5d429d124412134b466753b65506d2dd7a9
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772186"
---
# <a name="get-domain-statistics-api"></a><span data-ttu-id="19723-104">API per ottenere le statistiche del dominio</span><span class="sxs-lookup"><span data-stu-id="19723-104">Get domain statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19723-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="19723-105">**Applies to:**</span></span>
- [<span data-ttu-id="19723-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="19723-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="19723-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19723-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="19723-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="19723-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="19723-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="19723-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="19723-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="19723-110">API description</span></span>
<span data-ttu-id="19723-111">Recupera le statistiche sul dominio specificato.</span><span class="sxs-lookup"><span data-stu-id="19723-111">Retrieves the statistics on the given domain.</span></span>


## <a name="limitations"></a><span data-ttu-id="19723-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="19723-112">Limitations</span></span>
1. <span data-ttu-id="19723-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="19723-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="19723-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="19723-114">Permissions</span></span>
<span data-ttu-id="19723-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="19723-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="19723-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="19723-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="19723-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="19723-117">Permission type</span></span> |   <span data-ttu-id="19723-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="19723-118">Permission</span></span>  |   <span data-ttu-id="19723-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="19723-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="19723-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="19723-120">Application</span></span> |   <span data-ttu-id="19723-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="19723-121">URL.Read.All</span></span> |  <span data-ttu-id="19723-122">"Leggi URL"</span><span class="sxs-lookup"><span data-stu-id="19723-122">'Read URLs'</span></span>
<span data-ttu-id="19723-123">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="19723-123">Delegated (work or school account)</span></span> | <span data-ttu-id="19723-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="19723-124">URL.Read.All</span></span> | <span data-ttu-id="19723-125">"Leggi URL"</span><span class="sxs-lookup"><span data-stu-id="19723-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="19723-126">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="19723-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="19723-127">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="19723-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="19723-128">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="19723-128">HTTP request</span></span>
```
GET /api/domains/{domain}/stats
```

## <a name="request-headers"></a><span data-ttu-id="19723-129">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="19723-129">Request headers</span></span>

<span data-ttu-id="19723-130">Intestazione</span><span class="sxs-lookup"><span data-stu-id="19723-130">Header</span></span> | <span data-ttu-id="19723-131">Valore</span><span class="sxs-lookup"><span data-stu-id="19723-131">Value</span></span> 
:---|:---
<span data-ttu-id="19723-132">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="19723-132">Authorization</span></span> | <span data-ttu-id="19723-133">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="19723-133">Bearer {token}.</span></span> <span data-ttu-id="19723-134">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="19723-134">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="19723-135">Parametri URI di richiesta</span><span class="sxs-lookup"><span data-stu-id="19723-135">Request URI parameters</span></span>

<span data-ttu-id="19723-136">Nome</span><span class="sxs-lookup"><span data-stu-id="19723-136">Name</span></span> | <span data-ttu-id="19723-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="19723-137">Type</span></span> | <span data-ttu-id="19723-138">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19723-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="19723-139">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="19723-139">lookBackHours</span></span> | <span data-ttu-id="19723-140">Int32</span><span class="sxs-lookup"><span data-stu-id="19723-140">Int32</span></span> | <span data-ttu-id="19723-141">Definisce le ore di ricerca per ottenere le statistiche.</span><span class="sxs-lookup"><span data-stu-id="19723-141">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="19723-142">Il valore predefinito è 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="19723-142">Defaults to 30 days.</span></span> <span data-ttu-id="19723-143">**Facoltativo**.</span><span class="sxs-lookup"><span data-stu-id="19723-143">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="19723-144">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="19723-144">Request body</span></span>
<span data-ttu-id="19723-145">Vuoto</span><span class="sxs-lookup"><span data-stu-id="19723-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="19723-146">Risposta</span><span class="sxs-lookup"><span data-stu-id="19723-146">Response</span></span>
<span data-ttu-id="19723-147">Se ha esito positivo e il dominio esiste - 200 OK, con l'oggetto statistiche nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="19723-147">If successful and domain exists - 200 OK, with statistics object in the response body.</span></span> <span data-ttu-id="19723-148">Se il dominio non esiste - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="19723-148">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="19723-149">Esempio</span><span class="sxs-lookup"><span data-stu-id="19723-149">Example</span></span>

<span data-ttu-id="19723-150">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="19723-150">**Request**</span></span>

<span data-ttu-id="19723-151">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="19723-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/example.com/stats?lookBackHours=48
```

<span data-ttu-id="19723-152">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="19723-152">**Response**</span></span>

<span data-ttu-id="19723-153">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="19723-153">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgDomainStats",
    "host": "example.com",
    "orgPrevalence": "4070",
    "orgFirstSeen": "2017-07-30T13:23:48Z",
    "orgLastSeen": "2017-08-29T13:09:05Z"
}
```
