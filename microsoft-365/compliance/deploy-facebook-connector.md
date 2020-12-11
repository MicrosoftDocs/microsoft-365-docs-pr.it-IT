---
title: Distribuire un connettore per archiviare i dati di pagine business di Facebook
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori possono configurare un connettore nativo per l'importazione e l'archiviazione di pagine business di Facebook su Microsoft 365. Dopo aver importato i dati in Microsoft 365, è possibile utilizzare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire la governance dei dati di Facebook dell'organizzazione.
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619952"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="4ee91-104">Distribuire un connettore per archiviare i dati di pagine business di Facebook</span><span class="sxs-lookup"><span data-stu-id="4ee91-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="4ee91-105">Questo articolo contiene il processo dettagliato per la distribuzione di un connettore che utilizza il servizio di importazione di Office 365 per importare i dati dalle pagine business di Facebook a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4ee91-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="4ee91-106">Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore Facebook, vedere [configurare un connettore per archiviare i dati di Facebook](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="4ee91-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="4ee91-107">Passaggio 1: creare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4ee91-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="4ee91-108">Passare a <https://portal.azure.com> e accedere con le credenziali di un account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="4ee91-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![Creare un'app in AAD](../media/FBCimage1.png)

2. <span data-ttu-id="4ee91-110">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Fare clic su Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="4ee91-112">Nel riquadro di spostamento a sinistra, fare clic su **registrazioni app (anteprima)** e quindi fare clic su **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Fare clic su \* \* registrazioni app (anteprima) \* \* e quindi fare clic su \* \* nuova registrazione \* \*](../media/FBCimage3.png)

4. <span data-ttu-id="4ee91-114">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ee91-114">Register the application.</span></span> <span data-ttu-id="4ee91-115">In URI di reindirizzamento, selezionare Web nell'elenco a discesa tipo di applicazione e quindi digitare <https://portal.azure.com> nella casella per l'URI.</span><span class="sxs-lookup"><span data-stu-id="4ee91-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Registrare l'applicazione](../media/FBCimage4.png)

5. <span data-ttu-id="4ee91-117">Copiare l'ID dell' **applicazione (client)** e la **Directory (tenant)** e salvarli in un file di testo o in un'altra posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="4ee91-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="4ee91-118">È possibile utilizzare questi ID nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="4ee91-118">You use these IDs in later steps.</span></span>

   ![Copiare l'ID applicazione e l'ID directory e salvarli](../media/FBCimage5.png)

6. <span data-ttu-id="4ee91-120">Accedere a **certificati & segreti per la nuova app.**</span><span class="sxs-lookup"><span data-stu-id="4ee91-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Accedere a certificati & segreti per la nuova applicazione](../media/FBCimage6.png)

7. <span data-ttu-id="4ee91-122">Fare clic su **nuovo client segreto**</span><span class="sxs-lookup"><span data-stu-id="4ee91-122">Click **New client secret**</span></span>

   ![Fare clic su nuovo client segreto](../media/FBCimage7.png)

8. <span data-ttu-id="4ee91-124">Creare un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="4ee91-124">Create a new secret.</span></span> <span data-ttu-id="4ee91-125">Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza.</span><span class="sxs-lookup"><span data-stu-id="4ee91-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![Digita il segreto e quindi scegli un periodo di scadenza](../media/FBCimage8.png)

9. <span data-ttu-id="4ee91-127">Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="4ee91-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="4ee91-128">Si tratta del segreto dell'applicazione AAD utilizzato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="4ee91-128">This is the AAD application secret that you use in later steps.</span></span>

   ![Copiare il valore del segreto e salvarlo](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="4ee91-130">Passaggio 2: distribuire il servizio Web del connettore da GitHub all'account di Azure</span><span class="sxs-lookup"><span data-stu-id="4ee91-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="4ee91-131">Accedere a [questo sito GitHub](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) e fare clic su **Distribuisci in Azure**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Fare clic su Distribuisci in Azure](../media/FBCGithubApp.png)

2. <span data-ttu-id="4ee91-133">Dopo aver fatto clic su **Distribuisci in Azure**, verrà reindirizzato a un portale di Azure con una pagina modello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4ee91-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="4ee91-134">Compilare i dettagli delle **Impostazioni e delle** informazioni di **base** e quindi fare clic su **acquisto**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="4ee91-135">**Sottoscrizione:** Selezionare l'abbonamento di Azure in cui si desidera distribuire il servizio Web del connettore di pagine business di Facebook.</span><span class="sxs-lookup"><span data-stu-id="4ee91-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="4ee91-136">**Gruppo di risorse:** Scegliere o creare un nuovo gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="4ee91-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="4ee91-137">Un gruppo di risorse è un contenitore che contiene risorse correlate per una soluzione di Azure.</span><span class="sxs-lookup"><span data-stu-id="4ee91-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="4ee91-138">**Posizione:** Scegliere un percorso.</span><span class="sxs-lookup"><span data-stu-id="4ee91-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="4ee91-139">**Nome applicazione Web:** Specificare un nome univoco per il connettore Web App.</span><span class="sxs-lookup"><span data-stu-id="4ee91-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="4ee91-140">Il nome del Th deve essere compreso tra 3 e 18 caratteri.</span><span class="sxs-lookup"><span data-stu-id="4ee91-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="4ee91-141">Questo nome viene utilizzato per creare l'URL del servizio app di Azure. ad esempio, se si specifica il nome dell'applicazione Web di **fbconnector** , l'URL del servizio app di Azure sarà **fbconnector.azurewebsites.NET**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="4ee91-142">**tenantId:** L'ID tenant dell'organizzazione Microsoft 365 copiato dopo aver creato l'app connettore Facebook in Azure Active Directory nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="4ee91-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="4ee91-143">**APISecretKey:** È possibile digitare qualsiasi valore come segreto.</span><span class="sxs-lookup"><span data-stu-id="4ee91-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="4ee91-144">Viene utilizzato per accedere all'applicazione Web del connettore nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="4ee91-144">This is used to access the connector web app in Step 5.</span></span>

     ![Fare clic su Crea un account di archiviazione di risorse e tipi](../media/FBCimage12.png)

3. <span data-ttu-id="4ee91-146">Dopo che la distribuzione ha avuto esito positivo, la pagina avrà un aspetto simile alla schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="4ee91-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Fare clic su archiviazione e quindi su account di archiviazione](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="4ee91-148">Passaggio 3: registrare l'app Facebook</span><span class="sxs-lookup"><span data-stu-id="4ee91-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="4ee91-149">Accedere a <https://developers.facebook.com> , eseguire l'accesso usando le credenziali per l'account per le pagine business di Facebook dell'organizzazione e quindi fare clic su **Aggiungi nuova app**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Aggiungere una nuova app per la pagina business di Facebook](../media/FBCimage25.png)

2. <span data-ttu-id="4ee91-151">Creare un nuovo ID app.</span><span class="sxs-lookup"><span data-stu-id="4ee91-151">Create a new app ID.</span></span>

   ![Creare un nuovo ID app](../media/FBCimage26.png)

3. <span data-ttu-id="4ee91-153">Nel riquadro di spostamento a sinistra, fare clic su **Aggiungi prodotti** e quindi fare clic su **Configura** nella sezione **login Facebook** .</span><span class="sxs-lookup"><span data-stu-id="4ee91-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Fare clic su Aggiungi prodotti](../media/FBCimage27.png)

4. <span data-ttu-id="4ee91-155">Nella pagina integrazione account di accesso di Facebook fare clic su **Web**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Fare clic su Web nella pagina integrazione login Facebook](../media/FBCimage28.png)

5. <span data-ttu-id="4ee91-157">Aggiungere l'URL del servizio app di Azure; ad esempio `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="4ee91-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Aggiungere l'URL del servizio app di Azure](../media/FBCimage29.png)

6. <span data-ttu-id="4ee91-159">Completare la sezione Guida introduttiva della configurazione dell'account di accesso di Facebook.</span><span class="sxs-lookup"><span data-stu-id="4ee91-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Completare la sezione Guida introduttiva](../media/FBCimage30.png)

7. <span data-ttu-id="4ee91-161">Nel riquadro di spostamento a sinistra in **login Facebook**, fare clic su **Impostazioni** e aggiungere l'URI di reindirizzamento OAuth nella casella **Valid URI di reindirizzamento OAuth** .</span><span class="sxs-lookup"><span data-stu-id="4ee91-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="4ee91-162">Utilizzare il formato **\<connectorserviceuri> /views/FacebookOAuth**, in cui il valore di CONNECTORSERVICEURI è l'URL del servizio app di Azure per l'organizzazione, ad esempio `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="4ee91-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Aggiungere l'URI di reindirizzamento OAuth alla casella degli URI di reindirizzamento OAuth validi](../media/FBCimage31.png)

8. <span data-ttu-id="4ee91-164">Nel riquadro di spostamento a sinistra, fare clic su **Aggiungi prodotti** e quindi fare clic su **webhook.**</span><span class="sxs-lookup"><span data-stu-id="4ee91-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="4ee91-165">Nel menu a discesa della **pagina** , fare clic su **pagina**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![Fare clic su Aggiungi prodotti e quindi su \* \* webhooks](../media/FBCimage32.png)

9. <span data-ttu-id="4ee91-167">Aggiungere l'URL di callback di Webhook e aggiungere un token di verifica.</span><span class="sxs-lookup"><span data-stu-id="4ee91-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="4ee91-168">Il formato dell'URL di callback, utilizzare il formato **<connectorserviceuri> /API/FbPageWebhook**, in cui il valore di CONNECTORSERVICEURI è l'URL del servizio app di Azure per l'organizzazione, ad esempio `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="4ee91-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="4ee91-169">Il token di verifica dovrebbe essere simile a una password complessa.</span><span class="sxs-lookup"><span data-stu-id="4ee91-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="4ee91-170">Copiare il token di verifica in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="4ee91-170">Copy the verify token to a text file or other storage location.</span></span>

   ![Aggiungere il token di verifica](../media/FBCimage33.png)

10. <span data-ttu-id="4ee91-172">Testare e sottoscrivere l'endpoint per il feed.</span><span class="sxs-lookup"><span data-stu-id="4ee91-172">Test and subscribe to the endpoint for feed.</span></span>

    ![Testare e sottoscrivere l'endpoint](../media/FBCimage34.png)

11. <span data-ttu-id="4ee91-174">Aggiungere un URL di privacy, un'icona dell'app e un utilizzo aziendale.</span><span class="sxs-lookup"><span data-stu-id="4ee91-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="4ee91-175">Inoltre, copiare l'ID app e l'applicazione segreta in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="4ee91-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Aggiungere un URL di privacy, un'icona App e un utilizzo aziendale](../media/FBCimage35.png)

12. <span data-ttu-id="4ee91-177">Rendere pubblico l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4ee91-177">Make the app public.</span></span>

    ![Rendere pubblico l'app](../media/FBCimage36.png)

13. <span data-ttu-id="4ee91-179">Aggiungere un utente al ruolo di amministratore o tester.</span><span class="sxs-lookup"><span data-stu-id="4ee91-179">Add user to the admin or tester role.</span></span>

    ![Aggiungere un utente al ruolo di amministratore o tester](../media/FBCimage37.png)

14. <span data-ttu-id="4ee91-181">Aggiungere l'autorizzazione di **accesso al contenuto pubblico della pagina** .</span><span class="sxs-lookup"><span data-stu-id="4ee91-181">Add the **Page Public Content Access** permission.</span></span>

    ![dd la pagina autorizzazione di accesso al contenuto pubblico](../media/FBCimage38.png)

15. <span data-ttu-id="4ee91-183">Aggiungere l'autorizzazione Manage Pages.</span><span class="sxs-lookup"><span data-stu-id="4ee91-183">Add Manage Pages permission.</span></span>

    ![Aggiungere l'autorizzazione Gestisci pagine](../media/FBCimage39.png)

16. <span data-ttu-id="4ee91-185">Ottenere l'applicazione recensita da Facebook.</span><span class="sxs-lookup"><span data-stu-id="4ee91-185">Get the application reviewed by Facebook.</span></span>

    ![Ottenere l'applicazione recensita da Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="4ee91-187">Passaggio 4: configurare l'applicazione Web del connettore</span><span class="sxs-lookup"><span data-stu-id="4ee91-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="4ee91-188">Andare a `https://<AzureAppResourceName>.azurewebsites.net` (dove AzureAppResourceName è il nome della risorsa di Azure App denominata nel passaggio 4).</span><span class="sxs-lookup"><span data-stu-id="4ee91-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="4ee91-189">Ad esempio, se il nome è **fbconnector**, andare a `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="4ee91-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="4ee91-190">La Home page dell'app avrà lo stesso aspetto della schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="4ee91-190">The home page of the app will look like the following screenshot:</span></span>

   ![Accedere all'applicazione Web del connettore](../media/FBCimage41.png)

2. <span data-ttu-id="4ee91-192">Fare clic su **Configura** per visualizzare una pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="4ee91-192">Click **Configure** to display a sign in page.</span></span>

   ![Fare clic su Configura per visualizzare una pagina di accesso](../media/FBCimage42.png)

3. <span data-ttu-id="4ee91-194">Nella casella ID tenant digitare o incollare l'ID tenant (ottenuto nel passaggio 2).</span><span class="sxs-lookup"><span data-stu-id="4ee91-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="4ee91-195">Nella casella password digitare o incollare il APISecretKey (ottenuto nel passaggio 2), quindi fare clic su **imposta impostazioni di configurazione** per visualizzare la pagina dettagli di configurazione.</span><span class="sxs-lookup"><span data-stu-id="4ee91-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Accedere con l'ID e la password del tenant e passare alla pagina dei dettagli di configurazione](../media/FBCimage43.png)

4. <span data-ttu-id="4ee91-197">Immettere le impostazioni di configurazione seguenti</span><span class="sxs-lookup"><span data-stu-id="4ee91-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="4ee91-198">**ID applicazione Facebook:** ID app per l'applicazione Facebook ottenuta al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="4ee91-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="4ee91-199">**Segreto dell'applicazione Facebook:** Il segreto dell'app per l'applicazione Facebook ottenuta al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="4ee91-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="4ee91-200">I **webhook di Facebook verificano il token:** Il token di verifica creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="4ee91-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="4ee91-201">**ID applicazione AAD:** ID applicazione per l'app Azure Active Directory creata al passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="4ee91-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="4ee91-202">**Segreto dell'applicazione AAD:** Il valore del segreto di APISecretKey creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="4ee91-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="4ee91-203">Fare clic su **Salva** per salvare le impostazioni del connettore.</span><span class="sxs-lookup"><span data-stu-id="4ee91-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="4ee91-204">Passaggio 5: configurare un connettore Facebook nel centro conformità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ee91-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="4ee91-205">Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fare clic su **connettori dati** nel NAV sinistro.</span><span class="sxs-lookup"><span data-stu-id="4ee91-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="4ee91-206">Nella pagina **connettori dati** in **pagine business di Facebook** fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-206">On the **Data connectors** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="4ee91-207">Nella pagina **Facebook business Pages** fare clic su **Aggiungi connettore**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="4ee91-208">Nella pagina **condizioni del servizio** fare clic su **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="4ee91-209">Nella pagina **Aggiungi credenziali per l'app del connettore** , immettere le informazioni seguenti e quindi fare clic su **convalida connessione**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Immettere le credenziali delle app del connettore](../media/TCimage38.png)

   - <span data-ttu-id="4ee91-211">Nella casella **nome** Digitare un nome per il connettore, ad esempio pagina di **notizie di Facebook**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="4ee91-212">Nella casella **URL di connessione** Digitare o incollare l'URL del servizio app di Azure; ad esempio `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="4ee91-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="4ee91-213">Nella casella **password** Digitare o incollare il valore dell'APISecretKey aggiunto nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="4ee91-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="4ee91-214">Nella casella **ID app di Azure** Digitare o incollare il valore dell'ID applicazione (client) denominato anche ID dell'applicazione AAD creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="4ee91-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="4ee91-215">Dopo aver convalidato correttamente la connessione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="4ee91-216">Nella pagina **autorizza Microsoft 365 per importare i dati** , digitare o incollare di nuovo APISecretKey e quindi fare clic su **login Web App**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="4ee91-217">Nella pagina **Configura applicazione del connettore Facebook** , fare clic su **account di accesso con Facebook** e accedere usando le credenziali per l'account per le pagine business di Facebook dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ee91-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="4ee91-218">Assicurarsi che l'account di Facebook a cui è stato effettuato l'accesso sia assegnato il ruolo di amministratore per le pagine business di Facebook dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4ee91-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Accedere con Facebook](../media/FBCimage50.png)

9. <span data-ttu-id="4ee91-220">Viene visualizzato un elenco delle pagine business gestite dall'account di Facebook in cui è stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="4ee91-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="4ee91-221">Selezionare la pagina da archiviare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-221">Select the page to archive and then click **Next**.</span></span>

   ![Selezionare la pagina aziendale dell'organizzazione che si desidera archiviare](../media/FBCimage52.png)

10. <span data-ttu-id="4ee91-223">Fare clic su **continua** per uscire dal programma di installazione dell'app del servizio connettore.</span><span class="sxs-lookup"><span data-stu-id="4ee91-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="4ee91-224">Nella pagina **Imposta filtri** è possibile applicare un filtro per importare inizialmente gli elementi di una determinata età.</span><span class="sxs-lookup"><span data-stu-id="4ee91-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="4ee91-225">Selezionare un'età, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="4ee91-226">Nella pagina **Scegli percorso di archiviazione** , digitare l'indirizzo di posta elettronica della cassetta postale di Microsoft 365 a cui verranno importati gli elementi di Facebook e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4ee91-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="4ee91-227">Fare clic su **Avanti** per esaminare le impostazioni del connettore e quindi fare clic su **fine** per completare la configurazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="4ee91-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="4ee91-228">Nel centro conformità, andare alla pagina **connettori dati** e fare clic sulla scheda **connettori** per visualizzare lo stato di avanzamento del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="4ee91-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
