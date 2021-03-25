---
title: API di ricerca avanzata di Microsoft 365 Defender
description: Informazioni su come eseguire query di ricerca avanzate con l'API di ricerca avanzata di Microsoft 365 Defender
keywords: Advanced Hunting, APIs, api, MTP, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 482801bb47429ae370e06cfcbcf26bacfb8b2a92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066762"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="3f91e-104">API di ricerca avanzata di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f91e-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3f91e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3f91e-105">**Applies to:**</span></span>

- <span data-ttu-id="3f91e-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3f91e-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f91e-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="3f91e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3f91e-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="3f91e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="3f91e-109">[La ricerca](advanced-hunting-overview.md) avanzata è uno [](advanced-hunting-query-language.md) strumento di ricerca delle minacce che usa query appositamente costruite per esaminare gli ultimi 30 giorni di dati degli eventi in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3f91e-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="3f91e-110">È possibile utilizzare query di ricerca avanzate per esaminare attività insolite, rilevare possibili minacce e persino rispondere agli attacchi.</span><span class="sxs-lookup"><span data-stu-id="3f91e-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="3f91e-111">L'API di ricerca avanzata consente di eseguire query a livello di programmazione sui dati degli eventi.</span><span class="sxs-lookup"><span data-stu-id="3f91e-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="3f91e-112">Quote e allocazione delle risorse</span><span class="sxs-lookup"><span data-stu-id="3f91e-112">Quotas and resource allocation</span></span>

<span data-ttu-id="3f91e-113">Le condizioni seguenti sono correlate a tutte le query.</span><span class="sxs-lookup"><span data-stu-id="3f91e-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="3f91e-114">Le query esplorano e restituiscono dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="3f91e-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="3f91e-115">I risultati possono restituire fino a 100.000 righe.</span><span class="sxs-lookup"><span data-stu-id="3f91e-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="3f91e-116">È possibile effettuare fino a 15 chiamate al minuto per tenant.</span><span class="sxs-lookup"><span data-stu-id="3f91e-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="3f91e-117">Hai 10 minuti di tempo di esecuzione all'ora per ogni tenant.</span><span class="sxs-lookup"><span data-stu-id="3f91e-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="3f91e-118">Hai quattro ore totali di tempo di esecuzione al giorno per tenant.</span><span class="sxs-lookup"><span data-stu-id="3f91e-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="3f91e-119">Se una singola richiesta viene eseguita per più di 10 minuti, si verifica il timeout e viene restituito un errore.</span><span class="sxs-lookup"><span data-stu-id="3f91e-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="3f91e-120">Un codice di risposta HTTP indica che hai raggiunto una quota, in base al numero di richieste inviate o al tempo `429` di esecuzione assegnato.</span><span class="sxs-lookup"><span data-stu-id="3f91e-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="3f91e-121">Leggere il corpo della risposta per comprendere il limite raggiunto.</span><span class="sxs-lookup"><span data-stu-id="3f91e-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="3f91e-122">Tutte le quote elencate sopra (ad esempio 15 chiamate al min) sono per dimensione del tenant.</span><span class="sxs-lookup"><span data-stu-id="3f91e-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="3f91e-123">Queste quote sono minime.</span><span class="sxs-lookup"><span data-stu-id="3f91e-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="3f91e-124">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3f91e-124">Permissions</span></span>

<span data-ttu-id="3f91e-125">Una delle autorizzazioni seguenti è necessaria per chiamare l'API di ricerca avanzata.</span><span class="sxs-lookup"><span data-stu-id="3f91e-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="3f91e-126">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Accedere alle API di [Microsoft 365 Defender Protection](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="3f91e-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="3f91e-127">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3f91e-127">Permission type</span></span> | <span data-ttu-id="3f91e-128">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3f91e-128">Permission</span></span> | <span data-ttu-id="3f91e-129">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3f91e-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="3f91e-130">Applicazione</span><span class="sxs-lookup"><span data-stu-id="3f91e-130">Application</span></span> | <span data-ttu-id="3f91e-131">AdvancedHunting.Read.All</span><span class="sxs-lookup"><span data-stu-id="3f91e-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="3f91e-132">Eseguire query avanzate</span><span class="sxs-lookup"><span data-stu-id="3f91e-132">Run advanced queries</span></span>
<span data-ttu-id="3f91e-133">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="3f91e-133">Delegated (work or school account)</span></span> | <span data-ttu-id="3f91e-134">AdvancedHunting.Read</span><span class="sxs-lookup"><span data-stu-id="3f91e-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="3f91e-135">Eseguire query avanzate</span><span class="sxs-lookup"><span data-stu-id="3f91e-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="3f91e-136">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="3f91e-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="3f91e-137">L'utente deve disporre del ruolo AD "Visualizza dati"</span><span class="sxs-lookup"><span data-stu-id="3f91e-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="3f91e-138">L'utente deve avere accesso al dispositivo, in base alle impostazioni del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3f91e-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="3f91e-139">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="3f91e-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="3f91e-140">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="3f91e-140">Request headers</span></span>

<span data-ttu-id="3f91e-141">Intestazione</span><span class="sxs-lookup"><span data-stu-id="3f91e-141">Header</span></span> | <span data-ttu-id="3f91e-142">Valore</span><span class="sxs-lookup"><span data-stu-id="3f91e-142">Value</span></span>
-|-
<span data-ttu-id="3f91e-143">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3f91e-143">Authorization</span></span> | <span data-ttu-id="3f91e-144">Bearer {token} **Nota: obbligatoria**</span><span class="sxs-lookup"><span data-stu-id="3f91e-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="3f91e-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3f91e-145">Content-Type</span></span> | <span data-ttu-id="3f91e-146">application/json</span><span class="sxs-lookup"><span data-stu-id="3f91e-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="3f91e-147">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="3f91e-147">Request body</span></span>

<span data-ttu-id="3f91e-148">Nel corpo della richiesta, fornire un oggetto JSON con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f91e-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="3f91e-149">Parametro</span><span class="sxs-lookup"><span data-stu-id="3f91e-149">Parameter</span></span> | <span data-ttu-id="3f91e-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="3f91e-150">Type</span></span> | <span data-ttu-id="3f91e-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f91e-151">Description</span></span>
-|-|-
<span data-ttu-id="3f91e-152">Query</span><span class="sxs-lookup"><span data-stu-id="3f91e-152">Query</span></span> | <span data-ttu-id="3f91e-153">Testo</span><span class="sxs-lookup"><span data-stu-id="3f91e-153">Text</span></span> | <span data-ttu-id="3f91e-154">Query da eseguire.</span><span class="sxs-lookup"><span data-stu-id="3f91e-154">The query to run.</span></span> <span data-ttu-id="3f91e-155">**Nota: obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="3f91e-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="3f91e-156">Risposta</span><span class="sxs-lookup"><span data-stu-id="3f91e-156">Response</span></span>

<span data-ttu-id="3f91e-157">Se ha esito positivo, questo metodo restituirà `200 OK` e un _oggetto QueryResponse_ nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="3f91e-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="3f91e-158">L'oggetto response contiene tre proprietà di primo livello:</span><span class="sxs-lookup"><span data-stu-id="3f91e-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="3f91e-159">Statistiche: dizionario di statistiche sulle prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="3f91e-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="3f91e-160">Schema : schema della risposta, un elenco di coppie Name-Type per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="3f91e-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="3f91e-161">Risultati : elenco di eventi di ricerca avanzati.</span><span class="sxs-lookup"><span data-stu-id="3f91e-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="3f91e-162">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f91e-162">Example</span></span>

<span data-ttu-id="3f91e-163">Nell'esempio seguente, un utente invia la query seguente e riceve un oggetto risposta API contenente `Stats` `Schema` , e `Results` .</span><span class="sxs-lookup"><span data-stu-id="3f91e-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="3f91e-164">Query</span><span class="sxs-lookup"><span data-stu-id="3f91e-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="3f91e-165">Oggetto Response</span><span class="sxs-lookup"><span data-stu-id="3f91e-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="3f91e-166">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="3f91e-166">Related articles</span></span>

- [<span data-ttu-id="3f91e-167">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f91e-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="3f91e-168">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="3f91e-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="3f91e-169">Comprendere i codici di errore</span><span class="sxs-lookup"><span data-stu-id="3f91e-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="3f91e-170">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="3f91e-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)