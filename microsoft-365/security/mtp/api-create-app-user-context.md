---
title: Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente
description: Informazioni su come accedere alle API di Microsoft 365 Defender per conto di un utente.
keywords: accesso, per conto dell'utente, dell'API, dell'applicazione, dell'utente, del token di accesso, del token,
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
ms.openlocfilehash: f1c0caea9ff7810f79026c789241a4f250ec5303
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719417"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="d3a82-104">Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente</span><span class="sxs-lookup"><span data-stu-id="d3a82-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d3a82-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d3a82-105">**Applies to:**</span></span>

- <span data-ttu-id="d3a82-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3a82-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3a82-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="d3a82-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d3a82-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="d3a82-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d3a82-109">In questa pagina viene descritto come creare un'applicazione per ottenere l'accesso programmatico a Microsoft 365 Defender per conto di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="d3a82-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="d3a82-110">Se è necessario l'accesso a livello di programmazione a Microsoft 365 Defender senza un utente definito (ad esempio, se si sta scrivendo un'app o un daemon in background), vedere [creare un'app per accedere a microsoft 365 Defender senza un utente](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="d3a82-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="d3a82-111">Se è necessario fornire l'accesso per più tenant, ad esempio se si sta servendo un'organizzazione di grandi dimensioni o un gruppo di clienti, vedere [creare un'app con accesso partner a Microsoft 365 Defender Apis](api-partner-access.md). Se non si è certi del tipo di accesso necessario, vedere [Introduzione](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="d3a82-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="d3a82-112">Microsoft 365 Defender espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="d3a82-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="d3a82-113">Tali API consentono di automatizzare i flussi di lavoro e di avvalersi delle funzionalità di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d3a82-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="d3a82-114">Questo accesso API richiede l'autenticazione OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="d3a82-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="d3a82-115">Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="d3a82-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="d3a82-116">In generale, è necessario eseguire la procedura seguente per utilizzare queste API:</span><span class="sxs-lookup"><span data-stu-id="d3a82-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="d3a82-117">Creare un'applicazione Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d3a82-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="d3a82-118">Ottenere un token di accesso utilizzando l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d3a82-118">Get an access token using this application.</span></span>
- <span data-ttu-id="d3a82-119">Utilizzare il token per accedere a Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="d3a82-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="d3a82-120">In questo articolo viene illustrato come eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d3a82-120">This article explains how to:</span></span>

- <span data-ttu-id="d3a82-121">Creare un'applicazione Azure AD</span><span class="sxs-lookup"><span data-stu-id="d3a82-121">Create an Azure AD application</span></span>
- <span data-ttu-id="d3a82-122">Ottenere un token di accesso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3a82-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="d3a82-123">Convalidare il token</span><span class="sxs-lookup"><span data-stu-id="d3a82-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="d3a82-124">Quando si accede a Microsoft 365 Defender API per conto di un utente, è necessario disporre delle autorizzazioni appropriate per l'applicazione e delle autorizzazioni utente.</span><span class="sxs-lookup"><span data-stu-id="d3a82-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="d3a82-125">Se si dispone dell'autorizzazione necessaria per eseguire un'azione nel portale, è possibile disporre dell'autorizzazione per eseguire l'azione nell'API.</span><span class="sxs-lookup"><span data-stu-id="d3a82-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="d3a82-126">Creare un'app</span><span class="sxs-lookup"><span data-stu-id="d3a82-126">Create an app</span></span>

1. <span data-ttu-id="d3a82-127">Accedere a [Azure](https://portal.azure.com) come utente con il ruolo di **amministratore globale** .</span><span class="sxs-lookup"><span data-stu-id="d3a82-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="d3a82-128">Passare a registrazione delle app di **Azure Active Directory**  >    >  **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="d3a82-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Immagine di Microsoft Azure e spostamento alla registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="d3a82-130">Nel modulo scegliere un nome per l'applicazione e immettere le informazioni seguenti per l'URI di reindirizzamento, quindi selezionare **registra**.</span><span class="sxs-lookup"><span data-stu-id="d3a82-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Immagine della finestra Crea applicazione](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="d3a82-132">**Tipo di applicazione:** Client pubblico</span><span class="sxs-lookup"><span data-stu-id="d3a82-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="d3a82-133">**URI di reindirizzamento:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="d3a82-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="d3a82-134">Nella pagina dell'applicazione selezionare **autorizzazioni API**  >  **Aggiungi API di autorizzazione**  >  **l'organizzazione utilizza** >, digitare **Microsoft Threat Protection** e selezionare **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="d3a82-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="d3a82-135">L'app può ora accedere a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d3a82-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="d3a82-136">*Microsoft Threat Protection* è un nome precedente per Microsoft 365 Defender e non verrà visualizzato nell'elenco originale.</span><span class="sxs-lookup"><span data-stu-id="d3a82-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="d3a82-137">È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="d3a82-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Immagine della selezione delle autorizzazioni API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="d3a82-139">Scegliere **autorizzazioni delegate**.</span><span class="sxs-lookup"><span data-stu-id="d3a82-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="d3a82-140">Scegliere le autorizzazioni rilevanti per lo scenario, ad esempio **Incident. Read**, e quindi fare clic su **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="d3a82-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Immagine dell'accesso API e della selezione dell'API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="d3a82-142">È necessario selezionare le autorizzazioni rilevanti per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="d3a82-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="d3a82-143">*Leggere tutti gli eventi* non consentiti è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="d3a82-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="d3a82-144">Per determinare le autorizzazioni necessarie, vedere la sezione relativa alle **autorizzazioni** nell'API che si desidera chiamare.</span><span class="sxs-lookup"><span data-stu-id="d3a82-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="d3a82-145">Ad esempio, per [eseguire query avanzate](api-advanced-hunting.md), selezionare l'autorizzazione ' Esegui query avanzate '; per [isolare un dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), selezionare l'autorizzazione ' isolate machine '.</span><span class="sxs-lookup"><span data-stu-id="d3a82-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="d3a82-146">Selezionare **Concedi consenso amministratore**.</span><span class="sxs-lookup"><span data-stu-id="d3a82-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="d3a82-147">Ogni volta che si aggiunge un'autorizzazione, è necessario selezionare **Concedi all'amministratore il consenso** per rendere effettive le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d3a82-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Immagine delle autorizzazioni di concessione](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="d3a82-149">Registrare l'ID dell'applicazione e l'ID del tenant in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="d3a82-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="d3a82-150">Sono elencate in **Panoramica** nella pagina dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d3a82-150">They're listed under **Overview** on your application page.</span></span>

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="d3a82-152">Ottenere un token di accesso</span><span class="sxs-lookup"><span data-stu-id="d3a82-152">Get an access token</span></span>

<span data-ttu-id="d3a82-153">Per ulteriori informazioni sui token di Azure Active Directory, vedere l' [esercitazione su Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="d3a82-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="d3a82-154">Ottenere un token di accesso tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3a82-154">Get an access token using PowerShell</span></span>

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

## <a name="validate-the-token"></a><span data-ttu-id="d3a82-155">Convalidare il token</span><span class="sxs-lookup"><span data-stu-id="d3a82-155">Validate the token</span></span>

1. <span data-ttu-id="d3a82-156">Copiare e incollare il token in [JWT](https://jwt.ms) per decodificarlo.</span><span class="sxs-lookup"><span data-stu-id="d3a82-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="d3a82-157">Verificare che l'attestazione dei *ruoli* all'interno del token decodificato contenga le autorizzazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="d3a82-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="d3a82-158">Nell'immagine seguente, è possibile visualizzare un token decodificato acquisito da un'app, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` e le ```AdvancedHunting.Read.All``` autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="d3a82-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Immagine della convalida dei token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="d3a82-160">Utilizzare il token per accedere all'API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3a82-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="d3a82-161">Scegliere l'API che si desidera utilizzare (operazioni non consentite o ricerca avanzata).</span><span class="sxs-lookup"><span data-stu-id="d3a82-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="d3a82-162">Per ulteriori informazioni, vedere [API di Microsoft 365 Defender supportate](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="d3a82-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="d3a82-163">Nella richiesta HTTP che si sta per inviare, impostare l'intestazione di autorizzazione su `"Bearer" <token>` , *portatore* che è lo schema di autorizzazione e *token* che è il token convalidato.</span><span class="sxs-lookup"><span data-stu-id="d3a82-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="d3a82-164">Il token scadrà entro un'ora.</span><span class="sxs-lookup"><span data-stu-id="d3a82-164">The token will expire within one hour.</span></span> <span data-ttu-id="d3a82-165">È possibile inviare più di una richiesta durante questo periodo con lo stesso token.</span><span class="sxs-lookup"><span data-stu-id="d3a82-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="d3a82-166">Nell'esempio riportato di seguito viene illustrato come inviare una richiesta per ottenere un elenco di operazioni non consentite **tramite C#**.</span><span class="sxs-lookup"><span data-stu-id="d3a82-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="d3a82-167">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="d3a82-167">Related articles</span></span>

- [<span data-ttu-id="d3a82-168">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3a82-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="d3a82-169">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d3a82-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="d3a82-170">Creare un'app ' Hello World '</span><span class="sxs-lookup"><span data-stu-id="d3a82-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="d3a82-171">Creare un'app per accedere a Microsoft 365 Defender senza un utente</span><span class="sxs-lookup"><span data-stu-id="d3a82-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="d3a82-172">Creare un'app con accesso partner multi-tenant a Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="d3a82-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="d3a82-173">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="d3a82-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="d3a82-174">Informazioni sui codici di errore</span><span class="sxs-lookup"><span data-stu-id="d3a82-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="d3a82-175">OAuth 2,0 autorizzazione per l'accesso dell'utente e dell'API</span><span class="sxs-lookup"><span data-stu-id="d3a82-175">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
