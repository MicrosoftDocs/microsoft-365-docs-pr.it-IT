---
title: API di caccia avanzata Microsoft 365 Defender
description: Informazioni su come eseguire query di caccia avanzate utilizzando l'API di caccia avanzata di Microsoft 365 Defender
keywords: Advanced Hunting, APIs, API, MTP, M365 Defender, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 99f39a10de6231a72220c5c2a90ec915b1a4e44a
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988117"
---
# <a name="microsoft-365-defender-advanced-hunting-api"></a><span data-ttu-id="3cbec-104">API di caccia avanzata Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cbec-104">Microsoft 365 Defender Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3cbec-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="3cbec-105">**Applies to:**</span></span>

- <span data-ttu-id="3cbec-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3cbec-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cbec-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="3cbec-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3cbec-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="3cbec-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="3cbec-109">[Advanced Hunting](advanced-hunting-overview.md) è uno strumento di ricerca di minacce che utilizza [query appositamente costruite](advanced-hunting-query-language.md) per esaminare gli ultimi 30 giorni di dati degli eventi in Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3cbec-109">[Advanced hunting](advanced-hunting-overview.md) is a threat-hunting tool that uses [specially constructed queries](advanced-hunting-query-language.md) to examine the past 30 days of event data in Microsoft 365 Defender.</span></span> <span data-ttu-id="3cbec-110">È possibile utilizzare le query di ricerca avanzate per ispezionare attività inusuali, individuare possibili minacce e persino rispondere agli attacchi.</span><span class="sxs-lookup"><span data-stu-id="3cbec-110">You can use advanced hunting queries to inspect unusual activity, detect possible threats, and even respond to attacks.</span></span> <span data-ttu-id="3cbec-111">L'API di ricerca avanzata consente di programatically i dati degli eventi di query.</span><span class="sxs-lookup"><span data-stu-id="3cbec-111">The advanced hunting API allows you to programatically query event data.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="3cbec-112">Quote e allocazione delle risorse</span><span class="sxs-lookup"><span data-stu-id="3cbec-112">Quotas and resource allocation</span></span>

<span data-ttu-id="3cbec-113">Le seguenti condizioni si riferiscono a tutte le query.</span><span class="sxs-lookup"><span data-stu-id="3cbec-113">The following conditions relate to all queries.</span></span>

1. <span data-ttu-id="3cbec-114">Le query esplorano e restituiscono dati degli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="3cbec-114">Queries explore and return data from the past 30 days.</span></span>
2. <span data-ttu-id="3cbec-115">I risultati possono restituire fino a 100.000 righe.</span><span class="sxs-lookup"><span data-stu-id="3cbec-115">Results can return up to 100,000 rows.</span></span>
3. <span data-ttu-id="3cbec-116">È possibile effettuare fino a 15 chiamate al minuto per tenant.</span><span class="sxs-lookup"><span data-stu-id="3cbec-116">You can make up to 15 calls per minute per tenant.</span></span>
4. <span data-ttu-id="3cbec-117">Si dispone di 10 minuti di tempo di esecuzione per ora per tenant.</span><span class="sxs-lookup"><span data-stu-id="3cbec-117">You have 10 minutes of running time per hour per tenant.</span></span>
5. <span data-ttu-id="3cbec-118">Si dispone di quattro ore totali di tempo di esecuzione al giorno per tenant.</span><span class="sxs-lookup"><span data-stu-id="3cbec-118">You have four total hours of running time per day per tenant.</span></span>
6. <span data-ttu-id="3cbec-119">Se si esegue una singola richiesta per più di 10 minuti, il timeout e la restituzione di un errore.</span><span class="sxs-lookup"><span data-stu-id="3cbec-119">If a single request runs for more than 10 minutes, it will time out and return an error.</span></span>
7. <span data-ttu-id="3cbec-120">Un `429` codice di risposta HTTP indica che è stata raggiunta una quota, in base al numero di richieste inviate o al tempo di esecuzione assegnato.</span><span class="sxs-lookup"><span data-stu-id="3cbec-120">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="3cbec-121">Leggere il corpo della risposta per comprendere il limite raggiunto.</span><span class="sxs-lookup"><span data-stu-id="3cbec-121">Read the response body to understand the limit you have reached.</span></span> 

> [!NOTE]
> <span data-ttu-id="3cbec-122">Tutte le quote sopra elencate (ad esempio 15 chiamate al minuto) sono per dimensione tenant.</span><span class="sxs-lookup"><span data-stu-id="3cbec-122">All quotas listed above (for example 15 calls per min) are per tenant size.</span></span> <span data-ttu-id="3cbec-123">Queste quote sono minime.</span><span class="sxs-lookup"><span data-stu-id="3cbec-123">These quotas are the minimum.</span></span>

## <a name="permissions"></a><span data-ttu-id="3cbec-124">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3cbec-124">Permissions</span></span>

<span data-ttu-id="3cbec-125">È necessaria una delle autorizzazioni seguenti per chiamare l'API di caccia avanzata.</span><span class="sxs-lookup"><span data-stu-id="3cbec-125">One of the following permissions is required to call the advanced hunting API.</span></span> <span data-ttu-id="3cbec-126">Per ulteriori informazioni, tra cui la scelta delle autorizzazioni, vedere [Access the Microsoft 365 Defender Protection Apis](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="3cbec-126">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender Protection APIs](api-access.md)</span></span>

<span data-ttu-id="3cbec-127">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3cbec-127">Permission type</span></span> | <span data-ttu-id="3cbec-128">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3cbec-128">Permission</span></span> | <span data-ttu-id="3cbec-129">Nome visualizzato per le autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3cbec-129">Permission display name</span></span>
-|-|-
<span data-ttu-id="3cbec-130">Applicazione</span><span class="sxs-lookup"><span data-stu-id="3cbec-130">Application</span></span> | <span data-ttu-id="3cbec-131">AdvancedHunting. Read. All</span><span class="sxs-lookup"><span data-stu-id="3cbec-131">AdvancedHunting.Read.All</span></span> | <span data-ttu-id="3cbec-132">Eseguire query avanzate</span><span class="sxs-lookup"><span data-stu-id="3cbec-132">Run advanced queries</span></span>
<span data-ttu-id="3cbec-133">Delegati (account aziendale o dell'Istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="3cbec-133">Delegated (work or school account)</span></span> | <span data-ttu-id="3cbec-134">AdvancedHunting. Read</span><span class="sxs-lookup"><span data-stu-id="3cbec-134">AdvancedHunting.Read</span></span> | <span data-ttu-id="3cbec-135">Eseguire query avanzate</span><span class="sxs-lookup"><span data-stu-id="3cbec-135">Run advanced queries</span></span>

>[!Note]
> <span data-ttu-id="3cbec-136">Quando si ottiene un token utilizzando le credenziali utente:</span><span class="sxs-lookup"><span data-stu-id="3cbec-136">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="3cbec-137">L'utente deve disporre del ruolo di annuncio ' Visualizza dati '</span><span class="sxs-lookup"><span data-stu-id="3cbec-137">The user needs to have the 'View Data' AD role</span></span>
>- <span data-ttu-id="3cbec-138">L'utente deve disporre dell'accesso al dispositivo, in base alle impostazioni del gruppo di dispositivi.</span><span class="sxs-lookup"><span data-stu-id="3cbec-138">The user needs to have access to the device, based on device group settings.</span></span>

## <a name="http-request"></a><span data-ttu-id="3cbec-139">Richiesta HTTP</span><span class="sxs-lookup"><span data-stu-id="3cbec-139">HTTP request</span></span>

```HTTP
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a><span data-ttu-id="3cbec-140">Intestazioni di richiesta</span><span class="sxs-lookup"><span data-stu-id="3cbec-140">Request headers</span></span>

<span data-ttu-id="3cbec-141">Intestazione</span><span class="sxs-lookup"><span data-stu-id="3cbec-141">Header</span></span> | <span data-ttu-id="3cbec-142">Valore</span><span class="sxs-lookup"><span data-stu-id="3cbec-142">Value</span></span>
-|-
<span data-ttu-id="3cbec-143">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="3cbec-143">Authorization</span></span> | <span data-ttu-id="3cbec-144">Portatore {token} **Note: required**</span><span class="sxs-lookup"><span data-stu-id="3cbec-144">Bearer {token} **Note: required**</span></span>
<span data-ttu-id="3cbec-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3cbec-145">Content-Type</span></span> | <span data-ttu-id="3cbec-146">applicazione/JSON</span><span class="sxs-lookup"><span data-stu-id="3cbec-146">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="3cbec-147">Corpo della richiesta</span><span class="sxs-lookup"><span data-stu-id="3cbec-147">Request body</span></span>

<span data-ttu-id="3cbec-148">Nel corpo della richiesta fornire un oggetto JSON con i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="3cbec-148">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="3cbec-149">Parametro</span><span class="sxs-lookup"><span data-stu-id="3cbec-149">Parameter</span></span> | <span data-ttu-id="3cbec-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="3cbec-150">Type</span></span> | <span data-ttu-id="3cbec-151">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3cbec-151">Description</span></span>
-|-|-
<span data-ttu-id="3cbec-152">Query</span><span class="sxs-lookup"><span data-stu-id="3cbec-152">Query</span></span> | <span data-ttu-id="3cbec-153">Testo</span><span class="sxs-lookup"><span data-stu-id="3cbec-153">Text</span></span> | <span data-ttu-id="3cbec-154">La query da eseguire.</span><span class="sxs-lookup"><span data-stu-id="3cbec-154">The query to run.</span></span> <span data-ttu-id="3cbec-155">**Nota: obbligatoria**</span><span class="sxs-lookup"><span data-stu-id="3cbec-155">**Note: required**</span></span>

## <a name="response"></a><span data-ttu-id="3cbec-156">Risposta</span><span class="sxs-lookup"><span data-stu-id="3cbec-156">Response</span></span>

<span data-ttu-id="3cbec-157">Se l'operazione ha esito positivo, il metodo restituirà `200 OK` un oggetto _QueryResponse_ nel corpo della risposta.</span><span class="sxs-lookup"><span data-stu-id="3cbec-157">If successful, this method will return `200 OK`, and a _QueryResponse_ object in the response body.</span></span>

<span data-ttu-id="3cbec-158">L'oggetto Response contiene tre proprietà di primo livello:</span><span class="sxs-lookup"><span data-stu-id="3cbec-158">The response object contains three top-level properties:</span></span>

1. <span data-ttu-id="3cbec-159">Stats-un dizionario delle statistiche delle prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="3cbec-159">Stats - A dictionary of query performance statistics.</span></span>
2. <span data-ttu-id="3cbec-160">Schema: lo schema della risposta, un elenco di Name-Type coppie per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="3cbec-160">Schema - The schema of the response, a list of Name-Type pairs for each column.</span></span>
3. <span data-ttu-id="3cbec-161">Results-un elenco di eventi di caccia avanzati.</span><span class="sxs-lookup"><span data-stu-id="3cbec-161">Results - A list of advanced hunting events.</span></span>

## <a name="example"></a><span data-ttu-id="3cbec-162">Esempio</span><span class="sxs-lookup"><span data-stu-id="3cbec-162">Example</span></span>

<span data-ttu-id="3cbec-163">Nell'esempio seguente, un utente invia la query in basso e riceve un oggetto Response API contenente `Stats` , `Schema` e `Results` .</span><span class="sxs-lookup"><span data-stu-id="3cbec-163">In the following example, a user sends the query below and receives an API response object containing `Stats`, `Schema`, and `Results`.</span></span>

### <a name="query"></a><span data-ttu-id="3cbec-164">Query</span><span class="sxs-lookup"><span data-stu-id="3cbec-164">Query</span></span>

```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

### <a name="response-object"></a><span data-ttu-id="3cbec-165">Oggetto Response</span><span class="sxs-lookup"><span data-stu-id="3cbec-165">Response object</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="3cbec-166">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="3cbec-166">Related articles</span></span>

- [<span data-ttu-id="3cbec-167">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cbec-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="3cbec-168">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="3cbec-168">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="3cbec-169">Informazioni sui codici di errore</span><span class="sxs-lookup"><span data-stu-id="3cbec-169">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="3cbec-170">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="3cbec-170">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
