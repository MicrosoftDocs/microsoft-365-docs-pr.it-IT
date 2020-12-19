---
title: API di caccia avanzata Microsoft 365 Defender
description: Informazioni su come eseguire query di caccia avanzate utilizzando l'API di caccia avanzata di Microsoft 365 Defender
keywords: Advanced Hunting, APIs, API, MTP, M365 Defender, Microsoft 365 Defender
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
ms.openlocfilehash: e7cd9192ec25e01ed06b77cb2b39357cb9df79bd
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719381"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="ae5d2-104">API di caccia avanzata Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae5d2-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="ae5d2-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ae5d2-105">**Applies to:**</span></span>

- <span data-ttu-id="ae5d2-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ae5d2-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae5d2-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="ae5d2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ae5d2-109">[Advanced Hunting](advanced-hunting-overview.md) è uno strumento di ricerca di minacce che utilizza [query appositamente costruite](advanced-hunting-query-language.md) per esaminare gli ultimi 30 giorni di dati degli eventi in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="ae5d2-110">È possibile utilizzare le query di ricerca avanzate per ispezionare attività inusuali, individuare possibili minacce e persino rispondere agli attacchi.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="ae5d2-111">L'API di ricerca avanzata consente di programatically i dati degli eventi di query.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="ae5d2-112">Quote e allocazione delle risorse</span><span class="sxs-lookup"><span data-stu-id="ae5d2-112">Quotas and resource allocation</span></span>

<span data-ttu-id="ae5d2-113">Le seguenti condizioni si riferiscono a tutte le query.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="ae5d2-114">Le query esplorano e restituiscono dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="ae5d2-115">I risultati possono restituire fino a 100.000 righe.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="ae5d2-116">È possibile effettuare fino a 10 chiamate al minuto per tenant.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-116">You can make up to 10 calls per minute per tenant.</span></span>
4. <span data-ttu-id="ae5d2-117">Si dispone di 10 minuti di tempo di esecuzione per ora per tenant.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="ae5d2-118">Si dispone di quattro ore totali di tempo di esecuzione per ogni tenant.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-118">You have four total hours of running time day per tenant.</span></span>
6. <span data-ttu-id="ae5d2-119">Se si esegue una singola richiesta per più di 10 minuti, il timeout e la restituzione di un errore.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="ae5d2-120">Un `429` codice di risposta HTTP indica che è stata raggiunta una quota, in base al numero di richieste inviate o al tempo di esecuzione assegnato.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="ae5d2-121">Il corpo di risposta includerà l'ora in cui la quota raggiunta verrà reimpostata.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-121">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="ae5d2-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ae5d2-122">Permissions</span></span>

<span data-ttu-id="ae5d2-123">È necessaria una delle autorizzazioni seguenti per chiamare l'API di caccia avanzata.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-123">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="ae5d2-124">Per ulteriori informazioni, tra cui la scelta delle autorizzazioni, vedere [Access the Microsoft 365 Defender Protection Apis](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="ae5d2-124">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="ae5d2-125">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ae5d2-125">Permission type</span></span> | <span data-ttu-id="ae5d2-126">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ae5d2-126">Permission</span></span> | <span data-ttu-id="ae5d2-127">Nome visualizzato per le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ae5d2-127">Permission display name</span></span>
-|-|-
<span data-ttu-id="ae5d2-128">Applicazione</span><span class="sxs-lookup"><span data-stu-id="ae5d2-128">Application</span></span> | <span data-ttu-id="ae5d2-129">AdvancedHunting. Read. All</span><span class="sxs-lookup"><span data-stu-id="ae5d2-129">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="ae5d2-130">Eseguire query avanzate</span><span class="sxs-lookup"><span data-stu-id="ae5d2-130">Run advanced queries</span></span>
<span data-ttu-id="ae5d2-131">Delegati (account aziendale o dell'Istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="ae5d2-131">Delegated (work or school account)</span></span> | <span data-ttu-id="ae5d2-132">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="ae5d2-132">AdvancedHunting.Read</span></span> | <span data-ttu-id="ae5d2-133">Eseguire query avanzate</span><span class="sxs-lookup"><span data-stu-id="ae5d2-133">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="ae5d2-134">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="ae5d2-134">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="ae5d2-135">L'utente deve disporre del ruolo di annuncio ' Visualizza dati '</span><span class="sxs-lookup"><span data-stu-id="ae5d2-135">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="ae5d2-136">L'utente deve disporre dell'accesso al dispositivo, in base alle impostazioni del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-136">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="ae5d2-137">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="ae5d2-137">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="ae5d2-138">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="ae5d2-138">Request headers</span></span>

<span data-ttu-id="ae5d2-139">Intestazione</span><span class="sxs-lookup"><span data-stu-id="ae5d2-139">Header</span></span> | <span data-ttu-id="ae5d2-140">Valore</span><span class="sxs-lookup"><span data-stu-id="ae5d2-140">Value</span></span>
-|-
<span data-ttu-id="ae5d2-141">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="ae5d2-141">Authorization</span></span> | <span data-ttu-id="ae5d2-142">Portatore {token} **Note: required**</span><span class="sxs-lookup"><span data-stu-id="ae5d2-142">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="ae5d2-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ae5d2-143">Content-Type</span></span> | <span data-ttu-id="ae5d2-144">applicazione/JSON</span><span class="sxs-lookup"><span data-stu-id="ae5d2-144">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="ae5d2-145">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="ae5d2-145">Request body</span></span>

<span data-ttu-id="ae5d2-146">Nel corpo della richiesta fornire un oggetto JSON con i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="ae5d2-146">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="ae5d2-147">Parametro</span><span class="sxs-lookup"><span data-stu-id="ae5d2-147">Parameter</span></span> | <span data-ttu-id="ae5d2-148">Tipo</span><span class="sxs-lookup"><span data-stu-id="ae5d2-148">Type</span></span> | <span data-ttu-id="ae5d2-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae5d2-149">Description</span></span>
-|-|-
<span data-ttu-id="ae5d2-150">Query</span><span class="sxs-lookup"><span data-stu-id="ae5d2-150">Query</span></span> | <span data-ttu-id="ae5d2-151">Testo</span><span class="sxs-lookup"><span data-stu-id="ae5d2-151">Text</span></span> | <span data-ttu-id="ae5d2-152">La query da eseguire.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-152">The query to run.</span></span> <span data-ttu-id="ae5d2-153">**Nota: obbligatoria**</span><span class="sxs-lookup"><span data-stu-id="ae5d2-153">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="ae5d2-154">Risposta</span><span class="sxs-lookup"><span data-stu-id="ae5d2-154">Response</span></span>

<span data-ttu-id="ae5d2-155">Se l'operazione ha esito positivo, il metodo restituirà `200 OK` un oggetto _QueryResponse_ nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-155">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="ae5d2-156">L'oggetto Response contiene tre proprietà di primo livello:</span><span class="sxs-lookup"><span data-stu-id="ae5d2-156">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="ae5d2-157">Stats-un dizionario delle statistiche delle prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-157">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="ae5d2-158">Schema: lo schema della risposta, un elenco di Name-Type coppie per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-158">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="ae5d2-159">Results-un elenco di eventi di caccia avanzati.</span><span class="sxs-lookup"><span data-stu-id="ae5d2-159">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="ae5d2-160">Esempio</span><span class="sxs-lookup"><span data-stu-id="ae5d2-160">Example</span></span>

<span data-ttu-id="ae5d2-161">Nell'esempio seguente, un utente invia la query in basso e riceve un oggetto Response API contenente `Stats` , `Schema` e `Results` .</span><span class="sxs-lookup"><span data-stu-id="ae5d2-161">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="ae5d2-162">Query</span><span class="sxs-lookup"><span data-stu-id="ae5d2-162">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="ae5d2-163">Oggetto Response</span><span class="sxs-lookup"><span data-stu-id="ae5d2-163">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="ae5d2-164">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="ae5d2-164">Related articles</span></span>

- [<span data-ttu-id="ae5d2-165">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae5d2-165">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="ae5d2-166">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="ae5d2-166">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="ae5d2-167">Informazioni sui codici di errore</span><span class="sxs-lookup"><span data-stu-id="ae5d2-167">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="ae5d2-168">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="ae5d2-168">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
