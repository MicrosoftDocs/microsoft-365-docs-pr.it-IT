---
title: Casi di gestione dei rischi Insider
description: Informazioni sui casi di gestione dei rischi Insider in Microsoft 365
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
ms.openlocfilehash: c128f9e0c5754305e8b4d785c6a88931bc3ea976
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988172"
---
# <a name="insider-risk-management-cases"></a>Casi di gestione dei rischi Insider

I casi sono alla base della gestione dei rischi insider e consentono di analizzare e agire in modo approfondito sui problemi generati dagli indicatori di rischio definiti nei criteri. I casi vengono creati manualmente dagli avvisi in situazioni in cui sono necessarie ulteriori azioni per risolvere un problema correlato alla conformità per un utente. Ogni caso ha come ambito un singolo utente e più avvisi per l'utente possono essere aggiunti a un caso esistente o a un nuovo caso. 

Dopo aver indagato sui dettagli di un caso, è possibile eseguire le azioni seguenti:

- invio di un avviso all'utente
- risoluzione del caso come innocuo
- condivisione del caso con l'istanza ServiceNow o con un destinatario di posta elettronica
- escalation del caso per un'indagine advanced eDiscovery

## <a name="cases-dashboard"></a>Dashboard casi

Il dashboard dei casi di **gestione dei rischi** Insider consente di visualizzare e intervenire sui casi. Ogni widget report nel dashboard visualizza le informazioni degli ultimi 30 giorni.

- **Casi attivi:** numero totale di casi attivi oggetto di indagine.
- **Casi negli ultimi 30 giorni:** numero totale di casi creati, ordinati in base allo *stato Attivo* *e Chiuso.*
- **Statistiche:** tempo medio dei casi attivi, elencato in ore, giorni o mesi.

Nella coda dei casi sono elencati tutti i casi attivi e chiusi per l'organizzazione, oltre allo stato corrente degli attributi del caso seguenti:

- **Nome del** caso: nome del caso, definito quando viene confermato un avviso e viene creato il caso.  
- **Status**: lo stato del caso, *Active* o *Closed.*
- **User**: l'utente per il caso. Se è abilitata l'anonimizzazione per i nomi utente, vengono visualizzate informazioni anonime.
- **Time case opened**: L'ora trascorsa dall'apertura del caso.
- **Totale avvisi criteri:** numero di corrispondenze dei criteri incluse nel caso. Questo numero può aumentare se vengono aggiunti nuovi avvisi al caso.
- **Last updated**: L'ora trascorsa dall'aggiunta di una nota sul caso o di una modifica nello stato del caso.
- **Last updated by**: Il nome dell'analista di gestione dei rischi Insider o dell'investigatore che ha aggiornato il caso per ultimo.

![Dashboard dei casi di gestione dei rischi Insider](../media/insider-risk-cases-dashboard.png)

Utilizzare il **controllo Ricerca** per cercare nomi di maiuscole e minuscole per testo specifico e utilizzare il filtro di maiuscole e minuscole per ordinare le maiuscole e le minuscole in base agli attributi seguenti:

- Stato
- Data/ora apertura, data di inizio e data di fine
- Last updated, start date, and end date

## <a name="filter-cases"></a>Casi di filtro

A seconda del numero e del tipo di criteri di gestione dei rischi Insider attivi nell'organizzazione, esaminare una coda di casi di grandi dimensioni può essere difficile. L'uso di filtri dei casi può aiutare gli analisti e gli investigatori a ordinare i casi in base a diversi attributi. Per filtrare gli avvisi nel **dashboard Casi,** selezionare il **controllo Filtro.** È possibile filtrare i casi in base a uno o più attributi:

- **Stato**: selezionare uno o più valori di stato per filtrare l'elenco dei casi. Le opzioni sono *Attiva e* *Chiusa.*
- **Caso di apertura:** selezionare le date di inizio e di fine per l'apertura del caso.
- **Last updated**: selezionare le date di inizio e di fine relative all'aggiornamento del caso.

## <a name="investigate-a-case"></a>Analizzare un caso

Un'analisi più approfondita degli avvisi di gestione dei rischi Insider è fondamentale per eseguire le azioni correttive appropriate. I casi di gestione dei rischi Insider sono lo strumento di gestione centrale per approfondire la cronologia delle attività dei rischi degli utenti e i dettagli degli avvisi e per esplorare il contenuto e i messaggi esposti ai rischi. Gli analisti e gli investigatori dei rischi usano i casi anche per centralizzare il feedback e le note delle recensioni e per elaborare la risoluzione dei casi.

La selezione di un caso apre gli strumenti di gestione dei casi e consente ad analisti e investigatori di indagare nei dettagli dei casi.

### <a name="case-overview"></a>Panoramica del caso

La **scheda Panoramica del caso** riepiloga l'attività degli avvisi e la cronologia del livello di rischio per il caso. 

- Il widget **Avvisi** mostra le corrispondenze dei criteri per il caso, tra cui lo stato dell'avviso, la gravità del rischio dell'avviso e il momento in cui è stato rilevato l'avviso. 
- Nel **grafico Cronologia livello di rischio** viene visualizzato il livello di rischio degli utenti negli ultimi 30 giorni. Il grafico a linee consente ad analisti e investigatori di vedere rapidamente la tendenza del rischio complessivo degli utenti nel tempo. 
- Il widget **Contenuto attività rischio** riepiloga i tipi di dati e il contenuto contenuti negli avvisi aggiunti al caso. Questo widget offre una visualizzazione all-up dell'intero contenuto e dei dati a rischio nel caso.

Il **riquadro Dettagli caso** è disponibile in tutte le schede di gestione dei casi e riepiloga i dettagli del caso per gli analisti e gli investigatori del rischio. Include le aree seguenti:

- **Nome del** caso : Nome del caso, con prefisso con un numero di sequenza del caso generato automaticamente e il nome del rischio associato al modello di criteri a cui corrisponde il primo avviso confermato. 
- **Stato del caso**: lo stato corrente del caso, *attivo* o *chiuso.*
- **Punteggio di rischio dell'utente:** il livello di rischio calcolato corrente dell'utente per il caso. Questo punteggio viene calcolato ogni 24 ore e utilizza i punteggi di rischio degli avvisi di tutti gli avvisi attivi associati all'utente.
- **Avvisi confermati:** elenco di avvisi per l'utente confermato per il caso.
- **Contenuto correlato:** elenco di contenuto, ordinato in base alle origini e ai tipi di contenuto. Ad esempio, per il contenuto degli avvisi per i casi in SharePoint Online, potrebbero essere elencati nomi di file o cartelle associati all'attività di rischio per gli avvisi nel caso.

![Dettagli del caso di gestione dei rischi Insider](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Avvisi

La **scheda Alerts** riepiloga gli avvisi correnti inclusi nel caso. I nuovi avvisi possono essere aggiunti a un caso esistente e verranno aggiunti alla coda **degli** avvisi non appena vengono assegnati. Nella coda sono elencati gli attributi di avviso seguenti:

- Stato
- Gravità
- Ora rilevata

Selezionare un avviso dalla coda per visualizzare la **pagina Dettagli** avviso.

Utilizzare il controllo di ricerca per cercare nei nomi degli avvisi testo specifico e utilizzare il filtro degli avvisi per ordinare i casi in base agli attributi seguenti:

- Stato
- Gravità
- Ora rilevata, data di inizio e data di fine

Utilizzare il controllo filtro per filtrare gli avvisi in base a diversi attributi, tra cui:

- **Stato:** selezionare uno o più valori di stato per filtrare l'elenco di avvisi. Le opzioni sono *Confirmed,* *Dismissed,* *Needs review* e *Resolved.*
- **Gravità: selezionare** uno o più livelli di gravità del rischio di avviso per filtrare l'elenco degli avvisi. Le opzioni disponibili *sono Alta,* *Media* e *Bassa.*
- **Ora rilevata:** selezionare le date di inizio e di fine per la creazione dell'avviso.
- **Criterio:** selezionare uno o più criteri per filtrare gli avvisi generati dai criteri selezionati.

### <a name="user-activity"></a>Attività utente

La **scheda Attività utente** è uno degli strumenti più potenti per l'analisi e l'analisi dei rischi interni per i casi nella soluzione di gestione dei rischi Insider. Questa scheda è strutturata per consentire la revisione rapida di un caso, inclusa una cronologia di tutti gli avvisi, tutti i dettagli degli avvisi, il punteggio di rischio corrente per l'utente nel caso e i controlli per intraprendere un'azione efficace per contenere i rischi nel caso.

![Attività utente di gestione dei rischi Insider](../media/insider-risk-user-activities.png)

1. **Filtri data e ora** dell'intervallo: per impostazione predefinita, gli ultimi sei mesi di avvisi confermati nel caso vengono visualizzati nel grafico Attività utente. È possibile filtrare facilmente la visualizzazione grafico con i controlli dispositivo di scorrimento a entrambe le estremità della finestra del grafico oppure definendo date di inizio e di fine specifiche nel controllo filtro grafico.
2. **Attività e dettagli degli avvisi per i rischi:** le attività di rischio vengono visualizzate visivamente come bolle colorate nel grafico Attività utente. Le bolle vengono create per diverse categorie di rischio e le dimensioni delle bolle sono proporzionali al numero di attività di rischio per la categoria. Selezionare una bolla per visualizzare i dettagli per ogni attività di rischio. I dettagli includono:
    - **Data** dell'attività di rischio.
    - Categoria **dell'attività di rischio.** Ad esempio, *i messaggi di posta elettronica* con allegati inviati all'esterno dell'organizzazione o i file scaricati da *SharePoint Online.*
    - **Punteggio di rischio** per l'avviso. Questo punteggio è il punteggio numerico per il livello di gravità del rischio di avviso.
    - Numero di eventi associati all'avviso. Sono inoltre disponibili collegamenti a ogni file o messaggio di posta elettronica associato all'attività di rischio.
3. **Legenda attività** di rischio: nella parte inferiore del grafico delle attività utente, una legenda con colori consente di determinare rapidamente la categoria di rischio per ogni avviso.
4. **Cronologia dell'attività di** rischio : viene elencata la cronologia completa di tutti gli avvisi di rischio associati al caso, inclusi tutti i dettagli disponibili nella corrispondente bolla di avviso.
5. **Azioni caso:** le opzioni per la risoluzione del caso sono disponibili sulla barra degli strumenti delle azioni del caso. È possibile risolvere un caso, inviare un avviso tramite posta elettronica all'utente o inoltrare il caso per un'indagine sui dati o sull'utente.

### <a name="activity-explorer-preview"></a>Esplora attività (anteprima)

>[!IMPORTANT]
>La scheda Esplora attività è disponibile nell'area di gestione dei casi per gli utenti che attivano eventi dopo che questa funzionalità è disponibile nell'organizzazione.

La **scheda Esplora attività** consente agli analisti e agli investigatori del rischio di esaminare i dettagli dell'attività associati agli avvisi di rischio. Ad esempio, nell'ambito delle azioni di gestione dei casi, gli investigatori e gli analisti potrebbero dover esaminare tutte le attività di rischio associate al caso per ulteriori dettagli. Con **Esplora attività,** i revisori possono esaminare rapidamente una sequenza temporale delle attività rischiose rilevate e identificare e filtrare tutte le attività di rischio associate agli avvisi.

Per altre informazioni su Esplora attività, vedi l'articolo [sugli avvisi per la gestione dei rischi Insider.](insider-risk-management-alerts.md#activity-explorer-preview)

### <a name="content-explorer"></a>Esplora contenuto

La **scheda Esplora contenuto** consente agli analisti e agli investigatori del rischio di esaminare le copie di tutti i singoli file e messaggi di posta elettronica associati agli avvisi di rischio. Ad esempio, se viene creato un avviso quando un utente scarica centinaia di file da SharePoint Online e l'attività attiva un avviso per i criteri, tutti i file scaricati per l'avviso vengono acquisiti e copiati nel caso di gestione dei rischi Insider dalle origini di archiviazione originali.

Esplora contenuto è uno strumento potente con funzionalità di ricerca e filtro di base e avanzate. Per altre informazioni sull'uso di Esplora contenuto, vedi Esplora contenuto per la gestione dei rischi [Insider.](insider-risk-management-content-explorer.md)

![Caso di gestione dei rischi Insider Esplora contenuto](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Note sul caso

La **scheda Note caso** nel caso è in cui gli analisti e gli investigatori del rischio condividono commenti, feedback e informazioni dettagliate sul proprio lavoro per il caso. Le note sono aggiunte permanenti a un caso e non possono essere modificate o eliminate dopo il salvataggio della nota. Quando un caso viene creato da un avviso, i commenti immessi nella finestra di dialogo Conferma avviso e crea un caso di rischio **Insider** vengono aggiunti automaticamente come nota del caso.

Nel dashboard delle note del caso vengono visualizzate le note dell'utente che ha creato la nota e l'ora trascorsa dal salvataggio della nota. Per cercare una parola chiave specifica nel campo di testo della nota del caso, usa il pulsante **Cerca** nel dashboard del caso e immetti una parola chiave specifica.

Per aggiungere una nota a un caso:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la **scheda** Casi.
2. Selezionare un caso, quindi selezionare la **scheda Note caso.**
3. Selezionare **Aggiungi nota caso.**
4. Nella finestra **di dialogo Aggiungi nota caso** digitare la nota per il caso. Selezionare **Salva** per aggiungere la nota al caso oppure **scegliere** Annulla chiudi senza salvare la nota nel caso.

### <a name="contributors"></a>Collaboratori

Nella **scheda Collaboratori,** nel caso, gli analisti e gli investigatori del rischio possono aggiungere altri revisori al caso. Per impostazione predefinita, tutti gli utenti assegnati ai ruoli **Insider Risk Management Analysts** e **Insider Risk Management Investigators** sono elencati come collaboratori per ogni caso attivo e chiuso. Solo gli utenti a cui è assegnato il ruolo **Insider Risk Management Investigators** sono autorizzati a visualizzare file e messaggi in Esplora contenuto.

È possibile concedere l'accesso temporaneo a un caso aggiungendo un utente come collaboratore. I collaboratori dispongono di tutti i controlli di gestione dei casi per il caso specifico, ad eccezione di:

- Autorizzazione per confermare o ignorare gli avvisi
- Autorizzazione per modificare i collaboratori per i casi
- Autorizzazione per la visualizzazione di file e messaggi in Esplora contenuto

Per aggiungere un collaboratore a un caso:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la **scheda** Casi.
2. Selezionare un caso, quindi selezionare la **scheda Collaboratori.**
3. Selezionare **Aggiungi collaboratore.**
4. Nella finestra **di dialogo Aggiungi collaboratore** iniziare a digitare il nome dell'utente che si desidera aggiungere e quindi selezionare l'utente nell'elenco degli utenti suggeriti. Questo elenco viene generato da Azure Active Directory della sottoscrizione tenant.
5. Selezionare **Aggiungi** per aggiungere l'utente come collaboratore oppure **scegliere** Annulla per chiudere la finestra di dialogo senza aggiungere l'utente come collaboratore.

## <a name="case-actions"></a>Azioni caso

Gli analisti e gli investigatori del rischio possono intervenire su un caso in uno dei diversi metodi, a seconda della gravità del caso, della cronologia dei rischi dell'utente e delle linee guida per i rischi dell'organizzazione. In alcune situazioni potrebbe essere necessario inoltrare un caso a un utente o a un'indagine sui dati per collaborare con altre aree dell'organizzazione e approfondire le attività di rischio. La gestione dei rischi Insider è strettamente integrata con altre soluzioni di conformità di Microsoft 365 per facilitare la gestione della risoluzione end-to-end.

### <a name="send-email-notice"></a>Inviare un avviso tramite posta elettronica

Nella maggior parte dei casi, le azioni degli utenti che creano avvisi di rischio Insider sono accidentali o accidentali. L'invio di un promemoria all'utente tramite posta elettronica è un metodo efficace per documentare la revisione e l'azione dei casi ed è un metodo per ricordare agli utenti i criteri aziendali o per puntare a una formazione più aggiornata. Gli avvisi vengono generati dai modelli [di avviso creati per](insider-risk-management-notices.md) l'infrastruttura di gestione dei rischi Insider.

È importante ricordare che l'invio di un avviso tramite posta elettronica a un utente **_non_* _ risolve il caso come _Closed*. In alcuni casi, è possibile lasciare aperto un caso dopo aver inviato un avviso a un utente per cercare altre attività di rischio senza aprire un nuovo caso. Se si desidera risolvere un caso dopo l'invio di un avviso, è necessario selezionare il caso **Risolvi** come passaggio successivo dopo l'invio di un avviso.

Per inviare un avviso all'utente assegnato a un caso:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la **scheda** Casi.
2. Selezionare un caso, quindi selezionare il **pulsante** Invia avviso tramite posta elettronica sulla barra degli strumenti delle azioni del caso.
3. Nella finestra **di dialogo Invia avviso tramite posta** elettronica selezionare il controllo **a** discesa Scegliere un modello di avviso per selezionare il modello di avviso per l'avviso. Questa selezione precompilierà gli altri campi dell'avviso.
4. Esaminare i campi dell'avviso e aggiornarsi in base alle esigenze. I valori immessi qui sovrascriveranno i valori del modello.
5. Selezionare **Invia** per inviare l'avviso all'utente oppure **scegliere** Annulla per chiudere la finestra di dialogo senza inviare l'avviso all'utente. Tutti gli avvisi inviati vengono aggiunti alla coda delle note del caso nel dashboard **note del** caso.

### <a name="escalate-for-investigation"></a>Escalation per l'indagine

Inoltrare il caso per l'indagine degli utenti in situazioni in cui è necessaria un'ulteriore revisione legale per l'attività di rischio dell'utente. Questa escalation apre un nuovo caso di Advanced eDiscovery nell'organizzazione di Microsoft 365. Advanced eDiscovery fornisce un flusso di lavoro end-to-end per conservare, raccogliere, rivedere, analizzare ed esportare contenuti reattivi alle indagini legali interne ed esterne dell'organizzazione. Consente inoltre al team legale di gestire l'intero flusso di lavoro di notifica della conservazione per comunicare con i responsabile coinvolti in un caso. L'assegnazione di un revisore come responsabile in un caso di Advanced eDiscovery creato da un caso di gestione dei rischi insider consente al team legale di intraprendere le azioni appropriate e gestire l'archiviazione del contenuto. Per ulteriori informazioni sui casi di Advanced eDiscovery, vedere [Panoramica di Advanced eDiscovery in Microsoft 365.](overview-ediscovery-20.md)

Per inoltrare un caso a un'indagine utente:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la **scheda** Casi.
2. Seleziona un caso, quindi seleziona il pulsante Escalation **per** indagine sulla barra degli strumenti delle azioni del caso.
3. Nella finestra **di dialogo Escalation per l'analisi** immettere un nome per la nuova indagine utente. Se necessario, immettere le note sul caso e selezionare **Escalation.**
4. Esaminare i campi dell'avviso e aggiornarsi in base alle esigenze. I valori immessi qui sovrascriveranno i valori del modello.
5. Selezionare **Conferma per** creare il caso di indagine dell'utente o Annulla per chiudere la finestra di dialogo senza creare un nuovo caso di indagine dell'utente. 

Dopo che il caso di gestione dei rischi Insider è stato inoltrato a un nuovo caso di indagine utente, è possibile esaminare il nuovo caso nell'area **eDiscovery** avanzato nel Centro conformità  >   Microsoft 365.

### <a name="run-automated-tasks-with-power-automate-flows-for-the-case"></a>Eseguire attività automatizzate con i flussi di Power Automate per il caso

Utilizzando i flussi di Power Automate consigliati, gli investigatori e gli analisti del rischio possono intervenire rapidamente per:

- Richiedere informazioni alle risorse umane o aziendali su un utente in un caso di rischio Insider
- Notificare al responsabile quando un utente ha un avviso di rischio Insider
- Aggiungere un promemoria del calendario per il follow-up su un caso di rischio Insider
- Creare un record per un caso di gestione dei rischi Insider in ServiceNow

Per eseguire, gestire o creare flussi di Power Automate per un caso di gestione dei rischi Insider:

1. Selezionare **Automate sulla** barra degli strumenti delle azioni del caso. 
2. Scegliere il flusso di Power Automate da eseguire, quindi selezionare **Esegui flusso.** 
3. Al termine del flusso, selezionare **Fine.**

Per ulteriori informazioni sui flussi di Power Automate per la gestione dei rischi Insider, vedere [Introduzione alle impostazioni di gestione dei rischi Insider.](insider-risk-management-settings.md#power-automate-flows-preview)

### <a name="view-or-create-a-microsoft-teams-team-for-the-case"></a>Visualizzare o creare un team di Microsoft Teams per il caso

Quando l'integrazione di Microsoft Teams per la gestione dei rischi Insider è abilitata nelle impostazioni, viene creato automaticamente un team di Microsoft Teams ogni volta che viene confermato un avviso e viene creato un caso. Gli investigatori e gli analisti dei rischi possono aprire rapidamente Microsoft Teams e passare direttamente al team per un caso selezionando Visualizza **team di Microsoft Teams** sulla barra degli strumenti delle azioni del caso.

Per i casi aperti prima di abilitare l'integrazione di Microsoft Team, gli investigatori e gli analisti del rischio possono creare un nuovo team di Microsoft Teams per un caso selezionando Crea **team di Microsoft Teams** sulla barra degli strumenti delle azioni del caso.

Quando un caso viene risolto, il team microsoft associato verrà archiviato automaticamente (nascosto e trasformato in sola lettura).

Per ulteriori informazioni su Microsoft Teams per la gestione dei rischi Insider, vedere Introduzione alle [impostazioni di gestione dei rischi Insider.](insider-risk-management-settings.md#microsoft-teams-preview)

### <a name="share-the-case"></a>Condividere il caso

La condivisione di un caso di gestione dei rischi Insider consente agli investigatori e agli analisti del rischio di collaborare facilmente con altri stakeholder della conformità nell'organizzazione. È possibile condividere rapidamente un collegamento a un caso di gestione dei rischi Insider con gli stakeholder esterni dall'area di gestione dei casi. Per accedere al caso di gestione dei rischi Insider dal collegamento, le parti interessate devono essere incluse in uno qualsiasi dei gruppi di ruoli di gestione dei rischi Insider.

>[!NOTE]
>Grazie per il feedback e il supporto durante l'anteprima del connettore ServiceNow. We've decided to end the preview of ServiceNow connector and discontinue support in insider risk management on November 30, 2020. Stiamo valutando attivamente metodi alternativi per fornire ai clienti l'integrazione di ServiceNow nella gestione dei rischi insider.

Sono disponibili le opzioni di condivisione seguenti:

- **ServiceNow:** dopo aver configurato il connettore ServiceNow di Microsoft 365 per l'organizzazione di Microsoft 365, è possibile condividere facilmente un collegamento al caso, aprire un evento imprevisto o richiedere una modifica con l'organizzazione ServiceNow. Per condividere il caso con ServiceNow, selezionare **Share**  >  **ServiceNow nell'azione** del caso. L'integrazione di ServiceNow con i supporti per la gestione dei rischi Insider include le seguenti informazioni e azioni sul caso:
    - **Nome attività**: Nome della nuova attività ServiceNow.
    - **Task description**: La descrizione per la nuova attività ServiceNow. Questo campo di descrizione modificabile include automaticamente un collegamento al caso di gestione dei rischi Insider.
    - **Tipo di attività:** il tipo di attività per la nuova attività ServiceNow, evento *imprevisto* *o richiesta di modifica.*
    - **Priority**: la priorità per la nuova attività ServiceNow, *planning,* *low,* *moderate,* *high* o *critical.*
    - **Scadenza:** la data richiesta per il completamento dell'attività ServiceNow.

![Condivisione della gestione dei rischi Insider con ServiceNow](../media/insider-risk-share-servicenow.png)

- **Posta** elettronica: condivide un collegamento al caso di gestione dei rischi Insider in un messaggio di posta elettronica. È possibile scegliere qualsiasi client di posta elettronica configurato localmente con questa opzione di condivisione. Per condividere il collegamento del caso con la posta elettronica, selezionare **Condividi** messaggio di  >  **posta elettronica** dalla barra degli strumenti delle azioni del caso.
- **Copia collegamento:** copia un collegamento al caso di gestione dei rischi Insider negli Appunti. Per copiare il collegamento del caso negli Appunti, seleziona **Il**  >  **collegamento Condividi copia** dalla barra degli strumenti delle azioni del caso.

### <a name="resolve-the-case"></a>Risolvere il caso

Dopo che gli analisti e gli investigatori del rischio hanno completato la revisione e l'indagine, un caso può essere risolto per agire su tutti gli avvisi attualmente inclusi nel caso. La risoluzione di un caso aggiunge una classificazione della risoluzione, modifica lo stato del caso in *Chiuso* e i motivi dell'azione di risoluzione vengono aggiunti automaticamente alla coda delle note del caso nel dashboard note **del** caso. I casi vengono risolti come uno dei seguenti:

- **Benign:** la classificazione per i casi in cui gli avvisi di corrispondenza dei criteri vengono valutati come a basso rischio, non grave o falso positivo.
- **Violazione dei criteri confermata:** la classificazione per i casi in cui gli avvisi di corrispondenza dei criteri vengono valutati come rischiosi, gravi o il risultato di intenti dannosi.

Per risolvere un caso:

1. Nel Centro [conformità Microsoft 365](https://compliance.microsoft.com)passare a **Gestione dei rischi Insider** e selezionare la **scheda** Casi.
2. Selezionare un caso, quindi fare clic sul pulsante Risolvi **caso** sulla barra degli strumenti delle azioni del caso.
3. Nella finestra **di dialogo Risolvi caso** selezionare il controllo a discesa Risolvi **come** per selezionare la classificazione della risoluzione per il caso. Le opzioni sono **Benign** o **Confirmed policy violation.**
4. Nella finestra **di dialogo Risolvi** caso immettere i motivi della classificazione della risoluzione nel campo di **testo** Azione eseguita.
5. Selezionare **Risolvi** per chiudere il caso o **Annulla** per chiudere la finestra di dialogo senza risolvere il caso.
