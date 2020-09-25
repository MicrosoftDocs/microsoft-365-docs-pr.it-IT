---
title: Creare e gestire valutazioni in Microsoft Compliance Manager
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
description: Le valutazioni di compilazione in Microsoft Compliance Manager consentono di soddisfare i requisiti di normative e certificazioni importanti per la propria organizzazione.
ms.openlocfilehash: d09103f58be3a5fa39b57ca35da411e8046aace5
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262291"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Creare e gestire valutazioni in Compliance Manager

**In questo articolo:** Informazioni su come personalizzare Compliance Manager per l'organizzazione creando e gestendo **valutazioni**. In questo articolo viene illustrato come creare valutazioni, come organizzarle in **gruppi**, utilizzare i **controlli**, accettare **gli aggiornamenti**ed esportare i **report**di valutazione.

> [!IMPORTANT]
> Le valutazioni disponibili per l'organizzazione dipendono dal contratto di licenza. [Esaminare i dettagli](https://go.microsoft.com/fwlink/?linkid=2132371).

## <a name="introduction-to-assessments"></a>Introduzione alle valutazioni

Compliance Manager consente di gestire la conformità alle valutazioni per le normative e le certificazioni che si applicano all'organizzazione. Le valutazioni sono raggruppamenti di controlli di una specifica normativa, standard o criterio. Compliance Manager facilita l'avvio del monitoraggio della conformità fornendo valutazioni predefinite che coprono una vasta gamma di regolamenti e certificazioni industriali e regionali.

Ogni valutazione viene creata da un [modello di valutazione](compliance-manager-templates.md). I modelli fungono da Framework che contengono i controlli necessari, le azioni di miglioramento e le azioni di Microsoft per il completamento della valutazione. La configurazione delle valutazioni più rilevanti per l'organizzazione può essere utile per implementare i criteri e le procedure operative per limitare i rischi di conformità.

Tutte le valutazioni sono elencate nella pagina valutazioni. Ulteriori informazioni su [come filtrare la visualizzazione delle valutazioni e interpretare gli Stati di stato](compliance-manager-setup.md#assessments-page).

## <a name="data-protection-baseline-default-assessment"></a>Valutazione predefinita del criterio di protezione dei dati

Per iniziare, Microsoft fornisce una valutazione **predefinita** in Compliance Manager per la linea di base per la **protezione dei dati di Microsoft 365**. Questa valutazione di base contiene una serie di controlli per le normative e gli standard fondamentali per la protezione dei dati e la governance dei dati generale. Questa linea di base estrae gli elementi principalmente dal NIST CSF (Istituto nazionale per gli standard e la tecnologia Cybersecurity Framework) e ISO (International Organization for Standardizzation), oltre che da FedRAMP (Federal Risk and Authorization Management Program) e GDPR (General Data Protection Regulation dell'Unione europea).

Questa valutazione viene utilizzata per calcolare il Punteggio di conformità iniziale al primo utilizzo di Compliance Manager, prima di configurare eventuali altre valutazioni. Compliance Manager raccoglie i segnali iniziali dalle soluzioni Microsoft 365. Verrà visualizzato a colpo d'occhio il modo in cui l'organizzazione è in esecuzione rispetto agli standard e alle normative sulla protezione dei dati e le azioni consigliate da intraprendere.

Compliance Manager diventa più utile quando si creano e gestiscono le proprie valutazioni per soddisfare le esigenze specifiche dell'organizzazione.

## <a name="assessment-creation-overview"></a>Panoramica della creazione di valutazione

È possibile configurare le valutazioni in tre modi:

1. [Utilizzare una valutazione predefinita](#use-a-pre-built-assessment).
2. [Estendere una valutazione predefinita per soddisfare le proprie esigenze](#extend-a-pre-built-assessment).
3. [Creare la propria valutazione personalizzata](#create-your-own-custom-assessment).

> [!NOTE]
> Solo gli utenti che dispongono di un ruolo amministratore globale o di amministrazione Compliance Manager possono creare e modificare le valutazioni. Per ulteriori informazioni [, vedere ruoli e autorizzazioni](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

**Utilizzo di una valutazione predefinita**

Kickstart your Compliance Journey scegliendo una valutazione già configurata da Compliance Manager. Viene fornita una vasta gamma di [modelli](compliance-manager-templates.md) per le normative e le certificazioni che vengono allineate a settori, aree geografiche e standard di protezione dei dati comuni, ad esempio GDPR e ISO 27001. I modelli contengono i controlli e le azioni di miglioramento per aiutarti a soddisfare i requisiti di una determinata certificazione. Verrà chiesto di scegliere un modello quando si avvia [la creazione di una valutazione](#use-a-pre-built-assessment).

**Estendere una valutazione predefinita per soddisfare le proprie esigenze**

È possibile modificare una valutazione di Compliance Manager, ovvero un processo che si riferisce a come "Extending", aggiungendo controlli e azioni personalizzati per soddisfare al meglio le esigenze dell'organizzazione. Ad esempio, se è necessario in genere conformarsi a HIPAA ma richiedono ulteriori controlli di sicurezza o protezione dei dati, è possibile estendere il modello HIPAA aggiungendovi i propri controlli. Per ulteriori informazioni, vedere le istruzioni per l' [estensione di una valutazione](#extend-a-pre-built-assessment)predefinita.

**Creare una valutazione personalizzata**

È possibile creare la propria valutazione completamente da zero per individuare con precisione le esigenze dell'organizzazione. La creazione di una propria valutazione richiede la creazione di un modello personalizzato per la valutazione in Compliance Manager. Vedere le istruzioni per la [creazione di una valutazione personalizzata](#create-your-own-custom-assessment).

## <a name="understand-groups-before-creating-assessments"></a>Comprendere i gruppi prima di creare valutazioni

Prima di creare o modificare le valutazioni, è importante comprendere il funzionamento del gruppo. Quando si crea una valutazione, è necessario assegnarla a un gruppo durante il processo. Per questo motivo, è consigliabile pianificare una strategia di raggruppamento per le proprie valutazioni prima di creare valutazioni.

### <a name="what-are-groups"></a>Cosa sono i gruppi

I gruppi sono contenitori che consentono di organizzare valutazioni. È possibile raggruppare le valutazioni in modo logico, ad esempio per anno o regolamento, o in base alle divisioni o alle aree geografiche dell'organizzazione. Di seguito sono riportati alcuni esempi di due gruppi e le relative valutazioni sottostanti:

- **FFIEC è assessment 2020**
  - FFIEC È
- **Valutazione della sicurezza e della privacy dei dati**
  - ISO 27001:2013
  - ISO 27018:2014

Quando due diverse valutazioni nelle stesse azioni di miglioramento della condivisione di gruppo gestite dall'utente, tutti gli aggiornamenti apportati ai dettagli di implementazione o allo stato di un'azione verranno sincronizzati automaticamente alla stessa azione in qualsiasi altra valutazione del gruppo. Questa sincronizzazione consente di implementare un'azione di miglioramento e di soddisfare diversi requisiti in più normative.

### <a name="how-to-create-a-group"></a>Come creare un gruppo

È possibile creare un gruppo durante il processo di [creazione di una nuova valutazione](#to-create-an-assessment).

I gruppi non possono essere creati come entità autonome. Un gruppo deve contenere almeno una valutazione. Per creare un gruppo, è necessario innanzitutto creare una valutazione da inserire nel gruppo.

### <a name="what-to-know-when-working-with-groups"></a>Cosa sapere quando si lavora con i gruppi

- I nomi dei gruppi devono essere univoci all'interno dell'organizzazione.
- I gruppi non dispongono di proprietà di sicurezza. Tutte le autorizzazioni sono associate alle valutazioni.
- Dopo aver aggiunto una valutazione a un gruppo, non è possibile modificare il raggruppamento.
- I controlli relativi alla valutazione in diverse valutazioni all'interno dello stesso gruppo vengono aggiornati automaticamente quando sono stati completati.
- Se si aggiunge una nuova valutazione a un gruppo esistente, le informazioni comuni provenienti da valutazioni di quel gruppo vengono copiate nella nuova valutazione.
- I gruppi possono contenere valutazioni per la stessa certificazione o regolamentazione, ma ogni gruppo può contenere solo una valutazione per una coppia specifica di certificazione di prodotto. Ad esempio, un gruppo non può contenere due valutazioni per Office 365 e NIST CSF. Un gruppo può contenere più valutazioni per lo stesso prodotto solo se la certificazione o la normativa corrispondente per ognuna di esse è diversa.
- L'eliminazione di una valutazione interrompe la relazione tra tale valutazione e il gruppo.
- I gruppi non possono essere eliminati.
- Quando viene apportata una modifica a un miglioramento visualizzato in più gruppi, la modifica viene applicata a tutte le istanze dell'azione di miglioramento.

## <a name="use-a-pre-built-assessment"></a>Utilizzo di una valutazione predefinita

Sono disponibili due punti di partenza per la creazione di una valutazione da un modello di Compliance Manager.

È possibile iniziare il processo dalla pagina valutazioni selezionando il pulsante **Aggiungi valutazione** e quindi utilizzando la procedura guidata per la creazione di valutazione. I passaggi per questo processo sono riportati di seguito.

È anche possibile iniziare dalla pagina modelli di valutazione individuando il modello desiderato e selezionandolo dall'elenco per arrivare alla pagina dei dettagli. Nella pagina Dettagli modello selezionare **Crea valutazione**. Verrà quindi immessa la procedura guidata con il modello già selezionato.

### <a name="to-create-an-assessment"></a>Per creare una valutazione

1. Individuare il gruppo a cui assegnare la valutazione o essere preparato per crearne uno nuovo per la valutazione. [Per ulteriori informazioni](#understand-groups-before-creating-assessments), vedere gruppi.  

2. Passare alla pagina **valutazioni** in Compliance Manager e selezionare **Aggiungi valutazione**. Una procedura guidata di valutazione verrà visualizzata in un riquadro a comparsa di grandi dimensioni.

3. **Selezionare un modello**: scegliere un modello da utilizzare come base per la valutazione. Selezionare il pulsante di opzione accanto al modello scelto, quindi fare clic su **Avanti**.

4. **Nome e gruppo:** Immettere un nome per la valutazione nel campo **nome valutazione** . I nomi di valutazione devono essere univoci all'interno dei gruppi. Se il nome della valutazione corrisponde al nome di un'altra valutazione in un determinato gruppo, verrà visualizzato un messaggio di errore in cui viene chiesto di creare un altro nome.

5. Assegnare la valutazione a un gruppo. È possibile eseguire le operazioni seguenti:
    - Selezionare **Usa gruppo esistente** per assegnarlo a un gruppo già creato; o
    - Selezionare **Crea nuovo gruppo** per creare un nuovo gruppo e assegnargli questa valutazione:
        - Determinare un nome per il gruppo e inserirlo nel campo sotto il pulsante di opzione.
        - È possibile **copiare i dati da un gruppo esistente**, ad esempio l'implementazione e i dettagli e i documenti di testing, selezionando le caselle appropriate.

    Al termine, selezionare **Avanti**.

6. **Revisione e finitura:** Nell'ultima schermata della procedura guidata vengono visualizzati il modello, il nome e il gruppo scelti per la valutazione. È possibile modificare una qualsiasi di queste impostazioni dai collegamenti sullo schermo, che riportano ai passaggi rilevanti della procedura guidata. Quando si è pronti, selezionare **Crea valutazione**.

7. La schermata successiva conferma di aver creato correttamente la nuova valutazione. Fare **clic su fine per** chiudere la procedura guidata e sullo schermo verrà visualizzata la pagina dei dettagli della nuova valutazione.

Se viene visualizzata una schermata di **valutazione non riuscita** dopo aver selezionato **Crea valutazione**, fare clic su **Riprova** per ricreare la valutazione.

È possibile modificare il nome della valutazione dopo averlo creato selezionando il pulsante **modifica nome** nell'angolo in alto a destra della [pagina dei dettagli della valutazione](#monitor-assessment-progress-and-controls).

## <a name="extend-a-pre-built-assessment"></a>Estendere una valutazione predefinita

È possibile modificare una valutazione precompilata aggiungendo i propri controlli e le azioni di miglioramento al modello di valutazione. Questo processo è denominato "Extending a Microsoft template" in Compliance Manager. Quando si estende il modello di una valutazione, verranno ricevuti tutti gli aggiornamenti rilasciati da Microsoft, che possono verificarsi quando si verificano modifiche alla normativa o al prodotto correlati (vedere [accepting Updates to assessments](#accepting-updates-to-assessments)).

Questo processo viene completato iniziando dalla pagina dei **modelli di valutazione** invece che dalla pagina **valutazioni** .

**Prima di iniziare**

Per preparare questo processo, è necessario assemblare un foglio di calcolo di Excel appositamente formattato per importare i dati dei modelli necessari. Vi sono requisiti speciali per i [file di Excel formattati](compliance-manager-templates.md#formatting-your-template-data-with-excel) utilizzati nel processo di estensione. Vedere questi punti aggiuntivi per prevenire gli errori nel processo di importazione:

- Il foglio di calcolo deve contenere solo le azioni e i controlli che si desidera aggiungere alla valutazione. 
- Il foglio di calcolo non può contenere nessuno dei controlli o delle azioni già esistenti nella valutazione che si desidera modificare.
- Si consideri inclusa "extension" nel titolo del modello, ad esempio "GDPR – [Your Company Name] Extension". In questo modo è più facile identificare nell'elenco nella pagina dei **modelli di valutazione** una differenza rispetto al modello standard fornito da Microsoft o a un modello personalizzato con un nome analogo.

Dopo aver formattato il foglio di calcolo, seguire i passaggi riportati di seguito.

**Passaggi per l'estensione di un modello di Compliance Manager**

1. Passare alla pagina **modelli di valutazione** e selezionare **Crea nuovo modello**. Verrà aperta una creazione guidata modello.

2. Scegliere il tipo di modello che si desidera creare. In questo caso, selezionare **Estendi modello Microsoft**, quindi **selezionare**.

3. Sul lato destro dello schermo viene visualizzato un riquadro a comparsa di selezione dei modelli. Utilizzare la **ricerca** per applicare filtri per l'individuazione del modello desiderato

4. Dopo aver individuato il modello, selezionare il pulsante di opzione a sinistra del nome e quindi fare clic su **Salva**.

5. Nella schermata successiva viene visualizzato il modello selezionato. Se la correzione è corretta, selezionare **Avanti**. Se non è corretto, scegliere **Seleziona un modello diverso** per scegliere di nuovo.

6. Nella schermata **Carica file** selezionare **Sfoglia** per individuare e caricare il file di Excel formattato contenente tutti i dati dei modelli necessari.

7. Se non ci sono problemi con il file, nella schermata successiva viene visualizzato il nome del file caricato. Fare clic su **Avanti** per continuare (se è necessario modificare il file, selezionare **carica un file diverso**).

    - Se si verifica un problema con il file, un messaggio di errore nella parte superiore spiega cosa c'è di sbagliato. È necessario correggere e ricaricare il file. Si verificherà un errore se il foglio di calcolo è formattato in modo errato o se sono presenti informazioni non valide in determinati campi.
 
8. La schermata **revisione e fine** Visualizza il numero di azioni e controlli di miglioramento e il punteggio massimo per il modello. Quando si è pronti per l'approvazione, selezionare **Avanti**. Se è necessario apportare modifiche, selezionare **carica un file diverso**.

9. L'ultima schermata conferma che è stato creato un nuovo modello. Fare clic su **fine** per uscire dalla procedura guidata.

10. Si arriva alla pagina dei dettagli del nuovo modello. Da qui è possibile creare una valutazione selezionando **Crea valutazione**. Per ulteriori informazioni, iniziare dal passaggio #4 nelle [istruzioni per la creazione di valutazione precedenti](#to-create-an-assessment).

## <a name="create-your-own-custom-assessment"></a>Creare una valutazione personalizzata

La creazione di una valutazione personalizzata in Compliance Manager richiede la creazione di un modello personalizzato. Per creare un modello personalizzato, è innanzitutto necessario assemblare un foglio di calcolo di Excel formattato per importare i dati dei modelli necessari. Consente inoltre di decidere in anticipo quale gruppo verrà assegnato al momento della creazione della valutazione (ulteriori informazioni sui [gruppi](#what-are-groups)).

**Attenersi alla procedura riportata di seguito per creare una valutazione personalizzata:**

1. **Formattare il file di Excel.** Iniziare con la formattazione dei dati del modello in un foglio di calcolo di Excel utilizzando [queste istruzioni](compliance-manager-templates.md#formatting-your-template-data-with-excel).

2. **Creare il modello** attenendosi alle [istruzioni](compliance-manager-templates.md#create-a-new-template)riportate di seguito.

3. **Creare la propria valutazione** dal modello. È possibile iniziare aprendo la pagina dei dettagli del modello e selezionando **Crea valutazione**oppure andare alla pagina **valutazioni** e selezionare **Crea valutazione**.

4. Una procedura guidata per la creazione di valutazione verrà visualizzata in un riquadro a comparsa di grandi dimensioni. Da qui, è possibile seguire le linee guida a partire dal passaggio #3 delle istruzioni per la creazione di una [valutazione](#to-create-an-assessment), utilizzando il nuovo modello personalizzato per la valutazione.

## <a name="delete-an-assessment"></a>Eliminare una valutazione

L'eliminazione di una valutazione lo rimuove dall'elenco nella pagina valutazioni. Si notino questi punti importanti sull'eliminazione delle valutazioni:

- **L'eliminazione di una valutazione è permanente. non è possibile ottenerlo nuovamente.** Se si desidera utilizzare di nuovo la stessa valutazione, sarà necessario ricrearla.
- Se le azioni di miglioramento nella valutazione non vengono visualizzate in altre valutazioni, verranno eliminate quando viene eliminata la valutazione.
- È consigliabile [esportare un rapporto](#export-an-assessment-report) di valutazione prima di eliminarlo definitivamente.

Per eliminare una valutazione, attenersi alla procedura seguente:

1. Nella pagina **valutazioni** selezionare la valutazione che si desidera eliminare per aprire la pagina dei dettagli della valutazione.

2. Selezionare **Elimina valutazione** nell'angolo in alto a destra dello schermo.

3. Verrà visualizzata una finestra in cui viene chiesto di confermare che si desidera eliminare definitivamente la valutazione. Selezionare **Elimina valutazione** per chiudere la finestra. Si otterrà una finestra di conferma che la valutazione è stata eliminata da Compliance Manager.

Se si elimina l'unica valutazione in un gruppo, tale gruppo viene eliminato anche da Compliance Manager.

> [!NOTE]
> Non è possibile eliminare tutte le valutazioni. Le organizzazioni hanno bisogno di almeno una valutazione per il corretto funzionamento di Compliance Manager. Se la valutazione che si desidera eliminare è l'unica, aggiungere un'altra valutazione prima di eliminare l'altra valutazione.

## <a name="monitor-assessment-progress-and-controls"></a>Monitorare lo stato e i controlli di valutazione

Ogni valutazione contiene una pagina dei dettagli che fornisce una visualizzazione a colpo d'occhio dello stato di avanzamento per il completamento della valutazione. La pagina mostra lo stato di avanzamento del processo di completamento dei controlli e lo stato del test delle azioni di miglioramento principali all'interno di tali controlli.

### <a name="overview-tab"></a>Scheda Panoramica

La scheda Panoramica contiene un grafico che mostra la percentuale verso il completamento della valutazione. Questo grafico contiene una ripartizione dei punti dalle azioni possedute e punti dalle azioni di Microsoft, in modo da poter vedere quanti più punti è necessario per completare la valutazione.

Le azioni di miglioramento principali per i controlli nella valutazione sono elencate in ordine di maggiore impatto potenziale per ottenere punti. Il grafico associato descrive lo stato di test aggregato delle azioni di miglioramento, in modo da poter valutare rapidamente cosa è stato testato e cosa è necessario fare.

Per accedere alle azioni di miglioramento individuali, visitare la scheda **controlli** o la scheda **azioni di miglioramento** .

### <a name="controls-tab"></a>Scheda controlli

Nella scheda controlli vengono visualizzate informazioni dettagliate per ogni controllo mappato alla valutazione. Un grafico di **ripartizione dello stato del controllo** Mostra lo stato dei controlli in base alla famiglia, quindi è possibile vedere a colpo d'occhio quali gruppi di controlli richiedono attenzione.

Al di sotto del grafico, una tabella contiene informazioni dettagliate su ogni controllo all'interno della valutazione. I controlli sono raggruppati in base alla famiglia di controlli. Espandere ciascun nome di famiglia per rivelare i singoli controlli in esso contenuti. Le informazioni elencate per ogni controllo includono:

- **Titolo del controllo**
- **Stato**: riflette lo stato del test delle azioni di miglioramento all'interno del controllo. 
    - Le azioni di miglioramento **passate** -tutte hanno uno stato di test "superato" o almeno uno viene superato e gli altri sono "fuori portata"
    -  **Errore** : almeno un'azione di miglioramento ha lo stato di test "failed"
    - **None** -tutte le azioni di miglioramento non sono state testate
    - **Fuori portata** : tutte le azioni di miglioramento sono fuori portata per questa valutazione
    - **In Progress** -le azioni di miglioramento hanno uno stato diverso da quelli sopra elencati, che potrebbero includere "in corso", "credito parziale" o "non rilevato"
- **ID di controllo**: il numero di identificazione del controllo, assegnato dal regolamento, dallo standard o dal criterio corrispondente
- **Punti raggiunti**: il numero di punti ottenuti completando le azioni, al di fuori del numero totale di punti ottenibili 
- Le **azioni**: il numero di azioni eseguite al di fuori del numero totale di azioni da eseguire
- **Azioni Microsoft**: il numero di azioni completate da Microsoft 

Per visualizzare i dettagli di un controllo, selezionarlo dalla relativa riga nella tabella. Nella pagina dei dettagli del controllo viene visualizzato un grafico che indica lo stato del test delle azioni all'interno del controllo. Una tabella che segue il grafico Visualizza le azioni di miglioramento fondamentali per tale controllo.

Selezionare un'azione di miglioramento dall'elenco per eseguire il drill-through nella pagina dei dettagli dell'azione di miglioramento. Le pagine dei dettagli mostrano lo stato del test, le note di implementazione e l'avvio nella soluzione consigliata.

### <a name="your-improvement-actions-tab"></a>Scheda azioni di miglioramento

La scheda per le azioni di miglioramento elenca tutti i controlli della valutazione gestiti dall'organizzazione. La barra di stato consente di delineare lo stato di prova aggregato delle azioni di miglioramento nella valutazione, in modo da poter valutare rapidamente cosa è stato testato e cosa è ancora necessario eseguire. Sotto la barra si trova l'elenco completo delle azioni di miglioramento e dei dettagli chiave, tra cui: stato del test, il numero di punti potenziali e guadagnati, le normative e gli standard associati, la soluzione applicabile, il tipo di azione e la famiglia di controllo. Ulteriori informazioni sul [modo in cui le azioni contribuiscono al Punteggio di conformità](compliance-score-calculation.md#action-types-and-points).

Selezionare un'azione di miglioramento per visualizzare la pagina dei dettagli, quindi selezionare il collegamento **Avvia ora** per aprire la soluzione per eseguire l'azione.

### <a name="microsoft-actions-tab"></a>Scheda azioni Microsoft

La scheda Microsoft Actions elenca tutte le azioni nella valutazione gestita da Microsoft. Nell'elenco sono riportati i dettagli dell'azione chiave, tra cui: stato del test, punti che contribuiscono al Punteggio di conformità globale, alle normative e agli standard associati, alla soluzione applicabile, al tipo di azione e alla famiglia di controllo. Selezionare un'azione di miglioramento per visualizzare la pagina dei dettagli.

Ulteriori informazioni sul [modo in cui vengono registrati e segnati i controlli e le azioni di miglioramento.](compliance-score-calculation.md)

## <a name="accepting-updates-to-assessments"></a>Accettazione degli aggiornamenti alle valutazioni

Quando è disponibile un aggiornamento per una valutazione, viene visualizzata una notifica e si ha la possibilità di accettare l'aggiornamento o posticiparlo in un secondo momento.

### <a name="what-causes-an-update"></a>Quali sono le cause di un aggiornamento

Un aggiornamento di valutazione si verifica quando sono presenti modifiche al modello sottostanti che incidono sul punteggio. Le modifiche possono comportare la regolazione del mapping dei controlli o altre linee guida basate su modifiche normative o modifiche al prodotto. Gli aggiornamenti di valutazione possono avere origine dall'organizzazione, ad esempio quando [viene modificato un modello personalizzato](compliance-manager-templates.md#modify-a-template), nonché da Microsoft.

Se Microsoft aggiorna un modello di Compliance Manager esteso, la valutazione erediterà tali aggiornamenti dopo averli accettati. La valutazione conserva gli attributi aggiuntivi applicati alla valutazione quando è stata estesa.

Le valutazioni personalizzate create non ricevono gli aggiornamenti dei modelli da Microsoft. Le valutazioni personalizzate possono ricevere aggiornamenti per l'azione di miglioramento, ma gli eventuali aggiornamenti di Microsoft per controllare il mapping tra le valutazioni e le azioni di miglioramento non si applicano ai modelli personalizzati.

> [!NOTE]
> Gli aggiornamenti alle valutazioni si applicano solo a livello di gruppo. Se si dispone di due valutazioni generate dallo stesso modello che esistono in due gruppi diversi, ogni valutazione avrà una notifica di aggiornamento in sospeso e sarà necessario accettare l'aggiornamento a ogni valutazione del rispettivo gruppo singolarmente.

#### <a name="where-youll-see-assessment-update-notifications"></a>Dove vengono visualizzate le notifiche degli aggiornamenti per la valutazione

La pagina Dettagli valutazione Visualizza anche un'etichetta di **aggiornamento in sospeso** accanto alla valutazione con un aggiornamento. Selezionare tale valutazione per accedere alla pagina dei dettagli.

Un messaggio vicino alla parte superiore della pagina dei dettagli di valutazione indica che è disponibile un aggiornamento per tale valutazione. Selezionare il pulsante **Review Update** nel banner per esaminare le modifiche specifiche e accettare o posticipare l'aggiornamento.

La pagina Dettagli valutazione può anche elencare le azioni di miglioramento che dispongono di un'etichetta di **aggiornamento in sospeso** accanto a essi. Tali aggiornamenti sono per modifiche specifiche alle azioni di miglioramento e devono essere accettate separatamente. Visitare [accettazione degli aggiornamenti per le azioni di miglioramento](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) per ulteriori informazioni.

#### <a name="review-update-to-accept-or-defer"></a>Revisione dell'aggiornamento da accettare o posticipare

Dopo aver selezionato **revisione aggiornamento** dalla pagina Dettagli valutazione, sul lato destro dello schermo viene visualizzato un riquadro a comparsa. Nel riquadro a comparsa sono riportati i dettagli principali relativi all'aggiornamento in sospeso:

- Il titolo del modello
- Origine dell'aggiornamento (Microsoft, la propria organizzazione o un utente specifico)
- La data in cui è stato creato l'aggiornamento
- Una panoramica che spiega l'aggiornamento
- Dettagli specifici sulle modifiche, tra cui l'impatto sul punteggio di conformità, la quantità di progressi verso il completamento della valutazione e il numero specifico di modifiche apportate alle azioni e ai controlli di miglioramento.

Se si seleziona il collegamento **modello aggiornato** , verrà scaricato un file di Excel contenente i dati di controllo per la versione del modello con gli aggiornamenti in sospeso. Se si seleziona il collegamento al **modello corrente** , viene scaricato un file del modello esistente senza le modifiche apportate.

Per accettare l'aggiornamento e apportare le modifiche apportate alla valutazione, selezionare **accetta aggiornamento**. Le modifiche accettate sono permanenti.

Se si seleziona **Annulla**, l'aggiornamento non verrà applicato alla valutazione. Tuttavia, si continuerà a visualizzare la notifica di **aggiornamento in sospeso** fino a quando non si accetterà l'aggiornamento.

**Perché si consiglia di accettare gli aggiornamenti**

L'accettazione degli aggiornamenti consente di ottenere le informazioni più aggiornate sull'utilizzo delle soluzioni e sull'adozione di azioni di miglioramento appropriate che consentano di soddisfare i requisiti della certificazione a disposizione.

**Perché potrebbe essere opportuno rinviare un aggiornamento**

Se si sta eseguendo una valutazione, è possibile verificare di aver completato il lavoro prima di accettare un aggiornamento alla valutazione che potrebbe interrompere il mapping dei controlli. È possibile posticipare l'aggiornamento per un secondo momento selezionando **Annulla** nel riquadro del pannello a comparsa revisione aggiornamento.

## <a name="export-an-assessment-report"></a>Esportare un report di valutazione

È possibile esportare una valutazione in un file di Excel per la conformità delle parti interessate nell'organizzazione o per i revisori esterni e regolatori. Nella pagina Dettagli valutazione selezionare il pulsante **genera report** accanto alla parte superiore della pagina, che consente di creare un file di Excel che è possibile salvare e condividere.

Il report è un'istantanea della valutazione alla data e all'ora dell'esportazione. Contiene i dettagli per i controlli gestiti da Microsoft, compresi lo stato di implementazione, la data di test e i risultati dei test.