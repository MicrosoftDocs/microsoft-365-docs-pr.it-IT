---
title: Assegnare e completare azioni di miglioramento in Microsoft Compliance Manager
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
description: Informazioni su come eseguire l'implementazione e il testing sui controlli in Microsoft Compliance Manager. Assegnare lavoro, archiviare la documentazione ed esportare i report.
ms.openlocfilehash: c465a574ed9c1a8ad8ef9e2bfc7f864545ae28d9
ms.sourcegitcommit: 00d231bf0100e843a5a93161695e87ceff9e1349
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49849599"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>Assegnare e completare azioni di miglioramento in Compliance Manager

**In questo articolo:** In questo articolo viene illustrato come **gestire il flusso di lavoro di conformità** con le azioni di miglioramento. Informazioni su come **assegnare azioni di miglioramento** per l'implementazione e il testing, **gestire gli aggiornamenti** ed esportare i **report**.

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Gestire i flussi di lavoro di conformità con azioni di miglioramento

Le azioni di miglioramento centralizzano le attività di conformità. Ogni azione di miglioramento fornisce indicazioni dettagliate sull'implementazione che consentono di allineare le normative e i criteri di protezione dei dati. Le azioni possono essere assegnate agli utenti dell'organizzazione per eseguire il lavoro di implementazione e testing. È inoltre possibile archiviare la documentazione, le note e gli aggiornamenti dello stato del record all'interno dell'azione.

Tutte le azioni di miglioramento sono elencate nella pagina azioni di miglioramento. Ulteriori informazioni sulla [visualizzazione delle azioni di miglioramento](compliance-manager-setup.md#improvement-actions-page).

## <a name="improvement-actions-details-page"></a>Pagina dei dettagli sulle azioni di miglioramento

Ogni azione di miglioramento contiene una pagina dei dettagli che mostra lo stato corrente, gli standard correlati e i requisiti normativi e le linee guida per l'implementazione consigliate. Le [azioni tecniche](compliance-score-calculation.md#technical-and-non-technical-actions) includono un collegamento **Launch Now** che consente di eseguire la soluzione appropriata per l'implementazione. È possibile collegare la documentazione relativa all'implementazione e al testing direttamente nella pagina dei dettagli dell'azione di miglioramento.

Per visualizzare la pagina dei dettagli dell'azione di miglioramento:

1. Passare alla pagina azioni di miglioramento.
2. Selezionare la riga dell'azione di miglioramento desiderata, che apre la pagina dei dettagli.

È possibile visualizzare facilmente l'azione di miglioramento successiva o precedente nell'elenco selezionando la freccia verso l'alto o verso il basso nell'angolo in alto a destra dello schermo. Se l'elenco è stato filtrato nella pagina azioni di miglioramento, lo spostamento verso l'alto o verso il basso porta all'elemento successivo all'interno dell'elenco filtrato.

## <a name="assign-improvement-actions"></a>Assegnare azioni di miglioramento

Per iniziare a lavorare sull'implementazione di un'azione di miglioramento, è possibile eseguire autonomamente il lavoro o assegnarlo a un altro utente. La persona assegnata potrebbe essere:

- Il proprietario di un criterio di business
- Un implementatore IT
- Un altro dipendente che ha la responsabilità di eseguire l'attività

Dopo aver identificato l'assegnatario appropriato, accertarsi che dispongano di un [ruolo di Compliance Manager](compliance-manager-setup.md#set-user-permissions-and-assign-roles) sufficiente per eseguire il lavoro. Seguire quindi i passaggi riportati di seguito per assegnare l'azione di miglioramento:

1. Dalla pagina dei dettagli sulle azioni di miglioramento, selezionare **modifica stato** vicino alla sezione in alto a sinistra dello schermo.

2. Nel riquadro icona di modifica dello stato, selezionare la casella **assegnata** a per visualizzare un elenco di utenti **consigliato** . È possibile selezionare l'utente dall'elenco oppure digitare l'indirizzo di posta elettronica della persona a cui si desidera assegnarlo.

3. Selezionare **Salva e Chiudi**. L'utente assegnato riceverà un messaggio di posta elettronica in cui viene spiegato che è stata assegnata l'azione di miglioramento, con un collegamento diretto all'azione di miglioramento. (Nota: i clienti di US Government community (GCC) High non riceveranno un messaggio di posta elettronica quando le azioni vengono assegnate a tali utenti.

L'utente assegnato può quindi eseguire le azioni consigliate.

#### <a name="assign-multiple-improvement-actions-to-a-single-user"></a>Assegnare più azioni di miglioramento a un singolo utente

È possibile assegnare più azioni di miglioramento a un utente attenendosi alla procedura seguente:

1. Passare alla pagina azioni di miglioramento.
2. Selezionare l'area a sinistra del nome dell'azione di miglioramento. Verrà visualizzata un'icona di controllo rotondo che indica che è stata selezionata l'azione. Controllare tutte le azioni che si desidera assegnare.
3. Selezionare il collegamento **assegna a utente** nella parte superiore della tabella azioni di miglioramento.
4. Verrà visualizzata una finestra popup. Nel campo **assegna a** , iniziare a digitare il nome della persona a cui si desidera assegnare le azioni. È inoltre possibile selezionare dall'elenco di utenti suggeriti.
5. Dopo aver popolato il campo **assegna a** con il nome dell'assegnatario, selezionare **assegna**.
6. Verrà visualizzata la pagina azioni di miglioramento con il nuovo assegnatario elencato per le azioni appena assegnate.

## <a name="perform-work-and-store-documentation"></a>Eseguire la documentazione relativa al lavoro e all'archiviazione

È possibile caricare file e note relativi all'implementazione e al testing direttamente nella sezione **note e documentazione** . Questo ambiente è un repository sicuro e centralizzato che consente di dimostrare la soddisfazione dei controlli per soddisfare gli standard e i regolamenti di conformità. Qualsiasi utente con accesso in sola lettura può leggere il contenuto in questa sezione. Solo gli utenti con diritti di modifica possono caricare e scaricare file e immettere o modificare note.

La sezione **note e documentazione** contiene i campi per i documenti caricati, le note di implementazione, le note di test e altre note.

#### <a name="uploaded-documents"></a>Documenti caricati

- Selezionare **Gestisci documenti** per caricare eventuali file rilevanti.
- Quando viene aperto il riquadro dell'icona Gestisci documenti, selezionare **Aggiungi documento**, quindi selezionare il file dal sistema. Tipi di file accettati:
    - Documenti (. doc,. xls,. ppt,. txt,. pdf)
    - Immagini (. jpg,. png)
    - Video (con estensione MKV)
    - File compressi (con estensione zip,. rar)
- Dopo aver risolto il file nel riquadro Seleziona **Chiudi**, che salva automaticamente il file allegato. Verrà visualizzato il file elencato sotto i **documenti caricati**.
- Per scaricare o eliminare il documento, selezionare **Gestisci documenti** da sotto l'elenco dei documenti. Nel riquadro a comparsa selezionare la riga del documento per evidenziarla e quindi fare clic su **Scarica** o **Elimina**.

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>Note sull'implementazione, note di test e note aggiuntive

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
    - **Fuori ambito** – l'azione non è pertinente per l'organizzazione e non contribuisce al Punteggio
- **Data di implementazione**: disponibile per selezionare quando lo stato dell'implementazione è "implementato" o "implementazione alternativa"
- **Stato del test**: disponibile per selezionare quando lo stato dell'implementazione è "implementato" o "implementazione alternativa":
    - **Non valutato** : l'azione non è stata testata
    - L'implementazione **passata** è stata verificata da un valutatore
    - **Esito negativo** dei test a basso rischio non riuscito, rischio basso
    - **Esito** negativo del test di rischio medio non riuscito, rischio medio
    - **Errore ad alto rischio** -test non riuscito, ad alto rischio
    - **Fuori portata** : l'azione non rientra nell'ambito della valutazione e non contribuisce allo score
- **Data di testing**: passare dal menu a comparsa calendario per selezionare la data

Le azioni comuni si sincronizzano tra i gruppi. Quando due diverse valutazioni nelle stesse azioni di miglioramento della condivisione di gruppo gestite dall'utente, tutti gli aggiornamenti apportati ai dettagli di implementazione o allo stato di un'azione verranno sincronizzati automaticamente alla stessa azione in qualsiasi altra valutazione del gruppo. Questa sincronizzazione consente di implementare un'azione di miglioramento e di soddisfare diversi requisiti in più normative.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Assegnare un'azione di miglioramento all'analizzatore per il completamento

Dopo aver completato il lavoro, eseguito il testing e il caricamento della prova, il passaggio successivo consiste nell'assegnare l'azione di miglioramento a un valutatore per la convalida. Il valutatore convalida il lavoro ed esamina la documentazione e seleziona lo stato di test appropriato.

**Se lo stato del test è impostato su "superato"**: l'azione è completa e i punti ottenuti mostrano i punti massimi raggiunti. I punti vengono quindi conteggiati verso il Punteggio di conformità globale.

**Se lo stato del test è impostato su "non riuscito"**: l'azione non soddisfa i requisiti e il valutatore può assegnarlo all'utente appropriato per ulteriori operazioni.

## <a name="accepting-updates-to-improvement-actions"></a>Accettazione degli aggiornamenti per le azioni di miglioramento

Quando è disponibile un aggiornamento per un'azione di miglioramento, viene visualizzata una notifica accanto al relativo nome. È possibile accettare l'aggiornamento o posticiparlo per un secondo momento.

#### <a name="what-causes-an-update"></a>Quali sono le cause di un aggiornamento

Un aggiornamento si verifica quando vengono apportate modifiche relative al punteggio, all'automazione o all'ambito. Le modifiche possono comportare nuove linee guida per azioni di miglioramento basate su modifiche normative o potrebbero essere causa di modifiche al prodotto. Solo le azioni di miglioramento gestite dalle organizzazioni ricevono notifiche degli aggiornamenti.

#### <a name="where-youll-see-assessment-update-notifications"></a>Dove vengono visualizzate le notifiche degli aggiornamenti per la valutazione

Quando si aggiorna un'azione di miglioramento, viene visualizzata un'etichetta di **aggiornamento in sospeso** accanto al relativo nome nella pagina azioni di miglioramento e nella pagina dei dettagli delle valutazioni correlate.

Passare alla pagina dei dettagli dell'azione di miglioramento e selezionare il pulsante **Verifica aggiornamento** nel banner superiore per esaminare i dettagli relativi alle modifiche e accettare o rinviare l'aggiornamento.

#### <a name="review-update-to-accept-or-defer"></a>Revisione dell'aggiornamento da accettare o posticipare

Dopo aver selezionato **revisione aggiornamento** dalla pagina Dettagli azione di miglioramento, sul lato destro dello schermo viene visualizzato un riquadro a comparsa. Nel riquadro riquadro a comparsa sono disponibili informazioni importanti sull'aggiornamento, ad esempio le valutazioni interessate e le modifiche apportate al punteggio e all'ambito.

Selezionare **accetta aggiornamento** per accettare tutte le modifiche apportate all'azione di miglioramento. **Le modifiche accettate sono permanenti**.

> [!NOTE]
> Quando si accetta un aggiornamento a un'azione, vengono accettati anche gli aggiornamenti a qualsiasi altra versione o istanza di questa azione. Gli aggiornamenti verranno propagati a livello di tenant per le azioni tecniche e verranno propagati a livello di gruppo per le azioni non tecniche.

Se si seleziona **Annulla**, l'aggiornamento non verrà applicato all'azione di miglioramento. Tuttavia, si continuerà a visualizzare la notifica di **aggiornamento in sospeso** fino a quando non si accetterà l'aggiornamento.

**Perché si consiglia di accettare gli aggiornamenti**

L'accettazione degli aggiornamenti consente di ottenere le informazioni più aggiornate sull'utilizzo delle soluzioni e sull'adozione di azioni di miglioramento appropriate che consentano di soddisfare i requisiti della certificazione a disposizione.

**Perché potrebbe essere opportuno rinviare un aggiornamento**

Se si sta eseguendo una valutazione che include l'azione di miglioramento, potrebbe essere necessario verificare di aver completato il lavoro prima di accettare l'aggiornamento. È possibile posticipare l'aggiornamento per un secondo momento selezionando **Annulla** nel riquadro del pannello a comparsa revisione aggiornamento.

#### <a name="accept-all-updates-at-once"></a>Accetta tutti gli aggiornamenti contemporaneamente

Se si dispone di più aggiornamenti e si desidera accettarli contemporaneamente, selezionare il collegamento **accetta tutti gli aggiornamenti** nella parte superiore della tabella azioni di miglioramento. Verrà visualizzato un riquadro a comparsa che elenca il numero di azioni da aggiornare. Selezionare il pulsante **accetta aggiornamenti** per applicare tutti gli aggiornamenti.

Si noti che quando si torna alla pagina azioni di miglioramento, è possibile che venga visualizzato un messaggio nella parte superiore della pagina in cui viene chiesto di aggiornare la pagina per il completamento degli aggiornamenti.

## <a name="export-a-report"></a>Esportare un report

Selezionare **Esporta** nell'angolo superiore sinistro dello schermo per scaricare un foglio di lavoro di Excel contenente tutte le azioni di miglioramento e le categorie di filtri mostrate nella pagina azioni di miglioramento.