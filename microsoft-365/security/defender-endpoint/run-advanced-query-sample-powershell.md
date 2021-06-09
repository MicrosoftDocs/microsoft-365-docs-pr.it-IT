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
ms.openlocfilehash: 0d44f59f69c590ecd8d61207de8784af3e32197d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844887"
---
# <a name="advanced-hunting-using-powershell"></a>Rilevazione avanzata con PowerShell

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Eseguire query avanzate con PowerShell, vedere [Advanced Hunting API.](run-advanced-query-api.md)

In questa sezione condividiamo esempi di PowerShell per recuperare un token e usarlo per eseguire una query.

## <a name="before-you-begin"></a>Prima di iniziare
Devi prima creare [un'app](apis-intro.md).

## <a name="preparation-instructions"></a>Istruzioni per la preparazione

- Aprire una finestra di PowerShell.
- Se i criteri non consentono di eseguire i comandi di PowerShell, è possibile eseguire il comando seguente:
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

>Per altre informazioni, vedi la [documentazione di PowerShell](/powershell/module/microsoft.powershell.security/set-executionpolicy)

## <a name="get-token"></a>Get token

- Eseguire il comando seguente:

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

dove
- $tenantId: ID del tenant per conto del quale si desidera eseguire la query ( ovvero, la query verrà eseguita sui dati di questo tenant)
- $appId: ID dell'app Azure AD (l'app deve disporre dell'autorizzazione "Esegui query avanzate" per Defender per Endpoint)
- $appSecret: Segreto dell'app Azure AD

## <a name="run-query"></a>Eseguire query

Eseguire la query seguente:

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

- $results i risultati della query
- $schema contiene lo schema dei risultati della query

### <a name="complex-queries"></a>Query complesse

Se si desidera eseguire query complesse (o query su più righe), salvare la query in un file e, anziché la prima riga dell'esempio precedente, eseguire il comando seguente:

```
$query = [IO.File]::ReadAllText("C:\myQuery.txt"); # Replace with the path to your file
```

## <a name="work-with-query-results"></a>Usare i risultati delle query

È ora possibile utilizzare i risultati della query.

Per eseguire l'output dei risultati della query in formato CSV in formato file file1.csv eseguire le seguenti operazione:

```
$results | ConvertTo-Csv -NoTypeInformation | Set-Content file1.csv
```

Per eseguire l'output dei risultati della query in formato JSON in file1.jsfile, eseguire le seguenti operazione:

```
$results | ConvertTo-Json | Set-Content file1.json
```


## <a name="related-topic"></a>Argomento correlato
- [API di Microsoft Defender per endpoint](apis-intro.md)
- [Rilevazione avanzata API](run-advanced-query-api.md)
- [Rilevazione avanzata con Python](run-advanced-query-sample-python.md)
