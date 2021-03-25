---
title: Advanced Hunting with Python API Guide
ms.reviewer: ''
description: Scopri come eseguire query usando l'API di Microsoft Defender per endpoint, usando Python, con esempi.
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
ms.openlocfilehash: 78b6097ea9c3a83f35585f3b13fec4d9056ac25a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199718"
---
# <a name="advanced-hunting-using-python"></a><span data-ttu-id="23013-104">Ricerca avanzata con Python</span><span class="sxs-lookup"><span data-stu-id="23013-104">Advanced Hunting using Python</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="23013-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="23013-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="23013-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="23013-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="23013-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="23013-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="23013-108">Eseguire query avanzate con Python, vedere [Advanced Hunting API.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="23013-108">Run advanced queries using Python, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="23013-109">In questa sezione condividiamo esempi Python per recuperare un token e usarlo per eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="23013-109">In this section, we share Python samples to retrieve a token and use it to run a query.</span></span>

><span data-ttu-id="23013-110">**Prerequisito:** devi prima creare [un'app.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="23013-110">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="get-token"></a><span data-ttu-id="23013-111">Get token</span><span class="sxs-lookup"><span data-stu-id="23013-111">Get token</span></span>

- <span data-ttu-id="23013-112">Eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="23013-112">Run the following commands:</span></span>

```

import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.microsoftonline.com/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]

```

<span data-ttu-id="23013-113">dove</span><span class="sxs-lookup"><span data-stu-id="23013-113">where</span></span>
- <span data-ttu-id="23013-114">tenantId: ID del tenant per conto del quale si desidera eseguire la query ( ovvero, la query verrà eseguita sui dati di questo tenant)</span><span class="sxs-lookup"><span data-stu-id="23013-114">tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="23013-115">appId: ID dell'app Azure AD (l'app deve disporre dell'autorizzazione "Esegui query avanzate" per Microsoft Defender per Endpoint)</span><span class="sxs-lookup"><span data-stu-id="23013-115">appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Microsoft Defender for Endpoint)</span></span>
- <span data-ttu-id="23013-116">appSecret: segreto dell'app Azure AD</span><span class="sxs-lookup"><span data-stu-id="23013-116">appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="23013-117">Eseguire query</span><span class="sxs-lookup"><span data-stu-id="23013-117">Run query</span></span>

 <span data-ttu-id="23013-118">Eseguire la query seguente:</span><span class="sxs-lookup"><span data-stu-id="23013-118">Run the following query:</span></span>

```
query = 'RegistryEvents | limit 10' # Paste your own query here

url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
headers = { 
    'Content-Type' : 'application/json',
    'Accept' : 'application/json',
    'Authorization' : "Bearer " + aadToken
}

data = json.dumps({ 'Query' : query }).encode("utf-8")

req = urllib.request.Request(url, data, headers)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
schema = jsonResponse["Schema"]
results = jsonResponse["Results"]

```

- <span data-ttu-id="23013-119">schema contiene lo schema dei risultati della query</span><span class="sxs-lookup"><span data-stu-id="23013-119">schema contains the schema of the results of your query</span></span>
- <span data-ttu-id="23013-120">i risultati contengono i risultati della query</span><span class="sxs-lookup"><span data-stu-id="23013-120">results contain the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="23013-121">Query complesse</span><span class="sxs-lookup"><span data-stu-id="23013-121">Complex queries</span></span>

<span data-ttu-id="23013-122">Se si desidera eseguire query complesse (o query su più righe), salvare la query in un file e, anziché la prima riga dell'esempio precedente, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="23013-122">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a><span data-ttu-id="23013-123">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="23013-123">Work with query results</span></span>

<span data-ttu-id="23013-124">È ora possibile utilizzare i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="23013-124">You can now use the query results.</span></span>

<span data-ttu-id="23013-125">Per eseguire un'iterazione sui risultati, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="23013-125">To iterate over the results do the below:</span></span>

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


<span data-ttu-id="23013-126">Per eseguire l'output dei risultati della query in formato CSV in formato file file1.csv eseguire le seguenti operazione:</span><span class="sxs-lookup"><span data-stu-id="23013-126">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

<span data-ttu-id="23013-127">Per eseguire l'output dei risultati della query in formato JSON in file1.jsfile, eseguire le seguenti operazione:</span><span class="sxs-lookup"><span data-stu-id="23013-127">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a><span data-ttu-id="23013-128">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="23013-128">Related topic</span></span>
- [<span data-ttu-id="23013-129">API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="23013-129">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="23013-130">Rilevazione avanzata API</span><span class="sxs-lookup"><span data-stu-id="23013-130">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="23013-131">Ricerca avanzata tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="23013-131">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
