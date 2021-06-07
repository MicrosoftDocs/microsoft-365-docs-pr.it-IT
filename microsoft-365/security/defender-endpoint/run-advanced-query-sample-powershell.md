---
title: Ricerca avanzata con nozioni di base sulle API di PowerShell
ms.reviewer: ''
description: Informazioni di base sull'esecuzione di query sull'API di Microsoft Defender for Endpoint tramite PowerShell.
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
ms.openlocfilehash: 9192662b8d4ed23a5903dddb555f07bf182ab17f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771502"
---
# <a name="advanced-hunting-using-powershell"></a><span data-ttu-id="14386-104">Rilevazione avanzata con PowerShell</span><span class="sxs-lookup"><span data-stu-id="14386-104">Advanced Hunting using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="14386-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="14386-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="14386-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="14386-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="14386-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="14386-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="14386-108">Eseguire query avanzate con PowerShell, vedere [Advanced Hunting API.](run-advanced-query-api.md)</span><span class="sxs-lookup"><span data-stu-id="14386-108">Run advanced queries using PowerShell, see [Advanced Hunting API](run-advanced-query-api.md).</span></span>

<span data-ttu-id="14386-109">In questa sezione condividiamo esempi di PowerShell per recuperare un token e usarlo per eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="14386-109">In this section, we share PowerShell samples to retrieve a token and use it to run a query.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="14386-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="14386-110">Before you begin</span></span>
<span data-ttu-id="14386-111">Devi prima creare [un'app](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="14386-111">You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="14386-112">Istruzioni per la preparazione</span><span class="sxs-lookup"><span data-stu-id="14386-112">Preparation instructions</span></span>

- <span data-ttu-id="14386-113">Aprire una finestra di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="14386-113">Open a PowerShell window.</span></span>
- <span data-ttu-id="14386-114">Se i criteri non consentono di eseguire i comandi di PowerShell, è possibile eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="14386-114">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

><span data-ttu-id="14386-115">Per altre informazioni, vedi la [documentazione di PowerShell](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="14386-115">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="14386-116">Get token</span><span class="sxs-lookup"><span data-stu-id="14386-116">Get token</span></span>

- <span data-ttu-id="14386-117">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="14386-117">Run the following:</span></span>

```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$body = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$response = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $body -ErrorAction Stop
$aadToken = $response.access_token
```

<span data-ttu-id="14386-118">dove</span><span class="sxs-lookup"><span data-stu-id="14386-118">where</span></span>
- <span data-ttu-id="14386-119">$tenantId: ID del tenant per conto del quale si desidera eseguire la query ( ovvero, la query verrà eseguita sui dati di questo tenant)</span><span class="sxs-lookup"><span data-stu-id="14386-119">$tenantId: ID of the tenant on behalf of which you want to run the query (that is, the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="14386-120">$appId: ID dell'app Azure AD (l'app deve disporre dell'autorizzazione "Esegui query avanzate" per Defender per Endpoint)</span><span class="sxs-lookup"><span data-stu-id="14386-120">$appId: ID of your Azure AD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="14386-121">$appSecret: Segreto dell'app Azure AD</span><span class="sxs-lookup"><span data-stu-id="14386-121">$appSecret: Secret of your Azure AD app</span></span>

## <a name="run-query"></a><span data-ttu-id="14386-122">Eseguire query</span><span class="sxs-lookup"><span data-stu-id="14386-122">Run query</span></span>

<span data-ttu-id="14386-123">Eseguire la query seguente:</span><span class="sxs-lookup"><span data-stu-id="14386-123">Run the following query:</span></span>

```
$query = 'RegistryEvents | limit 10' # Paste your own query here

$url = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$body = ConvertTo-Json -InputObject @{ 'Query' = $query }
$webResponse = Invoke-WebRequest -Method Post -Uri $url -Headers $headers -Body $body -ErrorAction Stop
$response =  $webResponse | ConvertFrom-Json
$results = $response.Results
$schema = $response.Schema
```

- <span data-ttu-id="14386-124">$results i risultati della query</span><span class="sxs-lookup"><span data-stu-id="14386-124">$results contain the results of your query</span></span>
- <span data-ttu-id="14386-125">$schema contiene lo schema dei risultati della query</span><span class="sxs-lookup"><span data-stu-id="14386-125">$schema contains the schema of the results of your query</span></span>

### <a name="complex-queries"></a><span data-ttu-id="14386-126">Query complesse</span><span class="sxs-lookup"><span data-stu-id="14386-126">Complex queries</span></span>

<span data-ttu-id="14386-127">Se si desidera eseguire query complesse (o query su più righe), salvare la query in un file e, anziché la prima riga dell'esempio precedente, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="14386-127">If you want to run complex queries (or multilines queries), save your query in a file and, instead of the first line in the above sample, run the below command:</span></span>

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a><span data-ttu-id="14386-128">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="14386-128">Work with query results</span></span>

<span data-ttu-id="14386-129">È ora possibile utilizzare i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="14386-129">You can now use the query results.</span></span>

<span data-ttu-id="14386-130">Per eseguire l'output dei risultati della query in formato CSV in formato file file1.csv eseguire le seguenti operazione:</span><span class="sxs-lookup"><span data-stu-id="14386-130">To output the results of the query in CSV format in file file1.csv do the below:</span></span>

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

<span data-ttu-id="14386-131">Per eseguire l'output dei risultati della query in formato JSON in file1.jsfile, eseguire le seguenti operazione:</span><span class="sxs-lookup"><span data-stu-id="14386-131">To output the results of the query in JSON format in file file1.json do the below:</span></span>

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a><span data-ttu-id="14386-132">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="14386-132">Related topic</span></span>
- [<span data-ttu-id="14386-133">API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="14386-133">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="14386-134">Rilevazione avanzata API</span><span class="sxs-lookup"><span data-stu-id="14386-134">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="14386-135">Rilevazione avanzata con Python</span><span class="sxs-lookup"><span data-stu-id="14386-135">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
