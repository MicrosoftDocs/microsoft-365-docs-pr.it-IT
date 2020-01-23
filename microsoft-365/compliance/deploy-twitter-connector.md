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
# <a name="deploy-a-connector-to-archive-twitter-data"></a>Distribuire un connettore per archiviare i dati di Twitter

Questo articolo contiene il processo dettagliato per la distribuzione di un connettore che utilizza il servizio di importazione di Office 365 per importare i dati dall'account Twitter dell'organizzazione a Microsoft 365. Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore Twitter, vedere [configurare un connettore per archiviare i dati di Twitter ](archive-twitter-data-with-sample-connector.md). 

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Passaggio 1: creare un'app in Azure Active Directory

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

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Passaggio 2: distribuire il servizio Web del connettore da GitHub all'account di Azure

1. Accedere a [questo sito GitHub](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) e fare clic su **Distribuisci in Azure**.

    ![Passare alla Home page di Azure](media/FBCimage11.png)

2. Dopo aver fatto clic su **Distribuisci in Azure**, verrà reindirizzato a un portale di Azure con una pagina modello personalizzato. Compilare i dettagli delle **Impostazioni e delle** informazioni di **base** e quindi fare clic su **acquisto**.

   ![Fare clic su Crea un account di archiviazione di risorse e tipi](media/FBCimage12.png)

    - **Sottoscrizione:** Selezionare l'abbonamento di Azure in cui si desidera distribuire il servizio Web del connettore Twitter.
    
    - **Gruppo di risorse:** Scegliere o creare un nuovo gruppo di risorse. Un gruppo di risorse è un contenitore che contiene risorse correlate per una soluzione di Azure.

    - **Posizione:** Scegliere un percorso.

    - **Nome applicazione Web:** Specificare un nome univoco per il connettore Web App. Il nome del Th deve essere compreso tra 3 e 18 caratteri. Questo nome viene utilizzato per creare l'URL del servizio app di Azure. ad esempio, se si specifica il nome dell'applicazione Web di **twitterconnector** , l'URL del servizio app di Azure sarà **twitterconnector.azurewebsites.NET**.
    
    - **tenantId:** L'ID tenant dell'organizzazione Microsoft 365 copiato dopo aver creato l'app connettore Facebook in Azure Active Directory nel passaggio 1.
    
   - **APISecretKey:** È possibile digitare qualsiasi valore come segreto. Viene utilizzato per accedere all'applicazione Web del connettore nel passaggio 5.

3. Dopo che la distribuzione ha avuto esito positivo, la pagina avrà un aspetto simile alla schermata seguente:

    ![Fare clic su archiviazione e quindi su account di archiviazione](media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a>Passaggio 3: creare l'app Twitter

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

## <a name="step-4-configure-the-connector-web-app"></a>Passaggio 4: configurare l'applicazione Web del connettore 

1. Passare a https://\<AzureAppResourceName>. azurewebsites.NET (dove **AzureAppResourceName** è il nome della risorsa di Azure App denominata nel passaggio 4). Ad esempio, se il nome è **twitterconnector**, andare a https://twitterconnector.azurewebsites.net. La Home page dell'app è simile alla schermata seguente:

   ![Vai alla pagina delle risorse per le app di Azure](media/FBCimage41.png)

2. Fare clic su **Configura** per visualizzare una pagina di accesso.

   ![Fare clic su Configura per visualizzare la pagina di accesso](media/FBCimage42.png)

3. Nella casella ID tenant digitare o incollare l'ID tenant (ottenuto nel passaggio 2). Nella casella password digitare o incollare il APISecretKey (ottenuto nel passaggio 2), quindi fare clic su **imposta impostazioni di configurazione** per visualizzare la pagina dettagli di configurazione.

   ![Accedere utilizzando l'ID tenant e la chiave segreta dell'API](media/TCimage35.png)

4. Immettere le impostazioni di configurazione seguenti 

   - **Chiave API di Twitter:** ID app per l'applicazione Twitter creata al passaggio 3.
   
   - **Chiave segreta API Twitter:** La chiave segreta API per l'applicazione Twitter creata al passaggio 3.
   
   - **Token di accesso Twitter:** Il token di accesso creato nel passaggio 3.
   
   - **Segreto del token di accesso di Twitter:** Il segreto del token di accesso creato nel passaggio 3.
   
   - **ID applicazione AAD:** ID applicazione per l'app Azure Active Directory creata al passaggio 1
   
   - **Segreto dell'applicazione AAD:** Il valore del segreto di APISecretKey creato nel passaggio 1.

5. Fare clic su **Salva** per salvare le impostazioni del connettore.

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Passaggio 5: configurare un connettore Twitter nel centro conformità di Microsoft 365

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fare clic su **connettori dati** nel NAV sinistro.

2. Nella pagina **connettori dati (anteprima)** in **Twitter**, fare clic su **Visualizza**.

3. Nella pagina **Twitter** , fare clic su **Aggiungi connettore**.

4. Nella pagina **condizioni del servizio** fare clic su **Accetto**.

5. Nella pagina **Aggiungi credenziali per l'app del connettore** , immettere le informazioni seguenti e quindi fare clic su **convalida connessione**.

   ![Immettere le credenziali delle app del connettore](media/TCimage38.png)

    - Nella casella **nome** Digitare un nome per il connettore, ad esempio la **maniglia della Guida di Twitter**.
    
    - Nella casella **URL connettore** Digitare o incollare l'URL del servizio app di Azure; ad esempio `https://twitterconnector.azurewebsites.net`.
    
    - Nella casella **password** Digitare o incollare il valore del APISecretKey creato nel passaggio 2.
    
    - Nella casella **ID app di Azure** Digitare o incollare il valore dell'ID applicazione app di Azure (denominato anche *ID client*) ottenuto nel passaggio 1.

6. Dopo aver convalidato correttamente la connessione, fare clic su **Avanti**.

7. Nella pagina **autorizza Microsoft 365 per importare i dati** , digitare o incollare di nuovo APISecretKey e quindi fare clic su **login Web App**.

8. Fare clic su **login con Twitter**.

9. Nella pagina di accesso di Twitter, accedere usando le credenziali per l'account Twitter dell'organizzazione.

   ![Accedere all'account Twitter](media/TCimage42.png)

   Dopo aver eseguito l'accesso, nella pagina Twitter verrà visualizzato il messaggio seguente: "il processo del connettore di Twitter è stato configurato correttamente".

10. Fare clic su **continua** per completare la configurazione del connettore Twitter.

11. Nella pagina **Imposta filtri** è possibile applicare un filtro per importare inizialmente gli elementi di una determinata età. Selezionare un'età, quindi fare clic su **Avanti**.

12. Nella pagina **Scegli percorso di archiviazione** Digitare l'indirizzo di posta elettronica della cassetta postale di Microsoft 365 in cui verranno importati gli elementi di Twitter e quindi fare clic su **Avanti**.

13. Sul **consenso amministratore**, fare clic su **Fornisci consenso** e quindi eseguire la procedura. È necessario essere un amministratore globale per fornire il consenso per il servizio di importazione di Office 365 per accedere ai dati nell'organizzazione.

14. Fare clic su **Avanti** per esaminare le impostazioni del connettore e quindi fare clic su **fine** per completare la configurazione del connettore.

15. Nel centro conformità, andare alla pagina **connettori dati** e fare clic sulla scheda **connettori** per visualizzare lo stato di avanzamento del processo di importazione.
