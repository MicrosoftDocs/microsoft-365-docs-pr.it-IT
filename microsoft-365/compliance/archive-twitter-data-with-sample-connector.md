---
title: Utilizzare un connettore di esempio per archiviare i dati di Twitter (anteprima)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Gli amministratori possono configurare un connettore nativo per importare i dati di Twitter in Office 365. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Office 365 per poter utilizzare le funzionalità di conformità, ad esempio i criteri di conservazione legale, ricerca contenuto e mantenimento, per gestire la governance dei dati di terze parti dell'organizzazione.
ms.openlocfilehash: 77f0a0615a177c0bfd6179a6a5ce1a58b024dcdc
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807485"
---
# <a name="use-a-sample-connector-to-archive-twitter-data-preview"></a>Utilizzare un connettore di esempio per archiviare i dati di Twitter (anteprima)

La funzionalità di esempio del connettore per l'archiviazione dei dati di Twitter in Office 365 è in anteprima.

Utilizzare un connettore di esempio nel centro sicurezza & compliance in Office 365 per importare e archiviare i dati da Twitter. Dopo aver configurato e configurato un connettore di esempio, l'utente si connette all'account Twitter dell'organizzazione (su base pianificata), converte il contenuto di un elemento in un formato di messaggio di posta elettronica e quindi importa tali elementi in una cassetta postale in Office 365.

Dopo aver importato i dati di Twitter, è possibile applicare le funzionalità di conformità di Office 365, ad esempio il blocco per controversia legale, la ricerca di contenuto, l'archiviazione sul posto, il controllo, la [conformità alla comunicazione](communication-compliance.md)e i criteri di conservazione di Office 365 ai dati archiviati nella cassetta postale. Ad esempio, è possibile cercare i dati di Twitter utilizzando la ricerca contenuto o associare la cassetta postale in cui vengono archiviati i dati con un custode in un caso di eDiscovery avanzato. L'utilizzo di un connettore di esempio per l'importazione e l'archiviazione dei dati di Twitter in Office 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

> [!NOTE]
> Attualmente, solo i connettori di esempio per le [pagine business](archive-facebook-data-with-sample-connector.md) di Twitter e Facebook sono disponibili per l'anteprima. Sono disponibili più connettori di esempio.


## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a>Prerequisiti per la configurazione di un connettore per Twitter

Completare i prerequisiti seguenti prima di poter impostare e configurare un connettore di esempio nel centro sicurezza & Compliance per importare e archiviare i dati dall'account Twitter dell'organizzazione. 

- Per l'organizzazione è necessario un account Twitter. Quando si configura il connettore, è necessario accedere a questo account.

- L'organizzazione deve disporre di una sottoscrizione di Azure valida. Se non si dispone di una sottoscrizione di Azure esistente, è possibile iscriversi a una di queste opzioni:

    - [Iscriversi per un abbonamento gratuito a un anno di Azure](https://azure.microsoft.com/free) 

    - [Iscriversi a una sottoscrizione di Azure pay-as-you-go](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La [sottoscrizione gratuita di Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) inclusa nell'abbonamento a Office 365 non supporta i connettori di esempio nel centro sicurezza & conformità.

- L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale di Office 365 e quindi accettare la richiesta.

- All'utente che configura il connettore personalizzato nella sicurezza & conformità (al passaggio 7) deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un nuovo gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a>Passaggio 1: scaricare il pacchetto di app del connettore precompilato da GitHub

Il primo passaggio consiste nel scaricare il codice sorgente per l'app del connettore di esempio Twitter che utilizzerà un'API di Twitter per connettersi al proprio account Twitter ed estrarre i dati in modo da poterli importare in Office 365.

1. Accedere a [questo sito GitHub](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet/releases). 
2. Nella versione più recente, selezionare il file **SampleConnector. zip** .
3. Salvare il file ZIP in un percorso del computer locale. È possibile caricare il file zip in Azure nel passaggio 4.

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Passaggio 2: creare un'app in Azure Active Directory

Il passaggio successivo consiste nel registrare una nuova app in Azure Active Directory (AAD). Questa applicazione corrisponde alla risorsa Web App implementata nel passaggio 4 per il connettore Twitter. 

Per istruzioni dettagliate, vedere [passaggio 2: creare un'app in Azure Active Directory](deploy-twitter-connector.md#step-2-create-an-app-in-azure-active-directory).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), le informazioni seguenti vengono salvate in un file di testo. Questi valori verranno utilizzati nei passaggi successivi del processo di distribuzione.

- ID applicazione AAD
- Segreto dell'applicazione AAD
- URI dell'applicazione AAD
- ID tenant

## <a name="step-3-create-an-azure-storage-account"></a>Passaggio 3: creare un account di archiviazione di Azure

Il connettore Twitter distribuito per l'organizzazione carica gli elementi da Twitter nel percorso di archiviazione di Azure creato in questo passaggio. Dopo aver creato un connettore personalizzato nel centro sicurezza & Compliance (al passaggio 7), il servizio di importazione di Office 365 copierà i dati di Twitter dal percorso di archiviazione di Azure a una cassetta postale in Office 365. Come illustrato in precedenza nella sezione [Prerequisites](#prerequisites-for-setting-up-a-connector-for-twitter) , è necessario disporre di una sottoscrizione di Azure valida per creare un account di archiviazione di Azure.

Per istruzioni dettagliate, vedere [passaggio 3: creare un account di archiviazione di Azure](deploy-twitter-connector.md#step-3-create-an-azure-storage-account).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), è possibile salvare l'URI della stringa di connessione generato. Questa stringa viene utilizzata quando si crea una risorsa Web App in Azure nel passaggio 4.

## <a name="step-4-create-a-web-app-resource-in-azure"></a>Passaggio 4: creare una risorsa Web App in Azure

Il passaggio successivo consiste nel creare una risorsa Web App in Azure per il connettore Twitter. 

Per istruzioni dettagliate, vedere [passaggio 4: creare una nuova risorsa Web App in Azure](deploy-twitter-connector.md#step-4-create-a-new-web-app-resource-in-azure).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), vengono fornite le informazioni seguenti, che sono state copiate in un file di testo dopo aver completato i passaggi precedenti, durante la creazione della risorsa Web App.

- APISecretKey – è possibile creare questo segreto durante il completamento di questo passaggio; viene utilizzato nel passaggio 7.
- StorageAccountConnectionString: l'URI della stringa di connessione copiato dopo la creazione dell'account di archiviazione di Azure nel passaggio 3.
- tenantId-l'ID tenant dell'organizzazione di Office 365 copiato dopo aver creato l'app Twitter Connector in Azure Active Directory nel passaggio 2.

Inoltre, è possibile caricare il file SampleConnector. zip (scaricato nel passaggio 1) in questo passaggio per distribuire il codice sorgente per l'app del connettore Twitter.

Dopo aver completato questo passaggio, assicurarsi di copiare l'URL del servizio app di Azure (ad `https://twitterconnector.azurewebsites.net`esempio,). È necessario utilizzare questo URL per completare il passaggio 5, il passaggio 6 e il passaggio 7.

## <a name="step-5-create-developer-app-on-twitter"></a>Passaggio 5: creare un'app per sviluppatori su Twitter

Il passaggio successivo consiste nel creare e configurare un'app per sviluppatori su Twitter. Il connettore personalizzato creato nel passaggio 7 utilizza l'app Twitter per interagire con l'API di Twitter per ottenere i dati dall'account Twitter dell'organizzazione.

Per istruzioni dettagliate, vedere [passaggio 5: creare l'app Twitter](deploy-twitter-connector.md#step-5-create-the-twitter-app).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), salvare le informazioni seguenti in un file di testo. Questi valori verranno utilizzati per configurare l'app del connettore Twitter nel passaggio 6.

- Chiave API di Twitter
- Chiave segreta API di Twitter
- Token di accesso Twitter
- Segreto del token di accesso di Twitter

## <a name="step-6-configure-the-twitter-connector-app"></a>Passaggio 6: configurare l'app del connettore Twitter

Il passaggio successivo consiste nell'aggiungere le impostazioni di configurazione all'app del connettore Twitter che è stata caricata quando è stata creata la risorsa Azure Web App nel passaggio 4. A tale scopo, passare alla Home page dell'app del connettore e configurarla.

Per istruzioni dettagliate, vedere [passaggio 6: Configure the Connector Web App](deploy-twitter-connector.md#step-6-configure-the-connector-web-app).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), vengono fornite le informazioni seguenti (che sono state copiate in un file di testo dopo aver completato i passaggi precedenti):

- Chiave API di Twitter (ottenuto nel passaggio 5)
- Chiave segreta API di Twitter (ottenuta nel passaggio 5)
- Token di accesso Twitter (ottenuto nel passaggio 5)
- Segreto del token di accesso di Twitter (ottenuto nel passaggio 5)
- ID applicazione di Azure Active Directory (ID applicazione AAD ottenuto nel passaggio 2)
- Segreto dell'applicazione di Azure Active Directory (segreto dell'applicazione AAD ottenuto nel passaggio 2)
- URI dell'applicazione di Azure Active Directory (l'URI dell'applicazione AAD ottenuto nel passaggio 2, ad esempio,`https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)`

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>Passaggio 7: configurare un connettore personalizzato nel centro sicurezza & Compliance

Il passaggio finale consiste nel configurare il connettore personalizzato nel centro sicurezza & Compliance che importa i dati dall'account Twitter dell'organizzazione a una cassetta postale specificata in Office 365. Dopo aver completato questo passaggio, il servizio di importazione di Office 365 inizierà a importare i dati da Twitter a Office 365. 

Per istruzioni dettagliate, vedere [passaggio 7: configurare un connettore personalizzato nel centro sicurezza e conformità](deploy-twitter-connector.md#step-7-set-up-a-custom-connector-in-the-security-and-compliance-center). 

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), vengono fornite le informazioni seguenti (che sono state copiate in un file di testo dopo aver completato la procedura).

- URL del servizio app di Azure (ottenuto nel passaggio 4, ad `https://twitterconnector.azurewebsites.net`esempio,)
- APISecretKey (creato nel passaggio 4)
