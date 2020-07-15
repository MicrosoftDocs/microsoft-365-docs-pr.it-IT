---
title: Disposizione del contenuto
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Monitorare e gestire lo smaltimento del contenuto, sia che si utilizzi una recensione di disposizione o che il contenuto venga eliminato automaticamente in base alle impostazioni configurate.
ms.openlocfilehash: 5c8c8c4e99edbc32bbca4b3efbe79325f53a3380
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127013"
---
# <a name="disposition-of-content"></a>Disposizione del contenuto

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Utilizzare la scheda **disposizione** dalla **gestione dei record** nel centro conformità di Microsoft 365 per gestire le revisioni di disposizione e visualizzare i [record](records.md) eliminati automaticamente alla fine del periodo di conservazione. 

## <a name="prerequisites-for-viewing-content-dispositions"></a>Prerequisiti per la visualizzazione di disposizioni di contenuto

Per gestire le recensioni sulla disposizione e verificare che i record siano stati eliminati, è necessario disporre di autorizzazioni e controllo sufficienti.

### <a name="permissions-for-disposition"></a>Autorizzazioni per la disposizione

Per accedere correttamente alla scheda **disposizione** nel centro conformità di Microsoft 365, è necessario che gli utenti dispongano del ruolo **gestione disposizione** e del ruolo di **controllo di sola visualizzazione** . Anche se il Consiglio standard consiste nell'aggiungere utenti ai gruppi di ruoli predefiniti, in questo caso, è consigliabile creare un nuovo gruppo di ruoli denominato **reviewers Disposition** con questi due ruoli e aggiungere gli utenti a questo gruppo in base alle esigenze. Un singolo gruppo di ruoli per la disposizione consente di ridurre le spese generali di amministrazione e rende più semplice per gli utenti le autorizzazioni combinate di cui hanno bisogno.

> [!NOTE]
> Anche a un amministratore globale deve essere concesso il ruolo di **gestione della disposizione** . Pertanto, se gli amministratori globali devono accedere alla scheda disposizione, come membri del gruppo di ruolo **revisori disposizione** . 

Specifica del ruolo di **controllo di sola visualizzazione** :

- Poiché il cmdlet sottostante utilizzato per eseguire la ricerca nel log di controllo è un cmdlet di Exchange Online, è necessario assegnare agli utenti questo ruolo utilizzando l'interfaccia di [amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), anziché utilizzando la pagina **autorizzazioni** nel centro sicurezza & conformità. Per istruzioni, vedere [gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- I gruppi Microsoft 365 (in[precedenza gruppi di Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) non sono supportati per questo ruolo. Assegnare invece le cassette postali utente, gli utenti di posta elettronica o i gruppi di sicurezza abilitati alla posta elettronica.

Per istruzioni su come concedere agli utenti il ruolo di **gestione della disposizione** e creare il nuovo ruolo **revisori disposizione** , vedere [fornire agli utenti l'accesso al centro sicurezza e &amp; conformità di Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

### <a name="enable-auditing"></a>Abilitazione del controllo

Verificare che il controllo sia abilitato almeno un giorno prima della prima azione di eliminazione. Per ulteriori informazioni, vedere [eseguire la ricerca nel log di controllo nel centro sicurezza e &amp; conformità di Office 365](search-the-audit-log-in-security-and-compliance.md). 

## <a name="disposition-reviews"></a>Revisioni per l'eliminazione

Quando il contenuto raggiunge la fine del periodo di conservazione, è possibile che si desideri rivedere il contenuto per decidere se può essere eliminato in modo sicuro ("Disposed"). Ad esempio, potrebbe essere necessario:
  
- Sospendere l'eliminazione del contenuto pertinente in caso di controversia legale o di controllo.
    
- Rimuovere il contenuto dall'elenco di disposizione per archiviarlo in un archivio, se il contenuto ha una ricerca o un valore cronologico.
    
- Assegnare un periodo di conservazione diverso al contenuto, probabilmente perché le impostazioni di conservazione originali erano una soluzione temporanea o provvisoria.
    
- Restituire il contenuto ai client o trasferirlo in un'altra organizzazione.

Quando viene attivata una revisione della disposizione alla fine del periodo di conservazione:
  
- Gli utenti che scelgono ricevono una notifica tramite posta elettronica che dispongono di contenuto da esaminare. Questi revisori possono essere singoli utenti, gruppi di distribuzione o di sicurezza o gruppi Microsoft 365 (in[precedenza gruppi di Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)). Si noti che le notifiche vengono inviate su base settimanale.
    
- I revisori passano alla scheda **disposizione** del centro conformità Microsoft 365 per esaminare il contenuto e decidere se eliminarlo definitivamente, estenderne il periodo di conservazione o applicare un'etichetta di conservazione diversa.

Una recensione di disposizione può includere il contenuto nelle cassette postali di Exchange, siti di SharePoint, account di OneDrive e gruppi Microsoft 365. Il contenuto in attesa di una revisione della disposizione in tali posizioni viene eliminato solo dopo che un revisore sceglie di eliminare definitivamente il contenuto.

> [!NOTE]
> Una cassetta postale deve disporre di almeno 10 MB di dati per il supporto delle recensioni sulla disposizione.

È possibile visualizzare una panoramica di tutte le disposizioni in sospeso nella scheda **Panoramica** . Per esempio:

![Disposizioni in sospeso nella panoramica della gestione dei record](../media/dispositions-overview.png)

Quando si seleziona la **visualizzazione tutte le disposizioni in sospeso**, viene visualizzata la pagina **disposizione** . Ad esempio:

![Pagina disposizioni in Microsoft 365 Compliance Center](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a>Flusso di lavoro per una revisione della disposizione

Nel diagramma seguente viene illustrato il flusso di lavoro di base per una revisione della disposizione quando viene pubblicata un'etichetta di conservazione e quindi applicata manualmente da un utente. In alternativa, un'etichetta di conservazione configurata per una revisione di disposizione può essere applicata automaticamente al contenuto.
  
![Grafico che mostra il flusso di come funziona la disposizione](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
L'attivazione di una revisione della disposizione alla fine del periodo di conservazione è un'opzione di configurazione disponibile solo con un'etichetta di conservazione. Questa opzione non è disponibile per un criterio di conservazione. Per ulteriori informazioni su queste due soluzioni di conservazione, vedere informazioni [sui criteri di conservazione e sulle etichette di conservazione](retention.md).
  
![Impostazioni di conservazione per un'etichetta](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> Quando si seleziona l'opzione **notifica a queste persone quando sono disponibili elementi pronti per la revisione**, specificare un utente o un gruppo di sicurezza abilitato alla posta elettronica. I gruppi Microsoft 365 (in[precedenza gruppi di Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) non sono supportati per questa opzione.

### <a name="viewing-and-disposing-of-content"></a>Visualizzazione e eliminazione del contenuto

Quando un revisore riceve una notifica tramite posta elettronica che il contenuto è pronto per la revisione, accede alla scheda **disposizione** dalla **gestione dei record** nel centro conformità di Microsoft 365. I revisori possono vedere quanti elementi per ogni etichetta di conservazione sono in attesa di disposizione, quindi selezionare un'etichetta di conservazione per visualizzare tutto il contenuto con quell'etichetta.

Dopo aver selezionato un'etichetta di conservazione, vengono visualizzate tutte le disposizioni in sospeso per tale etichetta dalla scheda **disposizione in sospeso** . Selezionare uno o più elementi in cui è possibile scegliere un'azione e immettere un commento di giustificazione:

![Opzioni di disposizione](../media/retention-disposition-options.png)

Come si può vedere dall'immagine, le azioni supportate sono: 
  
- Elimina definitivamente l'elemento
- Estendere il periodo di conservazione
- Applicazione di un'etichetta di conservazione diversa

Se si dispone delle autorizzazioni per la posizione e il contenuto, è possibile utilizzare il collegamento nella colonna **percorso** per visualizzare i documenti nel percorso originale. Durante una revisione della disposizione, il contenuto non si sposta mai dal percorso originale e non viene mai eliminato fino a quando il revisore non lo sceglie.

Le notifiche di posta elettronica vengono inviate automaticamente ai revisori su base settimanale. Questo processo pianificato indica che quando il contenuto raggiunge la fine del periodo di conservazione, potrebbero essere necessari fino a sette giorni affinché i revisori ricevano la notifica di posta elettronica che il contenuto è in attesa di disposizione.
  
È possibile controllare tutte le azioni di disposizione e il testo di giustificazione immesso dal revisore viene salvato e visualizzato nella colonna **Commento** della pagina **elementi eliminati** .
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a>Durata dell'eliminazione definitiva del contenuto eliminato

Il contenuto in attesa di una revisione della disposizione viene eliminato solo dopo che un revisore sceglie di eliminare definitivamente il contenuto. Quando il revisore sceglie questa opzione, il contenuto del sito di SharePoint o dell'account OneDrive diventa idoneo per il processo di pulizia standard descritto in [modalità di funzionamento delle impostazioni di conservazione con il contenuto sul posto](retention.md#how-retention-settings-work-with-content-in-place).

## <a name="disposition-of-records"></a>Disposizione dei record

> [!NOTE]
> La possibilità di visualizzare i record che sono stati eliminati automaticamente senza una revisione della disposizione è gradualmente distribuita ai tenant nel corso di aprile e maggio 2020, quindi potrebbe non essere possibile visualizzare immediatamente questa esperienza.

Utilizzare la scheda **disposizione** della pagina **Gestione record** per identificare i record eliminati automaticamente. Questi elementi visualizzano i **record eliminati** nella colonna **tipo** . Ad esempio:

![Elementi eliminati senza una revisione di disposizione](../media/records-disposed2.png)

Gli elementi visualizzati nella scheda **elementi eliminati** per le etichette dei record vengono conservati per un massimo di 7 anni dopo l'eliminazione dell'elemento, con un limite di 1 milione elementi per ogni record per quel periodo. Se si Visualizza il numero di **conteggio** vicino a questo limite di 1 milione e si ha bisogno di una prova di disposizione per i record, contattare il [supporto tecnico Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

> [!NOTE]
> Questa funzionalità si basa su informazioni provenienti dal [Registro di controllo unificato](search-the-audit-log-in-security-and-compliance.md) e pertanto richiede l' [Abilitazione e la ricerca](turn-audit-log-search-on-or-off.md) in modo che gli eventi corrispondenti vengano acquisiti.
    
## <a name="filter-and-export-the-views"></a>Filtrare ed esportare le visualizzazioni

Quando si seleziona un'etichetta di conservazione dalla pagina **disposizione** , la scheda **disposizione in sospeso** (se applicabile) e la scheda **elementi eliminati** consentono di filtrare le visualizzazioni per facilitare la ricerca di elementi in modo più semplice. 

Per le disposizioni in sospeso, l'intervallo di tempo si basa sulla data di scadenza. Per gli elementi eliminati, l'intervallo di tempo è basato sulla data di eliminazione.
  
È possibile esportare le informazioni sugli elementi in una visualizzazione come file. csv che è possibile ordinare e gestire utilizzando Excel:

![Opzione di esportazione per la disposizione](../media/retention-export-option.png)
  
![Dati di disposizione esportati in Excel](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


