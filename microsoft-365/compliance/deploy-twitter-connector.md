---
title: Distribuire un connettore per archiviare i dati di Twitter
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
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori possono configurare un connettore nativo per importare e archiviare i dati di Twitter in Microsoft 365. Dopo aver importato i dati in Microsoft 365, è possibile utilizzare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire la governance dei dati di Twitter dell'organizzazione.
ms.openlocfilehash: 80c3ca71204b6050a1944250c20df4ff13bbd71e
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42635014"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="aeed1-104">Distribuire un connettore per archiviare i dati di Twitter</span><span class="sxs-lookup"><span data-stu-id="aeed1-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="aeed1-105">Questo articolo contiene il processo dettagliato per la distribuzione di un connettore che utilizza il servizio di importazione di Office 365 per importare i dati dall'account Twitter dell'organizzazione a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aeed1-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="aeed1-106">Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore Twitter, vedere [configurare un connettore per archiviare i dati di Twitter ](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="aeed1-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="aeed1-107">Passaggio 1: creare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="aeed1-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="aeed1-108">Accedere a <https://portal.azure.com> e accedere con le credenziali di un account di amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="aeed1-108">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![Accedere a Azure](../media/TCimage01.png)

2. <span data-ttu-id="aeed1-110">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Accedere a Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="aeed1-112">Nel riquadro di spostamento a sinistra, fare clic su **registrazioni app (anteprima)** e quindi fare clic su **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Creare una nuova registrazione delle app](../media/TCimage03.png)

4. <span data-ttu-id="aeed1-114">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="aeed1-114">Register the application.</span></span> <span data-ttu-id="aeed1-115">In **URI di reindirizzamento (facoltativo)** selezionare **Web** nell'elenco a discesa tipo di applicazione e quindi `https://portal.azure.com` digitare nella casella relativa all'URI.</span><span class="sxs-lookup"><span data-stu-id="aeed1-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="aeed1-116">Tipo https://portal.azure.com per l'URI di Reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="aeed1-116">Type https://portal.azure.com for the redirect URI</span></span> ](../media/TCimage04.png)

5. <span data-ttu-id="aeed1-117">Copiare l'ID dell' **applicazione (client)** e la **Directory (tenant)** e salvarli in un file di testo o in un'altra posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="aeed1-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="aeed1-118">È possibile utilizzare questi ID nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="aeed1-118">You use these IDs in later steps.</span></span>

    ![Copiare e salvare l'ID applicazione e l'ID directory](../media/TCimage05.png)

6. <span data-ttu-id="aeed1-120">Accedere a **certificati & segreti per la nuova applicazione** e in **segreti client** fare clic su **nuovo segreto client**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Creare un nuovo segreto client](../media/TCimage06.png)

7. <span data-ttu-id="aeed1-122">Creare un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="aeed1-122">Create a new secret.</span></span> <span data-ttu-id="aeed1-123">Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza.</span><span class="sxs-lookup"><span data-stu-id="aeed1-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Digitare il segreto e scegliere il periodo di scadenza](../media/TCimage08.png)

8. <span data-ttu-id="aeed1-125">Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="aeed1-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="aeed1-126">Si tratta del segreto dell'applicazione AAD utilizzato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="aeed1-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Copia e salvataggio del segreto](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="aeed1-128">Passaggio 2: distribuire il servizio Web del connettore da GitHub all'account di Azure</span><span class="sxs-lookup"><span data-stu-id="aeed1-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="aeed1-129">Accedere a [questo sito GitHub](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) e fare clic su **Distribuisci in Azure**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Passare alla Home page di Azure](../media/FBCimage11.png)

2. <span data-ttu-id="aeed1-131">Dopo aver fatto clic su **Distribuisci in Azure**, verrà reindirizzato a un portale di Azure con una pagina modello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="aeed1-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="aeed1-132">Compilare i dettagli delle **Impostazioni e delle** informazioni di **base** e quindi fare clic su **acquisto**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Fare clic su Crea un account di archiviazione di risorse e tipi](../media/FBCimage12.png)

    - <span data-ttu-id="aeed1-134">**Sottoscrizione:** Selezionare l'abbonamento di Azure in cui si desidera distribuire il servizio Web del connettore Twitter.</span><span class="sxs-lookup"><span data-stu-id="aeed1-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="aeed1-135">**Gruppo di risorse:** Scegliere o creare un nuovo gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="aeed1-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="aeed1-136">Un gruppo di risorse è un contenitore che contiene risorse correlate per una soluzione di Azure.</span><span class="sxs-lookup"><span data-stu-id="aeed1-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="aeed1-137">**Posizione:** Scegliere un percorso.</span><span class="sxs-lookup"><span data-stu-id="aeed1-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="aeed1-138">**Nome applicazione Web:** Specificare un nome univoco per il connettore Web App.</span><span class="sxs-lookup"><span data-stu-id="aeed1-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="aeed1-139">Il nome del Th deve essere compreso tra 3 e 18 caratteri.</span><span class="sxs-lookup"><span data-stu-id="aeed1-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="aeed1-140">Questo nome viene utilizzato per creare l'URL del servizio app di Azure. ad esempio, se si specifica il nome dell'applicazione Web di **twitterconnector** , l'URL del servizio app di Azure sarà **twitterconnector.azurewebsites.NET**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="aeed1-141">**tenantId:** L'ID tenant dell'organizzazione Microsoft 365 copiato dopo aver creato l'app connettore Facebook in Azure Active Directory nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="aeed1-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="aeed1-142">**APISecretKey:** È possibile digitare qualsiasi valore come segreto.</span><span class="sxs-lookup"><span data-stu-id="aeed1-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="aeed1-143">Viene utilizzato per accedere all'applicazione Web del connettore nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="aeed1-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="aeed1-144">Dopo che la distribuzione ha avuto esito positivo, la pagina avrà un aspetto simile alla schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="aeed1-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Fare clic su archiviazione e quindi su account di archiviazione](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="aeed1-146">Passaggio 3: creare l'app Twitter</span><span class="sxs-lookup"><span data-stu-id="aeed1-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="aeed1-147">Accedere a https://developer.twitter.com, eseguire l'accesso usando le credenziali per l'account di sviluppo per l'organizzazione, quindi fare clic su **app**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Accedere a https://developer.twitter.com ed eseguire l'accesso](../media/TCimage25-5.png)
2. <span data-ttu-id="aeed1-149">Fare clic su **Crea un'app**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-149">Click **Create an app**.</span></span>
   
   ![Vai alla pagina delle app per creare un'app](../media/TCimage26.png)

3. <span data-ttu-id="aeed1-151">In **Dettagli app**aggiungere informazioni sull'applicazione.</span><span class="sxs-lookup"><span data-stu-id="aeed1-151">Under **App details**, add information about the application.</span></span>

   ![Immettere informazioni sull'app](../media/TCimage27.png)

4. <span data-ttu-id="aeed1-153">Nel dashboard per sviluppatori di Twitter, selezionare l'app appena creata e copiare l'ID app visualizzato e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="aeed1-153">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="aeed1-154">Quindi fare clic su **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-154">Then click **Details**.</span></span>
   
   ![Copiare e salvare l'ID app](../media/TCimage28.png)

5. <span data-ttu-id="aeed1-156">Nella scheda **tasti e token** , in **tasti API consumer** copiare la chiave segreta API e salvarla in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="aeed1-156">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="aeed1-157">Fare quindi clic su **Crea** per generare un token di accesso e un segreto del token di accesso e copiarli in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="aeed1-157">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![Copia e Salva in chiave segreta API](../media/TCimage29.png)

   <span data-ttu-id="aeed1-159">Fare quindi clic su **Crea** per generare un token di accesso e un segreto del token di accesso e copiarli in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="aeed1-159">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="aeed1-160">Fare clic sulla scheda **autorizzazioni** e configurare le autorizzazioni come illustrato nella schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="aeed1-160">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Configurare le autorizzazioni](../media/TCimage30.png)

7. <span data-ttu-id="aeed1-162">Dopo aver salvato le impostazioni delle autorizzazioni, fare clic sulla scheda **Dettagli applicazione** e quindi fare clic su **modifica > modifica dettagli**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-162">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Modificare i dettagli dell'app](../media/TCimage31.png)

8. <span data-ttu-id="aeed1-164">Eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="aeed1-164">Do the following tasks:</span></span>

   - <span data-ttu-id="aeed1-165">Seleziona la casella di controllo per consentire all'app del connettore di accedere a Twitter.</span><span class="sxs-lookup"><span data-stu-id="aeed1-165">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="aeed1-166">Aggiungere l'URI di reindirizzamento OAuth utilizzando il formato seguente: \*\* \<connectorserviceuri>/views/twitteroauth\*\*, in cui il valore di *connectorserviceuri* è l'URL del servizio app di Azure per l'organizzazione. ad esempio, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span><span class="sxs-lookup"><span data-stu-id="aeed1-166">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Consenti all'app del connettore di accedere a Twitter e aggiungere l'URI di reindirizzamento OAuth](../media/TCimage32.png)

<span data-ttu-id="aeed1-168">L'app per sviluppatori di Twitter è ora pronta per essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="aeed1-168">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="aeed1-169">Passaggio 4: configurare l'applicazione Web del connettore</span><span class="sxs-lookup"><span data-stu-id="aeed1-169">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="aeed1-170">Passare a https://\<AzureAppResourceName>. azurewebsites.NET (dove **AzureAppResourceName** è il nome della risorsa di Azure App denominata nel passaggio 4).</span><span class="sxs-lookup"><span data-stu-id="aeed1-170">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="aeed1-171">Ad esempio, se il nome è **twitterconnector**, andare a https://twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="aeed1-171">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="aeed1-172">La Home page dell'app è simile alla schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="aeed1-172">The home page of the app looks like the following screenshot:</span></span>

   ![Vai alla pagina delle risorse per le app di Azure](../media/FBCimage41.png)

2. <span data-ttu-id="aeed1-174">Fare clic su **Configura** per visualizzare una pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="aeed1-174">Click **Configure** to display a sign in page.</span></span>

   ![Fare clic su Configura per visualizzare la pagina di accesso](../media/FBCimage42.png)

3. <span data-ttu-id="aeed1-176">Nella casella ID tenant digitare o incollare l'ID tenant (ottenuto nel passaggio 2).</span><span class="sxs-lookup"><span data-stu-id="aeed1-176">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="aeed1-177">Nella casella password digitare o incollare il APISecretKey (ottenuto nel passaggio 2), quindi fare clic su **imposta impostazioni di configurazione** per visualizzare la pagina dettagli di configurazione.</span><span class="sxs-lookup"><span data-stu-id="aeed1-177">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Accedere utilizzando l'ID tenant e la chiave segreta dell'API](../media/TCimage35.png)

4. <span data-ttu-id="aeed1-179">Immettere le impostazioni di configurazione seguenti</span><span class="sxs-lookup"><span data-stu-id="aeed1-179">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="aeed1-180">**Chiave API di Twitter:** ID app per l'applicazione Twitter creata al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="aeed1-180">**Twitter Api Key:** The app ID for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="aeed1-181">**Chiave segreta API Twitter:** La chiave segreta API per l'applicazione Twitter creata al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="aeed1-181">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="aeed1-182">**Token di accesso Twitter:** Il token di accesso creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="aeed1-182">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="aeed1-183">**Segreto del token di accesso di Twitter:** Il segreto del token di accesso creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="aeed1-183">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="aeed1-184">**ID applicazione AAD:** ID applicazione per l'app Azure Active Directory creata al passaggio 1</span><span class="sxs-lookup"><span data-stu-id="aeed1-184">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="aeed1-185">**Segreto dell'applicazione AAD:** Il valore del segreto di APISecretKey creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="aeed1-185">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="aeed1-186">Fare clic su **Salva** per salvare le impostazioni del connettore.</span><span class="sxs-lookup"><span data-stu-id="aeed1-186">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="aeed1-187">Passaggio 5: configurare un connettore Twitter nel centro conformità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aeed1-187">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="aeed1-188">Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fare clic su **connettori dati** nel NAV sinistro.</span><span class="sxs-lookup"><span data-stu-id="aeed1-188">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="aeed1-189">Nella pagina **connettori dati (anteprima)** in **Twitter**, fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-189">On the **Data connectors (preview)** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="aeed1-190">Nella pagina **Twitter** , fare clic su **Aggiungi connettore**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-190">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="aeed1-191">Nella pagina **condizioni del servizio** fare clic su **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-191">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="aeed1-192">Nella pagina **Aggiungi credenziali per l'app del connettore** , immettere le informazioni seguenti e quindi fare clic su **convalida connessione**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-192">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Immettere le credenziali delle app del connettore](../media/TCimage38.png)

    - <span data-ttu-id="aeed1-194">Nella casella **nome** Digitare un nome per il connettore, ad esempio la **maniglia della Guida di Twitter**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-194">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="aeed1-195">Nella casella **URL connettore** Digitare o incollare l'URL del servizio app di Azure; ad esempio `https://twitterconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="aeed1-195">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="aeed1-196">Nella casella **password** Digitare o incollare il valore del APISecretKey creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="aeed1-196">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="aeed1-197">Nella casella **ID app di Azure** Digitare o incollare il valore dell'ID applicazione app di Azure (denominato anche *ID client*) ottenuto nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="aeed1-197">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="aeed1-198">Dopo aver convalidato correttamente la connessione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-198">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="aeed1-199">Nella pagina **autorizza Microsoft 365 per importare i dati** , digitare o incollare di nuovo APISecretKey e quindi fare clic su **login Web App**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-199">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="aeed1-200">Fare clic su **login con Twitter**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-200">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="aeed1-201">Nella pagina di accesso di Twitter, accedere usando le credenziali per l'account Twitter dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aeed1-201">On the Twitter sign in page, sign in using the credentials for your organization’s Twitter account.</span></span>

   ![Accedere all'account Twitter](../media/TCimage42.png)

   <span data-ttu-id="aeed1-203">Dopo aver eseguito l'accesso, nella pagina Twitter verrà visualizzato il messaggio seguente: "il processo del connettore di Twitter è stato configurato correttamente".</span><span class="sxs-lookup"><span data-stu-id="aeed1-203">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="aeed1-204">Fare clic su **continua** per completare la configurazione del connettore Twitter.</span><span class="sxs-lookup"><span data-stu-id="aeed1-204">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="aeed1-205">Nella pagina **Imposta filtri** è possibile applicare un filtro per importare inizialmente gli elementi di una determinata età.</span><span class="sxs-lookup"><span data-stu-id="aeed1-205">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="aeed1-206">Selezionare un'età, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-206">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="aeed1-207">Nella pagina **Scegli percorso di archiviazione** Digitare l'indirizzo di posta elettronica della cassetta postale di Microsoft 365 in cui verranno importati gli elementi di Twitter e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="aeed1-207">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="aeed1-208">Sul **consenso amministratore**, fare clic su **Fornisci consenso** e quindi eseguire la procedura.</span><span class="sxs-lookup"><span data-stu-id="aeed1-208">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="aeed1-209">È necessario essere un amministratore globale per fornire il consenso per il servizio di importazione di Office 365 per accedere ai dati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="aeed1-209">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="aeed1-210">Fare clic su **Avanti** per esaminare le impostazioni del connettore e quindi fare clic su **fine** per completare la configurazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="aeed1-210">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="aeed1-211">Nel centro conformità, andare alla pagina **connettori dati** e fare clic sulla scheda **connettori** per visualizzare lo stato di avanzamento del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="aeed1-211">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
