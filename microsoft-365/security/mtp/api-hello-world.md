---
title: Hello World per Microsoft 365 Defender REST API
description: Informazioni su come creare un'app e utilizzare un token per accedere alle API di Microsoft 365 Defender
keywords: app, token, Access, AAD, app, registrazione applicazioni, PowerShell, script, amministratore globale, autorizzazione
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
ms.openlocfilehash: bd4f7e5485d67cf74477900ae2cc5c77f1a6ee41
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844045"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="8e8ff-104">Hello World per Microsoft 365 Defender REST API</span><span class="sxs-lookup"><span data-stu-id="8e8ff-104">Hello World for Microsoft 365 Defender REST API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8e8ff-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8e8ff-105">**Applies to:**</span></span>
- <span data-ttu-id="8e8ff-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e8ff-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="8e8ff-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8e8ff-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="8e8ff-109">Ottenere gli eventi imprevisti tramite uno script di PowerShell semplice</span><span class="sxs-lookup"><span data-stu-id="8e8ff-109">Get incidents using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="8e8ff-110">Quanto tempo è necessario per passare attraverso questo esempio?</span><span class="sxs-lookup"><span data-stu-id="8e8ff-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="8e8ff-111">Sono necessari solo 5 minuti in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="8e8ff-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="8e8ff-112">Registrazione applicazione</span><span class="sxs-lookup"><span data-stu-id="8e8ff-112">Application registration</span></span>
- <span data-ttu-id="8e8ff-113">Esempi di utilizzo: richiede solo copia/incolla di uno script di PowerShell breve</span><span class="sxs-lookup"><span data-stu-id="8e8ff-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="8e8ff-114">È necessaria un'autorizzazione per la connessione?</span><span class="sxs-lookup"><span data-stu-id="8e8ff-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="8e8ff-115">Per la fase di registrazione dell'applicazione, è necessario disporre di un ruolo di **amministratore globale** nel tenant di Azure Active Directory (Azure ad).</span><span class="sxs-lookup"><span data-stu-id="8e8ff-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="8e8ff-116">Passaggio 1: creare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8e8ff-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="8e8ff-117">Accedere a [Azure](https://portal.azure.com) con l'utente **amministratore globale** .</span><span class="sxs-lookup"><span data-stu-id="8e8ff-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="8e8ff-118">Passare a registrazione delle app di **Azure Active Directory**  >  **App registrations**  >  **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Immagine di Microsoft Azure e spostamento alla registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="8e8ff-120">Nel modulo di registrazione scegliere un nome per l'applicazione e quindi fare clic su **registra**.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-120">In the registration form, choose a name for your application and then select **Register**.</span></span>

4. <span data-ttu-id="8e8ff-121">Consenti all'applicazione di accedere a Microsoft Defender per endpoint e assegnarle **Leggi tutte le autorizzazioni per gli incidenti** :</span><span class="sxs-lookup"><span data-stu-id="8e8ff-121">Allow your Application to access Microsoft Defender for Endpoint and assign it **Read all incidents** permission:</span></span>

   - <span data-ttu-id="8e8ff-122">Nella pagina dell'applicazione selezionare **autorizzazioni API**  >  **Aggiungi API di autorizzazione**  >  **l'organizzazione utilizza** > tipo **Microsoft 365 Defender** e selezionare **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-122">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **Microsoft 365 Defender** and select on **Microsoft 365 Defender**.</span></span>

   >[!NOTE]
   ><span data-ttu-id="8e8ff-123">Microsoft 365 Defender non viene visualizzato nell'elenco originale.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-123">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="8e8ff-124">È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![Immagine dell'accesso API e della selezione dell'API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="8e8ff-126">Scegliere **Application Permissions**  >  **Incident. Read. All** > selezionare su **Add Permissions**</span><span class="sxs-lookup"><span data-stu-id="8e8ff-126">Choose **Application permissions** > **Incident.Read.All** > Select on **Add permissions**</span></span>

   ![Immagine dell'accesso API e della selezione dell'API](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   ><span data-ttu-id="8e8ff-128">È necessario selezionare le autorizzazioni rilevanti.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-128">You need to select the relevant permissions.</span></span> 

     <span data-ttu-id="8e8ff-129">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="8e8ff-129">For instance,</span></span>

     - <span data-ttu-id="8e8ff-130">Per determinare le autorizzazioni necessarie, consultare la sezione **autorizzazioni** nell'API che si desidera chiamare.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-130">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="8e8ff-131">Selezionare **Concedi consenso amministratore**</span><span class="sxs-lookup"><span data-stu-id="8e8ff-131">Select **Grant admin consent**</span></span>

    - >[!NOTE]
      > <span data-ttu-id="8e8ff-132">Ogni volta che si aggiunge l'autorizzazione, è necessario selezionare su **Concedi consenso** per la nuova autorizzazione per rendere effettive le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-132">Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

    ![Immagine delle autorizzazioni di concessione](../../media/grant-consent.PNG)

6. <span data-ttu-id="8e8ff-134">Aggiungere un segreto all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-134">Add a secret to the application.</span></span>

    - <span data-ttu-id="8e8ff-135">Selezionare **certificati & segreti** , aggiungere una descrizione al segreto e selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-135">Select **Certificates & secrets** , add description to the secret and select **Add**.</span></span>

    >[!IMPORTANT]
    > <span data-ttu-id="8e8ff-136">Dopo aver selezionato **Aggiungi** , **copiare il valore segreto generato**.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-136">After selecting **Add** , **copy the generated secret value**.</span></span> <span data-ttu-id="8e8ff-137">Non sarà possibile recuperare dopo l'uscita.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-137">You won't be able to retrieve after you leave!</span></span>

    ![Immagine del tasto Crea app](../../media/webapp-create-key2.png)

7. <span data-ttu-id="8e8ff-139">Annotare l'ID dell'applicazione e l'ID tenant:</span><span class="sxs-lookup"><span data-stu-id="8e8ff-139">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="8e8ff-140">Nella pagina applicazione passare a **Panoramica** e copiare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8e8ff-140">On your application page, go to **Overview** and copy the following:</span></span>

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)


<span data-ttu-id="8e8ff-142">Fatto!</span><span class="sxs-lookup"><span data-stu-id="8e8ff-142">Done!</span></span> <span data-ttu-id="8e8ff-143">L'applicazione è stata registrata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-143">You have successfully registered an application.</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="8e8ff-144">Passaggio 2: ottenere un token utilizzando l'app e utilizzare questo token per accedere all'API.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-144">Step 2 - Get a token using the App and use this token to access the API.</span></span>

-   <span data-ttu-id="8e8ff-145">Copiare lo script riportato di seguito in PowerShell ISE o in un editor di testo e salvarlo con il nome " **Get-Token.ps1** "</span><span class="sxs-lookup"><span data-stu-id="8e8ff-145">Copy the script below to PowerShell ISE or to a text editor, and save it as " **Get-Token.ps1** "</span></span>
-   <span data-ttu-id="8e8ff-146">L'esecuzione di questo script genererà un token e lo salverà nella cartella di lavoro con il nome " **Latest-token.txt** ".</span><span class="sxs-lookup"><span data-stu-id="8e8ff-146">Running this script will generate a token and will save it in the working folder under the name " **Latest-token.txt** ".</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
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

-   <span data-ttu-id="8e8ff-147">Verifica integrità:</span><span class="sxs-lookup"><span data-stu-id="8e8ff-147">Sanity Check:</span></span><br>
<span data-ttu-id="8e8ff-148">Eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-148">Run the script.</span></span><br>
<span data-ttu-id="8e8ff-149">Nel browser Vai a: https://jwt.ms/</span><span class="sxs-lookup"><span data-stu-id="8e8ff-149">In your browser go to: https://jwt.ms/</span></span> <br>
<span data-ttu-id="8e8ff-150">Copiare il token (il contenuto del file di Latest-token.txt).</span><span class="sxs-lookup"><span data-stu-id="8e8ff-150">Copy the token (the content of the Latest-token.txt file).</span></span><br>
<span data-ttu-id="8e8ff-151">Incolla nella casella superiore.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-151">Paste in the top box.</span></span><br>
<span data-ttu-id="8e8ff-152">Cercare la sezione "Roles".</span><span class="sxs-lookup"><span data-stu-id="8e8ff-152">Look for the "roles" section.</span></span> <span data-ttu-id="8e8ff-153">Individuare il ```Incidents.Read.All``` ruolo.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-153">Find the ```Incidents.Read.All``` role.</span></span><br>
<span data-ttu-id="8e8ff-154">L'esempio riportato di seguito è costituito da un'app con ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-154">The below example is from an app that has ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions.</span></span>

![Immagine jwt.ms](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a><span data-ttu-id="8e8ff-156">Consente di ottenere gli incidenti!</span><span class="sxs-lookup"><span data-stu-id="8e8ff-156">Lets get the Incidents!</span></span>

-   <span data-ttu-id="8e8ff-157">Lo script riportato di seguito utilizzerà **Get-Token.ps1** per accedere all'API e otterrà gli eventi non consentiti per l'ultimo aggiornamento nelle ultime 48 ore.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-157">The script below will use **Get-Token.ps1** to access the API and will get the incidents last updated in past 48 hours.</span></span>
-   <span data-ttu-id="8e8ff-158">Salvare lo script nella stessa cartella in cui è stato salvato lo script precedente **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-158">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span> 
-   <span data-ttu-id="8e8ff-159">Lo script un file JSON con i dati nella stessa cartella degli script.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-159">The script a json file with the data in the same folder as the scripts.</span></span>

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

<span data-ttu-id="8e8ff-160">Tutto finito.</span><span class="sxs-lookup"><span data-stu-id="8e8ff-160">You're all done!</span></span> <span data-ttu-id="8e8ff-161">È possibile eseguire correttamente le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8e8ff-161">You have just successfully:</span></span>
-   <span data-ttu-id="8e8ff-162">Creazione e registrazione e applicazione</span><span class="sxs-lookup"><span data-stu-id="8e8ff-162">Created and registered and application</span></span>
-   <span data-ttu-id="8e8ff-163">Autorizzazione concessa per l'applicazione per la lettura degli avvisi</span><span class="sxs-lookup"><span data-stu-id="8e8ff-163">Granted permission for that application to read alerts</span></span>
-   <span data-ttu-id="8e8ff-164">Connesso l'API</span><span class="sxs-lookup"><span data-stu-id="8e8ff-164">Connected the API</span></span>
-   <span data-ttu-id="8e8ff-165">Utilizzato uno script di PowerShell per restituire gli incidenti creati nelle ultime 48 ore</span><span class="sxs-lookup"><span data-stu-id="8e8ff-165">Used a PowerShell script to return incidents created in the past 48 hours</span></span>



## <a name="related-topic"></a><span data-ttu-id="8e8ff-166">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="8e8ff-166">Related topic</span></span>
- [<span data-ttu-id="8e8ff-167">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e8ff-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="8e8ff-168">Accedere a Microsoft 365 Defender con contesto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8e8ff-168">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="8e8ff-169">Accedere a Microsoft 365 Defender con contesto utente</span><span class="sxs-lookup"><span data-stu-id="8e8ff-169">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
