---
title: Esaminare e correggere gli avvisi di conformità delle comunicazioni
description: Esaminare e correggere gli avvisi di conformità della comunicazione in Microsoft 365.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: f214c1fcfa8a68695ca0c32a9807972a71ba7612
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087161"
---
# <a name="investigate-and-remediate-communication-compliance-alerts"></a>Esaminare e correggere gli avvisi di conformità delle comunicazioni

Dopo aver configurato i criteri di conformità della comunicazione, si inizierà a ricevere avvisi nel centro conformità di Microsoft 365 per i problemi dei messaggi che soddisfano le condizioni di criteri. Seguire le istruzioni del flusso di lavoro qui per esaminare e correggere i problemi di avviso.

## <a name="investigate-alerts"></a>Esaminare gli avvisi

Il primo passaggio per esaminare i problemi rilevati dai criteri consiste nell'esaminare gli avvisi di conformità della comunicazione nel centro conformità di Microsoft 365. Sono presenti diverse aree nell'area della soluzione per la conformità delle comunicazioni che consentono di esaminare rapidamente gli avvisi, a seconda del modo in cui si preferisce visualizzare il raggruppamento degli avvisi:

- **Pagina Criteri di conformità della comunicazione**: quando si accede all' [https://compliance.microsoft.com](https://compliance.microsoft.com) utilizzo delle credenziali per un account di amministratore nell'organizzazione Microsoft 365, selezionare **conformità comunicazione** per visualizzare la pagina **criteri** di conformità comunicazione. In questa pagina vengono visualizzati i criteri di conformità della comunicazione configurati per l'organizzazione Microsoft 365 e i collegamenti ai modelli di criteri consigliati. Ogni criterio elencato include il numero di avvisi che devono essere esaminati, i numeri di elementi decrescenti e risolti e lo stato corrente del criterio. Se si seleziona un criterio, vengono visualizzati tutti gli avvisi in sospeso per le corrispondenze al criterio, selezionare un avviso specifico per avviare la pagina dei dettagli del criterio e avviare le azioni di correzione.
- **Avvisi**: passare a avvisi di **conformità della comunicazione**  >  **Alerts** per visualizzare gli ultimi 30 giorni di avvisi raggruppati in base alle corrispondenze di criteri. Questa visualizzazione consente di visualizzare rapidamente quali criteri di conformità della comunicazione stanno generando la maggior parte degli avvisi ordinati per gravità. Per avviare le azioni di correzione, selezionare il criterio associato all'avviso per avviare la pagina dei **Dettagli del criterio** . Dalla pagina **dei dettagli del criterio** , è possibile esaminare un riepilogo delle attività nella pagina **Panoramica** , esaminare e agire sui messaggi di avviso nella pagina **in sospeso** oppure esaminare la cronologia degli avvisi chiusi nella pagina **risolta** .
- **Report**: passare ai **Communication compliance**  >  **report** di conformità della comunicazione per visualizzare i widget report di conformità comunicazione. Ogni widget fornisce una panoramica delle attività e degli Stati di conformità della comunicazione, tra cui l'accesso a informazioni più approfondite sulle corrispondenze di criteri e le azioni di correzione.

### <a name="using-filters"></a>Utilizzo di filtri

Il passaggio successivo consiste nell'ordinare i messaggi in modo che sia più facile esaminare gli avvisi. Dalla pagina dei **Dettagli del criterio** , la conformità alla comunicazione supporta il filtro a più livelli per diversi campi dei messaggi che consentono di analizzare e rivedere rapidamente i messaggi con le corrispondenze di criteri. Il filtro è disponibile per gli elementi in sospeso e risolti per ogni criterio configurato. È possibile configurare le query di filtro per un criterio o configurare e salvare query di filtro personalizzate e predefinite per l'utilizzo in ogni criterio specifico. Dopo aver configurato i campi per un filtro, verranno visualizzati i campi del filtro visualizzato nella parte superiore della coda dei messaggi di avviso che è possibile configurare per i valori di filtro specifici.

Per un elenco completo dei filtri e dettagli sul campo, vedere [filtri](communication-compliance-feature-reference.md#filters) nell'articolo di riferimento per le caratteristiche.

#### <a name="to-configure-a-filter"></a>Per configurare un filtro

1. Accedere [https://compliance.microsoft.com](https://compliance.microsoft.com) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro conformità di Microsoft 365, passare a **conformità comunicazione**.

3. Selezionare la scheda **criteri** e quindi selezionare un criterio per l'analisi, fare doppio clic per aprire la pagina **criteri** .

4. Nella pagina **criterio** selezionare la scheda **in sospeso** o **risolta** per visualizzare gli elementi per il filtro.

5. Selezionare il controllo **filtri** per aprire la pagina dei dettagli sui **filtri** .

6. Selezionare una o più caselle di controllo per abilitare i filtri per questi avvisi. È possibile scegliere tra numerosi filtri, tra cui *Data*, *mittente*, *oggetto/titolo*, *classificatori* e altro ancora.

7. Se si desidera salvare il filtro selezionato come filtro predefinito, fare clic su **Salva con nome predefinito**. Se si desidera utilizzare questo filtro come filtro salvato, fare clic su **fine**.

8. Se si desidera salvare i filtri selezionati come query di filtro, fare clic su **Salva il controllo query** dopo aver configurato almeno un valore di filtro. Immettere un nome per la query del filtro e selezionare **Salva**. Questo filtro è disponibile per essere utilizzato solo per questo criterio ed è elencato nella sezione **query di filtro salvate** della pagina dei dettagli sui **filtri** .

    ![Controlli Dettagli filtro conformità di comunicazione](../media/communication-compliance-filter-detail-controls.png)

### <a name="using-near-and-exact-duplicate-analysis"></a>Utilizzo dell'analisi duplicata vicina ed esatta

I criteri di conformità della comunicazione analizzano e pregruppo i duplicati del messaggio vicino ed esatto senza ulteriori passaggi di configurazione. Questa visualizzazione consente di agire rapidamente su messaggi simili uno-a-uno o come gruppo, riducendo il carico di indagine dei messaggi per i revisori. Quando vengono rilevati duplicati, **i duplicati e/** o i controlli **duplicati esatti** vengono visualizzati nella barra degli strumenti azione di correzione. Questa visualizzazione non è disponibile se sono stati trovati duplicati vicini o esatti.

#### <a name="to-remediate-duplicates"></a>Per correggere i duplicati

1. Accedere [https://compliance.microsoft.com](https://compliance.microsoft.com) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro conformità di Microsoft 365, passare a **conformità comunicazione**.

3. Selezionare la scheda **criteri** e quindi selezionare un criterio per l'analisi, fare doppio clic per aprire la pagina **criteri** .

4. Nella pagina **criterio** selezionare la scheda **in sospeso** o **risolta** per visualizzare i messaggi duplicati.

5. Selezionare i controlli **quasi** duplicati o **duplicati esatti** per aprire la pagina dei dettagli duplicati.

6. Selezionare uno o più messaggi per i controlli azione di correzione per questi messaggi.

7. Selezionare **Risolvi**, **notifica**, **Inoltra** o **Scarica** per applicare l'azione ai messaggi duplicati selezionati come filtro predefinito.

8. Selezionare **Chiudi** dopo aver completato le operazioni di correzione dei messaggi.

    ![Controlli di conformità dei duplicati esatti della comunicazione](../media/communication-compliance-duplicates-controls.png)

## <a name="remediate-alerts"></a>Correggere gli avvisi

Indipendentemente dal punto in cui si inizia a esaminare gli avvisi o il filtro configurato, il passaggio successivo consiste nell'intervenire per correggere l'avviso. Avviare la correzione degli avvisi utilizzando il flusso di lavoro seguente nelle pagine dei **criteri** o degli **avvisi** .

### <a name="step-1-examine-the-message-basics"></a>Passaggio 1: esaminare le nozioni di base sui messaggi

 A volte risulta evidente dall'origine o dall'oggetto che un messaggio può essere immediatamente rimediato. Potrebbe essere che il messaggio sia falso o erroneamente corrispondente a un criterio e che sia necessario risolverlo come falsi positivi. Selezionare il controllo **false positive** per risolvere immediatamente l'avviso e rimuoverlo dalla coda degli avvisi in sospeso. Dalle informazioni di origine o mittente, potrebbe essere già possibile sapere in che modo il messaggio deve essere instradato o gestito in queste circostanze. Considerare l'utilizzo del **tag come** o l' **escalation** dei controlli per assegnare un tag ai messaggi applicabili o per inviare messaggi a un revisore designato.

![Controlli di correzione della conformità di comunicazione](../media/communication-compliance-remediation-controls.png)

### <a name="step-2-examine-the-message-details"></a>Passaggio 2: esaminare i dettagli del messaggio

Dopo aver esaminato le nozioni di base sui messaggi, è necessario aprire un messaggio per esaminare i dettagli e determinare ulteriori azioni di correzione. Selezionare un messaggio per visualizzare le informazioni complete sull'intestazione e sul corpo del messaggio. Sono disponibili diverse visualizzazioni per facilitare la scelta del corso di azione appropriato:

- **Visualizzazione origine**: questa visualizzazione è la visualizzazione standard dei messaggi comunemente visualizzata nella maggior parte delle piattaforme di messaggistica basate sul Web. Le informazioni di intestazione sono formattate nello stile normale e il corpo del messaggio supporta i file grafici incorporati e il testo con wrapping di Word.
- **Visualizzazione testo**: la visualizzazione del testo Visualizza una visualizzazione di solo testo numerata in linea del messaggio e include l'evidenziazione delle parole chiave nei messaggi e negli allegati per i termini corrispondenti ai criteri di conformità della comunicazione associati. L'evidenziazione delle parole chiave consente di analizzare rapidamente i messaggi e gli allegati lunghi per l'area di interesse. In alcuni casi, il testo evidenziato può trovarsi solo in allegati per i messaggi che soddisfano le condizioni dei criteri. I file incorporati non vengono visualizzati e la numerazione delle righe questa visualizzazione è utile per fare riferimento ai dettagli pertinenti tra più revisori.
- **Visualizzazione annotazioni**: questa visualizzazione consente ai revisori di aggiungere annotazioni direttamente sul messaggio salvato nella visualizzazione del messaggio.
- **Cronologia utenti**: visualizzazione cronologia utenti Visualizza tutti gli altri avvisi generati da tutti i criteri di conformità della comunicazione per l'utente che invia il messaggio.
- **Visualizzazione Dettagli messaggio**: visualizzazione avanzata dei metadati del messaggio e delle informazioni di configurazione.
- **Notifica rilevato modello (anteprima)**: molte azioni di molestie e bullismo nel tempo e implicano istanze ricorrenti dello stesso comportamento da parte di un utente. La notifica di *pattern detected* viene visualizzata nei dettagli degli avvisi e solleva l'attenzione sull'avviso. Il rilevamento dei modelli si basa su una base per criterio e valuta il comportamento negli ultimi 30 giorni quando almeno due messaggi vengono inviati allo stesso destinatario da un mittente. Gli investigatori e i revisori possono utilizzare questa notifica per identificare il comportamento ripetuto per valutare l'avviso in base alle esigenze.

    ![Controlli di visualizzazione messaggi di conformità di comunicazione](../media/communication-compliance-message-views.png)

### <a name="step-3-decide-on-a-remediation-action"></a>Passaggio 3: decidere in merito a un'azione di correzione

Dopo aver esaminato i dettagli del messaggio per l'avviso, è possibile scegliere diverse azioni correttive:

- **Risoluzione**: se si seleziona il controllo **Risolvi** , il messaggio viene rimosso immediatamente dalla coda degli **avvisi in sospeso** e non è possibile eseguire altre operazioni sul messaggio. Selezionando **Risolvi**, l'avviso è stato sostanzialmente chiuso senza ulteriore classificazione e non può essere riaperto per ulteriori azioni. Tutti i messaggi risolti vengono visualizzati nella scheda **risolti** .
- **False positive**: è sempre possibile risolvere un messaggio come falso positivo in qualsiasi momento durante il flusso di lavoro per la revisione dei messaggi. False positive indica che l'avviso è stato non utilizzabile o che l'avviso è stato generato erroneamente dal processo di avviso. Il messaggio non può essere riaperto e tutti i messaggi falsi positivi sono visualizzati nella scheda **risolti** .
- **Power automatizzate (Preview)**: utilizzare un flusso Power automatizzate per automatizzare le attività del processo per un messaggio di avviso. Per impostazione predefinita, la conformità alla comunicazione include la *gestione notifiche quando un utente dispone di un* modello di flusso di avviso per la conformità delle comunicazioni che i revisori possono utilizzare per automatizzare il processo di notifica per gli utenti con avvisi dei messaggi. Per ulteriori informazioni sulla creazione e sulla gestione dei flussi automatici di alimentazione in conformità alla comunicazione, vedere l'articolo di [riferimento sulla funzionalità di conformità della comunicazione](communication-compliance-feature-reference.md#power-automate-flows-preview) .
- **Tag As**: contrassegnare il messaggio come *conforme*, *non conforme* o come *discutibile* in relazione ai criteri e agli standard per l'organizzazione. L'aggiunta di tag e commenti di tagging consente di filtrare gli avvisi per i criteri per le escalation o come parte di altri processi di revisione interni. Dopo aver completato il tagging, è anche possibile scegliere di risolvere il messaggio per spostarlo fuori dalla coda di revisione in sospeso.
- **Notify**: è possibile utilizzare il controllo **Notify** per assegnare un modello di avviso personalizzato all'avviso e per inviare un avviso all'utente. Scegliere il modello di avviso appropriato configurato nell'area delle **impostazioni di conformità della comunicazione** e selezionare Invia per **inviare** un sollecito all'utente che ha inviato il messaggio e per risolvere il problema.
- **Escalation**: se si utilizza il controllo **escalation** , è possibile scegliere chi altro nell'organizzazione deve esaminare il messaggio. Scegliere da un elenco di revisori configurati nel criterio di conformità della comunicazione per inviare una notifica tramite posta elettronica che richiede ulteriori riesami dell'avviso del messaggio. Il revisore selezionato può utilizzare un collegamento nella notifica di posta elettronica per passare direttamente agli elementi che sono stati escalati per la revisione.
- **Escalation for investigation**: using the **escalation for investigation** Control, è possibile creare un nuovo [caso di Advanced eDiscovery](overview-ediscovery-20.md) per singoli o più messaggi. Verranno forniti un nome e note per il nuovo caso e l'utente che ha inviato il messaggio che corrisponde al criterio viene automaticamente assegnato come custode del caso. Non sono necessarie ulteriori autorizzazioni per gestire il caso. La creazione di un caso non risolve o crea un nuovo tag per il messaggio. È possibile selezionare un totale di 100 messaggi durante la creazione di un caso avanzato di eDiscovery durante il processo di correzione. Sono supportati i messaggi in tutti i canali di comunicazione controllati dalla conformità di comunicazione. Ad esempio, è possibile selezionare 50 chat di Microsoft teams, 25 messaggi di posta elettronica di Exchange Online e 25 messaggi di Yammer quando si apre un nuovo caso avanzato di eDiscovery per un utente.
- **Migliorare la classificazione (anteprima)**: gli avvisi creati dal tipo di classificazione corrispondono potrebbero essere necessari commenti e suggerimenti per ridurre al minimo i falsi positivi nell'organizzazione. Utilizzare il controllo **migliora classificazione** per fornire commenti e suggerimenti se la classificazione di conformità della comunicazione è valida o suggerire altri classificatori addestrabili per questo tipo di corrispondenza. È possibile verificare che i classificatori *corrispondano* o meno a *una corrispondenza* o che altri classificatori addestrabili vengano associati a questo tipo di attività di avviso in futuro.

    1. Selezionare un messaggio dall'elenco degli avvisi.
    2. Scegliere i puntini di sospensione e selezionare **migliora classificazione**.
    3. Nel riquadro dei commenti e suggerimenti per il **classificatore dettagliato** , se l'elemento è un valore positivo vero, scegliere **match**.  Se l'elemento è stato erroneamente incluso nella categoria come falso positivo, scegliere **non una corrispondenza**.
    4. Se è presente un altro classificatore più appropriato per l'elemento, selezionarlo dall'elenco **Suggerisci altri classificatori addestrabili** . Questo feedback attiva l'altro classificatore per valutare l'elemento.

    > [!TIP]
    > È possibile fornire commenti e suggerimenti su più elementi contemporaneamente, scegliendo tutti e quindi scegliendo **Fornisci commenti e suggerimenti dettagliati** sulla barra dei comandi.

    5. Scegliere **Invia commenti e suggerimenti** per inviare la valutazione della **corrispondenza** e non una classificazione delle **corrispondenze** e suggerire altri classificatori addestrabili. Quando sono state fornite 30 istanze di commenti e suggerimenti a un classificatore, vengono riaddestrate automaticamente. La riqualificazione può richiedere 1-4 ore per il completamento. I classificatori possono essere riaddestrati solo due volte al giorno.

    > [!IMPORTANT]
    > Queste informazioni passano al classificatore del tenant, **ma non tornano a Microsoft**.

    Per ulteriori informazioni sul riqualificazione del classificatore per la conformità alla comunicazione, vedere la [procedura per riqualificare un classificatore nell'articolo Compliance Communications](classifier-how-to-retrain-comms-compliance.md) .

    ![Conformità della comunicazione migliorare la classificazione](../media/communication-compliance-improve-classifier.png)

- **Rimuovi messaggio nei team**: se si utilizza il controllo **Rimuovi messaggio in teams** , è possibile bloccare i messaggi e i contenuti inopportuni identificati in avvisi provenienti da Microsoft teams Channels e 1:1 e Group Chat. I messaggi e il contenuto rimossi sono stati sostituiti da un suggerimento per i criteri che spiega che è stato bloccato e che il criterio si applica alla relativa rimozione dalla visualizzazione. Ai destinatari viene fornito un collegamento nel suggerimento del criterio per ulteriori informazioni sui criteri applicabili e sul processo di revisione. Il mittente riceve un suggerimento per i criteri per il messaggio e il contenuto bloccati, ma può esaminare i dettagli del messaggio e del contenuto bloccati per il contesto relativo alla rimozione.

    ![Rimuovere un messaggio da Microsoft Teams](../media/communication-compliance-remove-teams-message.png)

### <a name="step-4-determine-if-message-details-should-be-archived-outside-of-communication-compliance"></a>Passaggio 4: determinare se i dettagli dei messaggi devono essere archiviati al di fuori della conformità di comunicazione

I dettagli del messaggio possono essere esportati o scaricati se è necessario archiviare i messaggi in una soluzione di archiviazione separata. Se si seleziona il controllo **download** , vengono aggiunti automaticamente i messaggi selezionati a un. File ZIP che può essere salvato nello spazio di archiviazione all'esterno di Microsoft 365.
