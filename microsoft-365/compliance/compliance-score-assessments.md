---
title: Personalizzare il Punteggio di conformità Microsoft con le valutazioni
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
description: Progettare la personalizzazione del Punteggio di conformità di Microsoft creando valutazioni che consentano di gestire la conformità per l'organizzazione.
ms.openlocfilehash: 8b27267461e226a6db2173158d2d35238c0d5a5e
ms.sourcegitcommit: 8595cb9ffe0ca5556080f24224182381e1d880de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2020
ms.locfileid: "45035631"
---
# <a name="customize-compliance-score-preview-with-assessments"></a>Personalizzare il Punteggio di conformità (Preview) con le valutazioni

**In questo articolo:** Informazioni su come personalizzare il Punteggio di conformità impostando le **valutazioni**pronte per l'uso. Leggere come modificare il **modello** per una valutazione e creare valutazioni personalizzate in base alle esigenze dell'organizzazione. In questo articolo viene inoltre illustrato come organizzare le valutazioni in **gruppi**, utilizzare i **controlli**ed esportare i **report**di valutazione.

## <a name="introduction-to-assessments"></a>Introduzione alle valutazioni

Il Punteggio di conformità consente di gestire la conformità alle valutazioni per le normative e le certificazioni che si applicano all'organizzazione. Le valutazioni sono raggruppamenti di controlli di una specifica normativa, standard o criterio. Il Punteggio di conformità rende più facile iniziare a tenere traccia della conformità fornendo valutazioni pronte per l'uso che coprono una vasta gamma di regolamenti e certificazioni industriali e regionali.

Ogni valutazione viene creata da un modello, che funge da Framework contenente i controlli e le azioni di miglioramento necessari per il completamento della valutazione. La configurazione delle valutazioni più rilevanti per l'organizzazione contribuisce a garantire l'implementazione di criteri e procedure operative che possano limitare i rischi di conformità.

Tutte le valutazioni sono elencate nella pagina valutazioni. [Ulteriori](compliance-score-setup.md#assessments-page) informazioni su come filtrare la visualizzazione delle valutazioni e interpretare gli Stati di stato.

## <a name="data-protection-baseline-default-assessment"></a>Valutazione predefinita del criterio di protezione dei dati

Per iniziare, Microsoft fornisce una valutazione **predefinita** del Punteggio di conformità che contiene la linea di base per la protezione dei dati di Microsoft 365. Questa linea di base è un insieme di controlli che include le normative fondamentali e gli standard per la protezione dei dati e la governance dei dati generale. Questa linea di base estrae gli elementi principalmente dal NIST CSF (Istituto nazionale per gli standard e la tecnologia Cybersecurity Framework) e ISO (International Organization for Standardizzation), oltre che da FedRAMP (Federal Risk and Authorization Management Program) e GDPR (General Data Protection Regulation dell'Unione europea).

Questa valutazione viene utilizzata per calcolare il punteggio iniziale al primo accesso al Punteggio di conformità, prima di configurare eventuali altre valutazioni. Il Punteggio di conformità raccoglie i segnali iniziali dalle soluzioni Microsoft 365. Verrà visualizzato a colpo d'occhio il modo in cui l'organizzazione è in esecuzione rispetto agli standard e alle normative sulla protezione dei dati e le azioni consigliate da intraprendere.

Poiché ogni organizzazione ha esigenze specifiche, il Punteggio di conformità si basa su di esso per configurare e gestire le proprie valutazioni per ridurre al minimo e ridurre il rischio nel modo più completo possibile.

## <a name="assessment-creation-overview"></a>Panoramica della creazione di valutazione

È possibile configurare le valutazioni in tre modi:

1. Scegliere una valutazione pronta all'uso.
2. Modificare il [modello di una valutazione](compliance-score-templates.md) in base alle proprie esigenze.
3. Creare la propria valutazione personalizzata.

Gli utenti devono mantenere un ruolo di amministratore globale, amministratore della conformità, amministratore dei dati di conformità o amministratore della sicurezza per creare o modificare le valutazioni. Per ulteriori informazioni [, vedere ruoli e autorizzazioni](compliance-score-setup.md#set-user-permissions-and-assign-roles).

> [!NOTE]
> Qualsiasi valutazione creata o modificata nel punteggio di conformità verrà riflessa anche in Compliance Manager. Per ulteriori informazioni [, vedere relazione tra conformità score e Compliance Manager](compliance-score.md#relationship-to-compliance-manager).

### <a name="ready-to-use-assessments"></a>Valutazioni pronte per l'uso

Avvia il viaggio di conformità scegliendo tra la selezione di [modelli](compliance-score-templates.md) di conformità dei punteggi per la creazione di valutazioni. I modelli contengono i controlli e le azioni di miglioramento necessari per ogni valutazione specifica. I modelli del Punteggio di conformità riguardano le normative e le certificazioni che vengono allineate a settori, aree geografiche e standard di protezione dei dati comuni, ad esempio GDPR e ISO 27001.

**Per impostare una valutazione**, scegliere uno dei modelli quando si avvia la creazione [della valutazione dalla procedura guidata](#create-an-assessment).

### <a name="modify-the-template-of-an-assessment"></a>Modificare il modello di una valutazione

È possibile modificare i modelli di Punteggio di conformità per le valutazioni al fine di soddisfare al meglio le esigenze dell'organizzazione. Ad esempio, se si ha generalmente necessità di conformarsi con HIPAA ma si richiedono ulteriori controlli di sicurezza o protezione dei dati, è possibile utilizzare il modello HIPAA e aggiungere i campi personalizzati per creare una nuova valutazione che esegua il monitoraggio dell'avanzamento nei modi necessari. Durante l'anteprima pubblica, è necessario andare alla gestione conformità per modificare i modelli.

**Per modificare il modello di una valutazione**, seguire le istruzioni riportate di seguito:

1. Consente di visualizzare l'elenco dei [modelli](compliance-score-templates.md) disponibili nel punteggio di conformità per determinare quale si desidera modificare.
2. Vedere le [istruzioni di Compliance Manager per personalizzare un modello utilizzando il processo di estensione](working-with-compliance-manager.md#customize-a-template-through-the-extension-process).
3. Dopo aver creato il modello e averlo importato in Gestione conformità, è possibile creare la nuova valutazione nel punteggio di conformità. Seguire il processo di creazione della valutazione tramite la [procedura guidata](#create-an-assessment)per la creazione di valutazioni.

> [!NOTE]
> Ulteriori informazioni sulla [relazione tra Score compliance e Compliance Manager](compliance-score.md#relationship-to-compliance-manager) durante l'anteprima pubblica.

### <a name="create-your-own-custom-assessment"></a>Creare una valutazione personalizzata

È possibile creare la propria valutazione completamente da zero per individuare con precisione le esigenze dell'organizzazione. Come nel caso del processo di modifica descritto in alto, la creazione di una propria valutazione richiede la creazione di un modello personalizzato per la valutazione in Compliance Manager.

**Per creare una valutazione personalizzata**, seguire le istruzioni riportate di seguito:

1. Leggere come [creare un modello personalizzato in Compliance Manager](working-with-compliance-manager.md#create-your-own-template-and-import-it-into-compliance-manager).
2. Dopo aver creato il modello e averlo importato in Gestione conformità, è possibile creare la nuova valutazione nel punteggio di conformità. Seguire il processo di creazione della valutazione tramite la [procedura guidata](#create-an-assessment)per la creazione di valutazioni.

## <a name="understand-groups-before-creating-assessments"></a>Comprendere i gruppi prima di creare valutazioni

Prima di creare o modificare le valutazioni, è importante comprendere il funzionamento del gruppo. Quando si crea una valutazione, è necessario assegnarla a un gruppo durante tale processo. È pertanto consigliabile pianificare una strategia di raggruppamento per le proprie valutazioni prima di creare valutazioni.

### <a name="what-are-groups"></a>Cosa sono i gruppi

I gruppi sono contenitori che consentono di organizzare valutazioni. È possibile raggruppare le valutazioni in modo logico, ad esempio per anno o regolamento, o in base alle divisioni o alle aree geografiche dell'organizzazione. Di seguito sono riportati alcuni esempi di due gruppi e le relative valutazioni sottostanti:

- **FFIEC è valutazioni 2020**
  - Office 365 + FFIEC è
  - Intune + FFIEC è
- **Valutazione della sicurezza e della privacy dei dati**
  - Office 365 e ISO 27001:2013
  - Office 365 e ISO 27018:2014

Quando due diverse valutazioni nelle stesse azioni di miglioramento della condivisione di gruppo gestite dall'utente, tutti gli aggiornamenti apportati ai dettagli di implementazione o allo stato di un'azione verranno sincronizzati automaticamente alla stessa azione in qualsiasi altra valutazione del gruppo. Questa sincronizzazione consente di implementare un'azione di miglioramento e di soddisfare diversi requisiti in più normative.

### <a name="how-to-create-a-group"></a>Come creare un gruppo

È possibile creare un gruppo durante il processo di [creazione di una nuova valutazione](#create-an-assessment).

I gruppi non possono essere creati come entità autonome; un gruppo deve contenere almeno una valutazione. Per creare un gruppo, è necessario innanzitutto creare una valutazione da inserire nel gruppo.

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

## <a name="create-an-assessment"></a>Creare una valutazione

Per creare una valutazione con punteggio di conformità, attenersi alla procedura seguente:

1. Nella pagina valutazioni fare clic su **Aggiungi valutazione**. Una procedura guidata di valutazione verrà visualizzata in un riquadro a comparsa di grandi dimensioni.

2. **Selezionare un modello:** Scegliere un modello che funga da base per la valutazione. È possibile scegliere un modello pronto per l'uso o un modello che è stato modificato o creato. Selezionare il pulsante di opzione accanto al modello scelto, quindi fare clic su **Avanti**.

> [!NOTE]
> Vedere [le istruzioni per la creazione e la modifica dei modelli](working-with-compliance-manager.md#templates), un processo gestito in Compliance Manager.

3. **Nome e gruppo:** Immettere un nome per la valutazione nel campo **nome valutazione** . I nomi di valutazione devono essere univoci all'interno dei gruppi. Se il nome della valutazione corrisponde al nome di un'altra valutazione in un determinato gruppo, verrà visualizzato un messaggio di errore in cui viene chiesto di creare un altro nome.

4. Assegnare la valutazione a un gruppo. È possibile eseguire le operazioni seguenti:
    - Selezionare **Usa gruppo esistente** per assegnarlo a un gruppo già creato; o
    - Selezionare **Crea nuovo gruppo** per creare un nuovo gruppo e assegnargli questa valutazione. Determinare un nome per il gruppo e inserirlo nel campo sotto il pulsante di opzione.

5. **Revisione e finitura:** Nell'ultima schermata della procedura guidata vengono visualizzati il modello, il nome e il gruppo scelti per la valutazione. È possibile modificare una qualsiasi di queste impostazioni dai collegamenti sullo schermo, che riportano ai passaggi rilevanti della procedura guidata. Dopo aver soddisfatto le impostazioni, selezionare **Crea valutazione**.

6. La schermata successiva conferma di aver creato correttamente la nuova valutazione. Fare **clic su fine per** chiudere la procedura guidata e sullo schermo verrà visualizzata la pagina dei dettagli della nuova valutazione.

Se viene visualizzata una schermata di **valutazione non riuscita** dopo aver selezionato **Crea valutazione**, fare clic su **Riprova** per ricreare la valutazione.

## <a name="delete-an-assessment"></a>Eliminare una valutazione

L'eliminazione di una valutazione lo rimuove dall'elenco nella pagina valutazioni. **L'eliminazione di una valutazione è permanente. non è possibile ottenerlo nuovamente.** Se si desidera eseguire di nuovo la stessa valutazione, è necessario ricrearla da zero. Se le azioni di miglioramento nella valutazione non vengono visualizzate in altre valutazioni, queste verranno eliminate quando viene eliminata la valutazione. È consigliabile esportare un rapporto di valutazione prima di eliminarlo definitivamente.

Per eliminare una valutazione, attenersi alla procedura seguente:

1. Nella pagina valutazioni selezionare la valutazione che si desidera eliminare per aprire la pagina dei dettagli della valutazione.
2. Selezionare **Elimina valutazione** nell'angolo in alto a destra dello schermo.
3. Verrà visualizzata una finestra in cui viene chiesto di confermare che si desidera eliminare definitivamente la valutazione. Selezionare **Elimina valutazione** per chiudere la finestra. Verrà visualizzata una finestra di conferma per la quale è stata eliminata la valutazione dal punteggio di conformità.

Se si elimina l'unica valutazione in un gruppo, tale gruppo viene eliminato anche dal punteggio di conformità.

## <a name="monitor-assessment-progress-and-controls"></a>Monitorare lo stato e i controlli di valutazione

Ogni valutazione contiene una pagina dei dettagli che fornisce una visualizzazione a colpo d'occhio dello stato di avanzamento per il completamento della valutazione. La pagina mostra lo stato di avanzamento del processo di completamento dei controlli e lo stato del test delle azioni di miglioramento principali all'interno di tali controlli.

### <a name="overview-tab"></a>Scheda Panoramica

La scheda Panoramica contiene un grafico che mostra la percentuale verso il completamento della valutazione. Questo grafico contiene una ripartizione dei punti dalle azioni possedute e punti dalle azioni di Microsoft, in modo da poter vedere quanti più punti è necessario per completare la valutazione.

Le azioni di miglioramento principali per i controlli nella valutazione sono elencate in ordine di maggiore impatto potenziale per ottenere punti. Il grafico associato descrive lo stato di test aggregato delle azioni di miglioramento, in modo da poter valutare rapidamente cosa è stato testato e cosa è necessario fare.

Per accedere alle singole azioni di miglioramento, passare alla scheda controlli.

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

#### <a name="learn-more"></a>Altre informazioni
[Comprendere in che modo i controlli e le azioni di miglioramento vengono registrati e segnati dal punteggio di conformità.](compliance-score-methodology.md)

## <a name="export-an-assessment-report"></a>Esportare un report di valutazione

È possibile esportare una valutazione in un file di Excel per la conformità delle parti interessate nell'organizzazione o per i revisori esterni e i regolatori [attenendosi alle istruzioni](working-with-compliance-manager.md#reports)riportate di seguito. Per esportare il report, è necessario visitare Compliance Manager.

Il report è un'istantanea della valutazione alla data e all'ora dell'esportazione. Contiene i dettagli per i controlli gestiti da Microsoft, compresi lo stato di implementazione, la data del test, i risultati dei test e i collegamenti ai documenti di prova caricati.