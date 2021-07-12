---
title: Informazioni sulla conservazione per Yammer
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
description: Informazioni sui criteri di conservazione applicabili a Yammer.
ms.openlocfilehash: 1398bf385631967d92de760924ef94e2b3c16441
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362295"
---
# <a name="learn-about-retention-for-yammer"></a>Informazioni sulla conservazione per Yammer

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Questa funzionalità è in anteprima e soggetta a modifiche.

Questo articolo integra [Informazioni sulla conservazione](retention.md) con informazioni specifiche per Yammer.

Per altri carichi di lavoro, vedere:

- [Informazioni sulla conservazione per SharePoint e OneDrive](retention-policies-sharepoint.md)
- [Informazioni sulla conservazione per Microsoft Teams](retention-policies-teams.md)
- [Informazioni sulla conservazione per Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Cosa è incluso per la conservazione e l'eliminazione

Usando i criteri di conservazione per Yammer è possibile conservare ed eliminare gli elementi di Yammer seguenti: messaggi della community e messaggi utente.

Le reazioni degli altri utenti sotto forma di emoticon non sono incluse in questi messaggi.

## <a name="how-retention-works-with-yammer"></a>Funzionamento della conservazione per Yammer

Usare questa sezione per comprendere come i requisiti di conformità vengono soddisfatti dall'archiviazione e dai processi back-end e come questi devono essere verificati dagli strumenti di eDiscovery anziché dai messaggi attualmente visibili nell'app Yammer.

È possibile usare i criteri di conservazione per conservare i dati dei messaggi della community e dei messaggi utente in Yammer e per eliminare tali messaggi. Nel frattempo, le cassette postali di Exchange vengono usate per archiviare e i dati copiati di questi messaggi. I dati dei messaggi utente di Yammer sono archiviati in una cartella nascosta nella cassetta postale di ogni utente incluso nel messaggio dell'utente, mentre una cartella nascosta simile in una cassetta postale di gruppo viene usata per i messaggi della community.

Le copie dei messaggi della community possono anche essere archiviate nella cartella nascosta delle cassette postali degli utenti quando @ menzionano gli utenti o inviano una notifica all'utente di una risposta. Anche se questi messaggi hanno origine come messaggio della community, i criteri di conservazione per i messaggi utente di Yammer includono spesso copie dei messaggi della community.

Queste cartelle nascoste non sono progettate per essere direttamente accessibili agli utenti o agli amministratori, ma archiviano dati che gli amministratori di conformità possono cercare con gli strumenti di eDiscovery.

> [!IMPORTANT]
> Poiché le copie dei messaggi della community possono essere archiviate anche nelle cassette postali degli utenti, un criterio di conservazione con un'azione di eliminazione per i messaggi utente di Yammer può comportare che il messaggio originale della community non sia più visibile agli utenti nell'app Yammer.
> 
> Tuttavia, una copia del messaggio originale è ancora disponibile nella cartella nascosta della cassetta postale del gruppo della community e accessibile con le ricerche di eDiscovery per scopi di conformità.

I messaggi di Yammer non sono interessati dai criteri di conservazione configurati per le cassette postali di Exchange. Benché i messaggi di Yammer siano archiviati in Exchange, questi dati di Yammer vengono inclusi solo da un criterio di conservazione configurato per le posizioni **Messaggi della community di Yammer** e **Messaggi utente di Yammer**.

> [!NOTE]
> Se un utente è incluso in un criterio di conservazione attivo che conserva i dati di Yammer e si eliminata una cassetta postale di un utente incluso in tale criterio, per conservare i dati di Yammer la cassetta postale viene convertita in una [cassetta postale inattiva](inactive-mailboxes-in-office-365.md). Se non è necessario conservare i dati di Yammer per l'utente, escludere l'account utente dal criterio di conservazione prima di eliminare la relativa cassetta postale.

Dopo che i criteri di conservazione sono stati configurati per messaggi di Yammer, un processo timer del servizio Exchange valuterà periodicamente gli elementi nella cartella nascosta in cui vengono archiviati i messaggi di Yammer. Il processo timer richiede fino a sette giorni per l'esecuzione. Quando il periodo di conservazione degli elementi scade, questi vengono spostati nella cartella SubstrateHolds, una cartella nascosta presente in ogni cassetta postale utente o di gruppo in cui vengono archiviati gli elementi "eliminati temporaneamente" prima che vengano eliminati definitivamente.

> [!NOTE]
> In base al [primo principio di conservazione](retention.md#the-principles-of-retention-or-what-takes-precedence), l'eliminazione permanente viene sempre sospesa se lo stesso elemento deve essere conservato a causa di un altro criterio di conservazione oppure è sottoposto a blocchi di eDiscovery per motivi legali o di indagine.

Dopo la configurazione di un criterio di conservazione per i messaggi di Yammer, i percorsi del contenuto variano in base al fatto che il criterio di conservazione sia impostato per conservare e poi eliminare, conservare solo o eliminare solo.

Se il criterio di conservazione conserva e poi elimina:

![Diagramma del flusso di conservazione dei messaggi di Yammer](../media/yammerretentionlifecycle.png)

Per i due percorsi nel diagramma:

1. **Se un messaggio di Yammer viene modificato o eliminato** dall’utente durante il periodo di conservazione, il messaggio originale viene copiato (se è stato modificato) o spostato (se è stato eliminato) immediatamente nella cartella SubstrateHolds. Il messaggio viene archiviato in questa posizione fino alla scadenza del periodo di conservazione, quindi viene eliminato immediatamente in modo definitivo.

2. **Se il messaggio di Yammer non viene eliminato**, così come per i messaggi correnti dopo essere stati modificati, il messaggio viene spostato nella cartella SubstrateHolds alla scadenza del periodo di conservazione. Questa azione richiede fino a sette giorni dalla data di scadenza. Dopo che il messaggio è stato spostato nella cartella SubstrateHolds, viene eliminato immediatamente in modo definitivo. 

> [!NOTE]
> I messaggi nella cartella SubstrateHolds sono disponibili per la ricerca tramite gli strumenti di eDiscovery. Finché i messaggi non vengono eliminati definitivamente (nella cartella SubstrateHolds), rimangono disponibili per la ricerca tramite gli strumenti di eDiscovery.

Quando il criterio di conservazione è Conserva solo, o Elimina solo, i percorsi del contenuto sono varianti di Conserva ed Elimina.

### <a name="content-paths-for-retain-only-retention-policy"></a>Percorsi di contenuto per il criterio di conservazione Conserva solo

1. **Se un messaggio di Yammer viene modificato o eliminato**: una copia del messaggio originale viene immediatamente creata nella cartella SubstrateHolds e conservata in tale posizione fino alla scadenza del periodo di conservazione. Quindi il messaggio viene eliminato immediatamente in modo definitivo dalla cartella SubstrateHolds.

2. **Se il messaggio di Yammer non viene modificato o eliminato**, così come per i messaggi correnti dopo essere stati modificati durante il periodo di conservazione: non succede niente prima o dopo il periodo di conservazione. L'elemento rimane nella posizione originale.

### <a name="content-paths-for-delete-only-retention-policy"></a>Percorsi di contenuto per il criterio di conservazione Elimina solo

1. **Se il messaggio di Yammer non viene eliminato** durante il periodo di conservazione: alla fine del periodo di conservazione il messaggio viene spostato nella cartella SubstrateHolds. Questa azione richiede fino a sette giorni dalla data di scadenza. Quindi il messaggio viene eliminato immediatamente in modo definitivo dalla cartella SubstrateHolds.

2. **Se il messaggio di Yammer viene eliminato dall'utente** durante il periodo, verrà immediatamente spostato nella cartella SubstrateHolds da dove verrà immediatamente eliminato in modo definitivo.


## <a name="messages-and-external-users"></a>Messaggi e utenti esterni

Per impostazione predefinita, i criteri di conservazione dei messaggi utente di Yammer si applicano a tutti gli utenti dell'organizzazione, ma non agli utenti esterni. Si può applicare un'etichetta di conservazione a utenti esterni selezionando l’opzione **Modifica** per gli utenti inclusi e specificando il loro account.

Al momento, gli utenti guest di Azure B2B non sono supportati.

## <a name="when-a-user-leaves-the-organization"></a>Quando un utente abbandona l’organizzazione 

Se un utente lascia l’organizzazione e il suo account di Microsoft 365 viene eliminato, i suoi messaggi utente di Yammer soggetti alla conservazione vengono archiviati in una cassetta postale inattiva. I messaggi restano sottoposti ai criteri di conservazione applicati all’utente prima della disattivazione della sua cassetta postale, e sono disponibili per la ricerca eDiscovery. Per altre informazioni, vedere [Cassette postali inattive in Exchange Online](inactive-mailboxes-in-office-365.md). 

Se l’utente ha archiviato dei file in Yammer, vedere la [sezione corrispondente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) per SharePoint e OneDrive.

## <a name="limitations"></a>Limitazioni

I criteri di conservazione di Yammer sono attualmente in anteprima, e stiamo lavorando continuamente all'ottimizzazione della funzionalità di conservazione. Nel frattempo, notare le limitazioni seguenti quando si usa la conservazione per i messaggi della community e i messaggi utente di Yammer:

- Quando si seleziona **Modifica** per la posizione **Messaggi utente di Yammer**, potrebbero essere visualizzati utenti non della cassetta postale e guest. I criteri di conservazione non sono pensati per questi utenti, quindi non selezionarli.

## <a name="configuration-guidance"></a>Linee guida per la configurazione

Se si configura per la prima volta la conservazione in Microsoft 365, vedere [Informazioni sui criteri e sulle etichette di conservazione](get-started-with-retention.md).

Se si è pronti per configurare un criterio di conservazione per Yammer, vedere [Creare e configurare criteri di conservazione](create-retention-policies.md).