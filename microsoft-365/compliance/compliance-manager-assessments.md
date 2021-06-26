---
title: Creare e gestire valutazioni in Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Creare valutazioni in Microsoft Compliance Manager per soddisfare i requisiti di normative e certificazioni importanti per l'organizzazione.
ms.openlocfilehash: 4530f8544834c672b3ae1ebb70625ffe8f2ae4ae
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148939"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Creare e gestire valutazioni in Compliance Manager

**In questo articolo:** Informazioni su come personalizzare Compliance Manager per l'organizzazione creando e gestendo **valutazioni.** In questo articolo viene illustrato come creare valutazioni, come organizzarle in **gruppi,** utilizzare i **controlli,** accettare aggiornamenti ed esportare report di  **valutazione.**

## <a name="introduction-to-assessments"></a>Introduzione alle valutazioni

Compliance Manager consente di creare valutazioni che valutano la conformità con le normative del settore e regionali applicabili all'organizzazione. Le valutazioni si basano sul framework dei modelli di valutazione, che contengono i controlli necessari, le azioni di miglioramento e le azioni Microsoft per completare la valutazione. L'impostazione delle valutazioni più rilevanti per l'organizzazione consente di implementare criteri e procedure operative per limitare i rischi di conformità.

Tutte le valutazioni sono elencate nella scheda valutazioni di Compliance Manager. Ulteriori informazioni su [come filtrare la visualizzazione delle valutazioni e interpretare gli stati di stato.](compliance-manager-setup.md#assessments-page)

> [!IMPORTANT]
> I modelli disponibili per l'organizzazione per la creazione di valutazioni dipendono dal contratto di licenza. [Esaminare i dettagli delle licenze](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="data-protection-baseline-default-assessment"></a>Valutazione predefinita di base per la protezione dei dati

Per iniziare, Microsoft fornisce  una valutazione predefinita in Compliance Manager per la Microsoft 365 **di protezione dei dati**. Questa valutazione di base include una serie di controlli per le normative e gli standard chiave per la protezione dei dati e la governance generale dei dati. Questa linea di base si basa principalmente su NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Standardization), nonché su FedRAMP (Federal Risk and Authorization Management Program) e GDPR (General Data Protection Regulation of the European Union).

Questa valutazione viene utilizzata per calcolare il punteggio di conformità iniziale la prima volta che si arriva a Compliance Manager, prima di configurare eventuali altre valutazioni. Compliance Manager raccoglie i segnali iniziali dalle Microsoft 365 soluzioni. Vedrai a colpo d'occhio le prestazioni dell'organizzazione rispetto agli standard e alle normative di protezione dei dati chiave e vedrai le azioni di miglioramento suggerite da intraprendere.

Compliance Manager diventa più utile durante la creazione e la gestione delle proprie valutazioni per soddisfare le esigenze specifiche dell'organizzazione.

## <a name="understand-groups-before-creating-assessments"></a>Comprendere i gruppi prima di creare valutazioni

Quando crei una valutazione, dovrai assegnarla a un gruppo. I gruppi sono contenitori che consentono di organizzare le valutazioni in modo logico, ad esempio in base all'anno o alla regolamentazione, o in base alle divisioni o alle aree geografiche dell'organizzazione. Per questo motivo è consigliabile pianificare una strategia di raggruppamento prima di creare valutazioni.

Di seguito sono riportati esempi di due gruppi e delle relative valutazioni sottostanti:

- **Valutazione FFIEC IS 2020**
  - FFIEC IS
- **Valutazioni della sicurezza e della privacy dei dati**
  - ISO 27001:2013
  - ISO 27018:2014

Quando due valutazioni diverse nello stesso gruppo condividono azioni di miglioramento gestite, tutti gli aggiornamenti apportati ai dettagli o allo stato di implementazione di un'azione verranno sincronizzati automaticamente in tutto il gruppo. Questa sincronizzazione consente di implementare un'unica azione di miglioramento e soddisfare diversi requisiti contemporaneamente.

### <a name="create-a-group"></a>Creare un gruppo

È possibile creare un gruppo durante la creazione di una nuova valutazione. I gruppi non possono essere creati come entità autonome.

### <a name="what-to-know-when-working-with-groups"></a>Cosa sapere quando si lavora con i gruppi

- Un gruppo deve contenere almeno una valutazione.
- I nomi dei gruppi devono essere univoci all'interno dell'organizzazione.
- I gruppi non dispongono di proprietà di sicurezza. Tutte le autorizzazioni sono associate alle valutazioni.
- Dopo aver aggiunto una valutazione a un gruppo, il raggruppamento non può essere modificato.
- Se si aggiunge una nuova valutazione a un gruppo esistente, le informazioni comuni delle valutazioni in tale gruppo vengono copiate nella nuova valutazione.
- I controlli di valutazione correlati in valutazioni diverse all'interno dello stesso gruppo vengono aggiornati automaticamente al termine.
- Quando viene apportata una modifica a un miglioramento visualizzato in più gruppi, tale modifica viene riflessa in tutte le istanze di tale azione di miglioramento.
- I gruppi possono contenere valutazioni per la stessa certificazione o regolamento, ma ogni gruppo può contenere solo una valutazione per una coppia di certificazione di prodotto specifica. Ad esempio, un gruppo non può contenere due valutazioni per Office 365 e NIST CSF. Un gruppo può contenere più valutazioni per lo stesso prodotto solo se la certificazione o il regolamento corrispondente per ognuno di essi è diverso.
- L'eliminazione di una valutazione interrompe la relazione tra tale valutazione e il gruppo.
- I gruppi non possono essere eliminati manualmente.

## <a name="create-assessments"></a>Creare valutazioni

> [!NOTE]
> Solo gli utenti che hanno un ruolo di amministratore globale, di amministrazione di Compliance Manager o di assessore di Compliance Manager possono creare e modificare le valutazioni. Ulteriori informazioni sui [ruoli e sulle autorizzazioni](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

Per iniziare a creare valutazioni, eseguire la procedura seguente.

1. Conoscere il gruppo a cui assegnare la valutazione o prepararsi a crearne uno nuovo per questa valutazione.

2. Aprire la procedura guidata di valutazione. È possibile accedere a questo riquadro a comparsa da una delle due posizioni seguenti:
    - Vai alla pagina **delle valutazioni** in Compliance Manager e seleziona **Aggiungi valutazione**; o
    - Individuare il modello che si desidera utilizzare nella scheda modelli **di** valutazione, visualizzarne i dettagli e selezionare **Crea valutazione.** Verrà popolato automaticamente il campo di selezione del modello della procedura guidata.

3. **Selezionare un modello:** se non è già stato scelto un modello nel passaggio 2, scegliere un modello da utilizzare come base per la valutazione. Vedrai l'elenco dei modelli suddivisi in categorie incluse e premium (vedi [Tipi di modelli](compliance-manager-templates.md#template-availability-and-licensing) per ulteriori informazioni). Seleziona il pulsante di opzione accanto al modello scelto, quindi seleziona **Avanti.**

4. **Nome e gruppo:** Impostare queste proprietà per identificare la valutazione e assegnarla a un gruppo.
    - **Nome**: immettere un nome per la valutazione nel **campo Nome valutazione.** I nomi di valutazione devono essere univoci all'interno dei gruppi. Se il nome della valutazione corrisponde al nome di un'altra valutazione in un determinato gruppo, verrà visualizzato un errore che richiede di creare un nome diverso.
    - **Gruppo**: assegnare la valutazione a un gruppo. È possibile:
        - Selezionare **Usa gruppo esistente** per assegnarlo a un gruppo già creato. o
        - Selezionare **Crea nuovo gruppo** per creare un nuovo gruppo e assegnarle questa valutazione:
            - Determinare un nome per il gruppo e immetterlo nel campo sotto il pulsante di opzione.
            - È possibile **copiare dati da un gruppo esistente,** ad esempio dettagli e documenti di implementazione e test, selezionando le caselle appropriate.

    Al termine, selezionare **Avanti**.

5. **Revisione e fine:** L'ultima schermata della procedura guidata mostra il modello, il nome e il gruppo scelti per la valutazione. È possibile modificare una qualsiasi di queste impostazioni dai collegamenti sullo schermo, riportandoti ai passaggi pertinenti della procedura guidata. Quando si è pronti, selezionare **Crea valutazione**.

6. La schermata successiva conferma che la nuova valutazione è stata creata correttamente. Seleziona **Fine** per chiudere la procedura guidata e la pagina dei dettagli della nuova valutazione verrà visualizzata sullo schermo.

Se viene visualizzata una **schermata Valutazione non** riuscita dopo aver selezionato **Crea** valutazione, selezionare **Riprova** per creare di nuovo la valutazione.

È possibile modificare il nome della valutazione dopo  la creazione selezionando il pulsante Modifica nome [nell'angolo](#monitor-assessment-progress-and-controls)superiore destro della pagina dei dettagli della valutazione.

## <a name="monitor-assessment-progress-and-controls"></a>Monitorare l'avanzamento della valutazione e i controlli

Ogni valutazione ha una pagina dei dettagli che offre una panoramica dei progressi nel completamento della valutazione. La pagina mostra lo stato di avanzamento del completamento dei controlli e lo stato di test delle azioni di miglioramento chiave all'interno di tali controlli.

### <a name="overview-tab"></a>Scheda Panoramica

La scheda panoramica contiene un grafico che mostra la percentuale di completamento della valutazione. Questo grafico contiene una suddivisione dei punti delle azioni di tua proprietà e dei punti delle azioni di proprietà di Microsoft, in modo da poter vedere quanti altri punti sono necessari per completare la valutazione.

Le azioni di miglioramento chiave per i controlli nella valutazione sono elencate in ordine di maggiore impatto potenziale per guadagnare punti. Il grafico associato dettaglia lo stato aggregato dei test delle azioni di miglioramento in modo da poter valutare rapidamente cosa è stato testato e cosa deve ancora essere fatto.

Per accedere alle singole azioni di miglioramento, visita la **scheda Controlli** o **Azioni di** miglioramento.

### <a name="controls-tab"></a>Scheda Controlli

Nella scheda controlli vengono visualizzate informazioni dettagliate per ogni controllo mappato alla valutazione. Un **grafico di scomposizione** dello stato dei controlli mostra lo stato dei controlli per famiglia, in modo da poter vedere a colpo d'occhio quali raggruppamenti di controlli necessitano di attenzione.

Sotto il grafico, una tabella elenca informazioni dettagliate su ogni controllo all'interno della valutazione. I controlli sono raggruppati per famiglia di controlli. Espandi il nome di ogni famiglia per visualizzare i singoli controlli in esso contenuti. Le informazioni elencate per ogni controllo includono:

- **Titolo del controllo**
- **Status**: riflette lo stato del test delle azioni di miglioramento all'interno del controllo 
    - **Superato:** tutte le azioni di miglioramento hanno lo stato di test "superato" o almeno una è stata superata e le altre sono "fuori ambito"
    -  **Non** riuscito: almeno un'azione di miglioramento ha lo stato di test "non riuscito"
    - **Nessuna:** tutte le azioni di miglioramento non sono state testate
    - **Fuori ambito:** tutte le azioni di miglioramento sono fuori ambito per questa valutazione
    - **In corso:** lo stato delle azioni di miglioramento è diverso da quello sopra elencato, che potrebbe includere "in corso", "credito parziale" o "non rilevato"
- **ID controllo**: numero di identificazione del controllo, assegnato in base al corrispondente regolamento, standard o criterio
- **Punti ottenuti**: numero di punti ottenuti completando le azioni, al di fuori del numero totale di punti raggiungibili 
- **Azioni:** numero di azioni completate dal numero totale di azioni da eseguire
- **Azioni Microsoft**: numero di azioni completate da Microsoft 

Per visualizzare i dettagli di un controllo, selezionarlo dalla relativa riga nella tabella. La pagina dei dettagli del controllo mostra un grafico che indica lo stato del test delle azioni all'interno di tale controllo. Una tabella sotto il grafico mostra le principali azioni di miglioramento per tale controllo.

Selezionare un'azione di miglioramento dall'elenco per esaminare la pagina dei dettagli dell'azione di miglioramento. Le pagine dei dettagli mostrano lo stato del test, le note sull'implementazione e l'avvio nella soluzione consigliata.

### <a name="your-improvement-actions-tab"></a>Scheda Azioni di miglioramento

Nella scheda per le azioni di miglioramento sono elencati tutti i controlli nella valutazione gestiti dall'organizzazione. La barra di stato dettaglia lo stato aggregato dei test delle azioni di miglioramento nella valutazione, in modo da poter valutare rapidamente cosa è stato testato e cosa deve ancora essere fatto. Sotto la barra è riportato l'elenco completo delle azioni di miglioramento e dei dettagli chiave, tra cui: stato del test, numero di punti potenziali e guadagnati, normative e standard associati, soluzione applicabile, tipo di azione e famiglia di controlli. Altre informazioni su [come le azioni contribuiscono al punteggio di conformità.](compliance-score-calculation.md#action-types-and-points)

Selezionare un'azione di miglioramento per visualizzarne la pagina dei dettagli e selezionare il **collegamento** Avvia ora per aprire la soluzione per eseguire l'azione.

### <a name="microsoft-actions-tab"></a>Scheda Azioni Microsoft

Nella scheda Azioni Microsoft sono elencate tutte le azioni della valutazione gestite da Microsoft. L'elenco mostra i dettagli principali dell'azione, tra cui: stato del test, punti che contribuiscono al punteggio di conformità complessivo, normative e standard associati, soluzione applicabile, tipo di azione e famiglia di controlli. Selezionare un'azione di miglioramento per visualizzarne la pagina dei dettagli.

Altre informazioni su [come vengono monitorati e](compliance-score-calculation.md) segnati i controlli e le azioni di miglioramento.

## <a name="accept-updates-to-assessments"></a>Accettare aggiornamenti per le valutazioni

Quando è disponibile un aggiornamento per una valutazione, vedrai una notifica e avrai la possibilità di accettare l'aggiornamento o rimandarlo in un secondo momento.

### <a name="what-causes-an-update"></a>Cosa causa un aggiornamento

Un aggiornamento di valutazione si verifica quando sono presenti modifiche al modello sottostanti che influiscono sul punteggio. Le modifiche possono comportare la modifica del mapping dei controlli o altre indicazioni basate su modifiche normative o modifiche al prodotto. Gli aggiornamenti di valutazione possono provenire dall'organizzazione (ad esempio, quando viene modificato un modello [personalizzato)](compliance-manager-templates.md#modify-a-template)e da Microsoft.

Se Microsoft aggiorna un modello di Compliance Manager esteso, la valutazione erediterà tali aggiornamenti dopo averli accettati. La valutazione manterrà gli attributi aggiuntivi applicati alla valutazione quando è stata estesa.

Le valutazioni personalizzate create dall'utente non ricevono aggiornamenti dei modelli da Microsoft. Le valutazioni personalizzate possono ricevere aggiornamenti delle azioni di miglioramento, ma qualsiasi aggiornamento Microsoft per controllare il mapping tra valutazioni e azioni di miglioramento non si applica ai modelli personalizzati.

> [!NOTE]
> Gli aggiornamenti alle valutazioni si applicano solo a livello di gruppo. Se si dispone di due valutazioni create dallo stesso modello che esistono in due gruppi diversi, ogni valutazione avrà una notifica di aggiornamento in sospeso e sarà necessario accettare l'aggiornamento di ogni valutazione nel rispettivo gruppo singolarmente.

#### <a name="where-youll-see-assessment-update-notifications"></a>Dove vedrai le notifiche di aggiornamento della valutazione

La pagina dei dettagli della valutazione mostra anche **un'etichetta Aggiornamento** in sospeso accanto alla valutazione con un aggiornamento. Seleziona tale valutazione per accedere alla relativa pagina dei dettagli.

Un messaggio nella parte superiore della pagina dei dettagli della valutazione mostra che è disponibile un aggiornamento per tale valutazione. Seleziona il **pulsante Rivedi** aggiornamento nel banner per rivedere le modifiche specifiche e accettare o rinviare l'aggiornamento.

La pagina dei dettagli della valutazione può anche elencare le azioni di miglioramento con un'etichetta **Aggiornamento** in sospeso accanto a esse. Tali aggiornamenti sono per modifiche specifiche alle azioni di miglioramento stesse e devono essere accettati separatamente. Per [altre informazioni, vedere Accettazione degli aggiornamenti per le azioni](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) di miglioramento.

#### <a name="review-update-to-accept-or-defer"></a>Rivedere l'aggiornamento per accettare o rinviare

Dopo aver **selezionato Rivedi** aggiornamento dalla pagina dei dettagli della valutazione, viene visualizzato un riquadro a comparsa sul lato destro dello schermo. Il riquadro a comparsa fornisce i dettagli principali seguenti sull'aggiornamento in sospeso:

- Titolo del modello
- Origine dell'aggiornamento (Microsoft, l'organizzazione o un utente specifico)
- Data di creazione dell'aggiornamento
- Panoramica dell'aggiornamento
- Dettagli specifici sulle modifiche, tra cui l'impatto sul punteggio di conformità, la quantità di progressi verso il completamento della valutazione e il numero specifico di modifiche apportate alle azioni di miglioramento e ai controlli.

Selezionando il **collegamento Modello** aggiornato verrà scaricato un file Excel contenente i dati di controllo per la versione del modello con gli aggiornamenti in sospeso. Se si **seleziona il collegamento** Modello corrente, viene scaricato un file del modello esistente senza le modifiche.

Per accettare l'aggiornamento e apportare le modifiche alla valutazione, selezionare **Accetta aggiornamento**. Le modifiche accettate sono permanenti.

Se si seleziona **Annulla**, l'aggiornamento non verrà applicato alla valutazione. Tuttavia, continuerai a visualizzare la notifica **di** aggiornamento in sospeso fino a quando non accetti l'aggiornamento.

**Perché è consigliabile accettare gli aggiornamenti**

L'accettazione degli aggiornamenti garantisce di disporre delle indicazioni più aggiornate sull'utilizzo delle soluzioni e sull'esecuzione di azioni di miglioramento appropriate per soddisfare i requisiti della certificazione a portata di mano.

**Motivo per cui potrebbe essere necessario rinviare un aggiornamento**

Se si sta completando una valutazione, è possibile assicurarsi di aver completato il lavoro prima di accettare un aggiornamento della valutazione che potrebbe interrompere il mapping del controllo. È possibile rinviare l'aggiornamento in un secondo momento selezionando **Annulla** nel riquadro a comparsa di revisione dell'aggiornamento.

## <a name="export-an-assessment-report"></a>Esportare un report di valutazione

È possibile esportare una valutazione in un file Excel per le parti interessate alla conformità nell'organizzazione o per revisori esterni e autorità di regolamentazione. Nella pagina dei dettagli della valutazione seleziona il pulsante Genera **report** nella parte superiore della pagina, che crea un file Excel che puoi salvare e condividere.

Il report è uno snapshot della valutazione alla data e all'ora dell'esportazione. Contiene i dettagli per i controlli gestiti dall'utente e da Microsoft, inclusi lo stato dell'implementazione, la data del test e i risultati dei test.

## <a name="delete-an-assessment"></a>Eliminare una valutazione

L'eliminazione di una valutazione la rimuove dall'elenco nella pagina delle valutazioni. Tenere presente questi punti importanti sull'eliminazione delle valutazioni:

- **L'eliminazione di una valutazione è permanente. non è possibile ottenerlo.** Se si desidera utilizzare di nuovo la stessa valutazione, sarà necessario crearla di nuovo.
- Se le azioni di miglioramento nella valutazione non vengono visualizzate in altre valutazioni, verranno eliminate quando la valutazione viene eliminata.
- È [consigliabile esportare un report](#export-an-assessment-report) della valutazione prima di eliminarlo definitivamente.

Per eliminare una valutazione, eseguire la procedura seguente:

1. Nella pagina **delle valutazioni** seleziona la valutazione che vuoi eliminare per aprire la pagina dei dettagli della valutazione.

2. Seleziona **Elimina valutazione** nell'angolo superiore destro dello schermo.

3. Verrà visualizzata una finestra in cui viene chiesto di confermare l'eliminazione definitiva della valutazione. Selezionare **Elimina valutazione** per chiudere la finestra. Si otterrà una finestra di conferma che la valutazione è stata eliminata da Compliance Manager.

Se si elimina l'unica valutazione in un gruppo, anche tale gruppo viene eliminato da Compliance Manager.

> [!NOTE]
> Non è possibile eliminare tutte le valutazioni. Le organizzazioni necessitano di almeno una valutazione per il corretto funzionamento di Compliance Manager. Se la valutazione che si desidera eliminare è l'unica, aggiungere un'altra valutazione prima di eliminare l'altra valutazione.
