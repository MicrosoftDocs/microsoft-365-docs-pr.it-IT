---
title: Accesso partner tramite Microsoft 365 Defender API
description: Scopri come creare un'app per ottenere l'accesso programmatico a Microsoft 365 Defender per conto degli utenti.
keywords: partner, accesso, api, multi tenant, consenso, token di accesso, app
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
ms.openlocfilehash: 46876fef8a0279ee350d57fdc85aeced82696656
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062037"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="9cb7d-104">Creare un'app con accesso partner alle API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cb7d-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9cb7d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="9cb7d-105">**Applies to:**</span></span>

- <span data-ttu-id="9cb7d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cb7d-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cb7d-107">Alcune informazioni fanno riferimento alle caratteristiche del prodotto prima del rilascio, e possono essere modificate sostanzialmente prima della distribuzione al pubblico.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9cb7d-108">Microsoft non fornisce alcuna garanzia, esplicita o implicita, in relazione alle informazioni contenute in questo documento.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="9cb7d-109">Questa pagina descrive come creare un'app Azure Active Directory con accesso a livello di codice a Microsoft 365 Defender, per conto degli utenti in più tenant.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="9cb7d-110">Le app multi-tenant sono utili per servire grandi gruppi di utenti.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="9cb7d-111">Se hai bisogno dell'accesso a livello di codice a Microsoft 365 Defender per conto di un singolo utente, vedi Creare un'app per accedere alle API di Microsoft 365 Defender per conto di [un utente.](api-create-app-user-context.md)</span><span class="sxs-lookup"><span data-stu-id="9cb7d-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="9cb7d-112">Se devi accedere senza definire esplicitamente un utente (ad esempio, se stai scrivendo un'app in background o un daemon), vedi Creare un'app per accedere a Microsoft 365 Defender senza [un utente.](api-create-app-web.md)</span><span class="sxs-lookup"><span data-stu-id="9cb7d-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="9cb7d-113">Se non si è certi del tipo di accesso necessario, vedere [Introduzione.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="9cb7d-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="9cb7d-114">Microsoft 365 Defender espone gran parte dei dati e delle azioni tramite un set di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="9cb7d-115">Queste API consentono di automatizzare i flussi di lavoro e di usare Microsoft 365 funzionalità di Defender.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="9cb7d-116">L'accesso all'API richiede l'autenticazione OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="9cb7d-117">Per ulteriori informazioni, vedere [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="9cb7d-117">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="9cb7d-118">In generale, dovrai eseguire la procedura seguente per usare queste API:</span><span class="sxs-lookup"><span data-stu-id="9cb7d-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="9cb7d-119">Creare un'Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9cb7d-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="9cb7d-120">Ottieni un token di accesso usando questa applicazione.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-120">Get an access token using this application.</span></span>
- <span data-ttu-id="9cb7d-121">Usa il token per accedere Microsoft 365'API Defender.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="9cb7d-122">Dal momento che questa app è multi-tenant, dovrai anche il consenso dell'amministratore [di](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) ogni tenant per conto dei suoi utenti.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-122">Since this app is multi-tenant, you'll also need [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="9cb7d-123">In questo articolo viene illustrato come:</span><span class="sxs-lookup"><span data-stu-id="9cb7d-123">This article explains how to:</span></span>

- <span data-ttu-id="9cb7d-124">Creare **un'applicazione** Azure AD multi-tenant</span><span class="sxs-lookup"><span data-stu-id="9cb7d-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="9cb7d-125">Ottenere il consenso autorizzato dall'amministratore dell'utente per l'applicazione per accedere al Microsoft 365 Defender necessario.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="9cb7d-126">Ottenere un token di accesso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cb7d-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="9cb7d-127">Convalidare il token</span><span class="sxs-lookup"><span data-stu-id="9cb7d-127">Validate the token</span></span>

<span data-ttu-id="9cb7d-128">Microsoft 365 Defender espone gran parte dei dati e delle azioni tramite un set di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="9cb7d-129">Queste API ti aiuteranno ad automatizzare i flussi di lavoro e a innovare in base alle Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="9cb7d-130">L'accesso API richiede l'autenticazione OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="9cb7d-131">Per ulteriori informazioni, vedere [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="9cb7d-131">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="9cb7d-132">In generale, dovrai eseguire la procedura seguente per usare le API:</span><span class="sxs-lookup"><span data-stu-id="9cb7d-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="9cb7d-133">Creare un'applicazione Azure AD **multi-tenant.**</span><span class="sxs-lookup"><span data-stu-id="9cb7d-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="9cb7d-134">Ottenere l'autorizzazione (consenso) dall'amministratore dell'utente per l'applicazione per accedere Microsoft 365 risorse defender necessarie.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="9cb7d-135">Ottieni un token di accesso usando questa applicazione.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-135">Get an access token using this application.</span></span>
- <span data-ttu-id="9cb7d-136">Usa il token per accedere Microsoft 365'API Defender.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="9cb7d-137">La procedura seguente illustra come creare un'applicazione Azure AD multi-tenant, ottenere un token di accesso Microsoft 365 Defender e convalidare il token.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="9cb7d-138">Creare l'app multi-tenant</span><span class="sxs-lookup"><span data-stu-id="9cb7d-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="9cb7d-139">Accedere ad [Azure](https://portal.azure.com) come utente con il **ruolo Amministratore** globale.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="9cb7d-140">Passare **a** Azure Active Directory  >  **app Nuove**  >  **registrazioni**.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Immagine dell'Microsoft Azure e della navigazione per la registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="9cb7d-142">Nel modulo di registrazione:</span><span class="sxs-lookup"><span data-stu-id="9cb7d-142">In the registration form:</span></span>

   - <span data-ttu-id="9cb7d-143">Scegliere un nome per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="9cb7d-144">In **Tipi di account supportati** selezionare Account in qualsiasi directory **dell'organizzazione (qualsiasi directory di Azure AD) - Multitenant**.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="9cb7d-145">Compila la **sezione Uri di reindirizzamento.**</span><span class="sxs-lookup"><span data-stu-id="9cb7d-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="9cb7d-146">Selezionare il tipo **Web** e assegnare l'URI di reindirizzamento come **https://portal.azure.com** .</span><span class="sxs-lookup"><span data-stu-id="9cb7d-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="9cb7d-147">Dopo aver compilato il modulo, selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-147">After you're done filling out the form, select **Register**.</span></span>

   ![Immagine del modulo Registra un'applicazione](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="9cb7d-149">Nella pagina dell'applicazione seleziona **Autorizzazioni API** Aggiungi API di autorizzazione che l'organizzazione usa  >    >   >, digita **Microsoft Threat Protection** e seleziona **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="9cb7d-150">La tua app può ora accedere Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="9cb7d-151">*Microsoft Threat Protection* è un ex nome di Microsoft 365 Defender e non verrà visualizzato nell'elenco originale.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="9cb7d-152">È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![Immagine della selezione delle autorizzazioni API](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="9cb7d-154">Selezionare **Autorizzazioni applicazione**.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-154">Select **Application permissions**.</span></span> <span data-ttu-id="9cb7d-155">Scegliere le autorizzazioni rilevanti per lo scenario, ad esempio **Incident.Read.All,** e quindi **selezionare Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Immagine dell'accesso alle API e della selezione delle API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="9cb7d-157">È necessario selezionare le autorizzazioni pertinenti per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="9cb7d-158">*Leggere tutti gli eventi imprevisti* è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="9cb7d-159">Per determinare l'autorizzazione necessaria, consulta la **sezione Autorizzazioni** nell'API che vuoi chiamare.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="9cb7d-160">Ad esempio, per [eseguire query avanzate,](api-advanced-hunting.md)selezionare l'autorizzazione "Esegui query avanzate". per [isolare un dispositivo,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)seleziona l'autorizzazione "Isola computer".</span><span class="sxs-lookup"><span data-stu-id="9cb7d-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="9cb7d-161">Selezionare **Concedi il consenso dell'amministratore.**</span><span class="sxs-lookup"><span data-stu-id="9cb7d-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="9cb7d-162">Ogni volta che aggiungi un'autorizzazione, devi selezionare **Concedi** il consenso dell'amministratore per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Immagine delle autorizzazioni di concessione](../../media/grant-consent.PNG)

7. <span data-ttu-id="9cb7d-164">Per aggiungere un segreto all'applicazione, selezionare **Certificati & segreti,** aggiungere una descrizione al segreto, quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="9cb7d-165">Dopo aver selezionato **Aggiungi,** selezionare **copia il valore segreto generato.**</span><span class="sxs-lookup"><span data-stu-id="9cb7d-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="9cb7d-166">Non sarà possibile recuperare il valore segreto dopo aver lasciato.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Immagine della chiave di creazione dell'app](../../media/webapp-create-key2.png)

8. <span data-ttu-id="9cb7d-168">Registrare l'ID applicazione e l'ID tenant in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="9cb7d-169">Sono elencati in **Panoramica nella** pagina dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-169">They're listed under **Overview** on your application page.</span></span>

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="9cb7d-171">Aggiungere l'applicazione al tenant dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="9cb7d-172">Poiché l'applicazione interagisce con Microsoft 365 Defender per conto degli utenti, deve essere approvata per ogni tenant in cui si intende usarla.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="9cb7d-173">Un **amministratore globale** del tenant dell'utente deve visualizzare il collegamento di consenso e approvare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="9cb7d-174">Il collegamento consenso ha il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="9cb7d-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="9cb7d-175">Le cifre `00000000-0000-0000-0000-000000000000` devono essere sostituite con l'ID applicazione.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="9cb7d-176">Dopo aver fatto clic sul collegamento di consenso, accedere con l'amministratore globale del tenant dell'utente e acconsentire all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![Immagine del consenso](../../media/app-consent-partner.png)

   <span data-ttu-id="9cb7d-178">Dovrai anche chiedere all'utente l'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="9cb7d-179">L'ID tenant è uno degli identificatori usati per acquisire i token di accesso.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="9cb7d-180">**Fatto!**</span><span class="sxs-lookup"><span data-stu-id="9cb7d-180">**Done!**</span></span> <span data-ttu-id="9cb7d-181">L'applicazione è stata registrata correttamente.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="9cb7d-182">Vedi gli esempi seguenti per l'acquisizione e la convalida di token.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="9cb7d-183">Ottenere un token di accesso</span><span class="sxs-lookup"><span data-stu-id="9cb7d-183">Get an access token</span></span>

<span data-ttu-id="9cb7d-184">Per altre informazioni sui token di Azure AD, vedi l'esercitazione [su Azure AD.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="9cb7d-184">For more information on Azure AD tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cb7d-185">Anche se gli esempi in questa sezione incoraggiano a incollare valori segreti a scopo di test, non è consigliabile codificare mai segreti **hardcoded** in un'applicazione in esecuzione nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="9cb7d-186">Una terza parte potrebbe usare il segreto per accedere alle risorse.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="9cb7d-187">Puoi proteggere i segreti dell'app usando [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="9cb7d-187">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="9cb7d-188">Per un esempio pratico di come proteggere la tua app, vedi Gestire i segreti [nelle app server con Azure Key Vault.](/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="9cb7d-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="9cb7d-189">Negli esempi seguenti, usa l'ID tenant di un utente per verificare che lo script funzioni.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="9cb7d-190">Ottenere un token di accesso tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cb7d-190">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="9cb7d-191">Ottenere un token di accesso con C\#</span><span class="sxs-lookup"><span data-stu-id="9cb7d-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="9cb7d-192">Il codice seguente è stato testato con Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="9cb7d-193">Creare una nuova applicazione console.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-193">Create a new console application.</span></span>
1. <span data-ttu-id="9cb7d-194">Installare NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="9cb7d-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="9cb7d-195">Aggiungere la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="9cb7d-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="9cb7d-196">Copia e incolla il codice seguente nella tua app (non dimenticare di aggiornare le tre variabili: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="9cb7d-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="9cb7d-197">Ottenere un token di accesso con Python</span><span class="sxs-lookup"><span data-stu-id="9cb7d-197">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="9cb7d-198">Ottenere un token di accesso con l'arricciatura</span><span class="sxs-lookup"><span data-stu-id="9cb7d-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="9cb7d-199">Curl è preinstallato in Windows 10, versioni 1803 e successive.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="9cb7d-200">Per altre versioni di Windows, scaricare e installare lo strumento direttamente dal sito [Web ufficiale di .NET Framework.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="9cb7d-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="9cb7d-201">Aprire un prompt dei comandi e impostare CLIENT_ID'ID applicazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="9cb7d-202">Impostare CLIENT_SECRET sul segreto dell'applicazione Azure.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="9cb7d-203">Imposta TENANT_ID'ID tenant di Azure dell'utente che vuole usare la tua app per accedere a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="9cb7d-204">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="9cb7d-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="9cb7d-205">Una risposta corretta sarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="9cb7d-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="9cb7d-206">Convalidare il token</span><span class="sxs-lookup"><span data-stu-id="9cb7d-206">Validate the token</span></span>

1. <span data-ttu-id="9cb7d-207">Copiare e incollare il token nel sito [Web JWT (Json Web Token Validator)](https://jwt.ms) per decodificarlo.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="9cb7d-208">Verificare che *l'attestazione dei* ruoli all'interno del token decodificato contenga le autorizzazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="9cb7d-209">Nell'immagine seguente puoi vedere un token decodificato acquisito da un'app, con ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , e ```AdvancedHunting.Read.All``` autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="9cb7d-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Immagine della convalida dei token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="9cb7d-211">Usare il token per accedere all'API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cb7d-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="9cb7d-212">Scegli l'API che vuoi usare (eventi imprevisti o ricerca avanzata).</span><span class="sxs-lookup"><span data-stu-id="9cb7d-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="9cb7d-213">Per altre informazioni, vedi [API Microsoft 365 Defender supportate.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="9cb7d-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="9cb7d-214">Nella richiesta http che stai per inviare, imposta l'intestazione di autorizzazione su , Bearer è lo schema di autorizzazione e il token è `"Bearer" <token>` il token  convalidato. </span><span class="sxs-lookup"><span data-stu-id="9cb7d-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="9cb7d-215">Il token scadrà entro un'ora.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-215">The token will expire within one hour.</span></span> <span data-ttu-id="9cb7d-216">Puoi inviare più di una richiesta durante questo periodo di tempo con lo stesso token.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="9cb7d-217">Nell'esempio seguente viene illustrato come inviare una richiesta per ottenere un elenco di eventi imprevisti **tramite C#**.</span><span class="sxs-lookup"><span data-stu-id="9cb7d-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="9cb7d-218">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="9cb7d-218">Related articles</span></span>

- [<span data-ttu-id="9cb7d-219">Microsoft 365 Panoramica delle API defender</span><span class="sxs-lookup"><span data-stu-id="9cb7d-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="9cb7d-220">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cb7d-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="9cb7d-221">Creare un'applicazione "Hello world"</span><span class="sxs-lookup"><span data-stu-id="9cb7d-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="9cb7d-222">Creare un'app per accedere Microsoft 365 Defender senza un utente</span><span class="sxs-lookup"><span data-stu-id="9cb7d-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="9cb7d-223">Creare un'app per accedere Microsoft 365 DEFENDER API per conto di un utente</span><span class="sxs-lookup"><span data-stu-id="9cb7d-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="9cb7d-224">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="9cb7d-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="9cb7d-225">Comprendere i codici di errore</span><span class="sxs-lookup"><span data-stu-id="9cb7d-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="9cb7d-226">Gestire i segreti nelle app server con Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="9cb7d-226">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="9cb7d-227">Autorizzazione OAuth 2.0 per l'accesso utente e l'accesso api</span><span class="sxs-lookup"><span data-stu-id="9cb7d-227">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)