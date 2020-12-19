---
title: Accesso partner tramite API Microsoft 365 Defender
description: Informazioni su come creare un'app per ottenere l'accesso programmatico a Microsoft 365 Defender per conto degli utenti.
keywords: partner, accesso, API, multi tenant, consenso, token di accesso, app
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
ms.openlocfilehash: 5de113c8f8419b3af2a287bd7ba7e41dc06b4121
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719441"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="0c7c7-104">Creare un'app con accesso partner a Microsoft 365 Defender APIs</span><span class="sxs-lookup"><span data-stu-id="0c7c7-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="0c7c7-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0c7c7-105">**Applies to:**</span></span>

- <span data-ttu-id="0c7c7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c7c7-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c7c7-107">Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0c7c7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="0c7c7-109">In questa pagina viene descritto come creare un'app di Azure Active Directory con accesso programmatico a Microsoft 365 Defender, per conto degli utenti tra più tenant.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="0c7c7-110">Le app multi-tenant sono utili per la gestione di gruppi di utenti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="0c7c7-111">Se è necessario l'accesso a livello di programmazione a Microsoft 365 Defender per conto di un singolo utente, vedere [Create an app to Access microsoft 365 Defender APIs per conto di un utente](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="0c7c7-112">Se è necessario l'accesso senza un utente definito in modo esplicito (ad esempio, se si sta scrivendo un'app o un daemon in background), vedere [creare un'app per accedere a Microsoft 365 Defender senza un utente](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="0c7c7-113">Se non si è certi del tipo di accesso necessario, vedere [Introduzione](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="0c7c7-114">Microsoft 365 Defender espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="0c7c7-115">Tali API consentono di automatizzare i flussi di lavoro e di avvalersi delle funzionalità di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="0c7c7-116">Questo accesso API richiede l'autenticazione OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="0c7c7-117">Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-117">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="0c7c7-118">In generale, è necessario eseguire la procedura seguente per utilizzare queste API:</span><span class="sxs-lookup"><span data-stu-id="0c7c7-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="0c7c7-119">Creare un'applicazione Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="0c7c7-120">Ottenere un token di accesso utilizzando l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-120">Get an access token using this application.</span></span>
- <span data-ttu-id="0c7c7-121">Utilizzare il token per accedere a Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="0c7c7-122">Poiché questa app è multi-tenant, è necessario anche il [consenso dell'amministratore](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) da ogni tenant per conto dei suoi utenti.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-122">Since this app is multi-tenant, you'll also need [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="0c7c7-123">In questo articolo viene illustrato come eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c7c7-123">This article explains how to:</span></span>

- <span data-ttu-id="0c7c7-124">Creare un'applicazione Azure AD **multi-tenant**</span><span class="sxs-lookup"><span data-stu-id="0c7c7-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="0c7c7-125">Ottenere il consenso autorizzato dall'amministratore degli utenti per l'applicazione per accedere a Microsoft 365 Defender che le risorse di cui ha bisogno.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="0c7c7-126">Ottenere un token di accesso a Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c7c7-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="0c7c7-127">Convalidare il token</span><span class="sxs-lookup"><span data-stu-id="0c7c7-127">Validate the token</span></span>

<span data-ttu-id="0c7c7-128">Microsoft 365 Defender espone gran parte dei suoi dati e delle sue azioni tramite un insieme di API programmatiche.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="0c7c7-129">Tali API consentono di automatizzare i flussi di lavoro e di innovare in base alle funzionalità di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="0c7c7-130">L'accesso API richiede l'autenticazione OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="0c7c7-131">Per ulteriori informazioni, vedere il [flusso del codice di autorizzazione OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-131">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="0c7c7-132">In generale, è necessario eseguire la procedura seguente per utilizzare le API:</span><span class="sxs-lookup"><span data-stu-id="0c7c7-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="0c7c7-133">Creare un'applicazione Azure AD **multi-tenant** .</span><span class="sxs-lookup"><span data-stu-id="0c7c7-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="0c7c7-134">Ottenere autorizzato (consenso) dall'amministratore degli utenti per l'applicazione per accedere alle risorse di Microsoft 365 Defender di cui ha bisogno.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="0c7c7-135">Ottenere un token di accesso utilizzando l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-135">Get an access token using this application.</span></span>
- <span data-ttu-id="0c7c7-136">Utilizzare il token per accedere a Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="0c7c7-137">Nei passaggi seguenti, che illustrano come creare un'applicazione Azure AD multi-tenant, ottenere un token di accesso a Microsoft 365 Defender e convalidare il token.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="0c7c7-138">Creare l'app multi-tenant</span><span class="sxs-lookup"><span data-stu-id="0c7c7-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="0c7c7-139">Accedere a [Azure](https://portal.azure.com) come utente con il ruolo di **amministratore globale** .</span><span class="sxs-lookup"><span data-stu-id="0c7c7-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="0c7c7-140">Passare a registrazione delle app di **Azure Active Directory**  >    >  **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Immagine di Microsoft Azure e spostamento alla registrazione dell'applicazione](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="0c7c7-142">Nel modulo di registrazione:</span><span class="sxs-lookup"><span data-stu-id="0c7c7-142">In the registration form:</span></span>

   - <span data-ttu-id="0c7c7-143">Scegliere un nome per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="0c7c7-144">Dai **tipi di account supportati**, selezionare **account in qualsiasi directory organizzativa (qualsiasi directory di Azure ad)-multitenant**.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="0c7c7-145">Compilare la sezione **URI di reindirizzamento** .</span><span class="sxs-lookup"><span data-stu-id="0c7c7-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="0c7c7-146">Selezionare tipo **Web** e assegnare l'URI di reindirizzamento come **https://portal.azure.com** .</span><span class="sxs-lookup"><span data-stu-id="0c7c7-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="0c7c7-147">Dopo aver completato la compilazione del modulo, selezionare **registra**.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-147">After you're done filling out the form, select **Register**.</span></span>

   ![Immagine del modulo registrazione di una domanda](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="0c7c7-149">Nella pagina dell'applicazione selezionare **autorizzazioni API**  >  **Aggiungi API di autorizzazione**  >  **l'organizzazione utilizza** >, digitare **Microsoft Threat Protection** e selezionare **Microsoft Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="0c7c7-150">L'app può ora accedere a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="0c7c7-151">*Microsoft Threat Protection* è un nome precedente per Microsoft 365 Defender e non verrà visualizzato nell'elenco originale.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="0c7c7-152">È necessario iniziare a scrivere il nome nella casella di testo per visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![Immagine della selezione delle autorizzazioni API](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="0c7c7-154">Selezionare **Autorizzazioni applicazione**.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-154">Select **Application permissions**.</span></span> <span data-ttu-id="0c7c7-155">Scegliere le autorizzazioni rilevanti per lo scenario, ad esempio **Incident. Read. All**, e quindi selezionare **Aggiungi autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Immagine dell'accesso API e della selezione dell'API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="0c7c7-157">È necessario selezionare le autorizzazioni rilevanti per lo scenario.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="0c7c7-158">*Leggere tutti gli eventi* non consentiti è solo un esempio.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="0c7c7-159">Per determinare le autorizzazioni necessarie, vedere la sezione relativa alle **autorizzazioni** nell'API che si desidera chiamare.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="0c7c7-160">Ad esempio, per [eseguire query avanzate](api-advanced-hunting.md), selezionare l'autorizzazione ' Esegui query avanzate '; per [isolare un dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), selezionare l'autorizzazione ' isolate machine '.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="0c7c7-161">Selezionare **Concedi consenso amministratore**.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="0c7c7-162">Ogni volta che si aggiunge un'autorizzazione, è necessario selezionare **Concedi all'amministratore il consenso** per rendere effettive le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Immagine delle autorizzazioni di concessione](../../media/grant-consent.PNG)

7. <span data-ttu-id="0c7c7-164">Per aggiungere un segreto all'applicazione, selezionare **certificati & segreti**, aggiungere una descrizione al segreto e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="0c7c7-165">Dopo aver selezionato **Aggiungi**, selezionare **copia il valore segreto generato**.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="0c7c7-166">Non sarà possibile recuperare il valore segreto dopo l'uscita.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Immagine del tasto Crea app](../../media/webapp-create-key2.png)

8. <span data-ttu-id="0c7c7-168">Registrare l'ID dell'applicazione e l'ID del tenant in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="0c7c7-169">Sono elencate in **Panoramica** nella pagina dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-169">They're listed under **Overview** on your application page.</span></span>

   ![Immagine dell'ID app creato](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="0c7c7-171">Aggiungere l'applicazione al tenant dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="0c7c7-172">Poiché l'applicazione interagisce con Microsoft 365 Defender per conto degli utenti, è necessario approvarla per ogni tenant su cui si intende utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="0c7c7-173">Un **amministratore globale** del tenant dell'utente deve visualizzare il collegamento di consenso e approvare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="0c7c7-174">Il collegamento di consenso ha il formato seguente:</span><span class="sxs-lookup"><span data-stu-id="0c7c7-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="0c7c7-175">Le cifre `00000000-0000-0000-0000-000000000000` devono essere sostituite con l'ID dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="0c7c7-176">Dopo aver fatto clic sul collegamento consenso, accedere con l'amministratore globale del tenant dell'utente e autorizzare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![Immagine del consenso](../../media/app-consent-partner.png)

   <span data-ttu-id="0c7c7-178">È inoltre necessario chiedere all'utente l'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="0c7c7-179">L'ID tenant è uno degli identificatori utilizzati per acquisire i token di accesso.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="0c7c7-180">**Fatto!**</span><span class="sxs-lookup"><span data-stu-id="0c7c7-180">**Done!**</span></span> <span data-ttu-id="0c7c7-181">La registrazione di un'applicazione è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="0c7c7-182">Vedere gli esempi riportati di seguito per l'acquisizione e la convalida dei token.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="0c7c7-183">Ottenere un token di accesso</span><span class="sxs-lookup"><span data-stu-id="0c7c7-183">Get an access token</span></span>

<span data-ttu-id="0c7c7-184">Per ulteriori informazioni sui token di Azure AD, vedere l' [esercitazione di Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-184">For more information on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c7c7-185">Anche se negli esempi di questa sezione è consigliabile incollare i valori segreti a scopo di testing, **non è mai necessario impostare come hardcoded i segreti** in un'applicazione in esecuzione in produzione.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="0c7c7-186">Una terza parte può usare il segreto per accedere alle risorse.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="0c7c7-187">È possibile proteggere i segreti dell'app utilizzando il [Vault Key di Azure](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-187">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="0c7c7-188">Per un esempio pratico del modo in cui è possibile proteggere l'app, vedere [gestire i segreti nelle app del server con il Vault Key di Azure](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="0c7c7-189">Negli esempi seguenti, utilizzare l'ID tenant di un utente per verificare che lo script funzioni.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="0c7c7-190">Ottenere un token di accesso tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c7c7-190">Get an access token using PowerShell</span></span>

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="0c7c7-191">Ottenere un token di accesso tramite C\#</span><span class="sxs-lookup"><span data-stu-id="0c7c7-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="0c7c7-192">Il codice seguente è stato testato con NuGet Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="0c7c7-193">Creare una nuova applicazione console.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-193">Create a new console application.</span></span>
1. <span data-ttu-id="0c7c7-194">Installare NuGet [Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="0c7c7-195">Aggiungere la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="0c7c7-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="0c7c7-196">Copiare e incollare il codice seguente nell'app (non dimenticare di aggiornare le tre variabili: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="0c7c7-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="0c7c7-197">Ottenere un token di accesso tramite Python</span><span class="sxs-lookup"><span data-stu-id="0c7c7-197">Get an access token using Python</span></span>

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="0c7c7-198">Ottenere un token di accesso tramite CURL</span><span class="sxs-lookup"><span data-stu-id="0c7c7-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="0c7c7-199">Curl è preinstallato in Windows 10, versione 1803 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="0c7c7-200">Per altre versioni di Windows, scaricare e installare lo strumento direttamente dal [sito web ufficiale di curl](https://curl.haxx.se/windows/).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="0c7c7-201">Aprire una finestra del prompt dei comandi e impostare CLIENT_ID sull'ID dell'applicazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="0c7c7-202">Impostare CLIENT_SECRET per l'applicazione di Azure segreta.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="0c7c7-203">Impostare TENANT_ID sull'ID tenant di Azure dell'utente che desidera utilizzare l'app per accedere a Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="0c7c7-204">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0c7c7-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="0c7c7-205">Una risposta corretta avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0c7c7-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="0c7c7-206">Convalidare il token</span><span class="sxs-lookup"><span data-stu-id="0c7c7-206">Validate the token</span></span>

1. <span data-ttu-id="0c7c7-207">Copiare e incollare il token nel [sito Web di convalida del token Web JSON, JWT,](https://jwt.ms) per decodificarlo.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="0c7c7-208">Verificare che l'attestazione dei *ruoli* all'interno del token decodificato contenga le autorizzazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="0c7c7-209">Nell'immagine seguente, è possibile visualizzare un token decodificato acquisito da un'app, con ```Incidents.Read.All``` , ```Incidents.ReadWrite.All``` e le ```AdvancedHunting.Read.All``` autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="0c7c7-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Immagine della convalida dei token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="0c7c7-211">Utilizzare il token per accedere all'API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c7c7-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="0c7c7-212">Scegliere l'API che si desidera utilizzare (operazioni non consentite o ricerca avanzata).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="0c7c7-213">Per ulteriori informazioni, vedere [API di Microsoft 365 Defender supportate](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="0c7c7-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="0c7c7-214">Nella richiesta HTTP che si sta per inviare, impostare l'intestazione di autorizzazione su `"Bearer" <token>` , *portatore* che è lo schema di autorizzazione e *token* che è il token convalidato.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="0c7c7-215">Il token scadrà entro un'ora.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-215">The token will expire within one hour.</span></span> <span data-ttu-id="0c7c7-216">È possibile inviare più di una richiesta durante questo periodo con lo stesso token.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="0c7c7-217">Nell'esempio riportato di seguito viene illustrato come inviare una richiesta per ottenere un elenco di operazioni non consentite **tramite C#**.</span><span class="sxs-lookup"><span data-stu-id="0c7c7-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="0c7c7-218">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="0c7c7-218">Related articles</span></span>

- [<span data-ttu-id="0c7c7-219">Panoramica delle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c7c7-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="0c7c7-220">Accedere alle API di Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c7c7-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="0c7c7-221">Creare un'applicazione ' Hello World '</span><span class="sxs-lookup"><span data-stu-id="0c7c7-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="0c7c7-222">Creare un'app per accedere a Microsoft 365 Defender senza un utente</span><span class="sxs-lookup"><span data-stu-id="0c7c7-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="0c7c7-223">Creare un'app per accedere alle API di Microsoft 365 Defender per conto di un utente</span><span class="sxs-lookup"><span data-stu-id="0c7c7-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="0c7c7-224">Informazioni sui limiti delle API e sulle licenze</span><span class="sxs-lookup"><span data-stu-id="0c7c7-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="0c7c7-225">Informazioni sui codici di errore</span><span class="sxs-lookup"><span data-stu-id="0c7c7-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="0c7c7-226">Gestione dei segreti nelle app del server con il Vault Key di Azure</span><span class="sxs-lookup"><span data-stu-id="0c7c7-226">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="0c7c7-227">OAuth 2,0 autorizzazione per l'accesso dell'utente e dell'API</span><span class="sxs-lookup"><span data-stu-id="0c7c7-227">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
