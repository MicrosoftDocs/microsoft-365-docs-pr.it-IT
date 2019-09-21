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
ms.openlocfilehash: 1f5b0f241616cc95e79e80d054a8782f97c5887b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071021"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a>Distribuire un connettore per archiviare i dati di Facebook in Office 365

Questo articolo contiene il processo dettagliato per la distribuzione di un connettore che utilizza il servizio di importazione di Office 365 per importare i dati da pagine business di Facebook a Office 365. Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore Facebook, vedere [use a sample Connector to Archive Facebook Data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md). 

## <a name="step-1-download-the-package"></a>Passaggio 1: scaricare il pacchetto

Scaricare il pacchetto precompilato dalla sezione Release nell'archivio GitHub all'indirizzo <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>. Nella versione più recente, scaricare il file zip denominato **SampleConnector. zip**. È possibile caricare il file zip in Azure nel passaggio 4.

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Passaggio 2: creare un'app in Azure Active Directory

1. Accedere a <https://portal.azure.com> e accedere con le credenziali di un account di amministratore globale di Office 365.

    ![Creare un'app in AAD](media/FBCimage1.png)

2. Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.

    ![](media/FBCimage2.png)

3. Nel riquadro di spostamento a sinistra, fare clic su **registrazioni app (anteprima)** e quindi fare clic su **nuova registrazione**.

    ![](media/FBCimage3.png)

4. Registrare l'applicazione. In URI di reindirizzamento, selezionare Web nell'elenco a discesa tipo di applicazione e <https://portal.azure.com> quindi digitare nella casella per l'URI.

   ![](media/FBCimage4.png)

5. Copiare l'ID dell' **applicazione (client)** e la **Directory (tenant)** e salvarli in un file di testo o in un'altra posizione sicura. È possibile utilizzare questi ID nei passaggi successivi.

   ![](media/FBCimage5.png)

6. Accedere a **certificati & segreti per la nuova app.**

   ![](media/FBCimage6.png)

7. Fare clic su **nuovo client segreto**

   ![](media/FBCimage7.png)

8. Creare un nuovo segreto. Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza. 

    ![](media/FBCimage8.png)

9. Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione. Si tratta del segreto dell'applicazione AAD utilizzato nei passaggi successivi.

   ![](media/FBCimage9.png)

10. Andare a **manifest** e copiare il identifierUris (denominato anche URI dell'applicazione AAD) come evidenziato nella schermata seguente. Copiare l'URI dell'applicazione AAD in un file di testo o in un altro percorso di archiviazione. Viene utilizzato nel passaggio 6.

   ![](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a>Passaggio 3: creare un account di archiviazione di Azure

1. Passare alla Home page di Azure per l'organizzazione.

    ![](media/FBCimage11.png)

2. Fare clic su **Crea una risorsa** e digitare **account di archiviazione** nella casella di ricerca.

    ![](media/FBCimage12.png)

3. Fare clic su **spazio di archiviazione**e quindi su **account di archiviazione**.

    ![](media/FBCimage13.png)

4. Nella pagina **Crea account di archiviazione** , nella casella sottoscrizione, selezionare **pay-as-you-go** o **versione di valutazione gratuita** a seconda del tipo di sottoscrizione di Azure di cui si dispone. Selezionare o creare un gruppo di risorse.

    ![](media/FBCimage14.png)

5. Digitare un nome per l'account di archiviazione.

    ![](media/FBCimage15.png)

6. Esaminare e quindi fare clic su **Crea** per creare l'account di archiviazione.

    ![](media/FBCimage16.png)

7. Dopo alcuni istanti, fare clic su **Aggiorna** e quindi su **Vai a risorsa** per passare all'account di archiviazione.

    ![](media/FBCimage17.png)

8. Fare clic su **tasti di accesso** nel riquadro di spostamento a sinistra.

    ![](media/FBCimage18.png)

9. Copiare una **stringa di connessione** e salvarla in un file di testo o in un altro percorso di archiviazione. Questa operazione viene utilizzata durante la creazione di una risorsa Web App.

    ![](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a>Passaggio 4: creare una nuova risorsa Web App in Azure

1. Nella **Home** page del portale di Azure, fare clic su **Crea una \> risorsa \> tutto Web App**. Nella pagina **Web App** fare clic su **Crea**. 

   ![](media/FBCimage20.png)

2. Inserire i dettagli (come illustrato di seguito) e quindi creare l'applicazione Web. Si noti che il nome immesso nella casella **nome app** viene utilizzato per creare l'URL del servizio app di Azure; ad esempio, fbconnector.azurewebsites.net.

   ![](media/FBCimage21.png)

3. Passare alla nuova risorsa Web App creata, fare clic su **Impostazioni applicazione** nel riquadro di spostamento sinistro. In Impostazioni applicazione fare clic su Aggiungi nuova impostazione e aggiungere le tre impostazioni seguenti: utilizzare i valori (copiati nel file di testo dai passaggi precedenti): 

    – **APISecretKey** – è possibile digitare qualsiasi valore come segreto. Viene utilizzato per accedere all'applicazione Web del connettore nel passaggio 7.

    – * * StorageAccountConnectionString: URI della stringa di connessione copiato dopo la creazione dell'account di archiviazione di Azure nel passaggio 3.

    – **tenantId** – l'ID tenant dell'organizzazione di Office 365 copiato dopo aver creato l'app Facebook Connector in Azure Active Directory nel passaggio 2.

    ![](media/FBCimage22.png)

4. In **Impostazioni generali**, fare clic **su** avanti accanto a **sempre attiva**. Fare clic su **Salva** nella parte superiore della pagina per salvare le impostazioni dell'applicazione.

   ![](media/FBCimage23.png)

5. Il passaggio finale consiste nel caricare il codice sorgente dell'app del connettore in Azure scaricato nel passaggio 1. In un Web browser, passare a https://<AzureAppResourceName>. SCM.azurewebsites.NET/ZipDeployUi. Ad esempio, se il nome della risorsa dell'app di Azure (denominato nel passaggio 2 di questa sezione) è **fbconnector**, si passa a https://fbconnector.scm.azurewebsites.net/ZipDeployUi. 

6. Trascinare e rilasciare il SampleConnector. zip (scaricato nel passaggio 1) in questa pagina. Dopo che i file sono stati caricati e la distribuzione ha esito positivo, la pagina avrà un aspetto simile alla schermata seguente:

   ![](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a>Passaggio 5: registrare l'app Facebook

1. Accedere a <https://developers.facebook.com>, eseguire l'accesso usando le credenziali per l'account per le pagine business di Facebook dell'organizzazione e quindi fare clic su **Aggiungi nuova app**.

   ![](media/FBCimage25.png)

2. Creare un nuovo ID app.

   ![](media/FBCimage26.png)

3. Nel riquadro di spostamento a sinistra, fare clic su **Aggiungi prodotti** e quindi fare clic su **Configura** nella sezione **login Facebook** .

   ![](media/FBCimage27.png)

4. Nella pagina integrazione account di accesso di Facebook fare clic su **Web**.

   ![](media/FBCimage28.png)

5. Aggiungere l'URL del servizio app di Azure; ad esempio https://fbconnector.azurewebsites.net.

   ![](media/FBCimage29.png)

6. Completare la sezione Guida introduttiva della configurazione dell'account di accesso di Facebook.

   ![](media/FBCimage30.png)

7. Nel riquadro di spostamento a sinistra in **login Facebook**, fare clic su **Impostazioni**e aggiungere l'URI di reindirizzamento OAuth nella casella **Valid URI di reindirizzamento OAuth** . Utilizzare il formato ** \<connectorserviceuri>/views/facebookoauth**, in cui il valore di connectorserviceuri è l'URL del servizio app di Azure per l'organizzazione. ad esempio, https://fbconnector.azurewebsites.net.

   ![](media/FBCimage31.png)

8. Nel riquadro di spostamento a sinistra, fare clic su **Aggiungi prodotti** e quindi fare clic su **webhook.** Nel menu a discesa della **pagina** , fare clic su **pagina**. 

   ![](media/FBCimage32.png)

9. Aggiungere l'URL di callback di Webhook e aggiungere un token di verifica. Il formato dell'URL di callback, utilizzare il formato ** <connectorserviceuri>/API/FbPageWebhook**, in cui il valore di connectorserviceuri è l'URL del servizio app di Azure per l'organizzazione. ad esempio https://fbconnector.azurewebsites.net. 

    Il token di verifica dovrebbe essere simile a una password complessa. Copiare il token di verifica in un file di testo o in un altro percorso di archiviazione.

     ![](media/FBCimage33.png)

10. Testare e sottoscrivere l'endpoint per il feed.

    ![](media/FBCimage34.png)

11. Aggiungere un URL di privacy, un'icona dell'app e un utilizzo aziendale. Inoltre, copiare l'ID app e l'applicazione segreta in un file di testo o in un altro percorso di archiviazione.

    ![](media/FBCimage35.png)

12. Rendere pubblico l'applicazione.

    ![](media/FBCimage36.png)

13. Aggiungere un utente al ruolo di amministratore o tester.

    ![](media/FBCimage37.png)

14. Aggiungere l'autorizzazione di **accesso al contenuto pubblico della pagina** .

    ![](media/FBCimage38.png)

15. Aggiungere l'autorizzazione Manage Pages.

    ![](media/FBCimage39.png)

16. Ottenere l'applicazione recensita da Facebook.

    ![](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a>Passaggio 6: configurare l'applicazione Web del connettore

1. Passare a https://\<AzureAppResourceName>. azurewebsites.NET (dove AzureAppResourceName è il nome della risorsa di Azure App denominata nel passaggio 4), ad esempio, se il nome è **fbconnector**, andare a https://fbconnector.azurewebsites.net. La Home page dell'app avrà lo stesso aspetto della schermata seguente:


   ![](media/FBCimage41.png)

2. Fare clic su **Configura** per visualizzare una pagina di accesso.
 
   ![](media/FBCimage42.png)

3. Nella casella ID tenant digitare o incollare l'ID tenant (ottenuto nel passaggio 2). Nella casella password digitare o incollare il APISecretKey (ottenuto nel passaggio 2), quindi fare clic su **imposta impostazioni di configurazione** per visualizzare la pagina **Dettagli di configurazione** .

    ![](media/FBCimage43.png)


4. In **Dettagli di configurazione**, immettere le impostazioni di configurazione seguenti 

   - **ID applicazione Facebook** -ID app per l'applicazione Facebook ottenuta al passaggio 5.
   - **Applicazione Facebook Secret** -l'app segreta per l'applicazione Facebook ottenuta al passaggio 5.
   – **Facebook webhooks Verify token** – il token di verifica creato nel passaggio 5.
   - **ID applicazione AAD** -ID applicazione per l'app Azure Active Directory creata al passaggio 2.
   – **AAD Application Secret** – il valore del segreto di APISecretKey creato nel passaggio 4.
   – **URI dell'applicazione AAD** – URI dell'applicazione AAD ottenuto nel passaggio 2; ad esempio, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.
   - **Chiave di strumentazione Insights app** -lasciare vuota questa casella.

5. Fare clic su **Salva** per salvare le impostazioni del connettore.

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>Passaggio 7: configurare un connettore personalizzato nel centro sicurezza & Compliance

1. Andare a <https://protection.office.com> e quindi fare clic su data **governance \> Import \> Archive data di terze parti**.

   ![](media/FBCimage44.png)

2.  Fare clic su **Aggiungi connettore** e quindi su **pagine di Facebook**.

    ![](media/FBCimage46.png)

3.  Nella pagina **Aggiungi applicazione del connettore** , immettere le informazioni seguenti e quindi fare clic su **convalida connettore**.

    – Nella prima casella digitare un nome per il connettore, ad esempio **Facebook**.
    – Nella seconda casella digitare o incollare il valore dell'APISecretKey aggiunto nel passaggio 4.
    – Nella terza casella digitare o incollare l'URL del servizio app di Azure; ad esempio **https://fbconnector.azurewebsites.net**.
 
    Dopo che il connettore è stato convalidato, fare clic su **Avanti**.
    
    ![](media/FBCimage47.png)

4.  Fare clic su **login con app connettore**.

    ![](media/FBCimage45.png)

5. Digitare o incollare di nuovo il APISecretKey e quindi fare clic su **accedi al servizio connettore**.

   ![](media/FBCimage48.png)


6. Fare clic su **login con Facebook.**

   ![](media/FBCimage49.png)

7. Nella pagina **Accedi alla pagina Facebook** accedere usando le credenziali per l'account per le pagine business di Facebook dell'organizzazione. Assicurarsi che l'account di Facebook a cui è stato effettuato l'accesso sia assegnato il ruolo di amministratore per le pagine business di Facebook dell'organizzazione

   ![](media/FBCimage50.png)

8. Fare clic su **Seleziona pagine** per scegliere le pagine business dell'organizzazione che si desidera archiviare in Office 365.

   ![](media/FBCimage51.png)

9. Viene visualizzato un elenco delle pagine business gestite dall'account di Facebook in cui è stato effettuato l'accesso. Selezionare la pagina da archiviare e quindi fare clic su **Salva**.

    ![](media/FBCimage52.png)

10. Fare clic su **prepara** per uscire dal programma di installazione dell'app del servizio connettore.

    ![](media/FBCimage53.png)

11. Nella pagina **Imposta filtri** è possibile applicare un filtro per importare e archiviare gli elementi di una determinata età. Fare clic su **Avanti**.

    ![](media/FBCimage54.png)

12. Nella pagina **Imposta account di archiviazione** selezionare la cassetta postale di Office 365 in cui verranno importate le pagine di business di Facebook selezionate in precedenza.

    ![](media/FBCimage55.png)

13. Esaminare le impostazioni e quindi fare clic su **fine** per completare la configurazione del connettore nel centro sicurezza & conformità.

    ![](media/FBCimage56.png)

14. Passare alla pagina di **archiviazione dei dati di terze parti** per visualizzare lo stato di avanzamento del processo di importazione.

    ![](media/FBCimage58.png)
