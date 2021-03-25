---
title: Rilevazione avanzata API
ms.reviewer: ''
description: Scopri come usare l'API di ricerca avanzata per eseguire query avanzate in Microsoft Defender per Endpoint. Scopri le limitazioni e vedi un esempio.
keywords: api, api supportate, ricerca avanzata, query
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
ms.openlocfilehash: caf7a1bacfd726c560356d542bec3cf56c6b39d4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200198"
---
# <a name="advanced-hunting-api"></a><span data-ttu-id="7684b-105">API di ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="7684b-105">Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7684b-106">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="7684b-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="7684b-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7684b-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7684b-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="7684b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a><span data-ttu-id="7684b-109">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="7684b-109">Limitations</span></span>
1. <span data-ttu-id="7684b-110">È possibile eseguire una query solo sui dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="7684b-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="7684b-111">I risultati includeranno un massimo di 100.000 righe.</span><span class="sxs-lookup"><span data-stu-id="7684b-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="7684b-112">Il numero di esecuzioni è limitato per tenant:</span><span class="sxs-lookup"><span data-stu-id="7684b-112">The number of executions is limited per tenant:</span></span>
   - <span data-ttu-id="7684b-113">Chiamate API: fino a 45 chiamate al minuto.</span><span class="sxs-lookup"><span data-stu-id="7684b-113">API calls: Up to 45 calls per minute.</span></span>
   - <span data-ttu-id="7684b-114">Tempo di esecuzione: 10 minuti di tempo di esecuzione ogni ora e 3 ore di esecuzione al giorno.</span><span class="sxs-lookup"><span data-stu-id="7684b-114">Execution time: 10 minutes of running time every hour and 3 hours of running time a day.</span></span>
4. <span data-ttu-id="7684b-115">Il tempo massimo di esecuzione di una singola richiesta è di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="7684b-115">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="7684b-116">La risposta 429 rappresenterà il raggiungimento del limite di quota in base al numero di richieste o alla CPU.</span><span class="sxs-lookup"><span data-stu-id="7684b-116">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="7684b-117">Leggere il corpo della risposta per comprendere quale limite è stato raggiunto.</span><span class="sxs-lookup"><span data-stu-id="7684b-117">Read response body to understand what limit has been reached.</span></span> 

## <a name="permissions"></a><span data-ttu-id="7684b-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7684b-118">Permissions</span></span>
<span data-ttu-id="7684b-119">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="7684b-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7684b-120">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi [Usare Microsoft Defender per le API endpoint](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7684b-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="7684b-121">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7684b-121">Permission type</span></span> |   <span data-ttu-id="7684b-122">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7684b-122">Permission</span></span>  |   <span data-ttu-id="7684b-123">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7684b-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7684b-124">Applicazione</span><span class="sxs-lookup"><span data-stu-id="7684b-124">Application</span></span> |   <span data-ttu-id="7684b-125">AdvancedQuery.Read.All</span><span class="sxs-lookup"><span data-stu-id="7684b-125">AdvancedQuery.Read.All</span></span> |    <span data-ttu-id="7684b-126">"Esegui query avanzate"</span><span class="sxs-lookup"><span data-stu-id="7684b-126">'Run advanced queries'</span></span>
<span data-ttu-id="7684b-127">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="7684b-127">Delegated (work or school account)</span></span> | <span data-ttu-id="7684b-128">AdvancedQuery.Read</span><span class="sxs-lookup"><span data-stu-id="7684b-128">AdvancedQuery.Read</span></span> | <span data-ttu-id="7684b-129">"Esegui query avanzate"</span><span class="sxs-lookup"><span data-stu-id="7684b-129">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="7684b-130">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="7684b-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="7684b-131">L'utente deve avere il ruolo AD "Visualizza dati"</span><span class="sxs-lookup"><span data-stu-id="7684b-131">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="7684b-132">L'utente deve avere accesso al dispositivo in base alle impostazioni del gruppo di dispositivi (per ulteriori informazioni, vedere [Creare](machine-groups.md) e gestire gruppi di dispositivi)</span><span class="sxs-lookup"><span data-stu-id="7684b-132">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="7684b-133">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="7684b-133">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a><span data-ttu-id="7684b-134">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="7684b-134">Request headers</span></span>

<span data-ttu-id="7684b-135">Intestazione</span><span class="sxs-lookup"><span data-stu-id="7684b-135">Header</span></span> | <span data-ttu-id="7684b-136">Valore</span><span class="sxs-lookup"><span data-stu-id="7684b-136">Value</span></span> 
:---|:---
<span data-ttu-id="7684b-137">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="7684b-137">Authorization</span></span> | <span data-ttu-id="7684b-138">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="7684b-138">Bearer {token}.</span></span> <span data-ttu-id="7684b-139">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="7684b-139">**Required**.</span></span>
<span data-ttu-id="7684b-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="7684b-140">Content-Type</span></span>    | <span data-ttu-id="7684b-141">application/json</span><span class="sxs-lookup"><span data-stu-id="7684b-141">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="7684b-142">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="7684b-142">Request body</span></span>
<span data-ttu-id="7684b-143">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="7684b-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="7684b-144">Parametro</span><span class="sxs-lookup"><span data-stu-id="7684b-144">Parameter</span></span> | <span data-ttu-id="7684b-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="7684b-145">Type</span></span>    | <span data-ttu-id="7684b-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7684b-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="7684b-147">Query</span><span class="sxs-lookup"><span data-stu-id="7684b-147">Query</span></span> | <span data-ttu-id="7684b-148">Testo</span><span class="sxs-lookup"><span data-stu-id="7684b-148">Text</span></span> |  <span data-ttu-id="7684b-149">Query da eseguire.</span><span class="sxs-lookup"><span data-stu-id="7684b-149">The query to run.</span></span> <span data-ttu-id="7684b-150">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="7684b-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="7684b-151">Risposta</span><span class="sxs-lookup"><span data-stu-id="7684b-151">Response</span></span>
<span data-ttu-id="7684b-152">Se ha esito positivo, questo metodo restituisce 200 OK e _l'oggetto QueryResponse_ nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="7684b-152">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="7684b-153">Esempio</span><span class="sxs-lookup"><span data-stu-id="7684b-153">Example</span></span>

<span data-ttu-id="7684b-154">Richiesta</span><span class="sxs-lookup"><span data-stu-id="7684b-154">Request</span></span>

<span data-ttu-id="7684b-155">Ecco un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="7684b-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

<span data-ttu-id="7684b-156">Risposta</span><span class="sxs-lookup"><span data-stu-id="7684b-156">Response</span></span>

<span data-ttu-id="7684b-157">Ecco un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="7684b-157">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="7684b-158">L'oggetto risposta mostrato qui potrebbe essere troncato per brevità.</span><span class="sxs-lookup"><span data-stu-id="7684b-158">The response object shown here may be truncated for brevity.</span></span> <span data-ttu-id="7684b-159">Tutte le proprietà verranno restituite da una chiamata effettiva.</span><span class="sxs-lookup"><span data-stu-id="7684b-159">All of the properties will be returned from an actual call.</span></span>

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topic"></a><span data-ttu-id="7684b-160">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="7684b-160">Related topic</span></span>
- [<span data-ttu-id="7684b-161">Introduzione alle API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="7684b-161">Microsoft Defender for Endpoint APIs introduction</span></span>](apis-intro.md)
- [<span data-ttu-id="7684b-162">Ricerca avanzata dal portale</span><span class="sxs-lookup"><span data-stu-id="7684b-162">Advanced Hunting from Portal</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7684b-163">Ricerca avanzata tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="7684b-163">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
