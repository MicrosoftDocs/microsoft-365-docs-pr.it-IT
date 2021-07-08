---
title: Casi di gestione dei rischi insider
description: Informazioni sui casi di gestione dei rischi insider in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 19fd44633f03a7797484ecaa6a15159e24da7fbf
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326820"
---
# <a name="insider-risk-management-cases"></a>Casi di gestione dei rischi insider

I casi sono il cuore della gestione dei rischi insider e consentono di analizzare e agire in modo approfondito sui problemi generati dagli indicatori di rischio definiti nei criteri. I casi vengono creati manualmente dagli avvisi in situazioni in cui sono necessarie ulteriori azioni per risolvere un problema correlato alla conformità per un utente. Ogni caso ha come ambito un singolo utente e più avvisi per l'utente possono essere aggiunti a un caso esistente o a un nuovo caso. 

Dopo aver indagato sui dettagli di un caso, è possibile eseguire le azioni seguenti:

- invio di un avviso all'utente
- risoluzione del caso come benigno
- condivisione del caso con l'istanza serviceNow o con un destinatario di posta elettronica
- escalation del caso per un'indagine Advanced eDiscovery ricerca

Guarda il [video insider Risk Management Investigation and Escalation](https://www.youtube.com/watch?v=UONUSmkRC8s) per una panoramica di come i casi vengono esaminati e gestiti nella gestione dei rischi insider.

## <a name="cases-dashboard"></a>Dashboard casi

Il dashboard dei casi di **gestione dei rischi insider** consente di visualizzare e agire sui casi. Ogni widget di report nel dashboard visualizza informazioni per gli ultimi 30 giorni.

- **Casi attivi**: numero totale di casi attivi oggetto di indagine.
- **Casi negli ultimi 30 giorni**: numero totale di casi creati, ordinati in base allo *stato Attivo* *e Chiuso.*
- **Statistiche**: tempo medio dei casi attivi, elencato in ore, giorni o mesi.

Nella coda dei casi sono elencati tutti i casi attivi e chiusi per l'organizzazione, oltre allo stato corrente degli attributi del caso seguenti:

- **Nome caso**: Nome del caso, definito quando viene confermato un avviso e viene creato il caso.  
- **Status**: lo stato del caso, *Active* o *Closed.*
- **User**: l'utente per il caso. Se è abilitata l'anonimizzazione per i nomi utente, vengono visualizzate informazioni anonime.
- **Time case opened**: L'ora trascorsa dall'apertura del caso.
- **Totale avvisi criteri**: numero di corrispondenze dei criteri incluse nel caso. Questo numero può aumentare se vengono aggiunti nuovi avvisi al caso.
- **Case last updated**: Tempo passato dopo l'aggiunta di una nota sul caso o di una modifica nello stato del caso.
- **Last updated by**: Nome dell'analista o dell'investigatore della gestione dei rischi insider che ha aggiornato il caso per l'ultima volta.

![Dashboard dei casi di gestione dei rischi insider](../media/insider-risk-cases-dashboard.png)

Utilizzare il **controllo Search** per cercare nomi di maiuscole e minuscole per testo specifico e utilizzare il filtro maiuscole/minuscole per ordinare i casi in base agli attributi seguenti:

- Stato
- Orario apertura del caso, data di inizio e data di fine
- Ultimo aggiornamento, data di inizio e data di fine

## <a name="filter-cases"></a>Casi di filtro

A seconda del numero e del tipo di criteri di gestione dei rischi insider attivi nell'organizzazione, la revisione di una grande coda di casi può essere difficile. L'uso di filtri dei casi può aiutare analisti e investigatori a ordinare i casi in base a diversi attributi. Per filtrare gli avvisi nel **dashboard Casi,** selezionare il **controllo Filtro.** È possibile filtrare i casi in base a uno o più attributi:

- **Stato:** selezionare uno o più valori di stato per filtrare l'elenco dei casi. Le opzioni sono *Attivo* e *Chiuso.*
- **Time case opened**: Selezionare le date di inizio e di fine per l'apertura del caso.
- **Last updated**: Selezionare le date di inizio e di fine per l'aggiornamento del caso.

## <a name="investigate-a-case"></a>Analizzare un caso

Un'analisi approfondita degli avvisi di gestione dei rischi insider è fondamentale per eseguire azioni correttive appropriate. I casi di gestione dei rischi insider sono lo strumento di gestione centrale per approfondire la cronologia delle attività di rischio degli utenti, i dettagli degli avvisi, la sequenza degli eventi di rischio e per esplorare il contenuto e i messaggi esposti ai rischi. Gli analisti e gli investigatori del rischio usano anche i casi per centralizzare il feedback e le note delle recensioni e per elaborare la risoluzione dei casi.

La selezione di un caso ne apre gli strumenti di gestione e consente ad analisti e investigatori di approfondirne i dettagli.

### <a name="case-overview"></a>Informazioni generali sul caso

La **scheda Panoramica del** caso riepiloga i dettagli del caso per gli analisti e gli investigatori del rischio. Include le informazioni seguenti nell'area **Informazioni su questo** caso

- **Status**: lo stato corrente del caso, Attivo o Chiuso.
- **Case created on**: Data e ora di creazione del caso.
- **Punteggio di rischio dell'utente**: Livello di rischio calcolato corrente dell'utente per il caso. Questo punteggio viene calcolato ogni 24 ore e utilizza i punteggi di rischio degli avvisi di tutti gli avvisi attivi associati all'utente.
- **Email**: Alias di posta elettronica dell'utente per il caso.
- **Organizzazione o reparto:** l'organizzazione o il reparto a cui è assegnato l'utente.
- **Nome manager**: Nome del responsabile dell'utente.
- **Indirizzo di posta elettronica** del responsabile: alias di posta elettronica del responsabile dell'utente.

La **scheda Panoramica caso** include anche una sezione **Avvisi** che include le informazioni seguenti sugli avvisi di corrispondenza dei criteri associati al caso:

- **Criteri corrisponde:** il nome del criterio di gestione dei rischi insider associato agli avvisi di corrispondenza per l'attività degli utenti.
- **Status**: Stato dell'avviso.
- **Severity**: Gravità dell'avviso.
- **Time detected**: Tempo passato dopo la generazione dell'avviso.

![Dettagli del caso di gestione dei rischi insider](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Avvisi

La **scheda Avvisi** riepiloga gli avvisi correnti inclusi nel caso. I nuovi avvisi possono essere aggiunti a un caso esistente e verranno aggiunti alla coda **degli** avvisi quando vengono assegnati. Nella coda sono elencati gli attributi di avviso seguenti:

- Stato
- Gravità
- Tempo rilevato

Selezionare un avviso dalla coda per visualizzare la **pagina Dettagli** avviso.

Utilizzare il controllo di ricerca per cercare i nomi degli avvisi per testo specifico e utilizzare il filtro degli avvisi per ordinare i casi in base agli attributi seguenti:

- Stato
- Gravità
- Orario rilevamento, data di inizio e data di fine

Utilizzare il controllo filtro per filtrare gli avvisi in base a diversi attributi, tra cui:

- **Stato:** selezionare uno o più valori di stato per filtrare l'elenco degli avvisi. Le opzioni sono *Confermato*, *Ignorato*, *Da rivedere* e *Risolto*.
- **Gravità:** selezionare uno o più livelli di gravità del rischio di avviso per filtrare l'elenco degli avvisi. Le opzioni sono *Elevato*, *Medio* e *Basso*.
- **Ora rilevata:** selezionare le date di inizio e di fine per la creazione dell'avviso.
- **Criterio:** selezionare uno o più criteri per filtrare gli avvisi generati dai criteri selezionati.

### <a name="user-activity"></a>Attività utente

La scheda **Attività utente** è uno degli strumenti più potenti per l'analisi e l'indagine interna dei rischi per i casi nella soluzione di gestione dei rischi Insider. Questa scheda è strutturata per consentire la revisione rapida di un caso, inclusa una cronologia di tutti gli avvisi, i dettagli degli avvisi, il punteggio di rischio corrente per l'utente nel caso, la sequenza di eventi di rischio e i controlli per intraprendere azioni efficaci per contenere i rischi nel caso.

![Attività utente di gestione dei rischi Insider](../media/insider-risk-user-activities.png)

1. **Filtri tempo:** per impostazione predefinita, gli ultimi sei mesi di avvisi confermati nel caso vengono visualizzati nel grafico Attività utente. È possibile filtrare facilmente la visualizzazione grafico selezionando le schede *6 Mesi*, *3* mesi o *1* mese nel grafico a bolle.
2. **Attività e dettagli degli avvisi di** rischio : le attività di rischio vengono visualizzate visivamente come bolle colorate nel grafico Attività utente. Le bolle vengono create per diverse categorie di rischio e le dimensioni delle bolle sono proporzionali al numero di attività di rischio per la categoria. Selezionare una bolla per visualizzare i dettagli per ogni attività di rischio. I dettagli includono:
    - **Data** dell'attività del rischio.
    - Categoria **di attività di rischio**. Ad esempio, *i messaggi* di posta elettronica con allegati inviati all'esterno dell'organizzazione o i file scaricati *da SharePoint Online.*
    - **Punteggio del rischio** per l'avviso. Questo corrisponde al punteggio numerico per il livello di gravità del rischio di avviso.
    - Numero di eventi associati all'avviso. Sono inoltre disponibili collegamenti a ogni file o messaggio di posta elettronica associato all'attività di rischio.
3. **Sequenza dei rischi (anteprima):** l'ordine cronologico delle attività rischiose è un aspetto importante dell'indagine sui rischi e l'identificazione di queste attività correlate è una parte importante della valutazione dei rischi complessivi per l'organizzazione. Le attività di avviso correlate vengono visualizzate con linee di connessione per evidenziare che queste attività sono associate a un'area di rischio più ampia. Questa visualizzazione delle attività può aiutare gli investigatori a "connettere letteralmente i puntini" per le attività di rischio che potrebbero essere state viste come eventi isolati o una sola volta. Selezionare una bolla nella sequenza per visualizzare i dettagli per tutte le attività di rischio associate. I dettagli includono:

    - **Nome** della sequenza.
    - **Data** o **intervallo di date** della sequenza.
    - **Punteggio di rischio** per la sequenza. Questo punteggio è il punteggio numerico per la sequenza dei livelli di gravità del rischio di avviso combinati per ogni attività correlata nella sequenza.
    - **Numero di eventi associati a ogni avviso nella sequenza**. Sono inoltre disponibili collegamenti a ogni file o messaggio di posta elettronica associato a ogni attività di rischio.
    - **Mostra le attività in sequenza**. Visualizza la sequenza come linea di evidenziazione nel grafico a bolle ed espande i dettagli dell'avviso per visualizzare tutti gli avvisi correlati nella sequenza.

4. **Legenda attività di** rischio : nella parte inferiore del grafico attività utente, una legenda con codice a colori consente di determinare rapidamente la categoria di rischio per ogni avviso.
5. **Cronologia attività di rischio**: viene elencata la cronologia completa di tutti gli avvisi di rischio associati al caso, inclusi tutti i dettagli disponibili nella corrispondente bolla di avviso.
6. **Azioni caso:** le opzioni per la risoluzione del caso sono disponibili sulla barra degli strumenti delle azioni del caso. È possibile risolvere un caso, inviare un avviso tramite posta elettronica all'utente o inoltrare il caso per un'indagine su dati o utenti.

### <a name="activity-explorer-preview"></a>Esplora attività (anteprima)

> [!IMPORTANT]
> La scheda Esplora attività è disponibile nell'area di gestione dei casi per gli utenti che attivano eventi dopo che questa funzionalità è disponibile nell'organizzazione.

La **scheda Esplora attività** consente agli analisti e agli investigatori del rischio di esaminare i dettagli dell'attività associati agli avvisi di rischio. Ad esempio, nell'ambito delle azioni di gestione dei casi, gli investigatori e gli analisti potrebbero dover esaminare tutte le attività di rischio associate al caso per ulteriori dettagli. Con **Esplora attività,** i revisori possono esaminare rapidamente una sequenza temporale delle attività rischiose rilevate e identificare e filtrare tutte le attività di rischio associate agli avvisi.

Per altre informazioni su Esplora attività, vedi l'articolo [Avvisi per la gestione dei rischi Insider.](insider-risk-management-activities.md#activity-explorer-preview)

### <a name="content-explorer"></a>Esplora contenuto

La scheda **Esplora contenuto** consente agli analisti e agli investigatori del rischio di esaminare le copie di tutti i singoli file e messaggi di posta elettronica associati agli avvisi di rischio. Ad esempio, se viene creato un avviso quando un utente scarica centinaia di file da SharePoint Online e l'attività attiva un avviso sui criteri, tutti i file scaricati per l'avviso vengono acquisiti e copiati nel caso di gestione dei rischi insider dalle origini di archiviazione originali.

Esplora contenuto è uno strumento potente con funzionalità di ricerca e filtro di base e avanzate. Per altre informazioni sull'uso di Esplora contenuto, vedi [Gestione dei rischi insider Esplora contenuto.](insider-risk-management-content-explorer.md)

![Caso di gestione dei rischi insider Esplora contenuto](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Note del caso

La **scheda Note caso** nel caso è in cui gli analisti e gli investigatori del rischio condividono commenti, feedback e informazioni dettagliate sul proprio lavoro per il caso. Le note sono aggiunte permanenti a un caso e non possono essere modificate o eliminate dopo essere state salvate. Quando un caso viene creato da un avviso, i commenti inseriti nella finestra di dialogo **Conferma avviso e crea caso di gestione del rischio Insider** vengono aggiunti automaticamente come nota al caso.

Nel dashboard delle note del caso vengono visualizzate le note dell'utente che ha creato la nota e il tempo passato dopo il salvataggio della nota. Per cercare una parola chiave specifica nel campo di testo della nota del caso, usa il pulsante **Cerca** nel dashboard del caso e immetti una parola chiave specifica.

Per aggiungere una nota a un caso:

1. Nella finestra [Centro conformità Microsoft 365](https://compliance.microsoft.com), vai a **Gestione dei rischi Insider** e seleziona la **scheda** Casi.
2. Selezionare un caso, quindi selezionare la **scheda Note caso.**
3. Selezionare **Aggiungi nota caso**.
4. Nella finestra **di dialogo Aggiungi nota caso** digitare la nota per il caso. Selezionare **Salva** per aggiungere la nota al caso oppure **scegliere** Annulla chiudi senza salvare la nota nel caso.

### <a name="contributors"></a>Collaboratori

La scheda **Collaboratori** nel caso è il luogo dove gli analisti e gli investigatori del rischio possono aggiungere altri revisori al caso. Per impostazione predefinita, tutti gli utenti assegnati ai ruoli **Insider Risk Management Analysts** e **Insider Risk Management Investigators** sono elencati come collaboratori per ogni caso attivo e chiuso. Solo gli utenti assegnati al **ruolo Insider Risk Management Investigators** dispongono dell'autorizzazione per visualizzare file e messaggi in Esplora contenuto.

L'accesso temporaneo a un caso può essere concesso aggiungendo un utente come collaboratore. I collaboratori dispongono di tutti i controlli di gestione dei casi per il caso specifico, ad eccezione di:

- Autorizzazione a confermare o ignorare gli avvisi
- Autorizzazione a modificare i collaboratori per i casi
- Autorizzazione per visualizzare file e messaggi in Esplora contenuto

Per aggiungere un collaboratore a un caso:

1. Nella finestra [Centro conformità Microsoft 365](https://compliance.microsoft.com), vai a **Gestione dei rischi Insider** e seleziona la **scheda** Casi.
2. Selezionare un caso, quindi selezionare la **scheda Collaboratori.**
3. Selezionare **Aggiungi collaboratore**.
4. Nella finestra **di dialogo Aggiungi** collaboratore iniziare a digitare il nome dell'utente che si desidera aggiungere e quindi selezionare l'utente nell'elenco degli utenti suggeriti. Questo elenco viene generato dall'Azure Active Directory della sottoscrizione tenant.
5. Selezionare **Aggiungi** per aggiungere l'utente come collaboratore oppure scegliere **Annulla** per chiudere la finestra di dialogo senza aggiungere l'utente come collaboratore.

## <a name="case-actions"></a>Azioni sul caso

Gli analisti e gli investigatori del rischio possono intervenire su un caso in uno dei diversi metodi, a seconda della gravità del caso, della cronologia dei rischi dell'utente e delle linee guida per i rischi dell'organizzazione. In alcune situazioni potrebbe essere necessario inoltrare un caso a un utente o a un'indagine sui dati per collaborare con altre aree dell'organizzazione e approfondire le attività a rischio. La gestione dei rischi insider è strettamente integrata con altre Microsoft 365 di conformità per facilitare la gestione della risoluzione end-to-end.

### <a name="send-email-notice"></a>Invia avviso tramite posta elettronica

Nella maggior parte dei casi, le azioni degli utenti che creano avvisi di rischio insider sono accidentali o accidentali. L'invio di un avviso di promemoria all'utente tramite posta elettronica è un metodo efficace per documentare la revisione e l'azione dei casi ed è un metodo per ricordare agli utenti i criteri aziendali o per inviarli a corsi di aggiornamento. Gli avvisi vengono generati dai modelli [di avviso creati per](insider-risk-management-notices.md) l'infrastruttura di gestione dei rischi insider.

È importante ricordare che l'invio di un avviso tramite posta elettronica a un utente ***non** risolve il caso come _Closed*. In alcuni casi, è possibile lasciare aperto un caso dopo aver inviato un avviso a un utente per cercare altre attività di rischio senza aprire un nuovo caso. Se si desidera risolvere un caso dopo aver inviato una notifica, è necessario selezionare **Risolvi caso** come passaggio successivo all'invio di una notifica.

Per inviare un avviso all'utente assegnato a un caso:

1. Nella finestra [Centro conformità Microsoft 365](https://compliance.microsoft.com), vai a **Gestione dei rischi Insider** e seleziona la **scheda** Casi.
2. Seleziona un caso, quindi seleziona il pulsante Invia avviso **tramite posta** elettronica sulla barra degli strumenti delle azioni del caso.
3. Nella finestra **di dialogo Invia avviso tramite posta** elettronica selezionare il controllo a discesa **Scegliere** un modello di avviso per selezionare il modello di avviso per l'avviso. Questa selezione precompilierà gli altri campi dell'avviso.
4. Esaminare i campi di avviso e aggiornarsi in base alle esigenze. I valori immessi qui sostituiscono i valori del modello.
5. Selezionare **Invia** per inviare l'avviso all'utente oppure scegliere **Annulla** per chiudere la finestra di dialogo senza inviare l'avviso all'utente. Tutti gli avvisi inviati vengono aggiunti alla coda delle note del caso nel dashboard **note caso.**

### <a name="escalate-for-investigation"></a>Escalation dell'indagine

Inoltrare il caso per le indagini degli utenti in situazioni in cui è necessaria un'ulteriore revisione legale per l'attività di rischio dell'utente. Questa operazione apre un nuovo caso di Advanced eDiscovery nell'organizzazione Microsoft 365. Advanced eDiscovery offre un flusso di lavoro end-to-end per conservare, raccogliere, rivedere, analizzare ed esportare contenuti rilevanti per le indagini legali interne ed esterne dell'organizzazione. Consente anche al team legale di gestire l'intero flusso di lavoro per le notifiche di blocco a fini giudiziari per comunicare con i responsabili coinvolti in un caso. Assegnare un revisore come responsabile in un caso di Advanced eDiscovery creato da un caso di gestione del rischio Insider aiuta il team legale a intraprendere le azioni appropriate e gestire la conservazione dei contenuti. Per maggiori informazioni sui casi di Advanced eDiscovery, consultare la [Panoramica di Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md).

Per inoltrare un caso a un'indagine utente:

1. Nella finestra [Centro conformità Microsoft 365](https://compliance.microsoft.com), vai a **Gestione dei rischi Insider** e seleziona la **scheda** Casi.
2. Seleziona un caso, quindi seleziona il pulsante Escalation **per** indagine sulla barra degli strumenti delle azioni del caso.
3. Nella finestra **di dialogo Escalation per l'indagine** immettere un nome per la nuova indagine utente. Se necessario, immettere le note sul caso e selezionare **Escalation.**
4. Esaminare i campi di avviso e aggiornarsi in base alle esigenze. I valori immessi qui sostituiscono i valori del modello.
5. Selezionare **Conferma per** creare il caso di indagine dell'utente oppure scegliere **Annulla** per chiudere la finestra di dialogo senza creare un nuovo caso di indagine utente.

Dopo l'escalation del caso di gestione dei rischi insider a un nuovo caso di indagine degli utenti, è possibile esaminare il nuovo caso nell'area **eDiscovery**  >  **avanzata** nella Centro conformità Microsoft 365.

### <a name="run-automated-tasks-with-power-automate-flows-for-the-case"></a>Eseguire attività automatizzate con flussi Power Automate per il caso

Utilizzando i flussi Power Automate di rischio consigliati, gli investigatori e gli analisti del rischio possono agire rapidamente per:

- Richiedere informazioni alle risorse umane o aziendali su un utente in un caso di rischio insider
- Notificare al responsabile quando un utente ha un avviso di rischio insider
- Creare un record per un caso di gestione dei rischi insider in ServiceNow
- Notificare agli utenti quando vengono aggiunti a un criterio di rischio insider

Per eseguire, gestire o creare flussi Power Automate per un caso di gestione dei rischi insider:

1. Seleziona **Automatizza** sulla barra degli strumenti delle azioni del caso. 
2. Scegliere il Power Automate da eseguire, quindi selezionare **Esegui flusso.** 
3. Al termine del flusso, selezionare **Fatto.**

Per ulteriori informazioni sui flussi Power Automate per la gestione dei rischi insider, vedere Introduzione alle impostazioni di gestione dei rischi [insider.](insider-risk-management-settings.md#power-automate-flows-preview)

### <a name="view-or-create-a-microsoft-teams-team-for-the-case"></a>Visualizzare o creare un team Microsoft Teams per il caso

Quando Microsoft Teams'integrazione per la gestione dei rischi insider è abilitata nelle impostazioni, viene creato automaticamente un team Microsoft Teams ogni volta che viene confermato un avviso e viene creato un caso. Gli investigatori e gli analisti dei rischi possono aprire rapidamente Microsoft Teams e passare direttamente al team per un caso selezionando Visualizza Microsoft Teams **team** sulla barra degli strumenti delle azioni del caso.

Per i casi aperti prima di abilitare l'integrazione di Microsoft Team, gli investigatori e gli analisti dei rischi possono creare un nuovo team di Microsoft Teams per un caso selezionando Crea **team di** Microsoft Teams sulla barra degli strumenti delle azioni del caso.

Quando un caso viene risolto, il team Microsoft associato verrà automaticamente archiviato (nascosto e trasformato in sola lettura).

Per ulteriori informazioni sulle Microsoft Teams per la gestione dei rischi insider, vedere Introduzione alle impostazioni di gestione dei rischi [insider.](insider-risk-management-settings.md#microsoft-teams-preview)

### <a name="resolve-the-case"></a>Risolvere il caso

Dopo che gli analisti e gli investigatori del rischio hanno completato la revisione e l'indagine, è possibile risolvere un caso per agire su tutti gli avvisi attualmente inclusi nel caso. La risoluzione di un caso aggiunge una classificazione di risoluzione, modifica lo stato del caso su *Chiuso* e i motivi dell'azione di risoluzione vengono aggiunti automaticamente alla coda delle note del caso nel dashboard **note caso.** I casi vengono contrassegnati come segue:

- **Benign**: classificazione per i casi in cui gli avvisi di corrispondenza dei criteri vengono valutati come a basso rischio, non grave o falso positivo.
- **Violazione dei criteri confermata:** classificazione per i casi in cui gli avvisi di corrispondenza dei criteri vengono valutati come rischiosi, gravi o il risultato di intenti dannosi.

Per risolvere un caso:

1. Nella finestra [Centro conformità Microsoft 365](https://compliance.microsoft.com), vai a **Gestione dei rischi Insider** e seleziona la **scheda** Casi.
2. Seleziona un caso, quindi seleziona il pulsante **Risolvi caso** sulla barra degli strumenti delle azioni del caso.
3. Nella finestra **di dialogo Risolvi** caso selezionare il controllo **a** discesa Risolvi come per selezionare la classificazione della risoluzione per il caso. Le opzioni sono **Benign** o **Confirmed policy violation.**
4. Nella finestra **di dialogo Risolvi** caso immettere i motivi della classificazione della risoluzione nel campo di **testo** Azione eseguita.
5. Selezionare **Risolvi** per chiudere il caso o **Annulla** per chiudere la finestra di dialogo senza risolvere il caso.
