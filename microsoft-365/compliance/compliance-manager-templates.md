---
title: Utilizzo dei modelli di valutazione in Microsoft Compliance Manager
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
description: Informazioni su come usare e gestire i modelli per la creazione di valutazioni in Microsoft Compliance Manager. Creare e modificare modelli utilizzando un file Excel formattato.
ms.openlocfilehash: 2d20fa69345f2ff2624252972cb0e017e401f0dd
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149131"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Utilizzo dei modelli di valutazione in Compliance Manager

**In questo articolo:** Comprendere **il funzionamento dei modelli** e come **gestirli** dalla pagina dei modelli di valutazione. Istruzioni per la **creazione di** nuovi modelli, **l'estensione** e la modifica di modelli esistenti, la formattazione dei dati del modello **con** Excel e l'esportazione di report **modello.** 

> [!IMPORTANT]
> I modelli di valutazione disponibili per l'organizzazione dipendono dal contratto di licenza. [Esaminare i dettagli](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="templates-overview"></a>Panoramica dei modelli

Un modello è un framework di controlli per la creazione di una valutazione in Compliance Manager. Il nostro set completo di modelli può aiutare l'organizzazione a rispettare i requisiti nazionali, regionali e specifici del settore che regolano la raccolta e l'uso dei dati. Ci riferiamo ai modelli con lo stesso nome della certificazione o del regolamento sottostante, ad esempio il modello GDPR dell'UE e il modello ISO/IEC 27701:2019.

## <a name="template-availability-and-licensing"></a>Disponibilità e licenze dei modelli

I modelli disponibili per l'utilizzo si basano sul contratto di licenza dell'organizzazione ([visualizzare i dettagli della licenza](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)). Esistono due categorie di modelli: incluso e premium.

#### <a name="included-and-premium-templates"></a>Modelli inclusi e premium

1. **I modelli inclusi** sono concessi dalla licenza e dai requisiti e dalle normative chiave di copertura.
2. **Premium modelli possono** essere acquistati per espandere la raccolta e soddisfare esigenze specifiche. Dopo l'acquisto, è possibile creare tutte le valutazioni da un modello in base alle esigenze. [Scopri come acquistare modelli premium.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

Visualizzare [l'elenco completo dei modelli](compliance-manager-templates-list.md).

#### <a name="active-and-inactive-templates"></a>Modelli attivi e inattivi

I modelli visualizzano lo stato di attivazione attivo o inattivo:

- Un modello viene considerato **attivo** dopo aver creato una valutazione da tale modello.
- Un modello viene considerato **inattivo** se l'organizzazione non lo usa per una valutazione.

Quando acquisti un modello premium e crei una valutazione da esso, tale modello è attivo per un anno. L'acquisto verrà rinnovato automaticamente a meno che non venga annullato.

Puoi anche provare i modelli premium in base alla versione di valutazione. Le licenze di valutazione sono valide per un massimo di 25 modelli per 30 giorni. Una volta avviata la versione di valutazione, i modelli dovrebbero diventare disponibili nel tenant entro 48 ore. Le versioni di valutazione possono essere attivate tramite interfaccia di amministrazione di Microsoft 365.

#### <a name="activated-templates-counter"></a>Contatore dei modelli attivati

La pagina di valutazione e la pagina dei modelli di valutazione hanno un **contatore dei modelli** attivato nella parte superiore. Il contatore visualizza il numero di modelli in uso al di fuori del numero che sei idoneo a usare in base al contratto di licenza. L'utilizzo dei modelli viene conteggiato a livello di certificazione.

Ad esempio, se il contatore mostra 2/5, significa che l'organizzazione ha attivato 2 modelli dei 5 disponibili per l'utilizzo.

Se il contatore indica 5/2, significa che l'organizzazione supera i limiti e deve acquistare 3 dei modelli premium in uso.

Per ulteriori dettagli, vedere [Linee guida sulla gestione delle licenze di Compliance Manager.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

## <a name="view-and-manage-templates"></a>Visualizzare e gestire i modelli

Nella pagina modelli di valutazione in Compliance Manager viene visualizzato un elenco di modelli e dettagli chiave su di essi. L'elenco include i modelli forniti da Compliance Manager e tutti i modelli modificati o creati dall'organizzazione. È possibile applicare filtri per trovare un modello basato su certificazione, ambito del prodotto, paese, settore, chi lo ha creato e se il modello è abilitato per la creazione della valutazione.

Selezionare un modello dalla riga corrispondente per visualizzare la relativa pagina dei dettagli. Questa pagina contiene una descrizione del modello e ulteriori informazioni sulla certificazione, l'ambito e i dettagli dei controlli. Da questa pagina è possibile selezionare i pulsanti appropriati per creare una valutazione, esportare i dati del modello Excel o modificare il modello.

## <a name="format-template-data-with-excel"></a>Formatta i dati del modello con Excel

Il Excel foglio di calcolo ([scaricare](https://go.microsoft.com/fwlink/?linkid=2124865)un esempio ) utilizzato per creare o modificare modelli ha un formato e uno schema specifici che devono essere utilizzati per eseguire correttamente l'importazione in Compliance Manager. Contiene quattro schede, tre delle quali sono necessarie:

1. [Modello](#template-tab) (obbligatorio)
2. [ControlFamily](#controlfamily-tab) (obbligatorio)
3. [Azioni](#actions-tab) (obbligatorio)
4. [Dimensioni](#dimensions-tab) (facoltativo)

Quando si compila il foglio di calcolo con i dati del modello, il foglio di calcolo deve includere le schede nell'ordine indicato in precedenza, **altrimenti** i dati non verranno importati correttamente in un modello.

##### <a name="template-tab"></a>Scheda Modello

La **scheda Modello** è obbligatoria. Le informazioni contenute in questa scheda forniscono metadati sul modello. Sono disponibili quattro colonne obbligatorie. Le colonne devono mantenere l'ordine nel foglio Excel come indicato di seguito. È possibile aggiungere una colonna **personale dopo** le quattro colonne per fornire dimensioni personalizzate. In questo caso, assicurarsi di aggiungerli alla **scheda** Dimensioni.

- **title**: questo è il titolo del modello, che deve essere univoco. Non può condividere un nome con un altro modello di Compliance Manager, inclusi i propri modelli o un modello di Compliance Manager.

- **product**: si tratta di una dimensione obbligatoria. Elencare il prodotto associato al modello.

- **certification**: si tratta della normativa in uso per il modello.

- **inScopeServices**: si tratta dei servizi all'interno del prodotto a cui si rivolge questa valutazione (ad esempio, se è stato elencato Office 365 come prodotto, Microsoft Teams potrebbe essere un servizio nell'ambito). È possibile elencare più servizi separati da due punti e virgola.

> [!NOTE]
> I dati inseriti nelle  celle **del** prodotto e della certificazione non possono essere modificati dopo l'importazione del foglio di calcolo per creare o personalizzare un modello. Inoltre, un gruppo non può contenere due valutazioni con la stessa combinazione **prodotto/certificazione.** Puoi avere più modelli con la stessa combinazione di prodotto/certificazione.

##### <a name="controlfamily-tab"></a>Scheda ControlFamily

La **scheda ControlFamily** è obbligatoria.  Le colonne obbligatorie in questa scheda, che devono seguire l'ordine indicato nel foglio di calcolo di esempio, sono:

- **controlName**: Questo è il nome del controllo della certificazione, dello standard o della normativa, che in genere è un tipo di ID. I nomi dei controlli devono essere univoci all'interno di un modello. Non è possibile avere più controlli con lo stesso nome nel foglio di calcolo.

- **controlFamily**: specifica una parola o una frase per controlFamily, che identifica un ampio raggruppamento di controlli. Un controlFamily non deve essere univoco. può essere elencato più di una volta in un foglio di calcolo. Lo stesso controlFamily può anche essere elencato in più modelli, anche se non hanno alcuna relazione l'uno con l'altro. Ogni controlFamily deve essere mappato ad almeno un controllo.

- **controlTitle**: fornire un titolo per il controllo. Mentre controlName è un codice di riferimento, il titolo è un formato RTF in genere presente nelle normative.

- **controlDescription**: fornire una descrizione del controllo.

- **controlActionTitle**: titolo di un'azione che si desidera correlare a questo controllo. È possibile aggiungere più azioni separando due punti e virgola senza spazio tra loro. Ogni controllo elencato deve includere almeno un'azione e l'azione deve esistere, ovvero  è possibile elencare un'azione elencata nella scheda Azioni dello stesso foglio di calcolo, un'azione presente in un modello diverso o un'azione creata da Microsoft. Controlli diversi possono fare riferimento alla stessa azione.

##### <a name="actions-tab"></a>Scheda Azioni

La **scheda Azioni** è obbligatoria.  Designa le azioni di miglioramento gestite dall'organizzazione e non quelle di Microsoft, che esistono già in Compliance Manager. Le colonne obbligatorie per questa scheda, che devono seguire l'ordine indicato nel foglio di calcolo di esempio, sono:

- **actionTitle**: questo è il titolo dell'azione ed è un campo obbligatorio. Il titolo fornito deve essere univoco. **Importante:** se si fa riferimento a un'azione già esistente (ad esempio in un altro modello) e si modifica uno dei relativi elementi nelle colonne successive, tali modifiche verranno propagate alla stessa azione in altri modelli.

- **implementationType**: in questo campo obbligatorio elencare uno dei tre tipi di implementazione seguenti:
    - **Operativo** : azioni implementate da persone e processi per proteggere la riservatezza, l'integrità e la disponibilità di sistemi, risorse, dati e personale dell'organizzazione (ad esempio, consapevolezza della sicurezza e formazione)
    - **Tecnico** - Azioni completate utilizzando la tecnologia e i meccanismi contenuti nei componenti hardware, software o firmware del sistema in informazioni per proteggere la riservatezza, l'integrità e la disponibilità dei sistemi e dei dati dell'organizzazione (ad esempio: autenticazione a più fattori)
    - **Documentazione** : azioni implementate tramite criteri e procedure documentati che stabiliscono e definiscono i controlli necessari per proteggere la riservatezza, l'integrità e la disponibilità di sistemi, risorse, dati e personale dell'organizzazione (ad esempio, un criterio di sicurezza delle informazioni)

- **actionScore**: in questo campo obbligatorio, fornisci un valore di punteggio numerico per l'azione. Il valore deve essere un numero intero compreso tra 1 e 99. non può essere 0, null o vuoto. Maggiore è il numero, maggiore è il valore per migliorare la postura di conformità. L'immagine seguente mostra come Compliance Manager punteggia i controlli:

![Valori dei punti dei controlli di Compliance Manager](../media/compliance-score-action-scoring.png "Valori dei punti dei controlli di Compliance Manager")

- **actionDescriptionTitle**: questo è il titolo della descrizione ed è obbligatorio. Questo titolo della descrizione consente di eseguire la stessa azione in più modelli e di visualizzare una descrizione diversa in ogni modello.  Questo campo consente di chiarire il modello a cui fa riferimento la descrizione. Nella maggior parte dei casi, è possibile inserire il nome del modello che si sta creando in questo campo.

- **actionDescription**: fornire una descrizione dell'azione. È possibile applicare formattazioni quali testo in grassetto e collegamenti ipertestuali. Questo campo è obbligatorio.

- **dimension-Action Purpose**: campo facoltativo. Se viene incluso, l'intestazione deve includere il prefisso "dimension-". Tutte le dimensioni incluse qui verranno utilizzate come filtri in Compliance Manager e verranno visualizzate nella pagina dei dettagli delle azioni di miglioramento in Compliance Manager.

##### <a name="dimensions-tab"></a>Scheda Dimensioni

La **scheda Dimensioni** è facoltativa. Tuttavia, se si fa riferimento a una dimensione altrove, è necessario specificarla qui se non esiste in un modello già creato o in un modello Microsoft. Le colonne per questa scheda sono elencate di seguito:

- **dimensionKey**: elenco come "prodotto", "certificazioni", "scopo azione"
- **dimensionValue**: esempi: Office 365, HIPPA, Preventivo, Detective

Quando si esporta un modello esistente, il foglio di calcolo esportato avrà la scheda **Dimensioni,** in cui sono elencate tutte le dimensioni utilizzate nel modello.

## <a name="create-an-assessment-template"></a>Creare un modello di valutazione

Per creare un nuovo modello personalizzato per le valutazioni personalizzate, userai il foglio di calcolo Excel formato speciale per assemblare i dati di controllo necessari. Dopo aver completato il foglio di calcolo, lo importeremo in Compliance Manager.

#### <a name="required-roles"></a>Ruoli obbligatori

Solo gli utenti che hanno un ruolo amministratore globale o amministratore di Compliance Manager possono creare e modificare i modelli. Ulteriori informazioni sui [ruoli e sulle autorizzazioni](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

### <a name="create-new-template-in-compliance-manager"></a>Creare un nuovo modello in Compliance Manager

1. Passare alla pagina **dei modelli di** valutazione in Compliance Manager.
2. Selezionare **Crea nuovo modello.** Verrà aperta una procedura guidata per la creazione di modelli.
3. Scegliere il tipo di modello che si desidera creare. In questo caso, selezionare **Crea un modello personalizzato,** quindi selezionare **Avanti.**
4. Nella schermata **Upload file** selezionare  Sfoglia per trovare e caricare il file Excel contenente tutti i dati del modello necessari.
5. In caso di problemi con il file, verrà visualizzato il nome del file caricato. Selezionare **Avanti** per continuare. Se è necessario modificare il file, selezionare Upload **file diverso.**
    - Se si verifica un errore con il file, nella parte superiore viene visualizzato un messaggio di errore che spiega il problema. Dovrai correggere il file e caricarlo di nuovo. Gli errori si verificano se il foglio di calcolo è formattato in modo non corretto o se sono presenti informazioni non valide in alcuni campi.
6. La **schermata Revisione e** fine mostra il numero di azioni e controlli di miglioramento e il punteggio massimo per il modello. Quando sei pronto per l'approvazione, seleziona **Crea modello.** Se è necessario apportare modifiche, selezionare **Indietro.**
7. L'ultima schermata conferma la creazione di un nuovo modello. Selezionare **Fine** per uscire dalla procedura guidata.
8. Verrà visualizzata la pagina dei dettagli del nuovo modello, in cui è possibile [creare la valutazione.](compliance-manager-assessments.md#create-assessments)

## <a name="extend-an-assessment-template"></a>Estendere un modello di valutazione

Compliance Manager offre la possibilità di aggiungere controlli personalizzati e azioni di miglioramento a un modello fornito da Microsoft esistente. Questo processo è denominato estensione di un modello Microsoft. Quando estendi un modello, può comunque ricevere gli aggiornamenti rilasciati da Microsoft, cosa che può verificarsi quando vengono apportate modifiche al regolamento o al prodotto correlato (vedi Accettare aggiornamenti [per le valutazioni).](compliance-manager-assessments.md#accept-updates-to-assessments)

Per prepararti, dovrai assemblare un foglio di calcolo Excel formato specifico per importare i dati del modello necessari. I Excel file seguono lo stesso formato generale descritto in precedenza, ma esistono requisiti speciali per le estensioni. Vedi questi punti aggiuntivi per evitare errori:

- Il foglio di calcolo deve contenere solo le azioni e i controlli che si desidera aggiungere alla valutazione.
- Il foglio di calcolo non può contenere controlli o azioni già esistenti nella valutazione che si desidera modificare.
- Prendi in considerazione l'inclusione di "estensione" nel titolo del modello, ad esempio "GDPR – [nome della tua società] estensione." Ciò semplifica l'identificazione nell'elenco  nella pagina dei modelli di valutazione in modo diverso dal modello standard fornito da Microsoft o da un modello personalizzato con un nome simile.

Dopo aver formattato il foglio di calcolo, eseguire la procedura seguente.

1. Vai alla pagina **Modelli di** valutazione e seleziona Crea **nuovo modello.** Verrà aperta una procedura guidata per la creazione di modelli.

2. Scegliere il tipo di modello che si desidera creare. In questo caso, selezionare **Estendi un modello Microsoft**, **quindi Selezionare il modello Microsoft**.

3. Sul lato destro dello schermo viene visualizzato un riquadro a comparsa per la selezione del modello, che mostra un elenco di tutti i modelli e il relativo stato attivo o inattivo. Il **contatore dei** modelli attivati mostra quanti modelli sono attualmente in uso al di fuori del numero totale disponibile per l'utilizzo. Se si è oltre il limite, verrà visualizzato un avviso sulla barra dei messaggi.

4. Sul lato destro dello schermo viene visualizzato un riquadro a comparsa di selezione del modello. Usare **la** ricerca per applicare filtri per l'individuazione del modello desiderato

5. Dopo aver individuato il modello, seleziona il pulsante di opzione a sinistra del nome, quindi seleziona **Salva**.

6. Nella schermata successiva viene visualizzato il modello selezionato. Se corretto, selezionare **Avanti**. Se non è corretto, scegliere **Seleziona un modello diverso da** scegliere di nuovo.

7. Nella schermata **Upload file** selezionare  Sfoglia per trovare e caricare il file Excel contenente tutti i dati del modello necessari.

8. Se non si verificano problemi con il file, nella schermata successiva viene visualizzato il nome del file caricato. Selezionare **Avanti** per continuare (se è necessario modificare il file, selezionare Upload **un file diverso).**

    - Se si verifica un problema con il file, nella parte superiore viene visualizzato un messaggio di errore che spiega il problema. Dovrai correggere e ricaricare il file. Gli errori si verificano se il foglio di calcolo è formattato in modo non corretto o se sono presenti informazioni non valide in alcuni campi.

9. La **schermata Revisione e** fine mostra il numero di azioni e controlli di miglioramento e il punteggio massimo per il modello. Quando si è pronti per l'approvazione, selezionare **Avanti**. Se è necessario apportare modifiche, **selezionare Upload un file diverso.**

10. L'ultima schermata conferma la creazione di un nuovo modello. Selezionare **Fine** per uscire dalla procedura guidata.

11. Arriverai alla pagina dei dettagli del nuovo modello. Da qui è possibile creare la valutazione selezionando **Crea valutazione**. Per istruzioni, vedere [Creare e gestire valutazioni.](compliance-manager-assessments.md#create-assessments)

## <a name="modify-a-template"></a>Modificare un modello

Potresti voler modificare un modello già creato, ad esempio aggiungere controlli o aggiungere o rimuovere azioni di miglioramento. Il processo è simile al processo di creazione del modello, in cui carichi il file Excel file formattato con i dati del modello.

Tuttavia, esistono dettagli da tenere presenti durante la formattazione del file con le modifiche ai dati del modello esistenti. **È consigliabile leggere attentamente queste istruzioni per assicurarsi di non sovrascrivere i dati esistenti che si desidera conservare.**

### <a name="format-your-excel-file-to-modify-an-existing-template"></a>Formattare il Excel file per modificare un modello esistente

Nella pagina **dei modelli di** valutazione seleziona il modello che vuoi   modificare, che ne visualizza la pagina dei dettagli. Selezionare quindi **Esporta in Excel**. Verrà scaricato Excel file con tutti i dati del modello. Salvare il file nel computer locale.

Per usare questo file, passare a una sezione seguente per trovare rapidamente le istruzioni necessarie:

- [Modificare gli attributi principali del modello](#edit-the-main-template-attributes)
- [Aggiungere un'azione di miglioramento](#add-an-improvement-action)
- [Modificare le informazioni di un'azione di miglioramento](#edit-an-improvement-actions-information)
- [Modificare il nome di un'azione di miglioramento](#change-an-improvement-actions-name)
- [Rimuovere un'azione di miglioramento](#remove-an-improvement-action)
- [Rimuovere un controllo](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>Modificare gli attributi principali del modello

Nella scheda **Modelli** è possibile modificare qualsiasi elemento nella colonna **del** titolo, **nella colonna inScopeServices** e in qualsiasi altra colonna aggiunta. Tuttavia, non è possibile modificare nulla nelle colonne **del prodotto** **o della** certificazione.

#### <a name="add-an-improvement-action"></a>Aggiungere un'azione di miglioramento

1. Passare alla **scheda** Azioni. Aggiungere le informazioni nei campi obbligatori nella prima riga vuota sotto le azioni esistenti.
2. Vai alla **scheda ControlFamily.** Individuare la riga contenente il controllo a cui è mappata l'azione di miglioramento. Aggiungi la nuova azione alla colonna **controlActionTitle** di tale riga (ricordati di separare più azioni in questo campo con due punti e virgola, senza spazio tra di loro).
3. Salvare il foglio di calcolo.

#### <a name="edit-an-improvement-actions-information"></a>Modificare le informazioni di un'azione di miglioramento

È possibile modificare le informazioni di qualsiasi azione di miglioramento *ad eccezione del titolo*. È possibile modificare qualsiasi cella dalle colonne B in poi e quando si importa di nuovo il file nel modello, le azioni di miglioramento in tale modello conterranno i dati aggiornati.

Non è possibile modificare **l'azioneTitle** (colonna A) perché in tal caso, Compliance Manager considera questa azione come una nuova azione di miglioramento. Se si desidera modificare il nome di un'azione di miglioramento, vedere le istruzioni immediatamente seguenti.

#### <a name="change-an-improvement-actions-name"></a>Modificare il nome di un'azione di miglioramento

Se si desidera modificare il nome di un'azione di miglioramento, è necessario indicare esplicitamente nel foglio di calcolo che si sta sostituendo un nome esistente con un nuovo nome. attenersi alla seguente procedura:

1. Nella scheda **Azioni** del foglio di calcolo aggiungere una nuova colonna al foglio di calcolo dopo la colonna A.
2. In questa nuova colonna, che ora è la colonna B, inserire come intestazione nella riga 1: **oldActionTitle**.
3. Copiare il contenuto della colonna A e incollarlo nella colonna B. In questo modo i titoli delle azioni di miglioramento esistenti, che sono ciò che si desidera modificare, vengono visualizzati nella colonna B.
4. Nella colonna A, **actionTitle,** eliminare il vecchio nome e sostituirlo con il nuovo nome per l'azione di miglioramento.

Si noti che i titoli delle azioni, sia per le azioni di miglioramento che per le azioni microsoft, devono essere scritti in inglese per essere riconosciuti quando si fa riferimento nei controlli.

#### <a name="remove-an-improvement-action"></a>Rimuovere un'azione di miglioramento

Per rimuovere un'azione di miglioramento da un modello, è necessario rimuoverla da ogni controllo che vi fa riferimento. Seguire la procedura seguente per modificare il foglio di calcolo:

1. Nella scheda **ControlFamily** cercare il titolo dell'azione di miglioramento che si desidera rimuovere.
2. Eliminare il titolo dell'azione di miglioramento nelle celle in cui viene visualizzata. Se l'azione di miglioramento è l'unica azione eseguita su tale riga, eliminare l'intera riga, rimuovendo così il controllo.
3. Nella scheda **Azioni** eliminare la riga contenente l'azione di miglioramento che si sta eliminando.
4. Salvare il foglio di calcolo.

Quando si importa di nuovo il foglio di calcolo nel modello, l'azione di miglioramento verrà rimossa dal modello.

La rimozione di un'azione di miglioramento da un modello non rimuove completamente l'azione di miglioramento da Compliance Manager. È comunque possibile fare riferimento a tale azione da un altro modello.

#### <a name="remove-a-control"></a>Rimuovere un controllo

Per rimuovere un controllo, modificare il foglio di calcolo seguendo la procedura seguente, quindi importare di nuovo il foglio di calcolo:

1. Nella scheda **ControlFamily** individuare il controllo che si desidera rimuovere nella **colonna controlName.**
2. Eliminare la riga per il controllo.
    - Se questo controllo eliminato contiene azioni di miglioramento a cui nessun altro controllo fa riferimento, sarà necessario rimuovere tali azioni di miglioramento dalla **scheda** Azioni. In caso contrario, verrà visualizzato un errore di convalida.

3. Salvare il foglio di calcolo.

Quando si importa di nuovo il foglio di calcolo nel modello, il controllo verrà rimosso dal modello.

### <a name="modify-template-info-in-compliance-manager"></a>Modificare le informazioni sul modello in Compliance Manager

Dopo aver Excel il file di configurazione e salvato, eseguire la procedura seguente.

1. Apri di nuovo la pagina del modello di valutazione e seleziona il modello. Nella pagina dei dettagli del modello seleziona **Modifica modello** per avviare la procedura guidata di modifica.
2. Nella schermata **Upload file** seleziona **Sfoglia** per trovare e caricare il file Excel file.
3. Se non si verificano problemi con il file, nella schermata successiva viene visualizzato il nome del file caricato. Selezionare **Avanti** per continuare (se è necessario modificare il file, selezionare Upload **un file diverso).**
    - Se si verifica un problema con il file, nella parte superiore viene visualizzato un messaggio di errore che spiega il problema. Dovrai correggere il file e caricarlo di nuovo. Gli errori si verificano se il foglio di calcolo è formattato in modo non corretto o se sono presenti informazioni non valide in alcuni campi.

4. La **schermata Revisione e** fine mostra il numero di azioni e controlli di miglioramento e il punteggio massimo per il modello. Quando si è pronti per l'approvazione, selezionare **Avanti**.
5. L'ultima schermata conferma che il modello è stato modificato. Selezionare **Fine** per uscire dalla procedura guidata.

Il modello includerà le modifiche apportate. Tutte le valutazioni che utilizzano questo modello modificato ora mostreranno gli aggiornamenti in sospeso e dovrai accettare gli aggiornamenti per le valutazioni per riflettere le modifiche apportate nel modello. Ulteriori informazioni sugli [aggiornamenti per le valutazioni](compliance-manager-assessments.md#accept-updates-to-assessments).

> [!NOTE]
> Se si utilizza Compliance Manager in una lingua diversa dall'inglese, si noterà che parte del testo viene visualizzato in inglese quando si esporta un modello in Excel. I titoli delle azioni (sia le azioni di miglioramento che le azioni microsoft) devono essere in inglese per essere riconosciuti dai controlli. Se si apportano modifiche al titolo di un'azione, assicurarsi di scriverlo in inglese in modo che il file venga importato correttamente.

## <a name="export-a-template"></a>Esportare un modello

È possibile esportare Excel file contenente tutti i dati di un modello. Dovrai esportare un modello per modificarlo, poiché questo sarà il file Excel che modificherai e carichi nel processo [di modifica.](#modify-a-template)

Per esportare il modello, passare alla pagina dei dettagli del modello e selezionare il pulsante **Esporta in Excel.**

Si noti che quando si esporta un modello esteso da un modello di Compliance Manager, il file esportato conterrà solo gli attributi aggiunti al modello. Il file esportato non includerà i dati del modello originale forniti da Microsoft. Per ottenere un report di questo tipo, vedere le istruzioni per [l'esportazione di un report di valutazione.](compliance-manager-assessments.md#export-an-assessment-report)
