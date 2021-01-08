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
description: Informazioni sui passaggi di configurazione di Microsoft 365 necessari per configurare un team per l'attività, la conversazione e la documentazione per la collaborazione con i clienti del team.
ms.openlocfilehash: 34b7d5d47d7fb0c9196beda70184fa6510b6cc33
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780545"
---
# <a name="collaborate-with-guests-in-a-team"></a>Collaborare con gli utenti guest in un team

Se è necessario collaborare con gli utenti tra documenti, attività e conversazioni, è consigliabile utilizzare Microsoft teams. Teams offre tutte le funzionalità di collaborazione disponibili in Office e SharePoint con chat persistente e un set di strumenti di collaborazione personalizzabile ed estensibile in un'esperienza utente unificata.

In questo articolo verranno illustrati i passaggi di configurazione di Microsoft 365 necessari per configurare un team per la collaborazione con gli utenti.

## <a name="video-demonstration"></a>Dimostrazione video

In questo video vengono illustrati i passaggi di configurazione descritti in questo documento.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Impostazioni di collaborazione esterna di Azure

La condivisione in Microsoft 365 è regolata al livello più alto dalle [impostazioni di collaborazione esterna B2B in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Se la condivisione Guest è disabilitata o limitata in Azure AD, questa impostazione sostituisce tutte le impostazioni di condivisione configurate in Microsoft 365.

Controllare le impostazioni di collaborazione esterna B2B per garantire che la condivisione con gli utenti non sia bloccata.

![Screenshot della pagina delle impostazioni delle relazioni aziendali di Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Per impostare le impostazioni di collaborazione esterna

1. Accedere a Azure Active Directory all'indirizzo [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. Nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.
3. Fare clic su **identità esterne**.
4. Nella schermata **inizia** , nel riquadro di spostamento a sinistra, fare clic su **impostazioni di collaborazione esterna**.
5. Verificare che **gli amministratori e gli utenti del ruolo invitato ospite possano invitare** e che **i membri possano invitare** siano entrambi impostati su **Sì**.
6. Se si apportano modifiche, fare clic su **Salva**.

Prendere nota delle impostazioni nella sezione **vincoli di collaborazione** . Verificare che i domini degli utenti con cui si desidera collaborare non siano bloccati.

Se si lavora con clienti provenienti da più organizzazioni, è possibile che si desideri limitare la possibilità di accedere ai dati della directory. Ciò impedirà loro di vedere chi altro è un ospite nella directory. Per eseguire questa operazione, in **restrizioni di accesso degli utenti Guest**, selezionare **Guest gli utenti hanno accesso limitato alle proprietà e l'appartenenza delle impostazioni degli oggetti directory** o **l'accesso degli utenti Guest è limitato alle proprietà e alle appartenenze dei propri oggetti directory**.

## <a name="teams-guest-access-settings"></a>Impostazioni di accesso Guest Teams

I team dispongono di un'opzione Master di attivazione/disattivazione dell'accesso guest e di una serie di impostazioni disponibili per controllare gli utenti che possono eseguire in un team. L'opzione master **consente all'accesso guest nei team** di essere **attiva** per l'accesso guest per il lavoro in teams.

Verificare che l'accesso Guest sia abilitato nei team e apportare eventuali adeguamenti alle impostazioni guest in base alle esigenze aziendali. Tenere presente che queste impostazioni influiscono su tutti i team.

![Screenshot dell'opzione di accesso guest in Teams](../media/teams-guest-access-toggle-on.png)

Per configurare le impostazioni di accesso guest di Teams

1. Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo [https://admin.microsoft.com](https://admin.microsoft.com).
2. Nel riquadro di spostamento a sinistra, fare clic su **Mostra tutto**.
3. In **Interfacce di amministrazione** fare clic su **Teams**.
4. Nell'interfaccia di amministrazione dei team, nel riquadro di spostamento a sinistra, espandere **impostazioni a livello di organizzazione** e fare clic su **accesso Guest**.
5. Assicurarsi che l'opzione **Consenti accesso ospite in Teams** sia **** abilitata.
6. Apportare le modifiche desiderate alle impostazioni guest aggiuntive e quindi fare clic su **Salva**.

Dopo aver abilitato l'accesso Guest ai team, è possibile controllare l'accesso Guest ai singoli team e ai siti di SharePoint associati utilizzando le etichette di riservatezza. Per altre informazioni, vedere [Usare le etichette di riservatezza per proteggere i contenuti in Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!NOTE]
> Dopo averla attivata, potrebbero essere necessarie fino a ventiquattro ore per rendere attive le impostazioni Guest del team.

## <a name="microsoft-365-groups-guest-settings"></a>Microsoft 365 groups Guest Settings

Teams utilizza i gruppi di Microsoft 365 per l'appartenenza al team. È necessario che le impostazioni Guest dei gruppi Microsoft 365 siano attivate in modo che l'accesso guest nei team funzioni.

![Screenshot delle impostazioni guest di Gruppi di Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365](../media/office-365-groups-guest-settings.png)

Per impostare Microsoft 365 groups Guest Settings

1. Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento a sinistra, espandere **Impostazioni**.
2. Fare clic su **Impostazioni organizzazione**.
3. Nell'elenco, fare clic su **gruppi Microsoft 365**.
4. Assicurarsi che i **proprietari di Let Group aggiungano le persone all'esterno dell'organizzazione ai gruppi di Microsoft 365 come ospiti** e che i **membri del gruppo di accesso al contenuto del** gruppo siano entrambi controllati.
5. Se sono state apportate modifiche, fare clic su **Salva modifiche**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Impostazioni di condivisione a livello di organizzazione di SharePoint

I contenuti dei team, ad esempio file, cartelle ed elenchi, sono tutti archiviati in SharePoint. Per consentire agli utenti di accedere a questi elementi nei team, le impostazioni di condivisione a livello dell'organizzazione di SharePoint devono essere consentite per la condivisione con gli utenti.

Le impostazioni a livello di organizzazione determinano le impostazioni disponibili per i singoli siti, inclusi i siti associati ai team. Le impostazioni del sito non possono essere più permissive rispetto alle impostazioni a livello di organizzazione.

Se si desidera consentire la condivisione di file e cartelle con persone non autenticate, scegliere **nessuno**. Se si desidera garantire che tutti gli utenti siano in grado di eseguire l'autenticazione, scegliere **clienti nuovi ed esistenti**. Scegliere l'impostazione più permissiva che sarà necessaria per qualsiasi sito dell'organizzazione.

![Screenshot delle impostazioni di condivisione a livello di organizzazione in SharePoint](../media/sharepoint-organization-external-sharing-controls.png)


Per impostare le impostazioni di condivisione a livello di organizzazione di SharePoint

1. Nell'interfaccia di amministrazione di Microsoft 365, nel riquadro di spostamento a sinistra, in interfaccia di **Amministrazione**, fare clic su **SharePoint**.
2. Nell'interfaccia di amministrazione di SharePoint, nel riquadro di spostamento a sinistra, espandere **criteri** e quindi fare clic su **condivisione**.
3. Assicurarsi che la condivisione esterna per SharePoint sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.
4. Se si apportano modifiche, fare clic su **Salva**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Impostazioni di collegamento predefinite a livello di organizzazione di SharePoint

Le impostazioni predefinite per il collegamento di file e cartelle determinano l'opzione di collegamento che verrà visualizzata agli utenti per impostazione predefinita quando condividono un file o una cartella. Gli utenti possono modificare il tipo di collegamento in una delle altre opzioni prima di condividerlo, se necessario.

Tenere presente che questa impostazione ha effetto su tutti i team e i siti di SharePoint dell'organizzazione.

Scegliere uno dei seguenti tipi di collegamento che verranno selezionati per impostazione predefinita quando gli utenti condividono file e cartelle:

- **Tutti gli utenti con il collegamento** : scegliere questa opzione se si prevede di eseguire la condivisione di file e cartelle in modo molto non autenticato. Se si desidera consentire collegamenti a *tutti gli utenti* , ma si è preoccupati per la condivisione accidentale non autenticata, prendere in considerazione una delle altre opzioni come impostazione predefinita. Questo tipo di collegamento è disponibile solo se è stata abilitata la condivisione di **utenti** .
- **Solo persone nell'organizzazione** : scegliere questa opzione se si prevede che la maggior parte della condivisione di file e cartelle sia con le persone all'interno dell'organizzazione.
- **Persone specifiche** : considerare questa opzione se si prevede di eseguire un sacco di condivisione di file e cartelle con gli utenti. Questo tipo di collegamento è compatibile con gli utenti e richiede l'autenticazione.
 
![Screenshot delle impostazioni di condivisione di file e cartelle a livello di organizzazione in SharePoint](../media/sharepoint-organization-files-folders-sharing-settings.png)


Per impostare le impostazioni dei collegamenti predefiniti a livello di organizzazione di SharePoint

1. Passare alla pagina condivisione nell'interfaccia di amministrazione di SharePoint.
2. In **collegamenti a file e cartelle** selezionare il collegamento di condivisione predefinito che si desidera utilizzare.
3. Se si apportano modifiche, fare clic su **Salva**.

## <a name="create-a-team"></a>Creare un team

Il passaggio successivo consiste nel creare il team che si intende utilizzare per la collaborazione con gli utenti.

Per creare un team
1. In teams fare clic su **join oppure creare un team** nella parte inferiore del riquadro sinistro nella scheda **Teams** .
2. Fare clic su **Crea team**.
3. Fare clic su **Crea un team da zero**.
4. Scegliere **privato** o **pubblico**.
5. Digitare un nome e una descrizione per il team, quindi fare clic su **Crea**.
6. Fare clic su **Ignora**.

Gli utenti verranno invitati in un secondo momento. Successivamente, è importante controllare le impostazioni di condivisione a livello di sito per il sito di SharePoint associato al team.

## <a name="sharepoint-site-level-sharing-settings"></a>Impostazioni di condivisione a livello di sito di SharePoint

Controllare le impostazioni di condivisione a livello di sito per assicurarsi che consentano il tipo di accesso desiderato per il team. Ad esempio, se si impostano le impostazioni a livello di organizzazione per tutti gli **utenti**, ma si desidera che tutti gli ospiti eseguano l'autenticazione per questo team, assicurarsi che le impostazioni di condivisione a livello di sito siano impostate su **Guest nuovi e esistenti**.

![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Per impostare le impostazioni di condivisione a livello di sito
1. Nell'interfaccia di amministrazione di SharePoint, nel riquadro di spostamento a sinistra, espandere **siti** e fare clic su **siti attivi**.
2. Selezionare il sito del team appena creato.
3. Fare clic su... e scegli **condivisione**.
4. Verificare che la condivisione sia impostata su **tutti gli utenti** o **gli ospiti nuovi e esistenti**.
5. Se si apportano modifiche, fare clic su **Salva**.

## <a name="invite-users"></a>Invitare utenti

Le impostazioni di condivisione Guest sono ora configurate, quindi è possibile iniziare ad aggiungere utenti interni e ospiti al team. 

Per invitare gli utenti interni a un team
1. Nel team, fare clic su **altre opzioni** ( **\*\*\*** ), quindi fare clic su **Aggiungi membro**.
2. Digitare il nome della persona che si desidera invitare.
3. Fare clic su **Aggiungi**, quindi fare clic su **Chiudi**.

Per invitare gli ospiti a un team
1. Nel team, fare clic su **altre opzioni** ( **\*\*\*** ), quindi fare clic su **Aggiungi membro**.
2. Digitare l'indirizzo di posta elettronica dell'ospite che si desidera invitare.
3. Fare clic su **modifica informazioni Guest**.
4. Digitare il nome completo dell'ospite e fare clic sul segno di spunta.
5. Fare clic su **Aggiungi**, quindi fare clic su **Chiudi**.

## <a name="see-also"></a>Vedere anche

[Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](best-practices-anonymous-sharing.md)

[Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest](share-limit-accidental-exposure.md)

[Creare un ambiente di condivisione guest sicuro](create-secure-guest-sharing-environment.md)

[Creare una Extranet B2B con guest gestiti](b2b-extranet.md).

[Integrazione di SharePoint e OneDrive con Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[Le opzioni di condivisione sono ingrigiate quando si condivide da SharePoint o OneDrive](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
