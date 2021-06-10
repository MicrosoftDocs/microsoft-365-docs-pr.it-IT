---
title: Creare un'app per accedere Microsoft 365 Defender senza un utente
description: Scopri come creare un'app per accedere Microsoft 365 Defender senza un utente.
keywords: app, accesso, api, creare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8ffa04492f42f7e1ee5f3fc7fadad963e6bb7fbe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066757"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="37836-104">Creare un'app per accedere Microsoft 365 Defender senza un utente</span><span class="sxs-lookup"><span data-stu-id="37836-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="37836-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="37836-105">**Applies to:**</span></span>

- <span data-ttu-id="37836-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37836-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37836-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="37836-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="37836-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="37836-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="37836-109">Questa pagina descrive come creare un'applicazione per ottenere l'accesso a livello di codice a Microsoft 365 Defender senza un utente definito, ad esempio se stai creando un daemon o un servizio in background.</span><span class="sxs-lookup"><span data-stu-id="37836-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a defined user—for example, if you're creating a daemon or background service.</span></span>

<span data-ttu-id="37836-110">Se hai bisogno dell'accesso a livello di codice a Microsoft 365 Defender per conto di uno o più utenti, vedi Creare [un'app](api-create-app-user-context.md) per accedere alle API di Microsoft 365 Defender per conto di un utente e Creare un'app con accesso partner alle API di [Microsoft 365 Defender.](api-partner-access.md)</span><span class="sxs-lookup"><span data-stu-id="37836-110">If you need programmatic access to Microsoft 365 Defender on behalf of one or more users, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md) and [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).</span></span> <span data-ttu-id="37836-111">Se non si è certi del tipo di accesso necessario, vedere [Introduzione.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="37836-111">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="37836-112">Microsoft 365 Defender espone gran parte dei dati e delle azioni tramite un set di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="37836-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="37836-113">Queste API consentono di automatizzare i flussi di lavoro e di usare Microsoft 365 funzionalità di Defender.</span><span class="sxs-lookup"><span data-stu-id="37836-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="37836-114">L'accesso all'API richiede l'autenticazione OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="37836-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="37836-115">Per ulteriori informazioni, vedere [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="37836-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="37836-116">In generale, dovrai eseguire la procedura seguente per usare queste API:</span><span class="sxs-lookup"><span data-stu-id="37836-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="37836-117">Creare un'Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="37836-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="37836-118">Ottieni un token di accesso usando questa applicazione.</span><span class="sxs-lookup"><span data-stu-id="37836-118">Get an access token using this application.</span></span>
- <span data-ttu-id="37836-119">Usa il token per accedere Microsoft 365'API Defender.</span><span class="sxs-lookup"><span data-stu-id="37836-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="37836-120">In questo articolo viene illustrato come:</span><span class="sxs-lookup"><span data-stu-id="37836-120">This article explains how to:</span></span>

- <span data-ttu-id="37836-121">Creare un'applicazione Azure AD</span><span class="sxs-lookup"><span data-stu-id="37836-121">Create an Azure AD application</span></span>
- <span data-ttu-id="37836-122">Ottenere un token di accesso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37836-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="37836-123">Convalidare il token.</span><span class="sxs-lookup"><span data-stu-id="37836-123">Validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="37836-124">Creare un'app</span><span class="sxs-lookup"><span data-stu-id="37836-124">Create an app</span></span>

1. <span data-ttu-id="37836-125">Accedere ad [Azure](https://portal.azure.com) come utente con il **ruolo Amministratore** globale.</span><span class="sxs-lookup"><span data-stu-id="37836-125">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="37836-126">Passare **a** Azure Active Directory  >  **app Nuove**  >  **registrazioni**.</span><span class="sxs-lookup"><span data-stu-id="37836-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Immagine dell'Microsoft Azure e della navigazione per la registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="37836-128">Nel modulo scegliere un nome per l'applicazione, quindi selezionare **Registra.**</span><span class="sxs-lookup"><span data-stu-id="37836-128">In the form, choose a name for your application, then select **Register**.</span></span>

4. <span data-ttu-id="37836-129">Nella pagina dell'applicazione seleziona **Autorizzazioni API** Aggiungi API di autorizzazione che l'organizzazione usa  >    >   >, digita **Microsoft Threat Protection** e seleziona **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="37836-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="37836-130">La tua app può ora accedere Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="37836-130">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="37836-131">*Microsoft Threat Protection* è un ex nome di Microsoft 365 Defender e non verrà visualizzato nell'elenco originale.</span><span class="sxs-lookup"><span data-stu-id="37836-131">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="37836-132">È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="37836-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![Immagine della selezione delle autorizzazioni API](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="37836-134">Selezionare **Autorizzazioni applicazione**.</span><span class="sxs-lookup"><span data-stu-id="37836-134">Select **Application permissions**.</span></span> <span data-ttu-id="37836-135">Scegliere le autorizzazioni rilevanti per lo scenario, ad esempio **Incident.Read.All,** e quindi **selezionare Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="37836-135">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Immagine dell'accesso alle API e della selezione delle API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="37836-137">È necessario selezionare le autorizzazioni pertinenti per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="37836-137">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="37836-138">*Leggere tutti gli eventi imprevisti* è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="37836-138">*Read all incidents* is just an example.</span></span> <span data-ttu-id="37836-139">Per determinare l'autorizzazione necessaria, consulta la **sezione Autorizzazioni** nell'API che vuoi chiamare.</span><span class="sxs-lookup"><span data-stu-id="37836-139">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="37836-140">Ad esempio, per [eseguire query avanzate,](api-advanced-hunting.md)selezionare l'autorizzazione "Esegui query avanzate". per [isolare un dispositivo,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)seleziona l'autorizzazione "Isola computer".</span><span class="sxs-lookup"><span data-stu-id="37836-140">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="37836-141">Selezionare **Concedi il consenso dell'amministratore.**</span><span class="sxs-lookup"><span data-stu-id="37836-141">Select **Grant admin consent**.</span></span> <span data-ttu-id="37836-142">Ogni volta che aggiungi un'autorizzazione, devi selezionare **Concedi** il consenso dell'amministratore per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="37836-142">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Immagine delle autorizzazioni di concessione](../../media/grant-consent.PNG)

7. <span data-ttu-id="37836-144">Per aggiungere un segreto all'applicazione, selezionare **Certificati & segreti,** aggiungere una descrizione al segreto, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="37836-144">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="37836-145">Dopo aver selezionato **Aggiungi,** selezionare **copia il valore segreto generato.**</span><span class="sxs-lookup"><span data-stu-id="37836-145">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="37836-146">Non sarà possibile recuperare il valore segreto dopo aver lasciato.</span><span class="sxs-lookup"><span data-stu-id="37836-146">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Immagine della chiave di creazione dell'app](../../media/webapp-create-key2.png)

8. <span data-ttu-id="37836-148">Registrare l'ID applicazione e l'ID tenant in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="37836-148">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="37836-149">Sono elencati in **Panoramica nella** pagina dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="37836-149">They're listed under **Overview** on your application page.</span></span>

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="37836-151">Solo **per Microsoft 365 Defender Partners:** segui queste istruzioni per l'accesso dei partner tramite le API di Microsoft 365 Defender, imposta l'app come multi-tenant, in modo che possa essere disponibile in tutti i tenant dopo aver ricevuto il consenso dell'amministratore. [](./api-partner-access.md)</span><span class="sxs-lookup"><span data-stu-id="37836-151">**For Microsoft 365 Defender Partners only**: [Follow these instructions](./api-partner-access.md) for partner access through the Microsoft 365 Defender APIs, set your app to be multi-tenant, so it can be available in all tenants once you receive admin consent.</span></span> <span data-ttu-id="37836-152">L'accesso **ai partner è** necessario per le app di terze parti, ad esempio se crei un'app che deve essere eseguita nei tenant di più clienti.</span><span class="sxs-lookup"><span data-stu-id="37836-152">Partner access is **required** for third-party apps—for example, if you create an app that is intended to run in multiple customers' tenants.</span></span> <span data-ttu-id="37836-153">Non è **necessario se** si crea un servizio che si desidera eseguire solo nel tenant, ad esempio un'applicazione per il proprio utilizzo che interagirà solo con i propri dati.</span><span class="sxs-lookup"><span data-stu-id="37836-153">It is **not required** if you create a service that you want to run in your tenant only, such as an application for your own usage that will only interact with your own data.</span></span> <span data-ttu-id="37836-154">Per impostare l'app come multi-tenant:</span><span class="sxs-lookup"><span data-stu-id="37836-154">To set your app to be multi-tenant:</span></span>

    - <span data-ttu-id="37836-155">Vai a **Autenticazione** e aggiungi https://portal.azure.com come URI di **reindirizzamento.**</span><span class="sxs-lookup"><span data-stu-id="37836-155">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="37836-156">Nella parte inferiore della pagina, in Tipi di **account supportati,** selezionare account **in qualsiasi** consenso dell'applicazione directory dell'organizzazione per l'app multi-tenant.</span><span class="sxs-lookup"><span data-stu-id="37836-156">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="37836-157">Poiché l'applicazione interagisce con Microsoft 365 Defender per conto degli utenti, deve essere approvata per ogni tenant in cui si intende usarla.</span><span class="sxs-lookup"><span data-stu-id="37836-157">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

    <span data-ttu-id="37836-158">L'amministratore globale di Active Directory per ogni tenant deve selezionare il collegamento di consenso e approvare l'app.</span><span class="sxs-lookup"><span data-stu-id="37836-158">The Active Directory global admin for each tenant needs to select the consent link and approve your app.</span></span>

    <span data-ttu-id="37836-159">Il collegamento di consenso ha la struttura seguente:</span><span class="sxs-lookup"><span data-stu-id="37836-159">The consent link has the following structure:</span></span>

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="37836-160">Le cifre `00000000-0000-0000-0000-000000000000` devono essere sostituite con l'ID applicazione.</span><span class="sxs-lookup"><span data-stu-id="37836-160">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>  

<span data-ttu-id="37836-161">**Fatto!**</span><span class="sxs-lookup"><span data-stu-id="37836-161">**Done!**</span></span> <span data-ttu-id="37836-162">L'applicazione è stata registrata correttamente.</span><span class="sxs-lookup"><span data-stu-id="37836-162">You've successfully registered an application!</span></span> <span data-ttu-id="37836-163">Vedi gli esempi seguenti per l'acquisizione e la convalida di token.</span><span class="sxs-lookup"><span data-stu-id="37836-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="37836-164">Ottenere un token di accesso</span><span class="sxs-lookup"><span data-stu-id="37836-164">Get an access token</span></span>

<span data-ttu-id="37836-165">Per altre informazioni sui token Azure Active Directory, vedi l'esercitazione [su Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="37836-165">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37836-166">Anche se gli esempi in questa sezione incoraggiano a incollare valori segreti a scopo di test, non è consigliabile codificare mai segreti **hardcoded** in un'applicazione in esecuzione nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="37836-166">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="37836-167">Una terza parte potrebbe usare il segreto per accedere alle risorse.</span><span class="sxs-lookup"><span data-stu-id="37836-167">A third party could use your secret to access resources.</span></span> <span data-ttu-id="37836-168">Puoi proteggere i segreti dell'app usando [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="37836-168">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="37836-169">Per un esempio pratico di come proteggere la tua app, vedi Gestire i segreti [nelle app server con Azure Key Vault.](/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="37836-169">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="37836-170">Ottenere un token di accesso tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="37836-170">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="37836-171">Ottenere un token di accesso con C\#</span><span class="sxs-lookup"><span data-stu-id="37836-171">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="37836-172">Il codice seguente è stato testato con Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="37836-172">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="37836-173">Creare una nuova applicazione console.</span><span class="sxs-lookup"><span data-stu-id="37836-173">Create a new console application.</span></span>

1. <span data-ttu-id="37836-174">Installare NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="37836-174">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>

1. <span data-ttu-id="37836-175">Aggiungere la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="37836-175">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="37836-176">Copia e incolla il codice seguente nella tua app (non dimenticare di aggiornare le tre variabili: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="37836-176">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="37836-177">Ottenere un token di accesso con Python</span><span class="sxs-lookup"><span data-stu-id="37836-177">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.security.microsoft.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="37836-178">Ottenere un token di accesso con l'arricciatura</span><span class="sxs-lookup"><span data-stu-id="37836-178">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="37836-179">Curl è preinstallato in Windows 10, versioni 1803 e successive.</span><span class="sxs-lookup"><span data-stu-id="37836-179">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="37836-180">Per altre versioni di Windows, scaricare e installare lo strumento direttamente dal sito [Web ufficiale di .NET Framework.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="37836-180">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="37836-181">Aprire un prompt dei comandi e impostare CLIENT_ID'ID applicazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="37836-181">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>

1. <span data-ttu-id="37836-182">Impostare CLIENT_SECRET sul segreto dell'applicazione Azure.</span><span class="sxs-lookup"><span data-stu-id="37836-182">Set CLIENT_SECRET to your Azure application secret.</span></span>

1. <span data-ttu-id="37836-183">Imposta TENANT_ID'ID tenant di Azure del cliente che vuole usare la tua app per accedere a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="37836-183">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>

1. <span data-ttu-id="37836-184">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="37836-184">Run the following command:</span></span>

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   <span data-ttu-id="37836-185">Una risposta corretta sarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="37836-185">A successful response will look like this:</span></span>

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a><span data-ttu-id="37836-186">Convalidare il token</span><span class="sxs-lookup"><span data-stu-id="37836-186">Validate the token</span></span>

1. <span data-ttu-id="37836-187">Copiare e incollare il token nel sito [Web JWT (Json Web Token Validator)](https://jwt.ms) per decodificarlo.</span><span class="sxs-lookup"><span data-stu-id="37836-187">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>

1. <span data-ttu-id="37836-188">Verificare che *l'attestazione dei* ruoli all'interno del token decodificato contenga le autorizzazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="37836-188">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

   <span data-ttu-id="37836-189">Nell'immagine seguente puoi vedere un token decodificato acquisito da un'app, con `Incidents.Read.All` `Incidents.ReadWrite.All` , e `AdvancedHunting.Read.All` autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="37836-189">In the following image, you can see a decoded token acquired from an app, with `Incidents.Read.All`, `Incidents.ReadWrite.All`, and `AdvancedHunting.Read.All` permissions:</span></span>

   ![Immagine della convalida dei token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="37836-191">Usare il token per accedere all'API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37836-191">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="37836-192">Scegli l'API che vuoi usare (eventi imprevisti o ricerca avanzata).</span><span class="sxs-lookup"><span data-stu-id="37836-192">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="37836-193">Per altre informazioni, vedi [API Microsoft 365 Defender supportate.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="37836-193">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="37836-194">Nella richiesta http che stai per inviare, imposta l'intestazione di autorizzazione su , Bearer è lo schema di autorizzazione e il token è `"Bearer" <token>` il token  convalidato. </span><span class="sxs-lookup"><span data-stu-id="37836-194">In the http request you are about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>

3. <span data-ttu-id="37836-195">Il token scadrà entro un'ora.</span><span class="sxs-lookup"><span data-stu-id="37836-195">The token will expire within one hour.</span></span> <span data-ttu-id="37836-196">Puoi inviare più di una richiesta durante questo periodo di tempo con lo stesso token.</span><span class="sxs-lookup"><span data-stu-id="37836-196">You can send more than one request during this time with the same token.</span></span>

<span data-ttu-id="37836-197">Nell'esempio seguente viene illustrato come inviare una richiesta per ottenere un elenco di eventi imprevisti **tramite C#**.</span><span class="sxs-lookup"><span data-stu-id="37836-197">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="37836-198">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="37836-198">Related articles</span></span>

- [<span data-ttu-id="37836-199">Microsoft 365 Panoramica delle API defender</span><span class="sxs-lookup"><span data-stu-id="37836-199">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="37836-200">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37836-200">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="37836-201">Creare un'applicazione "Hello world"</span><span class="sxs-lookup"><span data-stu-id="37836-201">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="37836-202">Creare un'app per accedere Microsoft 365 DEFENDER API per conto di un utente</span><span class="sxs-lookup"><span data-stu-id="37836-202">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="37836-203">Creare un'app con accesso partner multi-tenant alle API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37836-203">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="37836-204">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="37836-204">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="37836-205">Comprendere i codici di errore</span><span class="sxs-lookup"><span data-stu-id="37836-205">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="37836-206">Gestire i segreti nelle app server con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="37836-206">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="37836-207">Autorizzazione OAuth 2.0 per l'accesso utente e l'accesso api</span><span class="sxs-lookup"><span data-stu-id="37836-207">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)