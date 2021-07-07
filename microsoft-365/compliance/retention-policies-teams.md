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
ms.openlocfilehash: 5d888232d94ccd6634fc6102c26958e20d88fb4d
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322402"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Informazioni sulla conservazione per Microsoft Teams

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

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

Usando i criteri di conservazione per Teams è possibile eliminare i messaggi di chat e i messaggi di canale di Teams. Per motivi di conformità è possibile conservare, oltre al testo nei messaggi, i seguenti elementi: immagini incorporate, tabelle, collegamenti ipertestuali e collegamenti ad altri messaggi e file di Teams nonché il [contenuto della scheda](/microsoftteams/platform/task-modules-and-cards/what-are-cards). Nei messaggi di chat sono inclusi tutti i nomi degli utenti presenti in chat e nei messaggi dei canali sono inclusi il nome del team e il titolo del messaggio (se disponibile). 
> [!NOTE]
> Il supporto per i messaggi nei canali privati è attualmente in fase di implementazione in anteprima.

Quando si usano i criteri di conservazione per Teams, non vengono conservati frammenti di codice, memo vocali registrati dal client per dispositivi mobili di Teams, anteprime, immagini di annunci e reazioni di altri utenti sotto forma di emoticon.

I messaggi di posta elettronica e i file usati con Teams non sono inclusi nei criteri di conservazione per Teams. Questi elementi hanno i propri criteri di conservazione.

## <a name="how-retention-works-with-microsoft-teams"></a>Come funziona la conservazione in Microsoft Teams

Usare questa sezione per comprendere come i requisiti di conformità vengono soddisfatti dall'archiviazione e dai processi back-end e come questi devono essere verificati dagli strumenti di eDiscovery anziché dai messaggi attualmente visibili nell'app Teams.

È possibile usare i criteri di conservazione per conservare i dati delle chat e dei messaggi di canale in Teams e per eliminare tali chat e messaggi. Nel frattempo, le cassette postali di Exchange vengono usate per archiviare e i dati copiati di questi messaggi. I dati delle chat di Teams sono archiviati in una cartella nascosta nella cassetta postale di ogni utente della chat, mentre una cartella nascosta simile in una cassetta postale di gruppo viene usata per i messaggi dei canali di Teams. Queste cartelle nascoste non sono progettate per essere direttamente accessibili agli utenti o agli amministratori, ma archiviano dati che gli amministratori di conformità possono cercare con gli strumenti di eDiscovery.

Queste cassette postali sono elencate dall'attributo RecipientTypeDetails:

- **UserMailbox**: queste cassette postali archiviano i dati dei messaggi per gli utenti di Teams basati sul cloud.
- **MailUser**: queste cassette postali archiviano i dati dei messaggi per gli [utenti di Teams locali](search-cloud-based-mailboxes-for-on-premises-users.md).
- **GroupMailbox**: queste cassette postali archiviano i dati dei messaggi per i canali standard di Teams.

Altri tipi di cassette postali, ad esempio RoomMailbox usato per le sale riunioni di Teams, non sono supportati per i criteri di conservazione di Teams.

Teams usa un servizio di chat con tecnologia Azure come risorsa di archiviazione principale per tutti i messaggi (chat e messaggi di canale). Se è necessario eliminare i messaggi di Teams per motivi di conformità, i criteri di conservazione per Teams possono eliminare i messaggi dopo un periodo specifico, in base a quando alla data di creazione. I messaggi vengono eliminati definitivamente dalle cassette postali di Exchange in cui sono stati archiviati per le operazioni di conformità e dall'archiviazione primaria usata dal servizio di chat sottostante basato su Azure. Per altre informazioni sull'architettura sottostante, vedere [Sicurezza e conformità in Microsoft Teams](/MicrosoftTeams/security-compliance-overview) e in particolare la sezione [Architettura di protezione delle informazioni](/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Anche se i dati delle chat e dei messaggi di canale di Teams vengono archiviati nelle cassette postali, è necessario configurare un criterio di conservazione per le posizioni dei **messaggi del canale di Teams** e delle **chat di Teams**. Le chat e i messaggi di canale di Teams non sono inclusi nei criteri di conservazione configurati per le cassette postali di utenti o gruppi di Exchange.

> [!NOTE]
> Se un utente è incluso in un criterio di conservazione attivo che conserva i messaggi di Teams ed elimini una cassetta postale di un utente incluso in tale criterio, per conservare i dati di Teams la cassetta postale viene convertita in una [cassetta postale inattiva](inactive-mailboxes-in-office-365.md). Se non è necessario conservare i dati di Teams per l'utente, escludere l'account utente dal criterio di conservazione prima di eliminare la relativa cassetta postale.

Dopo che i criteri di conservazione sono stati configurati per messaggi di chat e canali, un processo timer del servizio Exchange valuterà periodicamente gli elementi nella cartella nascosta in cui vengono archiviati i messaggi di Teams. L'esecuzione del processo timer richiede in genere da 1 a 7 giorni. Quando il periodo di conservazione degli elementi scade, questi vengono spostati nella cartella SubstrateHolds, un'altra cartella nascosta presente in ogni cassetta postale utente o di gruppo in cui vengono archiviati gli elementi "eliminati temporaneamente" prima che vengano eliminati definitivamente. 

I messaggi rimangono nella cartella SubstrateHolds per almeno 1 giorno, quindi se sono idonei per l'eliminazione, il processo timer li elimina definitivamente alla successiva esecuzione.

> [!NOTE]
> In base al [primo principio di conservazione](retention.md#the-principles-of-retention-or-what-takes-precedence), l'eliminazione permanente viene sempre sospesa se lo stesso elemento deve essere conservato a causa di un altro criterio di conservazione oppure è sottoposto a blocchi di eDiscovery per motivi legali o di indagine.

Dopo la configurazione di un criterio di conservazione per i messaggi di chat e canali, i percorsi del contenuto variano in base al fatto che il criterio di conservazione sia impostato per conservare e poi eliminare, conservare solo o eliminare solo.

Se il criterio di conservazione conserva e poi elimina:

![Diagramma del flusso di conservazione per messaggi di chat e canali di Teams](../media/teamsretentionlifecycle.png)

Per i due percorsi nel diagramma:

1. **Se un messaggio della chat o del canale viene modificato o eliminato** da un utente durante il periodo di conservazione, il messaggio originale viene copiato (se è stato modificato) o spostato (se è stato eliminato) entro 21 giorni nella cartella SubstrateHolds. Il messaggio viene archiviato per almeno 1 giorno. Alla scadenza del periodo di conservazione, il messaggio viene eliminato definitivamente alla successiva esecuzione del processo timer, in genere da 1 a 7 giorni.

2. **Se il messaggio di una chat o un canale non viene eliminato** da un utente, così come per i messaggi correnti dopo essere stati modificati, il messaggio viene spostato nella cartella SubstrateHolds alla scadenza del periodo di conservazione. Questa azione richiede in genere da 1 a 7 giorni dalla data di scadenza. Quando il messaggio si trova nella cartella SubstrateHolds, viene archiviato in questa cartella per almeno 1 giorno e quindi viene eliminato definitivamente alla successiva esecuzione del processo timer, in genere da 1 a 7 giorni. 

> [!NOTE]
> Gli strumenti di eDiscovery consentono di eseguire ricerche nei messaggi archiviati nelle cassette postali, incluse le cartelle nascoste. Finché i messaggi non vengono eliminati definitivamente dalla cartella SubstrateHolds, rimangono disponibili per la ricerca tramite gli strumenti di eDiscovery.

Quando i messaggi vengono eliminati definitivamente dalla cartella SubstrateHolds, viene comunicata un'operazione di eliminazione al servizio chat di Azure back-end, che inoltra la stessa operazione all'app client Teams. I ritardi nella comunicazione o nella memorizzazione nella cache possono spiegare perché, per un breve periodo di tempo, gli utenti potrebbero ancora vedere questi messaggi nell'app Teams, ma i dati di questi messaggi non vengono restituiti nelle ricerche di eDiscovery. I messaggi visibili nell'app Teams non riflettono accuratamente se vengono conservati o eliminati definitivamente per i requisiti di conformità.

Quando il criterio di conservazione è Conserva solo, o Elimina solo, i percorsi del contenuto sono varianti di Conserva ed Elimina.

### <a name="content-paths-for-retain-only-retention-policy"></a>Percorsi di contenuto per il criterio di conservazione Conserva solo

1. **Se un messaggio della chat o del canale viene modificato o eliminato** da un utente durante il periodo di conservazione: il messaggio originale viene copiato (se è stato modificato) o spostato (se è stato eliminato) entro 21 giorni nella cartella SubstrateHolds. Se i criteri di conservazione sono configurati per conservarsi in modo permanente, l'elemento rimane in questa cartella. Se il criterio di conservazione ha una data di fine per il periodo di conservazione e scade, il messaggio viene eliminato definitivamente la prossima volta che viene eseguito il processo timer (in genere da 1 a 7 giorni).

2. **Se il messaggio della chat o del canale non viene modificato o eliminato** da un utente così come per i messaggi correnti dopo la modifica durante il periodo di conservazione: non accade nulla prima e dopo il periodo di conservazione. Il messaggio rimane nella posizione originale.

### <a name="content-paths-for-delete-only-retention-policy"></a>Percorsi di contenuto per il criterio di conservazione Elimina solo

1. **Se il messaggio della chat o del canale viene modificato o eliminato** da un utente durante il periodo di conservazione: il messaggio originale viene copiato (se è stato modificato) o spostato (se è stato eliminato) entro 21 giorni nella cartella SubstrateHolds. Il messaggio viene conservato in tale posizione per almeno 1 giorno ed eliminato definitivamente la volta successiva in cui viene eseguito il processo timer (in genere da 1 a 7 giorni).

2. **Se un messaggio di chat o di canale non viene eliminato** da un utente durante il periodo di conservazione: alla fine del periodo di conservazione il messaggio viene spostato nella cartella SubstrateHolds. Questa azione richiede in genere da 1 a 7 giorni dalla data di scadenza. Il messaggio viene conservato in tale posizione per almeno 1 giorno ed eliminato definitivamente la volta successiva in cui viene eseguito il processo timer (in genere da 1 a 7 giorni).

#### <a name="example-flows-and-timings-for-retention-policies"></a>Esempi di flussi e tempi per i criteri di conservazione

Usare gli esempi seguenti per vedere in che modo i processi e i tempi spiegati nelle sezioni precedenti si applicano ai criteri di conservazione con le seguenti configurazioni:

- [Esempio 1: Conservare solo per 7 anni](#example-1-retain-only-for-7-years)
- [Esempio 2: Conservare per 30 giorni e quindi eliminarlo](#example-2-retain-for-30-days-and-then-delete)
- [Esempio 3: Eliminare solo dopo 1 giorno](#example-3-delete-only-after-1-day)

Per tutti gli esempi che fanno riferimento all'eliminazione permanente, a causa dei [principi di conservazione](retention.md#the-principles-of-retention-or-what-takes-precedence), questa azione viene sospesa se il messaggio è soggetto a un altro criterio di conservazione per conservare l'elemento o è soggetto a un blocco eDiscovery.

##### <a name="example-1-retain-only-for-7-years"></a>Esempio 1: Conservare solo per 7 anni

Il primo giorno un utente crea un messaggio di chat o di canale.

Il quinto giorno l'utente modifica il messaggio.

Il trentesimo giorno l'utente elimina il messaggio corrente.

Risultati della conservazione:

- Per il messaggio originale:
    - Il quinto giorno il messaggio viene copiato nella cartella SubstrateHolds, in cui è possibile eseguire ricerche con gli strumenti di eDiscovery per almeno 7 anni dal primo giorno (il periodo di conservazione).

- Per il messaggio corrente (modificato):
    - Il trentesimo giorno il messaggio viene trasferito nella cartella SubstrateHolds, in cui è possibile eseguire ricerche con gli strumenti di eDiscovery per almeno 7 anni dal primo giorno (il periodo di conservazione).

Se l'utente ha eliminato il messaggio corrente dopo il periodo di conservazione specificato, anziché entro il periodo di conservazione, il messaggio verrà comunque spostato nella cartella SubstrateHolds. Tuttavia, dopo che il periodo di conservazione è scaduto, il messaggio verrà eliminato definitivamente dopo un minimo di 1 giorno e in genere da 1 a 7 giorni.

##### <a name="example-2-retain-for-30-days-and-then-delete"></a>Esempio 2: Conservare per 30 giorni e quindi eliminarlo

Il primo giorno un utente crea un messaggio di chat o di canale.

Il decimo giorno l'utente modifica il messaggio.

L'utente non apporta altre modifiche e non elimina il messaggio.

Risultati della conservazione:

- Per il messaggio originale:
    - Il decimo giorno il messaggio viene copiato nella cartella SubstrateHolds, in cui è possibile eseguire ricerche con gli strumenti di eDiscovery.
    - Alla fine del periodo di conservazione (30 giorni dal primo giorno), il messaggio viene eliminato definitivamente in genere entro 1-7 giorni dopo un minimo di 1 giorno e quindi non viene restituito con le ricerche di eDiscovery.

- Per il messaggio corrente (modificato):
    - Alla fine del periodo di conservazione (30 giorni dal primo giorno), il messaggio viene spostato nella cartella SubstrateHolds in genere entro 1-7 giorni, dove può ancora essere cercato con gli strumenti di eDiscovery.
    - Quindi, il messaggio viene eliminato definitivamente in genere entro 1-7 giorni dopo un minimo di 1 giorno e quindi non viene restituito con le ricerche di eDiscovery.

##### <a name="example-3-delete-only-after-1-day"></a>Esempio 3: Eliminare solo dopo 1 giorno

> [!NOTE]
> A causa della breve durata di questa configurazione, un giorno, e dei processi di conservazione che operano in un periodo di tempo compreso tra 1 e 7 giorni, questa sezione mostra intervalli di tempo di esempio che rientrano negli intervalli di tempo tipici.

Il primo giorno un utente crea un messaggio di chat o di canale.

Esempio di risultato di conservazione se l'utente non modifica o elimina il messaggio:

- Quinto giorno (in genere 1-7 giorni dopo l'inizio del periodo di conservazione il secondo giorno):
    - Il messaggio viene spostato nella cartella SubstrateHolds dove può ancora essere cercato con gli strumenti di eDiscovery e vi rimane per almeno 1 giorno.

- Nono giorno (in genere 1-7 giorni dopo un minimo di 1 giorno nella cartella SubstrateHolds):
    - Il messaggio viene eliminato definitivamente e quindi non viene restituito con le ricerche di eDiscovery.

Come illustrato in questo esempio, anche se è possibile configurare criteri di conservazione per eliminare i messaggi dopo un solo giorno, il servizio viene sottoposto a più processi per garantire un'eliminazione conforme. Di conseguenza, un'azione di eliminazione dopo 1 giorno potrebbe richiedere 16 giorni prima che il messaggio venga eliminato definitivamente in modo che non venga più restituito nelle ricerche di eDiscovery.

## <a name="skype-for-business-and-teams-interop-chats"></a>Chat di interoperabilità di Skype for Business e Teams.

Quando una chat di Skype for Business viene spostata in Teams, diventa un messaggio in un thread di chat di Teams e viene inserita nella cassetta postale appropriata. I criteri di conservazione di Teams verranno applicati a questi messaggi dal thread di Teams. 

Tuttavia, se la cronologia delle conversazioni è abilitata per Skype for Business e dal lato client di Skype for Business questa cronologia viene salvata in una cassetta postale, i dati della chat non vengono gestiti dai criteri di conservazione di Teams. Per questo contenuto, usare un criterio di conservazione configurato per Skype for Business.

## <a name="meetings-and-external-users"></a>Riunioni e utenti esterni

I messaggi delle riunioni di canale vengono archiviati allo stesso modo dei messaggi di canale, quindi per questi dati selezionare il percorso **Messaggi del canale di Teams** quando si configura il criterio di conservazione.

I messaggi delle riunioni estemporanee e pianificate vengono archiviati allo stesso modo dei messaggi delle chat di gruppo, quindi per questi dati selezionare il percorso **Chat di Teams** quando si configura il criterio di conservazione.

Quando in una riunione ospitata dall'organizzazione vengono inclusi utenti esterni:

- Se un utente esterno partecipa con un account guest nel tenant dell'organizzazione, l'utente ha una cassetta postale shadow che può essere soggetta ai criteri di conservazione dell'organizzazione per Teams. I messaggi della riunione vengono archiviati sia nella cassetta postale degli utenti che nella cassetta postale shadow. 

- Se un utente esterno partecipa usando un account di un'altra organizzazione di Microsoft 365, i criteri di conservazione non possono eliminare i messaggi per l'utente, perché sono archiviati nella sua cassetta postale in un altro tenant. Tuttavia, per la stessa riunione, i criteri di conservazione possono eliminare i messaggi per gli utenti.

## <a name="when-a-user-leaves-the-organization"></a>Quando un utente abbandona l’organizzazione 

Se un utente che dispone di una cassetta postale in Exchange Online lascia l’organizzazione e il suo account di Microsoft 365 viene eliminato, i suoi messaggi della chat soggetti alla conservazione vengono archiviati in una cassetta postale inattiva. I messaggi di chat restano sottoposti ai criteri di conservazione applicati all’utente prima della disattivazione della sua cassetta postale, e sono disponibili per la ricerca eDiscovery. Per altre informazioni, vedere [Cassette postali inattive in Exchange Online](inactive-mailboxes-in-office-365.md). 

Se l’utente ha archiviato dei file in Teams, vedere la sezione [corrispondente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) per SharePoint e OneDrive.

## <a name="configuration-guidance"></a>Linee guida per la configurazione

Se si configura per la prima volta la conservazione in Microsoft 365, vedere [Informazioni sui criteri e sulle etichette di conservazione](get-started-with-retention.md).

Se si è pronti per configurare un criterio di conservazione, vedere [Creare e configurare criteri di conservazione](create-retention-policies.md).