---
title: Distribuire un connettore per archiviare i dati di Twitter
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori possono configurare un connettore nativo per importare e archiviare i dati di Twitter in Microsoft 365. Dopo aver importato i dati in Microsoft 365, è possibile utilizzare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire la governance dei dati di Twitter dell'organizzazione.
ms.openlocfilehash: 5a7d7749f99615d9fd6858be05cc63153cfe1d31
ms.sourcegitcommit: 9b390881fe661deb0568b4b86a5a9094f3c795f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269397"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="9f191-104">Distribuire un connettore per archiviare i dati di Twitter</span><span class="sxs-lookup"><span data-stu-id="9f191-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="9f191-105">Questo articolo contiene il processo dettagliato per la distribuzione di un connettore che utilizza il servizio di importazione di Office 365 per importare i dati dall'account Twitter dell'organizzazione a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f191-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="9f191-106">Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore Twitter, vedere [configurare un connettore per archiviare i dati di Twitter ](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="9f191-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="9f191-107">Passaggio 1: creare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9f191-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="9f191-108">Accedere a <https://portal.azure.com> e accedere con le credenziali di un account di amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9f191-108">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![Accedere a Azure](media/TCimage01.png)

2. <span data-ttu-id="9f191-110">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="9f191-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Accedere a Azure Active Directory](media/TCimage02.png)

3. <span data-ttu-id="9f191-112">Nel riquadro di spostamento a sinistra, fare clic su **registrazioni app (anteprima)** e quindi fare clic su **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="9f191-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Creare una nuova registrazione delle app](media/TCimage03.png)

4. <span data-ttu-id="9f191-114">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-114">Register the application.</span></span> <span data-ttu-id="9f191-115">In **URI di reindirizzamento (facoltativo)** selezionare **Web** nell'elenco a discesa tipo di applicazione e quindi `https://portal.azure.com` digitare nella casella relativa all'URI.</span><span class="sxs-lookup"><span data-stu-id="9f191-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="9f191-116">Tipo https://portal.azure.com per l'URI di Reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="9f191-116">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="9f191-117">Copiare l'ID dell' **applicazione (client)** e la **Directory (tenant)** e salvarli in un file di testo o in un'altra posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="9f191-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="9f191-118">È possibile utilizzare questi ID nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="9f191-118">You use these IDs in later steps.</span></span>

    ![Copiare e salvare l'ID applicazione e l'ID directory](media/TCimage05.png)

6. <span data-ttu-id="9f191-120">Accedere a **certificati & segreti per la nuova applicazione** e in **segreti client** fare clic su **nuovo segreto client**.</span><span class="sxs-lookup"><span data-stu-id="9f191-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Creare un nuovo segreto client](media/TCimage06.png)

7. <span data-ttu-id="9f191-122">Creare un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="9f191-122">Create a new secret.</span></span> <span data-ttu-id="9f191-123">Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza.</span><span class="sxs-lookup"><span data-stu-id="9f191-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Digitare il segreto e scegliere il periodo di scadenza](media/TCimage08.png)

8. <span data-ttu-id="9f191-125">Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="9f191-126">Si tratta del segreto dell'applicazione AAD utilizzato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="9f191-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Copia e salvataggio del segreto](media/TCimage09.png)

9. <span data-ttu-id="9f191-128">Andare a **manifest** e copiare il identifierUris (denominato anche URI dell'applicazione AAD) come evidenziato nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="9f191-128">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="9f191-129">Copiare l'URI dell'applicazione AAD in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-129">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="9f191-130">Viene utilizzato nel passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="9f191-130">You use it in Step 6.</span></span>

    ![Copiare e salvare l'URI dell'applicazione AAD](media/TCimage10.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="9f191-132">Passaggio 2: distribuire il servizio Web del connettore da GitHub all'account di Azure</span><span class="sxs-lookup"><span data-stu-id="9f191-132">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="9f191-133">Accedere a [questo sito GitHub](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) e fare clic su **Distribuisci in Azure**.</span><span class="sxs-lookup"><span data-stu-id="9f191-133">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Passare alla Home page di Azure](media/FBCimage11.png)

2. <span data-ttu-id="9f191-135">Dopo aver fatto clic su **Distribuisci in Azure**, verrà reindirizzato a un portale di Azure con una pagina modello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9f191-135">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="9f191-136">Compilare i dettagli delle **Impostazioni e delle** informazioni di **base** e quindi fare clic su **acquisto**.</span><span class="sxs-lookup"><span data-stu-id="9f191-136">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Fare clic su Crea un account di archiviazione di risorse e tipi](media/FBCimage12.png)

    - <span data-ttu-id="9f191-138">**Sottoscrizione:** Selezionare l'abbonamento di Azure in cui si desidera distribuire il servizio Web del connettore Twitter.</span><span class="sxs-lookup"><span data-stu-id="9f191-138">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="9f191-139">**Gruppo di risorse:** Scegliere o creare un nuovo gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="9f191-139">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="9f191-140">Un gruppo di risorse è un contenitore che contiene risorse correlate per una soluzione di Azure.</span><span class="sxs-lookup"><span data-stu-id="9f191-140">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="9f191-141">**Posizione:** Scegliere un percorso.</span><span class="sxs-lookup"><span data-stu-id="9f191-141">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="9f191-142">**Nome applicazione Web:** Specificare un nome univoco per il connettore Web App.</span><span class="sxs-lookup"><span data-stu-id="9f191-142">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="9f191-143">Il nome del Th deve essere compreso tra 3 e 18 caratteri.</span><span class="sxs-lookup"><span data-stu-id="9f191-143">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="9f191-144">Questo nome viene utilizzato per creare l'URL del servizio app di Azure. ad esempio, se si specifica il nome dell'applicazione Web di **twitterconnector** , l'URL del servizio app di Azure sarà **twitterconnector.azurewebsites.NET**.</span><span class="sxs-lookup"><span data-stu-id="9f191-144">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="9f191-145">**tenantId:** L'ID tenant dell'organizzazione Microsoft 365 copiato dopo aver creato l'app connettore Facebook in Azure Active Directory nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="9f191-145">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="9f191-146">**APISecretKey:** È possibile digitare qualsiasi valore come segreto.</span><span class="sxs-lookup"><span data-stu-id="9f191-146">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="9f191-147">Viene utilizzato per accedere all'applicazione Web del connettore nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="9f191-147">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="9f191-148">Dopo che la distribuzione ha avuto esito positivo, la pagina avrà un aspetto simile alla schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="9f191-148">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Fare clic su archiviazione e quindi su account di archiviazione](media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="9f191-150">Passaggio 3: creare l'app Twitter</span><span class="sxs-lookup"><span data-stu-id="9f191-150">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="9f191-151">Accedere a https://developer.twitter.com, eseguire l'accesso usando le credenziali per l'account di sviluppo per l'organizzazione, quindi fare clic su **app**.</span><span class="sxs-lookup"><span data-stu-id="9f191-151">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Accedere a https://developer.twitter.com ed eseguire l'accesso](media/TCimage25-5.png)
2. <span data-ttu-id="9f191-153">Fare clic su **Crea un'app**.</span><span class="sxs-lookup"><span data-stu-id="9f191-153">Click **Create an app**.</span></span>
   
   ![Vai alla pagina delle app per creare un'app](media/TCimage26.png)

3. <span data-ttu-id="9f191-155">In **Dettagli app**aggiungere informazioni sull'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-155">Under **App details**, add information about the application.</span></span>

   ![Immettere informazioni sull'app](media/TCimage27.png)

4. <span data-ttu-id="9f191-157">Nel dashboard per sviluppatori di Twitter, selezionare l'app appena creata e copiare l'ID app visualizzato e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-157">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="9f191-158">Quindi fare clic su **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9f191-158">Then click **Details**.</span></span>
   
   ![Copiare e salvare l'ID app](media/TCimage28.png)

5. <span data-ttu-id="9f191-160">Nella scheda **tasti e token** , in **tasti API consumer** copiare la chiave segreta API e salvarla in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-160">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="9f191-161">Fare quindi clic su **Crea** per generare un token di accesso e un segreto del token di accesso e copiarli in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-161">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![Copia e Salva in chiave segreta API](media/TCimage29.png)

   <span data-ttu-id="9f191-163">Fare quindi clic su **Crea** per generare un token di accesso e un segreto del token di accesso e copiarli in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-163">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="9f191-164">Fare clic sulla scheda **autorizzazioni** e configurare le autorizzazioni come illustrato nella schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="9f191-164">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Configurare le autorizzazioni](media/TCimage30.png)

7. <span data-ttu-id="9f191-166">Dopo aver salvato le impostazioni delle autorizzazioni, fare clic sulla scheda **Dettagli applicazione** e quindi fare clic su **modifica > modifica dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9f191-166">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Modificare i dettagli dell'app](media/TCimage31.png)

8. <span data-ttu-id="9f191-168">Eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f191-168">Do the following tasks:</span></span>

   - <span data-ttu-id="9f191-169">Seleziona la casella di controllo per consentire all'app del connettore di accedere a Twitter.</span><span class="sxs-lookup"><span data-stu-id="9f191-169">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="9f191-170">Aggiungere l'URI di reindirizzamento OAuth utilizzando il formato seguente: \*\* \<connectorserviceuri>/views/twitteroauth\*\*, in cui il valore di *connectorserviceuri* è l'URL del servizio app di Azure per l'organizzazione. ad esempio, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span><span class="sxs-lookup"><span data-stu-id="9f191-170">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Consenti all'app del connettore di accedere a Twitter e aggiungere l'URI di reindirizzamento OAuth](media/TCimage32.png)

<span data-ttu-id="9f191-172">L'app per sviluppatori di Twitter è ora pronta per essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="9f191-172">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="9f191-173">Passaggio 4: configurare l'applicazione Web del connettore</span><span class="sxs-lookup"><span data-stu-id="9f191-173">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="9f191-174">Passare a https://\<AzureAppResourceName>. azurewebsites.NET (dove **AzureAppResourceName** è il nome della risorsa di Azure App denominata nel passaggio 4).</span><span class="sxs-lookup"><span data-stu-id="9f191-174">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="9f191-175">Ad esempio, se il nome è **twitterconnector**, andare a https://twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="9f191-175">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="9f191-176">La Home page dell'app è simile alla schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="9f191-176">The home page of the app looks like the following screenshot:</span></span>

   ![Vai alla pagina delle risorse per le app di Azure](media/FBCimage41.png)

2. <span data-ttu-id="9f191-178">Fare clic su **Configura** per visualizzare una pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="9f191-178">Click **Configure** to display a sign in page.</span></span>

   ![Fare clic su Configura per visualizzare la pagina di accesso](media/FBCimage42.png)

3. <span data-ttu-id="9f191-180">Nella casella ID tenant digitare o incollare l'ID tenant (ottenuto nel passaggio 2).</span><span class="sxs-lookup"><span data-stu-id="9f191-180">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="9f191-181">Nella casella password digitare o incollare il APISecretKey (ottenuto nel passaggio 2), quindi fare clic su **imposta impostazioni di configurazione** per visualizzare la pagina dettagli di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-181">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Accedere utilizzando l'ID tenant e la chiave segreta dell'API](media/TCimage35.png)

4. <span data-ttu-id="9f191-183">Immettere le impostazioni di configurazione seguenti</span><span class="sxs-lookup"><span data-stu-id="9f191-183">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="9f191-184">**Chiave API di Twitter:** ID app per l'applicazione Twitter creata al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="9f191-184">**Twitter Api Key:** The app ID for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="9f191-185">**Chiave segreta API Twitter:** La chiave segreta API per l'applicazione Twitter creata al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="9f191-185">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="9f191-186">**Token di accesso Twitter:** Il token di accesso creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="9f191-186">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="9f191-187">**Segreto del token di accesso di Twitter:** Il segreto del token di accesso creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="9f191-187">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="9f191-188">**ID applicazione AAD:** ID applicazione per l'app Azure Active Directory creata al passaggio 1</span><span class="sxs-lookup"><span data-stu-id="9f191-188">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="9f191-189">**Segreto dell'applicazione AAD:** Il valore del segreto di APISecretKey creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="9f191-189">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="9f191-190">Fare clic su **Salva** per salvare le impostazioni del connettore.</span><span class="sxs-lookup"><span data-stu-id="9f191-190">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="9f191-191">Passaggio 5: configurare un connettore Twitter nel centro conformità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9f191-191">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="9f191-192">Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fare clic su **connettori dati** nel NAV sinistro.</span><span class="sxs-lookup"><span data-stu-id="9f191-192">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="9f191-193">Nella pagina **connettori dati (anteprima)** in **Twitter**, fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="9f191-193">On the **Data connectors (preview)** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="9f191-194">Nella pagina **Twitter** , fare clic su **Aggiungi connettore**.</span><span class="sxs-lookup"><span data-stu-id="9f191-194">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="9f191-195">Nella pagina **condizioni del servizio** fare clic su **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="9f191-195">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="9f191-196">Nella pagina **Aggiungi credenziali per l'app del connettore** , immettere le informazioni seguenti e quindi fare clic su **convalida connessione**.</span><span class="sxs-lookup"><span data-stu-id="9f191-196">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Immettere le credenziali delle app del connettore](media/TCimage38.png)

    - <span data-ttu-id="9f191-198">Nella casella **nome** Digitare un nome per il connettore, ad esempio la **maniglia della Guida di Twitter**.</span><span class="sxs-lookup"><span data-stu-id="9f191-198">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="9f191-199">Nella casella **URL connettore** Digitare o incollare l'URL del servizio app di Azure; ad esempio `https://twitterconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="9f191-199">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="9f191-200">Nella casella **password** Digitare o incollare il valore del APISecretKey creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="9f191-200">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="9f191-201">Nella casella **ID app di Azure** Digitare o incollare il valore dell'ID applicazione app di Azure (denominato anche *ID client*) ottenuto nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="9f191-201">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="9f191-202">Dopo aver convalidato correttamente la connessione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9f191-202">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="9f191-203">Nella pagina **autorizza Microsoft 365 per importare i dati** , digitare o incollare di nuovo APISecretKey e quindi fare clic su **login Web App**.</span><span class="sxs-lookup"><span data-stu-id="9f191-203">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="9f191-204">Fare clic su **login con Twitter**.</span><span class="sxs-lookup"><span data-stu-id="9f191-204">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="9f191-205">Nella pagina di accesso di Twitter, accedere usando le credenziali per l'account Twitter dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-205">On the Twitter sign in page, sign in using the credentials for your organization’s Twitter account.</span></span>

   ![Accedere all'account Twitter](media/TCimage42.png)

   <span data-ttu-id="9f191-207">Dopo aver eseguito l'accesso, nella pagina Twitter verrà visualizzato il messaggio seguente: "il processo del connettore di Twitter è stato configurato correttamente".</span><span class="sxs-lookup"><span data-stu-id="9f191-207">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="9f191-208">Fare clic su **continua** per completare la configurazione del connettore Twitter.</span><span class="sxs-lookup"><span data-stu-id="9f191-208">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="9f191-209">Nella pagina **Imposta filtri** è possibile applicare un filtro per importare inizialmente gli elementi di una determinata età.</span><span class="sxs-lookup"><span data-stu-id="9f191-209">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="9f191-210">Selezionare un'età, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9f191-210">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="9f191-211">Nella pagina **Scegli percorso di archiviazione** Digitare l'indirizzo di posta elettronica della cassetta postale di Microsoft 365 in cui verranno importati gli elementi di Twitter e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9f191-211">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="9f191-212">Sul **consenso amministratore**, fare clic su **Fornisci consenso** e quindi eseguire la procedura.</span><span class="sxs-lookup"><span data-stu-id="9f191-212">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="9f191-213">È necessario essere un amministratore globale per fornire il consenso per il servizio di importazione di Office 365 per accedere ai dati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-213">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="9f191-214">Fare clic su **Avanti** per esaminare le impostazioni del connettore e quindi fare clic su **fine** per completare la configurazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="9f191-214">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="9f191-215">Nel centro conformità, andare alla pagina **connettori dati** e fare clic sulla scheda **connettori** per visualizzare lo stato di avanzamento del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="9f191-215">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
