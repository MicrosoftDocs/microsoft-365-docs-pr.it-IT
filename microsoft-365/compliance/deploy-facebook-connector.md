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
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a>Distribuire un connettore per archiviare i dati delle pagine business di Facebook

In questo articolo sono contenute le procedure dettagliate per distribuire un connettore che utilizza il servizio di importazione di Office 365 per importare i dati dalle pagine business di Facebook a Microsoft 365. Per una panoramica generale di questo processo e un elenco dei prerequisiti necessari per distribuire un connettore di Facebook, vedere [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Passaggio 1: Creare un'app in Azure Active Directory

1. Accedere a <https://portal.azure.com> e accedere utilizzando le credenziali di un account amministratore globale.

    ![Creare app in AAD](../media/FBCimage1.png)

2. Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.

    ![Fare clic Azure Active Directory](../media/FBCimage2.png)

3. Nel riquadro di spostamento sinistro fare clic su **Registrazioni app (anteprima)** e quindi su **Nuova registrazione.**

    ![Fai clic su **Registrazioni app (Anteprima)** e quindi fai clic su **Nuova registrazione**](../media/FBCimage3.png)

4. Registrare l'applicazione. In URI di reindirizzamento seleziona Web nell'elenco a discesa tipo di applicazione e quindi digita <https://portal.azure.com> nella casella per l'URI.

   ![Registrare l'applicazione](../media/FBCimage4.png)

5. Copiare **l'ID applicazione (client)** **e l'ID directory (tenant)** e salvarli in un file di testo o in un altro percorso sicuro. Questi ID vengono utilizzati nei passaggi successivi.

   ![Copiare l'ID applicazione e l'ID directory e salvarli](../media/FBCimage5.png)

6. Vai a **Certificati & segreti per la nuova app.**

   ![Vai a Certificati & segreti per la nuova app](../media/FBCimage6.png)

7. Fare **clic su Nuovo segreto client**

   ![Fare clic su Nuovo segreto client](../media/FBCimage7.png)

8. Creare un nuovo segreto. Nella casella Descrizione digitare il segreto e quindi scegliere un periodo di scadenza.

    ![Digitare il segreto e quindi scegliere un periodo di scadenza](../media/FBCimage8.png)

9. Copiare il valore del segreto e salvarlo in un file di testo o in un altro percorso di archiviazione. Si tratta del segreto dell'applicazione AAD utilizzato nei passaggi successivi.

   ![Copiare il valore del segreto e salvarlo](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Passaggio 2: Distribuire il servizio Web del connettore da GitHub all'account Azure

1. Accedere a [questo sito GitHub e](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) fare clic su **Distribuisci in Azure**.

    ![Fare clic su Distribuisci in Azure](../media/FBCGithubApp.png)

2. Dopo aver fatto **clic su Distribuisci in Azure,** si verrà reindirizzati a un portale di Azure con una pagina modello personalizzata. Compila i dettagli **di** base e **Impostazioni** e quindi fai clic su **Acquista.**

   - **Sottoscrizione:** Selezionare la sottoscrizione di Azure in cui si desidera distribuire il servizio Web del connettore pagine business di Facebook.

   - **Gruppo di risorse:** Scegliere o creare un nuovo gruppo di risorse. Un gruppo di risorse è un contenitore che contiene le risorse correlate per una soluzione di Azure.

   - **Posizione:** Scegliere una posizione.

   - **Nome app Web:** Specificare un nome univoco per l'app Web del connettore. Il nome deve avere una lunghezza compresa tra 3 e 18 caratteri. Questo nome viene usato per creare l'URL del servizio app di Azure. Ad esempio, se fornisci il nome dell'app Web **fbconnector,** l'URL del servizio app di Azure sarà **fbconnector.azurewebsites.net**.

   - **tenantId:** ID tenant dell'organizzazione Microsoft 365 che hai copiato dopo aver creato l'app del connettore di Facebook in Azure Active Directory nel passaggio 1.

   - **APISecretKey:** È possibile digitare qualsiasi valore come segreto. Viene usato per accedere all'app Web del connettore nel passaggio 5.

     ![Fare clic su Crea una risorsa e digitare l'account di archiviazione](../media/FBCimage12.png)

3. Una volta completata la distribuzione, la pagina avrà un aspetto simile allo screenshot seguente:

   ![Fare Archiviazione e quindi fare clic su Archiviazione account](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a>Passaggio 3: registrare l'app Facebook

1. Vai a , accedi usando le credenziali per l'account per le pagine Facebook Business dell'organizzazione e quindi fai <https://developers.facebook.com> clic su Aggiungi nuova **app.**

   ![Aggiungere una nuova app per la pagina aziendale di Facebook](../media/FBCimage25.png)

2. Crea un nuovo ID app.

   ![Creare un nuovo ID app](../media/FBCimage26.png)

3. Nel riquadro di spostamento sinistro fai clic **su Aggiungi prodotti** e quindi fai clic su **Configura** nel riquadro Accesso **a Facebook.**

   ![Fare clic su Aggiungi prodotti](../media/FBCimage27.png)

4. Nella pagina Integrare l'accesso a Facebook fare clic su **Web.**

   ![Fare clic su Web nella pagina Integra account di accesso di Facebook](../media/FBCimage28.png)

5. Aggiungere l'URL del servizio app di Azure; ad esempio `https://fbconnector.azurewebsites.net` .

   ![Aggiungere l'URL del servizio app di Azure](../media/FBCimage29.png)

6. Completa la sezione QuickStart della configurazione dell'accesso a Facebook.

   ![Completare la sezione Guida introduttiva](../media/FBCimage30.png)

7. Nel riquadro di spostamento sinistro in **Accesso a Facebook,** fare clic su **Impostazioni** e aggiungere l'URI di reindirizzamento OAuth nella casella URI di reindirizzamento **OAuth** validi. Utilizzare il formato **\<connectorserviceuri> /Views/FacebookOAuth**, dove il valore per connectorserviceuri è l'URL del servizio app di Azure per l'organizzazione, ad esempio `https://fbconnector.azurewebsites.net` .

   ![Aggiungere l'URI di reindirizzamento OAuth alla casella URI di reindirizzamento OAuth validi](../media/FBCimage31.png)

8. Nel riquadro di spostamento sinistro fare clic **su Aggiungi prodotti** e quindi su **Webhook.** Nel menu **a** discesa Pagina fare clic su **Pagina.**

   ![Fare clic su Aggiungi prodotti e quindi su **Webhook](../media/FBCimage32.png)

9. Aggiungere l'URL di richiamata webhook e aggiungere un token di verifica. Il formato dell'URL di richiamata, utilizzare il formato **<connectorserviceuri> /api/FbPageWebhook**, dove il valore per connectorserviceuri è l'URL del servizio app azure per l'organizzazione, ad esempio `https://fbconnector.azurewebsites.net` .

   Il token di verifica deve essere simile a una password complessa. Copiare il token di verifica in un file di testo o in un altro percorso di archiviazione.

   ![Aggiungere il token di verifica](../media/FBCimage33.png)

10. Testare e sottoscrivere l'endpoint per il feed.

    ![Testare e sottoscrivere l'endpoint](../media/FBCimage34.png)

11. Aggiungi un URL di privacy, un'icona dell'app e l'uso aziendale. Copia inoltre l'ID dell'app e il segreto dell'app in un file di testo o in un altro percorso di archiviazione.

    ![Aggiungere un URL di privacy, un'icona dell'app e un uso aziendale](../media/FBCimage35.png)

12. Rendi pubblica l'app.

    ![Rendere pubblica l'app](../media/FBCimage36.png)

13. Aggiungere un utente al ruolo di amministratore o tester.

    ![Aggiungere un utente al ruolo di amministratore o tester](../media/FBCimage37.png)

14. Aggiungere **l'autorizzazione Accesso contenuto pubblico pagina.**

    ![dd l'autorizzazione di accesso al contenuto pubblico della pagina](../media/FBCimage38.png)

15. Aggiungere l'autorizzazione Gestione pagine.

    ![Aggiunta dell'autorizzazione Gestione pagine](../media/FBCimage39.png)

16. Ottenere l'applicazione esaminata da Facebook.

    ![Ottenere l'applicazione esaminata da Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a>Passaggio 4: Configurare l'app Web del connettore

1. Passare a (dove AzureAppResourceName è il nome della risorsa app di Azure denominata `https://<AzureAppResourceName>.azurewebsites.net` nel passaggio 4). Ad esempio, se il nome è **fbconnector**, passare a `https://fbconnector.azurewebsites.net` . La home page dell'app sarà simile alla schermata seguente:

   ![Vai all'app Web connettore](../media/FBCimage41.png)

2. Fare **clic su** Configura per visualizzare una pagina di accesso.

   ![Fare clic su Configura per visualizzare una pagina di accesso](../media/FBCimage42.png)

3. Nella casella ID tenant digitare o incollare l'ID tenant ottenuto nel passaggio 2. Nella casella password digitare o **incollare** APISecretKey (ottenuto nel passaggio 2), quindi fare clic su Imposta configurazione Impostazioni per visualizzare la pagina dei dettagli della configurazione.

    ![Accedi usando l'ID tenant e la password e passa alla pagina dei dettagli della configurazione](../media/FBCimage43.png)

4. Immettere le impostazioni di configurazione seguenti

   - **ID applicazione Facebook:** ID dell'app per l'applicazione Facebook ottenuta nel passaggio 3.

   - **Segreto dell'applicazione Facebook:** Segreto dell'app per l'applicazione Facebook ottenuta nel passaggio 3.

   - **I webhook di Facebook verificano il token:** Token di verifica creato nel passaggio 3.

   - **ID applicazione AAD:** ID dell'applicazione Azure Active Directory'app creata nel passaggio 1.

   - **Segreto applicazione AAD:** Valore per il segreto APISecretKey creato nel passaggio 1.

5. Fare **clic su** Salva per salvare le impostazioni del connettore.

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a>Passaggio 5: Configurare un connettore di Facebook nel Centro Microsoft 365 conformità

1. Vai a [https://compliance.microsoft.com](https://compliance.microsoft.com) e quindi fai clic su **Connettori dati** nel riquadro di spostamento sinistro.

2. Nella pagina **Connettori dati in** Pagine **aziendali di Facebook** fare clic su **Visualizza.**

3. Nella pagina **Pagine aziendali di Facebook** fare clic su Aggiungi **connettore.**

4. Nella pagina **Condizioni di servizio** fare clic su **Accetta.**

5. Nella pagina **Aggiungi credenziali per l'app connettore** immettere le informazioni seguenti e quindi fare clic su **Convalida connessione.**

   ![Immettere le credenziali dell'app connettore](../media/TCimage38.png)

   - Nella casella **Nome** digitare un nome per il connettore, ad esempio **Pagina notizie di Facebook.**

   - Nella casella **URL connessione** digitare o incollare l'URL del servizio app di Azure. ad esempio `https://fbconnector.azurewebsites.net` .

   - Nella casella **Password** digitare o incollare il valore dell'APISecretKey aggiunto nel passaggio 2.

   - Nella casella **ID app azure** digitare o incollare il valore dell'ID applicazione (client) chiamato anche come ID applicazione AAD creato nel passaggio 1.

6. Dopo aver convalidato correttamente la connessione, fare clic su **Avanti.**

7. Nella pagina **Autorizza Microsoft 365 importare** dati digitare o incollare di nuovo APISecretKey e quindi fare clic su **Accedi all'app Web.**

8. Nella pagina **Configura l'app del connettore di Facebook** fare clic su Accedi con **Facebook** ed eseguire l'accesso utilizzando le credenziali per l'account per le pagine Facebook Business dell'organizzazione. Assicurati che all'account Facebook a cui hai effettuato l'accesso sia assegnato il ruolo di amministratore per le pagine Facebook Business dell'organizzazione.

   ![Accedere con Facebook](../media/FBCimage50.png)

9. Viene visualizzato un elenco delle pagine business gestite dall'account Facebook a cui hai effettuato l'accesso. Selezionare la pagina da archiviare e quindi fare clic su **Avanti.**

   ![Selezionare la pagina aziendale dell'organizzazione che si desidera archiviare](../media/FBCimage52.png)

10. Fare **clic su** Continua per uscire dall'installazione dell'app del servizio connettore.

11. Nella pagina **Imposta filtri** è possibile applicare un filtro per importare inizialmente elementi di una determinata età. Selezionare un'età e quindi fare clic su **Avanti.**

12. Nella pagina **Scegli percorso di archiviazione** digitare l'indirizzo di Microsoft 365 di posta elettronica in cui verranno importati gli elementi di Facebook e quindi fare clic su **Avanti.**

13. Fare **clic su** Avanti per esaminare le impostazioni del connettore e quindi fare clic su **Fine** per completare la configurazione del connettore.

14. Nel Centro conformità passare alla pagina **Connettori** di dati e fare clic sulla scheda **Connettori** per visualizzare l'avanzamento del processo di importazione.
