---
title: Assegnare e completare le azioni di miglioramento in Microsoft Compliance Manager
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
description: Informazioni su come eseguire l'implementazione e il test sui controlli in Microsoft Compliance Manager. Assegnare rapporti di lavoro, archiviare documentazione ed esportare.
ms.openlocfilehash: e761d8d4410f1c52bb79d4a225eec407f1fd6a6e
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570385"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>Assegnare e completare le azioni di miglioramento in Compliance Manager

**In questo articolo:** Questo articolo spiega come gestire il **flusso di lavoro di conformità con** le azioni di miglioramento. Informazioni su come **assegnare azioni di miglioramento per** l'implementazione e il testing, gestire gli **aggiornamenti** ed esportare **report.**

## <a name="manage-compliance-workflows-with-improvement-actions"></a>Gestire i flussi di lavoro di conformità con azioni di miglioramento

Le azioni di miglioramento centralizzare le attività di conformità. Ogni azione di miglioramento fornisce indicazioni dettagliate sull'implementazione per allinearti alle normative e agli standard di protezione dei dati. È possibile assegnare azioni agli utenti dell'organizzazione per eseguire attività di implementazione e test. È inoltre possibile archiviare documentazione, note e aggiornamenti dello stato dei record all'interno dell'azione.

Tutte le azioni di miglioramento sono elencate nella pagina azioni di miglioramento. Ulteriori informazioni sulla [visualizzazione delle azioni di miglioramento.](compliance-manager-setup.md#improvement-actions-page)

## <a name="improvement-actions-details-page"></a>Pagina dettagli azioni di miglioramento

Ogni azione di miglioramento ha una pagina dei dettagli che mostra lo stato corrente, gli standard e i requisiti normativi correlati e le indicazioni consigliate per l'implementazione. [Le azioni tecniche](compliance-score-calculation.md#technical-and-non-technical-actions) includono **un collegamento Avvia** ora che consente di accedere alla soluzione appropriata per l'implementazione. Puoi allegare la documentazione di implementazione e test direttamente nella pagina dei dettagli di un'azione di miglioramento.

Per visualizzare la pagina dei dettagli di un'azione di miglioramento:

1. Vai alla pagina delle azioni di miglioramento.
2. Selezionare la riga dell'azione di miglioramento prevista, che apre la relativa pagina dei dettagli.

È possibile visualizzare facilmente l'azione di miglioramento successiva o precedente nell'elenco selezionando la freccia su o giù nell'angolo superiore destro dello schermo. Se l'elenco è stato filtrato nella pagina delle azioni di miglioramento, lo spostamento verso l'alto o verso il basso consente di passare all'elemento successivo all'interno dell'elenco filtrato.

## <a name="assign-improvement-actions"></a>Assegnare azioni di miglioramento

Per iniziare il lavoro di implementazione su un'azione di miglioramento, puoi eseguire il lavoro manualmente o assegnarlo a un altro utente. La persona assegnata potrebbe essere:

- Il proprietario di un criterio di business
- Un implementatore IT
- Un altro dipendente responsabile dell'esecuzione dell'attività

Dopo aver identificato l'assegnatare appropriato, assicurarsi che dispongano di un ruolo [di Compliance Manager](compliance-manager-setup.md#set-user-permissions-and-assign-roles) sufficiente per eseguire il lavoro. Seguire quindi i passaggi seguenti per assegnare l'azione di miglioramento:

1. Nella pagina dei dettagli delle azioni di miglioramento seleziona **Modifica stato** nella sezione superiore sinistra dello schermo.

2. Nel riquadro a comparsa Modifica stato selezionare **la** casella Assegnato a per visualizzare un elenco di **utenti** suggeriti. È possibile selezionare l'utente dall'elenco o digitare l'indirizzo di posta elettronica della persona a cui si desidera assegnarlo.

3. Selezionare **Salva e chiudi**. L'utente assegnato riceverà un messaggio di posta elettronica in cui viene spiegato che l'azione di miglioramento è stata assegnata, con un collegamento diretto all'azione di miglioramento. 
> [!NOTE]
> I clienti della US Government Community (GCC) High and Department of Defense (DoD) non riceveranno un messaggio di posta elettronica quando vengono assegnate azioni di miglioramento.

L'utente assegnato può quindi eseguire le azioni consigliate.

#### <a name="assign-multiple-improvement-actions-to-a-single-user"></a>Assegnare più azioni di miglioramento a un singolo utente

È possibile assegnare più azioni di miglioramento a un utente seguendo questi passaggi:

1. Passare alla pagina Azioni di miglioramento.
2. Selezionare l'area a sinistra del nome dell'azione di miglioramento. Verrà visualizzata un'icona di controllo di tipo round che indica che l'azione è stata selezionata. Selezionare tutte le azioni che si desidera assegnare.
3. Selezionare il **collegamento Assegna all'utente** nella parte superiore della tabella delle azioni di miglioramento.
4. Verrà visualizzata una finestra popup. Nel campo **Assegna a** iniziare a digitare il nome della persona a cui si desidera assegnare le azioni. È inoltre possibile eseguire una selezione dall'elenco delle persone suggerite.
5. Dopo aver popolato il campo **Assegna a** con il nome dell'assegnatare, selezionare **Assegna**.
6. Verrà quindi visualizzata la pagina Azioni di miglioramento con il nuovo assegnatare elencato per le azioni appena assegnate.

## <a name="perform-work-and-store-documentation"></a>Eseguire documentazione di lavoro e archivio

Puoi caricare file e note relativi all'implementazione e al testing direttamente nella **sezione Note e** documentazione. Questo ambiente è un archivio sicuro e centralizzato che consente di dimostrare la soddisfazione dei controlli per soddisfare gli standard e le normative di conformità. Qualsiasi utente con accesso in sola lettura può leggere il contenuto di questa sezione. Solo gli utenti con diritti di modifica possono caricare e scaricare file e immettere o modificare le note.

La **sezione Note e documentazione** contiene i campi per i documenti caricati, le note sull'implementazione, le note di test e le note aggiuntive.

#### <a name="uploaded-documents"></a>Documenti caricati

- Selezionare **Gestisci documenti** per caricare i file pertinenti.
- Quando si apre il riquadro a comparsa Gestisci documenti, selezionare **Aggiungi documento,** quindi selezionare il file dal sistema. Tipi di file accettati:
    - Documenti (.doc, .xls, .ppt, .txt, .pdf)
    - Immagini (.jpg, .png)
    - Video (.mkv)
    - File compressi (.zip, .rar)
- Una volta risolto il file nel riquadro, selezionare **Chiudi**, che salva automaticamente il file allegato. Vedrai quindi il file elencato sotto **Documenti caricati**.
- Per scaricare o eliminare il documento, selezionare **Gestisci documenti sotto** l'elenco dei documenti. Nel riquadro a comparsa selezionare la riga del documento per evidenziarla, quindi selezionare **Scarica** o **Elimina.**

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>Note sull'implementazione, note di test e note aggiuntive

- Per aggiungere note in uno di questi tre campi, selezionare Modifica note **di implementazione** sotto uno di questi campi.
- Quando si apre il riquadro a comparsa, immettere le note nel campo di testo, quindi selezionare **Salva e chiudi.**
- Per modificare le note, selezionare **Modifica note di implementazione,** apportare le modifiche, quindi selezionare Salva **e chiudi.**

Non esiste alcun limite di caratteri nei campi note. È consigliabile tenere brevi le note in modo che sia possibile visualizzarle e modificarle facilmente dalla pagina dei dettagli delle azioni di miglioramento.

## <a name="change-improvement-action-status"></a>Modificare lo stato dell'azione di miglioramento

È possibile registrare lo stato e la data dell'implementazione e lo stato e la data del test per ogni azione di miglioramento. I **campi di** **implementazione e stato** del test possono essere modificati da qualsiasi utente con autorizzazioni di modifica, non solo dalla persona assegnata.

Per modificare lo stato di un'azione di miglioramento, selezionare **Modifica stato** nella sezione superiore sinistra della pagina dei dettagli. Di seguito sono riportati i campi disponibili e le opzioni di stato:

- **Stato implementazione**
    - **Non implementato** - Azione non ancora implementata
    - **Implementato** - Azione implementata
    - **Implementazione alternativa:** selezionare questa opzione se sono stati usati altri strumenti di terze parti o se sono state eseguite altre azioni non incluse nei suggerimenti microsoft
    - **Pianificato** - Azione pianificata per l'implementazione
    - **Fuori ambito:** l'azione non è rilevante per l'organizzazione e non contribuisce al punteggio
- **Data di implementazione**: disponibile per selezionare quando lo stato di implementazione è "implementato" o "implementazione alternativa"
- **Stato test**: disponibile per selezionare quando lo stato di implementazione è "implementato" o "implementazione alternativa":
    - **Non valutato:** l'azione non è stata testata
    - **Superato** : l'implementazione è stata verificata da un valutatore
    - **Rischio basso non riuscito** - Test non riuscito, basso rischio
    - **Rischio medio non riuscito** - Test non riuscito, rischio medio
    - **Rischio elevato non superato:** test non riusciti, rischio elevato
    - **Fuori ambito:** l'azione non è in ambito per la valutazione e non contribuisce al punteggio
- **Data test**: alterna il popup del calendario per selezionare la data

Le azioni comuni vengono sincronizzate tra gruppi. Quando due valutazioni diverse nello stesso gruppo condividono azioni di miglioramento gestite dall'utente, tutti gli aggiornamenti apportati ai dettagli o allo stato di implementazione di un'azione verranno sincronizzati automaticamente con la stessa azione in qualsiasi altra valutazione del gruppo. Questa sincronizzazione consente di implementare un'unica azione di miglioramento e soddisfare diversi requisiti in più normative.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Assegnare un'azione di miglioramento al valutatore per il completamento

Dopo aver completato il lavoro, aver completato i test e caricato le prove, il passaggio successivo consiste nell'assegnare l'azione di miglioramento a un valutatore per la convalida. Il valutatore convalida il lavoro ed esamina la documentazione e seleziona lo stato del test appropriato.

**Se lo stato del test è impostato su "Superato":** l'azione è completa e i punti ottenuti mostrano i punti massimi raggiunti. I punti vengono quindi conteggiati per il punteggio di conformità complessivo.

Se lo stato del test è impostato su **"Non riuscito":** l'azione non soddisfa i requisiti e il valutatore può assegnarlo nuovamente all'utente appropriato per ulteriori attività.

## <a name="accepting-updates-to-improvement-actions"></a>Accettazione degli aggiornamenti per le azioni di miglioramento

Quando è disponibile un aggiornamento per un'azione di miglioramento, vedrai una notifica accanto al suo nome. Puoi accettare l'aggiornamento o rimandarlo in un secondo momento.

#### <a name="what-causes-an-update"></a>Cosa causa un aggiornamento

Un aggiornamento si verifica quando sono presenti modifiche relative al punteggio, all'automazione o all'ambito. Le modifiche possono comportare nuove linee guida per le azioni di miglioramento basate su modifiche normative o a causa di modifiche del prodotto. Solo le azioni di miglioramento gestite dalle organizzazioni ricevono notifiche di aggiornamento.

#### <a name="where-youll-see-assessment-update-notifications"></a>Dove vedrai le notifiche di aggiornamento della valutazione

Quando un'azione di miglioramento viene  aggiornata, viene visualizzata un'etichetta Aggiornamento in sospeso accanto al relativo nome nella pagina azioni di miglioramento e nella pagina dei dettagli delle valutazioni correlate.

Vai alla pagina dei dettagli dell'azione  di miglioramento e seleziona il pulsante Rivedi aggiornamento nel banner superiore per esaminare i dettagli sulle modifiche e accettare o rinviare l'aggiornamento.

#### <a name="review-update-to-accept-or-defer"></a>Rivedere l'aggiornamento per accettare o rinviare

Dopo aver **selezionato Rivedi** aggiornamento dalla pagina dei dettagli dell'azione di miglioramento, viene visualizzato un riquadro a comparsa sul lato destro dello schermo. Il riquadro a comparsa fornisce dettagli chiave sull'aggiornamento, ad esempio le valutazioni influenzate e le modifiche nel punteggio e nell'ambito.

Selezionare **Accetta aggiornamento** per accettare tutte le modifiche apportate all'azione di miglioramento. **Le modifiche accettate sono permanenti.**

> [!NOTE]
> Quando accetti un aggiornamento di un'azione, accetti anche gli aggiornamenti di altre versioni o istanze di questa azione. Gli aggiornamenti verranno propagati a livello di tenant per le azioni tecniche e verranno propagati a livello di gruppo per le azioni non tecniche.

Se si seleziona **Annulla,** l'aggiornamento non verrà applicato all'azione di miglioramento. Tuttavia, continuerai a visualizzare la notifica **di** aggiornamento in sospeso fino a quando non accetti l'aggiornamento.

**Perché è consigliabile accettare gli aggiornamenti**

L'accettazione degli aggiornamenti garantisce di disporre delle indicazioni più aggiornate sull'utilizzo delle soluzioni e sull'esecuzione di azioni di miglioramento appropriate per soddisfare i requisiti della certificazione a portata di mano.

**Motivo per cui potrebbe essere necessario rinviare un aggiornamento**

Se si sta completando una valutazione che include l'azione di miglioramento, è possibile assicurarsi di aver completato il lavoro prima di accettare l'aggiornamento. È possibile rinviare l'aggiornamento in un secondo momento selezionando **Annulla** nel riquadro a comparsa di revisione dell'aggiornamento.

#### <a name="accept-all-updates-at-once"></a>Accetta tutti gli aggiornamenti contemporaneamente

Se si dispone di più aggiornamenti e si desidera  accettarli tutti contemporaneamente, selezionare il collegamento Accetta tutti gli aggiornamenti nella parte superiore della tabella delle azioni di miglioramento. Verrà visualizzato un riquadro a comparsa che elenca il numero di azioni da aggiornare. Seleziona il **pulsante Accetta aggiornamenti** per applicare tutti gli aggiornamenti.

Si noti che quando si torna alla pagina delle azioni di miglioramento, è possibile che venga visualizzato un messaggio nella parte superiore della pagina in cui viene chiesto di aggiornare la pagina per il completamento degli aggiornamenti.

## <a name="export-a-report"></a>Esportare un report

Selezionare **Esporta** nell'angolo superiore sinistro dello schermo per scaricare un foglio di lavoro di Excel contenente tutte le azioni di miglioramento e le categorie di filtro visualizzate nella pagina delle azioni di miglioramento.