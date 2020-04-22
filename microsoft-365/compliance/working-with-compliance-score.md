---
title: Utilizzo del Punteggio di conformità Microsoft
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
description: Informazioni su come utilizzare gli strumenti di flusso di lavoro in Microsoft Compliance score per facilitare la gestione della conformità per l'organizzazione.
ms.openlocfilehash: 8bef3e09decede679d5d0667360ba87b7cd7e6ad
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626222"
---
# <a name="working-with-microsoft-compliance-score-preview"></a>Utilizzo del Punteggio di conformità Microsoft (anteprima)

In questo articolo viene illustrato come utilizzare gli elementi chiave del Punteggio di conformità. Vengono fornite informazioni su come utilizzare le **azioni di miglioramento** per gestire il flusso di lavoro di conformità. Verrà inoltre illustrato come utilizzare le informazioni sulle pagine **soluzioni** e **valutazioni** e come produrre report.

## <a name="manage-your-workflow-with-improvement-actions"></a>Gestire il flusso di lavoro con azioni di miglioramento

Le **azioni di miglioramento** centralizzano le attività di conformità. Ogni azione di miglioramento fornisce indicazioni dettagliate sull'implementazione che consentono di allineare le normative e i criteri di protezione dei dati. Le azioni possono essere assegnate agli utenti dell'organizzazione per eseguire il lavoro di implementazione e testing. È inoltre possibile archiviare la documentazione, le note e gli aggiornamenti dello stato del record all'interno dell'azione di miglioramento.

## <a name="view-your-improvement-actions"></a>Visualizzare le azioni di miglioramento

Il dashboard del Punteggio di conformità consente di visualizzare le **azioni di miglioramento principali**, ovvero quelle con i punti più disponibili che affrontano i problemi più importanti.

Per visualizzare tutte le azioni di miglioramento nella pagina **azioni di miglioramento** , selezionare la scheda **azioni di miglioramento** nel dashboard. In alternativa, seleziona **Visualizza tutte le azioni di miglioramento** sotto l'elenco delle azioni di miglioramento chiave nel dashboard.

Se si dispone di un lungo elenco di azioni, potrebbe essere utile filtrare la visualizzazione. Selezionare **filtro** nell'angolo in alto a destra dell'elenco delle azioni. Quando viene visualizzato il riquadro dei **filtri** a comparsa, selezionare i criteri in base alle normative e agli standard, alla soluzione e al gruppo. È inoltre possibile personalizzare la visualizzazione selezionando **gruppo** nell'angolo in alto a destra. Dal menu a discesa, selezionare per visualizzare per gruppo, soluzione, categoria, tipo di azione o stato.

La visualizzazione predefinita per questa pagina non Mostra azioni di miglioramento con uno stato di test **superato**. Per visualizzare le azioni che hanno superato il testing, selezionare la casella **passata** nel riquadro dei **filtri** a comparsa. Solo le azioni con uno stato di prova del conteggio **superato** verso il punteggio.

Nella pagina azioni di miglioramento vengono visualizzate le seguenti coordinate per ogni azione di miglioramento:

- **Impatto sul punteggio**: i punti in base ai quali il punteggio complessivo aumenterà al termine dell'azione
- **Regolamenti**: il regolamento o la norma pertinente all'azione
- **Gruppo**: gruppo a cui è stata assegnata l'azione
- **Solutions**: la soluzione in cui è possibile accedere per eseguire l'azione
- **Valutazioni**: la valutazione (che consente di organizzare i controlli per soddisfare un determinato obiettivo di conformità) in cui si trova l'azione
- **Categorie**: la categoria relativa alla protezione dei dati (ad esempio, protezione delle informazioni, gestione di dispositivi e così via)
- **Stato del test**:
    - **None** -non è stato registrato alcun aggiornamento di stato
    - **Non valutato** : il testing non è stato avviato
    - **Non nell'ambito** -è escluso dal calcolo del Punteggio di conformità e non aumenta il Punteggio
    - Il testing **parzialmente testato** non è ancora stato completato
    - Non è stato verificato un errore **elevato** dei test di esecuzione e il rischio di non conformità con lo standard applicabile è elevato
    - L'implementazione **passata** ha testato correttamente
- **Rilevato**: Visualizza i punti ottenuti al di fuori del massimo che potrebbe essere guadagnato

### <a name="improvement-actions-details"></a>Dettagli sulle azioni di miglioramento

Per ogni azione di miglioramento è presente una pagina dei dettagli. In questa pagina sono disponibili istruzioni dettagliate per l'implementazione per il completamento delle azioni consigliate per soddisfare gli standard e i requisiti normativi riportati nell'intestazione **a colpo d'occhio** .

La pagina dei dettagli è la posizione in cui è possibile avviare l'azione consigliata. È inoltre possibile assegnare il lavoro a un altro utente, aggiornare lo stato e allegare note e documentazione.

Per visualizzare la pagina dei dettagli dell'azione di miglioramento:

1. Passare alla pagina azioni di miglioramento.
2. Fare clic o toccare un punto qualsiasi della riga dell'azione di miglioramento desiderata, che apre la pagina dei dettagli.

È possibile visualizzare facilmente l'azione di miglioramento successiva o precedente nell'elenco selezionando la freccia verso l'alto o verso il basso nell'angolo in alto a destra dello schermo. Se l'elenco è stato filtrato nella pagina azioni di miglioramento, lo spostamento verso l'alto o verso il basso consentirà di passare all'elemento successivo all'interno dell'elenco filtrato.

## <a name="assign-improvement-actions"></a>Assegnare azioni di miglioramento

Per iniziare a lavorare sull'implementazione di un'azione di miglioramento, è possibile eseguire autonomamente il lavoro o assegnarlo a un altro utente. La persona assegnata potrebbe essere:

- Il proprietario di un criterio di business
- Un implementatore IT
- Un altro dipendente che ha la responsabilità di eseguire l'attività

Dopo aver identificato la persona appropriata, accertarsi che dispongano di un [ruolo](compliance-score-setup.md#set-user-permissions-and-assign-roles) sufficiente in Score Compliance (compliance Administrator, Compliance Data Administrator, Security Administrator o Global Administrator) per eseguire il lavoro, procedere come segue: 

1. Dalla pagina dei dettagli sulle azioni di miglioramento, selezionare **modifica stato** vicino alla sezione in alto a sinistra dello schermo. 

2. Nel riquadro a comparsa modifica stato fare clic o toccare nella casella **assegnata a** , in cui viene inserito un elenco di utenti **consigliato** . È possibile selezionare l'utente dall'elenco oppure digitare l'indirizzo di posta elettronica della persona a cui si desidera assegnare l'azione.

3. Selezionare **Salva e Chiudi** per completare l'assegnazione. L'utente assegnato riceverà un messaggio di posta elettronica a cui è stata assegnata l'azione di miglioramento e potrà quindi aprire l'azione di miglioramento dal proprio dashboard.

L'utente assegnato può quindi eseguire le operazioni consigliate descritte nelle istruzioni di implementazione.

## <a name="perform-work-and-store-documentation"></a>Eseguire la documentazione relativa al lavoro e all'archiviazione

Quando si esegue il lavoro di implementazione, è possibile caricare file e note direttamente nell'azione di miglioramento nella sezione **note e documentazione** .  Questo ambiente è un repository sicuro e centralizzato che consente di dimostrare la soddisfazione dei controlli per soddisfare gli standard e i regolamenti di conformità. Qualsiasi utente con accesso in sola lettura può leggere il contenuto in questa sezione. Solo gli utenti con diritti di modifica possono caricare e scaricare file e immettere o modificare note.

Nei campi della sezione **note e documentazione** sono inclusi i seguenti:

**Documenti caricati**

- Selezionare **Gestisci documenti** per caricare eventuali file rilevanti.
- Quando viene aperto il riquadro dell'icona Gestisci documenti, selezionare **Aggiungi documento**, quindi selezionare il file dal sistema. Tipi di file accettati: 
  - Documenti (. doc,. xls,. ppt,. txt,. pdf)
  - Immagini (. jpg,. png)
  - Video (con estensione MKV)
  - File compressi (con estensione zip,. rar)
- Dopo aver risolto il file nel riquadro, selezionare **Chiudi,** che salva automaticamente il file allegato. Verrà visualizzato il file elencato sotto i **documenti caricati.** 
- Per scaricare o eliminare il documento, selezionare **Gestisci documenti** da sotto l'elenco dei documenti. Nel riquadro a comparsa, fare clic o toccare la riga del documento per evidenziarla, quindi selezionare **Scarica** o **Elimina.**

**Implementazione, test e note aggiuntive**

- Per aggiungere note in uno di questi tre campi, selezionare **modifica note di implementazione** al di sotto di uno di questi campi.
- Quando viene aperto il riquadro a comparsa, immettere note nel campo di testo, quindi selezionare **Salva e Chiudi**.
- Per modificare le note, selezionare **modifica note di implementazione**, apportare le modifiche, quindi selezionare **Salva e Chiudi**.

Nei campi Notes non è presente alcun limite di caratteri. È consigliabile mantenere le note brevi in modo che sia possibile visualizzarle e modificarle facilmente dalla pagina dei dettagli sulle azioni di miglioramento.

## <a name="change-improvement-action-status"></a>Stato azione miglioramento modifiche

È possibile registrare lo stato di implementazione e la data e lo stato e la data del test per ogni azione di miglioramento. Di seguito sono riportati i campi e le opzioni di stato disponibili:

- **Stato dell'implementazione**: selezionare una delle opzioni di stato seguenti:
    - **Non implementato** : azione non ancora implementata
    - **Implementato** -azione implementata
    - **Implementazione alternativa** : selezionare questa opzione se sono stati utilizzati altri strumenti di terze parti o sono state eseguite altre azioni non incluse nei consigli di Microsoft
    - **Pianificata** -azione pianificata per l'implementazione
    - **Non nell'ambito** : opzione per le azioni non rilevanti per la propria organizzazione. Se si seleziona questo stato, l'azione viene esclusa dal punteggio. la deselezione includerà l'azione nel Punteggio
- **Data di implementazione**: campo Available quando lo stato dell'implementazione è impostato su **implementato** o su un' **implementazione alternativa**; attiva o disattiva la finestra del calendario per selezionare la data
- **Stato del test**: selezionare una delle opzioni seguenti:
    - **Non valutato** : il testing non è stato avviato
    - L'implementazione **passata**ha testato correttamente
    - **Esito negativo** dei test a basso rischio non riuscito, rischio basso
    - **Esito** negativo del test di rischio medio non riuscito, rischio medio
    - **Errore di test ad alto rischio** non riuscito, ad alto rischio
- **Data di testing**: passare dal menu a comparsa calendario per selezionare la data

> [!NOTE]
> I campi di stato di implementazione e di testing possono essere modificati da qualsiasi utente con autorizzazioni di modifica, non solo dall'utente **assegnato** .

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Assegnare un'azione di miglioramento all'analizzatore per il completamento

Dopo aver completato il lavoro e aver caricato la prova, il passaggio successivo consiste nell'impostare lo stato e la data di implementazione e assegnare l'azione di miglioramento a un valutatore per la convalida.

Tra i tipi di consulenti sono inclusi i seguenti:

- Valutatori interni che eseguono la convalida dei controlli all'interno dell'organizzazione
- Valutatori esterni che esaminano, verificano e certificano la conformità, ad esempio organizzazioni indipendenti di terze parti che controllano i servizi cloud Microsoft

Il valutatore convalida il lavoro ed esamina la documentazione e seleziona lo stato di test appropriato.

**Se lo stato del test è "superato"**: l'azione è completa e i **punti ottenuti** mostrano il numero totale di punti possibili ottenuti e conteggiati verso il Punteggio di conformità globale.

**Se lo stato del test è un qualsiasi grado di "errore"**: l'azione non soddisfa i requisiti e il valutatore può assegnarlo all'utente appropriato per ulteriori operazioni.

## <a name="solutions-page"></a>Pagina soluzioni

La **pagina soluzioni** è un altro punto di partenza per lavorare sulle azioni di miglioramento per aumentare il punteggio. 

Per accedere alla pagina soluzioni, seleziona la scheda **soluzioni** nel dashboard o seleziona **Visualizza tutte le soluzioni** al di sotto delle **soluzioni che influiscono sul punteggio** nella sezione in alto a destra del dashboard.

La pagina soluzioni consente di visualizzare la quota dei punti guadagnati e potenziali organizzati dalla soluzione. La visualizzazione dei punti rimanenti e le azioni di miglioramento da questa visualizzazione consentono di comprendere quali soluzioni richiedono un'attenzione più immediata.

### <a name="filtering-your-solutions-view"></a>Applicazione del filtro alla visualizzazione soluzioni

Per filtrare la visualizzazione delle soluzioni:

1. Selezionare **filtro** nell'angolo in alto a sinistra dell'elenco di valutazioni.
2. Nel riquadro **filtri** a comparsa, inserire un controllo accanto ai criteri desiderati (standard e normative, soluzione, tipo di azione, gruppo di Compliance Manager, categoria).
3. Selezionare il pulsante **applica** . Il riquadro del filtro si chiude e vedrai la visualizzazione filtrata.

È inoltre possibile modificare la visualizzazione per visualizzare le valutazioni per gruppo, prodotto o regolamento selezionando il tipo di raggruppamento dal menu a discesa **gruppo** sopra l'elenco valutazioni.

### <a name="taking-actions-from-the-solutions-page"></a>Esecuzione di azioni dalla pagina soluzioni

Nella pagina soluzioni vengono visualizzate le soluzioni dell'organizzazione connesse alle azioni di miglioramento. Nella tabella sono elencati i contributi di ogni soluzione per il Punteggio globale, i punti di miglioramento dei punteggi conseguiti e possibili all'interno di tale soluzione e il numero di azioni per migliorare che sono state raggruppate in tale soluzione in grado di aumentare il punteggio.

È possibile eseguire un'azione da questa schermata in due modi:

1. Nella riga della soluzione desiderata fare clic sul numero di collegamenti ipertestuali nella colonna **azioni rimanenti** . Verrà visualizzata una visualizzazione filtrata della schermata azioni di miglioramento che mostra le azioni di miglioramento non testate per tale soluzione.

2. Nella riga della soluzione desiderata fare clic su **Apri**nella colonna **Apri soluzione** . Verrà visualizzata la soluzione o la posizione nei centri di sicurezza e conformità di Microsoft 365 e Office 365, in cui è possibile eseguire l'azione consigliata.

## <a name="assessments-page"></a>Pagina valutazioni

Nella pagina valutazioni sono elencate le valutazioni selezionate per la gestione dell'organizzazione. Il denominatore del Punteggio di conformità è determinato da tutte le valutazioni registrate. Le altre valutazioni aggiunte, le azioni di miglioramento più visibili nella pagina azioni di miglioramento e più alto è il denominatore del punteggio.

Per accedere alla pagina valutazioni, selezionare la scheda **valutazioni** nel dashboard.

In questa pagina, è possibile visualizzare rapidamente informazioni importanti su ogni valutazione:

- **Status**: lo stato verso il completamento di tutte le azioni di miglioramento nella valutazione verrà elencato come:
    - **Non conforme**: le azioni di miglioramento non sono state implementate e sono state testate con esito positivo. l'attività non è ancora iniziata
    - **In Progress**: è in corso l'implementazione o la verifica delle azioni di miglioramento; ad esempio, un'azione di miglioramento nella valutazione è stata assegnata per il lavoro, è in fase di implementazione e test
- **Progress Assessment**: la percentuale del lavoro eseguito verso il completamento finale della valutazione, misurata in base al numero di controlli testati correttamente.
- **Azioni gestite dal cliente**: il numero di azioni completate per soddisfare l'implementazione dei controlli gestiti dal cliente
- **Azioni gestite da Microsoft**: il numero di azioni completate per soddisfare l'implementazione dei controlli gestiti da Microsoft
- **Gruppo di valutazione**: nome del gruppo creato, in cui si trova la valutazione
- **Servizi correlati**: servizio Microsoft 365 associato
- **Normative correlate**: lo standard normativo, la politica o la legge che la valutazione cerca di soddisfare

### <a name="default-assessments"></a>Valutazioni predefinite

Per impostazione predefinita, nella pagina valutazioni verrà visualizzata la valutazione della linea di base per la protezione dei dati di Microsoft 365. Il Punteggio di conformità fornisce anche diverse valutazioni preconfigurate ([vedere l'elenco completo](compliance-score.md#templates)). È possibile aggiungere ulteriori valutazioni per coprire ulteriori normative e standard in Compliance Manager.

### <a name="managing-assessments"></a>Gestione delle valutazioni

Durante l'anteprima pubblica, si passerà allo strumento Compliance Manager per incassare, personalizzare e gestire le proprie valutazioni.

Nella pagina **valutazioni** in Punteggio conformità, selezionare **Gestisci valutazioni in Compliance Manager** all'inizio dell'elenco valutazioni. Questo collegamento porta al dashboard di **valutazione** in Compliance Manager.

L'altro collegamento all'inizio dell'elenco valutazioni, **Microsoft Actions in Compliance Manager**, consente di visualizzare il Dashboard delle **informazioni sui controlli** in Compliance Manager con i controlli Microsoft che contribuiscono al Punteggio di conformità.

### <a name="filtering-your-assessments-view"></a>Filtrare la visualizzazione delle valutazioni

Per filtrare la visualizzazione delle valutazioni:

1. Selezionare **filtro** nell'angolo in alto a sinistra dell'elenco di valutazioni.
2. Nel riquadro **filtri** a comparsa, inserire un controllo accanto ai criteri desiderati (standard e regolamenti, gruppo Compliance Manager).
3. Selezionare il pulsante **applica** . Il riquadro del filtro si chiude e si vedrà la visualizzazione filtrata.

È inoltre possibile modificare la visualizzazione per visualizzare le valutazioni per gruppo, prodotto o regolamento selezionando il tipo di raggruppamento dal menu a discesa **gruppo** sopra l'elenco valutazioni.

### <a name="managing-improvement-actions-within-an-assessment"></a>Gestione delle azioni di miglioramento all'interno di una valutazione

Nell'elenco valutazione, nella colonna **azioni gestite dal cliente** , selezionare il testo collegato nella riga della valutazione desiderata. Viene visualizzata una visualizzazione filtrata della pagina azioni di miglioramento che mostra le azioni all'interno di tale valutazione.

## <a name="reporting"></a>Reporting

È possibile esportare un rapporto di tutte le azioni di miglioramento nel punteggio di conformità. Nella pagina **azioni di miglioramento** selezionare **Esporta** nell'angolo superiore sinistro dello schermo, sopra l'elenco delle azioni. In questo modo verrà generato un foglio di lavoro di Excel con tutte le azioni di miglioramento e le categorie di filtro visualizzate nella pagina **azioni di miglioramento** .

È inoltre possibile esportare un report da Compliance Manager attenendosi alla procedura seguente:

1. In Compliance Manager, andare al dashboard **info Controls** .
2. Verrà visualizzata una scheda **valutazione** e una scheda **modello** .  
3. Per esportare una valutazione: selezionare la scheda **valutazione** . utilizzare i menu a discesa **gruppo** e **valutazione** per selezionare la valutazione che si desidera esportare. Seleziona **Esporta** vicino all'angolo in alto a destra dello schermo. Verrà scaricato un file di Excel. Include un elenco di azioni, raggruppate per controllo, con l'implementazione e i dettagli dei test.
4. Per esportare un modello: selezionare la scheda **modello** e scegliere il modello che si desidera esportare dal menu a discesa **modello** . Seleziona **Esporta** vicino all'angolo in alto a destra dello schermo. Verrà scaricato un file di Excel. Include un elenco di azioni, raggruppate per controllo, con l'implementazione e i dettagli dei test.