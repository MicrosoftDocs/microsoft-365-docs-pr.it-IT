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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 17ad28121935adfc958629f7999311c11a8d784e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771446"
---
# <a name="advanced-hunting-using-python"></a>Rilevazione avanzata con Python

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Eseguire query avanzate con Python, vedere [Advanced Hunting API.](run-advanced-query-api.md)

In questa sezione condividiamo esempi Python per recuperare un token e usarlo per eseguire una query.

>**Prerequisito:** devi prima creare [un'app.](apis-intro.md)

## <a name="get-token"></a>Get token

- Eseguire i comandi seguenti:

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

dove
- tenantId: ID del tenant per conto del quale si desidera eseguire la query ( ovvero, la query verrà eseguita sui dati di questo tenant)
- appId: ID dell'app Azure AD (l'app deve disporre dell'autorizzazione "Esegui query avanzate" per Microsoft Defender per Endpoint)
- appSecret: segreto dell'app Azure AD

## <a name="run-query"></a>Eseguire query

 Eseguire la query seguente:

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

- schema contiene lo schema dei risultati della query
- i risultati contengono i risultati della query

### <a name="complex-queries"></a>Query complesse

Se si desidera eseguire query complesse (o query su più righe), salvare la query in un file e, anziché la prima riga dell'esempio precedente, eseguire il comando seguente:

```
queryFile = open("D:\\Temp\\myQuery.txt", 'r') # Replace with the path to your file
query = queryFile.read()
queryFile.close()
```

## <a name="work-with-query-results"></a>Usare i risultati delle query

È ora possibile utilizzare i risultati della query.

Per eseguire un'iterazione sui risultati, procedere come segue:

```
for result in results:
    print(result) # Prints the whole result
    print(result["EventTime"]) # Prints only the property 'EventTime' from the result


```


Per eseguire l'output dei risultati della query in formato CSV in formato file file1.csv eseguire le seguenti operazione:

```
import csv

outputFile = open("D:\\Temp\\file1.csv", 'w')
output = csv.writer(outputFile)
output.writerow(results[0].keys())
for result in results:
    output.writerow(result.values())

outputFile.close()
```

Per eseguire l'output dei risultati della query in formato JSON in file1.jsfile, eseguire le seguenti operazione:

```
outputFile = open("D:\\Temp\\file1.json", 'w')
json.dump(results, outputFile)
outputFile.close()
```


## <a name="related-topic"></a>Argomento correlato
- [API di Microsoft Defender per endpoint](apis-intro.md)
- [Rilevazione avanzata API](run-advanced-query-api.md)
- [Rilevazione avanzata con PowerShell](run-advanced-query-sample-powershell.md)
