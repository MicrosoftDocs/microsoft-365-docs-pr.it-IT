---
title: API Per ottenere le statistiche dei file
description: Scopri come usare l'API Get file statistics per recuperare le statistiche per il file specificato in Microsoft Defender per Endpoint.
keywords: api, api del grafico, api supportate, ottenere, file, statistiche
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
ms.openlocfilehash: ff43f6c46d89bc92cd1dc2a4fb0f329757b8f69e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167126"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="8f746-104">API Per ottenere le statistiche dei file</span><span class="sxs-lookup"><span data-stu-id="8f746-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8f746-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8f746-105">**Applies to:**</span></span>
- [<span data-ttu-id="8f746-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="8f746-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8f746-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f746-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8f746-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="8f746-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8f746-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="8f746-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8f746-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="8f746-110">API description</span></span>
<span data-ttu-id="8f746-111">Recupera le statistiche per il file specificato.</span><span class="sxs-lookup"><span data-stu-id="8f746-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="8f746-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="8f746-112">Limitations</span></span>
1. <span data-ttu-id="8f746-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="8f746-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="8f746-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8f746-114">Permissions</span></span>
<span data-ttu-id="8f746-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8f746-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8f746-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8f746-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8f746-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8f746-117">Permission type</span></span> |   <span data-ttu-id="8f746-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8f746-118">Permission</span></span>  |   <span data-ttu-id="8f746-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8f746-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8f746-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="8f746-120">Application</span></span> |   <span data-ttu-id="8f746-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="8f746-121">File.Read.All</span></span> | <span data-ttu-id="8f746-122">"Lettura profili file"</span><span class="sxs-lookup"><span data-stu-id="8f746-122">'Read file profiles'</span></span>
<span data-ttu-id="8f746-123">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="8f746-123">Delegated (work or school account)</span></span> | <span data-ttu-id="8f746-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="8f746-124">File.Read.All</span></span> | <span data-ttu-id="8f746-125">"Lettura profili file"</span><span class="sxs-lookup"><span data-stu-id="8f746-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="8f746-126">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="8f746-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8f746-127">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="8f746-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="8f746-128">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="8f746-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="8f746-129">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="8f746-129">Request headers</span></span>

<span data-ttu-id="8f746-130">Name</span><span class="sxs-lookup"><span data-stu-id="8f746-130">Name</span></span> | <span data-ttu-id="8f746-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="8f746-131">Type</span></span> | <span data-ttu-id="8f746-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f746-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="8f746-133">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="8f746-133">Authorization</span></span> | <span data-ttu-id="8f746-134">Stringa</span><span class="sxs-lookup"><span data-stu-id="8f746-134">String</span></span> | <span data-ttu-id="8f746-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="8f746-135">Bearer {token}.</span></span> <span data-ttu-id="8f746-136">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="8f746-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="8f746-137">Parametri URI di richiesta</span><span class="sxs-lookup"><span data-stu-id="8f746-137">Request URI parameters</span></span>

<span data-ttu-id="8f746-138">Nome</span><span class="sxs-lookup"><span data-stu-id="8f746-138">Name</span></span> | <span data-ttu-id="8f746-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="8f746-139">Type</span></span> | <span data-ttu-id="8f746-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8f746-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="8f746-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="8f746-141">lookBackHours</span></span> | <span data-ttu-id="8f746-142">Int32</span><span class="sxs-lookup"><span data-stu-id="8f746-142">Int32</span></span> | <span data-ttu-id="8f746-143">Definisce le ore di ricerca per ottenere le statistiche.</span><span class="sxs-lookup"><span data-stu-id="8f746-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="8f746-144">Il valore predefinito è 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="8f746-144">Defaults to 30 days.</span></span> <span data-ttu-id="8f746-145">**Facoltativo**.</span><span class="sxs-lookup"><span data-stu-id="8f746-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8f746-146">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="8f746-146">Request body</span></span>
<span data-ttu-id="8f746-147">Vuoto</span><span class="sxs-lookup"><span data-stu-id="8f746-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8f746-148">Risposta</span><span class="sxs-lookup"><span data-stu-id="8f746-148">Response</span></span>
<span data-ttu-id="8f746-149">Se ha esito positivo e il file esiste- 200 OK con dati statistici nel corpo.</span><span class="sxs-lookup"><span data-stu-id="8f746-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="8f746-150">Se il file non esiste - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="8f746-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="8f746-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f746-151">Example</span></span>

<span data-ttu-id="8f746-152">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="8f746-152">**Request**</span></span>

<span data-ttu-id="8f746-153">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="8f746-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="8f746-154">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="8f746-154">**Response**</span></span>

<span data-ttu-id="8f746-155">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="8f746-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "orgPrevalence": "14850",
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globalPrevalence": "705012",
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
