---
title: Eliminazione del contenuto
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Monitorare e gestire lo smaltimento del contenuto, sia che si utilizzi una revisione per l'eliminazione o che il contenuto venga eliminato automaticamente in base alle impostazioni configurate.
ms.openlocfilehash: 9c2e9055d0468270df4e46fe39115708762052f3
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682669"
---
# <a name="disposition-of-content"></a>Eliminazione del contenuto

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Utilizzare la scheda **eliminazione** dalla **gestione record** nel Centro conformità Microsoft 365 per gestire le revisioni per l’eliminazione e visualizzare i [record](records-management.md#records) eliminati automaticamente al termine del periodo di conservazione. 

## <a name="prerequisites-for-viewing-content-dispositions"></a>Prerequisiti per la visualizzazione delle eliminazioni di contenuto

Per gestire le revisioni per l’eliminazione e verificare che i record siano stati eliminati, è necessario avere le autorizzazioni necessarie e che il controllo sia abilitato.

### <a name="permissions-for-disposition"></a>Autorizzazioni per l'eliminazione

Per accedere correttamente alla scheda **eliminazione** nel Centro conformità Microsoft 365, è necessario che gli utenti abbiano il ruolo di amministratore per la **gestione dell’eliminazione**. Da dicembre 2020, questo ruolo è incluso nel gruppo dei ruoli di amministratore predefiniti di **Gestione record**.

> [!NOTE]
> Per impostazione predefinita, un amministratore globale non può avere il ruolo di **gestione dell'eliminazione**. 

Per concedere agli utenti solo le autorizzazioni necessarie per le revisioni per l'eliminazione senza concedere loro l’autorizzazione a visualizzare e configurare altre funzionalità per la conservazione e la gestione dei record, creare un gruppo di ruoli personalizzato (ad esempio, denominato "Revisori per l’eliminazione") e concedere a questo gruppo il ruolo di Gestione delle eliminazioni.

Inoltre, per visualizzare il contenuto degli elementi durante il processo di eliminazione, aggiungere utenti ai due gruppi di ruoli seguenti: **Visualizzatore contenuto di Esplora contenuto** e **Visualizzatore elenco di Esplora contenuto**. Se gli utenti non hanno le autorizzazioni di questi gruppi di ruoli, possono comunque selezionare un'azione di revisione per l'eliminazione per completare l'operazione, ma devono farlo senza poter vedere il contenuto dell'elemento nel centro conformità.

Per le istruzioni per configurare queste autorizzazioni, vedere [Fornire agli utenti l'accesso al Centro sicurezza e conformità di Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

### <a name="enable-auditing"></a>Abilitazione del controllo

Verificare che il controllo sia abilitato almeno un giorno prima della prima azione di eliminazione. Per ulteriori informazioni, vedere [Eseguire una ricerca nel log di controllo nel &amp;Centro sicurezza e conformità di Office 365](search-the-audit-log-in-security-and-compliance.md). 

## <a name="disposition-reviews"></a>Revisioni per l'eliminazione

Quando il contenuto raggiunge la fine del periodo di conservazione, ci possono essere diversi motivi per cui è consigliabile esaminare il contenuto prima di decidere se possa essere eliminato senza problemi ("disposto"). Ad esempio, potrebbe essere necessario:
  
- Sospendere l'eliminazione del contenuto pertinente in caso di controversie legali o di un controllo.
    
- Rimuovere il contenuto dall'elenco di eliminazioni per archiviarlo, se tale contenuto ha un valore storico o di ricerca.
    
- Assegnare un periodo di conservazione diverso al contenuto, perché ad esempio le impostazioni di conservazione originali erano una soluzione temporanea o provvisoria.
    
- Restituire il contenuto ai clienti o trasferirlo a un'altra organizzazione.

Quando viene attivata una revisione per l'eliminazione alla fine del periodo di conservazione:
  
- Gli utenti prescelti ricevono una notifica di posta elettronica che indica che hanno dei contenuti da rivedere. Questi revisori possono essere singoli utenti o gruppi di sicurezza abilitati alla posta elettronica. Si noti che le notifiche vengono inviate su base settimanale.
    
- I revisori accedono alla scheda **eliminazione** nel Centro conformità Microsoft 365 per rivedere il contenuto e decidere se eliminarlo definitivamente, estendere il periodo di conservazione o applicare una diversa etichetta di conservazione.

Una revisione per l'eliminazione può includere il contenuto di cassette postali di Exchange, siti di SharePoint, account di OneDrive e gruppi di Microsoft 365. Il contenuto in attesa di una revisione per l'eliminazione in tali posizioni viene eliminato solo dopo che un revisore sceglie di eliminarlo definitivamente.

> [!NOTE]
> Una cassetta postale deve contenere almeno 10 MB di dati per supportare le revisioni per l’eliminazione.

È possibile visualizzare una panoramica di tutte le eliminazioni in sospeso nella scheda **panoramica**. Per esempio:

![Eliminazioni in sospeso nella panoramica sulla gestione dei record](../media/dispositions-overview.png)

Quando si seleziona **Visualizza tutte le eliminazioni in sospeso**, viene visualizzata la pagina **eliminazione**. Ad esempio:

![Pagina eliminazioni nel Centro conformità Microsoft 365.](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a>Flusso di lavoro della revisione per l'eliminazione.

Il diagramma seguente illustra il flusso di lavoro di base di una revisione per l'eliminazione quando viene pubblicata una etichetta di conservazione e quindi applicata manualmente da un utente. In alternativa, un'etichetta di conservazione configurata per una revisione per l’eliminazione può essere applicata automaticamente al contenuto.
  
![Grafico che mostra il flusso di funzionamento dell’eliminazione](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
L'attivazione di una revisione per l'eliminazione alla fine del periodo di conservazione è un'opzione di configurazione disponibile solo con un'etichetta di conservazione. Questa opzione non è disponibile per i criteri di conservazione. Per saperne di più su queste due soluzioni di conservazione, vedere [Informazioni sui criteri e le etichette di conservazione](retention.md).

Dalla pagina **Definisci le impostazioni di conservazione** per un'etichetta di conservazione:

![Impostazioni di conservazione per l'etichetta](../media/disposition-review-option.png)
 
Dopo aver selezionato l'opzione **Attiva una revisione per l'eliminazione**, si specificano i revisori per l’eliminazione nella pagina successiva della procedura guidata:

![Specifica dei revisori per l’eliminazione](../media/disposition-reviewers.png)

Per i revisori, specificare un utente o un gruppo di sicurezza abilitato alla posta elettronica. I gruppi di Microsoft 365 (in precedenza[gruppi di Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) non sono supportati per questa opzione.

### <a name="viewing-and-disposing-of-content"></a>Visualizzazione ed eliminazione del contenuto

Quando riceve una notifica tramite posta elettronica che informa che il contenuto è pronto per la revisione, il revisore può accedere alla scheda **eliminazione** dalla **gestione dei record** nel Centro conformità Microsoft 365. I revisori possono visualizzare il numero di elementi per ogni etichetta di conservazione in attesa di eliminazione e quindi selezionare un'etichetta di conservazione per visualizzare tutto il contenuto sotto tale etichetta.

Dopo aver selezionato un'etichetta di conservazione, sono visualizzate tutte le eliminazioni in sospeso relative a tale etichetta dalla scheda **eliminazione in sospeso**. Selezionare uno o più elementi, poi scegliere un’azione relativamente ad essi e inserire un commento di motivazione:

![Opzioni di eliminazione](../media/retention-disposition-options.png)

Come si può vedere dall'immagine, le azioni supportate sono: 
  
- Eliminare definitivamente l'elemento.
- Estendere il periodo di conservazione.
- Applicare un'etichetta di conservazione diversa

Se si hanno le autorizzazioni necessarie per la posizione e il contenuto, è possibile usare il collegamento nella colonna **posizione** per visualizzare i documenti nella posizione originale. Durante una revisione per l'eliminazione, il contenuto non si sposta mai dalla posizione originale e non viene eliminato finché non lo decide il revisore.

Le notifiche di posta elettronica vengono inviate automaticamente ai revisori con cadenza settimanale. Questa programmazione implica che, quando il contenuto raggiunge la fine del periodo di conservazione, possono trascorrere fino a sette giorni perché ai revisori venga notificato tramite posta elettronica che il contenuto è in attesa di eliminazione.
  
Tutte le azioni di eliminazione possono essere controllate e il testo della motivazione inserito dal revisore viene salvato e visualizzato nella colonna **commento** nella pagina **elementi eliminati**.
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a>Dopo quanto tempo viene eliminato definitivamente il contenuto eliminato

Il contenuto in attesa di una revisione per l'eliminazione viene eliminato solo dopo che un revisore sceglie di eliminarlo definitivamente. Se il revisore sceglie questa opzione, il contenuto del sito di SharePoint o dell'account di OneDrive diventa idoneo per il processo di pulizia standard descritto in [Funzionamento delle impostazioni di conservazione con i contenuti in locale](retention.md#how-retention-settings-work-with-content-in-place).

## <a name="disposition-of-records"></a>Eliminazione dei record

Usare la scheda **eliminazione** della pagina **gestione record** per identificare i record che vengono ora eliminati, automaticamente o dopo una revisione dell’eliminazione. Questi elementi visualizzano i **record eliminati** nella colonna **Tipo**. Ad esempio:

![Elementi eliminati senza revisione per l'eliminazione](../media/records-disposed2.png)

Gli elementi visualizzati nella scheda **elementi eliminati** delle etichette dei record vengono conservati per un massimo di sette anni dalla data di eliminazione dell'elemento, con un limite di 1 milione di elementi per ogni record per quel periodo. Se la cifra di **Conteggio** visualizzata si avvicina al limite di 1 milione e occorre prova di eliminazione dei record, contattare il [supporto tecnico Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

> [!NOTE]
> Questa funzionalità si basa sulle informazioni provenienti dal [Log di controllo unificato](search-the-audit-log-in-security-and-compliance.md) e, di conseguenza, è necessario che il controllo sia [abilitato e con ricerca consentita](turn-audit-log-search-on-or-off.md) in modo da acquisire gli eventi corrispondenti.

Per il controllo, cercare **File eliminato contrassegnato come record** nella categoria **Attività su file e pagine**. Questo evento di controllo è applicabile ai documenti e ai messaggi di posta elettronica.

## <a name="filter-and-export-the-views"></a>Filtrare ed esportare le visualizzazioni

Se si seleziona un'etichetta di conservazione dalla pagina **eliminazione**, la scheda **eliminazione in sospeso**(se applicabile) e la scheda **elementi eliminati** consentono di filtrare le visualizzazioni per trovare più facilmente gli elementi. 

Per le eliminazioni in sospeso, l'intervallo di tempo si basa sulla data di scadenza. Per gli elementi eliminati, l'intervallo di tempo si basa sulla data di eliminazione.
  
Per entrambe le visualizzazioni è possibile esportare le informazioni sugli elementi come file .csv, che si può poi ordinare e gestire con Excel:

![Opzione Esporta per l’eliminazione](../media/retention-export-option.png)

