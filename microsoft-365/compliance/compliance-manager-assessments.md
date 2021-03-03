---
title: Creare e gestire le valutazioni in Microsoft Compliance Manager
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
description: Creare valutazioni in Microsoft Compliance Manager per soddisfare i requisiti delle normative e delle certificazioni importanti per l'organizzazione.
ms.openlocfilehash: 06b644293c014dafbe46c115b498c2ad2390e99d
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406758"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Creare e gestire valutazioni in Compliance Manager

**In questo articolo:** Informazioni su come personalizzare Compliance Manager per l'organizzazione creando e gestendo **le valutazioni.** In questo articolo viene illustrato come creare valutazioni, come organizzarle in **gruppi,** utilizzare i **controlli,** accettare aggiornamenti ed esportare report di  **valutazione.**

> [!IMPORTANT]
> Le valutazioni disponibili per l'organizzazione dipendono dal contratto di licenza. [Esaminare i dettagli.](https://go.microsoft.com/fwlink/?linkid=2132371)

## <a name="introduction-to-assessments"></a>Introduzione alle valutazioni

Compliance Manager consente di gestire la conformità alle valutazioni per le normative e le certificazioni applicabili all'organizzazione. Le valutazioni sono raggruppamenti di controlli di uno specifico regolamento, standard o criterio. Compliance Manager consente di iniziare facilmente a tenere traccia della conformità fornendo valutazioni predefinite che riguardano un'ampia gamma di normative e certificazioni del settore e regionali.

Ogni valutazione viene creata da un modello [di valutazione.](compliance-manager-templates.md) I modelli fungono da framework contenente i controlli necessari, le azioni di miglioramento e le azioni di Microsoft per completare la valutazione. L'impostazione delle valutazioni più rilevanti per l'organizzazione consente di implementare criteri e procedure operative per limitare i rischi di conformità.

Tutte le valutazioni sono elencate nella pagina delle valutazioni. Ulteriori informazioni su [come filtrare la visualizzazione delle valutazioni e interpretare gli stati di stato.](compliance-manager-setup.md#assessments-page)

## <a name="data-protection-baseline-default-assessment"></a>Valutazione predefinita di base della protezione dei dati

Per iniziare, Microsoft fornisce una **valutazione** predefinita in Compliance Manager per la baseline di protezione dei dati **di Microsoft 365.** Questa valutazione di base include una serie di controlli per le normative e gli standard chiave per la protezione dei dati e la governance generale dei dati. Questa linea di base si basa principalmente su NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Standardization), nonché su FedRAMP (Federal Risk and Authorization Management Program) e GDPR (Regolamento generale sulla protezione dei dati dell'Unione Europea).

Questa valutazione viene usata per calcolare il punteggio di conformità iniziale la prima volta che si arriva a Compliance Manager, prima di configurare eventuali altre valutazioni. Compliance Manager raccoglie i segnali iniziali dalle soluzioni Di Microsoft 365. Vedrai a colpo d'occhio le prestazioni dell'organizzazione in relazione agli standard e alle normative di protezione dei dati chiave e vedrai le azioni di miglioramento suggerite da intraprendere.

Compliance Manager diventa più utile durante la creazione e la gestione delle proprie valutazioni per soddisfare le esigenze specifiche dell'organizzazione.

## <a name="assessment-creation-overview"></a>Panoramica della creazione della valutazione

Esistono tre modi per configurare le valutazioni:

1. [Utilizzare una valutazione precompisa.](#use-a-pre-built-assessment)
2. [Estendere una valutazione precompisa in base alle proprie esigenze.](#extend-a-pre-built-assessment)
3. [Creare una valutazione personalizzata.](#create-your-own-custom-assessment)

> [!NOTE]
> Solo gli utenti che hanno un ruolo di amministratore globale o di amministrazione di Compliance Manager possono creare e modificare le valutazioni. Ulteriori informazioni su [ruoli e autorizzazioni.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

**Usare una valutazione precompisa**

Avvia il percorso di conformità scegliendo una valutazione già impostata da Compliance Manager. Offriamo un'ampia [](compliance-manager-templates.md) selezione di modelli per normative e certificazioni in linea con i settori, le aree geografiche e gli standard di protezione dei dati comuni, come GDPR e ISO 27001. I modelli contengono i controlli e le azioni di miglioramento per aiutarti a soddisfare i requisiti di una determinata certificazione. Ti verrà chiesto di scegliere un modello quando inizi a [creare una valutazione.](#use-a-pre-built-assessment)

**Estendere una valutazione precompisa in base alle proprie esigenze**

È possibile modificare una valutazione di Compliance Manager, un processo che viene detto "estensione", aggiungendo controlli e azioni personalizzati in base alle esigenze dell'organizzazione. Ad esempio, se in genere è necessario rispettare HIPAA ma richiedono ulteriori controlli di sicurezza o protezione dei dati, è possibile estendere il modello HIPAA aggiungendo controlli personalizzati. Vedere le istruzioni per [l'estensione di una valutazione pre-creata.](#extend-a-pre-built-assessment)

**Creare una valutazione personalizzata**

È possibile creare la propria valutazione interamente da zero per tenere traccia precisamente delle esigenze dell'organizzazione. La creazione di una valutazione personale richiede la creazione di un modello personalizzato per la valutazione in Compliance Manager. Vedere le istruzioni per [la creazione di una valutazione personalizzata.](#create-your-own-custom-assessment)

## <a name="understand-groups-before-creating-assessments"></a>Comprendere i gruppi prima di creare le valutazioni

Prima di creare o modificare le valutazioni, è importante comprendere il funzionamento dei gruppi. Quando si crea una valutazione, è necessario assegnarla a un gruppo durante il processo. Ecco perché è consigliabile pianificare una strategia di raggruppamento per le valutazioni prima di creare le valutazioni.

### <a name="what-are-groups"></a>Che cosa sono i gruppi

I gruppi sono contenitori che consentono di organizzare le valutazioni. È possibile raggruppare le valutazioni in modo logico, ad esempio in base all'anno o alla normativa, o in base alle divisioni o alle aree geografiche dell'organizzazione. Di seguito sono riportati alcuni esempi di due gruppi e delle relative valutazioni sottostanti:

- **Valutazione FFIEC IS 2020**
  - FFIEC IS
- **Valutazioni della sicurezza e della privacy dei dati**
  - ISO 27001:2013
  - ISO 27018:2014

Quando due valutazioni diverse nello stesso gruppo condividono le azioni di miglioramento gestite dall'utente, qualsiasi aggiornamento apportato ai dettagli o allo stato di implementazione di un'azione verrà sincronizzato automaticamente con la stessa azione in qualsiasi altra valutazione del gruppo. Questa sincronizzazione consente di implementare un'unica azione di miglioramento e di soddisfare diversi requisiti in più normative.

### <a name="how-to-create-a-group"></a>Come creare un gruppo

Si crea un gruppo durante il processo di [creazione di una nuova valutazione.](#to-create-an-assessment)

I gruppi non possono essere creati come entità autonome. Un gruppo deve contenere almeno una valutazione. Per creare un gruppo, devi prima creare una valutazione da inserire nel gruppo.

### <a name="what-to-know-when-working-with-groups"></a>Cosa sapere quando si lavora con i gruppi

- I nomi dei gruppi devono essere univoci all'interno dell'organizzazione.
- I gruppi non dispongono di proprietà di sicurezza. Tutte le autorizzazioni sono associate alle valutazioni.
- Dopo aver aggiunto una valutazione a un gruppo, il raggruppamento non può essere modificato.
- I controlli di valutazione correlati in valutazioni diverse all'interno dello stesso gruppo vengono aggiornati automaticamente al termine.
- Se si aggiunge una nuova valutazione a un gruppo esistente, le informazioni comuni delle valutazioni in tale gruppo vengono copiate nella nuova valutazione.
- I gruppi possono contenere valutazioni per la stessa certificazione o regolamento, ma ogni gruppo può contenere solo una valutazione per una coppia di prodotti-certificazione specifica. Ad esempio, un gruppo non può contenere due valutazioni per Office 365 e NIST CSF. Un gruppo può contenere più valutazioni per lo stesso prodotto solo se la certificazione o la normativa corrispondente per ognuna di essi è diversa.
- L'eliminazione di una valutazione interrompe la relazione tra tale valutazione e il gruppo.
- I gruppi non possono essere eliminati.
- Quando viene apportata una modifica a un miglioramento presente in più gruppi, tale modifica viene riflessa in tutte le istanze di tale azione di miglioramento.

## <a name="use-a-pre-built-assessment"></a>Usare una valutazione precompisa

Esistono due punti di partenza per creare una valutazione da un modello di Compliance Manager.

È possibile iniziare il processo dalla pagina  delle valutazioni selezionando il pulsante Aggiungi valutazione e quindi utilizzando la procedura guidata di creazione della valutazione. I passaggi per questo processo sono riportati di seguito.

Puoi anche iniziare dalla pagina dei modelli di valutazione trovando il modello desiderato e selezionandolo nell'elenco per arrivare alla relativa pagina dei dettagli. Nella pagina dei dettagli del modello selezionare **Crea valutazione.** Verrà quindi immessa la procedura guidata con il modello già selezionato.

### <a name="to-create-an-assessment"></a>Per creare una valutazione

1. Conoscere il gruppo a cui assegnare la valutazione o prepararsi a crearne uno nuovo per questa valutazione. [Ulteriori informazioni sui gruppi.](#understand-groups-before-creating-assessments)  

2. Passare alla pagina **delle valutazioni** in Compliance Manager e selezionare **Aggiungi valutazione.** Una valutazione guidata verrà visualizzata in un riquadro a comparsa di grandi dimensioni.

3. **Selezionare un modello:** scegliere un modello da utilizzare come base per la valutazione. Vedrai l'elenco dei modelli suddivisi in categorie incluse e premium (vedi [Tipi di modello](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) per altre informazioni). Seleziona il pulsante di opzione accanto al modello scelto, quindi seleziona **Avanti.**

4. **Nome e gruppo:** Immettere un nome per la valutazione nel **campo Nome valutazione.** I nomi delle valutazioni devono essere univoci all'interno dei gruppi. Se il nome della valutazione corrisponde al nome di un'altra valutazione in un determinato gruppo, verrà visualizzato un errore che richiede di creare un nome diverso.

5. Assegnare la valutazione a un gruppo. È possibile:
    - Selezionare **Usa gruppo esistente** per assegnarlo a un gruppo già creato. oppure
    - Selezionare **Crea nuovo gruppo** per creare un nuovo gruppo e assegnare la valutazione seguente:
        - Determinare un nome per il gruppo e immetterlo nel campo sotto il pulsante di opzione.
        - È possibile **copiare i dati da un gruppo esistente,** ad esempio i dettagli e i documenti di implementazione e test, selezionando le caselle appropriate.

    Al termine, selezionare **Avanti.**

6. **Rivedere e terminare:** Nell'ultima schermata della procedura guidata vengono visualizzati il modello, il nome e il gruppo scelti per la valutazione. Puoi modificare una qualsiasi di queste impostazioni dai collegamenti sullo schermo, riportandoti ai passaggi pertinenti della procedura guidata. Quando si è pronti, selezionare **Crea valutazione.**

7. La schermata successiva conferma che la nuova valutazione è stata creata correttamente. Selezionare **Fine** per chiudere la procedura guidata e la pagina dei dettagli della nuova valutazione verrà visualizzata sullo schermo.

Se viene visualizzata una **schermata di** valutazione non riuscita dopo aver selezionato **Crea** valutazione, selezionare **Riprova** per creare di nuovo la valutazione.

È possibile modificare il nome della valutazione dopo  la creazione selezionando il pulsante Modifica nome [nell'angolo](#monitor-assessment-progress-and-controls)superiore destro della pagina dei dettagli della valutazione.

## <a name="extend-a-pre-built-assessment"></a>Estendere una valutazione pre-creata

È possibile modificare una valutazione pre-creata aggiungendo controlli e azioni di miglioramento personalizzati al modello della valutazione. Questo processo è denominato "estensione di un modello Microsoft" in Compliance Manager. Quando si estende il modello di una valutazione, riceverà gli aggiornamenti rilasciati da Microsoft, che potrebbero verificarsi quando vengono apportate modifiche al prodotto o al regolamento correlato (vedere Accettazione di aggiornamenti [per le valutazioni).](#accepting-updates-to-assessments)

Questo processo verrà completato iniziando dalla pagina dei modelli **di** valutazione anziché dalla **pagina delle valutazioni.**

**Prima di iniziare**

Per prepararsi a questo processo, è necessario prima assemblare un foglio di calcolo di Excel formattato in modo specifico per importare i dati del modello necessari. Esistono requisiti speciali per i [file di Excel](compliance-manager-templates.md#formatting-your-template-data-with-excel) formattati utilizzati nel processo di estensione. Vedere questi punti aggiuntivi per evitare errori nel processo di importazione:

- Il foglio di calcolo deve contenere solo le azioni e i controlli che si desidera aggiungere alla valutazione. 
- Il foglio di calcolo non può contenere controlli o azioni già esistenti nella valutazione che si desidera modificare.
- Prendi in considerazione l'inclusione di "estensione" nel titolo del modello, ad esempio "GDPR – estensione [nome della tua società]." Ciò semplifica l'identificazione nell'elenco  nella pagina dei modelli di valutazione in modo diverso dal modello standard fornito da Microsoft o da un modello personalizzato con un nome simile.

Dopo aver formattato il foglio di calcolo, eseguire la procedura seguente.

**Passaggi per l'estensione di un modello di Compliance Manager**

1. Vai alla pagina **Modelli di valutazione** e seleziona Crea nuovo **modello.** Verrà aperta una procedura guidata per la creazione di modelli.

2. Scegliere il tipo di modello che si desidera creare. In questo caso, selezionare **Estendi un modello Microsoft,** quindi **Selezionare il modello Microsoft.**

3. Sul lato destro dello schermo viene visualizzato un riquadro a comparsa di selezione del modello, che mostra un elenco di tutti i modelli e il relativo stato attivo o inattivo. Il **contatore dei** modelli attivati mostra quanti modelli sono attualmente in uso al di fuori del numero totale disponibile per l'uso. Se si è oltre il limite, verrà visualizzato un avviso sulla barra dei messaggi. Per [ulteriori informazioni, vedere](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) Tipi di modello.

4. Sul lato destro dello schermo viene visualizzato un riquadro a comparsa di selezione del modello. Usare **la** ricerca per applicare filtri per l'individuazione del modello desiderato

5. Dopo aver individuato il modello, seleziona il pulsante di opzione a sinistra del nome e quindi seleziona **Salva.**

6. Nella schermata successiva viene visualizzato il modello selezionato. Se corretto, selezionare **Avanti.** Se non è corretto, scegliere **Seleziona un modello diverso** da scegliere di nuovo.

7. Nella schermata **Carica file** selezionare Sfoglia per **trovare** e caricare il file di Excel formattato contenente tutti i dati del modello necessari.

8. Se non si verificano problemi con il file, nella schermata successiva viene visualizzato il nome del file caricato. Selezionare **Avanti** per continuare (se è necessario modificare il file, selezionare **Carica un altro file).**

    - Se si verifica un problema con il file, nella parte superiore viene visualizzato un messaggio di errore che spiega il problema. You'll need to fix and re-upload your file. Se il foglio di calcolo non è formattato correttamente o se sono presenti informazioni non valide in alcuni campi, si verificano errori.
 
9. La **schermata Revisione e** fine mostra il numero di azioni e controlli di miglioramento e il punteggio massimo per il modello. Quando si è pronti per l'approvazione, selezionare **Avanti.** Se è necessario apportare modifiche, selezionare **Carica un file diverso.**

10. L'ultima schermata conferma la creazione di un nuovo modello. Selezionare **Fine per** uscire dalla procedura guidata.

11. Arriverai alla pagina dei dettagli del nuovo modello. Da qui è possibile creare la valutazione selezionando **Crea valutazione.** Per indicazioni, iniziare dal passaggio #4 nelle istruzioni per la [creazione della valutazione precedenti.](#to-create-an-assessment)

## <a name="create-your-own-custom-assessment"></a>Creare una valutazione personalizzata

Per creare una valutazione personalizzata in Compliance Manager è necessario creare un modello personalizzato. Per creare un modello personalizzato, è necessario innanzitutto assemblare un foglio di calcolo di Excel formattato per importare i dati del modello necessari. Consente inoltre di decidere in anticipo a quale gruppo assegnare la valutazione al momento della creazione (ulteriori informazioni sui [gruppi).](#what-are-groups)

**Seguire i passaggi seguenti per creare la valutazione personalizzata:**

1. **Formattare il file di Excel.** Per iniziare, formattare i dati del modello in un foglio di calcolo di Excel usando [queste istruzioni.](compliance-manager-templates.md#formatting-your-template-data-with-excel)

2. **Crea il modello** seguendo [queste istruzioni.](compliance-manager-templates.md#create-a-new-template)

3. **Creare la valutazione** dal modello. È possibile iniziare aprendo la pagina dei dettagli del modello  e selezionando Crea valutazione **oppure** passare alla pagina delle valutazioni e selezionare **Crea valutazione.**

4. Una procedura guidata per la creazione di una valutazione verrà visualizzata in un riquadro a comparsa di grandi dimensioni. Da qui è possibile seguire le indicazioni a partire dal passaggio #3 delle istruzioni per la creazione della [valutazione,](#to-create-an-assessment)usando il nuovo modello personalizzato per la valutazione.

## <a name="delete-an-assessment"></a>Eliminare una valutazione

L'eliminazione di una valutazione la rimuove dall'elenco nella pagina delle valutazioni. Tenere presente questi punti importanti sull'eliminazione delle valutazioni:

- **L'eliminazione di una valutazione è permanente; non è possibile ottenerlo.** Se si desidera utilizzare di nuovo la stessa valutazione, sarà necessario crearla di nuovo.
- Se le azioni di miglioramento nella valutazione non vengono visualizzate in altre valutazioni, verranno eliminate quando la valutazione viene eliminata.
- È [consigliabile esportare un report](#export-an-assessment-report) della valutazione prima di eliminarlo definitivamente.

Per eliminare una valutazione, eseguire la procedura seguente:

1. Nella pagina **delle valutazioni** selezionare la valutazione che si desidera eliminare per aprire la pagina dei dettagli della valutazione.

2. Seleziona **Elimina valutazione** nell'angolo in alto a destra dello schermo.

3. Verrà visualizzata una finestra in cui viene chiesto di confermare l'eliminazione definitiva della valutazione. Selezionare **Elimina valutazione** per chiudere la finestra. Verrà visualizzata una finestra di conferma che indica che la valutazione è stata eliminata da Compliance Manager.

Se si elimina l'unica valutazione in un gruppo, tale gruppo viene eliminato anche da Compliance Manager.

> [!NOTE]
> Non è possibile eliminare tutte le valutazioni. Le organizzazioni necessitano di almeno una valutazione per il corretto funzionamento di Compliance Manager. Se la valutazione che si desidera eliminare è l'unica, aggiungere un'altra valutazione prima di eliminare l'altra valutazione.

## <a name="monitor-assessment-progress-and-controls"></a>Monitorare l'avanzamento della valutazione e i controlli

Ogni valutazione ha una pagina dei dettagli che offre una panoramica dei tuoi progressi nel completamento della valutazione. La pagina mostra lo stato di avanzamento del completamento dei controlli e lo stato di test delle azioni di miglioramento chiave all'interno di tali controlli.

### <a name="overview-tab"></a>Scheda Panoramica

La scheda panoramica contiene un grafico che mostra la percentuale di completamento della valutazione. Questo grafico contiene un'analisi dei punti delle azioni di cui si è proprietari e dei punti delle azioni di proprietà di Microsoft, in modo da poter vedere quanti altri punti sono necessari per completare la valutazione.

Le azioni di miglioramento chiave per i controlli nella valutazione sono elencate in ordine di massimo impatto potenziale per guadagnare punti. Nel grafico associato viene indicato in dettaglio lo stato aggregato dei test delle azioni di miglioramento, in modo da poter valutare rapidamente cosa è stato testato e cosa è ancora necessario fare.

Per accedere alle singole azioni di miglioramento, visitare la **scheda Controlli** o Le **azioni di** miglioramento.

### <a name="controls-tab"></a>Scheda Controlli

Nella scheda dei controlli vengono visualizzate informazioni dettagliate per ogni controllo mappato alla valutazione. Un **grafico di scomposizione** dello stato dei controlli mostra lo stato dei controlli in base alla famiglia, in modo da poter vedere a colpo d'occhio quali raggruppamenti di controlli necessitano attenzione.

Sotto il grafico, una tabella elenca informazioni dettagliate su ogni controllo all'interno della valutazione. I controlli sono raggruppati in base alla famiglia di controlli. Espandi il nome di ogni famiglia per visualizzare i singoli controlli in esso contenuti. Le informazioni elencate per ogni controllo includono:

- **Titolo del controllo**
- **Status**: riflette lo stato di test delle azioni di miglioramento all'interno del controllo 
    - **Superato:** tutte le azioni di miglioramento hanno lo stato di test "superato" o almeno una è stata superata e le altre sono "fuori ambito"
    -  **Failed:** almeno un'azione di miglioramento ha lo stato test "failed"
    - **Nessuna:** tutte le azioni di miglioramento non sono state testate
    - **Fuori ambito:** tutte le azioni di miglioramento non sono nell'ambito di questa valutazione
    - **In corso:** le azioni di miglioramento hanno uno stato diverso da quello elencato in precedenza, che potrebbe includere "in corso", "credito parziale" o "non rilevato"
- **ID controllo**: numero di identificazione del controllo, assegnato dal corrispondente regolamento, standard o criterio
- **Punti ottenuti:** il numero di punti ottenuti completando le azioni, del numero totale di punti raggiungibili 
- **Azioni :** numero di azioni completate al di fuori del numero totale di azioni da eseguire
- **Azioni Microsoft**: numero di azioni completate da Microsoft 

Per visualizzare i dettagli di un controllo, selezionarlo dalla riga corrispondente nella tabella. La pagina dei dettagli del controllo mostra un grafico che indica lo stato di test delle azioni all'interno di tale controllo. Una tabella sotto il grafico mostra le principali azioni di miglioramento per tale controllo.

Selezionare un'azione di miglioramento dall'elenco per eseguire il drill-down nella pagina dei dettagli dell'azione di miglioramento. Le pagine dei dettagli mostrano lo stato del test, le note sull'implementazione e l'avvio nella soluzione consigliata.

### <a name="your-improvement-actions-tab"></a>Scheda Azioni di miglioramento

Nella scheda per le azioni di miglioramento sono elencati tutti i controlli della valutazione gestiti dall'organizzazione. La barra di stato contiene informazioni dettagliate sullo stato aggregato dei test delle azioni di miglioramento nella valutazione, in modo da poter valutare rapidamente cosa è stato testato e cosa è ancora necessario fare. Sotto la barra è riportato l'elenco completo delle azioni di miglioramento e dei dettagli chiave, tra cui: stato del test, numero di punti potenziali e ottenuti, normative e standard associati, soluzione applicabile, tipo di azione e famiglia di controlli. Ulteriori informazioni su [come le azioni contribuiscono al punteggio di conformità.](compliance-score-calculation.md#action-types-and-points)

Selezionare un'azione di miglioramento per visualizzarne la pagina dei dettagli e selezionare il **collegamento** Avvia ora per aprire la soluzione per eseguire l'azione.

### <a name="microsoft-actions-tab"></a>Scheda Azioni Microsoft

Nella scheda Azioni Microsoft sono elencate tutte le azioni della valutazione gestite da Microsoft. L'elenco mostra i dettagli principali delle azioni, tra cui: stato del test, punti che contribuiscono al punteggio di conformità complessivo, normative e standard associati, soluzione applicabile, tipo di azione e famiglia di controlli. Selezionare un'azione di miglioramento per visualizzarne la pagina dei dettagli.

Ulteriori informazioni sul [modo in cui i controlli e le azioni di miglioramento vengono monitorati e classificati.](compliance-score-calculation.md)

## <a name="accepting-updates-to-assessments"></a>Accettazione degli aggiornamenti alle valutazioni

Quando un aggiornamento è disponibile per una valutazione, vedrai una notifica e avrai la possibilità di accettarlo o rinviare l'aggiornamento per un secondo momento.

### <a name="what-causes-an-update"></a>Cause di un aggiornamento

Un aggiornamento di valutazione si verifica quando sono presenti modifiche al modello sottostanti che influiscono sul punteggio. Le modifiche possono implicare la modifica del mapping dei controlli o altre indicazioni in base alle modifiche normative o ai cambiamenti del prodotto. Gli aggiornamenti di valutazione possono provenire dall'organizzazione (ad esempio, quando [viene](compliance-manager-templates.md#modify-a-template)modificato un modello personalizzato) e da Microsoft.

Se Microsoft aggiorna un modello di Compliance Manager esteso, la valutazione erediterà tali aggiornamenti una volta accettati. La valutazione manterrà gli attributi aggiuntivi applicati alla valutazione al momento dell'estensione.

Le valutazioni personalizzate create dall'utente non ricevono aggiornamenti dei modelli da Microsoft. Le valutazioni personalizzate possono ricevere aggiornamenti delle azioni di miglioramento, ma qualsiasi aggiornamento Microsoft per controllare il mapping tra le valutazioni e le azioni di miglioramento non si applica ai modelli personalizzati.

> [!NOTE]
> Gli aggiornamenti alle valutazioni si applicano solo a livello di gruppo. Se si dispone di due valutazioni create dallo stesso modello presenti in due gruppi diversi, ogni valutazione avrà una notifica di aggiornamento in sospeso e sarà necessario accettare l'aggiornamento di ogni valutazione nel rispettivo gruppo singolarmente.

#### <a name="where-youll-see-assessment-update-notifications"></a>Dove vedrai le notifiche di aggiornamento della valutazione

La pagina dei dettagli della valutazione mostra anche **un'etichetta di** aggiornamento in sospeso accanto alla valutazione con un aggiornamento. Selezionare tale valutazione per accedere alla relativa pagina dei dettagli.

Un messaggio nella parte superiore della pagina dei dettagli della valutazione mostra che è disponibile un aggiornamento per tale valutazione. Seleziona il **pulsante Rivedi** aggiornamento nel banner per rivedere le modifiche specifiche e accettare o rinviare l'aggiornamento.

La pagina dei dettagli della valutazione può anche elencare le azioni di miglioramento con un'etichetta **di** aggiornamento in sospeso accanto. Tali aggiornamenti sono per modifiche specifiche alle azioni di miglioramento e devono essere accettati separatamente. Per [altre informazioni, vedere Accettazione di aggiornamenti per le azioni](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) di miglioramento.

#### <a name="review-update-to-accept-or-defer"></a>Rivedere l'aggiornamento da accettare o rinviare

Dopo aver **selezionato Rivedi** aggiornamento dalla pagina dei dettagli della valutazione, viene visualizzato un riquadro a comparsa sul lato destro dello schermo. Il riquadro a comparsa fornisce i dettagli principali seguenti sull'aggiornamento in sospeso:

- Titolo del modello
- Origine dell'aggiornamento (Microsoft, l'organizzazione o un utente specifico)
- Data di creazione dell'aggiornamento
- Panoramica dell'aggiornamento
- Dettagli specifici sulle modifiche, tra cui l'impatto sul punteggio di conformità, la quantità di progressi verso il completamento della valutazione e il numero specifico di modifiche alle azioni di miglioramento e ai controlli.

Se si **seleziona il collegamento Modello** aggiornato, verrà scaricato un file di Excel contenente i dati del controllo per la versione del modello con gli aggiornamenti in sospeso. Se si **seleziona il** collegamento Modello corrente, viene scaricato un file del modello esistente senza modifiche.

Per accettare l'aggiornamento e apportare le modifiche alla valutazione, selezionare **Accetta aggiornamento.** Le modifiche accettate sono permanenti.

Se si seleziona **Annulla,** l'aggiornamento non verrà applicato alla valutazione. Tuttavia, continuerai a vedere la notifica di **aggiornamento** in sospeso fino a quando non accetti l'aggiornamento.

**Perché è consigliabile accettare gli aggiornamenti**

L'accettazione degli aggiornamenti garantisce di disporre delle indicazioni più aggiornate sull'utilizzo delle soluzioni e sull'esecuzione di azioni di miglioramento appropriate per soddisfare i requisiti della certificazione a portata di mano.

**Motivo per cui potrebbe essere necessario rinviare un aggiornamento**

Se si sta completando una valutazione, è possibile assicurarsi di aver completato il lavoro prima di accettare un aggiornamento della valutazione che potrebbe interrompere il mapping dei controlli. Puoi rinviare l'aggiornamento in un secondo momento selezionando **Annulla** nel riquadro a comparsa per l'aggiornamento della revisione.

## <a name="export-an-assessment-report"></a>Esportare un report di valutazione

È possibile esportare una valutazione in un file Excel per gli stakeholder della conformità nell'organizzazione o per revisori ed enti normativi esterni. Nella pagina dei dettagli della valutazione selezionare il pulsante Genera **report** nella parte superiore della pagina, che consente di creare un file di Excel che è possibile salvare e condividere.

Il report è uno snapshot della valutazione alla data e all'ora dell'esportazione. Contiene i dettagli per i controlli gestiti dall'utente e da Microsoft, inclusi lo stato dell'implementazione, la data di test e i risultati dei test.