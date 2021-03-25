---
title: Advanced Hunting with PowerShell API Guide
ms.reviewer: ''
description: Usa questi esempi di codice per eseguire query su diverse API di Microsoft Defender for Endpoint.
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
ms.date: 09/24/2018
ms.technology: mde
ms.openlocfilehash: 9913d1b0b0d5d0462fdee0b9c576a590bd3ddbc9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198325"
---
# <a name="microsoft-defender-for-endpoint-apis-using-powershell"></a><span data-ttu-id="d47c8-104">API di Microsoft Defender per endpoint con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d47c8-104">Microsoft Defender for Endpoint APIs using PowerShell</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d47c8-105">**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="d47c8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="d47c8-106">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d47c8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d47c8-107">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d47c8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

><span data-ttu-id="d47c8-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d47c8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d47c8-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d47c8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="d47c8-110">Scenario completo con più API di Microsoft Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d47c8-110">Full scenario using multiple APIs from Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="d47c8-111">In questa sezione condividiamo gli esempi di PowerShell per</span><span class="sxs-lookup"><span data-stu-id="d47c8-111">In this section, we share PowerShell samples to</span></span> 
- <span data-ttu-id="d47c8-112">Recuperare un token</span><span class="sxs-lookup"><span data-stu-id="d47c8-112">Retrieve a token</span></span> 
- <span data-ttu-id="d47c8-113">Usare il token per recuperare gli avvisi più recenti in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d47c8-113">Use token to retrieve the latest alerts in Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="d47c8-114">Per ogni avviso, se l'avviso ha priorità media o alta ed è ancora in corso, controlla quante volte il dispositivo si è connesso a UN URL sospetto.</span><span class="sxs-lookup"><span data-stu-id="d47c8-114">For each alert, if the alert has medium or high priority and is still in progress, check how many times the device has connected to suspicious URL.</span></span>

<span data-ttu-id="d47c8-115">**Prerequisito:** devi prima creare [un'app.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d47c8-115">**Prerequisite**: You first need to [create an app](apis-intro.md).</span></span>

## <a name="preparation-instructions"></a><span data-ttu-id="d47c8-116">Istruzioni per la preparazione</span><span class="sxs-lookup"><span data-stu-id="d47c8-116">Preparation instructions</span></span>

- <span data-ttu-id="d47c8-117">Aprire una finestra di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d47c8-117">Open a PowerShell window.</span></span>
- <span data-ttu-id="d47c8-118">Se i criteri non consentono di eseguire i comandi di PowerShell, è possibile eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d47c8-118">If your policy does not allow you to run the PowerShell commands, you can run the below command:</span></span>
  ```
  Set-ExecutionPolicy -ExecutionPolicy Bypass
  ```

<span data-ttu-id="d47c8-119">Per altre informazioni, vedi la [documentazione di PowerShell](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span><span class="sxs-lookup"><span data-stu-id="d47c8-119">For more information, see [PowerShell documentation](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

## <a name="get-token"></a><span data-ttu-id="d47c8-120">Get token</span><span class="sxs-lookup"><span data-stu-id="d47c8-120">Get token</span></span>

<span data-ttu-id="d47c8-121">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d47c8-121">Run the below:</span></span>

- <span data-ttu-id="d47c8-122">$tenantId: ID del tenant per conto del quale si desidera eseguire la query (ad esempio, la query verrà eseguita sui dati di questo tenant)</span><span class="sxs-lookup"><span data-stu-id="d47c8-122">$tenantId: ID of the tenant on behalf of which you want to run the query (i.e., the query will be run on the data of this tenant)</span></span>
- <span data-ttu-id="d47c8-123">$appId: ID della tua app AAD (l'app deve disporre dell'autorizzazione "Esegui query avanzate" per Defender per Endpoint)</span><span class="sxs-lookup"><span data-stu-id="d47c8-123">$appId: ID of your AAD app (the app must have 'Run advanced queries' permission to Defender for Endpoint)</span></span>
- <span data-ttu-id="d47c8-124">$appSecret: Segreto dell'app Azure AD</span><span class="sxs-lookup"><span data-stu-id="d47c8-124">$appSecret: Secret of your Azure AD app</span></span>

- <span data-ttu-id="d47c8-125">$suspiciousUrl: l'URL</span><span class="sxs-lookup"><span data-stu-id="d47c8-125">$suspiciousUrl: The URL</span></span>


```
$tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
$appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
$appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here
$suspiciousUrl = 'www.suspiciousUrl.com' # Paste your own URL here

$resourceAppIdUri = 'https://securitycenter.onmicrosoft.com/windowsatpservice'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$aadToken = $authResponse.access_token


#Get latest alert
$alertUrl = "https://api.securitycenter.microsoft.com/api/alerts?`$top=10"
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $aadToken" 
}
$alertResponse = Invoke-WebRequest -Method Get -Uri $alertUrl -Headers $headers -ErrorAction Stop
$alerts =  ($alertResponse | ConvertFrom-Json).value

$machinesToInvestigate = New-Object System.Collections.ArrayList

Foreach($alert in $alerts)
{
    #echo $alert.id $alert.machineId    $alert.severity $alert.status

    $isSevereAlert = $alert.severity -in 'Medium', 'High'
    $isOpenAlert = $alert.status -in 'InProgress', 'New'
    if($isOpenAlert -and $isSevereAlert)
    {
        if (-not $machinesToInvestigate.Contains($alert.machineId))
        {
            $machinesToInvestigate.Add($alert.machineId) > $null
        }
    }
}

$commaSeparatedMachines = '"{0}"' -f ($machinesToInvestigate -join '","')

$query = "NetworkCommunicationEvents
| where MachineId in ($commaSeparatedMachines)
| where RemoteUrl  == `"$suspiciousUrl`"
| summarize ConnectionsCount = count() by MachineId"

$queryUrl = "https://api.securitycenter.microsoft.com/api/advancedqueries/run"

$queryBody = ConvertTo-Json -InputObject @{ 'Query' = $query }
$queryResponse = Invoke-WebRequest -Method Post -Uri $queryUrl -Headers $headers -Body $queryBody -ErrorAction Stop
$response =  ($queryResponse | ConvertFrom-Json).Results
$response
```


## <a name="see-also"></a><span data-ttu-id="d47c8-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d47c8-126">See also</span></span>
- [<span data-ttu-id="d47c8-127">API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d47c8-127">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="d47c8-128">Rilevazione avanzata API</span><span class="sxs-lookup"><span data-stu-id="d47c8-128">Advanced Hunting API</span></span>](run-advanced-query-api.md)
- [<span data-ttu-id="d47c8-129">Ricerca avanzata con Python</span><span class="sxs-lookup"><span data-stu-id="d47c8-129">Advanced Hunting using Python</span></span>](run-advanced-query-sample-python.md)
