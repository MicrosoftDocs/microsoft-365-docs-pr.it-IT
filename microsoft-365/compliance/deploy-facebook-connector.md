---
title: Distribuire un connettore per archiviare i dati di Facebook in Office 365
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
description: Gli amministratori possono configurare un connettore nativo per l'importazione e l'archiviazione di pagine business di Facebook in Office 365. Dopo aver importato i dati in Office 365, è possibile utilizzare le funzionalità di conformità, ad esempio la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire la governance dei dati di Facebook dell'organizzazione.
ms.openlocfilehash: 786ff97c558a5618643783de803c742c50185f00
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "38686498"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a><span data-ttu-id="ce8ec-104">Distribuire un connettore per archiviare i dati di Facebook in Office 365</span><span class="sxs-lookup"><span data-stu-id="ce8ec-104">Deploy a connector to archive Facebook data in Office 365</span></span>

<span data-ttu-id="ce8ec-105">Questo articolo contiene il processo dettagliato per la distribuzione di un connettore che utilizza il servizio di importazione di Office 365 per importare i dati da pagine business di Facebook a Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="ce8ec-106">Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore Facebook, vedere [use a sample Connector to Archive Facebook Data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="ce8ec-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use a sample connector to archive Facebook data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="ce8ec-107">Passaggio 1: scaricare il pacchetto</span><span class="sxs-lookup"><span data-stu-id="ce8ec-107">Step 1: Download the package</span></span>

<span data-ttu-id="ce8ec-108">Scaricare il pacchetto precompilato dalla sezione Release nell'archivio GitHub all'indirizzo <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-108">Download the prebuilt package from the Release section in the GitHub repository at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="ce8ec-109">Nella versione più recente, scaricare il file zip denominato **SampleConnector. zip**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="ce8ec-110">È possibile caricare il file zip in Azure nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="ce8ec-111">Passaggio 2: creare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ce8ec-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="ce8ec-112">Accedere a <https://portal.azure.com> e accedere con le credenziali di un account di amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![Creare un'app in AAD](media/FBCimage1.png)

2. <span data-ttu-id="ce8ec-114">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Fare clic su Azure Active Directory](media/FBCimage2.png)

3. <span data-ttu-id="ce8ec-116">Nel riquadro di spostamento a sinistra, fare clic su **registrazioni app (anteprima)** e quindi fare clic su **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-116">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Fare clic su \* \* registrazioni app (anteprima) \* \* e quindi fare clic su \* \* nuova registrazione \* \*](media/FBCimage3.png)

4. <span data-ttu-id="ce8ec-118">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-118">Register the application.</span></span> <span data-ttu-id="ce8ec-119">In URI di reindirizzamento, selezionare Web nell'elenco a discesa tipo di applicazione e <https://portal.azure.com> quindi digitare nella casella per l'URI.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-119">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Registrare l'applicazione](media/FBCimage4.png)

5. <span data-ttu-id="ce8ec-121">Copiare l'ID dell' **applicazione (client)** e la **Directory (tenant)** e salvarli in un file di testo o in un'altra posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-121">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="ce8ec-122">È possibile utilizzare questi ID nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-122">You use these IDs in later steps.</span></span>

   ![Copiare l'ID applicazione e l'ID directory e salvarli](media/FBCimage5.png)

6. <span data-ttu-id="ce8ec-124">Accedere a **certificati & segreti per la nuova app.**</span><span class="sxs-lookup"><span data-stu-id="ce8ec-124">Go to **Certificates & secrets for the new app.**</span></span>

   ![Accedere a certificati & segreti per la nuova applicazione](media/FBCimage6.png)

7. <span data-ttu-id="ce8ec-126">Fare clic su **nuovo client segreto**</span><span class="sxs-lookup"><span data-stu-id="ce8ec-126">Click **New client secret**</span></span>

   ![Fare clic su nuovo client segreto](media/FBCimage7.png)

8. <span data-ttu-id="ce8ec-128">Creare un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-128">Create a new secret.</span></span> <span data-ttu-id="ce8ec-129">Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-129">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![Digita il segreto e quindi scegli un periodo di scadenza](media/FBCimage8.png)

9. <span data-ttu-id="ce8ec-131">Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-131">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="ce8ec-132">Si tratta del segreto dell'applicazione AAD utilizzato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-132">This is the AAD application secret that you use in later steps.</span></span>

   ![Copiare il valore del segreto e salvarlo](media/FBCimage9.png)

10. <span data-ttu-id="ce8ec-134">Andare a **manifest** e copiare il identifierUris (denominato anche URI dell'applicazione AAD) come evidenziato nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-134">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="ce8ec-135">Copiare l'URI dell'applicazione AAD in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-135">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="ce8ec-136">Viene utilizzato nel passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-136">You use it in Step 6.</span></span>

   ![Passare a manifest e copiare l'URI dell'applicazione AAD](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="ce8ec-138">Passaggio 3: creare un account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="ce8ec-138">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="ce8ec-139">Passare alla Home page di Azure per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-139">Go to the Azure home page for your organization.</span></span>

    ![Passare alla Home page di Azure](media/FBCimage11.png)

2. <span data-ttu-id="ce8ec-141">Fare clic su **Crea una risorsa** e quindi digitare **account di archiviazione** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-141">Click **Create a resource** and then type **storage account** in the search box.</span></span>

    ![Fare clic su Crea un account di archiviazione di risorse e tipi](media/FBCimage12.png)

3. <span data-ttu-id="ce8ec-143">Fare clic su **spazio di archiviazione**e quindi su **account di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-143">Click **Storage**, and then click **Storage account**.</span></span>

    ![Fare clic su archiviazione e quindi su account di archiviazione](media/FBCimage13.png)

4. <span data-ttu-id="ce8ec-145">Nella pagina **Crea account di archiviazione** , nella casella sottoscrizione, selezionare **pay-as-you-go** o **versione di valutazione gratuita** a seconda del tipo di sottoscrizione di Azure di cui si dispone.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-145">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="ce8ec-146">Selezionare o creare un gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-146">Then select or create a resource group.</span></span>

    ![Selezionare pay-as-you-go o versione di valutazione gratuita](media/FBCimage14.png)

5. <span data-ttu-id="ce8ec-148">Digitare un nome per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-148">Type a name for the storage account.</span></span>

    ![Digitare un nome per l'account di archiviazione](media/FBCimage15.png)

6. <span data-ttu-id="ce8ec-150">Esaminare e quindi fare clic su **Crea** per creare l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-150">Review and then click **Create** to create the storage account.</span></span>

    ![Creare l'account di archiviazione](media/FBCimage16.png)

7. <span data-ttu-id="ce8ec-152">Dopo alcuni istanti, fare clic su **Aggiorna** e quindi su **Vai a risorsa** per passare all'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-152">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![Passare all'account di archiviazione](media/FBCimage17.png)

8. <span data-ttu-id="ce8ec-154">Fare clic su **tasti di accesso** nel riquadro di spostamento a sinistra.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-154">Click **Access keys** in the left navigation pane.</span></span>

    ![Fare clic su tasti di accesso](media/FBCimage18.png)

9. <span data-ttu-id="ce8ec-156">Copiare una **stringa di connessione** e salvarla in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-156">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="ce8ec-157">Questa operazione viene utilizzata durante la creazione di una risorsa Web App.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-157">You use this when creating a web app resource.</span></span>

    ![Copiare una stringa di connessione e salvarla](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="ce8ec-159">Passaggio 4: creare una nuova risorsa Web App in Azure</span><span class="sxs-lookup"><span data-stu-id="ce8ec-159">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="ce8ec-160">Nella **Home** page del portale di Azure, fare clic su **Crea una \> risorsa \> tutto Web App**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-160">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="ce8ec-161">Nella pagina **Web App** fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-161">On the **Web app** page, click **Create**.</span></span> 

   ![Creare una nuova risorsa Web App](media/FBCimage20.png)

2. <span data-ttu-id="ce8ec-163">Inserire i dettagli (come illustrato di seguito) e quindi creare l'applicazione Web.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-163">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="ce8ec-164">Si noti che il nome immesso nella casella **nome app** viene utilizzato per creare l'URL del servizio app di Azure; ad esempio, fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-164">Note that the name that you enter in the **App name** box is used to create the Azure app service URL; for example, fbconnector.azurewebsites.net.</span></span>

   ![Inserire i dettagli e quindi creare l'app Web](media/FBCimage21.png)

3. <span data-ttu-id="ce8ec-166">Passare alla nuova risorsa Web App creata, fare clic su **Impostazioni applicazione** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-166">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="ce8ec-167">In Impostazioni applicazione fare clic su Aggiungi nuova impostazione e aggiungere le tre impostazioni seguenti: utilizzare i valori (copiati nel file di testo dai passaggi precedenti):</span><span class="sxs-lookup"><span data-stu-id="ce8ec-167">Under Application settings, click Add new setting and add the following three settings: Use the values (that you copied to the text file from the previous steps):</span></span> 

    - <span data-ttu-id="ce8ec-168">**APISecretKey** – è possibile digitare qualsiasi valore come segreto.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-168">**APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="ce8ec-169">Viene utilizzato per accedere all'applicazione Web del connettore nel passaggio 7.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-169">This is used to access the connector web app in Step 7.</span></span>

    - <span data-ttu-id="ce8ec-170">**StorageAccountConnectionString** -URI della stringa di connessione copiato dopo la creazione dell'account di archiviazione di Azure nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-170">**StorageAccountConnectionString** — The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    - <span data-ttu-id="ce8ec-171">**tenantId** -l'ID tenant dell'organizzazione di Office 365 copiato dopo aver creato l'app Facebook Connector in Azure Active Directory nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-171">**tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![Digitare le impostazioni dell'applicazione](media/FBCimage22.png)

4. <span data-ttu-id="ce8ec-173">In **Impostazioni generali**, fare clic **su** avanti accanto a **sempre attiva**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-173">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="ce8ec-174">Fare clic su **Salva** nella parte superiore della pagina per salvare le impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-174">Click **Save** at the top of the page to save the application settings.</span></span>

   ![Salvare le impostazioni dell'applicazione](media/FBCimage23.png)

5. <span data-ttu-id="ce8ec-176">Il passaggio finale consiste nel caricare il codice sorgente dell'app del connettore in Azure scaricato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-176">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="ce8ec-177">In un Web browser, passare a https://<AzureAppResourceName>. SCM.azurewebsites.NET/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-177">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="ce8ec-178">Ad esempio, se il nome della risorsa dell'app di Azure (denominato nel passaggio 2 di questa sezione) è **fbconnector**, si passa a https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-178">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="ce8ec-179">Trascinare e rilasciare il SampleConnector. zip (scaricato nel passaggio 1) in questa pagina.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-179">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="ce8ec-180">Dopo che i file sono stati caricati e la distribuzione ha esito positivo, la pagina avrà un aspetto simile alla schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="ce8ec-180">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Trascinare e rilasciare il SampleConnector. zip in questa pagina](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="ce8ec-182">Passaggio 5: registrare l'app Facebook</span><span class="sxs-lookup"><span data-stu-id="ce8ec-182">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="ce8ec-183">Accedere a <https://developers.facebook.com>, eseguire l'accesso usando le credenziali per l'account per le pagine business di Facebook dell'organizzazione e quindi fare clic su **Aggiungi nuova app**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-183">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![Aggiungere una nuova app per la pagina business di Facebook](media/FBCimage25.png)

2. <span data-ttu-id="ce8ec-185">Creare un nuovo ID app.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-185">Create a new app ID.</span></span>

   ![Creare un nuovo ID app](media/FBCimage26.png)

3. <span data-ttu-id="ce8ec-187">Nel riquadro di spostamento a sinistra, fare clic su **Aggiungi prodotti** e quindi fare clic su **Configura** nella sezione **login Facebook** .</span><span class="sxs-lookup"><span data-stu-id="ce8ec-187">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Fare clic su Aggiungi prodotti](media/FBCimage27.png)

4. <span data-ttu-id="ce8ec-189">Nella pagina integrazione account di accesso di Facebook fare clic su **Web**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-189">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Fare clic su Web nella pagina integrazione login Facebook](media/FBCimage28.png)

5. <span data-ttu-id="ce8ec-191">Aggiungere l'URL del servizio app di Azure; ad esempio `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-191">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Aggiungere l'URL del servizio app di Azure](media/FBCimage29.png)

6. <span data-ttu-id="ce8ec-193">Completare la sezione Guida introduttiva della configurazione dell'account di accesso di Facebook.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-193">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Completare la sezione Guida introduttiva](media/FBCimage30.png)

7. <span data-ttu-id="ce8ec-195">Nel riquadro di spostamento a sinistra in **login Facebook**, fare clic su **Impostazioni**e aggiungere l'URI di reindirizzamento OAuth nella casella **Valid URI di reindirizzamento OAuth** .</span><span class="sxs-lookup"><span data-stu-id="ce8ec-195">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="ce8ec-196">Utilizzare il formato \*\* \<connectorserviceuri>/views/facebookoauth\*\*, in cui il valore di connectorserviceuri è l'URL del servizio app di Azure per l'organizzazione. ad esempio, `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-196">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Aggiungere l'URI di reindirizzamento OAuth alla casella degli URI di reindirizzamento OAuth validi](media/FBCimage31.png)

8. <span data-ttu-id="ce8ec-198">Nel riquadro di spostamento a sinistra, fare clic su **Aggiungi prodotti** e quindi fare clic su **webhook.**</span><span class="sxs-lookup"><span data-stu-id="ce8ec-198">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="ce8ec-199">Nel menu a discesa della **pagina** , fare clic su **pagina**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-199">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![Fare clic su Aggiungi prodotti e quindi su \* \* webhooks](media/FBCimage32.png)

9. <span data-ttu-id="ce8ec-201">Aggiungere l'URL di callback di Webhook e aggiungere un token di verifica.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-201">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="ce8ec-202">Il formato dell'URL di callback, utilizzare il formato \*\* <connectorserviceuri>/API/FbPageWebhook\*\*, in cui il valore di connectorserviceuri è l'URL del servizio app di Azure per l'organizzazione. ad esempio `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-202">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span> 

    <span data-ttu-id="ce8ec-203">Il token di verifica dovrebbe essere simile a una password complessa.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-203">The verify token should similar to a strong password.</span></span> <span data-ttu-id="ce8ec-204">Copiare il token di verifica in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-204">Copy the verify token to a text file or other storage location.</span></span>

        ![Add the verify token](media/FBCimage33.png)

10. <span data-ttu-id="ce8ec-205">Testare e sottoscrivere l'endpoint per il feed.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-205">Test and subscribe to the endpoint for feed.</span></span>

    ![Testare e sottoscrivere l'endpoint](media/FBCimage34.png)

11. <span data-ttu-id="ce8ec-207">Aggiungere un URL di privacy, un'icona dell'app e un utilizzo aziendale.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-207">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="ce8ec-208">Inoltre, copiare l'ID app e l'applicazione segreta in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-208">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Aggiungere un URL di privacy, un'icona App e un utilizzo aziendale](media/FBCimage35.png)

12. <span data-ttu-id="ce8ec-210">Rendere pubblico l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-210">Make the app public.</span></span>

    ![Rendere pubblico l'app](media/FBCimage36.png)

13. <span data-ttu-id="ce8ec-212">Aggiungere un utente al ruolo di amministratore o tester.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-212">Add user to the admin or tester role.</span></span>

    ![Aggiungere un utente al ruolo di amministratore o tester](media/FBCimage37.png)

14. <span data-ttu-id="ce8ec-214">Aggiungere l'autorizzazione di **accesso al contenuto pubblico della pagina** .</span><span class="sxs-lookup"><span data-stu-id="ce8ec-214">Add the **Page Public Content Access** permission.</span></span>

    ![dd la pagina autorizzazione di accesso al contenuto pubblico](media/FBCimage38.png)

15. <span data-ttu-id="ce8ec-216">Aggiungere l'autorizzazione Manage Pages.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-216">Add Manage Pages permission.</span></span>

    ![Aggiungere l'autorizzazione Gestisci pagine](media/FBCimage39.png)

16. <span data-ttu-id="ce8ec-218">Ottenere l'applicazione recensita da Facebook.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-218">Get the application reviewed by Facebook.</span></span>

    ![Ottenere l'applicazione recensita da Facebook](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="ce8ec-220">Passaggio 6: configurare l'applicazione Web del connettore</span><span class="sxs-lookup"><span data-stu-id="ce8ec-220">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="ce8ec-221">Passare a https://\<AzureAppResourceName>. azurewebsites.NET (dove AzureAppResourceName è il nome della risorsa di Azure App denominata nel passaggio 4), ad esempio, se il nome è **fbconnector**, andare a `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-221">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="ce8ec-222">La Home page dell'app avrà lo stesso aspetto della schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="ce8ec-222">The home page of the app will look like the following screenshot:</span></span>

   ![Accedere all'applicazione Web del connettore](media/FBCimage41.png)

2. <span data-ttu-id="ce8ec-224">Fare clic su **Configura** per visualizzare una pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-224">Click **Configure** to display a sign in page.</span></span>
 
   ![Fare clic su Configura per visualizzare una pagina di accesso](media/FBCimage42.png)

3. <span data-ttu-id="ce8ec-226">Nella casella ID tenant digitare o incollare l'ID tenant (ottenuto nel passaggio 2).</span><span class="sxs-lookup"><span data-stu-id="ce8ec-226">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="ce8ec-227">Nella casella password digitare o incollare il APISecretKey (ottenuto nel passaggio 2), quindi fare clic su **imposta impostazioni di configurazione** per visualizzare la pagina **Dettagli di configurazione** .</span><span class="sxs-lookup"><span data-stu-id="ce8ec-227">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![Accedere con l'ID e la password del tenant e passare alla pagina dei dettagli di configurazione](media/FBCimage43.png)

4. <span data-ttu-id="ce8ec-229">In **Dettagli di configurazione**, immettere le impostazioni di configurazione seguenti</span><span class="sxs-lookup"><span data-stu-id="ce8ec-229">Under **Configuration Details**, enter the following configuration settings</span></span> 

   - <span data-ttu-id="ce8ec-230">**ID applicazione Facebook** -ID app per l'applicazione Facebook ottenuta al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-230">**Facebook application ID** – The app ID for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="ce8ec-231">**Segreto dell'applicazione Facebook** : il segreto dell'app per l'applicazione Facebook ottenuta al passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-231">**Facebook application secret** – The app secret for the Facebook application that you obtained in Step 5.</span></span>
   - <span data-ttu-id="ce8ec-232">**Facebook webhooks Verify token** – il token di verifica creato nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-232">**Facebook webhooks verify token** – The verify token that you created in Step 5.</span></span>
   - <span data-ttu-id="ce8ec-233">**ID applicazione AAD** -ID applicazione per l'app Azure Active Directory creata al passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-233">**AAD application ID** – The application ID for the Azure Active Directory app that you created in Step 2.</span></span>
   - <span data-ttu-id="ce8ec-234">**Segreto dell'applicazione AAD** : il valore del segreto di APISecretKey creato nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-234">**AAD application secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   - <span data-ttu-id="ce8ec-235">**URI dell'applicazione AAD** – URI dell'applicazione AAD ottenuto nel passaggio 2; ad esempio, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-235">**AAD application Uri** – The AAD application Uri obtained in Step 2; for example, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.</span></span>
   - <span data-ttu-id="ce8ec-236">**Chiave di strumentazione Insights app** : lasciare vuota questa casella.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-236">**App insights instrumentation key** – Leave this box blank.</span></span>

5. <span data-ttu-id="ce8ec-237">Fare clic su **Salva** per salvare le impostazioni del connettore.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-237">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="ce8ec-238">Passaggio 7: configurare un connettore personalizzato nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="ce8ec-238">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="ce8ec-239">Andare a <https://protection.office.com> e quindi fare clic su data **governance \> Import \> Archive data di terze parti**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-239">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

   ![Accedere al centro sicurezza e conformità e fare clic su data governance > Import > Archive data di terze parti](media/FBCimage44.png)

2.  <span data-ttu-id="ce8ec-241">Fare clic su **Aggiungi connettore** e quindi su **pagine di Facebook**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-241">Click **Add a connector** and then click **Facebook pages**.</span></span>

    ![Aggiungere un connettore di Facebook configurare il connettore](media/FBCimage46.png)

3.  <span data-ttu-id="ce8ec-243">Nella pagina **Aggiungi applicazione del connettore** , immettere le informazioni seguenti e quindi fare clic su **convalida connettore**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-243">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    - <span data-ttu-id="ce8ec-244">Nella prima casella digitare un nome per il connettore, ad esempio **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-244">In the first box, type a name for the connector, such as **Facebook**.</span></span>
    - <span data-ttu-id="ce8ec-245">Nella seconda casella digitare o incollare il valore dell'APISecretKey aggiunto nel passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-245">In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    - <span data-ttu-id="ce8ec-246">Nella terza casella digitare o incollare l'URL del servizio app di Azure; ad esempio `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-246">In the third box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>
 
    <span data-ttu-id="ce8ec-247">Dopo che il connettore è stato convalidato, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-247">After the connector is successfully validated, click **Next**.</span></span>
    
    ![Fare clic su Avanti dopo che il connettore è stato convalidato](media/FBCimage47.png)

4.  <span data-ttu-id="ce8ec-249">Fare clic su **login con app connettore**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-249">Click **Login with Connector App**.</span></span>

    ![Fare clic su login con app Connector](media/FBCimage45.png)

5. <span data-ttu-id="ce8ec-251">Digitare o incollare di nuovo il APISecretKey e quindi fare clic su **accedi al servizio connettore**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-251">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![Digitare o incollare il APISecretKey e quindi fare clic sul pulsante di accesso](media/FBCimage48.png)

6. <span data-ttu-id="ce8ec-253">Fare clic su **login con Facebook**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-253">Click **Login with Facebook**.</span></span>

   ![Fare clic su \* \* login con Facebook](media/FBCimage49.png)

7. <span data-ttu-id="ce8ec-255">Nella pagina **Accedi alla pagina Facebook** accedere usando le credenziali per l'account per le pagine business di Facebook dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-255">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="ce8ec-256">Assicurarsi che l'account di Facebook a cui è stato effettuato l'accesso sia assegnato il ruolo di amministratore per le pagine business di Facebook dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ce8ec-256">Make sure the Facebook account that you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![Accedere a Facebook](media/FBCimage50.png)

8. <span data-ttu-id="ce8ec-258">Fare clic su **Seleziona pagine** per scegliere le pagine business dell'organizzazione che si desidera archiviare in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-258">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![Fare clic su Seleziona pagine per visualizzare le pagine aziendali dell'organizzazione](media/FBCimage51.png)

9. <span data-ttu-id="ce8ec-260">Viene visualizzato un elenco delle pagine business gestite dall'account di Facebook in cui è stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-260">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="ce8ec-261">Selezionare la pagina da archiviare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-261">Select the page to archive and then click **Save**.</span></span>

    ![Selezionare la pagina aziendale dell'organizzazione che si desidera archiviare](media/FBCimage52.png)

10. <span data-ttu-id="ce8ec-263">Fare clic su **fine** per uscire dal programma di installazione dell'app del servizio connettore.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-263">Click **Finish** to exit the setup of the connector service app.</span></span>

    ![Fare clic su fine per uscire dall'applicazione del servizio di connessione](media/FBCimage53.png)

11. <span data-ttu-id="ce8ec-265">Nella pagina **Imposta filtri** è possibile applicare un filtro per importare e archiviare gli elementi di una determinata età.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-265">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="ce8ec-266">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-266">Click **Next**.</span></span>

    ![Applicare un filtro per importare gli elementi di una determinata età](media/FBCimage54.png)

12. <span data-ttu-id="ce8ec-268">Nella pagina **Imposta account di archiviazione** selezionare la cassetta postale di Office 365 in cui verranno importate le pagine di business di Facebook selezionate in precedenza.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-268">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![Specificare gli elementi di archiviazione delle cassette postali di Office 365 importati da Facebook](media/FBCimage55.png)

13. <span data-ttu-id="ce8ec-270">Esaminare le impostazioni e quindi fare clic su **fine** per completare la configurazione del connettore nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-270">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![Esaminare le impostazioni del connettore](media/FBCimage56.png)

14. <span data-ttu-id="ce8ec-272">Passare alla pagina di **archiviazione dei dati di terze parti** per visualizzare lo stato di avanzamento del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="ce8ec-272">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![Passare alla pagina di archiviazione dei dati di terze parti per monitorare il processo di importazione](media/FBCimage58.png)
