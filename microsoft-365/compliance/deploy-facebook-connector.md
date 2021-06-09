---
title: Distribuire un connettore per archiviare i dati delle pagine business di Facebook
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
description: Gli amministratori possono configurare un connettore nativo per importare e archiviare le pagine di Facebook Business Microsoft 365. Dopo aver importato questi dati in Microsoft 365, è possibile utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire la governance dei dati di Facebook dell'organizzazione.
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619952"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="14394-104">Distribuire un connettore per archiviare i dati delle pagine business di Facebook</span><span class="sxs-lookup"><span data-stu-id="14394-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="14394-105">In questo articolo sono contenute le procedure dettagliate per distribuire un connettore che utilizza il servizio di importazione di Office 365 per importare i dati dalle pagine business di Facebook a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14394-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="14394-106">Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore di Facebook, vedere [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="14394-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="14394-107">Passaggio 1: Creare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="14394-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="14394-108">Accedere a <https://portal.azure.com> e accedere utilizzando le credenziali di un account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="14394-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![Creare app in AAD](../media/FBCimage1.png)

2. <span data-ttu-id="14394-110">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="14394-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Fare clic Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="14394-112">Nel riquadro di spostamento sinistro fare clic su **Registrazioni app (anteprima)** e quindi su **Nuova registrazione.**</span><span class="sxs-lookup"><span data-stu-id="14394-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Fai clic su **Registrazioni app (Anteprima)** e quindi fai clic su **Nuova registrazione**](../media/FBCimage3.png)

4. <span data-ttu-id="14394-114">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="14394-114">Register the application.</span></span> <span data-ttu-id="14394-115">In URI di reindirizzamento seleziona Web nell'elenco a discesa tipo di applicazione e quindi digita <https://portal.azure.com> nella casella per l'URI.</span><span class="sxs-lookup"><span data-stu-id="14394-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Registrare l'applicazione](../media/FBCimage4.png)

5. <span data-ttu-id="14394-117">Copiare **l'ID applicazione (client)** **e l'ID directory (tenant)** e salvarli in un file di testo o in un altro percorso sicuro.</span><span class="sxs-lookup"><span data-stu-id="14394-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="14394-118">Questi ID vengono utilizzati nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="14394-118">You use these IDs in later steps.</span></span>

   ![Copiare l'ID applicazione e l'ID directory e salvarli](../media/FBCimage5.png)

6. <span data-ttu-id="14394-120">Vai a **Certificati & segreti per la nuova app.**</span><span class="sxs-lookup"><span data-stu-id="14394-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Vai a Certificati & segreti per la nuova app](../media/FBCimage6.png)

7. <span data-ttu-id="14394-122">Fare **clic su Nuovo segreto client**</span><span class="sxs-lookup"><span data-stu-id="14394-122">Click **New client secret**</span></span>

   ![Fare clic su Nuovo segreto client](../media/FBCimage7.png)

8. <span data-ttu-id="14394-124">Creare un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="14394-124">Create a new secret.</span></span> <span data-ttu-id="14394-125">Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza.</span><span class="sxs-lookup"><span data-stu-id="14394-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![Digitare il segreto e quindi scegliere un periodo di scadenza](../media/FBCimage8.png)

9. <span data-ttu-id="14394-127">Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="14394-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="14394-128">Si tratta del segreto dell'applicazione AAD utilizzato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="14394-128">This is the AAD application secret that you use in later steps.</span></span>

   ![Copiare il valore del segreto e salvarlo](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="14394-130">Passaggio 2: Distribuire il servizio Web del connettore da GitHub all'account Azure</span><span class="sxs-lookup"><span data-stu-id="14394-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="14394-131">Accedere a [questo sito GitHub e](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) fare clic su **Distribuisci in Azure**.</span><span class="sxs-lookup"><span data-stu-id="14394-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Fare clic su Distribuisci in Azure](../media/FBCGithubApp.png)

2. <span data-ttu-id="14394-133">Dopo aver fatto **clic su Distribuisci in Azure,** si verrà reindirizzati a un portale di Azure con una pagina modello personalizzata.</span><span class="sxs-lookup"><span data-stu-id="14394-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="14394-134">Compila i dettagli **di** base e **Impostazioni** e quindi fai clic su **Acquista.**</span><span class="sxs-lookup"><span data-stu-id="14394-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="14394-135">**Sottoscrizione:** Selezionare la sottoscrizione di Azure in cui si desidera distribuire il servizio Web del connettore pagine business di Facebook.</span><span class="sxs-lookup"><span data-stu-id="14394-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="14394-136">**Gruppo di risorse:** Scegliere o creare un nuovo gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="14394-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="14394-137">Un gruppo di risorse è un contenitore che contiene le risorse correlate per una soluzione di Azure.</span><span class="sxs-lookup"><span data-stu-id="14394-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="14394-138">**Posizione:** Scegliere una posizione.</span><span class="sxs-lookup"><span data-stu-id="14394-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="14394-139">**Nome app Web:** Specificare un nome univoco per l'app Web del connettore.</span><span class="sxs-lookup"><span data-stu-id="14394-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="14394-140">Il nome deve avere una lunghezza compresa tra 3 e 18 caratteri.</span><span class="sxs-lookup"><span data-stu-id="14394-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="14394-141">Questo nome viene usato per creare l'URL del servizio app di Azure. Ad esempio, se fornisci il nome dell'app Web **fbconnector,** l'URL del servizio app di Azure sarà **fbconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="14394-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="14394-142">**tenantId:** ID tenant dell'organizzazione Microsoft 365 che hai copiato dopo aver creato l'app del connettore di Facebook in Azure Active Directory nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="14394-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="14394-143">**APISecretKey:** È possibile digitare qualsiasi valore come segreto.</span><span class="sxs-lookup"><span data-stu-id="14394-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="14394-144">Viene usato per accedere all'app Web del connettore nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="14394-144">This is used to access the connector web app in Step 5.</span></span>

     ![Fare clic su Crea una risorsa e digitare l'account di archiviazione](../media/FBCimage12.png)

3. <span data-ttu-id="14394-146">Una volta completata la distribuzione, la pagina avrà un aspetto simile allo screenshot seguente:</span><span class="sxs-lookup"><span data-stu-id="14394-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Fare Archiviazione e quindi fare clic su Archiviazione account](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="14394-148">Passaggio 3: registrare l'app Facebook</span><span class="sxs-lookup"><span data-stu-id="14394-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="14394-149">Vai a , accedi usando le credenziali per l'account per le pagine Facebook Business dell'organizzazione e quindi fai <https://developers.facebook.com> clic su Aggiungi nuova **app.**</span><span class="sxs-lookup"><span data-stu-id="14394-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Aggiungere una nuova app per la pagina aziendale di Facebook](../media/FBCimage25.png)

2. <span data-ttu-id="14394-151">Crea un nuovo ID app.</span><span class="sxs-lookup"><span data-stu-id="14394-151">Create a new app ID.</span></span>

   ![Creare un nuovo ID app](../media/FBCimage26.png)

3. <span data-ttu-id="14394-153">Nel riquadro di spostamento sinistro fai clic **su Aggiungi prodotti** e quindi fai clic su **Configura** nel riquadro Accesso **a Facebook.**</span><span class="sxs-lookup"><span data-stu-id="14394-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Fare clic su Aggiungi prodotti](../media/FBCimage27.png)

4. <span data-ttu-id="14394-155">Nella pagina Integrare l'accesso a Facebook fare clic su **Web.**</span><span class="sxs-lookup"><span data-stu-id="14394-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Fare clic su Web nella pagina Integra account di accesso di Facebook](../media/FBCimage28.png)

5. <span data-ttu-id="14394-157">Aggiungere l'URL del servizio app di Azure; ad esempio `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="14394-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Aggiungere l'URL del servizio app di Azure](../media/FBCimage29.png)

6. <span data-ttu-id="14394-159">Completa la sezione QuickStart della configurazione dell'accesso a Facebook.</span><span class="sxs-lookup"><span data-stu-id="14394-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Completare la sezione Guida introduttiva](../media/FBCimage30.png)

7. <span data-ttu-id="14394-161">Nel riquadro di spostamento sinistro in **Accesso a Facebook,** fare clic su **Impostazioni** e aggiungere l'URI di reindirizzamento OAuth nella casella URI di reindirizzamento **OAuth** validi.</span><span class="sxs-lookup"><span data-stu-id="14394-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="14394-162">Utilizzare il formato **\<connectorserviceuri> /Views/FacebookOAuth**, dove il valore per connectorserviceuri è l'URL del servizio app di Azure per l'organizzazione, ad esempio `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="14394-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Aggiungere l'URI di reindirizzamento OAuth alla casella URI di reindirizzamento OAuth validi](../media/FBCimage31.png)

8. <span data-ttu-id="14394-164">Nel riquadro di spostamento sinistro fare clic **su Aggiungi prodotti** e quindi su **Webhook.**</span><span class="sxs-lookup"><span data-stu-id="14394-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="14394-165">Nel menu **a** discesa Pagina fare clic su **Pagina.**</span><span class="sxs-lookup"><span data-stu-id="14394-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![Fare clic su Aggiungi prodotti e quindi su \*\*Webhook](../media/FBCimage32.png)

9. <span data-ttu-id="14394-167">Aggiungere l'URL di richiamata webhook e aggiungere un token di verifica.</span><span class="sxs-lookup"><span data-stu-id="14394-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="14394-168">Il formato dell'URL di richiamata, utilizzare il formato **<connectorserviceuri> /api/FbPageWebhook**, dove il valore per connectorserviceuri è l'URL del servizio app azure per l'organizzazione, ad esempio `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="14394-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="14394-169">Il token di verifica deve essere simile a una password complessa.</span><span class="sxs-lookup"><span data-stu-id="14394-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="14394-170">Copiare il token di verifica in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="14394-170">Copy the verify token to a text file or other storage location.</span></span>

   ![Aggiungere il token di verifica](../media/FBCimage33.png)

10. <span data-ttu-id="14394-172">Testare e sottoscrivere l'endpoint per il feed.</span><span class="sxs-lookup"><span data-stu-id="14394-172">Test and subscribe to the endpoint for feed.</span></span>

    ![Testare e sottoscrivere l'endpoint](../media/FBCimage34.png)

11. <span data-ttu-id="14394-174">Aggiungi un URL di privacy, un'icona dell'app e l'uso aziendale.</span><span class="sxs-lookup"><span data-stu-id="14394-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="14394-175">Copia inoltre l'ID dell'app e il segreto dell'app in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="14394-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Aggiungere un URL di privacy, un'icona dell'app e un uso aziendale](../media/FBCimage35.png)

12. <span data-ttu-id="14394-177">Rendi pubblica l'app.</span><span class="sxs-lookup"><span data-stu-id="14394-177">Make the app public.</span></span>

    ![Rendere pubblica l'app](../media/FBCimage36.png)

13. <span data-ttu-id="14394-179">Aggiungere un utente al ruolo di amministratore o tester.</span><span class="sxs-lookup"><span data-stu-id="14394-179">Add user to the admin or tester role.</span></span>

    ![Aggiungere un utente al ruolo di amministratore o tester](../media/FBCimage37.png)

14. <span data-ttu-id="14394-181">Aggiungere **l'autorizzazione Accesso contenuto pubblico pagina.**</span><span class="sxs-lookup"><span data-stu-id="14394-181">Add the **Page Public Content Access** permission.</span></span>

    ![dd l'autorizzazione di accesso al contenuto pubblico della pagina](../media/FBCimage38.png)

15. <span data-ttu-id="14394-183">Aggiungere l'autorizzazione Gestione pagine.</span><span class="sxs-lookup"><span data-stu-id="14394-183">Add Manage Pages permission.</span></span>

    ![Aggiunta dell'autorizzazione Gestione pagine](../media/FBCimage39.png)

16. <span data-ttu-id="14394-185">Ottenere l'applicazione esaminata da Facebook.</span><span class="sxs-lookup"><span data-stu-id="14394-185">Get the application reviewed by Facebook.</span></span>

    ![Ottenere l'applicazione esaminata da Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="14394-187">Passaggio 4: Configurare l'app Web del connettore</span><span class="sxs-lookup"><span data-stu-id="14394-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="14394-188">Passare a (dove AzureAppResourceName è il nome della risorsa app di Azure denominata `https://<AzureAppResourceName>.azurewebsites.net` nel passaggio 4).</span><span class="sxs-lookup"><span data-stu-id="14394-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="14394-189">Ad esempio, se il nome è **fbconnector**, passare a `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="14394-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="14394-190">La home page dell'app sarà simile alla schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="14394-190">The home page of the app will look like the following screenshot:</span></span>

   ![Vai all'app Web connettore](../media/FBCimage41.png)

2. <span data-ttu-id="14394-192">Fare **clic su** Configura per visualizzare una pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="14394-192">Click **Configure** to display a sign in page.</span></span>

   ![Fare clic su Configura per visualizzare una pagina di accesso](../media/FBCimage42.png)

3. <span data-ttu-id="14394-194">Nella casella ID tenant digitare o incollare l'ID tenant ottenuto nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="14394-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="14394-195">Nella casella password digitare o **incollare** APISecretKey (ottenuto nel passaggio 2), quindi fare clic su Imposta configurazione Impostazioni per visualizzare la pagina dei dettagli della configurazione.</span><span class="sxs-lookup"><span data-stu-id="14394-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Accedi usando l'ID tenant e la password e passa alla pagina dei dettagli della configurazione](../media/FBCimage43.png)

4. <span data-ttu-id="14394-197">Immettere le impostazioni di configurazione seguenti</span><span class="sxs-lookup"><span data-stu-id="14394-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="14394-198">**ID applicazione Facebook:** ID dell'app per l'applicazione Facebook ottenuta nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="14394-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="14394-199">**Segreto dell'applicazione Facebook:** Segreto dell'app per l'applicazione Facebook ottenuta nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="14394-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="14394-200">**I webhook di Facebook verificano il token:** Token di verifica creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="14394-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="14394-201">**ID applicazione AAD:** ID dell'applicazione Azure Active Directory'app creata nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="14394-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="14394-202">**Segreto applicazione AAD:** Valore per il segreto APISecretKey creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="14394-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="14394-203">Fare **clic su** Salva per salvare le impostazioni del connettore.</span><span class="sxs-lookup"><span data-stu-id="14394-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="14394-204">Passaggio 5: Configurare un connettore di Facebook nel Centro Microsoft 365 conformità</span><span class="sxs-lookup"><span data-stu-id="14394-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="14394-205">Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fai clic su **Connettori dati** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="14394-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="14394-206">Nella pagina **Connettori dati in** Pagine **aziendali di Facebook** fare clic su **Visualizza.**</span><span class="sxs-lookup"><span data-stu-id="14394-206">On the **Data connectors** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="14394-207">Nella pagina **Pagine aziendali di Facebook** fare clic su Aggiungi **connettore.**</span><span class="sxs-lookup"><span data-stu-id="14394-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="14394-208">Nella pagina **Condizioni di servizio** fare clic su **Accetta.**</span><span class="sxs-lookup"><span data-stu-id="14394-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="14394-209">Nella pagina **Aggiungi credenziali per l'app connettore** immettere le informazioni seguenti e quindi fare clic su **Convalida connessione.**</span><span class="sxs-lookup"><span data-stu-id="14394-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Immettere le credenziali dell'app connettore](../media/TCimage38.png)

   - <span data-ttu-id="14394-211">Nella casella **Nome** digitare un nome per il connettore, ad esempio **Pagina notizie di Facebook.**</span><span class="sxs-lookup"><span data-stu-id="14394-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="14394-212">Nella casella **URL connessione** digitare o incollare l'URL del servizio app di Azure. ad esempio `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="14394-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="14394-213">Nella casella **Password** digitare o incollare il valore dell'APISecretKey aggiunto nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="14394-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="14394-214">Nella casella **ID app azure** digitare o incollare il valore dell'ID applicazione (client) chiamato anche come ID applicazione AAD creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="14394-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="14394-215">Dopo aver convalidato correttamente la connessione, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="14394-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="14394-216">Nella pagina **Autorizza Microsoft 365 importare** dati digitare o incollare di nuovo APISecretKey e quindi fare clic su **Accedi all'app Web.**</span><span class="sxs-lookup"><span data-stu-id="14394-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="14394-217">Nella pagina **Configura l'app del connettore di Facebook** fare clic su Accedi con **Facebook** ed eseguire l'accesso utilizzando le credenziali per l'account per le pagine Facebook Business dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14394-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="14394-218">Assicurati che all'account Facebook a cui hai effettuato l'accesso sia assegnato il ruolo di amministratore per le pagine Facebook Business dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="14394-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Accedere con Facebook](../media/FBCimage50.png)

9. <span data-ttu-id="14394-220">Viene visualizzato un elenco delle pagine business gestite dall'account Facebook a cui hai effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="14394-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="14394-221">Selezionare la pagina da archiviare e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="14394-221">Select the page to archive and then click **Next**.</span></span>

   ![Selezionare la pagina aziendale dell'organizzazione che si desidera archiviare](../media/FBCimage52.png)

10. <span data-ttu-id="14394-223">Fare **clic su** Continua per uscire dall'installazione dell'app del servizio connettore.</span><span class="sxs-lookup"><span data-stu-id="14394-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="14394-224">Nella pagina **Imposta filtri** è possibile applicare un filtro per importare inizialmente elementi di una determinata età.</span><span class="sxs-lookup"><span data-stu-id="14394-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="14394-225">Selezionare un'età e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="14394-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="14394-226">Nella pagina **Scegli percorso di archiviazione** digitare l'indirizzo di Microsoft 365 di posta elettronica in cui verranno importati gli elementi di Facebook e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="14394-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="14394-227">Fare **clic su** Avanti per esaminare le impostazioni del connettore e quindi fare clic su **Fine** per completare la configurazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="14394-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="14394-228">Nel Centro conformità passare alla pagina **Connettori** di dati e fare clic sulla scheda **Connettori** per visualizzare l'avanzamento del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="14394-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
