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
description: Gli amministratori possono configurare un connettore nativo per importare e archiviare i dati di Twitter in Office 365. Dopo aver importato i dati in Office 365, è possibile utilizzare le funzionalità di conformità, ad esempio la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire la governance dei dati di Twitter dell'organizzazione.
ms.openlocfilehash: ee15086c6389fa2d2e7d07412ab533301cd8a842
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247469"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="27230-104">Distribuire un connettore per archiviare i dati di Twitter</span><span class="sxs-lookup"><span data-stu-id="27230-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="27230-105">Questo articolo contiene il processo dettagliato per la distribuzione di un connettore che utilizza il servizio di importazione di Office 365 per importare i dati dall'account Twitter dell'organizzazione a Office 365.</span><span class="sxs-lookup"><span data-stu-id="27230-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Office 365.</span></span> <span data-ttu-id="27230-106">Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore Twitter, vedere [use a Connector to Archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="27230-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Use a connector to archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="27230-107">Passaggio 1: scaricare il pacchetto</span><span class="sxs-lookup"><span data-stu-id="27230-107">Step 1: Download the package</span></span>

<span data-ttu-id="27230-108">Scaricare il pacchetto precompilato dalla sezione Release nell'archivio GitHub all'indirizzo [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span><span class="sxs-lookup"><span data-stu-id="27230-108">Download the prebuilt package from the Release section in the GitHub repository at [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases).</span></span> <span data-ttu-id="27230-109">Nella versione più recente, scaricare il file zip denominato **SampleConnector. zip**.</span><span class="sxs-lookup"><span data-stu-id="27230-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="27230-110">È possibile caricare il file zip in Azure nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="27230-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="27230-111">Passaggio 2: creare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="27230-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="27230-112">Accedere a <https://portal.azure.com> e accedere con le credenziali di un account di amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="27230-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

   ![Accedere a Azure](media/TCimage01.png)

2. <span data-ttu-id="27230-114">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="27230-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Accedere a Azure Active Directory](media/TCimage02.png)

3. <span data-ttu-id="27230-116">Nel riquadro di spostamento a sinistra, fare clic su **registrazioni app (anteprima)** e quindi fare clic su **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="27230-116">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Creare una nuova registrazione delle app](media/TCimage03.png)

4. <span data-ttu-id="27230-118">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27230-118">Register the application.</span></span> <span data-ttu-id="27230-119">In **URI di reindirizzamento (facoltativo)** selezionare **Web** nell'elenco a discesa tipo di applicazione e quindi `https://portal.azure.com` digitare nella casella relativa all'URI.</span><span class="sxs-lookup"><span data-stu-id="27230-119">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="27230-120">Tipo https://portal.azure.com per l'URI di Reindirizzamento</span><span class="sxs-lookup"><span data-stu-id="27230-120">Type https://portal.azure.com for the redirect URI</span></span> ](media/TCimage04.png)

5. <span data-ttu-id="27230-121">Copiare l'ID dell' **applicazione (client)** e la **Directory (tenant)** e salvarli in un file di testo o in un'altra posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="27230-121">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="27230-122">È possibile utilizzare questi ID nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="27230-122">You use these IDs in later steps.</span></span>

    ![Copiare e salvare l'ID applicazione e l'ID directory](media/TCimage05.png)

6. <span data-ttu-id="27230-124">Accedere a **certificati & segreti per la nuova applicazione** e in **segreti client** fare clic su **nuovo segreto client**.</span><span class="sxs-lookup"><span data-stu-id="27230-124">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Creare un nuovo segreto client](media/TCimage06.png)

7. <span data-ttu-id="27230-126">Creare un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="27230-126">Create a new secret.</span></span> <span data-ttu-id="27230-127">Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza.</span><span class="sxs-lookup"><span data-stu-id="27230-127">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Digitare il segreto e scegliere il periodo di scadenza](media/TCimage08.png)

8. <span data-ttu-id="27230-129">Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="27230-129">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="27230-130">Si tratta del segreto dell'applicazione AAD utilizzato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="27230-130">This is the AAD application secret that you use in later steps.</span></span>

   ![Copia e salvataggio del segreto](media/TCimage09.png)

9. <span data-ttu-id="27230-132">Andare a **manifest** e copiare il identifierUris (denominato anche URI dell'applicazione AAD) come evidenziato nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="27230-132">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="27230-133">Copiare l'URI dell'applicazione AAD in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="27230-133">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="27230-134">Viene utilizzato nel passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="27230-134">You use it in Step 6.</span></span>

    ![Copiare e salvare l'URI dell'applicazione AAD](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="27230-136">Passaggio 3: creare un account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="27230-136">Step 3: Create an Azure storage account</span></span>

1.  <span data-ttu-id="27230-137">Passare alla Home page di Azure per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="27230-137">Go to the Azure home page for your organization.</span></span>

    ![Home page gi-Azure](media/TCimage11.png)

2. <span data-ttu-id="27230-139">Fare clic su **Crea una risorsa** e digitare **account di archiviazione** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="27230-139">Click **Create a resource** and they type **storage account** in the search box.</span></span>

   ![Creare una risorsa dell'account di archiviazione](media/TCimage12.png)

3. <span data-ttu-id="27230-141">Fare clic su **spazio di archiviazione**e quindi su **account di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="27230-141">Click **Storage**, and then click **Storage account**.</span></span>

   ![Fare clic su archiviazione e quindi su account di archiviazione](media/TCimage13.png)

4. <span data-ttu-id="27230-143">Nella pagina **Crea account di archiviazione** , nella casella sottoscrizione, selezionare **pay-as-you-go** o **versione di valutazione gratuita** a seconda del tipo di sottoscrizione di Azure di cui si dispone.</span><span class="sxs-lookup"><span data-stu-id="27230-143">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> 

   ![Selezionare un tipo di account di archiviazione](media/TCimage14.png)

5. <span data-ttu-id="27230-145">Selezionare o creare un gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="27230-145">Select or create a resource group.</span></span>

   ![Selezionare o creare un gruppo di risorse](media/TCimage15.png)

6. <span data-ttu-id="27230-147">Digitare un nome per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="27230-147">Type a name for the storage account.</span></span>

   ![Assegnare un nome all'account di archiviazione](media/TCimage16.png)

7. <span data-ttu-id="27230-149">Esaminare e quindi fare clic su **Crea** per creare l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="27230-149">Review and then click **Create** to create the storage account.</span></span>

   ![Rivedere le impostazioni e quindi creare un account di archiviazione](media/TCimage17.png)

8. <span data-ttu-id="27230-151">Dopo alcuni istanti, fare clic su **Aggiorna** e quindi su **Vai a risorsa** per passare all'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="27230-151">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

   ![Passare all'account di archiviazione appena creato](media/TCimage18.png)

9. <span data-ttu-id="27230-153">Fare clic su **tasti di accesso** nel riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="27230-153">Click **Access keys** in the left navigation pane.</span></span>

   ![Fare clic su tasti di accesso](media/TCimage19.png)

10. <span data-ttu-id="27230-155">Copiare una **stringa di connessione** e salvarla in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="27230-155">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="27230-156">Questa operazione viene utilizzata quando si crea una risorsa Web App nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="27230-156">You use this when creating a web app resource in Step 4.</span></span>

    ![Copiare una stringa di connessione](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="27230-158">Passaggio 4: creare una nuova risorsa Web App in Azure</span><span class="sxs-lookup"><span data-stu-id="27230-158">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="27230-159">Nella **Home** page del portale di Azure, fare clic su **Crea una \> risorsa \> tutto Web App**.</span><span class="sxs-lookup"><span data-stu-id="27230-159">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="27230-160">Nella pagina **Web App** fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="27230-160">On the **Web app** page, click **Create**.</span></span>

   ![Creare una risorsa Web App in Azure](media/TCimage21.png)

2. <span data-ttu-id="27230-162">Inserire i dettagli (come illustrato di seguito) e quindi creare l'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="27230-162">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="27230-163">Il nome immesso nella casella **nome app** viene utilizzato per creare l'URL del servizio app di Azure. ad esempio, twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="27230-163">The name that you enter in the **App name** box is used to create the Azure app service URL; for example, twitterconnector.azurewebsites.net.</span></span>

   ![<span data-ttu-id="27230-164">Nome del tipo per la risorsa dell'applicazione Web. ad esempio twitterconnector.azurewebsites.net</span><span class="sxs-lookup"><span data-stu-id="27230-164">Type name for the web app resource; for example twitterconnector.azurewebsites.net</span></span> ](media/TCimage22.png)

3. <span data-ttu-id="27230-165">Passare alla risorsa nuova applicazione Web creata e fare clic su **Impostazioni applicazione** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="27230-165">Go to the newly created web app resource and click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="27230-166">In **Impostazioni applicazione**fare clic su **Aggiungi nuova impostazione** e quindi aggiungere le tre impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="27230-166">Under **Application settings**, click **Add new setting** and add the following three settings.</span></span> <span data-ttu-id="27230-167">Utilizzare i valori (copiati nel file di testo dai passaggi precedenti):</span><span class="sxs-lookup"><span data-stu-id="27230-167">Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="27230-168">**APISecretKey** – è possibile digitare qualsiasi valore come segreto.</span><span class="sxs-lookup"><span data-stu-id="27230-168">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="27230-169">Viene utilizzato per accedere all'applicazione Web del connettore nel passaggio 7.</span><span class="sxs-lookup"><span data-stu-id="27230-169">This is used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="27230-170">**StorageAccountConnectionString** : l'URI della stringa di connessione copiato dopo la creazione dell'account di archiviazione di Azure nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="27230-170">**StorageAccountConnectionString** – The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="27230-171">**tenantId** -l'ID tenant dell'organizzazione di Office 365 copiato dopo aver creato l'app Twitter Connector in Azure Active Directory nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="27230-171">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Twitter connector app in Azure Active Directory in Step 2.</span></span>

    ![Aggiungere le impostazioni delle app](media/TCimage23.png)

4. <span data-ttu-id="27230-173">In **Impostazioni generali**, fare clic **su** avanti accanto a **sempre attiva**.</span><span class="sxs-lookup"><span data-stu-id="27230-173">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="27230-174">Fare clic su **Salva** nella parte superiore della pagina per salvare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27230-174">Click **Save** at the top of the page to save the application settings.</span></span>

   ![Attiva risorsa Web App e quindi salvala](media/TCimage24.png)

5. <span data-ttu-id="27230-176">Il passaggio finale consiste nel caricare il codice sorgente dell'app del connettore in Azure scaricato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="27230-176">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="27230-177">In un Web browser, passare a https://<AzureAppResourceName>. SCM.azurewebsites.NET/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="27230-177">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="27230-178">Ad esempio, se il nome della risorsa dell'app di Azure (denominato nel passaggio 2 di questa sezione) è **twitterconnector**, si passa a https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="27230-178">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **twitterconnector**, then you would go to https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.</span></span>

6. <span data-ttu-id="27230-179">Trascinare e rilasciare il SampleConnector. zip (scaricato nel passaggio 1) in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="27230-179">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="27230-180">Dopo che i file sono stati caricati e la distribuzione ha esito positivo, la pagina avrà un aspetto simile alla schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="27230-180">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Trascinare e rilasciare il file SampleConnector. zip in questa pagina](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a><span data-ttu-id="27230-182">Passaggio 5: creare l'app Twitter</span><span class="sxs-lookup"><span data-stu-id="27230-182">Step 5: Create the Twitter app</span></span>

1. <span data-ttu-id="27230-183">Accedere a https://developer.twitter.com, eseguire l'accesso usando le credenziali per l'account di sviluppo per l'organizzazione, quindi fare clic su **app**.</span><span class="sxs-lookup"><span data-stu-id="27230-183">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Accedere a https://developer.twitter.com ed eseguire l'accesso](media/TCimage25-5.png)
2. <span data-ttu-id="27230-185">Fare clic su **Crea un'app**.</span><span class="sxs-lookup"><span data-stu-id="27230-185">Click **Create an app**.</span></span>
   
   ![Vai alla pagina delle app per creare un'app](media/TCimage26.png)

3. <span data-ttu-id="27230-187">In **Dettagli app**aggiungere informazioni sull'applicazione.</span><span class="sxs-lookup"><span data-stu-id="27230-187">Under **App details**, add information about the application.</span></span>

   ![Immettere informazioni sull'app](media/TCimage27.png)

4. <span data-ttu-id="27230-189">Nel dashboard per sviluppatori di Twitter, selezionare l'app appena creata e copiare l'ID app visualizzato e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="27230-189">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="27230-190">Quindi fare clic su **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="27230-190">Then click **Details**.</span></span>
   
   ![Copiare e salvare l'ID app](media/TCimage28.png)

5. <span data-ttu-id="27230-192">Nella scheda **tasti e token** , in **tasti API consumer** copiare la chiave segreta API e salvarla in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="27230-192">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="27230-193">Fare quindi clic su **Crea** per generare un token di accesso e un segreto del token di accesso e copiarli in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="27230-193">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![Copia e Salva in chiave segreta API](media/TCimage29.png)

   <span data-ttu-id="27230-195">Fare quindi clic su **Crea** per generare un token di accesso e un segreto del token di accesso e copiarli in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="27230-195">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="27230-196">Fare clic sulla scheda **autorizzazioni** e configurare le autorizzazioni come illustrato nella schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="27230-196">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Configurare le autorizzazioni](media/TCimage30.png)

7. <span data-ttu-id="27230-198">Dopo aver salvato le impostazioni delle autorizzazioni, fare clic sulla scheda **Dettagli applicazione** e quindi fare clic su **modifica > modifica dettagli**.</span><span class="sxs-lookup"><span data-stu-id="27230-198">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Modificare i dettagli dell'app](media/TCimage31.png)

8. <span data-ttu-id="27230-200">Eseguire le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="27230-200">Do the following tasks:</span></span>

   - <span data-ttu-id="27230-201">Seleziona la casella di controllo per consentire all'app del connettore di accedere a Twitter.</span><span class="sxs-lookup"><span data-stu-id="27230-201">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="27230-202">Aggiungere l'URI di reindirizzamento OAuth utilizzando il formato seguente: \*\* \<connectorserviceuri>/views/twitteroauth\*\*, in cui il valore di *connectorserviceuri* è l'URL del servizio app di Azure per l'organizzazione. ad esempio, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span><span class="sxs-lookup"><span data-stu-id="27230-202">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Consenti all'app del connettore di accedere a Twitter e aggiungere l'URI di reindirizzamento OAuth](media/TCimage32.png)

<span data-ttu-id="27230-204">L'app per sviluppatori di Twitter è ora pronta per essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="27230-204">The Twitter developer app is now ready to use.</span></span>

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="27230-205">Passaggio 6: configurare l'applicazione Web del connettore</span><span class="sxs-lookup"><span data-stu-id="27230-205">Step 6: Configure the connector web app</span></span> 

1. <span data-ttu-id="27230-206">Passare a https://\<AzureAppResourceName>. azurewebsites.NET (dove **AzureAppResourceName** è il nome della risorsa di Azure App denominata nel passaggio 4).</span><span class="sxs-lookup"><span data-stu-id="27230-206">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="27230-207">Ad esempio, se il nome è **twitterconnector**, andare a https://twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="27230-207">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="27230-208">La Home page dell'app è simile alla schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="27230-208">The home page of the app looks like the following screenshot:</span></span>

   ![Vai alla pagina delle risorse per le app di Azure](media/FBCimage41.png)

2. <span data-ttu-id="27230-210">Fare clic su **Configura** per visualizzare una pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="27230-210">Click **Configure** to display a sign in page.</span></span>

   ![Fare clic su Configura per visualizzare la pagina di accesso](media/FBCimage42.png)

3. <span data-ttu-id="27230-212">Nella casella ID tenant digitare o incollare l'ID tenant (ottenuto nel passaggio 2).</span><span class="sxs-lookup"><span data-stu-id="27230-212">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="27230-213">Nella casella password digitare o incollare il APISecretKey (ottenuto nel passaggio 2), quindi fare clic su **imposta impostazioni di configurazione** per visualizzare la pagina **Dettagli di configurazione** .</span><span class="sxs-lookup"><span data-stu-id="27230-213">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

   ![Accedere utilizzando l'ID tenant e la chiave segreta dell'API](media/TCimage35.png)

4. <span data-ttu-id="27230-215">In **Dettagli di configurazione**, immettere le impostazioni di configurazione seguenti</span><span class="sxs-lookup"><span data-stu-id="27230-215">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="27230-216">**Chiave API di Twitter** : l'ID app per l'applicazione Twitter creata al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="27230-216">**Twitter Api Key** – The app ID for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="27230-217">**Chiave segreta API di Twitter** – la chiave segreta API per l'applicazione Twitter creata al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="27230-217">**Twitter Api Secret Key** – The API secret key for the Twitter application that you created in Step 5.</span></span>
   - <span data-ttu-id="27230-218">**Token di accesso Twitter** : il token di accesso creato nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="27230-218">**Twitter Access Token** – The access token that you created in Step 5.</span></span>
   - <span data-ttu-id="27230-219">**Segreto del token di accesso di Twitter** -il segreto del token di accesso creato nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="27230-219">**Twitter Access Token Secret** – The access token secret that you created in Step 5.</span></span>
   - <span data-ttu-id="27230-220">**ID applicazione AAD** -ID applicazione per l'app Azure Active Directory creata al passaggio 2</span><span class="sxs-lookup"><span data-stu-id="27230-220">**AAD Application ID** – The application ID for the Azure Active Directory app that you created in Step 2</span></span>
   - <span data-ttu-id="27230-221">**Segreto dell'applicazione AAD** : il valore del segreto di APISecretKey creato nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="27230-221">**AAD Application Secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="27230-222">**URI dell'applicazione AAD** – URI dell'applicazione AAD ottenuto nel passaggio 2; ad esempio, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span><span class="sxs-lookup"><span data-stu-id="27230-222">**AAD Application Uri** – The AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span></span>
   - <span data-ttu-id="27230-223">**Chiave di strumentazione Insights app** : lasciare vuota questa casella.</span><span class="sxs-lookup"><span data-stu-id="27230-223">**App Insights Instrumentation Key** – Leave this box blank.</span></span>

5. <span data-ttu-id="27230-224">Fare clic su **Salva** per salvare le impostazioni del connettore.</span><span class="sxs-lookup"><span data-stu-id="27230-224">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a><span data-ttu-id="27230-225">Passaggio 7: configurare un connettore personalizzato nel centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="27230-225">Step 7: Set up a custom connector in the security and compliance center</span></span>

1.  <span data-ttu-id="27230-226">Passare a <https://protection.office.com> e quindi fare clic su **dati di terze parti sull' \> importazione \> di governance delle informazioni**.</span><span class="sxs-lookup"><span data-stu-id="27230-226">Go to <https://protection.office.com> and then click **Information governance \> Import \> Archive third-party data**.</span></span>

    ![Passare alla pagina di archiviazione dei dati di terze parti nel centro sicurezza e conformità](media/TCimage36.png)

2. <span data-ttu-id="27230-228">Fare clic su **Aggiungi connettore** e quindi su **Twitter**.</span><span class="sxs-lookup"><span data-stu-id="27230-228">Click **Add a connector** and then click **Twitter**.</span></span>

   ![Fare clic su Aggiungi connettore per aggiungere un connettore Twitter](media/TCimage37.png)

3. <span data-ttu-id="27230-230">Nella pagina **Aggiungi applicazione del connettore** , immettere le informazioni seguenti e quindi fare clic su **convalida connettore**.</span><span class="sxs-lookup"><span data-stu-id="27230-230">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="27230-231">Nella prima casella digitare un nome per il connettore, ad esempio **Twitter**.</span><span class="sxs-lookup"><span data-stu-id="27230-231">In the first box, type a name for the connector, such as **Twitter**.</span></span>
    - <span data-ttu-id="27230-232">Nella seconda casella digitare o incollare il valore dell'APISecretKey aggiunto nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="27230-232">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="27230-233">Nella terza casella digitare o incollare l'URL del servizio app di Azure; ad esempio, **https://twitterconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="27230-233">In the third box, type or paste the Azure app service URL; for example, **https://twitterconnector.azurewebsites.net**.</span></span>

   <span data-ttu-id="27230-234">Dopo che il connettore è stato convalidato, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27230-234">After the connector is successfully validated, click **Next**.</span></span>

   ![Immettere le impostazioni delle app del connettore](media/TCimage38.png)

4. <span data-ttu-id="27230-236">Fare clic su **login con app connettore**.</span><span class="sxs-lookup"><span data-stu-id="27230-236">Click **Login with Connector App**.</span></span>

   ![Accedere all'app del connettore](media/TCimage39.png)

5. <span data-ttu-id="27230-238">Digitare o incollare di nuovo il APISecretKey e quindi fare clic su **accedi al servizio connettore**.</span><span class="sxs-lookup"><span data-stu-id="27230-238">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![Chiave segreta API di tipo per accedere al servizio del connettore](media/TCimage40.png)

6. <span data-ttu-id="27230-240">Fare clic su **continua con Twitter**.</span><span class="sxs-lookup"><span data-stu-id="27230-240">Click **Continue with Twitter**.</span></span>

7. <span data-ttu-id="27230-241">Nella pagina di accesso di Twitter, accedere usando le credenziali per l'account per l'account Twitter dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="27230-241">On the Twitter sign in page, sign in using the credentials for the account for your organization’s Twitter account.</span></span>

   ![Accedere all'account Twitter](media/TCimage42.png)

   <span data-ttu-id="27230-243">Dopo aver eseguito l'accesso, nella pagina Twitter verrà visualizzato il messaggio seguente: "il processo del connettore di Twitter è stato configurato correttamente".</span><span class="sxs-lookup"><span data-stu-id="27230-243">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

8. <span data-ttu-id="27230-244">Fare clic su **fine** per completare la configurazione del connettore Twitter.</span><span class="sxs-lookup"><span data-stu-id="27230-244">Click **Finish** to complete setting up the Twitter connector.</span></span>

9. <span data-ttu-id="27230-245">Nella pagina **Imposta filtri** è possibile applicare un filtro per importare e archiviare gli elementi di una determinata età.</span><span class="sxs-lookup"><span data-stu-id="27230-245">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="27230-246">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="27230-246">Click **Next**.</span></span>

   ![Configurare il filtro per importare elementi di una determinata età](media/TCimage44.png)

10. <span data-ttu-id="27230-248">Nella pagina **Imposta account di archiviazione** Digitare l'indirizzo di posta elettronica di una cassetta postale di Office 365 in cui verranno importati gli elementi di Twitter.</span><span class="sxs-lookup"><span data-stu-id="27230-248">On the **Set Storage Account** page, type the email address of an Office 365 mailbox that the Twitter items will be imported to.</span></span>

    ![Specificare una cassetta postale di Office 365 per importare gli elementi di Twitter in](media/TCimage45.png)

11. <span data-ttu-id="27230-250">Esaminare le impostazioni e quindi fare clic su **fine** per completare la configurazione del connettore nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="27230-250">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![Rivedere le impostazioni e quindi fare clic su fine.](media/TCimage46.png)

    ![Schermata che mostra che la configurazione del connettore è stata completata](media/TCimage47.png)

12. <span data-ttu-id="27230-253">Passare alla pagina di **archiviazione dei dati di terze parti** per visualizzare lo stato di avanzamento del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="27230-253">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![Nuovo connettore visualizzato nel centro sicurezza e conformità](media/TCimage48.png)
