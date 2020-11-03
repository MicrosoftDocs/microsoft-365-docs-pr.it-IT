---
title: API di caccia avanzate
description: Informazioni su come eseguire query di ricerca avanzata tramite Microsoft 365 Defender API
keywords: Ricerca avanzata, API, API, MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c43d263009578af6280ffdc780ab0f9a174a3b97
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844033"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="4aa76-104">API di caccia avanzate</span><span class="sxs-lookup"><span data-stu-id="4aa76-104">Advanced hunting APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4aa76-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4aa76-105">**Applies to:**</span></span>
- <span data-ttu-id="4aa76-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4aa76-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="4aa76-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="4aa76-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4aa76-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="4aa76-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="4aa76-109">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="4aa76-109">Limitations</span></span>
1. <span data-ttu-id="4aa76-110">È possibile eseguire una query solo sui dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="4aa76-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="4aa76-111">I risultati includono un massimo di 100.000 righe.</span><span class="sxs-lookup"><span data-stu-id="4aa76-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="4aa76-112">Il numero di esecuzioni è limitato per tenant: fino a 10 chiamate al minuto, 10 minuti di tempo di esecuzione ogni ora e 4 ore di tempo di esecuzione al giorno.</span><span class="sxs-lookup"><span data-stu-id="4aa76-112">The number of executions is limited per tenant: up to 10 calls per minute, 10 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="4aa76-113">Il tempo di esecuzione massimo di una singola richiesta è di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="4aa76-113">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="4aa76-114">la risposta 429 rappresenterà il raggiungimento del limite di quota sia per numero di richieste che per CPU.</span><span class="sxs-lookup"><span data-stu-id="4aa76-114">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="4aa76-115">Il corpo di risposta 429 indicherà anche l'ora in cui la quota viene rinnovata.</span><span class="sxs-lookup"><span data-stu-id="4aa76-115">The 429 response body will also indicate the time until the quota is renewed.</span></span> 


## <a name="permissions"></a><span data-ttu-id="4aa76-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4aa76-116">Permissions</span></span>
<span data-ttu-id="4aa76-117">Per chiamare l'API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4aa76-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4aa76-118">Per ulteriori informazioni, tra cui la scelta delle autorizzazioni, vedere [Access the Microsoft 365 Defender Apis](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="4aa76-118">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="4aa76-119">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4aa76-119">Permission type</span></span> |   <span data-ttu-id="4aa76-120">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4aa76-120">Permission</span></span>  |   <span data-ttu-id="4aa76-121">Nome visualizzato per le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4aa76-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4aa76-122">Applicazione</span><span class="sxs-lookup"><span data-stu-id="4aa76-122">Application</span></span> |   <span data-ttu-id="4aa76-123">AdvancedHunting. Read. All</span><span class="sxs-lookup"><span data-stu-id="4aa76-123">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="4aa76-124">' Esegui query avanzate '</span><span class="sxs-lookup"><span data-stu-id="4aa76-124">'Run advanced queries'</span></span>
<span data-ttu-id="4aa76-125">Delegati (account aziendale o dell'Istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="4aa76-125">Delegated (work or school account)</span></span> | <span data-ttu-id="4aa76-126">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="4aa76-126">AdvancedHunting.Read</span></span> | <span data-ttu-id="4aa76-127">' Esegui query avanzate '</span><span class="sxs-lookup"><span data-stu-id="4aa76-127">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="4aa76-128">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="4aa76-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4aa76-129">L'utente deve disporre del ruolo di annuncio ' Visualizza dati '</span><span class="sxs-lookup"><span data-stu-id="4aa76-129">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="4aa76-130">L'utente deve disporre dell'accesso al dispositivo, in base alle impostazioni del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="4aa76-130">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="4aa76-131">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="4aa76-131">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="4aa76-132">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="4aa76-132">Request headers</span></span>

<span data-ttu-id="4aa76-133">Intestazione</span><span class="sxs-lookup"><span data-stu-id="4aa76-133">Header</span></span> | <span data-ttu-id="4aa76-134">Valore</span><span class="sxs-lookup"><span data-stu-id="4aa76-134">Value</span></span> 
:---|:---
<span data-ttu-id="4aa76-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="4aa76-135">Authorization</span></span> | <span data-ttu-id="4aa76-136">Portatore {token}.</span><span class="sxs-lookup"><span data-stu-id="4aa76-136">Bearer {token}.</span></span> <span data-ttu-id="4aa76-137">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4aa76-137">**Required**.</span></span>
<span data-ttu-id="4aa76-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="4aa76-138">Content-Type</span></span>    | <span data-ttu-id="4aa76-139">applicazione/JSON</span><span class="sxs-lookup"><span data-stu-id="4aa76-139">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="4aa76-140">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="4aa76-140">Request body</span></span>
<span data-ttu-id="4aa76-141">Nel corpo della richiesta fornire un oggetto JSON con i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="4aa76-141">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="4aa76-142">Parametro</span><span class="sxs-lookup"><span data-stu-id="4aa76-142">Parameter</span></span> | <span data-ttu-id="4aa76-143">Tipo</span><span class="sxs-lookup"><span data-stu-id="4aa76-143">Type</span></span>    | <span data-ttu-id="4aa76-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4aa76-144">Description</span></span>
:---|:---|:---
<span data-ttu-id="4aa76-145">Query</span><span class="sxs-lookup"><span data-stu-id="4aa76-145">Query</span></span> | <span data-ttu-id="4aa76-146">Testo</span><span class="sxs-lookup"><span data-stu-id="4aa76-146">Text</span></span> |  <span data-ttu-id="4aa76-147">La query da eseguire.</span><span class="sxs-lookup"><span data-stu-id="4aa76-147">The query to run.</span></span> <span data-ttu-id="4aa76-148">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="4aa76-148">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="4aa76-149">Risposta</span><span class="sxs-lookup"><span data-stu-id="4aa76-149">Response</span></span>
<span data-ttu-id="4aa76-150">Se l'operazione ha esito positivo, questo metodo restituirà 200 OK e l'oggetto _QueryResponse_ nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="4aa76-150">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="4aa76-151">L'oggetto Response è suddiviso in tre parti (proprietà):</span><span class="sxs-lookup"><span data-stu-id="4aa76-151">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="4aa76-152">```Stats``` -Statistiche sulle prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="4aa76-152">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="4aa76-153">```Schema``` -Lo schema della risposta, un elenco di Name-Type coppie per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="4aa76-153">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="4aa76-154">```Results``` -Un elenco di eventi di caccia avanzati.</span><span class="sxs-lookup"><span data-stu-id="4aa76-154">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="4aa76-155">Esempio</span><span class="sxs-lookup"><span data-stu-id="4aa76-155">Example</span></span>

<span data-ttu-id="4aa76-156">Richiesta</span><span class="sxs-lookup"><span data-stu-id="4aa76-156">Request</span></span>

<span data-ttu-id="4aa76-157">Di seguito è riportato un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="4aa76-157">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="4aa76-158">Risposta</span><span class="sxs-lookup"><span data-stu-id="4aa76-158">Response</span></span>

<span data-ttu-id="4aa76-159">Di seguito è riportato un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="4aa76-159">Here is an example of the response.</span></span>


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
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
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a><span data-ttu-id="4aa76-160">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="4aa76-160">Related topic</span></span>
- [<span data-ttu-id="4aa76-161">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4aa76-161">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
