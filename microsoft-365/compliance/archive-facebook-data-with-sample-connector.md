---
title: Configurare un connettore per archiviare i dati di Facebook
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
description: Gli amministratori possono configurare un connettore per l'importazione di dati di terze parti da origini dati, ad esempio pagine business di Facebook, Twitter, pagine società di LinkedIn e Instant Bloomberg. In questo modo è possibile archiviare i dati provenienti da origini dati di terze parti in Microsoft 365 per poter utilizzare le funzionalità di conformità, ad esempio la conservazione legale, la ricerca di contenuto e i criteri di ritenzione per gestire la governance dei dati di terze parti dell'organizzazione.
ms.openlocfilehash: 5c8bb4c1330af0f9c10dd93f9cedd47b3d3b34b0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637126"
---
# <a name="set-up-a-connector-to-archive-facebook-data"></a>Configurare un connettore per archiviare i dati di Facebook

Utilizzare un connettore nel centro conformità di Microsoft 365 per importare e archiviare i dati da pagine business di Facebook a Microsoft 365. Dopo aver configurato e configurato il connettore, si connette alla pagina business di Facebook (su base pianificata), converte il contenuto degli elementi di Facebook in un formato di messaggio di posta elettronica e quindi importa tali elementi in una cassetta postale in Microsoft 365.

Dopo aver importato i dati di Facebook, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio il blocco per controversia legale, la ricerca di contenuti, l'archiviazione sul posto, il controllo, la conformità alla comunicazione e i criteri di conservazione di Microsoft 365 ai dati di Facebook. Ad esempio, quando una cassetta postale viene inserita nella conservazione per controversia legale o assegnata a un criterio di mantenimento, vengono conservati i dati di Facebook. È possibile cercare i dati di terze parti utilizzando la ricerca contenuto o associare la cassetta postale in cui vengono archiviati i dati di Facebook con un custode in un caso avanzato di eDiscovery. L'utilizzo di un connettore per l'importazione e l'archiviazione dei dati di Facebook in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Prerequisiti per la configurazione di un connettore per le pagine business di Facebook

Completare i prerequisiti seguenti prima di poter impostare e configurare un connettore nel centro conformità di Microsoft 365 per importare e archiviare i dati dalle pagine aziendali di Facebook dell'organizzazione. 

- Per le pagine business dell'organizzazione è necessario un account di Facebook (è necessario accedere a questo account quando si configura il connettore). Attualmente, è possibile archiviare i dati solo da pagine business di Facebook; non è possibile archiviare i dati provenienti da singoli profili Facebook.

- L'organizzazione deve disporre di una sottoscrizione di Azure valida. Se non si dispone di una sottoscrizione di Azure esistente, è possibile iscriversi a una di queste opzioni:

    - [Iscriversi per un abbonamento gratuito a un anno di Azure](https://azure.microsoft.com/free) 

    - [Iscriversi a una sottoscrizione di Azure pay-as-you-go](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La [sottoscrizione gratuita di Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) inclusa nell'abbonamento a Microsoft 365 non supporta i connettori nel centro sicurezza & conformità.

- L'organizzazione deve autorizzare il servizio di importazione di Office 365 per accedere ai dati delle cassette postali nell'organizzazione. Per acconsentire a questa richiesta, accedere a [Questa pagina](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), accedere con le credenziali di un amministratore globale e quindi accettare la richiesta.

- All'utente che configura il connettore personalizzato nel centro conformità di Microsoft 365 (nel passaggio 5) deve essere assegnato il ruolo di esportazione delle cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo import export delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In alternativa, è possibile creare un gruppo di ruoli, assegnare il ruolo di esportazione delle cassette postali e quindi aggiungere gli utenti corretti come membri. Per ulteriori informazioni, vedere la sezione creare gruppi di [ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o [modificare gruppi di ruoli](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Passaggio 1: creare un'app in Azure Active Directory

Il primo passaggio consiste nel registrare una nuova app in Azure Active Directory (AAD). Questa applicazione corrisponde alla risorsa Web App implementata nel passaggio 4 e al passaggio 5 per il connettore Facebook. 

Per istruzioni dettagliate, vedere [creare un'app in Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).

Durante il completamento di questo passaggio (utilizzando le istruzioni dettagliate precedenti), vengono salvate in un file di testo le informazioni seguenti. Questi valori vengono utilizzati nei passaggi successivi del processo di distribuzione.

- ID applicazione AAD

- Segreto dell'applicazione AAD

- ID tenant

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Passaggio 2: distribuire il servizio Web del connettore da GitHub all'account di Azure

Il passaggio successivo consiste nel distribuire il codice sorgente per l'app Facebook business Pages Connector che utilizzerà l'API di Facebook per connettersi all'account di Facebook ed estrarre i dati in modo da poterli importare in Microsoft 365. Il connettore Facebook distribuito per l'organizzazione invierà gli elementi dalle pagine di business di Facebook al percorso di archiviazione di Azure creato in questo passaggio. Dopo aver creato un connettore di pagine business di Facebook nel centro conformità di Microsoft 365 (al passaggio 5), il servizio di importazione copierà i dati di pagine business di Facebook dal percorso di archiviazione di Azure a una cassetta postale nell'organizzazione di Microsoft 365. Come illustrato in precedenza nella sezione [Prerequisites](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) , è necessario disporre di una sottoscrizione di Azure valida per creare un account di archiviazione di Azure.

Per istruzioni dettagliate, vedere [deploy the Connector Web Service from GitHub to your Azure account](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

Nelle istruzioni dettagliate per completare questo passaggio, sono disponibili le seguenti informazioni:

- APISecretKey: questo segreto è stato creato durante il completamento di questo passaggio. Viene utilizzato nel passaggio 5.

- TenantId: l'ID tenant dell'organizzazione Microsoft 365 copiato dopo aver creato l'app Facebook Connector in Azure Active Directory nel passaggio 1.

Dopo aver completato questo passaggio, assicurarsi di copiare l'URL del servizio app di Azure, https://fbconnector.azurewebsites.net)ad esempio. Per completare il passaggio 3, il passaggio 4 e il passaggio 5, è necessario utilizzare questo URL.

## <a name="step-3-register-the-web-app-on-facebook"></a>Passaggio 3: registrare l'app Web su Facebook

Il passaggio successivo consiste nel creare e configurare una nuova applicazione su Facebook. Il connettore di pagine business di Facebook creato nel passaggio 5 utilizza l'app Web Facebook per interagire con l'API di Facebook per ottenere i dati dalle pagine aziendali di Facebook dell'organizzazione.

Per istruzioni dettagliate, vedere [Register the Facebook app](deploy-facebook-connector.md#step-3-register-the-facebook-app).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), salvare le informazioni seguenti in un file di testo. Questi valori vengono utilizzati per configurare l'app connettore Facebook nel passaggio 4.

- ID applicazione Facebook

- Segreto dell'applicazione Facebook

- I webhook di Facebook verificano il token

## <a name="step-4-configure-the-facebook-connector-app"></a>Passaggio 4: configurare l'app del connettore Facebook

Il passaggio successivo consiste nell'aggiungere impostazioni di configurazione all'app del connettore Facebook che è stata caricata quando è stata creata la risorsa Azure Web App nel passaggio 1. A tale scopo, passare alla Home page dell'app del connettore e configurarla.

Per istruzioni dettagliate, vedere [Configure the Facebook Connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), vengono fornite le informazioni seguenti (che sono state copiate in un file di testo dopo aver completato i passaggi precedenti):

- ID applicazione Facebook (ottenuto nel passaggio 3)

- Segreto dell'applicazione Facebook (ottenuto nel passaggio 3)

- I webhook di Facebook verificano il token (ottenuto nel passaggio 3)

- ID applicazione di Azure Active Directory (ID applicazione AAD ottenuto nel passaggio 1)

- Segreto dell'applicazione di Azure Active Directory (segreto dell'applicazione AAD ottenuto nel passaggio 1)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Passaggio 5: configurare un connettore di pagine business di Facebook nel centro conformità di Microsoft 365

Il passaggio finale consiste nel configurare il connettore nel centro conformità di Microsoft 365 che importerà i dati dalle pagine aziendali di Facebook a una cassetta postale specificata in Microsoft 365. Dopo aver completato questo passaggio, il servizio di importazione di Office 365 inizierà a importare i dati dalle pagine business di Facebook a Microsoft 365.

Per istruzioni dettagliate, vedere [passaggio 5: configurare un connettore Facebook nel centro conformità di Microsoft 365](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center). 

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), vengono fornite le informazioni seguenti (che sono state copiate in un file di testo dopo aver completato la procedura).

- ID applicazione AAD (ottenuto nel passaggio 1)

- URL del servizio app di Azure (ottenuto nel passaggio 1, ad esempiohttps://fbconnector.azurewebsites.net)

- APISecretKey (creato nel passaggio 2)
