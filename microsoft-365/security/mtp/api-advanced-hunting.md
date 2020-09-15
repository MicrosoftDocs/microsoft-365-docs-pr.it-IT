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
ms.openlocfilehash: 92d5d2840963ae00ae0f03e3359f287371f770ee
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650384"
---
# <a name="advanced-hunting-apis"></a><span data-ttu-id="30524-104">API di caccia avanzate</span><span class="sxs-lookup"><span data-stu-id="30524-104">Advanced hunting APIs</span></span>

<span data-ttu-id="30524-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="30524-105">**Applies to:**</span></span>
- <span data-ttu-id="30524-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="30524-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="30524-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="30524-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="30524-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="30524-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="limitations"></a><span data-ttu-id="30524-109">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="30524-109">Limitations</span></span>
1. <span data-ttu-id="30524-110">È possibile eseguire una query solo sui dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="30524-110">You can only run a query on data from the last 30 days.</span></span>
2. <span data-ttu-id="30524-111">I risultati includono un massimo di 100.000 righe.</span><span class="sxs-lookup"><span data-stu-id="30524-111">The results will include a maximum of 100,000 rows.</span></span>
3. <span data-ttu-id="30524-112">Il numero di esecuzioni è limitato per tenant: fino a 15 chiamate al minuto, 15 minuti di tempo di esecuzione ogni ora e 4 ore di tempo di esecuzione al giorno.</span><span class="sxs-lookup"><span data-stu-id="30524-112">The number of executions is limited per tenant: up to 15 calls per minute, 15 minutes of running time every hour and 4 hours of running time a day.</span></span>
4. <span data-ttu-id="30524-113">Il tempo di esecuzione massimo di una singola richiesta è di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="30524-113">The maximal execution time of a single request is 10 minutes.</span></span>

## <a name="permissions"></a><span data-ttu-id="30524-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="30524-114">Permissions</span></span>
<span data-ttu-id="30524-115">Per chiamare l'API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="30524-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="30524-116">Per ulteriori informazioni, inclusa la scelta delle autorizzazioni, vedere [Access the Microsoft Threat Protection Apis](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="30524-116">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="30524-117">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="30524-117">Permission type</span></span> |   <span data-ttu-id="30524-118">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="30524-118">Permission</span></span>  |   <span data-ttu-id="30524-119">Nome visualizzato per le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="30524-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="30524-120">Applicazione</span><span class="sxs-lookup"><span data-stu-id="30524-120">Application</span></span> |   <span data-ttu-id="30524-121">AdvancedHunting. Read. All</span><span class="sxs-lookup"><span data-stu-id="30524-121">AdvancedHunting.Read.All</span></span> |  <span data-ttu-id="30524-122">' Esegui query avanzate '</span><span class="sxs-lookup"><span data-stu-id="30524-122">'Run advanced queries'</span></span>
<span data-ttu-id="30524-123">Delegati (account aziendale o dell'Istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="30524-123">Delegated (work or school account)</span></span> | <span data-ttu-id="30524-124">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="30524-124">AdvancedHunting.Read</span></span> | <span data-ttu-id="30524-125">' Esegui query avanzate '</span><span class="sxs-lookup"><span data-stu-id="30524-125">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="30524-126">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="30524-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="30524-127">L'utente deve disporre del ruolo di annuncio ' Visualizza dati '</span><span class="sxs-lookup"><span data-stu-id="30524-127">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="30524-128">L'utente deve disporre dell'accesso al dispositivo, in base alle impostazioni del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="30524-128">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="30524-129">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="30524-129">HTTP request</span></span>
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="30524-130">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="30524-130">Request headers</span></span>

<span data-ttu-id="30524-131">Intestazione</span><span class="sxs-lookup"><span data-stu-id="30524-131">Header</span></span> | <span data-ttu-id="30524-132">Valore</span><span class="sxs-lookup"><span data-stu-id="30524-132">Value</span></span> 
:---|:---
<span data-ttu-id="30524-133">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="30524-133">Authorization</span></span> | <span data-ttu-id="30524-134">Portatore {token}.</span><span class="sxs-lookup"><span data-stu-id="30524-134">Bearer {token}.</span></span> <span data-ttu-id="30524-135">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="30524-135">**Required**.</span></span>
<span data-ttu-id="30524-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="30524-136">Content-Type</span></span>    | <span data-ttu-id="30524-137">applicazione/JSON</span><span class="sxs-lookup"><span data-stu-id="30524-137">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="30524-138">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="30524-138">Request body</span></span>
<span data-ttu-id="30524-139">Nel corpo della richiesta fornire un oggetto JSON con i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="30524-139">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="30524-140">Parametro</span><span class="sxs-lookup"><span data-stu-id="30524-140">Parameter</span></span> | <span data-ttu-id="30524-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="30524-141">Type</span></span>    | <span data-ttu-id="30524-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30524-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="30524-143">Query</span><span class="sxs-lookup"><span data-stu-id="30524-143">Query</span></span> | <span data-ttu-id="30524-144">Testo</span><span class="sxs-lookup"><span data-stu-id="30524-144">Text</span></span> |  <span data-ttu-id="30524-145">La query da eseguire.</span><span class="sxs-lookup"><span data-stu-id="30524-145">The query to run.</span></span> <span data-ttu-id="30524-146">**Obbligatorio**.</span><span class="sxs-lookup"><span data-stu-id="30524-146">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="30524-147">Risposta</span><span class="sxs-lookup"><span data-stu-id="30524-147">Response</span></span>
<span data-ttu-id="30524-148">Se l'operazione ha esito positivo, questo metodo restituirà 200 OK e l'oggetto _QueryResponse_ nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="30524-148">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span> <br><br>

<span data-ttu-id="30524-149">L'oggetto Response è suddiviso in tre parti (proprietà):</span><span class="sxs-lookup"><span data-stu-id="30524-149">The response object is divided to 3 parts (properties):</span></span><br>
1) <span data-ttu-id="30524-150">```Stats``` -Statistiche sulle prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="30524-150">```Stats``` - Query performance statistics.</span></span><br>
2) <span data-ttu-id="30524-151">```Schema``` -Lo schema della risposta, un elenco delle coppie nome-tipo per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="30524-151">```Schema``` - The schema of the response, a list of Name-Type pairs for each column.</span></span> <br>
3) <span data-ttu-id="30524-152">```Results``` -Un elenco di eventi di caccia avanzati.</span><span class="sxs-lookup"><span data-stu-id="30524-152">```Results``` - A list of Advanced Hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="30524-153">Esempio</span><span class="sxs-lookup"><span data-stu-id="30524-153">Example</span></span>

<span data-ttu-id="30524-154">Richiesta</span><span class="sxs-lookup"><span data-stu-id="30524-154">Request</span></span>

<span data-ttu-id="30524-155">Di seguito è riportato un esempio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="30524-155">Here is an example of the request.</span></span>


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

<span data-ttu-id="30524-156">Risposta</span><span class="sxs-lookup"><span data-stu-id="30524-156">Response</span></span>

<span data-ttu-id="30524-157">Di seguito è riportato un esempio di risposta.</span><span class="sxs-lookup"><span data-stu-id="30524-157">Here is an example of the response.</span></span>


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

## <a name="related-topic"></a><span data-ttu-id="30524-158">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="30524-158">Related topic</span></span>
- [<span data-ttu-id="30524-159">Accedere alle API di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="30524-159">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
