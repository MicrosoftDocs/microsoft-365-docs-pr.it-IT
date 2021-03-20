---
title: Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente
description: Scopri come accedere alle API di Microsoft 365 Defender per conto di un utente.
keywords: accesso, per conto di utente, api, applicazione, utente, token di accesso, token,
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
ms.openlocfilehash: 85c41c0bae9590e76801c18b2a33401874cc7cc3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903953"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="b0f1e-104">Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente</span><span class="sxs-lookup"><span data-stu-id="b0f1e-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b0f1e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b0f1e-105">**Applies to:**</span></span>

- <span data-ttu-id="b0f1e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0f1e-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b0f1e-107">Alcune informazioni riguardano prodotti prereleased che possono essere sostanzialmente modificati prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b0f1e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b0f1e-109">Questa pagina descrive come creare un'applicazione per ottenere l'accesso a livello di codice a Microsoft 365 Defender per conto di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="b0f1e-110">Se è necessario l'accesso a livello di codice a Microsoft 365 Defender senza un utente definito (ad esempio, se stai scrivendo un'app in background o un daemon), vedi Creare un'app per accedere a [Microsoft 365 Defender](api-create-app-web.md)senza un utente.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="b0f1e-111">Se devi fornire l'accesso a più tenant, ad esempio se stai servendo un'organizzazione di grandi dimensioni o un gruppo di clienti, vedi Creare un'app con accesso partner alle API di [Microsoft 365 Defender.](api-partner-access.md) Se non si è certi del tipo di accesso necessario, vedere [Introduzione.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="b0f1e-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="b0f1e-112">Microsoft 365 Defender espone gran parte dei dati e delle azioni tramite un set di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="b0f1e-113">Queste API consentono di automatizzare i flussi di lavoro e di usare le funzionalità di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="b0f1e-114">L'accesso all'API richiede l'autenticazione OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="b0f1e-115">Per ulteriori informazioni, vedere Flusso del codice di autorizzazione [OAuth 2.0.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="b0f1e-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="b0f1e-116">In generale, dovrai eseguire la procedura seguente per usare queste API:</span><span class="sxs-lookup"><span data-stu-id="b0f1e-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="b0f1e-117">Creare un'applicazione Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b0f1e-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="b0f1e-118">Ottieni un token di accesso usando questa applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-118">Get an access token using this application.</span></span>
- <span data-ttu-id="b0f1e-119">Usa il token per accedere all'API di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="b0f1e-120">In questo articolo viene illustrato come:</span><span class="sxs-lookup"><span data-stu-id="b0f1e-120">This article explains how to:</span></span>

- <span data-ttu-id="b0f1e-121">Creare un'applicazione Azure AD</span><span class="sxs-lookup"><span data-stu-id="b0f1e-121">Create an Azure AD application</span></span>
- <span data-ttu-id="b0f1e-122">Ottenere un token di accesso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0f1e-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="b0f1e-123">Convalidare il token</span><span class="sxs-lookup"><span data-stu-id="b0f1e-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="b0f1e-124">Quando si accede all'API di Microsoft 365 Defender per conto di un utente, sono necessarie le autorizzazioni dell'applicazione e le autorizzazioni utente corrette.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="b0f1e-125">Se hai l'autorizzazione per eseguire un'azione nel portale, hai l'autorizzazione per eseguire l'azione nell'API.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="b0f1e-126">Creare un'app</span><span class="sxs-lookup"><span data-stu-id="b0f1e-126">Create an app</span></span>

1. <span data-ttu-id="b0f1e-127">Accedere ad [Azure](https://portal.azure.com) come utente con il **ruolo Amministratore** globale.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="b0f1e-128">Passare ad **Azure Active Directory** App  >  **registrations** Nuova  >  **registrazione**.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Immagine di Microsoft Azure e spostamento nella registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="b0f1e-130">Nel modulo scegliere un nome per l'applicazione e immettere le informazioni seguenti per l'URI di reindirizzamento, quindi selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Immagine della finestra Crea applicazione](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="b0f1e-132">**Tipo di applicazione:** Client pubblico</span><span class="sxs-lookup"><span data-stu-id="b0f1e-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="b0f1e-133">**URI di reindirizzamento:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="b0f1e-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="b0f1e-134">Nella pagina dell'applicazione seleziona **Autorizzazioni API** Aggiungi le API di autorizzazione che l'organizzazione usa >, digita  >    >   Microsoft **Threat Protection** e seleziona Microsoft **Threat Protection.**</span><span class="sxs-lookup"><span data-stu-id="b0f1e-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="b0f1e-135">La tua app ora può accedere a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="b0f1e-136">*Microsoft Threat Protection* è un ex nome di Microsoft 365 Defender e non verrà visualizzato nell'elenco originale.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="b0f1e-137">È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Immagine della selezione delle autorizzazioni API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="b0f1e-139">Scegliere **Autorizzazioni delegate**.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="b0f1e-140">Scegliere le autorizzazioni rilevanti per lo scenario, ad esempio **Incident.Read,** e quindi **selezionare Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Immagine dell'accesso alle API e della selezione delle API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="b0f1e-142">È necessario selezionare le autorizzazioni pertinenti per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="b0f1e-143">*Leggere tutti gli eventi imprevisti* è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="b0f1e-144">Per determinare l'autorizzazione necessaria, consulta la **sezione Autorizzazioni** nell'API che vuoi chiamare.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="b0f1e-145">Ad esempio, per [eseguire query avanzate,](api-advanced-hunting.md)selezionare l'autorizzazione "Esegui query avanzate". per [isolare un dispositivo,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)seleziona l'autorizzazione "Isola computer".</span><span class="sxs-lookup"><span data-stu-id="b0f1e-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="b0f1e-146">Selezionare **Concedi il consenso dell'amministratore.**</span><span class="sxs-lookup"><span data-stu-id="b0f1e-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="b0f1e-147">Ogni volta che aggiungi un'autorizzazione, devi selezionare **Concedi** il consenso dell'amministratore per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Immagine delle autorizzazioni di concessione](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="b0f1e-149">Registrare l'ID applicazione e l'ID tenant in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="b0f1e-150">Sono elencati in **Panoramica nella** pagina dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-150">They're listed under **Overview** on your application page.</span></span>

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="b0f1e-152">Ottenere un token di accesso</span><span class="sxs-lookup"><span data-stu-id="b0f1e-152">Get an access token</span></span>

<span data-ttu-id="b0f1e-153">Per altre informazioni sui token di Azure Active Directory, vedi l'esercitazione [su Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="b0f1e-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="b0f1e-154">Ottenere un token di accesso tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0f1e-154">Get an access token using PowerShell</span></span>

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a><span data-ttu-id="b0f1e-155">Convalidare il token</span><span class="sxs-lookup"><span data-stu-id="b0f1e-155">Validate the token</span></span>

1. <span data-ttu-id="b0f1e-156">Copia e incolla il token in [JWT](https://jwt.ms) per decodificarlo.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="b0f1e-157">Verificare che *l'attestazione dei* ruoli all'interno del token decodificato contenga le autorizzazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="b0f1e-158">Nell'immagine seguente puoi vedere un token decodificato acquisito da un'app, con ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , e ```AdvancedHunting.Read.All``` autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="b0f1e-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Immagine della convalida dei token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="b0f1e-160">Usare il token per accedere all'API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0f1e-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="b0f1e-161">Scegli l'API che vuoi usare (eventi imprevisti o ricerca avanzata).</span><span class="sxs-lookup"><span data-stu-id="b0f1e-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="b0f1e-162">Per altre informazioni, vedi [API supportate di Microsoft 365 Defender.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="b0f1e-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="b0f1e-163">Nella richiesta http che stai per inviare, imposta l'intestazione di autorizzazione su , Bearer è lo schema di autorizzazione e il token è `"Bearer" <token>` il token  convalidato. </span><span class="sxs-lookup"><span data-stu-id="b0f1e-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="b0f1e-164">Il token scadrà entro un'ora.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-164">The token will expire within one hour.</span></span> <span data-ttu-id="b0f1e-165">Puoi inviare più di una richiesta durante questo periodo di tempo con lo stesso token.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="b0f1e-166">Nell'esempio seguente viene illustrato come inviare una richiesta per ottenere un elenco di eventi imprevisti **tramite C#**.</span><span class="sxs-lookup"><span data-stu-id="b0f1e-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="b0f1e-167">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="b0f1e-167">Related articles</span></span>

- [<span data-ttu-id="b0f1e-168">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0f1e-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="b0f1e-169">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0f1e-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="b0f1e-170">Creare un'app "Hello world"</span><span class="sxs-lookup"><span data-stu-id="b0f1e-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="b0f1e-171">Creare un'app per accedere a Microsoft 365 Defender senza un utente</span><span class="sxs-lookup"><span data-stu-id="b0f1e-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="b0f1e-172">Creare un'app con accesso partner multi-tenant alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0f1e-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="b0f1e-173">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="b0f1e-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="b0f1e-174">Comprendere i codici di errore</span><span class="sxs-lookup"><span data-stu-id="b0f1e-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="b0f1e-175">Autorizzazione OAuth 2.0 per l'accesso utente e l'accesso api</span><span class="sxs-lookup"><span data-stu-id="b0f1e-175">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)