---
title: Configurare un connettore per archiviare i dati di Facebook
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
description: Informazioni su come configurare & usare un connettore nel Centro conformità Microsoft 365 per importare & dati di archiviazione dalle pagine business di Facebook a Microsoft 365.
ms.openlocfilehash: 616466a3af83c1558184526aa463f68c10ef9e70
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921736"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Configurare un connettore per archiviare i dati di Facebook (anteprima)

Usare un connettore nel Centro Microsoft 365 conformità per importare e archiviare i dati dalle pagine business di Facebook per Microsoft 365. Dopo aver configurato e configurato il connettore, si connette alla pagina Facebook Business (su base pianificata), converte il contenuto degli elementi di Facebook in un formato di messaggio di posta elettronica e quindi importa tali elementi in una cassetta postale in Microsoft 365.

Dopo l'importazione dei dati di Facebook, è possibile applicare ai dati di Facebook le funzionalità di conformità di Microsoft 365 quali conservazione per controversia legale, Ricerca contenuto, archiviazione In-Place, controllo, conformità delle comunicazioni e criteri di conservazione Microsoft 365. Ad esempio, quando una cassetta postale viene messa in conservazione per controversia legale o assegnata a un criterio di conservazione, i dati di Facebook vengono mantenuti. È possibile cercare dati di terze parti utilizzando Ricerca contenuto o associare la cassetta postale in cui i dati di Facebook sono archiviati a un responsabile in un Advanced eDiscovery caso. L'uso di un connettore per importare e archiviare i dati di Facebook in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Prerequisiti per la configurazione di un connettore per le pagine di Facebook Business

Completare i prerequisiti seguenti prima di poter configurare e configurare un connettore nel Centro conformità Microsoft 365 per importare e archiviare i dati dalle pagine Facebook Business dell'organizzazione. 

- È necessario un account Facebook per le pagine aziendali dell'organizzazione (è necessario accedere a questo account durante la configurazione del connettore). Attualmente, è possibile archiviare solo i dati dalle pagine business di Facebook. non è possibile archiviare dati da singoli profili Facebook.

- L'organizzazione deve avere una sottoscrizione di Azure valida. Se non si dispone di una sottoscrizione di Azure esistente, è possibile iscriversi a una di queste opzioni:

    - [Iscriversi per un abbonamento gratuito di Azure di un anno](https://azure.microsoft.com/free)

    - [Iscriversi a una sottoscrizione di Azure con pagamento in base al prezzo](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La [sottoscrizione Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) gratuita inclusa nell'abbonamento Microsoft 365 non supporta i connettori nel Centro sicurezza & conformità.

- Il connettore per le pagine facebook business può importare un totale di 200.000 elementi in un solo giorno. Se sono presenti più di 200.000 elementi di Facebook Business in un giorno, nessuno di questi elementi verrà importato in Microsoft 365.

- All'utente che configura il connettore personalizzato nel Centro conformità Microsoft 365 (nel passaggio 5) deve essere assegnato il ruolo Esportazione importazione cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo Esportazione importazione cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In caso contrario, è possibile creare un gruppo di ruoli, assegnare il ruolo Importazione/Esportazione cassette postali e quindi aggiungere gli utenti appropriati come membri. Per ulteriori informazioni, vedere le sezioni [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) o Modify role [groups](/Exchange/permissions-exo/role-groups#modify-role-groups) nell'articolo "Manage role groups in Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Passaggio 1: Creare un'app in Azure Active Directory

Il primo passaggio consiste nel registrare una nuova app in Azure Active Directory (AAD). Questa app corrisponde alla risorsa dell'app Web implementata nei passaggi 4 e 5 per il connettore Facebook. 

Per istruzioni dettagliate, vedi [Creare un'app in Azure Active Directory.](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)

Durante il completamento di questo passaggio ,utilizzando le istruzioni dettagliate precedenti, le informazioni seguenti verranno salvate in un file di testo. Questi valori vengono utilizzati nei passaggi successivi del processo di distribuzione.

- ID applicazione AAD

- Segreto dell'applicazione AAD

- Tenant Id

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Passaggio 2: Distribuire il servizio Web del connettore da GitHub all'account Azure

Il passaggio successivo consiste nel distribuire il codice sorgente per l'app del connettore delle pagine business di Facebook che userà l'API di Facebook per connettersi al tuo account Facebook ed estrarre i dati in modo da poterlo importare in Microsoft 365. Il connettore di Facebook distribuito per l'organizzazione carica gli elementi dalle pagine di Facebook Business nella posizione Archiviazione di Azure creata in questo passaggio. Dopo aver creato un connettore pagine business di Facebook nel Centro conformità Microsoft 365 (nel passaggio 5), il servizio di importazione copierà i dati delle pagine business di Facebook dalla posizione di Archiviazione di Azure a una cassetta postale nell'organizzazione di Microsoft 365. Come illustrato in precedenza nella [sezione Prerequisiti,](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) è necessario disporre di una sottoscrizione di Azure valida per creare un Archiviazione di Azure account.

Per istruzioni dettagliate, vedere [Deploy the connector web service from GitHub to your Azure account.](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)

Nelle istruzioni dettagliate per completare questo passaggio verranno fornite le informazioni seguenti:

- APISecretKey: questo segreto viene creato durante il completamento di questo passaggio. Viene utilizzato nel passaggio 5.

- TenantId: l'ID tenant dell'organizzazione Microsoft 365 che hai copiato dopo aver creato l'app del connettore di Facebook in Azure Active Directory nel passaggio 1.

Dopo aver completato questo passaggio, assicurati di copiare l'URL del servizio app di Azure (ad esempio, https://fbconnector.azurewebsites.net) . È necessario utilizzare questo URL per completare i passaggi 3, 4 e 5.

## <a name="step-3-register-the-web-app-on-facebook"></a>Passaggio 3: registrare l'app Web su Facebook

Il passaggio successivo consiste nel creare e configurare una nuova app su Facebook. Il connettore delle pagine business di Facebook creato nel passaggio 5 usa l'app Web Di Facebook per interagire con l'API di Facebook per ottenere i dati dalle pagine Facebook Business dell'organizzazione.

Per istruzioni dettagliate, vedi Registrare [l'app Facebook.](deploy-facebook-connector.md#step-3-register-the-facebook-app)

Durante il completamento di questo passaggio, seguendo le istruzioni dettagliate, è possibile salvare le informazioni seguenti in un file di testo. Questi valori vengono usati per configurare l'app del connettore Facebook nel passaggio 4.

- ID applicazione Facebook

- Segreto dell'applicazione Facebook

- I webhook di Facebook verificano il token

## <a name="step-4-configure-the-facebook-connector-app"></a>Passaggio 4: Configurare l'app connettore Di Facebook

Il passaggio successivo consiste nell'aggiungere le impostazioni di configurazione all'app del connettore di Facebook caricata al momento della creazione della risorsa app Web di Azure nel passaggio 1. A tale scopo, accedere alla home page dell'app connettore e configurarla.

Per istruzioni dettagliate, vedere [Configure the Facebook connector app.](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)

Durante il completamento di questo passaggio ,seguendo le istruzioni dettagliate, vengono fornite le informazioni seguenti (copiate in un file di testo dopo aver completato i passaggi precedenti):

- ID applicazione Facebook (ottenuto nel passaggio 3)

- Segreto dell'applicazione Facebook (ottenuto nel passaggio 3)

- I webhook di Facebook verificano il token (ottenuto nel passaggio 3)

- Azure Active Directory dell'applicazione (ID applicazione AAD ottenuto nel passaggio 1)

- Azure Active Directory dell'applicazione (il segreto dell'applicazione AAD ottenuto nel passaggio 1)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Passaggio 5: Configurare un connettore pagine business di Facebook nel Centro Microsoft 365 conformità

Il passaggio finale consiste nel configurare il connettore nel Centro conformità Microsoft 365 che importerà i dati dalle pagine di Facebook Business a una cassetta postale specificata in Microsoft 365. Dopo aver completato questo passaggio, il servizio Microsoft 365 importerà i dati dalle pagine di Facebook Business per Microsoft 365.

Per istruzioni dettagliate, vedere [Passaggio 5: Configurare un](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)connettore di Facebook nel Centro Microsoft 365 conformità. 

Al termine di questo passaggio, seguendo le istruzioni dettagliate, vengono fornite le informazioni seguenti, che sono stati copiati in un file di testo dopo aver completato i passaggi.

- ID applicazione AAD (ottenuto nel passaggio 1)

- URL del servizio app di Azure (ottenuto nel passaggio 1, ad esempio, https://fbconnector.azurewebsites.net)

- APISecretKey (creato nel passaggio 2)