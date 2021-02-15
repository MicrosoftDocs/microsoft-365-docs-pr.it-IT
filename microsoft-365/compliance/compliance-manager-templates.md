---
title: Uso dei modelli di valutazione in Microsoft Compliance Manager
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
description: Informazioni su come usare e gestire i modelli per la creazione di valutazioni in Microsoft Compliance Manager. Creare e modificare modelli utilizzando un file di Excel formattato.
ms.openlocfilehash: 34adb79392b235152cc0e00f5b7d661e90c9005e
ms.sourcegitcommit: 00d231bf0100e843a5a93161695e87ceff9e1349
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49849610"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Uso dei modelli di valutazione in Compliance Manager

**In questo articolo:** Comprendere **il funzionamento dei modelli** e come **gestirli dalla** pagina dei modelli di valutazione. Istruzioni per la **creazione di** nuovi modelli, **la modifica** dei modelli esistenti, la **formattazione dei** dati del modello con Excel e l'esportazione dei report **dei modelli.**

> [!IMPORTANT]
> I modelli di valutazione disponibili per l'organizzazione dipendono dal contratto di licenza. [Esaminare i dettagli.](https://go.microsoft.com/fwlink/?linkid=2132371)

## <a name="templates-overview"></a>Panoramica dei modelli

Un modello è un framework per la creazione di una valutazione in Compliance Manager. Contengono i controlli per soddisfare i requisiti di una certificazione che utilizza un determinato prodotto. Compliance Manager fornisce un set completo di modelli che consentono all'organizzazione di rispettare i requisiti nazionali, regionali e specifici del settore che regolano la raccolta e l'uso dei dati.

## <a name="list-of-pre-built-templates-for-assessments"></a>Elenco di modelli predefiniti per le valutazioni

Compliance Manager fornisce modelli per la creazione di valutazioni che consentono di soddisfare diverse normative e standard. Visualizzare [l'elenco dei modelli](compliance-manager-templates-list.md) forniti da Compliance Manager. I nuovi modelli vengono aggiunti regolarmente, quindi controlla spesso l'elenco.

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>Visualizzazione e gestione dei modelli dalla pagina dei modelli di valutazione

La pagina dei modelli di valutazione in Compliance Manager visualizza un elenco di modelli e dettagli chiave. L'elenco include i modelli forniti da Compliance Manager e tutti i modelli modificati o creati dall'organizzazione. È possibile applicare filtri per trovare un modello basato su certificazione, ambito di prodotto, paese, settore, chi lo ha creato e se il modello è abilitato per la creazione della valutazione.

Selezionare un modello dalla riga corrispondente per visualizzare la relativa pagina dei dettagli. Questa pagina contiene una descrizione del modello e ulteriori informazioni sulla certificazione, l'ambito e i dettagli dei controlli. Da questa pagina è possibile selezionare i pulsanti appropriati per creare una valutazione, esportare i dati del modello in Excel o modificare il modello.

## <a name="creating-and-modifying-templates-overview"></a>Panoramica della creazione e della modifica dei modelli

Per modificare un modello esistente o per creare un nuovo modello personalizzato, si utilizzerà un foglio di calcolo di Excel formattato in modo specifico ([scaricare](https://go.microsoft.com/fwlink/?linkid=2124865)un esempio ) per assemblare i dati del controllo necessari. Dopo aver completato il foglio di calcolo, importarlo in Compliance Manager durante il processo di creazione o modifica di un modello.

> [!NOTE]
> Il foglio di calcolo ha un formato e uno schema specifici che devono essere utilizzati oppure non verrà importato correttamente in Compliance Manager. Le [istruzioni di formattazione](#formatting-your-template-data-with-excel) sono riportate di seguito.

**Ruoli obbligatori**

Solo gli utenti che hanno un ruolo di amministratore globale o di amministrazione di Compliance Manager possono creare e modificare i modelli. Ulteriori informazioni su [ruoli e autorizzazioni.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

## <a name="create-a-new-template"></a>Creare un nuovo modello

Per creare un nuovo modello personalizzato (usato per la creazione di valutazioni personalizzate), segui i passaggi seguenti.

1. Passare alla pagina **dei modelli di** valutazione in Compliance Manager.
2. Selezionare **Crea nuovo modello.** Verrà aperta una procedura guidata per la creazione di modelli.
3. Scegliere il tipo di modello che si desidera creare. In questo caso, selezionare **Crea un modello personalizzato,** quindi selezionare **Avanti.**
4. At the **Upload file** screen, select **Browse** to find and upload your formatted Excel file containing all the required template data (see instructions for properly formatting [your file](#formatting-your-template-data-with-excel)).
5. Se non si verificano problemi con il file, verrà visualizzato il nome del file caricato. Selezionare **Avanti** per continuare. Se è necessario modificare il file, selezionare **Carica un file diverso.**
    - Se si verifica un errore con il file, nella parte superiore viene visualizzato un messaggio di errore che spiega il problema. Dovrai correggere il file e caricarlo di nuovo. Gli errori si verificano se il foglio di calcolo non è formattato correttamente o se sono presenti informazioni non valide in determinati campi (fare di nuovo riferimento alle [istruzioni di formattazione).](#formatting-your-template-data-with-excel)  
    
6. La **schermata Revisione e** fine mostra il numero di azioni e controlli di miglioramento e il punteggio massimo per il modello. Quando si è pronti per l'approvazione, **selezionare Crea modello.** Se è necessario apportare modifiche, selezionare **Indietro.**
7. L'ultima schermata conferma la creazione di un nuovo modello. Selezionare **Fine per** uscire dalla procedura guidata.
8. Verrà visualizzata la pagina dei dettagli del nuovo modello, in cui è possibile [creare la valutazione.](compliance-manager-assessments.md#create-your-own-custom-assessment)

## <a name="formatting-your-template-data-with-excel"></a>Formattazione dei dati del modello con Excel

Il foglio di calcolo di Excel utilizzato per creare i modelli contiene quattro schede, tre delle quali sono necessarie:

1. [Modello](#template-tab) (obbligatorio)
2. [ControlFamily](#controlfamily-tab) (obbligatorio)
3. [Azioni](#actions-tab) (obbligatorio)
4. [Dimensioni](#dimensions-tab) (facoltativo)

Quando si compila il foglio di calcolo con i dati del modello, il foglio di calcolo deve includere le schede nell'ordine indicato in precedenza,  **altrimenti** i dati non verranno importati correttamente in un modello.

##### <a name="template-tab"></a>Scheda Modello

La **scheda Modello** è obbligatoria. Le informazioni contenute in questa scheda forniscono i metadati relativi al modello. Sono disponibili quattro colonne obbligatorie. Le colonne devono mantenere l'ordine nel foglio di Excel come indicato di seguito. È possibile aggiungere una propria **colonna dopo** le quattro colonne per fornire dimensioni personalizzate. In questo caso, assicurarsi di aggiungerli alla **scheda** Dimensioni usando le [istruzioni riportate di seguito.](#dimensions-tab)

- **title**: questo è il titolo del modello, che deve essere univoco. Non può condividere un nome con un altro modello presente in Compliance Manager, inclusi i propri modelli o un modello di Compliance Manager.

- **product**: dimensione obbligatoria. Elencare il prodotto associato al modello.

- **certification:** questa è la normativa che stai usando per il modello.

- **inScopeServices:** questi sono i servizi all'interno del prodotto a cui si rivolge questa valutazione (ad esempio, se office 365 è stato elencato come prodotto, Microsoft Teams potrebbe essere un servizio nell'ambito). È possibile elencare più servizi separati da due punti e virgola.

> [!NOTE]
> I dati inseriti nelle  celle **del** prodotto e della certificazione non possono essere modificati dopo l'importazione del foglio di calcolo per creare o personalizzare un modello. Inoltre, un gruppo non può contenere due valutazioni con la stessa combinazione **di prodotto/certificazione.** Puoi avere più modelli con la stessa combinazione di prodotto/certificazione.

##### <a name="controlfamily-tab"></a>Scheda ControlFamily

La **scheda ControlFamily** è obbligatoria.  Le colonne obbligatorie in questa scheda, che devono seguire l'ordine indicato nel foglio di calcolo di esempio, sono:

- **controlName**: questo è il nome del controllo della certificazione, dello standard o della normativa, che in genere è un tipo di ID. I nomi dei controlli devono essere univoci all'interno di un modello. Non è possibile avere più controlli con lo stesso nome nel foglio di calcolo.

- **controlFamily:** specifica una parola o una frase per controlFamily, che identifica un ampio raggruppamento di controlli. Un controlFamily non deve essere univoco; può essere elencato più di una volta in un foglio di calcolo. Lo stesso controlFamily può anche essere elencato in più modelli, anche se non hanno alcuna relazione tra loro. Ogni controlFamily deve essere mappato ad almeno un controllo.

- **controlTitle**: specifica un titolo per il controllo. Mentre controlName è un codice di riferimento, il titolo è un formato RTF in genere presente nelle normative.

- **controlDescription:** fornire una descrizione del controllo.

- **controlActionTitle:** titolo di un'azione che si desidera correlare a questo controllo. È possibile aggiungere più azioni separando due punti e virgola senza spazi. Ogni controllo elencato deve includere almeno un'azione e l'azione deve esistere( ciò  significa che è possibile elencare un'azione elencata nella scheda Azioni dello stesso foglio di calcolo, un'azione presente in un modello diverso o un'azione creata da Microsoft). Controlli diversi possono fare riferimento alla stessa azione.

##### <a name="actions-tab"></a>Scheda Azioni

La **scheda Azioni** è obbligatoria.  Designa le azioni di miglioramento gestite dall'organizzazione e non quelle di Microsoft, già esistenti in Compliance Manager. Le colonne necessarie per questa scheda, che devono seguire l'ordine indicato nel foglio di calcolo di esempio, sono:

- **actionTitle:** questo è il titolo dell'azione ed è un campo obbligatorio. Il titolo fornito deve essere univoco. **Importante:** se si fa riferimento a un'azione già esistente (ad esempio in un altro modello) e si modifica uno dei relativi elementi nelle colonne successive, tali modifiche verranno propagate alla stessa azione in altri modelli.

- **implementationType:** in questo campo obbligatorio elenca uno dei tre tipi di implementazione seguenti:
    - **Operativo:** azioni implementate da persone e processi per proteggere la riservatezza, l'integrità e la disponibilità di sistemi, risorse, dati e personale dell'organizzazione (ad esempio: sensibilizzazione e formazione sulla sicurezza)
    - **Tecniche:** azioni completate tramite l'uso di tecnologie e meccanismi contenuti nei componenti hardware, software o firmware del sistema in informazioni per proteggere la riservatezza, l'integrità e la disponibilità dei sistemi e dei dati dell'organizzazione (ad esempio: autenticazione a più fattori)
    - **Documentazione** : azioni implementate tramite criteri e procedure documentati che definiscono e definiscono i controlli necessari per proteggere la riservatezza, l'integrità e la disponibilità di sistemi, risorse, dati e personale dell'organizzazione (ad esempio: criteri di sicurezza delle informazioni)

- **actionScore:** in questo campo obbligatorio, fornisci un valore di punteggio numerico per l'azione. Deve essere un numero intero compreso tra 1 e 99. non può essere 0, null o vuoto. Più alto è il numero, maggiore è il valore verso il miglioramento della postura di conformità. L'immagine seguente mostra il modo in cui Compliance Manager ottiene i controlli:

![Compliance Manager controlla i valori dei punti](../media/compliance-score-action-scoring.png "Compliance Manager controlla i valori dei punti")

- **actionDescriptionTitle**: questo è il titolo della descrizione ed è obbligatorio. Questo titolo della descrizione ti consente di eseguire la stessa azione in più modelli e di visualizzare una descrizione diversa in ogni modello.  Questo campo consente di chiarire il modello a cui fa riferimento la descrizione. Nella maggior parte dei casi, è possibile inserire il nome del modello che si sta creando in questo campo.

- **actionDescription:** fornire una descrizione dell'azione. È possibile applicare la formattazione, ad esempio testo in grassetto e collegamenti ipertestuali. Questo campo è obbligatorio.

- **dimension-Action Purpose**: questo è un campo facoltativo. Se viene incluso, l'intestazione deve includere il prefisso "dimension-". Tutte le dimensioni incluse qui verranno utilizzate come filtri in Compliance Manager e verranno visualizzate nella pagina dei dettagli delle azioni di miglioramento in Compliance Manager.

##### <a name="dimensions-tab"></a>Scheda Dimensioni

La **scheda Dimensioni** è facoltativa. Tuttavia, se si fa riferimento a una dimensione altrove, è necessario specificarla qui se non esiste in un modello già creato o in un modello Microsoft. Le colonne per questa scheda sono elencate di seguito:

- **dimensionKey**: list as "product", "certifications", "action purpose"
- **dimensionValue**: esempi: Office 365, HIPPA, Preventivo, Detective

Per visualizzare le dimensioni esistenti, accedere a **Gestione tenant** e selezionare la **scheda** Dimensioni. Inoltre, ogni volta che si esporta un modello  esistente, il foglio di calcolo esportato avrà la scheda Dimensioni, in cui sono elencate tutte le dimensioni utilizzate nel modello.

## <a name="modify-a-template"></a>Modificare un modello

È possibile modificare un modello già creato, ad esempio aggiungere controlli o aggiungere o rimuovere azioni di miglioramento. Il processo è simile al processo di creazione del modello in cui verrà caricato un file di Excel formattato con i dati del modello.

Tuttavia, esistono particolari dettagli da tenere presenti durante la formattazione del file con le modifiche ai dati del modello esistente. **È consigliabile leggere attentamente queste istruzioni per assicurarsi di non sovrascrivere i dati esistenti che si desidera conservare.**

### <a name="template-modification-process-steps"></a>Passaggi del processo di modifica del modello

Per modificare un modello, eseguire la procedura seguente:

1. Nella pagina **dei modelli di** valutazione selezionare il modello che si desidera modificare, visualizzando la relativa pagina dei dettagli.
2. Selezionare **Esporta in Excel.** Verrà scaricato un file di Excel con tutti i dati del modello. Salvare il file nel computer locale.
3. Apportare le modifiche al modello [modificando il file di Excel utilizzando le istruzioni riportate di seguito.](#formatting-your-excel-file-to-modify-a-template)
4. Dopo aver apportato modifiche al file di Excel, salvare il file.
5. Nella pagina dei dettagli del modello selezionare **Modifica** modello per avviare la procedura guidata di modifica. 
6. Nella schermata **Carica file** selezionare **Sfoglia per** trovare e caricare il file di Excel.
7. Se non si verificano problemi con il file, nella schermata successiva viene visualizzato il nome del file caricato. Selezionare **Avanti** per continuare (se è necessario modificare il file, selezionare **Carica un altro file).**
    - Se si verifica un problema con il file, nella parte superiore viene visualizzato un messaggio di errore che spiega il problema. Dovrai correggere il file e caricarlo di nuovo. Se il foglio di calcolo non è formattato correttamente o se sono presenti informazioni non valide in alcuni campi, si verificano errori.

8. La **schermata Revisione e** fine mostra il numero di azioni e controlli di miglioramento e il punteggio massimo per il modello. Quando si è pronti per l'approvazione, selezionare **Avanti.**
9. L'ultima schermata conferma che il modello è stato modificato. Selezionare **Fine per** uscire dalla procedura guidata.

Il modello includerà ora le modifiche apportate. Tutte le valutazioni che usano questo modello modificato mostreranno gli aggiornamenti in sospeso ed è necessario accettare gli aggiornamenti per le valutazioni per riflettere le modifiche apportate nel modello. Ulteriori informazioni sugli [aggiornamenti alle valutazioni.](compliance-manager-assessments.md#accepting-updates-to-assessments)

> [!NOTE]
> Se si usa Compliance Manager in una lingua diversa dall'inglese, si noterà che parte del testo viene visualizzato in inglese quando si esporta un modello in Excel. I titoli delle azioni (sia le azioni di miglioramento che le azioni di Microsoft) devono essere in inglese per essere riconosciuti dai controlli. Se si apportano modifiche al titolo di un'azione, assicurarsi di scriverlo in inglese in modo che il file venga importato correttamente.

### <a name="formatting-your-excel-file-to-modify-a-template"></a>Formattazione del file di Excel per modificare un modello

Passare a una sezione seguente per trovare rapidamente le istruzioni necessarie:

- [Modificare gli attributi del modello principale](#edit-the-main-template-attributes)
- [Aggiungere un'azione di miglioramento](#add-an-improvement-action)
- [Modificare le informazioni di un'azione di miglioramento](#edit-an-improvement-actions-information)
- [Modificare il nome di un'azione di miglioramento](#change-an-improvement-actions-name)
- [Rimuovere un'azione di miglioramento](#remove-an-improvement-action)
- [Rimuovere un controllo](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>Modificare gli attributi del modello principale

Nella scheda **Modelli** è possibile modificare  qualsiasi elemento nella colonna del titolo, **nella colonna inScopeServices** e in qualsiasi altra colonna aggiunta. Tuttavia, non è possibile modificare nulla nelle colonne **del** prodotto **o della** certificazione.

#### <a name="add-an-improvement-action"></a>Aggiungere un'azione di miglioramento

1. Passare alla **scheda** Azioni. Aggiungere le informazioni nei campi obbligatori nella prima riga vuota sotto le azioni esistenti.
2. Vai alla scheda **ControlFamily.** Individuare la riga contenente il controllo a cui è mappata l'azione di miglioramento. Aggiungere la nuova azione alla colonna **controlActionTitle** in tale riga (ricordare di separare più azioni in questo campo con due punti e virgola, senza spazio tra di loro).
3. Salvare il foglio di calcolo.

#### <a name="edit-an-improvement-actions-information"></a>Modificare le informazioni di un'azione di miglioramento

È possibile modificare le informazioni di qualsiasi azione di *miglioramento, ad eccezione del titolo.* È possibile modificare qualsiasi cella dalle colonne B e versioni successive e, quando si importa di nuovo il file nel modello, le azioni di miglioramento in tale modello conterranno i dati aggiornati.

Non è possibile modificare **l'azioneTitle** (colonna A) perché, in tal caso, Compliance Manager considera questa azione come una nuova azione di miglioramento. Se si desidera modificare il nome di un'azione di miglioramento, vedere le istruzioni immediatamente seguenti.

#### <a name="change-an-improvement-actions-name"></a>Modificare il nome di un'azione di miglioramento

Se si desidera modificare il nome di un'azione di miglioramento, è necessario designare esplicitamente nel foglio di calcolo la sostituzione di un nome esistente con un nuovo nome. attenersi alla seguente procedura:

1. Nella scheda **Azioni del** foglio di calcolo aggiungere una nuova colonna al foglio di calcolo dopo la colonna A.
2. In questa nuova colonna, che ora è la colonna B, inserire come intestazione nella riga 1: **oldActionTitle.**
3. Copiare il contenuto della colonna A e incollarlo nella colonna B. In questo modo i titoli delle azioni di miglioramento esistenti, che sono gli elementi che si desidera modificare, vengono visualizzati nella colonna B.
4. Nella colonna A, **actionTitle,** eliminare il nome precedente e sostituirlo con il nuovo nome per l'azione di miglioramento.

Si noti che i titoli delle azioni, sia per le azioni di miglioramento che per le azioni di Microsoft, devono essere scritti in inglese per essere riconosciuti quando si fa riferimento nei controlli.

#### <a name="remove-an-improvement-action"></a>Rimuovere un'azione di miglioramento

Per rimuovere un'azione di miglioramento da un modello, è necessario rimuoverla da ogni controllo che vi fa riferimento. Seguire i passaggi seguenti per modificare il foglio di calcolo:

1. Nella scheda **ControlFamily** cercare il titolo dell'azione di miglioramento che si desidera rimuovere.
2. Eliminare il titolo dell'azione di miglioramento nelle celle in cui viene visualizzata. Se l'azione di miglioramento è l'unica azione eseguita su tale riga, eliminare l'intera riga, rimuovendo così il controllo.
3. Nella scheda **Azioni** eliminare la riga contenente l'azione di miglioramento da eliminare.
4. Salvare il foglio di calcolo.

Quando si importa di nuovo il foglio di calcolo nel modello, l'azione di miglioramento verrà rimossa dal modello.

La rimozione di un'azione di miglioramento da un modello non rimuove completamente l'azione di miglioramento da Compliance Manager. Tale azione può comunque essere referenziato da un altro modello.

#### <a name="remove-a-control"></a>Rimuovere un controllo

Per rimuovere un controllo, modificare il foglio di calcolo seguendo la procedura seguente, quindi importare di nuovo il foglio di calcolo:

1. Nella scheda **ControlFamily** individuare il controllo che si desidera rimuovere nella **colonna controlName.**
2. Eliminare la riga per il controllo.
    - Se il controllo eliminato contiene azioni di miglioramento a cui non fanno riferimento altri controlli, sarà necessario rimuovere tali azioni di miglioramento dalla **scheda** Azioni. In caso contrario, verrà visualizzato un errore di convalida.

3. Salvare il foglio di calcolo.

Quando si importa di nuovo il foglio di calcolo nel modello, il controllo verrà rimosso dal modello.

## <a name="export-a-template"></a>Esportare un modello

È possibile esportare un file di Excel contenente tutti i dati di un modello. Sarà necessario esportare un modello per modificare il modello, poiché questo sarà il file di Excel modificato e caricato nel processo [di modifica.](#modify-a-template)

Per esportare il modello, passare alla pagina dei dettagli del modello e selezionare il **pulsante Esporta in Excel.**

Si noti che quando si esporta un modello esteso da un modello di Compliance Manager, il file esportato conterrà solo gli attributi aggiunti al modello. Il file esportato non includerà i dati del modello originale forniti da Microsoft. Per ottenere un report di questo tipo, vedere le istruzioni per [l'esportazione di un report di valutazione.](compliance-manager-assessments.md#export-an-assessment-report)