---
title: API di caccia avanzate
description: Informazioni su come eseguire query di ricerca avanzata tramite l'API Microsoft Threat Protection
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
ms.openlocfilehash: dd7b02200e370588bbb9470a3d7e897b30234ead
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197810"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="31ed1-104">API di caccia avanzate</span><span class="sxs-lookup"><span data-stu-id="31ed1-104">Advanced hunting APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="31ed1-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="31ed1-105">**Applies to:**</span></span>
- <span data-ttu-id="31ed1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="31ed1-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="31ed1-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="31ed1-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="31ed1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="31ed1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="31ed1-109">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="31ed1-109">Limitations</span></span>
1. <span data-ttu-id="31ed1-110">È possibile eseguire una query solo sui dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="31ed1-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="31ed1-111">I risultati includono un massimo di 100.000 righe.</span><span class="sxs-lookup"><span data-stu-id="31ed1-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="31ed1-112">Il numero di esecuzioni è limitato per tenant: fino a 10 chiamate al minuto, 10 minuti di tempo di esecuzione ogni ora e 4 ore di tempo di esecuzione al giorno.</span><span class="sxs-lookup"><span data-stu-id="31ed1-112">The number of executions is limited per tenant: up to 10 calls per minute, 10 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="31ed1-113">Il tempo di esecuzione massimo di una singola richiesta è di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="31ed1-113">The maximal execution time of a single request is 10 minutes.</span></span>
5. <span data-ttu-id="31ed1-114">la risposta 429 rappresenterà il raggiungimento del limite di quota sia per numero di richieste che per CPU.</span><span class="sxs-lookup"><span data-stu-id="31ed1-114">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="31ed1-115">Il corpo di risposta 429 indicherà anche l'ora in cui la quota viene rinnovata.</span><span class="sxs-lookup"><span data-stu-id="31ed1-115">The 429 response body will also indicate the time until the quota is renewed.</span></span> 


## <a name="permissions"></a><span data-ttu-id="31ed1-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="31ed1-116">Permissions</span></span>
<span data-ttu-id="31ed1-117">Per chiamare l'API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="31ed1-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="31ed1-118">Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Access the Microsoft Threat Protection Apis](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="31ed1-118">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="31ed1-119">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="31ed1-119">Permission type</span></span> |   <span data-ttu-id="31ed1-120">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="31ed1-120">Permission</span></span>  |   <span data-ttu-id="31ed1-121">Nome visualizzato per le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="31ed1-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="31ed1-122">Applicazione</span><span class="sxs-lookup"><span data-stu-id="31ed1-122">Application</span></span> |   <span data-ttu-id="31ed1-123">AdvancedHunting. Read. All</span><span class="sxs-lookup"><span data-stu-id="31ed1-123">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="31ed1-124">' Esegui query avanzate '</span><span class="sxs-lookup"><span data-stu-id="31ed1-124">'Run advanced queries'</span></span>
<span data-ttu-id="31ed1-125">Delegati (account aziendale o dell'Istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="31ed1-125">Delegated (work or school account)</span></span> | <span data-ttu-id="31ed1-126">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="31ed1-126">AdvancedHunting.Read</span></span> | <span data-ttu-id="31ed1-127">' Esegui query avanzate '</span><span class="sxs-lookup"><span data-stu-id="31ed1-127">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="31ed1-128">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="31ed1-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="31ed1-129">L'utente deve disporre del ruolo di annuncio ' Visualizza dati '</span><span class="sxs-lookup"><span data-stu-id="31ed1-129">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="31ed1-130">L'utente deve disporre dell'accesso al dispositivo, in base alle impostazioni del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="31ed1-130">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="31ed1-131">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="31ed1-131">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="31ed1-132">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="31ed1-132">Request headers</span></span>

<span data-ttu-id="31ed1-133">Intestazione</span><span class="sxs-lookup"><span data-stu-id="31ed1-133">Header</span></span> | <span data-ttu-id="31ed1-134">Valore</span><span class="sxs-lookup"><span data-stu-id="31ed1-134">Value</span></span> 
:---|:---
<span data-ttu-id="31ed1-135">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="31ed1-135">Authorization</span></span> | <span data-ttu-id="31ed1-136">Portatore {token}.</span><span class="sxs-lookup"><span data-stu-id="31ed1-136">Bearer {token}.</span></span> <span data-ttu-id="31ed1-137">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="31ed1-137">**Required**.</span></span>
<span data-ttu-id="31ed1-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="31ed1-138">Content-Type</span></span>    | <span data-ttu-id="31ed1-139">applicazione/JSON</span><span class="sxs-lookup"><span data-stu-id="31ed1-139">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="31ed1-140">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="31ed1-140">Request body</span></span>
<span data-ttu-id="31ed1-141">Nel corpo della richiesta fornire un oggetto JSON con i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="31ed1-141">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="31ed1-142">Parametro</span><span class="sxs-lookup"><span data-stu-id="31ed1-142">Parameter</span></span> | <span data-ttu-id="31ed1-143">Tipo</span><span class="sxs-lookup"><span data-stu-id="31ed1-143">Type</span></span>    | <span data-ttu-id="31ed1-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31ed1-144">Description</span></span>
:---|:---|:---
<span data-ttu-id="31ed1-145">Query</span><span class="sxs-lookup"><span data-stu-id="31ed1-145">Query</span></span> | <span data-ttu-id="31ed1-146">Testo</span><span class="sxs-lookup"><span data-stu-id="31ed1-146">Text</span></span> |  <span data-ttu-id="31ed1-147">La query da eseguire.</span><span class="sxs-lookup"><span data-stu-id="31ed1-147">The query to run.</span></span> <span data-ttu-id="31ed1-148">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="31ed1-148">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="31ed1-149">Risposta</span><span class="sxs-lookup"><span data-stu-id="31ed1-149">Response</span></span>
<span data-ttu-id="31ed1-150">Se l'operazione ha esito positivo, questo metodo restituirà 200 OK e l'oggetto _QueryResponse_ nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="31ed1-150">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="31ed1-151">L'oggetto Response è suddiviso in tre parti (proprietà):</span><span class="sxs-lookup"><span data-stu-id="31ed1-151">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="31ed1-152">```Stats``` -Statistiche sulle prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="31ed1-152">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="31ed1-153">```Schema``` -Lo schema della risposta, un elenco delle coppie nome-tipo per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="31ed1-153">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="31ed1-154">```Results``` -Un elenco di eventi di caccia avanzati.</span><span class="sxs-lookup"><span data-stu-id="31ed1-154">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="31ed1-155">Esempio</span><span class="sxs-lookup"><span data-stu-id="31ed1-155">Example</span></span>

<span data-ttu-id="31ed1-156">Richiesta</span><span class="sxs-lookup"><span data-stu-id="31ed1-156">Request</span></span>

<span data-ttu-id="31ed1-157">Di seguito è riportato un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="31ed1-157">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="31ed1-158">Risposta</span><span class="sxs-lookup"><span data-stu-id="31ed1-158">Response</span></span>

<span data-ttu-id="31ed1-159">Di seguito è riportato un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="31ed1-159">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="31ed1-160">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="31ed1-160">Related topic</span></span>
- [<span data-ttu-id="31ed1-161">Accedere alle API di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="31ed1-161">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
