---
title: API Per ottenere statistiche IP
description: Ottieni le statistiche più recenti per il tuo IP usando Microsoft Defender for Endpoint.
keywords: api, api del grafico, api supportate, get, ip, statistiche, prevalenza
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
ms.openlocfilehash: c47a5e58b1888447a4428fad78e71b85cfe79b69
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167186"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="ab1df-104">API Per ottenere statistiche IP</span><span class="sxs-lookup"><span data-stu-id="ab1df-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ab1df-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ab1df-105">**Applies to:**</span></span>
- [<span data-ttu-id="ab1df-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ab1df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ab1df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab1df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ab1df-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="ab1df-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ab1df-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="ab1df-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="ab1df-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="ab1df-110">API description</span></span>
<span data-ttu-id="ab1df-111">Recupera le statistiche per l'IP specificato.</span><span class="sxs-lookup"><span data-stu-id="ab1df-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="ab1df-112">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="ab1df-112">Limitations</span></span>
1. <span data-ttu-id="ab1df-113">I limiti di frequenza per questa API sono 100 chiamate al minuto e 1500 chiamate all'ora.</span><span class="sxs-lookup"><span data-stu-id="ab1df-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="ab1df-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ab1df-114">Permissions</span></span>
<span data-ttu-id="ab1df-115">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="ab1df-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ab1df-116">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ab1df-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ab1df-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ab1df-117">Permission type</span></span> |   <span data-ttu-id="ab1df-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ab1df-118">Permission</span></span>  |   <span data-ttu-id="ab1df-119">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ab1df-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ab1df-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="ab1df-120">Application</span></span> |   <span data-ttu-id="ab1df-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="ab1df-121">Ip.Read.All</span></span> |   <span data-ttu-id="ab1df-122">"Lettura dei profili degli indirizzi IP"</span><span class="sxs-lookup"><span data-stu-id="ab1df-122">'Read IP address profiles'</span></span>
<span data-ttu-id="ab1df-123">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="ab1df-123">Delegated (work or school account)</span></span> | <span data-ttu-id="ab1df-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="ab1df-124">Ip.Read.All</span></span> |  <span data-ttu-id="ab1df-125">"Lettura dei profili degli indirizzi IP"</span><span class="sxs-lookup"><span data-stu-id="ab1df-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="ab1df-126">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="ab1df-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ab1df-127">L'utente deve disporre almeno dell'autorizzazione di ruolo seguente: 'Visualizza dati' (per ulteriori informazioni, vedere [Creare](user-roles.md) e gestire ruoli)</span><span class="sxs-lookup"><span data-stu-id="ab1df-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="ab1df-128">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="ab1df-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="ab1df-129">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="ab1df-129">Request headers</span></span>

<span data-ttu-id="ab1df-130">Name</span><span class="sxs-lookup"><span data-stu-id="ab1df-130">Name</span></span> | <span data-ttu-id="ab1df-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab1df-131">Type</span></span> | <span data-ttu-id="ab1df-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab1df-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="ab1df-133">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ab1df-133">Authorization</span></span> | <span data-ttu-id="ab1df-134">Stringa</span><span class="sxs-lookup"><span data-stu-id="ab1df-134">String</span></span> | <span data-ttu-id="ab1df-135">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="ab1df-135">Bearer {token}.</span></span> <span data-ttu-id="ab1df-136">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="ab1df-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="ab1df-137">Parametri URI di richiesta</span><span class="sxs-lookup"><span data-stu-id="ab1df-137">Request URI parameters</span></span>

<span data-ttu-id="ab1df-138">Nome</span><span class="sxs-lookup"><span data-stu-id="ab1df-138">Name</span></span> | <span data-ttu-id="ab1df-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab1df-139">Type</span></span> | <span data-ttu-id="ab1df-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab1df-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="ab1df-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="ab1df-141">lookBackHours</span></span> | <span data-ttu-id="ab1df-142">Int32</span><span class="sxs-lookup"><span data-stu-id="ab1df-142">Int32</span></span> | <span data-ttu-id="ab1df-143">Definisce le ore di ricerca per ottenere le statistiche.</span><span class="sxs-lookup"><span data-stu-id="ab1df-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="ab1df-144">Il valore predefinito è 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="ab1df-144">Defaults to 30 days.</span></span> <span data-ttu-id="ab1df-145">**Facoltativo**.</span><span class="sxs-lookup"><span data-stu-id="ab1df-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ab1df-146">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="ab1df-146">Request body</span></span>
<span data-ttu-id="ab1df-147">Vuoto</span><span class="sxs-lookup"><span data-stu-id="ab1df-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ab1df-148">Risposta</span><span class="sxs-lookup"><span data-stu-id="ab1df-148">Response</span></span>
<span data-ttu-id="ab1df-149">Se ha esito positivo e ip esiste - 200 OK con dati statistici nel corpo.</span><span class="sxs-lookup"><span data-stu-id="ab1df-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="ab1df-150">IP non esistente - 404 Non trovato.</span><span class="sxs-lookup"><span data-stu-id="ab1df-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="ab1df-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab1df-151">Example</span></span>

<span data-ttu-id="ab1df-152">**Richiesta**</span><span class="sxs-lookup"><span data-stu-id="ab1df-152">**Request**</span></span>

<span data-ttu-id="ab1df-153">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="ab1df-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="ab1df-154">**Risposta**</span><span class="sxs-lookup"><span data-stu-id="ab1df-154">**Response**</span></span>

<span data-ttu-id="ab1df-155">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="ab1df-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "orgPrevalence": "63515",
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="ab1df-156">Nome</span><span class="sxs-lookup"><span data-stu-id="ab1df-156">Name</span></span> | <span data-ttu-id="ab1df-157">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ab1df-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="ab1df-158">Prevalenza dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ab1df-158">Org prevalence</span></span> | <span data-ttu-id="ab1df-159">il conteggio distinto dei dispositivi che hanno aperto la connessione di rete a questo IP.</span><span class="sxs-lookup"><span data-stu-id="ab1df-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="ab1df-160">Org first seen</span><span class="sxs-lookup"><span data-stu-id="ab1df-160">Org first seen</span></span> | <span data-ttu-id="ab1df-161">la prima connessione per questo INDIRIZZO IP nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ab1df-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="ab1df-162">Org last seen</span><span class="sxs-lookup"><span data-stu-id="ab1df-162">Org last seen</span></span>  | <span data-ttu-id="ab1df-163">l'ultima connessione per questo INDIRIZZO IP nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ab1df-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="ab1df-164">Queste informazioni statistiche si basano sui dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="ab1df-164">This statistic information is based on data from the past 30 days.</span></span> 
