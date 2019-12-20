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
ms.openlocfilehash: 87faad6546d70b1e3893e2f5737af189ebb5f77b
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806149"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a>Distribuire un connettore per archiviare i dati di Twitter

Questo articolo contiene il processo dettagliato per la distribuzione di un connettore che utilizza il servizio di importazione di Office 365 per importare i dati dall'account Twitter dell'organizzazione a Office 365. Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore Twitter, vedere [use a sample Connector to Archive Twitter data in Office 365 (Preview)](archive-twitter-data-with-sample-connector.md). 

## <a name="step-1-download-the-package"></a>Passaggio 1: scaricare il pacchetto

Scaricare il pacchetto precompilato dalla sezione Release nell'archivio GitHub all'indirizzo [https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases). Nella versione più recente, scaricare il file zip denominato **SampleConnector. zip**. È possibile caricare il file zip in Azure nel passaggio 4.

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Passaggio 2: creare un'app in Azure Active Directory

1. Accedere a <https://portal.azure.com> e accedere con le credenziali di un account di amministratore globale di Office 365.

   ![Accedere a Azure](media/TCimage01.png)

2. Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.

   ![Accedere a Azure Active Directory](media/TCimage02.png)

3. Nel riquadro di spostamento a sinistra, fare clic su **registrazioni app (anteprima)** e quindi fare clic su **nuova registrazione**.

   ![Creare una nuova registrazione delle app](media/TCimage03.png)

4. Registrare l'applicazione. In **URI di reindirizzamento (facoltativo)** selezionare **Web** nell'elenco a discesa tipo di applicazione e quindi `https://portal.azure.com` digitare nella casella relativa all'URI.

   ![Tipo https://portal.azure.com per l'URI di Reindirizzamento ](media/TCimage04.png)

5. Copiare l'ID dell' **applicazione (client)** e la **Directory (tenant)** e salvarli in un file di testo o in un'altra posizione sicura. È possibile utilizzare questi ID nei passaggi successivi.

    ![Copiare e salvare l'ID applicazione e l'ID directory](media/TCimage05.png)

6. Accedere a **certificati & segreti per la nuova applicazione** e in **segreti client** fare clic su **nuovo segreto client**.

   ![Creare un nuovo segreto client](media/TCimage06.png)

7. Creare un nuovo segreto. Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza. 

   ![Digitare il segreto e scegliere il periodo di scadenza](media/TCimage08.png)

8. Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione. Si tratta del segreto dell'applicazione AAD utilizzato nei passaggi successivi.

   ![Copia e salvataggio del segreto](media/TCimage09.png)

9. Andare a **manifest** e copiare il identifierUris (denominato anche URI dell'applicazione AAD) come evidenziato nella schermata seguente. Copiare l'URI dell'applicazione AAD in un file di testo o in un altro percorso di archiviazione. Viene utilizzato nel passaggio 6.

    ![Copiare e salvare l'URI dell'applicazione AAD](media/TCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a>Passaggio 3: creare un account di archiviazione di Azure

1.  Passare alla Home page di Azure per l'organizzazione.

    ![Home page gi-Azure](media/TCimage11.png)

2. Fare clic su **Crea una risorsa** e digitare **account di archiviazione** nella casella di ricerca.

   ![Creare una risorsa dell'account di archiviazione](media/TCimage12.png)

3. Fare clic su **spazio di archiviazione**e quindi su **account di archiviazione**.

   ![Fare clic su archiviazione e quindi su account di archiviazione](media/TCimage13.png)

4. Nella pagina **Crea account di archiviazione** , nella casella sottoscrizione, selezionare **pay-as-you-go** o **versione di valutazione gratuita** a seconda del tipo di sottoscrizione di Azure di cui si dispone. 

   ![Selezionare un tipo di account di archiviazione](media/TCimage14.png)

5. Selezionare o creare un gruppo di risorse.

   ![Selezionare o creare un gruppo di risorse](media/TCimage15.png)

6. Digitare un nome per l'account di archiviazione.

   ![Assegnare un nome all'account di archiviazione](media/TCimage16.png)

7. Esaminare e quindi fare clic su **Crea** per creare l'account di archiviazione.

   ![Rivedere le impostazioni e quindi creare un account di archiviazione](media/TCimage17.png)

8. Dopo alcuni istanti, fare clic su **Aggiorna** e quindi su **Vai a risorsa** per passare all'account di archiviazione.

   ![Passare all'account di archiviazione appena creato](media/TCimage18.png)

9. Fare clic su **tasti di accesso** nel riquadro di spostamento a sinistra.

   ![Fare clic su tasti di accesso](media/TCimage19.png)

10. Copiare una **stringa di connessione** e salvarla in un file di testo o in un altro percorso di archiviazione. Questa operazione viene utilizzata quando si crea una risorsa Web App nel passaggio 4.

    ![Copiare una stringa di connessione](media/TCimage20.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a>Passaggio 4: creare una nuova risorsa Web App in Azure

1. Nella **Home** page del portale di Azure, fare clic su **Crea una \> risorsa \> tutto Web App**. Nella pagina **Web App** fare clic su **Crea**.

   ![Creare una risorsa Web App in Azure](media/TCimage21.png)

2. Inserire i dettagli (come illustrato di seguito) e quindi creare l'applicazione Web. Il nome immesso nella casella **nome app** viene utilizzato per creare l'URL del servizio app di Azure. ad esempio, twitterconnector.azurewebsites.net.

   ![Nome del tipo per la risorsa dell'applicazione Web. ad esempio twitterconnector.azurewebsites.net ](media/TCimage22.png)

3. Passare alla risorsa nuova applicazione Web creata e fare clic su **Impostazioni applicazione** nel riquadro di spostamento sinistro. In **Impostazioni applicazione**fare clic su **Aggiungi nuova impostazione** e quindi aggiungere le tre impostazioni seguenti. Utilizzare i valori (copiati nel file di testo dai passaggi precedenti): 

    - **APISecretKey** – è possibile digitare qualsiasi valore come segreto. Viene utilizzato per accedere all'applicazione Web del connettore nel passaggio 7.

    - **StorageAccountConnectionString** : l'URI della stringa di connessione copiato dopo la creazione dell'account di archiviazione di Azure nel passaggio 3.

    - **tenantId** -l'ID tenant dell'organizzazione di Office 365 copiato dopo aver creato l'app Twitter Connector in Azure Active Directory nel passaggio 2.

    ![Aggiungere le impostazioni delle app](media/TCimage23.png)

4. In **Impostazioni generali**, fare clic **su** avanti accanto a **sempre attiva**. Fare clic su **Salva** nella parte superiore della pagina per salvare le impostazioni dell'applicazione.

   ![Attiva risorsa Web App e quindi salvala](media/TCimage24.png)

5. Il passaggio finale consiste nel caricare il codice sorgente dell'app del connettore in Azure scaricato nel passaggio 1. In un Web browser, passare a https://<AzureAppResourceName>. SCM.azurewebsites.NET/ZipDeployUi. Ad esempio, se il nome della risorsa dell'app di Azure (denominato nel passaggio 2 di questa sezione) è **twitterconnector**, si passa a https://twitterconnector.scm.azurewebsites.net/ZipDeployUi.

6. Trascinare e rilasciare il SampleConnector. zip (scaricato nel passaggio 1) in questa pagina. Dopo che i file sono stati caricati e la distribuzione ha esito positivo, la pagina avrà un aspetto simile alla schermata seguente:

   ![Trascinare e rilasciare il file SampleConnector. zip in questa pagina](media/TCimage25.png)

## <a name="step-5-create-the-twitter-app"></a>Passaggio 5: creare l'app Twitter

1. Accedere a https://developer.twitter.com, eseguire l'accesso usando le credenziali per l'account di sviluppo per l'organizzazione, quindi fare clic su **app**.

   ![Accedere a https://developer.twitter.com ed eseguire l'accesso](media/TCimage25-5.png)
2. Fare clic su **Crea un'app**.
   
   ![Vai alla pagina delle app per creare un'app](media/TCimage26.png)

3. In **Dettagli app**aggiungere informazioni sull'applicazione.

   ![Immettere informazioni sull'app](media/TCimage27.png)

4. Nel dashboard per sviluppatori di Twitter, selezionare l'app appena creata e copiare l'ID app visualizzato e salvarlo in un file di testo o in un altro percorso di archiviazione. Quindi fare clic su **Dettagli**.
   
   ![Copiare e salvare l'ID app](media/TCimage28.png)

5. Nella scheda **tasti e token** , in **tasti API consumer** copiare la chiave segreta API e salvarla in un file di testo o in un altro percorso di archiviazione. Fare quindi clic su **Crea** per generare un token di accesso e un segreto del token di accesso e copiarli in un file di testo o in un altro percorso di archiviazione.
   
   ![Copia e Salva in chiave segreta API](media/TCimage29.png)

   Fare quindi clic su **Crea** per generare un token di accesso e un segreto del token di accesso e copiarli in un file di testo o in un altro percorso di archiviazione.

6. Fare clic sulla scheda **autorizzazioni** e configurare le autorizzazioni come illustrato nella schermata seguente:

   ![Configurare le autorizzazioni](media/TCimage30.png)

7. Dopo aver salvato le impostazioni delle autorizzazioni, fare clic sulla scheda **Dettagli applicazione** e quindi fare clic su **modifica > modifica dettagli**.

   ![Modificare i dettagli dell'app](media/TCimage31.png)

8. Eseguire le attività seguenti:

   - Seleziona la casella di controllo per consentire all'app del connettore di accedere a Twitter.
   
   - Aggiungere l'URI di reindirizzamento OAuth utilizzando il formato seguente: ** \<connectorserviceuri>/views/twitteroauth**, in cui il valore di *connectorserviceuri* è l'URL del servizio app di Azure per l'organizzazione. ad esempio, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.

    ![Consenti all'app del connettore di accedere a Twitter e aggiungere l'URI di reindirizzamento OAuth](media/TCimage32.png)

L'app per sviluppatori di Twitter è ora pronta per essere utilizzata.

## <a name="step-6-configure-the-connector-web-app"></a>Passaggio 6: configurare l'applicazione Web del connettore 

1. Passare a https://\<AzureAppResourceName>. azurewebsites.NET (dove **AzureAppResourceName** è il nome della risorsa di Azure App denominata nel passaggio 4). Ad esempio, se il nome è **twitterconnector**, andare a https://twitterconnector.azurewebsites.net. La Home page dell'app è simile alla schermata seguente:

   ![Vai alla pagina delle risorse per le app di Azure](media/FBCimage41.png)

2. Fare clic su **Configura** per visualizzare una pagina di accesso.

   ![Fare clic su Configura per visualizzare la pagina di accesso](media/FBCimage42.png)

3. Nella casella ID tenant digitare o incollare l'ID tenant (ottenuto nel passaggio 2). Nella casella password digitare o incollare il APISecretKey (ottenuto nel passaggio 2), quindi fare clic su **imposta impostazioni di configurazione** per visualizzare la pagina **Dettagli di configurazione** .

   ![Accedere utilizzando l'ID tenant e la chiave segreta dell'API](media/TCimage35.png)

4. In **Dettagli di configurazione**, immettere le impostazioni di configurazione seguenti 

   - **Chiave API di Twitter** : l'ID app per l'applicazione Twitter creata al passaggio 5.
   - **Chiave segreta API di Twitter** – la chiave segreta API per l'applicazione Twitter creata al passaggio 5.
   - **Token di accesso Twitter** : il token di accesso creato nel passaggio 5.
   - **Segreto del token di accesso di Twitter** -il segreto del token di accesso creato nel passaggio 5.
   - **ID applicazione AAD** -ID applicazione per l'app Azure Active Directory creata al passaggio 2
   - **Segreto dell'applicazione AAD** : il valore del segreto di APISecretKey creato nel passaggio 4.
   - **URI dell'applicazione AAD** – URI dell'applicazione AAD ottenuto nel passaggio 2; ad esempio, `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`.
   - **Chiave di strumentazione Insights app** : lasciare vuota questa casella.

5. Fare clic su **Salva** per salvare le impostazioni del connettore.

## <a name="step-7-set-up-a-custom-connector-in-the-security-and-compliance-center"></a>Passaggio 7: configurare un connettore personalizzato nel centro sicurezza e conformità

1.  Passare a <https://protection.office.com> e quindi fare clic su **dati di terze parti sull' \> importazione \> di governance delle informazioni**.

    ![Passare alla pagina di archiviazione dei dati di terze parti nel centro sicurezza e conformità](media/TCimage36.png)

2. Fare clic su **Aggiungi connettore** e quindi su **Twitter**.

   ![Fare clic su Aggiungi connettore per aggiungere un connettore Twitter](media/TCimage37.png)

3. Nella pagina **Aggiungi applicazione del connettore** , immettere le informazioni seguenti e quindi fare clic su **convalida connettore**.

    - Nella prima casella digitare un nome per il connettore, ad esempio **Twitter**.
    - Nella seconda casella digitare o incollare il valore dell'APISecretKey aggiunto nel passaggio 4.
    - Nella terza casella digitare o incollare l'URL del servizio app di Azure; ad esempio, **https://twitterconnector.azurewebsites.net**.

   Dopo che il connettore è stato convalidato, fare clic su **Avanti**.

   ![Immettere le impostazioni delle app del connettore](media/TCimage38.png)

4. Fare clic su **login con app connettore**.

   ![Accedere all'app del connettore](media/TCimage39.png)

5. Digitare o incollare di nuovo il APISecretKey e quindi fare clic su **accedi al servizio connettore**.

   ![Chiave segreta API di tipo per accedere al servizio del connettore](media/TCimage40.png)

6. Fare clic su **continua con Twitter**.

7. Nella pagina di accesso di Twitter, accedere usando le credenziali per l'account per l'account Twitter dell'organizzazione.

   ![Accedere all'account Twitter](media/TCimage42.png)

   Dopo aver eseguito l'accesso, nella pagina Twitter verrà visualizzato il messaggio seguente: "il processo del connettore di Twitter è stato configurato correttamente".

8. Fare clic su **fine** per completare la configurazione del connettore Twitter.

9. Nella pagina **Imposta filtri** è possibile applicare un filtro per importare e archiviare gli elementi di una determinata età. Fare clic su **Avanti**.

   ![Configurare il filtro per importare elementi di una determinata età](media/TCimage44.png)

10. Nella pagina **Imposta account di archiviazione** Digitare l'indirizzo di posta elettronica di una cassetta postale di Office 365 in cui verranno importati gli elementi di Twitter.

    ![Specificare una cassetta postale di Office 365 per importare gli elementi di Twitter in](media/TCimage45.png)

11. Esaminare le impostazioni e quindi fare clic su **fine** per completare la configurazione del connettore nel centro sicurezza & conformità.

    ![Rivedere le impostazioni e quindi fare clic su fine.](media/TCimage46.png)

    ![Schermata che mostra che la configurazione del connettore è stata completata](media/TCimage47.png)

12. Passare alla pagina di **archiviazione dei dati di terze parti** per visualizzare lo stato di avanzamento del processo di importazione.

    ![Nuovo connettore visualizzato nel centro sicurezza e conformità](media/TCimage48.png)
