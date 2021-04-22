---
title: Hello World for Microsoft Defender for Endpoint API
ms.reviewer: ''
description: Crea una chiamata API di tipo "Hello world" pratica all'API di Microsoft Defender per endpoint.
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
ms.openlocfilehash: f4571607181fc96d87934ff60801643f5969e7e9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929252"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a><span data-ttu-id="0ed9b-104">API di Microsoft Defender per endpoint - Hello World</span><span class="sxs-lookup"><span data-stu-id="0ed9b-104">Microsoft Defender for Endpoint API - Hello World</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0ed9b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0ed9b-105">**Applies to:**</span></span> 
- [<span data-ttu-id="0ed9b-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0ed9b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)


- <span data-ttu-id="0ed9b-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0ed9b-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0ed9b-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a><span data-ttu-id="0ed9b-109">Ottenere avvisi con un semplice script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="0ed9b-109">Get Alerts using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="0ed9b-110">Quanto tempo è necessario per eseguire questo esempio?</span><span class="sxs-lookup"><span data-stu-id="0ed9b-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="0ed9b-111">L'operazione richiede solo 5 minuti in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="0ed9b-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="0ed9b-112">Registrazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0ed9b-112">Application registration</span></span>
- <span data-ttu-id="0ed9b-113">Esempi di utilizzo: richiede solo copia/incolla di uno script di PowerShell breve</span><span class="sxs-lookup"><span data-stu-id="0ed9b-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="0ed9b-114">È necessaria un'autorizzazione per connettersi?</span><span class="sxs-lookup"><span data-stu-id="0ed9b-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="0ed9b-115">Per la fase di registrazione dell'applicazione, è necessario disporre di un **ruolo di** amministratore globale nel tenant di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="0ed9b-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="0ed9b-116">Passaggio 1 - Creare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0ed9b-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="0ed9b-117">Accedere ad [Azure con](https://portal.azure.com) l'utente **amministratore** globale.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="0ed9b-118">Passare ad **Azure Active Directory** App  >  **registrations** Nuova  >  **registrazione**.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Immagine di Microsoft Azure e spostamento nella registrazione dell'applicazione](images/atp-azure-new-app2.png)

3. <span data-ttu-id="0ed9b-120">Nel modulo di registrazione scegliere un nome per l'applicazione e quindi fare clic su **Registra.**</span><span class="sxs-lookup"><span data-stu-id="0ed9b-120">In the registration form, choose a name for your application and then click **Register**.</span></span>

4. <span data-ttu-id="0ed9b-121">Consenti all'applicazione di accedere a Defender per Endpoint e assegnarle **l'autorizzazione "Leggi tutti gli avvisi":**</span><span class="sxs-lookup"><span data-stu-id="0ed9b-121">Allow your Application to access Defender for Endpoint and assign it **'Read all alerts'** permission:</span></span>

   - <span data-ttu-id="0ed9b-122">Nella pagina dell'applicazione fai clic su **Autorizzazioni API** Aggiungi API di autorizzazione che l'organizzazione usa > digitare  >    >   **WindowsDefenderATP** e fare clic su **WindowsDefenderATP.**</span><span class="sxs-lookup"><span data-stu-id="0ed9b-122">On your application page, click **API Permissions** > **Add permission** > **APIs my organization uses** > type **WindowsDefenderATP** and click on **WindowsDefenderATP**.</span></span>

   - <span data-ttu-id="0ed9b-123">**Nota:** WindowsDefenderATP non viene visualizzato nell'elenco originale.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-123">**Note**: WindowsDefenderATP does not appear in the original list.</span></span> <span data-ttu-id="0ed9b-124">È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![Immagine dell'accesso alle API e della selezione delle API1](images/add-permission.png)

   - <span data-ttu-id="0ed9b-126">Choose **Application permissions**  >  **Alert.Read.All >** Click on Add **permissions**</span><span class="sxs-lookup"><span data-stu-id="0ed9b-126">Choose **Application permissions** > **Alert.Read.All** > Click on **Add permissions**</span></span>

   ![Immagine dell'accesso alle API e della selezione delle API2](images/application-permissions.png)

   <span data-ttu-id="0ed9b-128">**Nota importante:** è necessario selezionare le autorizzazioni pertinenti.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-128">**Important note**: You need to select the relevant permissions.</span></span> <span data-ttu-id="0ed9b-129">"Leggi tutti gli avvisi" è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-129">'Read All Alerts' is only an example!</span></span>

     <span data-ttu-id="0ed9b-130">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="0ed9b-130">For instance,</span></span>

     - <span data-ttu-id="0ed9b-131">Per [eseguire query avanzate,](run-advanced-query-api.md)selezionare l'autorizzazione "Esegui query avanzate"</span><span class="sxs-lookup"><span data-stu-id="0ed9b-131">To [run advanced queries](run-advanced-query-api.md), select 'Run advanced queries' permission</span></span>
     - <span data-ttu-id="0ed9b-132">Per [isolare un computer,](isolate-machine.md)selezionare l'autorizzazione "Isola computer"</span><span class="sxs-lookup"><span data-stu-id="0ed9b-132">To [isolate a machine](isolate-machine.md), select 'Isolate machine' permission</span></span>
     - <span data-ttu-id="0ed9b-133">Per determinare l'autorizzazione necessaria, consulta la **sezione Autorizzazioni** nell'API che vuoi chiamare.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="0ed9b-134">Fai clic **su Concedi consenso**</span><span class="sxs-lookup"><span data-stu-id="0ed9b-134">Click **Grant consent**</span></span>

    - <span data-ttu-id="0ed9b-135">**Nota:** ogni volta che aggiungi l'autorizzazione, devi fare clic su **Concedi il** consenso perché la nuova autorizzazione sia effettiva.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-135">**Note**: Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

    ![Immagine delle autorizzazioni di concessione](images/grant-consent.png)

6. <span data-ttu-id="0ed9b-137">Aggiungere un segreto all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-137">Add a secret to the application.</span></span>

    - <span data-ttu-id="0ed9b-138">Fare **clic su & segreti,** aggiungere una descrizione al segreto e fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="0ed9b-138">Click **Certificates & secrets**, add description to the secret and click **Add**.</span></span>

    <span data-ttu-id="0ed9b-139">**Importante:** dopo aver fatto clic su Aggiungi, **copia il valore segreto generato.**</span><span class="sxs-lookup"><span data-stu-id="0ed9b-139">**Important**: After click Add, **copy the generated secret value**.</span></span> <span data-ttu-id="0ed9b-140">Non sarà possibile recuperare dopo aver lasciato!</span><span class="sxs-lookup"><span data-stu-id="0ed9b-140">You won't be able to retrieve after you leave!</span></span>

    ![Immagine della chiave di creazione dell'app](images/webapp-create-key2.png)

7. <span data-ttu-id="0ed9b-142">Annota l'ID applicazione e l'ID tenant:</span><span class="sxs-lookup"><span data-stu-id="0ed9b-142">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="0ed9b-143">Nella pagina dell'applicazione passare a **Panoramica** e copiare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="0ed9b-143">On your application page, go to **Overview** and copy the following:</span></span>

   ![Immagine dell'ID app creato](images/app-and-tenant-ids.png)


<span data-ttu-id="0ed9b-145">Fatto!</span><span class="sxs-lookup"><span data-stu-id="0ed9b-145">Done!</span></span> <span data-ttu-id="0ed9b-146">L'applicazione è stata registrata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-146">You have successfully registered an application!</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="0ed9b-147">Passaggio 2: ottenere un token usando l'app e usare questo token per accedere all'API.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-147">Step 2 - Get a token using the App and use this token to access the API.</span></span>

-   <span data-ttu-id="0ed9b-148">Copiare lo script seguente in PowerShell ISE o in un editor di testo e salvarlo come "**Get-Token.ps1**"</span><span class="sxs-lookup"><span data-stu-id="0ed9b-148">Copy the script below to PowerShell ISE or to a text editor, and save it as "**Get-Token.ps1**"</span></span>
-   <span data-ttu-id="0ed9b-149">L'esecuzione di questo script genererà un token e lo salverà nella cartella di lavoro con il nome "**Latest-token.txt**".</span><span class="sxs-lookup"><span data-stu-id="0ed9b-149">Running this script will generate a token and will save it in the working folder under the name "**Latest-token.txt**".</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

-   <span data-ttu-id="0ed9b-150">Controllo di sanità mentale:</span><span class="sxs-lookup"><span data-stu-id="0ed9b-150">Sanity Check:</span></span><br>
<span data-ttu-id="0ed9b-151">Eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-151">Run the script.</span></span><br>
<span data-ttu-id="0ed9b-152">Nel browser passare a: https://jwt.ms/</span><span class="sxs-lookup"><span data-stu-id="0ed9b-152">In your browser go to: https://jwt.ms/</span></span> <br>
<span data-ttu-id="0ed9b-153">Copia il token (il contenuto del file Latest-token.txt file).</span><span class="sxs-lookup"><span data-stu-id="0ed9b-153">Copy the token (the content of the Latest-token.txt file).</span></span><br>
<span data-ttu-id="0ed9b-154">Incolla nella casella superiore.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-154">Paste in the top box.</span></span><br>
<span data-ttu-id="0ed9b-155">Cercare la sezione "ruoli".</span><span class="sxs-lookup"><span data-stu-id="0ed9b-155">Look for the "roles" section.</span></span> <span data-ttu-id="0ed9b-156">Individuare il ruolo Alert.Read.All.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-156">Find the Alert.Read.All role.</span></span>

![Immagine jwt.ms](images/api-jwt-ms.png)

### <a name="lets-get-the-alerts"></a><span data-ttu-id="0ed9b-158">Consente di ottenere gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-158">Lets get the Alerts!</span></span>

-   <span data-ttu-id="0ed9b-159">Lo script seguente **userà** Get-Token.ps1per accedere all'API e riceverà gli avvisi delle ultime 48 ore.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-159">The script below will use **Get-Token.ps1** to access the API and will get the past 48 hours Alerts.</span></span>
-   <span data-ttu-id="0ed9b-160">Salvare lo script nella stessa cartella in cui è stato salvato lo script **precedenteGet-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-160">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span> 
-   <span data-ttu-id="0ed9b-161">Lo script crea due file (json e csv) con i dati nella stessa cartella degli script.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-161">The script creates two files (json and csv) with the data in the same folder as the scripts.</span></span>

```
# Returns Alerts created in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Alert from the last 48 hours. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")       

# The URL contains the type of query and the time filter we create above
# Read more about other query options and filters at   Https://TBD- add the documentation link
$url = "https://api.securitycenter.microsoft.com/api/alerts?`$filter=alertCreationTime ge $dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the alerts from the results. 
$alerts =  ($response | ConvertFrom-Json).value | ConvertTo-Json

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json and as csv
$outputJsonPath = "./Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "./Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
($alerts | ConvertFrom-Json) | Export-CSV $outputCsvPath -NoTypeInformation 
```

<span data-ttu-id="0ed9b-162">Hai finito.</span><span class="sxs-lookup"><span data-stu-id="0ed9b-162">You’re all done!</span></span> <span data-ttu-id="0ed9b-163">Hai appena avuto successo:</span><span class="sxs-lookup"><span data-stu-id="0ed9b-163">You have just successfully:</span></span>
-   <span data-ttu-id="0ed9b-164">Creato e registrato e applicazione</span><span class="sxs-lookup"><span data-stu-id="0ed9b-164">Created and registered and application</span></span>
-   <span data-ttu-id="0ed9b-165">Autorizzazione concessa per l'applicazione per la lettura degli avvisi</span><span class="sxs-lookup"><span data-stu-id="0ed9b-165">Granted permission for that application to read alerts</span></span>
-   <span data-ttu-id="0ed9b-166">Connesso l'API</span><span class="sxs-lookup"><span data-stu-id="0ed9b-166">Connected the API</span></span>
-   <span data-ttu-id="0ed9b-167">È stato usato uno script di PowerShell per restituire gli avvisi creati nelle ultime 48 ore</span><span class="sxs-lookup"><span data-stu-id="0ed9b-167">Used a PowerShell script to return alerts created in the past 48 hours</span></span>



## <a name="related-topic"></a><span data-ttu-id="0ed9b-168">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="0ed9b-168">Related topic</span></span>
- [<span data-ttu-id="0ed9b-169">API di Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0ed9b-169">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="0ed9b-170">Accedere a Microsoft Defender for Endpoint con il contesto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="0ed9b-170">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="0ed9b-171">Accedere a Microsoft Defender per Endpoint con contesto utente</span><span class="sxs-lookup"><span data-stu-id="0ed9b-171">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
