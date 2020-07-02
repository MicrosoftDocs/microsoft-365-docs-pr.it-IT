---
title: Utilizzare le azioni di miglioramento in Microsoft Compliance Score (Preview)
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come gestire le attività di conformità nel punteggio di conformità di Microsoft mediante operazioni di miglioramento.
ms.openlocfilehash: d10e04f144595e1976f4b20e894ccbc299aade7b
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016599"
---
# <a name="work-with-improvement-actions-in-compliance-score-preview"></a>Utilizzare le azioni di miglioramento nel punteggio di conformità (anteprima)

**In questo articolo:** In questo articolo viene illustrato come **gestire il flusso di lavoro di conformità** con le azioni di miglioramento. Informazioni su come **assegnare azioni di miglioramento** per l'implementazione e il testing, assegnarle ai valutatori per il completamento ed esportare i **report**.

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Gestire i flussi di lavoro di conformità con azioni di miglioramento

Le azioni di miglioramento centralizzano le attività di conformità. Ogni azione di miglioramento fornisce indicazioni dettagliate sull'implementazione che consentono di allineare le normative e i criteri di protezione dei dati. Le azioni possono essere assegnate agli utenti dell'organizzazione per eseguire il lavoro di implementazione e testing. È inoltre possibile archiviare la documentazione, le note e gli aggiornamenti dello stato del record all'interno dell'azione di miglioramento.

Tutti i miglioramenti sono elencati nella pagina azioni di miglioramento. Ulteriori informazioni su [come filtrare la visualizzazione delle azioni di miglioramento e interpretare gli Stati di stato](compliance-score-setup.md#improvement-actions-page).

## <a name="improvement-actions-details-page"></a>Pagina dei dettagli sulle azioni di miglioramento

Ogni azione di miglioramento contiene una pagina dei dettagli che mostra lo stato corrente e gli standard e i requisiti normativi correlati. Per informazioni dettagliate sull'implementazione, è incluso un collegamento **Launch Now** che consente di eseguire la soluzione appropriata per l'implementazione. È possibile collegare la documentazione relativa all'implementazione e al testing direttamente nella pagina dei dettagli dell'azione di miglioramento.

Per visualizzare la pagina dei dettagli dell'azione di miglioramento:

1. Passare alla pagina azioni di miglioramento.
2. Selezionare la riga dell'azione di miglioramento desiderata, che apre la pagina dei dettagli.

È possibile visualizzare facilmente l'azione di miglioramento successiva o precedente nell'elenco selezionando la freccia verso l'alto o verso il basso nell'angolo in alto a destra dello schermo. Se l'elenco è stato filtrato nella pagina azioni di miglioramento, lo spostamento verso l'alto o verso il basso porta all'elemento successivo all'interno dell'elenco filtrato.

## <a name="assign-improvement-actions"></a>Assegnare azioni di miglioramento

Per iniziare a lavorare sull'implementazione di un'azione di miglioramento, è possibile eseguire autonomamente il lavoro o assegnarlo a un altro utente. La persona assegnata potrebbe essere:

- Il proprietario di un criterio di business
- Un implementatore IT
- Un altro dipendente che ha la responsabilità di eseguire l'attività

Dopo aver identificato l'assegnatario appropriato, accertarsi che dispongano di un [ruolo sufficiente in Score Compliance](compliance-score-setup.md#set-user-permissions-and-assign-roles) (compliance Administrator, Compliance Data Administrator, Security Administrator o Global Administrator) per eseguire il lavoro, quindi effettuare le seguenti operazioni:

1. Dalla pagina dei dettagli sulle azioni di miglioramento, selezionare **modifica stato** vicino alla sezione in alto a sinistra dello schermo.

2. Nel riquadro icona di modifica dello stato, selezionare la casella **assegnata** a per visualizzare un elenco di utenti **consigliato** . È possibile selezionare l'utente dall'elenco oppure digitare l'indirizzo di posta elettronica della persona a cui si desidera assegnarlo.

3. Selezionare **Salva e Chiudi**. L'utente assegnato riceverà un messaggio di posta elettronica a cui è stata assegnata l'azione di miglioramento e potrà quindi aprire l'azione di miglioramento dal proprio dashboard.

L'utente assegnato può quindi eseguire le azioni consigliate.

## <a name="perform-work-and-store-documentation"></a>Eseguire la documentazione relativa al lavoro e all'archiviazione

È possibile caricare file e note relativi all'implementazione e al testing direttamente nella sezione **note e documentazione** . Questo ambiente è un repository sicuro e centralizzato che consente di dimostrare la soddisfazione dei controlli per soddisfare gli standard e i regolamenti di conformità. Qualsiasi utente con accesso in sola lettura può leggere il contenuto in questa sezione. Solo gli utenti con diritti di modifica possono caricare e scaricare file e immettere o modificare note.

Nei campi della sezione **note e documentazione** sono inclusi i seguenti:

### <a name="uploaded-documents"></a>Documenti caricati

- Selezionare **Gestisci documenti** per caricare eventuali file rilevanti.
- Quando viene aperto il riquadro dell'icona Gestisci documenti, selezionare **Aggiungi documento**, quindi selezionare il file dal sistema. Tipi di file accettati:
    - Documenti (. doc,. xls,. ppt,. txt,. pdf)
    - Immagini (. jpg,. png)
    - Video (con estensione MKV)
    - File compressi (con estensione zip,. rar)
- Dopo aver risolto il file nel riquadro Seleziona **Chiudi**, che salva automaticamente il file allegato. Verrà visualizzato il file elencato sotto i **documenti caricati**.
- Per scaricare o eliminare il documento, selezionare **Gestisci documenti** da sotto l'elenco dei documenti. Nel riquadro a comparsa, fare clic o toccare la riga del documento per evidenziarla, quindi selezionare **Scarica** o **Elimina**.

### <a name="implementation-notes-test-notes-and-additional-notes"></a>Note sull'implementazione, note di test e note aggiuntive

- Per aggiungere note in uno di questi tre campi, selezionare **modifica note di implementazione** al di sotto di uno di questi campi.
- Quando viene aperto il riquadro a comparsa, immettere note nel campo di testo, quindi selezionare **Salva e Chiudi**.
- Per modificare le note, selezionare **modifica note di implementazione**, apportare le modifiche, quindi selezionare **Salva e Chiudi**.

Nei campi Notes non è presente alcun limite di caratteri. È consigliabile mantenere le note brevi in modo che sia possibile visualizzarle e modificarle facilmente dalla pagina dei dettagli sulle azioni di miglioramento.

## <a name="change-improvement-action-status"></a>Stato azione miglioramento modifiche

È possibile registrare lo stato di implementazione e la data e lo stato e la data del test per ogni azione di miglioramento. I campi di stato di **implementazione** e di **testing** possono essere modificati da qualsiasi utente con autorizzazioni di modifica, non solo dalla persona assegnata.

Per modificare lo stato di un'azione di miglioramento, selezionare **modifica stato** nella sezione in alto a sinistra della pagina dei dettagli. Di seguito sono riportati i campi e le opzioni di stato disponibili:

- **Stato di implementazione**
    - **Non implementato** : azione non ancora implementata
    - **Implementato** -azione implementata
    - **Implementazione alternativa** : selezionare questa opzione se sono stati utilizzati altri strumenti di terze parti o sono state eseguite altre azioni non incluse nei consigli di Microsoft
    - **Pianificata** -azione pianificata per l'implementazione
    - **Non nell'ambito** – l'azione non è pertinente per l'organizzazione e non contribuisce allo score
- **Data di implementazione**: disponibile per selezionare quando lo stato dell'implementazione è "implementato" o "implementazione alternativa"
- **Stato del test**: disponibile per selezionare quando lo stato dell'implementazione è "implementato" o "implementazione alternativa":
    - **Non valutato** : l'azione non è stata testata
    - L'implementazione **passata**è stata verificata da un valutatore
    - **Esito negativo** dei test a basso rischio non riuscito, rischio basso
    - **Esito** negativo del test di rischio medio non riuscito, rischio medio
    - **Errore ad alto rischio** -test non riuscito, ad alto rischio
    - **Non nell'ambito** – l'azione non rientra nell'ambito della valutazione e non contribuisce allo score
- **Data di testing**: passare dal menu a comparsa calendario per selezionare la data

Le azioni comuni si sincronizzano tra i gruppi. Quando due diverse valutazioni nelle stesse azioni di miglioramento della condivisione di gruppo gestite dall'utente, tutti gli aggiornamenti apportati ai dettagli di implementazione o allo stato di un'azione verranno sincronizzati automaticamente alla stessa azione in qualsiasi altra valutazione del gruppo. Questa sincronizzazione consente di implementare un'azione di miglioramento e di soddisfare diversi requisiti in più normative.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Assegnare un'azione di miglioramento all'analizzatore per il completamento

Dopo aver completato il lavoro, eseguito il testing e il caricamento della prova, il passaggio successivo consiste nell'assegnare l'azione di miglioramento a un valutatore per la convalida.

Tra i tipi di consulenti sono inclusi i seguenti:

- Valutatori interni che eseguono la convalida dei controlli all'interno dell'organizzazione
- Valutatori esterni che esaminano, verificano e certificano la conformità, ad esempio organizzazioni indipendenti di terze parti che controllano i servizi cloud Microsoft

Il valutatore convalida il lavoro ed esamina la documentazione e seleziona lo stato di test appropriato.

**Se lo stato del test è impostato su "superato"**: l'azione è completa e i punti ottenuti mostrano i punti massimi raggiunti. I punti vengono quindi conteggiati verso il Punteggio di conformità globale.

**Se lo stato del test è impostato su "non riuscito"**: l'azione non soddisfa i requisiti e il valutatore può assegnarlo all'utente appropriato per ulteriori operazioni.

## <a name="export-a-report"></a>Esportare un report

Selezionare **Esporta** nell'angolo superiore sinistro dello schermo per scaricare un foglio di lavoro di Excel contenente tutte le azioni di miglioramento e le categorie di filtri mostrate nella pagina azioni di miglioramento.