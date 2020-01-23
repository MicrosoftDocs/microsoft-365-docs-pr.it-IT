---
title: Distribuire un connettore per archiviare i dati di pagine business di Facebook
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
description: Gli amministratori possono configurare un connettore nativo per l'importazione e l'archiviazione di pagine business di Facebook su Microsoft 365. Dopo aver importato i dati in Microsoft 365, è possibile utilizzare le funzionalità di conformità, ad esempio il blocco legale, la ricerca di contenuto e i criteri di conservazione per gestire la governance dei dati di Facebook dell'organizzazione.
ms.openlocfilehash: 1222a82e3a3b8415aa3fc98cd3c06376e491beb0
ms.sourcegitcommit: 9b390881fe661deb0568b4b86a5a9094f3c795f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269419"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="d4b49-104">Distribuire un connettore per archiviare i dati di pagine business di Facebook</span><span class="sxs-lookup"><span data-stu-id="d4b49-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="d4b49-105">In questo articolo è incluso il processo dettagliato per la distribuzione di un connettore che utilizza il servizio di importazione Microsoft 365 per importare i dati dalle pagine business di Facebook a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4b49-105">This article contains the step-by-step process to deploy a connector that uses the Microsoft 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="d4b49-106">Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore Facebook, vedere [configurare un connettore per archiviare i dati di Facebook](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="d4b49-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="d4b49-107">Passaggio 1: creare un'app in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d4b49-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="d4b49-108">Accedere a <https://portal.azure.com> e accedere con le credenziali di un account di amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d4b49-108">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![Creare un'app in AAD](media/FBCimage1.png)

2. <span data-ttu-id="d4b49-110">Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Fare clic su Azure Active Directory](media/FBCimage2.png)

3. <span data-ttu-id="d4b49-112">Nel riquadro di spostamento a sinistra, fare clic su **registrazioni app (anteprima)** e quindi fare clic su **nuova registrazione**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Fare clic su \* \* registrazioni app (anteprima) \* \* e quindi fare clic su \* \* nuova registrazione \* \*](media/FBCimage3.png)

4. <span data-ttu-id="d4b49-114">Registrare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4b49-114">Register the application.</span></span> <span data-ttu-id="d4b49-115">In URI di reindirizzamento, selezionare Web nell'elenco a discesa tipo di applicazione e <https://portal.azure.com> quindi digitare nella casella per l'URI.</span><span class="sxs-lookup"><span data-stu-id="d4b49-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Registrare l'applicazione](media/FBCimage4.png)

5. <span data-ttu-id="d4b49-117">Copiare l'ID dell' **applicazione (client)** e la **Directory (tenant)** e salvarli in un file di testo o in un'altra posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="d4b49-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="d4b49-118">È possibile utilizzare questi ID nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="d4b49-118">You use these IDs in later steps.</span></span>

   ![Copiare l'ID applicazione e l'ID directory e salvarli](media/FBCimage5.png)

6. <span data-ttu-id="d4b49-120">Accedere a **certificati & segreti per la nuova app.**</span><span class="sxs-lookup"><span data-stu-id="d4b49-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Accedere a certificati & segreti per la nuova applicazione](media/FBCimage6.png)

7. <span data-ttu-id="d4b49-122">Fare clic su **nuovo client segreto**</span><span class="sxs-lookup"><span data-stu-id="d4b49-122">Click **New client secret**</span></span>

   ![Fare clic su nuovo client segreto](media/FBCimage7.png)

8. <span data-ttu-id="d4b49-124">Creare un nuovo segreto.</span><span class="sxs-lookup"><span data-stu-id="d4b49-124">Create a new secret.</span></span> <span data-ttu-id="d4b49-125">Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza.</span><span class="sxs-lookup"><span data-stu-id="d4b49-125">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![Digita il segreto e quindi scegli un periodo di scadenza](media/FBCimage8.png)

9. <span data-ttu-id="d4b49-127">Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d4b49-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="d4b49-128">Si tratta del segreto dell'applicazione AAD utilizzato nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="d4b49-128">This is the AAD application secret that you use in later steps.</span></span>

   ![Copiare il valore del segreto e salvarlo](media/FBCimage9.png)

10. <span data-ttu-id="d4b49-130">Andare a **manifest** e copiare il identifierUris (denominato anche URI dell'applicazione AAD) come evidenziato nella schermata seguente.</span><span class="sxs-lookup"><span data-stu-id="d4b49-130">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="d4b49-131">Copiare l'URI dell'applicazione AAD in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d4b49-131">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="d4b49-132">Viene utilizzato nel passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="d4b49-132">You use it in Step 6.</span></span>

    ![Passare a manifest e copiare l'URI dell'applicazione AAD](media/FBCimage10.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="d4b49-134">Passaggio 2: distribuire il servizio Web del connettore da GitHub all'account di Azure</span><span class="sxs-lookup"><span data-stu-id="d4b49-134">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="d4b49-135">Accedere a [questo sito GitHub](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) e fare clic su **Distribuisci in Azure**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-135">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Fare clic su Distribuisci in Azure](media/FBCimage11.png)

2. <span data-ttu-id="d4b49-137">Dopo aver fatto clic su **Distribuisci in Azure**, verrà reindirizzato a un portale di Azure con una pagina modello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d4b49-137">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="d4b49-138">Compilare i dettagli delle **Impostazioni e delle** informazioni di **base** e quindi fare clic su **acquisto**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-138">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

    - <span data-ttu-id="d4b49-139">**Sottoscrizione:** Selezionare l'abbonamento di Azure in cui si desidera distribuire il servizio Web del connettore di pagine business di Facebook.</span><span class="sxs-lookup"><span data-stu-id="d4b49-139">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>
    
    - <span data-ttu-id="d4b49-140">**Gruppo di risorse:** Scegliere o creare un nuovo gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="d4b49-140">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="d4b49-141">Un gruppo di risorse è un contenitore che contiene risorse correlate per una soluzione di Azure.</span><span class="sxs-lookup"><span data-stu-id="d4b49-141">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="d4b49-142">**Posizione:** Scegliere un percorso.</span><span class="sxs-lookup"><span data-stu-id="d4b49-142">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="d4b49-143">**Nome applicazione Web:** Specificare un nome univoco per il connettore Web App.</span><span class="sxs-lookup"><span data-stu-id="d4b49-143">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="d4b49-144">Il nome del Th deve essere compreso tra 3 e 18 caratteri.</span><span class="sxs-lookup"><span data-stu-id="d4b49-144">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="d4b49-145">Questo nome viene utilizzato per creare l'URL del servizio app di Azure. ad esempio, se si specifica il nome dell'applicazione Web di **fbconnector** , l'URL del servizio app di Azure sarà **fbconnector.azurewebsites.NET**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-145">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="d4b49-146">**tenantId:** L'ID tenant dell'organizzazione Microsoft 365 copiato dopo aver creato l'app connettore Facebook in Azure Active Directory nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d4b49-146">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="d4b49-147">**APISecretKey:** È possibile digitare qualsiasi valore come segreto.</span><span class="sxs-lookup"><span data-stu-id="d4b49-147">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="d4b49-148">Viene utilizzato per accedere all'applicazione Web del connettore nel passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="d4b49-148">This is used to access the connector web app in Step 5.</span></span>
   
     ![Fare clic su Crea un account di archiviazione di risorse e tipi](media/FBCimage12.png)

3. <span data-ttu-id="d4b49-150">Dopo che la distribuzione ha avuto esito positivo, la pagina avrà un aspetto simile alla schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="d4b49-150">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

     ![Fare clic su archiviazione e quindi su account di archiviazione](media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="d4b49-152">Passaggio 3: registrare l'app Facebook</span><span class="sxs-lookup"><span data-stu-id="d4b49-152">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="d4b49-153">Accedere a <https://developers.facebook.com>, eseguire l'accesso usando le credenziali per l'account per le pagine business di Facebook dell'organizzazione e quindi fare clic su **Aggiungi nuova app**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-153">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![Aggiungere una nuova app per la pagina business di Facebook](media/FBCimage25.png)

2. <span data-ttu-id="d4b49-155">Creare un nuovo ID app.</span><span class="sxs-lookup"><span data-stu-id="d4b49-155">Create a new app ID.</span></span>

   ![Creare un nuovo ID app](media/FBCimage26.png)

3. <span data-ttu-id="d4b49-157">Nel riquadro di spostamento a sinistra, fare clic su **Aggiungi prodotti** e quindi fare clic su **Configura** nella sezione **login Facebook** .</span><span class="sxs-lookup"><span data-stu-id="d4b49-157">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Fare clic su Aggiungi prodotti](media/FBCimage27.png)

4. <span data-ttu-id="d4b49-159">Nella pagina integrazione account di accesso di Facebook fare clic su **Web**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-159">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Fare clic su Web nella pagina integrazione login Facebook](media/FBCimage28.png)

5. <span data-ttu-id="d4b49-161">Aggiungere l'URL del servizio app di Azure; ad esempio `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="d4b49-161">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Aggiungere l'URL del servizio app di Azure](media/FBCimage29.png)

6. <span data-ttu-id="d4b49-163">Completare la sezione Guida introduttiva della configurazione dell'account di accesso di Facebook.</span><span class="sxs-lookup"><span data-stu-id="d4b49-163">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Completare la sezione Guida introduttiva](media/FBCimage30.png)

7. <span data-ttu-id="d4b49-165">Nel riquadro di spostamento a sinistra in **login Facebook**, fare clic su **Impostazioni**e aggiungere l'URI di reindirizzamento OAuth nella casella **Valid URI di reindirizzamento OAuth** .</span><span class="sxs-lookup"><span data-stu-id="d4b49-165">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="d4b49-166">Utilizzare il formato \*\* \<connectorserviceuri>/views/facebookoauth\*\*, in cui il valore di connectorserviceuri è l'URL del servizio app di Azure per l'organizzazione. ad esempio, `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="d4b49-166">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Aggiungere l'URI di reindirizzamento OAuth alla casella degli URI di reindirizzamento OAuth validi](media/FBCimage31.png)

8. <span data-ttu-id="d4b49-168">Nel riquadro di spostamento a sinistra, fare clic su **Aggiungi prodotti** e quindi fare clic su **webhook.**</span><span class="sxs-lookup"><span data-stu-id="d4b49-168">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="d4b49-169">Nel menu a discesa della **pagina** , fare clic su **pagina**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-169">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![Fare clic su Aggiungi prodotti e quindi su \* \* webhooks](media/FBCimage32.png)

9. <span data-ttu-id="d4b49-171">Aggiungere l'URL di callback di Webhook e aggiungere un token di verifica.</span><span class="sxs-lookup"><span data-stu-id="d4b49-171">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="d4b49-172">Il formato dell'URL di callback, utilizzare il formato \*\* <connectorserviceuri>/API/FbPageWebhook\*\*, in cui il valore di connectorserviceuri è l'URL del servizio app di Azure per l'organizzazione. ad esempio `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="d4b49-172">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span> 

    <span data-ttu-id="d4b49-173">Il token di verifica dovrebbe essere simile a una password complessa.</span><span class="sxs-lookup"><span data-stu-id="d4b49-173">The verify token should similar to a strong password.</span></span> <span data-ttu-id="d4b49-174">Copiare il token di verifica in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d4b49-174">Copy the verify token to a text file or other storage location.</span></span>

        ![Add the verify token](media/FBCimage33.png)

10. <span data-ttu-id="d4b49-175">Testare e sottoscrivere l'endpoint per il feed.</span><span class="sxs-lookup"><span data-stu-id="d4b49-175">Test and subscribe to the endpoint for feed.</span></span>

    ![Testare e sottoscrivere l'endpoint](media/FBCimage34.png)

11. <span data-ttu-id="d4b49-177">Aggiungere un URL di privacy, un'icona dell'app e un utilizzo aziendale.</span><span class="sxs-lookup"><span data-stu-id="d4b49-177">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="d4b49-178">Inoltre, copiare l'ID app e l'applicazione segreta in un file di testo o in un altro percorso di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="d4b49-178">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Aggiungere un URL di privacy, un'icona App e un utilizzo aziendale](media/FBCimage35.png)

12. <span data-ttu-id="d4b49-180">Rendere pubblico l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4b49-180">Make the app public.</span></span>

    ![Rendere pubblico l'app](media/FBCimage36.png)

13. <span data-ttu-id="d4b49-182">Aggiungere un utente al ruolo di amministratore o tester.</span><span class="sxs-lookup"><span data-stu-id="d4b49-182">Add user to the admin or tester role.</span></span>

    ![Aggiungere un utente al ruolo di amministratore o tester](media/FBCimage37.png)

14. <span data-ttu-id="d4b49-184">Aggiungere l'autorizzazione di **accesso al contenuto pubblico della pagina** .</span><span class="sxs-lookup"><span data-stu-id="d4b49-184">Add the **Page Public Content Access** permission.</span></span>

    ![dd la pagina autorizzazione di accesso al contenuto pubblico](media/FBCimage38.png)

15. <span data-ttu-id="d4b49-186">Aggiungere l'autorizzazione Manage Pages.</span><span class="sxs-lookup"><span data-stu-id="d4b49-186">Add Manage Pages permission.</span></span>

    ![Aggiungere l'autorizzazione Gestisci pagine](media/FBCimage39.png)

16. <span data-ttu-id="d4b49-188">Ottenere l'applicazione recensita da Facebook.</span><span class="sxs-lookup"><span data-stu-id="d4b49-188">Get the application reviewed by Facebook.</span></span>

    ![Ottenere l'applicazione recensita da Facebook](media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="d4b49-190">Passaggio 4: configurare l'applicazione Web del connettore</span><span class="sxs-lookup"><span data-stu-id="d4b49-190">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="d4b49-191">Passare a https://\<AzureAppResourceName>. azurewebsites.NET (dove AzureAppResourceName è il nome della risorsa di Azure App denominata nel passaggio 4), ad esempio, se il nome è **fbconnector**, andare a `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="d4b49-191">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="d4b49-192">La Home page dell'app avrà lo stesso aspetto della schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="d4b49-192">The home page of the app will look like the following screenshot:</span></span>

   ![Accedere all'applicazione Web del connettore](media/FBCimage41.png)

2. <span data-ttu-id="d4b49-194">Fare clic su **Configura** per visualizzare una pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="d4b49-194">Click **Configure** to display a sign in page.</span></span>
 
   ![Fare clic su Configura per visualizzare una pagina di accesso](media/FBCimage42.png)

3. <span data-ttu-id="d4b49-196">Nella casella ID tenant digitare o incollare l'ID tenant (ottenuto nel passaggio 2).</span><span class="sxs-lookup"><span data-stu-id="d4b49-196">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="d4b49-197">Nella casella password digitare o incollare il APISecretKey (ottenuto nel passaggio 2), quindi fare clic su **imposta impostazioni di configurazione** per visualizzare la pagina dettagli di configurazione.</span><span class="sxs-lookup"><span data-stu-id="d4b49-197">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Accedere con l'ID e la password del tenant e passare alla pagina dei dettagli di configurazione](media/FBCimage43.png)

4. <span data-ttu-id="d4b49-199">Immettere le impostazioni di configurazione seguenti</span><span class="sxs-lookup"><span data-stu-id="d4b49-199">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="d4b49-200">**ID applicazione Facebook:** ID app per l'applicazione Facebook ottenuta al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="d4b49-200">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>
   
   - <span data-ttu-id="d4b49-201">**Segreto dell'applicazione Facebook:** Il segreto dell'app per l'applicazione Facebook ottenuta al passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="d4b49-201">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>
   
   - <span data-ttu-id="d4b49-202">I **webhook di Facebook verificano il token:** Il token di verifica creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="d4b49-202">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="d4b49-203">**ID applicazione AAD:** ID applicazione per l'app Azure Active Directory creata al passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d4b49-203">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>
   
   - <span data-ttu-id="d4b49-204">**Segreto dell'applicazione AAD:** Il valore del segreto di APISecretKey creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d4b49-204">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="d4b49-205">Fare clic su **Salva** per salvare le impostazioni del connettore.</span><span class="sxs-lookup"><span data-stu-id="d4b49-205">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="d4b49-206">Passaggio 5: configurare un connettore Facebook nel centro conformità di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d4b49-206">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="d4b49-207">Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fare clic su **connettori dati** nel NAV sinistro.</span><span class="sxs-lookup"><span data-stu-id="d4b49-207">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="d4b49-208">Nella pagina **connettori dati (anteprima)** in **pagine business di Facebook**fare clic su **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-208">On the **Data connectors (preview)** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="d4b49-209">Nella pagina **Facebook business Pages** fare clic su **Aggiungi connettore**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-209">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="d4b49-210">Nella pagina **condizioni del servizio** fare clic su **Accetto**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-210">On the **Terms of service** page, click **Accept**.</span></span>

5.  <span data-ttu-id="d4b49-211">Nella pagina **Aggiungi credenziali per l'app del connettore** , immettere le informazioni seguenti e quindi fare clic su **convalida connessione**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-211">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

    ![Immettere le credenziali delle app del connettore](media/TCimage38.png)

    - <span data-ttu-id="d4b49-213">Nella casella **nome** Digitare un nome per il connettore, ad esempio pagina di **notizie di Facebook**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-213">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>
    
    - <span data-ttu-id="d4b49-214">Nella casella **URL di connessione** Digitare o incollare l'URL del servizio app di Azure; ad esempio `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="d4b49-214">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="d4b49-215">Nella casella **password** Digitare o incollare il valore dell'APISecretKey aggiunto nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="d4b49-215">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>
    
    - <span data-ttu-id="d4b49-216">Nella casella **ID app di Azure** Digitare o incollare il valore dell'ID applicazione (client) denominato anche ID dell'applicazione AAD creato nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="d4b49-216">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>
 
6. <span data-ttu-id="d4b49-217">Dopo aver convalidato correttamente la connessione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-217">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="d4b49-218">Nella pagina **autorizza Microsoft 365 per importare i dati** , digitare o incollare di nuovo APISecretKey e quindi fare clic su **login Web App**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-218">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="d4b49-219">Nella pagina **Configura applicazione del connettore Facebook** , fare clic su **account di accesso con Facebook** e accedere usando le credenziali per l'account per le pagine business di Facebook dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d4b49-219">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="d4b49-220">Assicurarsi che l'account di Facebook a cui è stato effettuato l'accesso sia assegnato il ruolo di amministratore per le pagine business di Facebook dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d4b49-220">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Accedere con Facebook](media/FBCimage50.png)

9. <span data-ttu-id="d4b49-222">Viene visualizzato un elenco delle pagine business gestite dall'account di Facebook in cui è stato effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d4b49-222">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="d4b49-223">Selezionare la pagina da archiviare e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-223">Select the page to archive and then click **Next**.</span></span>

    ![Selezionare la pagina aziendale dell'organizzazione che si desidera archiviare](media/FBCimage52.png)

10. <span data-ttu-id="d4b49-225">Fare clic su **continua** per uscire dal programma di installazione dell'app del servizio connettore.</span><span class="sxs-lookup"><span data-stu-id="d4b49-225">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="d4b49-226">Nella pagina **Imposta filtri** è possibile applicare un filtro per importare inizialmente gli elementi di una determinata età.</span><span class="sxs-lookup"><span data-stu-id="d4b49-226">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="d4b49-227">Selezionare un'età, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-227">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="d4b49-228">Nella pagina **Scegli percorso di archiviazione** , digitare l'indirizzo di posta elettronica della cassetta postale di Microsoft 365 a cui verranno importati gli elementi di Facebook e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d4b49-228">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="d4b49-229">Sul **consenso amministratore**, fare clic su **Fornisci consenso** e quindi eseguire la procedura.</span><span class="sxs-lookup"><span data-stu-id="d4b49-229">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="d4b49-230">È necessario essere un amministratore globale per fornire il consenso per il servizio di importazione di Office 365 per accedere ai dati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d4b49-230">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="d4b49-231">Fare clic su **Avanti** per esaminare le impostazioni del connettore e quindi fare clic su **fine** per completare la configurazione del connettore.</span><span class="sxs-lookup"><span data-stu-id="d4b49-231">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="d4b49-232">Nel centro conformità, andare alla pagina **connettori dati** e fare clic sulla scheda **connettori** per visualizzare lo stato di avanzamento del processo di importazione.</span><span class="sxs-lookup"><span data-stu-id="d4b49-232">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
