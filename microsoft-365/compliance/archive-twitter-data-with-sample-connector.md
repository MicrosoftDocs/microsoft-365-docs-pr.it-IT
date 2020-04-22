---
title: Configurare un connettore per archiviare i dati di Twitter
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
description: Gli amministratori possono configurare un connettore nativo per importare i dati di Twitter in Microsoft 365. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Microsoft 365 per poter utilizzare le funzionalità di conformità, ad esempio la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire la governance dei dati di terze parti dell'organizzazione.
ms.openlocfilehash: 866bd61c40aa998bcb612ee1d82f8275f075bb8e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630613"
---
# <a name="set-up-a-connector-to-archive-twitter-data"></a>Configurare un connettore per archiviare i dati di Twitter

Utilizzare un connettore nel centro conformità di Microsoft 365 per importare e archiviare i dati da Twitter a Microsoft 365. Dopo aver configurato e configurato il connettore, l'utente si connette all'account Twitter dell'organizzazione (su base pianificata), converte il contenuto di un elemento in un formato di messaggio di posta elettronica e quindi importa tali elementi in una cassetta postale in Microsoft 365.

Dopo aver importato i dati di Twitter, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, la ricerca di contenuto, l'archiviazione sul posto, il controllo e i criteri di conservazione di Microsoft 365 ai dati di Twitter. Ad esempio, quando una cassetta postale viene inserita in un blocco per controversia legale o assegnata a un criterio di conservazione, vengono conservati i dati di Twitter. È possibile eseguire la ricerca di dati di terze parti utilizzando la ricerca contenuto o associare la cassetta postale in cui vengono archiviati i dati di Twitter con un custode in un caso avanzato di eDiscovery. L'utilizzo di un connettore per l'importazione e l'archiviazione dei dati di Twitter in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

Dopo aver importato i dati di Twitter, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, la ricerca di contenuto, l'archiviazione sul posto, il controllo, la conformità alla comunicazione e i criteri di conservazione di Microsoft 365 ai dati archiviati nella cassetta postale. Ad esempio, è possibile cercare i dati di Twitter utilizzando la ricerca contenuto o associare la cassetta postale in cui vengono archiviati i dati con un custode in un caso di eDiscovery avanzato. L'utilizzo di un connettore per l'importazione e l'archiviazione dei dati di Twitter in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a>Prerequisiti per la configurazione di un connettore per Twitter

Completare i prerequisiti seguenti prima di poter impostare e configurare un connettore nel centro conformità di Microsoft 365 per importare e archiviare i dati dall'account Twitter dell'organizzazione.

- Per l'organizzazione è necessario un account Twitter. Quando si configura il connettore, è necessario accedere a questo account.

- L'organizzazione deve disporre di una sottoscrizione di Azure valida. Se non si dispone di una sottoscrizione di Azure esistente, è possibile iscriversi a una di queste opzioni:

    - [Iscriversi per un abbonamento gratuito a un anno di Azure](https://azure.microsoft.com/free) 

    - [Iscriversi a una sottoscrizione di Azure pay-as-you-go](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La [sottoscrizione gratuita di Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) inclusa nell'abbonamento a Microsoft 365 non supporta i connettori nel centro sicurezza & conformità.

- L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale e quindi accettare la richiesta.

- Gli utenti che configurano il connettore Twitter nel centro conformità di Microsoft 365 (al passaggio 5) devono essere assegnati al ruolo import export delle cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Passaggio 1: creare un'app in Azure Active Directory

Il primo passaggio consiste nel registrare una nuova app in Azure Active Directory (AAD). Questa applicazione corrisponde alla risorsa Web App implementata nel passaggio 2 per il connettore Twitter.

Per istruzioni dettagliate, vedere [creare un'app in Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), le informazioni seguenti vengono salvate in un file di testo. Questi valori verranno utilizzati nei passaggi successivi del processo di distribuzione.

- ID applicazione AAD

- Segreto dell'applicazione AAD

- ID tenant

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Passaggio 2: distribuire il servizio Web del connettore dall'archivio GitHub all'account di Azure

Il passaggio successivo consiste nel distribuire il codice sorgente per l'app del connettore Twitter che utilizzerà l'API di Twitter per connettersi al proprio account Twitter ed estrarre i dati in modo da poterli importare in Microsoft 365. Il connettore Twitter distribuito per l'organizzazione caricherà gli elementi dall'account Twitter dell'organizzazione nel percorso di archiviazione di Azure creato in questo passaggio. Dopo aver creato un connettore Twitter nel centro conformità di Microsoft 365 (al passaggio 5), il servizio di importazione di Office 365 copierà i dati di Twitter dal percorso di archiviazione di Azure a una cassetta postale in Microsoft 365. Come illustrato in precedenza nella sezione [Prerequisites](#prerequisites-for-setting-up-a-connector-for-twitter) , è necessario disporre di una sottoscrizione di Azure valida per creare un account di archiviazione di Azure.

Per distribuire il codice sorgente per l'app del connettore Twitter:

1. Accedere a [questo sito GitHub](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).

2. Fare clic su **Distribuisci in Azure**.

Per istruzioni dettagliate, vedere [deploy the Connector Web Service from GitHub to your Azure account](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

Se si seguono le istruzioni dettagliate per completare questo passaggio, vengono fornite le informazioni seguenti:

- APISecretKey: questo segreto è stato creato durante il completamento di questo passaggio. Viene utilizzato nel passaggio 5.

- tenantId: l'ID tenant dell'organizzazione Microsoft 365 copiato dopo aver creato l'app Twitter in Azure Active Directory nel passaggio 1.

Dopo aver completato questo passaggio, assicurarsi di copiare l'URL del servizio app (ad esempio `https://twitterconnector.azurewebsites.net`,). Per completare il passaggio 3, il passaggio 4 e il passaggio 5, è necessario utilizzare questo URL.

## <a name="step-3-create-developer-app-on-twitter"></a>Passaggio 3: creare un'app per sviluppatori su Twitter

Il passaggio successivo consiste nel creare e configurare un'app per sviluppatori su Twitter. Il connettore personalizzato creato nel passaggio 7 utilizza l'app Twitter per interagire con l'API di Twitter per ottenere i dati dall'account Twitter dell'organizzazione.

Per istruzioni dettagliate, vedere [creare l'app Twitter](deploy-twitter-connector.md#step-3-create-the-twitter-app).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), salvare le informazioni seguenti in un file di testo. Questi valori verranno utilizzati per configurare l'app del connettore Twitter nel passaggio 4.

- Chiave API di Twitter

- Chiave segreta API di Twitter

- Token di accesso Twitter

- Segreto del token di accesso di Twitter

## <a name="step-4-configure-the-twitter-connector-app"></a>Passaggio 4: configurare l'app del connettore Twitter

Il passaggio successivo consiste nell'aggiungere le impostazioni di configurazione all'app del connettore Twitter distribuita nel passaggio 2. A tale scopo, passare alla Home page dell'app del connettore e configurarla.

Per istruzioni dettagliate, vedere [Configure the Connector Web App](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), vengono fornite le informazioni seguenti (che sono state copiate in un file di testo dopo aver completato i passaggi precedenti):

- Chiave API di Twitter (ottenuto nel passaggio 3)

- Chiave segreta API di Twitter (ottenuto nel passaggio 3)

- Token di accesso Twitter (ottenuto nel passaggio 3)

- Segreto del token di accesso di Twitter (ottenuto nel passaggio 3)

- ID applicazione di Azure Active Directory (ID applicazione AAD ottenuto nel passaggio 1)

- Segreto dell'applicazione di Azure Active Directory (segreto dell'applicazione AAD ottenuto nel passaggio 1)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Passaggio 5: configurare un connettore Twitter nel centro conformità di Microsoft 365

Il passaggio finale consiste nel configurare il connettore Twitter nel centro conformità di Microsoft 365 che importerà i dati dall'account Twitter dell'organizzazione a una cassetta postale specificata in Microsoft 365. Dopo aver completato questo passaggio, il servizio di importazione di Office 365 inizierà a importare i dati dall'account Twitter dell'organizzazione a Microsoft 365.

Per istruzioni dettagliate, vedere [configurare un connettore Twitter nel centro conformità di Microsoft 365](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center). 

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), vengono fornite le informazioni seguenti (che sono state copiate in un file di testo dopo aver completato la procedura).

- URL del servizio app di Azure (ottenuto nel passaggio 2, ad `https://twitterconnector.azurewebsites.net`esempio,)

- APISecretKey (creato nel passaggio 2)
