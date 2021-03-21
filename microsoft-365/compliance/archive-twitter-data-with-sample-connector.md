---
title: Configurare un connettore per archiviare i dati di Twitter
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Informazioni su come gli amministratori possono configurare e usare un connettore nativo per importare i dati di Twitter in Microsoft 365.
ms.openlocfilehash: 277af8ea7367936c4c9528a8ca50ccd678745bf6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922258"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>Configurare un connettore per archiviare i dati di Twitter (anteprima)

Usare un connettore nel Centro conformità Microsoft 365 per importare e archiviare i dati da Twitter a Microsoft 365. Dopo aver configurato e configurato il connettore, si connette all'account Twitter dell'organizzazione (su base pianificata), converte il contenuto di un elemento in un formato di messaggio di posta elettronica e quindi importa tali elementi in una cassetta postale in Microsoft 365.

Dopo l'importazione dei dati di Twitter, è possibile applicare ai dati di Twitter le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, Ricerca contenuto, archiviazione In-Place, controllo e criteri di conservazione di Microsoft 365. Ad esempio, quando una cassetta postale viene messa in conservazione per controversia legale o assegnata a un criterio di conservazione, i dati di Twitter vengono mantenuti. È possibile cercare dati di terze parti utilizzando Ricerca contenuto o associare la cassetta postale in cui i dati di Twitter sono archiviati a un responsabile in un caso di Advanced eDiscovery. L'utilizzo di un connettore per importare e archiviare i dati di Twitter in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

Dopo l'importazione dei dati di Twitter, è possibile applicare ai dati archiviati nella cassetta postale le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, ricerca contenuto, archiviazione In-Place, controllo, conformità delle comunicazioni e criteri di conservazione di Microsoft 365. Ad esempio, è possibile cercare i dati di Twitter utilizzando Ricerca contenuto o associare la cassetta postale in cui i dati sono archiviati a un responsabile in un caso advanced eDiscovery. L'utilizzo di un connettore per importare e archiviare i dati di Twitter in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="before-you-set-up-a-connector"></a>Prima di configurare un connettore

Completare i prerequisiti seguenti prima di poter configurare e configurare un connettore nel Centro conformità Microsoft 365 per importare e archiviare i dati dall'account Twitter dell'organizzazione.

- È necessario un account Twitter per l'organizzazione. è necessario accedere a questo account durante la configurazione del connettore.

- L'organizzazione deve avere una sottoscrizione di Azure valida. Se non si dispone di una sottoscrizione di Azure esistente, è possibile iscriversi a una di queste opzioni:

    - [Iscriversi per un abbonamento gratuito di Azure di un anno](https://azure.microsoft.com/free) 

    - [Iscriversi a una sottoscrizione di Azure con pagamento in base al prezzo](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La sottoscrizione gratuita di [Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) inclusa nell'abbonamento a Microsoft 365 non supporta i connettori nel Centro sicurezza & conformità.

- Il connettore Twitter può importare un totale di 200.000 elementi in un solo giorno. Se sono presenti più di 200.000 elementi di Twitter in un giorno, nessuno di questi elementi verrà importato in Microsoft 365.

- All'utente che configura il connettore Twitter nel Centro conformità Microsoft 365 (nel passaggio 5) deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni  [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Passaggio 1: Creare un'app in Azure Active Directory

Il primo passaggio consiste nel registrare una nuova app in Azure Active Directory (AAD). Questa app corrisponde alla risorsa dell'app Web implementata nel passaggio 2 per il connettore Twitter.

Per istruzioni dettagliate, vedere [Creare un'app in Azure Active Directory.](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)

Al termine di questo passaggio, seguendo le istruzioni dettagliate, le informazioni seguenti verranno salvate in un file di testo. Questi valori verranno utilizzati nei passaggi successivi del processo di distribuzione.

- ID applicazione AAD

- Segreto dell'applicazione AAD

- Tenant Id

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Passaggio 2: Distribuire il servizio Web del connettore dal repository GitHub all'account Azure

Il passaggio successivo consiste nel distribuire il codice sorgente per l'app del connettore Twitter che userà l'API di Twitter per connettersi al tuo account Twitter ed estrarre i dati in modo da poterlo importare in Microsoft 365. Il connettore Twitter distribuito per l'organizzazione carica gli elementi dall'account Twitter dell'organizzazione nel percorso di Archiviazione di Azure creato in questo passaggio. Dopo aver creato un connettore Twitter nel Centro conformità Microsoft 365 (nel passaggio 5), il servizio di importazione di Microsoft 365 copierà i dati di Twitter dalla posizione di Archiviazione di Azure a una cassetta postale in Microsoft 365. Come illustrato in precedenza nella sezione Prima di configurare un [connettore,](#before-you-set-up-a-connector) è necessario disporre di una sottoscrizione di Azure valida per creare un account di archiviazione di Azure.

Per distribuire il codice sorgente per l'app connettore Twitter:

1. Vai a [questo sito GitHub.](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)

2. Fare **clic su Distribuisci in Azure**.

Per istruzioni dettagliate, vedere [Deploy the connector web service from GitHub to your Azure account.](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)

Mentre segui le istruzioni dettagliate per completare questo passaggio, fornisci le informazioni seguenti

- APISecretKey: questo segreto viene creato durante il completamento di questo passaggio. Viene utilizzato nel passaggio 5.

- tenantId: ID tenant dell'organizzazione di Microsoft 365 copiato dopo aver creato l'app Twitter in Azure Active Directory nel passaggio 1.

Dopo aver completato questo passaggio, assicurati di copiare l'URL del servizio app (ad esempio, `https://twitterconnector.azurewebsites.net` ). È necessario utilizzare questo URL per completare i passaggi 3, 4 e 5.

## <a name="step-3-create-developer-app-on-twitter"></a>Passaggio 3: Creare app per sviluppatori su Twitter

Il passaggio successivo consiste nel creare e configurare un'app per sviluppatori su Twitter. Il connettore personalizzato creato nel passaggio 7 usa l'app Twitter per interagire con l'API di Twitter per ottenere dati dall'account Twitter dell'organizzazione.

Per istruzioni dettagliate, vedi Creare [l'app Twitter.](deploy-twitter-connector.md#step-3-create-the-twitter-app)

Durante il completamento di questo passaggio, seguendo le istruzioni dettagliate, è possibile salvare le informazioni seguenti in un file di testo. Questi valori verranno usati per configurare l'app connettore Twitter nel passaggio 4.

- Chiave API Twitter

- Chiave privata DELL'API di Twitter

- Token di accesso Twitter

- Twitter Access Token Secret

## <a name="step-4-configure-the-twitter-connector-app"></a>Passaggio 4: Configurare l'app connettore Twitter

Il passaggio successivo consiste nell'aggiungere le impostazioni di configurazione all'app del connettore di Twitter distribuita nel passaggio 2. A tale scopo, accedere alla home page dell'app connettore e configurarla.

Per istruzioni dettagliate, vedere [Configure the connector web app.](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)

Durante il completamento di questo passaggio ,seguendo le istruzioni dettagliate, verranno fornite le informazioni seguenti (copiate in un file di testo dopo aver completato i passaggi precedenti):

- Chiave API Twitter (ottenuta nel passaggio 3)

- Chiave privata DELL'API di Twitter (ottenuta nel passaggio 3)

- Token di accesso Twitter (ottenuto nel passaggio 3)

- Twitter Access Token Secret (ottenuto nel passaggio 3)

- ID applicazione di Azure Active Directory (ID applicazione AAD ottenuto nel passaggio 1)

- Segreto dell'applicazione Azure Active Directory (il segreto dell'applicazione AAD ottenuto nel passaggio 1)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Passaggio 5: Configurare un connettore Twitter nel Centro conformità Microsoft 365

Il passaggio finale consiste nel configurare il connettore Twitter nel Centro conformità Microsoft 365 che importerà i dati dall'account Twitter dell'organizzazione a una cassetta postale specificata in Microsoft 365. Dopo aver completato questo passaggio, il servizio di importazione di Microsoft 365 inizierà a importare dati dall'account Twitter dell'organizzazione a Microsoft 365.

Per istruzioni dettagliate, vedere [Set up a Twitter connector in the Microsoft 365 compliance center.](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center) 

Durante il completamento di questo passaggio ,seguendo le istruzioni dettagliate, verranno fornite le informazioni seguenti(che sono stati copiati in un file di testo dopo aver completato i passaggi).

- URL del servizio app di Azure (ottenuto nel passaggio 2, ad esempio, `https://twitterconnector.azurewebsites.net` )

- APISecretKey (creato nel passaggio 2)