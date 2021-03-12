---
title: Informazioni sulla conservazione per Teams
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Informazioni sui criteri di conservazione applicabili a Microsoft Teams.
ms.openlocfilehash: 4296924684e13e163f28e0f952b2cd380cdcc047
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712012"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Informazioni sulla conservazione per Microsoft Teams

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

> [!NOTE]
> Se viene visualizzato un messaggio in Teams che indica che le chat o i messaggi sono stati eliminati da un criterio di conservazione, vedere [Messaggi di Teams sui criteri di conservazione](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> Le informazioni fornite in questa pagina sono riservate agli amministratori IT che gestiscono questi criteri di conservazione.

Questo articolo integra [Informazioni sulla conservazione](retention.md) con informazioni specifiche per i messaggi di Microsoft Teams.

Per altri carichi di lavoro, vedere:

- [Informazioni sulla conservazione per SharePoint e OneDrive](retention-policies-sharepoint.md)
- [Informazioni sulla conservazione per Yammer](retention-policies-yammer.md)
- [Informazioni sulla conservazione per Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Cosa è incluso per la conservazione e l'eliminazione

Usando i criteri di conservazione per Teams è possibile conservare ed eliminare gli elementi di Teams seguenti: messaggi di chat e canali, inclusi immagini incorporate, tabelle, collegamenti ipertestuali e collegamenti ad altri messaggi e file di Teams, nonché il [contenuto della scheda](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards). Nei messaggi di chat sono inclusi tutti i nomi degli utenti presenti in chat e nei messaggi dei canali sono inclusi il nome del team e il titolo del messaggio (se disponibile). 

> [!NOTE]
> L'inclusione del contenuto della scheda è un'aggiunta recente ed è attualmente in fase di distribuzione ai tenant. Per altre informazioni vedere [Funzionalità di conformità di Microsoft 365 ora disponibili per il contenuto delle schede adattive tramite le app in Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869).

I messaggi Teams nei canali privati non sono attualmente supportati per i criteri di conservazione. Quando si usano i criteri di conservazione per Teams, non vengono inclusi frammenti di codice, memo vocali registrati dal client per dispositivi mobili di Teams, anteprime, immagini di annunci e reazioni di altri utenti sotto forma di emoticon.

I messaggi di posta elettronica e i file usati con Teams non sono inclusi nei criteri di conservazione per Teams. Questi elementi hanno criteri di conservazione personalizzati.

## <a name="how-retention-works-with-microsoft-teams"></a>Come funziona la conservazione dei dati in Microsoft Teams

È possibile usare i criteri di conservazione per conservare e cancellare dati dai messaggi di chat e canali in Teams. Dietro le quinte, le cassette postali di Exchange vengono usate per archiviare questi messaggi. I dati delle chat di Teams sono archiviati in una cartella nascosta nella cassetta postale di ogni utente della chat, mentre una cartella nascosta simile in una cassetta postale di gruppo viene usata per i messaggi dei canali di Teams.

Queste cassette postali sono elencate dall'attributo RecipientTypeDetails:

- **MailUser**: queste cassette postali archiviano i messaggi per gli utenti di Teams basati sul cloud.
- **UserMailbox**: queste cassette postali archiviano i messaggi per gli [utenti di Teams locali](search-cloud-based-mailboxes-for-on-premises-users.md).
- **GroupMailbox**: queste cassette postali archiviano i messaggi per i canali di Teams.

Altri tipi di cassette postali, ad esempio RoomMailbox usato per le sale riunioni di Teams, non sono supportati per i criteri di conservazione di Teams.

È importante sapere che Teams usa un servizio di chat con tecnologia Azure che archivia anche questi dati e che, per impostazione predefinita, questo servizio archivia i dati a tempo indeterminato. Per questo motivo, se bisogna cancellare i messaggi di Teams per motivi di conformità, raccomandiamo di usare criteri di conservazione di Teams che siano in grado di cancellare definitivamente questi dati sia dalle cassette postali di Exchange che dal servizio di chat sottostante basato su Azure. Per altre informazioni sull'architettura sottostante, vedere [Sicurezza e conformità in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258) e in particolare la sezione [Architettura di protezione delle informazioni](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Anche se i messaggi di chat e canali di Teams vengono archiviati nelle cassette postali, questi dati vengono inclusi solo da un criterio di conservazione configurato per le posizioni **Messaggi del canale di Teams** e **Chat di Teams**. I messaggi di chat e canali di Teams non sono interessati dai criteri di conservazione configurati per le cassette postali di utenti o gruppi di Exchange.

> [!NOTE]
> Se un utente è incluso in un criterio di conservazione attivo che conserva i dati di Teams e si eliminata una cassetta postale di un utente incluso in tale criterio, per conservare i dati di Teams la cassetta postale viene convertita in una [cassetta postale inattiva](inactive-mailboxes-in-office-365.md). Se non è necessario conservare i dati di Teams per l'utente, escludere l'account utente dal criterio di conservazione prima di eliminare la relativa cassetta postale.

Dopo che i criteri di conservazione sono stati configurati per messaggi di chat e canali, un processo timer del servizio Exchange valuterà periodicamente gli elementi nella cartella nascosta in cui vengono archiviati i messaggi di Teams. Il processo timer richiede fino a sette giorni per l'esecuzione. Quando il periodo di conservazione degli elementi scade, questi vengono spostati nella cartella SubstrateHolds, un'altra cartella nascosta presente in ogni cassetta postale utente o di gruppo in cui vengono archiviati gli elementi "eliminati temporaneamente" prima che vengano eliminati definitivamente.

Dopo la configurazione di un criterio di conservazione per i messaggi di chat e canali, i percorsi del contenuto variano in base al fatto che il criterio di conservazione sia impostato per conservare e poi eliminare, conservare solo o eliminare solo.

Se il criterio di conservazione conserva e poi elimina:

![Diagramma del flusso di conservazione per messaggi di chat e canali di Teams](../media/teamsretentionlifecycle.png)

Per i due percorsi nel diagramma:

1. **Se un messaggio della chat o del canale viene modificato o eliminato** dall’utente durante il periodo di conservazione, il messaggio originale viene copiato (se è stato modificato) o spostato (se è stato eliminato) entro 21 giorni nella cartella SubstrateHolds. Il messaggio viene archiviato in questa posizione fino alla scadenza del periodo di conservazione, quindi viene eliminato definitivamente entro 24 ore.

2. **Se il messaggio di una chat o un canale non viene eliminato**, così come per i messaggi correnti dopo essere stati modificati, il messaggio viene spostato nella cartella SubstrateHolds alla scadenza del periodo di conservazione. Questa azione richiede fino a sette giorni dalla data di scadenza. Dopo che il messaggio è stato spostato nella cartella SubstrateHolds, viene eliminato definitivamente entro 24 ore. 

> [!NOTE]
> I messaggi nella cartella SubstrateHolds sono disponibili per la ricerca tramite gli strumenti di eDiscovery. Finché i messaggi non vengono eliminati definitivamente dalla cartella SubstrateHolds, rimangono disponibili per la ricerca tramite gli strumenti di eDiscovery.

Quando il criterio di conservazione è Conserva solo, o Elimina solo, i percorsi del contenuto sono varianti di Conserva ed Elimina.

### <a name="content-paths-for-retain-only-retention-policy"></a>Percorsi di contenuto per il criterio di conservazione Conserva solo

1. **Se un messaggio della chat o del canale viene modificato o eliminato**: una copia del messaggio originale viene creata nella cartella SubstrateHolds entro 21 giorni e conservata in tale posizione fino alla scadenza del periodo di conservazione. Quindi il messaggio viene eliminato definitivamente dalla cartella SubstrateHolds entro 24 ore.

2. **Se l'elemento non viene modificato o eliminato**, così come per i messaggi correnti dopo essere stati modificati durante il periodo di conservazione: non succede niente prima o dopo il periodo di conservazione. L'elemento rimane nella posizione originale.

### <a name="content-paths-for-delete-only-retention-policy"></a>Percorsi di contenuto per il criterio di conservazione Elimina solo

1. **Se il messaggio non viene eliminato** durante il periodo di conservazione: alla fine del periodo di conservazione il messaggio viene spostato nella cartella SubstrateHolds. Questa azione richiede fino a sette giorni dalla data di scadenza. Quindi il messaggio viene eliminato definitivamente dalla cartella SubstrateHolds entro 24 ore.

2. **Se l'elemento viene eliminato dall'utente** durante il periodo, verrà spostato entro 21 giorni nella cartella SubstrateHolds, da dove verrà eliminato definitivamente entro 24 ore.


## <a name="skype-for-business-and-teams-interop-chats"></a>Chat di interoperabilità di Skype for Business e Teams.

Quando una chat di Skype for Business viene spostata in Teams, diventa un messaggio in un thread di chat di Teams e viene inserita nella cassetta postale appropriata. I criteri di conservazione di Teams verranno applicati a questi messaggi dal thread di Teams. 

Tuttavia, se la cronologia delle conversazioni è abilitata per Skype for Business e dal lato client di Skype for Business questa cronologia viene salvata in una cassetta postale, i dati della chat non vengono gestiti dai criteri di conservazione di Teams. Per questo contenuto, usare un criterio di conservazione configurato per Skype for Business.

## <a name="meetings-and-external-users"></a>Riunioni e utenti esterni

I messaggi delle riunioni di canale vengono archiviati allo stesso modo dei messaggi di canale, quindi per questi dati selezionare il percorso **Messaggi del canale di Teams** quando si configura il criterio di conservazione.

I messaggi delle riunioni estemporanee e pianificate vengono archiviati allo stesso modo dei messaggi delle chat di gruppo, quindi per questi dati selezionare il percorso **Chat di Teams** quando si configura il criterio di conservazione.

Quando in una riunione ospitata dall'organizzazione vengono inclusi utenti esterni:

- Se un utente esterno partecipa con un account guest nel tenant dell'organizzazione, l'utente ha una cassetta postale shadow che può essere soggetta ai criteri di conservazione dell'organizzazione per Teams. I messaggi della riunione vengono archiviati sia nella cassetta postale degli utenti che nella cassetta postale shadow. 

- Se un utente esterno partecipa usando un account di un'altra organizzazione di Microsoft 365, i criteri di conservazione non possono eliminare i messaggi per l'utente, perché sono archiviati nella sua cassetta postale in un altro tenant. Per la stessa riunione, tuttavia, i criteri di conservazione configurati possono eliminare i messaggi per gli utenti interni dell'organizzazione.

## <a name="when-a-user-leaves-the-organization"></a>Quando un utente abbandona l’organizzazione 

Se un utente che dispone di una cassetta postale in Exchange Online lascia l’organizzazione e il suo account di Microsoft 365 viene eliminato, i suoi messaggi della chat soggetti alla conservazione vengono archiviati in una cassetta postale inattiva. I messaggi di chat restano sottoposti ai criteri di conservazione applicati all’utente prima della disattivazione della sua cassetta postale, e sono disponibili per la ricerca eDiscovery. Per altre informazioni, vedere [Cassette postali inattive in Exchange Online](inactive-mailboxes-in-office-365.md). 

Se l’utente ha archiviato dei file in Teams, vedere la sezione [corrispondente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) per SharePoint e OneDrive.

## <a name="limitations"></a>Limitazioni

Lavoriamo costantemente all'ottimizzazione della funzionalità di conservazione in Teams. Nel frattempo, di seguito sono riportate alcune limitazioni da tenere presenti quando si usa la conservazione per le chat e i messaggi dei canali di Teams:

- **Problema di visualizzazione non corretta in Outlook**. Se si creano criteri di conservazione per i percorsi di Skype o Teams, uno di questi criteri viene visualizzato come criterio cartella predefinito quando un utente visualizza le proprietà di una cartella della cassetta postale nel client desktop di Outlook. Si tratta di un problema di visualizzazione non corretta in Outlook e di un [problema noto](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). Quello che dovrebbe essere visualizzato come criterio cartella predefinito è il criterio di conservazione della cassetta postale applicato alla cartella. Il criterio di conservazione di Skype o Teams non viene applicato alla cassetta postale dell'utente.

- **Problemi di configurazione**: 
    - Quando si seleziona **Scegli i team** per il percorso **Messaggi del canale di Teams**, potrebbero essere visualizzati gruppi di Microsoft 365 che non corrispondono anche a team. Non selezionare questi gruppi.
    
    - Quando si seleziona **Scegli utenti** per la posizione **Chat di Teams**, potrebbero essere visualizzati utenti non della cassetta postale e guest. I criteri di conservazione non sono pensati per questi utenti, quindi non selezionarli.

## <a name="configuration-guidance"></a>Linee guida per la configurazione

Se si configura per la prima volta la conservazione in Microsoft 365, vedere [Informazioni sui criteri e sulle etichette di conservazione](get-started-with-retention.md).

Se si è pronti per configurare un criterio di conservazione, vedere [Creare e configurare criteri di conservazione](create-retention-policies.md).
