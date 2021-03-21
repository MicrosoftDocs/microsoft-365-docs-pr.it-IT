---
title: API REST hello world per Microsoft 365 Defender
description: Scopri come creare un'app e usare un token per accedere alle API di Microsoft 365 Defender
keywords: app, token, accesso, aad, app, registrazione dell'applicazione, powershell, script, amministratore globale, autorizzazione, microsoft 365 defender
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
ms.openlocfilehash: 65319d46871282c454287af225647f89e3535c78
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924339"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="90d16-104">API REST hello world per Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90d16-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="90d16-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="90d16-105">**Applies to:**</span></span>

- <span data-ttu-id="90d16-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90d16-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90d16-107">Alcune informazioni riguardano prodotti prereleased che possono essere sostanzialmente modificati prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="90d16-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="90d16-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="90d16-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="90d16-109">Ottenere eventi imprevisti usando un semplice script di PowerShell</span><span class="sxs-lookup"><span data-stu-id="90d16-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="90d16-110">Il completamento del progetto dovrebbe richiedere da 5 a 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="90d16-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="90d16-111">Questa stima del tempo include la registrazione dell'applicazione e l'applicazione del codice dallo script di esempio di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90d16-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="90d16-112">Registrare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="90d16-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="90d16-113">Accedere ad [Azure](https://portal.azure.com) come utente con il **ruolo amministratore** globale.</span><span class="sxs-lookup"><span data-stu-id="90d16-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="90d16-114">Passare ad **Azure Active Directory** App  >  **registrations** Nuova  >  **registrazione**.</span><span class="sxs-lookup"><span data-stu-id="90d16-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Immagine di Microsoft Azure e spostamento nella registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="90d16-116">Nel modulo di registrazione scegliere un nome per l'applicazione, quindi selezionare **Registra.**</span><span class="sxs-lookup"><span data-stu-id="90d16-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="90d16-117">La selezione di un URI di reindirizzamento è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="90d16-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="90d16-118">Non è necessario per completare questo esempio.</span><span class="sxs-lookup"><span data-stu-id="90d16-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="90d16-119">Nella pagina dell'applicazione seleziona **Autorizzazioni API** Aggiungi le API di autorizzazione che l'organizzazione usa >, digita  >    >   Microsoft **Threat Protection** e seleziona Microsoft **Threat Protection.**</span><span class="sxs-lookup"><span data-stu-id="90d16-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="90d16-120">La tua app ora può accedere a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="90d16-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="90d16-121">*Microsoft Threat Protection* è un ex nome di Microsoft 365 Defender e non verrà visualizzato nell'elenco originale.</span><span class="sxs-lookup"><span data-stu-id="90d16-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="90d16-122">È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="90d16-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="90d16-123">![Immagine della selezione delle autorizzazioni API](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="90d16-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="90d16-124">Scegliere **Autorizzazioni applicazione**  >  **Incident.Read.All** e selezionare Aggiungi **autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="90d16-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![Immagine dell'accesso alle API e della selezione delle API](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="90d16-126">Selezionare **Concedi il consenso dell'amministratore.**</span><span class="sxs-lookup"><span data-stu-id="90d16-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="90d16-127">Ogni volta che aggiungi un'autorizzazione, devi selezionare **Concedi** il consenso dell'amministratore per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="90d16-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Immagine delle autorizzazioni di concessione](../../media/grant-consent.PNG)

6. <span data-ttu-id="90d16-129">Aggiungere un segreto all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="90d16-129">Add a secret to the application.</span></span> <span data-ttu-id="90d16-130">Selezionare **Certificati & segreti**, aggiungere una descrizione al segreto, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="90d16-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="90d16-131">Dopo aver selezionato **Aggiungi,** selezionare **copia il valore segreto generato.**</span><span class="sxs-lookup"><span data-stu-id="90d16-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="90d16-132">Non sarà possibile recuperare il valore segreto dopo aver lasciato.</span><span class="sxs-lookup"><span data-stu-id="90d16-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Immagine della chiave di creazione dell'app](../../media/webapp-create-key2.png)

7. <span data-ttu-id="90d16-134">Registrare l'ID applicazione e l'ID tenant in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="90d16-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="90d16-135">Sono elencati in **Panoramica nella** pagina dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="90d16-135">They're listed under **Overview** on your application page.</span></span>

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="90d16-137">Ottieni un token usando l'app e usa il token per accedere all'API</span><span class="sxs-lookup"><span data-stu-id="90d16-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="90d16-138">Per altre informazioni sui token di Azure Active Directory, vedi l'esercitazione [su Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="90d16-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90d16-139">Anche se l'esempio in questa app demo ti incoraggia a incollare il valore segreto a scopo di test, non dovresti mai codificare i segreti in modo **hardcoded** in un'applicazione in esecuzione in produzione.</span><span class="sxs-lookup"><span data-stu-id="90d16-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="90d16-140">Una terza parte potrebbe usare il segreto per accedere alle risorse.</span><span class="sxs-lookup"><span data-stu-id="90d16-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="90d16-141">Puoi proteggere i segreti dell'app usando [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="90d16-141">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="90d16-142">Per un esempio pratico di come proteggere la tua app, vedi Gestire i segreti [nelle app server con Azure Key Vault.](/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="90d16-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="90d16-143">Copia lo script seguente e incollalo nell'editor di testo preferito.</span><span class="sxs-lookup"><span data-stu-id="90d16-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="90d16-144">Salva con **nomeGet-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="90d16-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="90d16-145">È anche possibile eseguire il codice così come è in PowerShell ISE, ma è consigliabile salvarlo, perché sarà necessario eseguirlo di nuovo quando si utilizza lo script di recupero degli eventi imprevisti nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="90d16-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="90d16-146">Questo script genererà un token e lo salverà nella cartella di lavoro con il nome *Latest-token.txt*.</span><span class="sxs-lookup"><span data-stu-id="90d16-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

    $resourceAppIdUri = 'https://api.security.microsoft.com'
    $oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"
    $authBody = [Ordered] @{
      resource = $resourceAppIdUri
      client_id = $clientId
      client_secret = $appSecret
      grant_type = 'client_credentials'
    }
    $authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
    $token = $authResponse.access_token
    Out-File -FilePath "./Latest-token.txt" -InputObject $token
    return $token
    ```

#### <a name="validate-the-token"></a><span data-ttu-id="90d16-147">Convalidare il token</span><span class="sxs-lookup"><span data-stu-id="90d16-147">Validate the token</span></span>

1. <span data-ttu-id="90d16-148">Copia e incolla il token ricevuto in [JWT](https://jwt.ms) per decodificarlo.</span><span class="sxs-lookup"><span data-stu-id="90d16-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="90d16-149">*JWT* è *l'acronimo di JSON Web Token*.</span><span class="sxs-lookup"><span data-stu-id="90d16-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="90d16-150">Il token decodificato conterrà un numero di elementi o attestazioni in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="90d16-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="90d16-151">Verificare che *l'attestazione dei* ruoli all'interno del token decodificato contenga le autorizzazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="90d16-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="90d16-152">Nell'immagine seguente puoi vedere un token decodificato acquisito da un'app, con ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , e ```AdvancedHunting.Read.All``` autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="90d16-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![Immagine jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="90d16-154">Ottenere un elenco di eventi imprevisti recenti</span><span class="sxs-lookup"><span data-stu-id="90d16-154">Get a list of recent incidents</span></span>

<span data-ttu-id="90d16-155">Lo script seguente **userà** Get-Token.ps1per accedere all'API.</span><span class="sxs-lookup"><span data-stu-id="90d16-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="90d16-156">Viene quindi recuperato un elenco di eventi imprevisti che sono stati aggiornati per l'ultima volta nelle ultime 48 ore e l'elenco viene salvato come file JSON.</span><span class="sxs-lookup"><span data-stu-id="90d16-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90d16-157">Salvare lo script nella stessa cartella salvata **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="90d16-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

<span data-ttu-id="90d16-158">Hai finito.</span><span class="sxs-lookup"><span data-stu-id="90d16-158">You're all done!</span></span> <span data-ttu-id="90d16-159">Hai avuto esito positivo:</span><span class="sxs-lookup"><span data-stu-id="90d16-159">You've successfully:</span></span>

- <span data-ttu-id="90d16-160">È stata creata e registrata un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="90d16-160">Created and registered an application.</span></span>
- <span data-ttu-id="90d16-161">Autorizzazione concessa all'applicazione per la lettura degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="90d16-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="90d16-162">Connesso all'API.</span><span class="sxs-lookup"><span data-stu-id="90d16-162">Connected to the API.</span></span>
- <span data-ttu-id="90d16-163">È stato usato uno script di PowerShell per restituire gli eventi imprevisti aggiornati nelle ultime 48 ore.</span><span class="sxs-lookup"><span data-stu-id="90d16-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="90d16-164">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="90d16-164">Related articles</span></span>

- [<span data-ttu-id="90d16-165">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90d16-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="90d16-166">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90d16-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="90d16-167">Creare un'app per accedere a Microsoft 365 Defender senza un utente</span><span class="sxs-lookup"><span data-stu-id="90d16-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="90d16-168">Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente</span><span class="sxs-lookup"><span data-stu-id="90d16-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="90d16-169">Creare un'app con accesso partner multi-tenant alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90d16-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="90d16-170">Gestire i segreti nelle app server con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="90d16-170">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="90d16-171">Autorizzazione OAuth 2.0 per l'accesso utente e l'accesso api</span><span class="sxs-lookup"><span data-stu-id="90d16-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)