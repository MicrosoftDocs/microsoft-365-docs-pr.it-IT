---
title: Collaborare con gli utenti guest in un team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Informazioni sui passaggi di configurazione di Microsoft 365 necessari per configurare un team per la collaborazione su attività, conversazioni e documentazione con gli utenti guest in Teams.
ms.openlocfilehash: 34b7d5d47d7fb0c9196beda70184fa6510b6cc33
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780545"
---
# <a name="collaborate-with-guests-in-a-team"></a>Collaborare con gli utenti guest in un team

Se è necessario collaborare con gli utenti guest tra documenti, attività e conversazioni, è consigliabile usare Microsoft Teams. Teams offre tutte le funzionalità di collaborazione disponibili in Office e SharePoint con chat persistente e un set personalizzabile ed estendibile di strumenti di collaborazione in un'esperienza utente unificata.

In questo articolo verranno descritti i passaggi di configurazione di Microsoft 365 necessari per configurare un team per la collaborazione con gli utenti guest.

## <a name="video-demonstration"></a>Dimostrazione video

In questo video vengono illustrati i passaggi di configurazione descritti in questo documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Impostazioni di collaborazione esterna di Azure

La condivisione in Microsoft 365 è regolata al livello più alto dalle impostazioni di collaborazione esterna [B2B in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations) Se la condivisione guest è disabilitata o limitata in Azure AD, questa impostazione sostituisce tutte le impostazioni di condivisione configurate in Microsoft 365.

Controllare le impostazioni di collaborazione esterna B2B per assicurarsi che la condivisione con gli utenti guest non sia bloccata.

![Screenshot della pagina delle impostazioni delle relazioni aziendali di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Per impostare le impostazioni di collaborazione esterna

1. Accedere ad Azure Active Directory all'indirizzo [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. Nel riquadro di spostamento sinistro fare clic su **Azure Active Directory.**
3. Fare **clic su Identità esterne.**
4. Nel riquadro **di spostamento sinistro** della schermata Introduzione fare clic su Impostazioni collaborazione **esterna.**
5. Assicurarsi che **gli amministratori e gli utenti** nel  ruolo di mittente dell'invito guest possano invitare e che i membri possano invitare siano entrambi impostati su **Sì.**
6. Se si apportano modifiche, fare clic su **Salva**.

Prendere nota delle impostazioni nella **sezione Restrizioni di** collaborazione. Assicurarsi che i domini dei guest con cui si vuole collaborare non siano bloccati.

Se si lavora con utenti guest di più organizzazioni, è possibile limitare la possibilità di accedere ai dati della directory. Ciò impedirà loro di vedere chi altro è un guest nella directory. A tale scopo, in Restrizioni di accesso degli utenti **guest,** selezionare Gli utenti guest hanno accesso limitato alle proprietà e l'appartenenza alle impostazioni degli oggetti **directory** o l'accesso degli utenti Guest è limitato alle proprietà e alle appartenenze dei propri oggetti **directory.**

## <a name="teams-guest-access-settings"></a>Impostazioni di accesso guest di Teams

Teams dispone di un interruttore master on/off per l'accesso guest e di un'ampia gamma di impostazioni disponibili per controllare le operazioni che gli utenti guest possono eseguire in un team. L'opzione master Consenti **l'accesso guest in Teams** deve essere **attivata** perché l'accesso guest funzioni in Teams.

Verificare che l'accesso guest sia abilitato in Teams e apportare eventuali modifiche alle impostazioni guest in base alle esigenze aziendali. Tenere presente che queste impostazioni influiscono su tutti i team.

![Screenshot dell'opzione di accesso guest in Teams](../media/teams-guest-access-toggle-on.png)

Per configurare le impostazioni di accesso guest di Teams

1. Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com).
2. Nel riquadro di spostamento sinistro fare clic su **Mostra tutto.**
3. In **Interfacce di amministrazione** fare clic su **Teams**.
4. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams espandere **Impostazioni a livello di** organizzazione e fare clic su Accesso **guest.**
5. Assicurarsi che l'opzione **Consenti accesso ospite in Teams** sia **** abilitata.
6. Apportare le modifiche desiderate alle impostazioni guest aggiuntive e quindi fare clic su **Salva**.

Una volta attivato l'accesso guest di Teams, è possibile controllare facoltativamente l'accesso guest ai singoli team e ai siti di SharePoint associati utilizzando le etichette di riservatezza. Per altre informazioni, vedere [Usare le etichette di riservatezza per proteggere i contenuti in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!NOTE]
> Potrebbero essere necessario fino a 24 ore prima che le impostazioni guest di Teams diventino attive dopo l'attivazione.

## <a name="microsoft-365-groups-guest-settings"></a>Impostazioni guest dei gruppi di Microsoft 365

Teams usa i gruppi di Microsoft 365 per l'appartenenza al team. Le impostazioni guest dei gruppi di Microsoft 365 devono essere attivate per consentire il funzionamento dell'accesso guest in Teams.

![Screenshot delle impostazioni guest di Gruppi di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365](../media/office-365-groups-guest-settings.png)

Per configurare le impostazioni guest dei gruppi di Microsoft 365

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 espandere **Impostazioni.**
2. Fare **clic su Impostazioni organizzazione.**
3. Nell'elenco fare clic su **Gruppi di Microsoft 365.**
4. Verificare che le caselle di controllo Consenti ai proprietari del gruppo di aggiungere persone esterne all'organizzazione ai gruppi di **Microsoft 365** come guest e che le caselle di controllo Consenti ai membri del gruppo **guest** di accedere al contenuto del gruppo siano entrambe selezionate.
5. Se sono state apportate modifiche, fare clic **su Salva modifiche.**


## <a name="sharepoint-organization-level-sharing-settings"></a>Impostazioni di condivisione a livello di organizzazione di SharePoint

I contenuti di Teams, ad esempio file, cartelle ed elenchi, vengono tutti archiviati in SharePoint. Per consentire agli utenti guest di accedere a questi elementi in Teams, le impostazioni di condivisione a livello di organizzazione di SharePoint devono consentire la condivisione con gli utenti guest.

Le impostazioni a livello di organizzazione determinano le impostazioni disponibili per i singoli siti, inclusi i siti associati ai team. Le impostazioni del sito non possono essere più permissive delle impostazioni a livello di organizzazione.

Se si desidera consentire la condivisione di file e cartelle con utenti non autenticati, scegliere **Chiunque.** Se si desidera assicurarsi che tutti gli utenti guest devono eseguire l'autenticazione, scegliere Utenti **guest nuovi ed esistenti.** Scegliere l'impostazione più permissiva che sarà necessaria a qualsiasi sito dell'organizzazione.

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Per configurare le impostazioni di condivisione a livello di organizzazione di SharePoint

1. Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento sinistro, in **Interfaccia di amministrazione,** fare clic su **SharePoint.**
2. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di SharePoint espandere **Criteri** e quindi fare clic su **Condivisione.**
3. Verificare che la condivisione esterna per SharePoint sia impostata su **Chiunque** o Utenti guest nuovi **ed esistenti.**
4. Se si apportano modifiche, fare clic su **Salva**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Impostazioni di collegamento predefinite a livello di organizzazione di SharePoint

Le impostazioni predefinite dei collegamenti a file e cartelle determinano l'opzione di collegamento che verrà visualizzata agli utenti per impostazione predefinita quando condividono un file o una cartella. Gli utenti possono modificare il tipo di collegamento in una delle altre opzioni prima della condivisione, se lo si desidera.

Tenere presente che questa impostazione influisce su tutti i team e i siti di SharePoint nell'organizzazione.

Scegliere uno dei tipi di collegamento seguenti che verranno selezionati per impostazione predefinita quando gli utenti condividono file e cartelle:

- **Chiunque abbia il collegamento:** scegliere questa opzione se si prevede di eseguire una grande condivisione non autenticata di file e cartelle. Se si desidera consentire collegamenti *chiunque* ma si è preoccupati per la condivisione accidentale non autenticata, prendere in considerazione una delle altre opzioni come impostazione predefinita. Questo tipo di collegamento è disponibile solo se è stata abilitata la **condivisione chiunque.**
- **Solo gli utenti dell'organizzazione:** scegliere questa opzione se si prevede che la maggior parte della condivisione di file e cartelle sia con utenti interni all'organizzazione.
- **Persone specifiche:** prendere in considerazione questa opzione se si prevede di eseguire molte attività di condivisione di file e cartelle con utenti guest. Questo tipo di collegamento funziona con gli utenti guest e richiede l'autenticazione.
 
![Screenshot delle impostazioni di condivisione di file e cartelle a livello di organizzazione in SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


Per impostare le impostazioni di collegamento predefinite a livello di organizzazione di SharePoint

1. Passare alla pagina Condivisione nell'interfaccia di amministrazione di SharePoint.
2. In **Collegamenti a file e cartelle** selezionare il collegamento di condivisione predefinito che si desidera utilizzare.
3. Se si apportano modifiche, fare clic su **Salva**.

## <a name="create-a-team"></a>Creare un team

Il passaggio successivo consiste nel creare il team che si prevede di usare per la collaborazione con gli utenti guest.

Per creare un team
1. In Teams, nella scheda **Teams,** fare clic su **Partecipa o crea un team** nella parte inferiore del riquadro sinistro.
2. Fare **clic su Crea team.**
3. Fare **clic su Crea un team da zero.**
4. Scegliere **Privato** o **Pubblico.**
5. Digitare un nome e una descrizione per il team e quindi fare clic su **Crea.**
6. Fare **clic su Ignora.**

Inviteremo gli utenti in un secondo momento. Successivamente, è importante controllare le impostazioni di condivisione a livello di sito per il sito di SharePoint associato al team.

## <a name="sharepoint-site-level-sharing-settings"></a>Impostazioni di condivisione a livello di sito di SharePoint

Controllare le impostazioni di condivisione a livello di sito per assicurarsi che consentano il tipo di accesso desiderato per il team. Ad esempio, se si impostano le impostazioni a livello di organizzazione su **Chiunque**, ma si desidera che tutti gli utenti guest eseercitino l'autenticazione per questo team, assicurarsi che le impostazioni di condivisione a livello di sito siano impostate su Utenti guest nuovi ed **esistenti.**

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Per configurare le impostazioni di condivisione a livello di sito
1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di SharePoint espandere **Siti** e fare clic su **Siti attivi.**
2. Selezionare il sito del team appena creato.
3. Fare clic su ... e scegliere **Condivisione.**
4. Verificare che la condivisione sia impostata **su Chiunque o** Utenti guest nuovi ed **esistenti.**
5. Se si apportano modifiche, fare clic su **Salva**.

## <a name="invite-users"></a>Invitare utenti

Le impostazioni di condivisione guest sono ora configurate, quindi è possibile iniziare ad aggiungere utenti interni e guest al team. 

Per invitare utenti interni a un team
1. Nel team fare clic su **Altre opzioni** ( ) e quindi su **\*\*\*** Aggiungi **membro.**
2. Digitare il nome della persona che si desidera invitare.
3. Fare clic su **Aggiungi**, quindi fare clic su **Chiudi**.

Per invitare utenti guest a un team
1. Nel team fare clic su **Altre opzioni** ( ) e quindi su **\*\*\*** Aggiungi **membro.**
2. Digitare l'indirizzo di posta elettronica del guest che si desidera invitare.
3. Fare **clic su Modifica informazioni guest.**
4. Digitare il nome completo del guest e fare clic sul segno di spunta.
5. Fare clic su **Aggiungi**, quindi fare clic su **Chiudi**.

## <a name="see-also"></a>Vedere anche

[Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](best-practices-anonymous-sharing.md)

[Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest](share-limit-accidental-exposure.md)

[Creare un ambiente di condivisione guest sicuro](create-secure-guest-sharing-environment.md)

[Creare una Extranet B2B con guest gestiti](b2b-extranet.md).

[Integrazione di SharePoint e OneDrive con Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[Le opzioni di condivisione sono disattivate durante la condivisione da SharePoint o OneDrive](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
