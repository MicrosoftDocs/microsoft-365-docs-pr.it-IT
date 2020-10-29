---
title: Utilizzo dei modelli di valutazione in Microsoft Compliance Manager
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
description: Informazioni su come utilizzare e gestire i modelli per la creazione di valutazioni in Microsoft Compliance Manager. Creare e modificare modelli utilizzando un file di Excel formattato.
ms.openlocfilehash: cc3092e486e4f25fa1edad1ff64e638410cf3a63
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791808"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Utilizzo dei modelli di valutazione in Compliance Manager

**In questo articolo:** Informazioni su **come funzionano i modelli** e **su come gestirli** dalla pagina modelli di valutazione. Ottenere le istruzioni per la **creazione** di nuovi modelli, la **modifica** di modelli esistenti, **la formattazione dei dati del modello con Excel e l'** esportazione di **report sui** modelli.

> [!IMPORTANT]
> I modelli di valutazione disponibili per l'organizzazione variano a seconda del contratto di licenza. [Esaminare i dettagli](https://go.microsoft.com/fwlink/?linkid=2132371).

## <a name="templates-overview"></a>Panoramica sui modelli

Un modello è un Framework per la creazione di una valutazione in Compliance Manager. Contengono i controlli per soddisfare i requisiti di una certificazione che utilizza un determinato prodotto. Compliance Manager fornisce una serie completa di modelli per aiutare l'organizzazione a rispettare i requisiti nazionali, regionali e specifici per l'industria che disciplinano la raccolta e l'utilizzo dei dati.

## <a name="list-of-pre-built-templates-for-assessments"></a>Elenco dei modelli predefiniti per le valutazioni

Compliance Manager fornisce modelli per la creazione di valutazioni che consentono di soddisfare diverse normative e standard. Consente di visualizzare l' [elenco dei modelli](compliance-manager-templates-list.md) forniti da Compliance Manager. I nuovi modelli vengono aggiunti regolarmente, quindi controllare l'elenco spesso.

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>Visualizzazione e gestione dei modelli dalla pagina modelli di valutazione

Nella pagina modelli di valutazione in Compliance Manager viene visualizzato un elenco di modelli e dettagli principali. L'elenco include modelli forniti da Compliance Manager così come tutti i modelli che l'organizzazione ha modificato o creato. È possibile applicare filtri per trovare un modello basato su certificazione, ambito di prodotto, paese, industria, che l'ha creato e se il modello è abilitato per la creazione di una valutazione.

Selezionare un modello dalla relativa riga per visualizzare la pagina dei dettagli. Questa pagina contiene una descrizione del modello e ulteriori informazioni sui dettagli sulla certificazione, sull'ambito e sui controlli. Da questa pagina è possibile selezionare i pulsanti adatti per creare una valutazione, esportare i dati del modello in Excel o modificare il modello.

## <a name="creating-and-modifying-templates-overview"></a>Panoramica della creazione e della modifica di modelli

Per modificare un modello esistente o per creare un nuovo modello, è possibile utilizzare un foglio di calcolo di Excel appositamente formattato ([scaricare un esempio](https://go.microsoft.com/fwlink/?linkid=2124865)) per assemblare i dati di controllo necessari. Dopo aver completato il foglio di calcolo, è necessario importarlo in Compliance Manager durante il processo di creazione o modifica di un modello.

> [!NOTE]
> Il foglio di calcolo ha un formato specifico e uno schema che deve essere utilizzato oppure non verrà importato correttamente in Compliance Manager. Le [istruzioni di formattazione](#formatting-your-template-data-with-excel) sono riportate di seguito.

**Ruoli necessari**

Solo gli utenti che dispongono di un ruolo amministratore globale o di amministrazione Compliance Manager possono creare e modificare modelli. Per ulteriori informazioni [, vedere ruoli e autorizzazioni](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

## <a name="create-a-new-template"></a>Creare un nuovo modello

Per creare un nuovo modello personalizzato (utilizzato per la creazione di valutazioni personalizzate), attenersi alla procedura riportata di seguito.

1. Andare alla pagina dei **modelli di valutazione** in Compliance Manager.
2. Selezionare **Crea nuovo modello** . Verrà aperta una creazione guidata modello.
3. Scegliere il tipo di modello che si desidera creare. In questo caso, selezionare **Crea un modello personalizzato** , quindi fare clic su **Avanti** .
4. Nella schermata **Carica file** selezionare **Sfoglia** per individuare e caricare il file di Excel formattato contenente tutti i dati dei modelli necessari (vedere [le istruzioni per la formattazione corretta del file](#formatting-your-template-data-with-excel)).
5. Se non si verificano problemi con il file, verrà visualizzato il nome del file caricato. Fare clic su **Avanti** per continuare. Se è necessario modificare il file, selezionare **carica un file diverso** .
    - Se si verifica un errore nel file, un messaggio di errore nella parte superiore spiega cosa c'è di sbagliato. È necessario correggere il file e caricarlo di nuovo. Se il foglio di calcolo è formattato in modo errato o se sono presenti informazioni non valide in alcuni campi, verranno restituiti errori (fare nuovamente riferimento alle [istruzioni di formattazione](#formatting-your-template-data-with-excel)).  
    
6. La schermata **revisione e fine** Visualizza il numero di azioni e controlli di miglioramento e il punteggio massimo per il modello. Quando si è pronti per l'approvazione, selezionare **Crea modello.** Se è necessario apportare modifiche, selezionare **indietro** .
7. L'ultima schermata conferma che è stato creato un nuovo modello. Fare clic su **fine** per uscire dalla procedura guidata.
8. Si arriva alla pagina dei dettagli del nuovo modello, in cui è possibile [creare la propria valutazione](compliance-manager-assessments.md#create-your-own-custom-assessment).

## <a name="formatting-your-template-data-with-excel"></a>Formattazione dei dati del modello con Excel

Il foglio di calcolo di Excel utilizzato per creare modelli contiene quattro schede, tre delle quali sono necessarie:

1. [Modello](#template-tab) (obbligatorio)
2. [ControlFamily](#controlfamily-tab) (obbligatorio)
3. [Azioni](#actions-tab) (obbligatorio)
4. [Dimensioni](#dimensions-tab) (facoltativa)

Quando si compila il foglio di calcolo con i dati dei modelli, il foglio di calcolo  **deve includere le schede nell'ordine indicato** , altrimenti i dati non verranno importati correttamente in un modello.

##### <a name="template-tab"></a>Scheda modello

La scheda **modello** è obbligatoria. Le informazioni contenute in questa scheda forniscono i metadati relativi al modello. Sono disponibili quattro colonne obbligatorie. Le colonne devono mantenere l'ordine nel foglio di Excel come elencato di seguito. È possibile aggiungere una colonna personalizzata **dopo** le quattro colonne per fornire le proprie dimensioni. Se si esegue questa operazione, accertarsi di aggiungerli alla scheda **dimensioni** seguendo le istruzioni riportate di [seguito](#dimensions-tab).

- **title** : questo è il titolo del modello, che deve essere univoco. Non è in grado di condividere un nome con un altro modello incluso in Compliance Manager, inclusi i propri modelli o un modello di Compliance Manager.

- **Product** : questa è una dimensione obbligatoria. Elencare il prodotto associato al modello.

- **Certification** : questo è il regolamento che si sta utilizzando per il modello.

- **inScopeServices** : questi sono i servizi all'interno del prodotto che questa valutazione affronta (ad esempio, se è stato elencato Office 365 come prodotto, Microsoft teams potrebbe essere un servizio in ambito). È possibile elencare più servizi separati da due punti e virgola.

> [!NOTE]
> I dati inseriti nelle celle del **prodotto** e di **certificazione** non possono essere modificati dopo l'importazione del foglio di calcolo per la creazione o la personalizzazione di un modello. Inoltre, un gruppo non può contenere due valutazioni che hanno la stessa combinazione di **prodotto/certificazione** . È possibile disporre di più modelli con la stessa combinazione di prodotto/certificazione.

##### <a name="controlfamily-tab"></a>Scheda ControlFamily

La scheda **ControlFamily** è obbligatoria.  Le colonne obbligatorie di questa scheda, che devono seguire l'ordine specificato nel foglio di calcolo di esempio, sono le seguenti:

- **ControlName** : questo è il nome del controllo della certificazione, standard o Regulation, che in genere è un tipo di ID. I nomi dei controlli devono essere univoci all'interno di un modello. Non è possibile disporre di più controlli con lo stesso nome nel foglio di calcolo.

- **controlFamily** : consente di specificare una parola o una frase per il controlFamily, che identifica un ampio raggruppamento di controlli. Un controlFamily non deve essere univoco. è possibile elencare più di una volta in un foglio di calcolo. Lo stesso controlFamily può anche essere elencato in più modelli, anche se non hanno alcuna relazione tra loro. Ogni controlFamily deve essere mappato a almeno un controllo.

- **controlTitle** : consente di specificare un titolo per il controllo. Mentre la proprietà ControlName è un codice di riferimento, il titolo è un formato RTF generalmente visualizzato nelle normative.

- **controlDescription** : consente di specificare una descrizione del controllo.

- **controlActionTitle** : si tratta del titolo di un'azione che si desidera correlare a questo controllo. È possibile aggiungere più azioni separando da due punti e virgola senza spazi tra. Ogni controllo da elencare deve includere almeno un'azione e l'azione deve esistere (il che significa che è possibile elencare un'azione che viene elencata nella scheda **azioni** dello stesso foglio di calcolo, un'azione che esiste in un modello diverso o un'azione creata da Microsoft). Controlli diversi possono fare riferimento alla stessa azione.

##### <a name="actions-tab"></a>Scheda azioni

La scheda **azioni** è obbligatoria.  Designa le azioni di miglioramento gestite dall'organizzazione e non quelle di Microsoft, che già esistono in Compliance Manager. Le colonne obbligatorie per questa scheda, che devono seguire l'ordine specificato nel foglio di calcolo di esempio, sono le seguenti:

- **actionTitle** : questo è il titolo dell'azione ed è un campo obbligatorio. Il titolo specificato deve essere univoco. **Importante** : se si fa riferimento a un'azione proprietaria già esistente, ad esempio in un altro modello, e si modifica uno dei suoi elementi nelle colonne successive, tali modifiche verranno propagate alla stessa azione in altri modelli.

- **implementationType** : in questo campo obbligatorio elencare uno dei tre tipi di implementazione seguenti:
    - **Operative** -azioni implementate da persone e processi per proteggere la riservatezza, l'integrità e la disponibilità dei sistemi, delle risorse, dei dati e del personale dell'organizzazione (ad esempio: sensibilizzazione e formazione sulla sicurezza)
    - **Technical** -azioni completate tramite l'utilizzo di tecnologie e meccanismi contenuti nei componenti hardware, software o firmware del sistema informativo per proteggere la riservatezza, l'integrità e la disponibilità dei sistemi e dei dati dell'organizzazione (ad esempio: autenticazione a più fattori)
    - **Documentazione** : azioni implementate mediante criteri e procedure documentate che stabiliscono e definiscono i controlli necessari per proteggere la riservatezza, l'integrità e la disponibilità dei sistemi, delle risorse, dei dati e del personale dell'organizzazione (ad esempio, un criterio di sicurezza delle informazioni)

- **actionScore** : in questo campo obbligatorio fornire un valore numerico per l'azione. Deve essere un numero intero compreso tra 1 e 99; non può essere 0, null o vuoto. Maggiore è il numero, maggiore è il valore verso il miglioramento della posizione di conformità. Nell'immagine seguente viene illustrato il controllo dei punteggi di Compliance Manager:

![Compliance Manager controlla i valori dei punti](../media/compliance-score-action-scoring.png "Compliance Manager controlla i valori dei punti")

- **actionDescriptionTitle** : questo è il titolo della descrizione ed è obbligatorio. Questo titolo di descrizione consente di avere la stessa azione in più modelli e di superficie una descrizione diversa in ogni modello.  Questo campo consente di chiarire il modello a cui fa riferimento la descrizione. Nella maggior parte dei casi, è possibile inserire il nome del modello che si sta creando in questo campo.

- **actionDescription** : consente di specificare una descrizione dell'azione. È possibile applicare la formattazione come testo in grassetto e collegamenti ipertestuali. Questo è il campo obbligatorio.

- **scopo della dimensione** : questo è un campo facoltativo. Se lo si include, l'intestazione deve includere il prefisso "Dimension-". Tutte le dimensioni incluse in questa sezione verranno utilizzate come filtri in Compliance Manager e visualizzate nella pagina dei dettagli sulle azioni di miglioramento in Compliance Manager.

##### <a name="dimensions-tab"></a>Scheda dimensioni

La scheda **dimensioni** è facoltativa. Tuttavia, se si fa riferimento a una dimensione altrove, è necessario specificarla qui se non esiste in un modello già creato o in un modello Microsoft. Le colonne di questa scheda sono elencate di seguito:

- **dimensionKey** : elenco come "prodotto", "certificazioni", "scopo dell'azione"
- **dimensionValue** : esempi: Office 365, HIPPA, preventive, detective

È possibile visualizzare le dimensioni esistenti accedendo alla **gestione tenant** e selezionando la scheda **dimensioni** . Inoltre, ogni volta che si esporta un modello esistente, il foglio di calcolo esportato avrà la scheda **dimensioni** , in cui sono elencate tutte le dimensioni utilizzate nel modello.

## <a name="modify-a-template"></a>Modificare un modello

È possibile che si desideri modificare un modello già creato, ad esempio per aggiungere controlli o per aggiungere o rimuovere azioni di miglioramento. Il processo è simile al processo di creazione dei modelli, in quanto verrà caricato il file di Excel formattato con i dati del modello.

Tuttavia, sono disponibili dettagli particolari da tenere presenti quando si formatta il file con le modifiche apportate ai dati dei modelli esistenti. **È consigliabile esaminare attentamente queste istruzioni per assicurarsi di non sovrascrivere i dati esistenti che si desidera conservare.**

### <a name="template-modification-process-steps"></a>Passaggi del processo di modifica del modello

Per modificare un modello, eseguire la procedura seguente:

1. Dalla pagina **modelli di valutazione** selezionare il modello che si desidera modificare, che consentirà di visualizzare la pagina dei dettagli.
2. Selezionare **Esporta in Excel** . Verrà scaricato un file di Excel con tutti i dati del modello. Salvare il file nel computer locale.
3. Apportare le modifiche al modello modificando [il file di Excel attenendosi alle istruzioni](#formatting-your-excel-file-to-modify-a-template)riportate di seguito.
4. Dopo aver completato le modifiche apportate al file di Excel, salvare il file.
5. Nella pagina dei dettagli del modello selezionare **modifica modello** per avviare la procedura guidata per la modifica. 
6. Nella schermata **Carica file** fare clic su **Sfoglia** per individuare e caricare il file di Excel.
7. Se non ci sono problemi con il file, nella schermata successiva viene visualizzato il nome del file caricato. Fare clic su **Avanti** per continuare (se è necessario modificare il file, selezionare **carica un file diverso** ).
    - Se si verifica un problema con il file, un messaggio di errore nella parte superiore spiega cosa c'è di sbagliato. È necessario correggere il file e caricarlo di nuovo. Si verificherà un errore se il foglio di calcolo è formattato in modo errato o se sono presenti informazioni non valide in determinati campi.

8. La schermata **revisione e fine** Visualizza il numero di azioni e controlli di miglioramento e il punteggio massimo per il modello. Quando si è pronti per l'approvazione, selezionare **Avanti** .
9. L'ultima schermata conferma che il modello è stato modificato. Fare clic su **fine** per uscire dalla procedura guidata.

Il modello includerà ora le modifiche apportate. Tutte le valutazioni che utilizzano questo modello modificato ora visualizzeranno gli aggiornamenti in sospeso e sarà necessario accettare gli aggiornamenti alle valutazioni per riflettere le modifiche apportate nel modello. Per ulteriori informazioni, vedere [aggiornamenti alle valutazioni](compliance-manager-assessments.md#accepting-updates-to-assessments).

> [!NOTE]
> Se si utilizza Compliance Manager in una lingua diversa dall'inglese, si noterà che alcuni testi vengono visualizzati in inglese quando si esporta un modello in Excel. I titoli delle azioni (sia le azioni di miglioramento che le azioni Microsoft) devono essere in inglese per essere riconosciuti dai controlli. Se si apportano modifiche a un titolo di azione, accertarsi di scriverlo in inglese in modo che il file importi correttamente.

### <a name="formatting-your-excel-file-to-modify-a-template"></a>Formattazione del file di Excel per modificare un modello

Passare a una delle sezioni seguenti per trovare rapidamente le istruzioni necessarie:

- [Modificare gli attributi dei modelli principali](#edit-the-main-template-attributes)
- [Aggiungere un'azione di miglioramento](#add-an-improvement-action)
- [Modificare le informazioni di un'azione di miglioramento](#edit-an-improvement-actions-information)
- [Modificare il nome di un'azione di miglioramento](#change-an-improvement-actions-name)
- [Eliminazione di un'azione di miglioramento](#remove-an-improvement-action)
- [Rimuovere un controllo](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>Modificare gli attributi dei modelli principali

Nella scheda **modelli** è possibile modificare qualsiasi elemento nella colonna **title** , nella colonna **inScopeServices** e in qualsiasi altra colonna aggiunta. Tuttavia, non è possibile modificare nulla nelle colonne **Product** o **Certification** .

#### <a name="add-an-improvement-action"></a>Aggiungere un'azione di miglioramento

1. Passare alla scheda **azioni** . Aggiungere le informazioni nei campi obbligatori nella prima riga vuota al di sotto delle azioni esistenti.
2. Andare alla scheda **ControlFamily** . Individuare la riga contenente il controllo a cui è associata l'azione di miglioramento. Aggiungere la nuova azione alla colonna **controlActionTitle** in quella riga (ricordarsi di separare più azioni in questo campo con due punti e virgola, senza spazi tra).
3. Salvare il foglio di calcolo.

#### <a name="edit-an-improvement-actions-information"></a>Modificare le informazioni di un'azione di miglioramento

È possibile modificare le informazioni di qualsiasi azione di miglioramento *ad eccezione del titolo* . È possibile modificare qualsiasi cella dalle colonne B e quindi quando si importa il file di nuovo nel modello, le azioni di miglioramento in quel modello conterranno ora i dati aggiornati.

Non è possibile modificare il **actionTitle** (colonna a) perché, se lo si desidera, Compliance Manager ritiene che sia una nuova azione di miglioramento. Se si desidera modificare il nome di un'azione di miglioramento, vedere le istruzioni riportate di seguito.

#### <a name="change-an-improvement-actions-name"></a>Modificare il nome di un'azione di miglioramento

Se si desidera modificare il nome di un'azione di miglioramento, è necessario indicare in modo esplicito nel foglio di calcolo che si sostituisce un nome esistente con un nuovo nome. attenersi alla seguente procedura:

1. Nella scheda **azioni** del foglio di calcolo, aggiungere una nuova colonna al foglio di calcolo dopo la colonna a.
2. In questa nuova colonna, che ora è la colonna B, inserire l'intestazione nella riga 1: **oldActionTitle** .
3. Copiare il contenuto della colonna A e incollarlo nella colonna B. In questo modo i titoli di azione di miglioramento esistenti, che sono ciò che si desidera modificare, vengono inseriti nella colonna B.
4. Nella colonna A, **actionTitle** , eliminare il vecchio nome e sostituirlo con il nuovo nome per l'azione di miglioramento.

Tenere presente che i titoli di azione, sia per le azioni di miglioramento che per le azioni Microsoft, devono essere scritti in inglese per essere riconosciuti quando si fa riferimento ai controlli.

#### <a name="remove-an-improvement-action"></a>Eliminazione di un'azione di miglioramento

L'eliminazione di un'azione di miglioramento da una riga di un foglio di calcolo **non** consente di rimuovere l'azione dal modello che si sta modificando. Seguire invece il processo seguente:

1. Nella scheda **azioni** , inserire una nuova colonna come colonna a e inserire l' **operazione** nella riga di intestazione, che corrisponde al numero di riga 1.
2. Nella riga per l'azione di miglioramento che si desidera rimuovere, inserire **Delete** nella colonna a per quella riga.
3. Verificare che questa azione di miglioramento non sia più referenziata da un controllo. Andare alla scheda **ControlFamily** e cercare il titolo dell'azione di miglioramento nella colonna F, che è **controlActionTitle** .
4. Quando si trova l'azione di miglioramento elencata nella colonna **controlActionTitle** , eliminarla.
5. Salvare il foglio di calcolo.

Quando si importa di nuovo il foglio di calcolo nel modello, l'azione verrà rimossa dal modello. La rimozione di un'azione da un modello non rimuove completamente l'azione. È comunque possibile fare riferimento a questa azione tramite un altro modello.

Se si sta rimuovendo l'ultima azione di miglioramento che fa riferimento a un controllo, è necessario rimuovere il controllo.

#### <a name="remove-a-control"></a>Rimuovere un controllo

Per rimuovere un controllo, seguire lo stesso processo per rimuovere un'azione di miglioramento come illustrato sopra. Nella scheda **ControlFamily** aggiungere una colonna **Operation** e inserire **Delete** accanto al controllo che si desidera rimuovere.

## <a name="export-a-template"></a>Esportare un modello

È possibile esportare un file di Excel contenente tutti i dati di un modello. Sarà necessario esportare un modello per modificare il modello, in quanto si tratta del file di Excel da modificare e caricare nel [processo di modifica](#modify-a-template).

Per esportare il modello, passare alla pagina dei dettagli del modello e selezionare il pulsante **Esporta in Excel** .

Si noti che quando si esporta un modello esteso da un modello di Compliance Manager, il file esportato conterrà solo gli attributi aggiunti al modello. Il file esportato non includerà i dati del modello originale forniti da Microsoft. Per ottenere un report di questo tipo, vedere le istruzioni per l' [esportazione di un rapporto di valutazione](compliance-manager-assessments.md#export-an-assessment-report).