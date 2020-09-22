---
title: Creare un'app per accedere a Microsoft Threat Protection senza un utente
description: Informazioni su come creare un'app per accedere a Microsoft Threat Protection senza un utente
keywords: app, Access, API, creare
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
ms.openlocfilehash: 57ba0eb77ccb855cc0c0224b5321f11809e21ae8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201420"
---
# <a name="create-an-app-to-access-microsoft-threat-protection-without-a-user"></a><span data-ttu-id="8f331-104">Creare un'app per accedere a Microsoft Threat Protection senza un utente</span><span class="sxs-lookup"><span data-stu-id="8f331-104">Create an app to access Microsoft Threat Protection without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8f331-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="8f331-105">**Applies to:**</span></span>
- <span data-ttu-id="8f331-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8f331-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="8f331-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="8f331-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8f331-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="8f331-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8f331-109">In questa pagina viene descritto come creare un'applicazione per ottenere l'accesso programmatico a Microsoft Threat Protection senza un utente.</span><span class="sxs-lookup"><span data-stu-id="8f331-109">This page describes how to create an application to get programmatic access to Microsoft Threat Protection without a user.</span></span> <span data-ttu-id="8f331-110">Se è necessario l'accesso a livello di programmazione a Microsoft Threat Protection per conto di un utente, vedere [Get Access with user context](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="8f331-110">If you need programmatic access to Microsoft Threat Protection on behalf of a user, see [Get access with user context](api-create-app-user-context.md).</span></span> <span data-ttu-id="8f331-111">Se non si è certi di quale accesso è necessario, vedere [Introduzione](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="8f331-111">If you are not sure which access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="8f331-112">Microsoft Threat Protection espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="8f331-112">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="8f331-113">Tali API consentono di automatizzare i flussi di lavoro e di innovare in base alle funzionalità di protezione dalle minacce di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8f331-113">Those APIs will help you automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="8f331-114">L'accesso API richiede l'autenticazione OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="8f331-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="8f331-115">Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="8f331-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="8f331-116">In generale, è necessario eseguire la procedura seguente per utilizzare le API:</span><span class="sxs-lookup"><span data-stu-id="8f331-116">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="8f331-117">Creare un'applicazione Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8f331-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="8f331-118">Ottenere un token di accesso utilizzando l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8f331-118">Get an access token using this application.</span></span>
- <span data-ttu-id="8f331-119">Utilizzare il token per accedere all'API di Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="8f331-119">Use the token to access Microsoft Threat Protection API.</span></span>

<span data-ttu-id="8f331-120">In questo articolo viene illustrato come creare un'applicazione Azure AD, ottenere un token di accesso a Microsoft Threat Protection e convalidare il token.</span><span class="sxs-lookup"><span data-stu-id="8f331-120">This article explains how to create an Azure AD application, get an access token to Microsoft Threat Protection, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="8f331-121">Creare un'app</span><span class="sxs-lookup"><span data-stu-id="8f331-121">Create an app</span></span>

1. <span data-ttu-id="8f331-122">Accedere a [Azure](https://portal.azure.com) con un utente che ha il ruolo di **amministratore globale** .</span><span class="sxs-lookup"><span data-stu-id="8f331-122">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="8f331-123">Passare a registrazione delle app di **Azure Active Directory**  >  **App registrations**  >  **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="8f331-123">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Immagine di Microsoft Azure e spostamento alla registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="8f331-125">Nel modulo di registrazione scegliere un nome per l'applicazione e quindi fare clic su **registra**.</span><span class="sxs-lookup"><span data-stu-id="8f331-125">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="8f331-126">Per consentire all'app di accedere a Microsoft Threat Protection e assegnargli le autorizzazioni, nella pagina dell'applicazione selezionare **autorizzazioni API**  >  **Aggiungi autorizzazione**API  >  **l'organizzazione utilizza** >, digitare **Microsoft Threat Protection**e quindi selezionare **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="8f331-126">To enable your app to access Microsoft Threat Protection and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and then select **Microsoft Threat Protection**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8f331-127">Microsoft Threat Protection non viene visualizzato nell'elenco originale.</span><span class="sxs-lookup"><span data-stu-id="8f331-127">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="8f331-128">È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="8f331-128">You need to start writing its name in the text box to see it appear.</span></span>

   ![Immagine dell'accesso API e della selezione dell'API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="8f331-130">Selezionare **Autorizzazioni applicazione** > scegliere le autorizzazioni rilevanti per lo scenario, ad esempio, **Incident. Read. All**, quindi selezionare **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="8f331-130">Select **Application permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read.All**, and then select **Add permissions**.</span></span>

   ![Immagine dell'accesso API e della selezione dell'API](../../media/request-api-permissions.PNG)

    >[!NOTE]
    ><span data-ttu-id="8f331-132">È necessario selezionare le autorizzazioni rilevanti per lo scenario, **' Leggi tutti gli incidenti '** è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="8f331-132">You need to select the relevant permissions for your scenario, **'Read all incidents'** is just an example.</span></span> <span data-ttu-id="8f331-133">Per determinare le autorizzazioni necessarie, consultare la sezione **autorizzazioni** nell'API che si desidera chiamare.</span><span class="sxs-lookup"><span data-stu-id="8f331-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="8f331-134">Selezionare **Concedi consenso**.</span><span class="sxs-lookup"><span data-stu-id="8f331-134">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="8f331-135">Ogni volta che si aggiunge un'autorizzazione, è necessario selezionare **Concedi consenso** per rendere effettive le nuove autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8f331-135">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![Immagine delle autorizzazioni di concessione](../../media/grant-consent.PNG)

6. <span data-ttu-id="8f331-137">Per aggiungere un segreto all'applicazione, selezionare **certificati & segreti**, aggiungere una descrizione al segreto e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8f331-137">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8f331-138">Dopo aver selezionato **Aggiungi**, selezionare **copia il valore segreto generato**.</span><span class="sxs-lookup"><span data-stu-id="8f331-138">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="8f331-139">Non sarà possibile recuperare questo valore dopo l'uscita.</span><span class="sxs-lookup"><span data-stu-id="8f331-139">You won't be able to retrieve this value after you leave.</span></span>

    ![Immagine del tasto Crea app](../../media/webapp-create-key2.png)

7. <span data-ttu-id="8f331-141">Annotare l'ID dell'applicazione e l'ID del tenant.</span><span class="sxs-lookup"><span data-stu-id="8f331-141">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="8f331-142">Nella pagina applicazione passare a **Panoramica** e copiare quanto segue.</span><span class="sxs-lookup"><span data-stu-id="8f331-142">On your application page, go to **Overview** and copy the following.</span></span>

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

8. <span data-ttu-id="8f331-144">**Solo per i partner di Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="8f331-144">**For Microsoft Threat Protection Partners only**.</span></span> <span data-ttu-id="8f331-145">[Seguire le istruzioni](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access)riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="8f331-145">[Follow the instructions here](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span></span> <span data-ttu-id="8f331-146">Impostare l'app come multi-tenanted (disponibile in tutti i tenant dopo il consenso).</span><span class="sxs-lookup"><span data-stu-id="8f331-146">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="8f331-147">Questo è **necessario** per le app di terze parti (ad esempio, se si crea un'app che deve essere eseguita in più tenant dei clienti).</span><span class="sxs-lookup"><span data-stu-id="8f331-147">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="8f331-148">Non è **necessario** se si crea un servizio che si desidera eseguire solo nel tenant (ad esempio, se si crea un'applicazione per il proprio utilizzo che interagirà solo con i propri dati).</span><span class="sxs-lookup"><span data-stu-id="8f331-148">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="8f331-149">Per impostare l'app come multi-tenant:</span><span class="sxs-lookup"><span data-stu-id="8f331-149">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="8f331-150">Andare a **autenticazione**e aggiungere https://portal.azure.com come URI di **Reindirizzamento**.</span><span class="sxs-lookup"><span data-stu-id="8f331-150">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="8f331-151">Nella parte inferiore della pagina, in **tipi di account supportati**, selezionare gli **account in qualsiasi** autorizzazione dell'applicazione directory organizzativa per l'app multi-tenant.</span><span class="sxs-lookup"><span data-stu-id="8f331-151">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="8f331-152">È necessario che l'applicazione venga approvata in ogni tenant in cui si intende utilizzarla.</span><span class="sxs-lookup"><span data-stu-id="8f331-152">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="8f331-153">Ciò è dovuto al fatto che l'applicazione interagisce sulla protezione dalle minacce Microsoft per conto del cliente.</span><span class="sxs-lookup"><span data-stu-id="8f331-153">This is because your application interacts Microsoft Threat Protection on behalf of your customer.</span></span>

    <span data-ttu-id="8f331-154">Se si sta scrivendo un'app di terze parti, l'utente o il cliente deve selezionare il collegamento di consenso e approvare l'app.</span><span class="sxs-lookup"><span data-stu-id="8f331-154">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="8f331-155">Il consenso dovrebbe essere effettuato con un utente che dispone di privilegi amministrativi in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8f331-155">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="8f331-156">Il collegamento di consenso è formato come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="8f331-156">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="8f331-157">Dove 00000000-0000-0000-0000-000000000000 viene sostituito con l'ID dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8f331-157">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="8f331-158">**Fatto!**</span><span class="sxs-lookup"><span data-stu-id="8f331-158">**Done!**</span></span> <span data-ttu-id="8f331-159">La registrazione di un'applicazione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8f331-159">You have successfully registered an application!</span></span> <span data-ttu-id="8f331-160">Vedere gli esempi riportati di seguito per l'acquisizione e la convalida dei token.</span><span class="sxs-lookup"><span data-stu-id="8f331-160">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="8f331-161">Ottenere un token di accesso</span><span class="sxs-lookup"><span data-stu-id="8f331-161">Get an access token</span></span>

<span data-ttu-id="8f331-162">Per ulteriori informazioni sui token di Azure AD, vedere l' [esercitazione di Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="8f331-162">For more details on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="8f331-163">Utilizzo di PowerShell</span><span class="sxs-lookup"><span data-stu-id="8f331-163">Use PowerShell</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

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

### <a name="use-c"></a><span data-ttu-id="8f331-164">Utilizzare C#:</span><span class="sxs-lookup"><span data-stu-id="8f331-164">Use C#:</span></span>

<span data-ttu-id="8f331-165">Il codice seguente è stato testato con NuGet Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="8f331-165">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="8f331-166">Creare una nuova applicazione console.</span><span class="sxs-lookup"><span data-stu-id="8f331-166">Create a new console application.</span></span>
1. <span data-ttu-id="8f331-167">Installare NuGet [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="8f331-167">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="8f331-168">Aggiungere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f331-168">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="8f331-169">Copiare e incollare il codice seguente nell'app (non dimenticare di aggiornare le tre variabili: ```tenantId, appId, appSecret``` ):</span><span class="sxs-lookup"><span data-stu-id="8f331-169">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a><span data-ttu-id="8f331-170">Utilizzare Python</span><span class="sxs-lookup"><span data-stu-id="8f331-170">Use Python</span></span> 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

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
### <a name="use-curl"></a><span data-ttu-id="8f331-171">Utilizzo di curl</span><span class="sxs-lookup"><span data-stu-id="8f331-171">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="8f331-172">La procedura seguente presuppone che curl per Windows sia già installato nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="8f331-172">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="8f331-173">Aprire una finestra del prompt dei comandi e impostare CLIENT_ID sull'ID dell'applicazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="8f331-173">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="8f331-174">Impostare CLIENT_SECRET per l'applicazione di Azure segreta.</span><span class="sxs-lookup"><span data-stu-id="8f331-174">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="8f331-175">Impostare TENANT_ID sull'ID tenant di Azure del cliente che desidera utilizzare l'app per accedere a Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="8f331-175">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft Threat Protection.</span></span>
1. <span data-ttu-id="8f331-176">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8f331-176">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="8f331-177">Si otterrà una risposta nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="8f331-177">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="8f331-178">Convalidare il token</span><span class="sxs-lookup"><span data-stu-id="8f331-178">Validate the token</span></span>

<span data-ttu-id="8f331-179">Assicurarsi di aver ottenuto il token corretto:</span><span class="sxs-lookup"><span data-stu-id="8f331-179">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="8f331-180">Copiare e incollare il token ottenuto nel passaggio precedente in [JWT](https://jwt.ms) per decodificarlo.</span><span class="sxs-lookup"><span data-stu-id="8f331-180">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="8f331-181">Convalidare che si ottiene un'attestazione di ' ruoli ' con le autorizzazioni desiderate</span><span class="sxs-lookup"><span data-stu-id="8f331-181">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="8f331-182">Nell'immagine seguente, è possibile visualizzare un token decodificato acquisito da un'app con ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` e ```AdvancedHunting.Read.All``` autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="8f331-182">In the following image, you can see a decoded token acquired from an app with ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Immagine della convalida dei token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a><span data-ttu-id="8f331-184">Utilizzare il token per accedere all'API di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8f331-184">Use the token to access Microsoft Threat Protection API</span></span>

1. <span data-ttu-id="8f331-185">Scegliere l'API che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="8f331-185">Choose the API you want to use.</span></span> <span data-ttu-id="8f331-186">Per ulteriori informazioni, vedere [API di Microsoft Threat Protection supportate](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="8f331-186">For more information, see [Supported Microsoft Threat Protection APIs](api-supported.md).</span></span>

2. <span data-ttu-id="8f331-187">Impostare l'intestazione di autorizzazione nella richiesta HTTP inviata a "portatore {token}" (il portatore è lo schema di autorizzazione).</span><span class="sxs-lookup"><span data-stu-id="8f331-187">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>

3. <span data-ttu-id="8f331-188">La data di scadenza del token è di un'ora.</span><span class="sxs-lookup"><span data-stu-id="8f331-188">The expiration time of the token is one hour.</span></span> <span data-ttu-id="8f331-189">È possibile inviare più di una richiesta con lo stesso token.</span><span class="sxs-lookup"><span data-stu-id="8f331-189">You can send more then one request with the same token.</span></span>

<span data-ttu-id="8f331-190">Di seguito è riportato un esempio di invio di una richiesta per ottenere un elenco di operazioni non consentite **tramite C#**:</span><span class="sxs-lookup"><span data-stu-id="8f331-190">The following is an example of sending a request to get a list of incidents **using C#**:</span></span> 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a><span data-ttu-id="8f331-191">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8f331-191">Related topics</span></span>
- [<span data-ttu-id="8f331-192">Accedere alle API di Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8f331-192">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="8f331-193">Accedere a Microsoft Threat Protection con il contesto dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8f331-193">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="8f331-194">Accedere a Microsoft Threat Protection con contesto utente</span><span class="sxs-lookup"><span data-stu-id="8f331-194">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
