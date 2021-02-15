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
description: Informazioni su come configurare & usare un connettore nel Centro conformità Microsoft 365 per importare i dati di & archivio dalle pagine di Facebook Business in Microsoft 365.
ms.openlocfilehash: df86897defa92788399f704c53c00ebb9e4f4269
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790150"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Configurare un connettore per archiviare i dati di Facebook (anteprima)

Usare un connettore nel Centro conformità Microsoft 365 per importare e archiviare i dati dalle pagine business di Facebook in Microsoft 365. Dopo aver configurato e configurato il connettore, si connette alla pagina Facebook Business (su base pianificata), converte il contenuto degli elementi di Facebook in un formato di messaggio di posta elettronica e quindi importa tali elementi in una cassetta postale in Microsoft 365.

Dopo aver importato i dati di Facebook, è possibile applicare ai dati di Facebook le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, Ricerca contenuto, archiviazione In-Place, controllo, conformità delle comunicazioni e criteri di conservazione di Microsoft 365. Ad esempio, quando a una cassetta postale viene assegnato il blocco per controversia legale o a un criterio di conservazione, i dati di Facebook vengono mantenuti. È possibile cercare dati di terze parti utilizzando Ricerca contenuto o associare la cassetta postale in cui sono archiviati i dati di Facebook a un responsabile in un caso di Advanced eDiscovery. L'uso di un connettore per importare e archiviare i dati di Facebook in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri normativi e governativi.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Prerequisiti per la configurazione di un connettore per le pagine di Facebook Business

Completare i prerequisiti seguenti prima di configurare e configurare un connettore nel Centro conformità Microsoft 365 per importare e archiviare i dati dalle pagine Facebook Business dell'organizzazione. 

- È necessario un account Facebook per le pagine aziendali dell'organizzazione (è necessario accedere a questo account durante la configurazione del connettore). Attualmente, è possibile archiviare solo i dati dalle pagine business di Facebook; non è possibile archiviare i dati dai singoli profili Facebook.

- L'organizzazione deve avere una sottoscrizione di Azure valida. Se non si dispone di una sottoscrizione di Azure esistente, è possibile iscriversi per una di queste opzioni:

    - [Iscriversi per una sottoscrizione gratuita di Azure di un anno](https://azure.microsoft.com/free)

    - [Iscriversi a una sottoscrizione di Azure con pagamento in base al prezzo](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > La sottoscrizione gratuita di [Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) inclusa nell'abbonamento a Microsoft 365 non supporta i connettori nel Centro sicurezza & conformità.

- Il connettore per le pagine di Facebook Business può importare un totale di 200.000 elementi in un singolo giorno. Se sono presenti più di 200.000 elementi di Facebook Business in un giorno, nessuno di questi elementi verrà importato in Microsoft 365.

- All'utente che configura il connettore personalizzato nel Centro conformità Microsoft 365 (nel passaggio 5) deve essere assegnato il ruolo di importazione/esportazione delle cassette postali in Exchange Online. Per impostazione predefinita, questo ruolo non è assegnato ad alcun gruppo di ruoli in Exchange Online. È possibile aggiungere il ruolo di importazione/esportazione delle cassette postali al gruppo di ruoli Gestione organizzazione in Exchange Online. In or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members. Per ulteriori informazioni, vedere le sezioni  [Creazione](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) di gruppi di ruoli o Modifica gruppi [di](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ruoli nell'articolo "Gestire i gruppi di ruoli in Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Passaggio 1: creare un'app in Azure Active Directory

Il primo passaggio consiste nel registrare una nuova app in Azure Active Directory (AAD). Questa app corrisponde alla risorsa dell'app Web implementata nei passaggi 4 e 5 per il connettore Facebook. 

Per istruzioni dettagliate, vedere Creare [un'app in Azure Active Directory.](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)

Durante il completamento di questo passaggio (usando le istruzioni dettagliate precedenti), le informazioni seguenti verranno salvate in un file di testo. Questi valori vengono utilizzati nei passaggi successivi del processo di distribuzione.

- ID applicazione AAD

- Segreto dell'applicazione AAD

- Tenant Id

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Passaggio 2: Distribuire il servizio Web del connettore da GitHub all'account Azure

Il passaggio successivo consiste nel distribuire il codice sorgente per l'app Del connettore pagine business di Facebook che userà l'API di Facebook per connettersi al tuo account Facebook ed estrarre i dati in modo da poterlo importare in Microsoft 365. Il connettore Facebook distribuito per l'organizzazione carica gli elementi dalle pagine di Facebook Business nella posizione di archiviazione di Azure creata in questo passaggio. Dopo aver creato un connettore per le pagine aziendali di Facebook nel Centro conformità Microsoft 365 (nel passaggio 5), il servizio di importazione copierà i dati delle pagine business di Facebook dalla posizione di Archiviazione di Azure a una cassetta postale nell'organizzazione di Microsoft 365. Come descritto in precedenza nella [sezione Prerequisiti,](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) è necessario disporre di una sottoscrizione di Azure valida per creare un account di archiviazione di Azure.

Per istruzioni dettagliate, vedere Distribuire il servizio Web del connettore [da GitHub all'account Azure.](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)

Nelle istruzioni dettagliate per completare questo passaggio, verranno fornite le informazioni seguenti:

- APISecretKey: questo segreto viene creato durante il completamento di questo passaggio. Viene utilizzato nel passaggio 5.

- TenantId: l'ID tenant dell'organizzazione Di Microsoft 365 copiato dopo aver creato l'app del connettore Facebook in Azure Active Directory nel passaggio 1.

Dopo aver completato questo passaggio, assicurarsi di copiare l'URL del servizio app di Azure (ad esempio, https://fbconnector.azurewebsites.net) . È necessario utilizzare questo URL per completare i passaggi 3, 4 e 5.

## <a name="step-3-register-the-web-app-on-facebook"></a>Passaggio 3: registrare l'app Web su Facebook

Il passaggio successivo consiste nel creare e configurare una nuova app su Facebook. Il connettore per le pagine business di Facebook creato nel passaggio 5 utilizza l'app Web Di Facebook per interagire con l'API di Facebook per ottenere dati dalle pagine Facebook Business dell'organizzazione.

Per istruzioni dettagliate, vedi Registrare [l'app Facebook.](deploy-facebook-connector.md#step-3-register-the-facebook-app)

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), è possibile salvare le informazioni seguenti in un file di testo. Questi valori vengono utilizzati per configurare l'app connettore Facebook nel passaggio 4.

- ID applicazione Facebook

- Segreto dell'applicazione Facebook

- I webhook di Facebook verificano il token

## <a name="step-4-configure-the-facebook-connector-app"></a>Passaggio 4: Configurare l'app connettore Di Facebook

Il passaggio successivo consiste nell'aggiungere le impostazioni di configurazione all'app del connettore Di Facebook caricata al momento della creazione della risorsa app Web di Azure nel passaggio 1. A tale scopo, accedere alla home page dell'app connettore e configurarla.

Per istruzioni dettagliate, vedere Configurare [l'app Connettore Facebook.](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), devi fornire le informazioni seguenti (che hai copiato in un file di testo dopo aver completato i passaggi precedenti):

- ID applicazione Facebook (ottenuto nel passaggio 3)

- Segreto dell'applicazione Facebook (ottenuto nel passaggio 3)

- I webhook di Facebook verificano il token (ottenuto nel passaggio 3)

- ID applicazione di Azure Active Directory (ID applicazione AAD ottenuto nel passaggio 1)

- Segreto dell'applicazione Azure Active Directory (il segreto dell'applicazione AAD ottenuto nel passaggio 1)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Passaggio 5: Configurare un connettore di pagine di Facebook Business nel Centro conformità Microsoft 365

Il passaggio finale consiste nel configurare il connettore nel Centro conformità Microsoft 365 che importerà i dati dalle pagine di Facebook Business in una cassetta postale specificata in Microsoft 365. Dopo aver completato questo passaggio, il servizio di importazione di Microsoft 365 inizierà a importare i dati dalle pagine di Facebook Business a Microsoft 365.

Per istruzioni dettagliate, vedere Passaggio 5: Configurare un connettore Facebook nel Centro conformità [Microsoft 365.](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center) 

Durante il completamento di questo passaggio (seguendo le istruzioni dettagliate), devi fornire le informazioni seguenti (che hai copiato in un file di testo dopo aver completato i passaggi).

- ID applicazione AAD (ottenuto nel passaggio 1)

- URL del servizio app di Azure (ottenuto nel passaggio 1, ad esempio https://fbconnector.azurewebsites.net)

- APISecretKey (creato nel passaggio 2)
