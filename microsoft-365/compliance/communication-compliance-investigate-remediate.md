---
title: Esaminare e correggere gli avvisi di conformità della comunicazione
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
ms.openlocfilehash: 31a38ac28d1b483d6b5cdce6fade82d252457641
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661952"
---
# <a name="investigate-and-remediate-communication-compliance-alerts"></a>Esaminare e correggere gli avvisi di conformità della comunicazione

Dopo aver configurato i criteri di conformità della comunicazione, si inizierà a ricevere avvisi nel centro conformità di Microsoft 365 per i problemi dei messaggi che soddisfano le condizioni di criteri. Seguire le istruzioni del flusso di lavoro qui per esaminare e correggere i problemi di avviso.

## <a name="investigate-alerts"></a>Esaminare gli avvisi

Il primo passaggio per esaminare i problemi rilevati dai criteri consiste nell'esaminare gli avvisi generati nel centro conformità di Microsoft 365. Nel centro conformità sono presenti diverse aree che consentono di esaminare rapidamente gli avvisi, a seconda di come si preferisce visualizzare il raggruppamento degli avvisi:

- **Home page Compliance Communication**: quando si accede all' [https://compliance.microsoft.com](https://compliance.microsoft.com) utilizzo delle credenziali per un account di amministratore nell'organizzazione Microsoft 365, selezionare > **Overview** **Compliance Communication**per visualizzare la Home page conformità comunicazione. Di seguito vengono visualizzate le informazioni seguenti:
    - Avvisi che richiedono la revisione elencata dalla gravità elevata a quella bassa. Selezionare un avviso per avviare la pagina dei dettagli dell'avviso e avviare le azioni di correzione.
    - Corrispondenze di criteri recenti elencate in base al nome del criterio.
    - Elementi risolti elencati in base al nome del criterio.
    - Escalation elencate in base al nome del criterio.
    - Utenti con la maggior parte delle corrispondenze di criteri, elencate tra la maggior parte e il minor numero di corrispondenze.
- **Scheda avvisi**: passare a **** > **avvisi** di conformità della comunicazione per visualizzare gli avvisi raggruppati in base al criterio di conformità della comunicazione corrispondente. Questa visualizzazione consente di visualizzare rapidamente quali criteri di conformità della comunicazione stanno generando la maggior parte degli avvisi ordinati per gravità.  Per avviare le azioni di correzione, espandere un criterio per selezionare un avviso specifico e avviare la pagina dei dettagli dell'avviso.
- **Scheda criteri**: passare ai **** > **criteri** di conformità della comunicazione per visualizzare i criteri di conformità della comunicazione configurati per l'organizzazione Microsoft 365. Ogni criterio elencato include il numero di avvisi che devono essere esaminati. Se si seleziona un criterio, vengono visualizzati tutti gli avvisi in sospeso per le corrispondenze al criterio, selezionare un avviso specifico per avviare la pagina dei dettagli del criterio e avviare le azioni di correzione.

### <a name="using-filters"></a>Utilizzo di filtri

Il passaggio successivo consiste nell'ordinare i messaggi in modo che sia più facile esaminare gli avvisi. La conformità alla comunicazione supporta il filtro a più livelli per diversi campi dei messaggi che consentono di analizzare e rivedere rapidamente i messaggi con le corrispondenze di criteri. Il filtro è disponibile per gli elementi in sospeso e risolti per ogni criterio configurato. È possibile configurare le query di filtro per un criterio o configurare e salvare query di filtro personalizzate e predefinite per l'utilizzo in ogni criterio specifico. Dopo aver configurato i campi per un filtro, verranno visualizzati i campi del filtro visualizzato nella parte superiore della coda dei messaggi di avviso che è possibile configurare per i valori di filtro specifici.

Per un elenco completo dei filtri e dettagli sul campo, vedere [Filters](communication-compliance-feature-reference.md#filters) in the feature reference topic.

#### <a name="to-configure-a-filter"></a>Per configurare un filtro

1. Accedere [https://compliance.microsoft.com](https://compliance.microsoft.com) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro conformità di Microsoft 365, passare a **conformità comunicazione**.

3. Selezionare la scheda **criteri** e quindi selezionare un criterio per l'analisi, fare doppio clic per aprire la pagina **criteri** .

4. Nella pagina **criterio** selezionare la scheda **in sospeso** o **risolta** per visualizzare gli elementi per il filtro.

5. Selezionare il controllo **filtri** per aprire la pagina dei dettagli sui **filtri** .

6. Selezionare una o più caselle di controllo per abilitare i filtri per questi avvisi. È possibile scegliere tra numerosi filtri, tra cui *Data*, *mittente*, *oggetto/titolo*, *classificatori*e altro ancora.

7. Se si desidera salvare il filtro selezionato come filtro predefinito, fare clic su **Salva con nome predefinito**. Se si desidera utilizzare questo filtro come filtro salvato, fare clic su **fine**.

8. Se si desidera salvare i filtri selezionati come query di filtro, fare clic su **Salva il controllo query** dopo aver configurato almeno un valore di filtro. Immettere un nome per la query del filtro e selezionare **Salva**. Questo filtro è disponibile per essere utilizzato solo per questo criterio ed è elencato nella sezione **query di filtro salvate** della pagina dei dettagli sui **filtri** .

    ![Controlli Dettagli filtro conformità di comunicazione](media/communication-compliance-filter-detail-controls.png)

### <a name="using-near-and-exact-duplicate-analysis"></a>Utilizzo dell'analisi duplicata vicina ed esatta

I criteri di conformità della comunicazione analizzano e pregruppo i duplicati del messaggio vicino ed esatto senza ulteriori passaggi di configurazione. Questa visualizzazione consente di correggere rapidamente i messaggi simili uno per uno o come gruppo, riducendo il carico di indagine dei messaggi per i revisori. Quando vengono rilevati duplicati, **i duplicati e/** o i controlli **duplicati esatti** vengono visualizzati nella barra degli strumenti azione di correzione.

#### <a name="to-remediate-duplicates"></a>Per correggere i duplicati

1. Accedere [https://compliance.microsoft.com](https://compliance.microsoft.com) con le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nel centro conformità di Microsoft 365, passare a **conformità comunicazione**.

3. Selezionare la scheda **criteri** e quindi selezionare un criterio per l'analisi, fare doppio clic per aprire la pagina **criteri** .

4. Nella pagina **criterio** selezionare la scheda **in sospeso** o **risolta** per visualizzare i messaggi duplicati.

5. Selezionare i controlli **quasi** duplicati o **duplicati esatti** per aprire la pagina dei dettagli duplicati.

6. Selezionare uno o più messaggi per i controlli azione di correzione per questi messaggi.

7. Selezionare **Risolvi**, **notifica**, **Inoltra**o **Scarica** per applicare l'azione ai messaggi duplicati selezionati. eletta come filtro predefinito.

8. Selezionare **Chiudi** dopo aver completato le operazioni di correzione dei messaggi.

    ![Controlli di conformità dei duplicati esatti della comunicazione](media/communication-compliance-duplicates-controls.png)

## <a name="remediate-alerts"></a>Correggere gli avvisi

Indipendentemente dal punto in cui si inizia a esaminare gli avvisi o il filtro configurato, il passaggio successivo consiste nell'intervenire per correggere l'avviso. Avviare la correzione degli avvisi utilizzando il flusso di lavoro seguente nelle pagine dei **criteri** o degli **avvisi** :

1. **Esaminare le nozioni di base sui messaggi**: a volte risulta evidente dall'origine o dall'oggetto che un messaggio può essere immediatamente rimediato. Potrebbe essere che il messaggio sia falso o erroneamente corrispondente a un criterio e che sia necessario risolverlo come falsi positivi. Selezionare il controllo **false positive** per risolvere immediatamente l'avviso e rimuoverlo dalla coda degli avvisi in sospeso. Dalle informazioni di origine o mittente, potrebbe essere già possibile sapere in che modo il messaggio deve essere instradato o gestito in queste circostanze. Considerare l'utilizzo del **tag come** o l' **escalation** dei controlli per assegnare un tag ai messaggi applicabili o per inviare messaggi a un revisore designato.

    ![Controlli di correzione della conformità di comunicazione](media/communication-compliance-remediation-controls.png)

2. **Esaminare i dettagli del messaggio**: dopo aver esaminato le nozioni di base del messaggio, è necessario aprire un messaggio per esaminare i dettagli e determinare ulteriori azioni di correzione. Selezionare un messaggio per visualizzare le informazioni complete sull'intestazione e sul corpo del messaggio. Sono disponibili diverse visualizzazioni per facilitare la scelta del corso di azione appropriato:

    - **Visualizzazione origine**: questa visualizzazione è la visualizzazione standard dei messaggi comunemente visualizzata nella maggior parte delle piattaforme di messaggistica basate sul Web. Le informazioni di intestazione sono formattate nello stile normale e il corpo del messaggio supporta i file grafici incorporati e il testo con wrapping di Word.
    - **Visualizzazione testo**: la visualizzazione del testo Visualizza una visualizzazione di solo testo numerato in linea del messaggio e include l'evidenziazione delle parole chiave per i termini corrispondenti nei criteri di conformità della comunicazione associati. L'evidenziazione delle parole chiave può essere utile per l'analisi rapida dei messaggi lunghi per l'area di interesse. I file incorporati non vengono visualizzati e la numerazione delle righe questa visualizzazione è utile per fare riferimento ai dettagli pertinenti tra più revisori.
    - **Visualizzazione annotazioni**: questa visualizzazione consente ai revisori di aggiungere annotazioni direttamente sul messaggio salvato nella visualizzazione del messaggio.
    - **Cronologia utenti**: visualizzazione cronologia utenti Visualizza tutti gli altri avvisi generati da tutti i criteri di conformità della comunicazione per l'utente che invia il messaggio.

    ![Controlli di visualizzazione messaggi di conformità di comunicazione](media/communication-compliance-message-views.png)

3. **Decidere in merito a un'azione di correzione**: dopo aver esaminato i dettagli del messaggio per l'avviso, è possibile scegliere diverse azioni correttive:

    - **Risoluzione**: se si seleziona il controllo **Risolvi** , il messaggio viene rimosso immediatamente dalla coda degli **avvisi in sospeso** e non è possibile eseguire altre operazioni sul messaggio. Selezionando **Risolvi**, l'avviso è stato sostanzialmente chiuso senza ulteriore classificazione e non può essere riaperto per ulteriori azioni. Tutti i messaggi risolti vengono visualizzati nella scheda **risolti** .
    - **False positive**: è sempre possibile risolvere un messaggio come falso positivo in qualsiasi momento durante il flusso di lavoro per la revisione dei messaggi. Il messaggio non può essere riaperto e tutti i messaggi falsi positivi sono visualizzati nella scheda **risolti** .
    - **Tag As**: contrassegnare il messaggio come *conforme*, *non conforme*o come *discutibile* in relazione ai criteri e agli standard per l'organizzazione. L'aggiunta di tag e commenti di tagging può aiutare a filtrare gli avvisi per i criteri per le escalation o come parte di altri processi di revisione interni. Dopo aver completato il tagging, è anche possibile scegliere di risolvere il messaggio per spostarlo fuori dalla coda di revisione in sospeso.
    - **Notify**: è possibile utilizzare il controllo **Notify** per assegnare un modello di avviso personalizzato all'avviso e per inviare un avviso all'utente. Scegliere il modello di avviso appropriato e quindi fare clic su **Invia** alla posta elettronica un promemoria per il dipendente che ha inviato il messaggio e per risolvere il problema.
    - **Escalation**: se si utilizza il controllo **escalation** , è possibile scegliere chi altro nell'organizzazione deve esaminare il messaggio. Scegliere da un elenco di revisori configurati per inviare una notifica tramite posta elettronica che richiede ulteriori riesami dell'avviso del messaggio. Il revisore selezionato può utilizzare un collegamento nella notifica di posta elettronica per passare direttamente agli elementi che sono stati escalati per la revisione.
    - **Creare un caso**: utilizzando il controllo **Create a case** , è possibile creare un nuovo [caso di eDiscovery avanzato](overview-ediscovery-20.md) per singoli o più messaggi. Verranno forniti un nome e note per il nuovo caso e l'utente che ha inviato il messaggio che corrisponde al criterio viene automaticamente assegnato come custode del caso. Non sono necessarie ulteriori autorizzazioni per gestire il caso. La creazione di un caso non risolve o crea un nuovo tag per il messaggio.

4. **Determinare se i dettagli dei messaggi devono essere archiviati all'esterno della conformità di comunicazione**: i dettagli del messaggio possono essere esportati o scaricati se è necessario archiviarli in una soluzione di archiviazione separata. Se si seleziona il controllo **download** , vengono aggiunti automaticamente i messaggi selezionati a un. File ZIP che può essere salvato nello spazio di archiviazione all'esterno di Microsoft 365.
