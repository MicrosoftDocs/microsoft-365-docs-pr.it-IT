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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Gli amministratori possono configurare un connettore nativo per importare e archiviare i dati di Twitter Microsoft 365. Dopo aver importato questi dati in Microsoft 365, è possibile utilizzare funzionalità di conformità come il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire la governance dei dati twitter dell'organizzazione.
ms.openlocfilehash: 0a0ebb18cb39b7dd7416f2d03dcb5b4d21332c9b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227056"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="1f4ee-104">Distribuire un connettore per archiviare i dati di Twitter</span><span class="sxs-lookup"><span data-stu-id="1f4ee-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="1f4ee-105">In questo articolo sono contenute le procedure dettagliate per distribuire un connettore che utilizza il servizio di importazione di Office 365 per importare dati dall'account Twitter dell'organizzazione a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="1f4ee-106">Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore Twitter, vedere [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1f4ee-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="1f4ee-107">Passaggio 1: Creare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1f4ee-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="1f4ee-108">Accedere a <https://portal.azure.com> e accedere utilizzando le credenziali di un account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Accedere ad Azure](../media/TCimage01.png)

2. <span data-ttu-id="1f4ee-110">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Vai a Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="1f4ee-112">Nel riquadro di spostamento sinistro fare clic su **Registrazioni app (anteprima)** e quindi su **Nuova registrazione.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Creare una nuova registrazione dell'app](../media/TCimage03.png)

4. <span data-ttu-id="1f4ee-114">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-114">Register the application.</span></span> <span data-ttu-id="1f4ee-115">In **URI di reindirizzamento (facoltativo)** seleziona **Web** nell'elenco a discesa tipo di applicazione e quindi digita nella casella `https://portal.azure.com` per l'URI.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![Tipo https://portal.azure.com per l'URI di reindirizzamento](../media/TCimage04.png)

5. <span data-ttu-id="1f4ee-117">Copiare **l'ID applicazione (client)** **e l'ID directory (tenant)** e salvarli in un file di testo o in un altro percorso sicuro.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="1f4ee-118">Questi ID vengono utilizzati nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-118">You use these IDs in later steps.</span></span>

    ![Copiare e salvare l'ID applicazione e l'ID directory](../media/TCimage05.png)

6. <span data-ttu-id="1f4ee-120">Vai a **Certificati & segreti per la nuova app** e in Segreti client **fai** clic su Nuovo **segreto client.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Creare un nuovo segreto client](../media/TCimage06.png)

7. <span data-ttu-id="1f4ee-122">Creare un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-122">Create a new secret.</span></span> <span data-ttu-id="1f4ee-123">Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-123">In the description box, type the secret and then choose an expiration period.</span></span>

   ![Digitare il segreto e scegliere il periodo di scadenza](../media/TCimage08.png)

8. <span data-ttu-id="1f4ee-125">Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="1f4ee-126">Si tratta del segreto dell'applicazione AAD utilizzato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Copiare e salvare il segreto](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="1f4ee-128">Passaggio 2: Distribuire il servizio Web del connettore da GitHub all'account Azure</span><span class="sxs-lookup"><span data-stu-id="1f4ee-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="1f4ee-129">Accedere a [questo sito GitHub e](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) fare clic su **Distribuisci in Azure**.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Passare alla home page di Azure](../media/FBCimage11.png)

2. <span data-ttu-id="1f4ee-131">Dopo aver fatto **clic su Distribuisci in Azure,** si verrà reindirizzati a un portale di Azure con una pagina modello personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="1f4ee-132">Compila i dettagli **di** base e **Impostazioni** e quindi fai clic su **Acquista.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Fare clic su Crea una risorsa e digitare l'account di archiviazione](../media/FBCimage12.png)

    - <span data-ttu-id="1f4ee-134">**Sottoscrizione:** Selezionare la sottoscrizione di Azure in cui si desidera distribuire il servizio Web del connettore Di Twitter.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>

    - <span data-ttu-id="1f4ee-135">**Gruppo di risorse:** Scegliere o creare un nuovo gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="1f4ee-136">Un gruppo di risorse è un contenitore che contiene le risorse correlate per una soluzione di Azure.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="1f4ee-137">**Posizione:** Scegliere una posizione.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="1f4ee-138">**Nome app Web:** Specificare un nome univoco per l'app Web del connettore.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="1f4ee-139">Il nome deve avere una lunghezza compresa tra 3 e 18 caratteri.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="1f4ee-140">Questo nome viene usato per creare l'URL del servizio app di Azure. Ad esempio, se fornisci il nome dell'app Web **twitterconnector,** l'URL del servizio app di Azure verrà **twitterconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>

    - <span data-ttu-id="1f4ee-141">**tenantId:** L'ID tenant dell'Microsoft 365 che hai copiato dopo aver creato l'app del connettore Facebook in Azure Active Directory nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>

   - <span data-ttu-id="1f4ee-142">**APISecretKey:** È possibile digitare qualsiasi valore come segreto.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="1f4ee-143">Viene usato per accedere all'app Web del connettore nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="1f4ee-144">Una volta completata la distribuzione, la pagina avrà un aspetto simile allo screenshot seguente:</span><span class="sxs-lookup"><span data-stu-id="1f4ee-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Fare Archiviazione e quindi fare clic su Archiviazione account](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="1f4ee-146">Passaggio 3: Creare l'app Twitter</span><span class="sxs-lookup"><span data-stu-id="1f4ee-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="1f4ee-147">Vai a https://developer.twitter.com , accedi usando le credenziali per l'account sviluppatore per l'organizzazione e quindi fai clic su **App.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Vai a https://developer.twitter.com e accedi](../media/TCimage25-5.png)
2. <span data-ttu-id="1f4ee-149">Fai **clic su Crea un'app.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-149">Click **Create an app**.</span></span>

   ![Vai alla pagina App per creare un'app](../media/TCimage26.png)

3. <span data-ttu-id="1f4ee-151">In **Dettagli app** aggiungi informazioni sull'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-151">Under **App details**, add information about the application.</span></span>

   ![Immetti informazioni sull'app](../media/TCimage27.png)

4. <span data-ttu-id="1f4ee-153">Nel dashboard per sviluppatori di Twitter seleziona l'app appena creata e quindi fai clic su **Dettagli.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>

   ![Copiare e salvare l'ID app](../media/TCimage28.png)

5. <span data-ttu-id="1f4ee-155">Nella scheda **Chiavi e token,** in Chiavi **API** consumer copiare sia la chiave API che la chiave privata dell'API e salvarle in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="1f4ee-156">Fare quindi **clic su Crea** per generare un token di accesso e un token di accesso segreto e copiarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>

   ![Copiare e salvare nella chiave privata API](../media/TCimage29.png)

   <span data-ttu-id="1f4ee-158">Fare quindi **clic su Crea** per generare un token di accesso e un segreto token di accesso e copiarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="1f4ee-159">Fare clic **sulla scheda** Autorizzazioni e configurare le autorizzazioni come illustrato nello screenshot seguente:</span><span class="sxs-lookup"><span data-stu-id="1f4ee-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Configurare le autorizzazioni](../media/TCimage30.png)

7. <span data-ttu-id="1f4ee-161">Dopo aver salvato le impostazioni di autorizzazione, fare clic sulla **scheda Dettagli** app e quindi su Modifica > **Modifica dettagli**.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Modificare i dettagli dell'app](../media/TCimage31.png)

8. <span data-ttu-id="1f4ee-163">Eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f4ee-163">Do the following tasks:</span></span>

   - <span data-ttu-id="1f4ee-164">Seleziona la casella di controllo per consentire all'app connettore di accedere a Twitter.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>

   - <span data-ttu-id="1f4ee-165">Aggiungere l'URI di reindirizzamento OAuth nel formato **\<connectorserviceuri> seguente: /Views/TwitterOAuth**, dove il valore di *connectorserviceuri è* l'URL del servizio app azure per l'organizzazione, ad esempio https://twitterconnector.azurewebsites.net/Views/TwitterOAuth .</span><span class="sxs-lookup"><span data-stu-id="1f4ee-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Consenti all'app connettore di accedere a Twitter e aggiungere uri di reindirizzamento OAuth](../media/TCimage32.png)

<span data-ttu-id="1f4ee-167">L'app per sviluppatori Twitter è ora pronta per l'uso.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="1f4ee-168">Passaggio 4: Configurare l'app Web del connettore</span><span class="sxs-lookup"><span data-stu-id="1f4ee-168">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="1f4ee-169">Vai a https:// \<AzureAppResourceName> .azurewebsites.net (dove **AzureAppResourceName** è il nome della risorsa app di Azure denominata nel passaggio 4).</span><span class="sxs-lookup"><span data-stu-id="1f4ee-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="1f4ee-170">Ad esempio, se il nome è **twitterconnector**, passare a https://twitterconnector.azurewebsites.net .</span><span class="sxs-lookup"><span data-stu-id="1f4ee-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="1f4ee-171">La home page dell'app è simile alla schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="1f4ee-171">The home page of the app looks like the following screenshot:</span></span>

   ![Vai alla pagina delle risorse dell'app azure](../media/FBCimage41.png)

2. <span data-ttu-id="1f4ee-173">Fare **clic su** Configura per visualizzare una pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-173">Click **Configure** to display a sign in page.</span></span>

   ![Fare clic su Configura per visualizzare la pagina di accesso](../media/FBCimage42.png)

3. <span data-ttu-id="1f4ee-175">Nella casella ID tenant digitare o incollare l'ID tenant ottenuto nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="1f4ee-176">Nella casella password digitare o **incollare** APISecretKey (ottenuto nel passaggio 2), quindi fare clic su Imposta configurazione Impostazioni per visualizzare la pagina dei dettagli della configurazione.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Accedere usando l'ID tenant e la chiave privata API](../media/TCimage35.png)

4. <span data-ttu-id="1f4ee-178">Immettere le impostazioni di configurazione seguenti</span><span class="sxs-lookup"><span data-stu-id="1f4ee-178">Enter the following configuration settings</span></span>

   - <span data-ttu-id="1f4ee-179">**Chiave api Twitter:** La chiave API per l'applicazione Twitter creata nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>

   - <span data-ttu-id="1f4ee-180">**Chiave privata api Twitter:** Chiave privata API per l'applicazione Twitter creata nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>

   - <span data-ttu-id="1f4ee-181">**Token di accesso Twitter:** Token di accesso creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>

   - <span data-ttu-id="1f4ee-182">**Twitter Access Token Secret:** Il token di accesso segreto creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>

   - <span data-ttu-id="1f4ee-183">**ID applicazione AAD:** ID dell'applicazione Azure Active Directory'app creata nel passaggio 1</span><span class="sxs-lookup"><span data-stu-id="1f4ee-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>

   - <span data-ttu-id="1f4ee-184">**Segreto applicazione AAD:** Valore per il segreto APISecretKey creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="1f4ee-185">Fare **clic su** Salva per salvare le impostazioni del connettore.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="1f4ee-186">Passaggio 5: Configurare un connettore Twitter nella Centro conformità Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1f4ee-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="1f4ee-187">Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fai clic su **Connettori dati** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="1f4ee-188">Nella pagina **Connettori dati** in **Twitter** fare clic su **Visualizza.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="1f4ee-189">Nella pagina **Twitter** fare clic su **Aggiungi connettore.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="1f4ee-190">Nella pagina **Condizioni di servizio** fare clic su **Accetta.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="1f4ee-191">Nella pagina **Aggiungi credenziali per l'app connettore** immettere le informazioni seguenti e quindi fare clic su **Convalida connessione.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Immettere le credenziali dell'app connettore](../media/TCimage38.png)

    - <span data-ttu-id="1f4ee-193">Nella casella **Nome** digitare un nome per il connettore, ad esempio Gestione della **Guida di Twitter.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>

    - <span data-ttu-id="1f4ee-194">Nella casella **URL connettore** digitare o incollare l'URL del servizio app di Azure. ad esempio `https://twitterconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="1f4ee-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>

    - <span data-ttu-id="1f4ee-195">Nella casella **Password** digitare o incollare il valore di APISecretKey creato nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>

    - <span data-ttu-id="1f4ee-196">Nella casella **ID app di Azure** digitare o incollare il valore dell'ID app dell'applicazione Azure (denominato anche ID *client)* ottenuto nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="1f4ee-197">Dopo aver convalidato correttamente la connessione, fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="1f4ee-198">Nella pagina **Autorizza Microsoft 365 importare** dati digitare o incollare di nuovo APISecretKey e quindi fare clic su **Accedi all'app Web.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="1f4ee-199">Fai **clic su Accedi con Twitter.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="1f4ee-200">Nella pagina di accesso a Twitter, accedere utilizzando le credenziali per l'account Twitter dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Accedere all'account Twitter](../media/TCimage42.png)

   <span data-ttu-id="1f4ee-202">Dopo aver eseguito l'accesso, nella pagina Twitter verrà visualizzato il messaggio seguente, "Configurazione completata del processo del connettore twitter".</span><span class="sxs-lookup"><span data-stu-id="1f4ee-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="1f4ee-203">Fare **clic su** Continua per completare la configurazione del connettore Twitter.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="1f4ee-204">Nella pagina **Imposta filtri** è possibile applicare un filtro per importare inizialmente elementi di una determinata età.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="1f4ee-205">Selezionare un'età e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="1f4ee-206">Nella pagina **Scegli percorso di archiviazione** digitare l'indirizzo di Microsoft 365 di posta elettronica in cui verranno importati gli elementi di Twitter e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="1f4ee-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="1f4ee-207">Fare **clic su** Avanti per esaminare le impostazioni del connettore e quindi fare clic su **Fine** per completare la configurazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-207">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="1f4ee-208">Nel Centro conformità passare alla pagina **Connettori** di dati e fare clic sulla scheda **Connettori** per visualizzare l'avanzamento del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="1f4ee-208">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
