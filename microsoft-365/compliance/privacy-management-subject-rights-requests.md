---
title: Gestire le richieste di diritti dell'oggetto nella gestione della privacy Microsoft (anteprima)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: La soluzione di richiesta dei diritti dell'oggetto nella gestione della privacy Microsoft consente di trovare i dati personali e collaborare alla revisione del contenuto e alla creazione di report.
ms.openlocfilehash: b266708c97ee4b81af6ba61dfa6716c57ff6026e
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53419776"
---
# <a name="manage-subject-rights-requests-in-privacy-management-preview"></a>Gestire le richieste di diritti dell'oggetto nella gestione della privacy (anteprima)

In questo articolo: informazioni su come utilizzare  la soluzione di richiesta dei diritti dell'oggetto per trovare i dati personali nell'ambiente, collaborare alle recensioni, creare **report** e **automatizzare** le attività chiave.

## <a name="purpose-of-subject-rights-requests"></a>Scopo delle richieste di diritti dell'oggetto

La gestione della privacy offre potenti funzionalità per le richieste di diritti dell'oggetto che consentono di gestire le richieste di persone che desiderano gestire i propri dati personali all'interno dell'organizzazione. Queste richieste vengono talvolta definite anche richieste dell'oggetto dei dati (DSR), richieste DSR (Data Subject Access Requests) o richieste di diritti degli utenti. La gestione della privacy consente al personale responsabile di soddisfare le richieste di diritti dell'oggetto per identificare facilmente gli interessati e trovare le proprie informazioni personali tra i dati dell'organizzazione in Exchange, SharePoint, OneDrive e Teams.

La gestione della privacy è in grado di aiutarti a definire la priorità degli elementi da esaminare all'interno dei dati raccolti per queste richieste. La soluzione è a conoscenza Microsoft Information Protection di riservatezza, che indicano contenuti potenzialmente riservati e che potrebbero richiedere una revisione speciale, e contrassegna gli elementi con queste etichette. Per ulteriori informazioni sulle etichette di riservatezza, vedere [Informazioni sulle etichette di riservatezza.](sensitivity-labels.md) Inoltre, la gestione della privacy può rilevare e contrassegnare gli elementi contenenti i dati di più persone, dove potrebbe essere necessario redigere il contenuto prima di fornirlo all'oggetto dei dati.

Dopo aver raccolto e valutato i dati, è possibile selezionare gli elementi più rilevanti da includere nei report e nelle esportazioni e collaborare in modo sicuro con altri membri del team per spostare le richieste verso il completamento.

## <a name="get-started-with-subject-rights-requests"></a>Introduzione alle richieste di diritti dell'oggetto

La gestione della privacy offre agli amministratori della privacy un hub centrale per gestire le richieste di diritti dell'oggetto ricevute dall'organizzazione.

Per iniziare a gestire un nuovo caso di richiesta o a lavorare su una richiesta in corso, visita la pagina **principale Richieste di diritti dell'oggetto.** Fornisce una panoramica visiva dei casi creati dal team nell'ambito della gestione della privacy, del relativo stato (attivo, chiuso o scaduto), dei tipi di richiesta e di un elenco filtrabile di tutte le richieste. Questa pagina è anche il punto in cui è possibile aprire una nuova richiesta.

Per visualizzare i dettagli sui casi aperti, selezionare qualsiasi richiesta nell'elenco e scegliere **Vai a richiesta dettagli**. Per ulteriori informazioni, vedere [Review and take action on requests](#review-and-take-action-on-requests).

Per aprire una nuova richiesta, vedere [Create a request](#create-a-request).

## <a name="create-a-request"></a>Creare una richiesta

Gli amministratori di Subject Rights Management possono utilizzare la procedura guidata di gestione della privacy per creare richieste. La procedura guidata guiderà l'utente attraverso il processo di ricerca dei dati personali su un soggetto di dati e l'adempimento della loro richiesta.

I quattro passaggi principali includono i seguenti.

### <a name="identify-the-data-subject"></a>Identificare l'oggetto dei dati

Fornire il nome dell'oggetto che ha effettuato la richiesta e specificare la relazione con la società.

### <a name="select-the-request-type"></a>Selezionare il tipo di richiesta

Scegli un tipo di richiesta in base alle attività che l'utente vuole che tu faccia con i loro dati. Se la richiesta si riferisce a una specifica normativa sulla privacy dei dati, puoi anche selezionarla da un elenco fornito per aggiungere altro contesto. L'impostazione di una scadenza (obbligatoria) agevolerà l'ordinamento delle richieste in arrivo o scadute e la risoluzione delle richieste in modo rapido. I tipi di richiesta includono:

- **Access**: fornisce un riepilogo delle informazioni personali dell'utente tenuto dall'organizzazione in Microsoft 365.
- **Export**: fornisce un riepilogo e un'esportazione delle informazioni personali dell'oggetto dati, come raccolto e annotato durante la revisione.
- **Elenco contrassegnato per il follow-up:** genera un riepilogo dei file che potrebbero richiedere ulteriori azioni al di fuori della gestione della privacy. Uno scenario di esempio può essere se è necessario facilitare l'eliminazione delle informazioni personali dell'oggetto dei dati in base alla loro richiesta.

### <a name="confirm-the-request-name"></a>Confermare il nome della richiesta

Questo passaggio consente di confermare il nome di questa richiesta e aggiungere una descrizione facoltativa come riferimento.

### <a name="review-and-finish"></a>Rivedere e completare 

Riepilogo degli elementi immessi durante i passaggi precedenti. È possibile modificare qualsiasi campo prima di selezionare **Crea richiesta.**

A questo livello, alcune proprietà possono essere modificate dopo la creazione della richiesta, tra cui la scadenza, il nome della richiesta e la descrizione, ma le proprietà chiave come l'identità dell'oggetto non possono essere modificate. Per modificare una richiesta esistente, trovarla nell'elenco delle richieste nella pagina Richieste diritti oggetto e utilizzare **l'azione Modifica dettagli** richiesta.

## <a name="review-and-take-action-on-requests"></a>Esaminare ed eseguire azioni sulle richieste

Dopo l'apertura di una richiesta, la gestione della privacy inizierà a cercare i dati Microsoft 365 per trovare i dati sull'oggetto. Per visualizzare i risultati iniziali, selezionare la richiesta nell'elenco e scegliere **Vai a richiesta dettagli**. Qui puoi trovare altre informazioni sulle proprietà della richiesta, sui risultati della ricerca e sullo stato della richiesta. Questa pagina diventerà anche l'hub per lavorare e collaborare alla gestione dei file trovati, alla creazione di report ed esportazioni e al completamento della richiesta.

I riquadri in questa pagina includono:

- **Dettagli**: dettagli di base sulla richiesta, inclusa la data di scadenza e la data della richiesta, la descrizione e la normativa sulla privacy correlata.
- **Progress**: sequenza temporale che indica i passaggi completati e tutte le attività ancora da completare.
- **Riepilogo della stima dei** dati : panoramica dei dati valutati nella ricerca. Per ulteriori informazioni su queste informazioni, vedere View and edit search queries.
- Elementi di priorità da **esaminare:** se applicabile, verranno visualizzate informazioni sugli elementi importanti rilevati automaticamente dalla gestione della privacy, incluse le informazioni riservate che già recano un'etichetta di riservatezza Microsoft o gli elementi con dati su più utenti che potrebbero richiedere una redazione. Gli elementi di priorità sono disponibili in Dati raccolti filtrando in base alla colonna "Tipi di priorità".

### <a name="monitor-progress-and-complete-requests"></a>Monitorare lo stato e le richieste complete

Le richieste di diritti dell'oggetto attraversano più fasi per il completamento. Alcune fasi avanzano automaticamente con la valutazione dei dati da parte della gestione della privacy, mentre altre avanzano quando gli amministratori e i collaboratori delle richieste di diritti dell'oggetto completano passaggi essenziali come la revisione, la selezione e la redazione dei file.

Poiché potrebbe essere necessario lavorare sulle richieste nel tempo o da più collaboratori, la gestione della privacy fornisce aggiornamenti continui sullo stato di una richiesta e indicazioni sui passaggi successivi da eseguire. Questi aggiornamenti possono essere visualizzati nella pagina panoramica della richiesta di diritti dell'oggetto. Le fasi di avanzamento includono le seguenti.

#### <a name="data-estimate"></a>Stima dei dati

La stima dei dati è la fase iniziale della valutazione dei dati. Dopo la creazione di una richiesta, la gestione della privacy identifica il numero di elementi nei dati dell'organizzazione che includono potenziali corrispondenze all'oggetto dei dati e prende nota della posizione in cui si trova Microsoft 365. Al termine della stima dei dati, è possibile visualizzare in anteprima i risultati ed esaminare i dettagli della query di ricerca originale. Se si desidera modificare la query di ricerca, vedere le istruzioni in [Visualizzazione e modifica delle query di ricerca.](#view-and-edit-search-queries) Se i risultati iniziali sono soddisfacenti, è possibile procedere con **il recupero dei dati**.

- È possibile recuperare fino a 10.000 singoli elementi da qualsiasi ricerca. I file associati a un elemento corrispondente (ad esempio, file allegati in un messaggio di posta elettronica) possono contare sul totale. Se la ricerca supera la soglia di conteggio dei file, provare a rivedere la ricerca per affinare l'ambito. Per ulteriori [informazioni, vedere la](#view-and-edit-search-queries) sezione Visualizzare e modificare le query di ricerca. Non sarà possibile modificare la query di ricerca dopo aver avviato la fase di recupero dei dati.

#### <a name="retrieve-data"></a>Recuperare i dati

Questa fase indica che la gestione della privacy è in fase di recupero dei dati. Una volta completato, avanzerà automaticamente per esaminare **i dati.**

#### <a name="review-data"></a>Esaminare i dati

In questa fase, i collaboratori devono esaminare i risultati nella scheda Dati raccolti. I passaggi essenziali includono:

- Scegliere se includere gli elementi identificati nei riepiloghi e/o nelle esportazioni. Se nell'esportazione o nel report non è necessaria una corrispondenza segnalata, selezionare l'opzione "Escludi". Se il contenuto sembra essere un falso positivo, puoi scegliere "Non una corrispondenza" per escludere il file dai rapporti finali e contrassegnare l'elemento come elemento che non dovrebbe essere stato raccolto dalla richiesta. Per impostare lo stato di un elemento, usa il menu azione (puntini di sospensione verticali) accanto al nome e seleziona la scelta desiderata. Se richiesto, aggiungere una nota per il riferimento interno per spiegare la decisione. Le note sono necessarie quando si escludono i file.
- Usa **l'opzione Applica** tag per identificare gli elementi che necessitano di attenzione. I tag disponibili includono le opzioni fornite dal sistema, ad esempio il tagging di un elemento per il follow-up, e possono includere tag personalizzati come definito in Impostazioni.
- Usa **Annota** per creare contrassegni in linea o redazioni su un file selezionato. Ad esempio, se è necessario includere un file per una persona che contiene anche le informazioni personali di altri utenti, è possibile utilizzare la **redazione Area** (sotto il pulsante Disegno nella barra dei comandi) per black out tutte le informazioni che non riguardano la persona che ha effettuato la richiesta. Al termine delle modifiche, selezionare Includi per aggiungere il file redatto alla richiesta. Nota che l'annotazione crea una copia del file, in modo che nulla nel file originale sia modificato e rimanga nella posizione originale. La copia viene archiviata nel BLOB di Azure e rimarrà per tutta la durata del periodo di conservazione dei dati specificato. Per altre informazioni, vedi [Conservazione dei dati di](#data-retention) seguito.
- Per rivedere le note su un elemento, selezionarlo e passare alla scheda Note file. Puoi anche usare l'opzione Aggiungi nota file per creare un nuovo commento. Per rivedere o aggiungere note a livello di caso generale, passare alla scheda Note principale sopra e usare **Aggiungi nota caso.** Queste note saranno visibili agli utenti che lavorano alla richiesta, ma non verranno incluse nel report finale o condivise in altro modo con l'oggetto dei dati.

Dopo aver esaminato tutti gli elementi e  impostato i relativi stati, selezionare Completa revisione per aprire un riquadro a comparsa in cui è possibile esaminare un riepilogo dei dati e aggiungere eventuali note pertinenti. Queste note sono per la conservazione dei record interni e non vengono condivise con l'oggetto dei dati. Selezionare di nuovo Completa revisione per passare alla fase successiva. I riepiloghi delle decisioni verranno forniti in un secondo momento nella scheda Report.

#### <a name="generate-reports"></a>Generare report

Questa fase indica che i report vengono generati. Al termine, questi elementi sono disponibili nella **scheda** Report. I file finiti qui possono essere esportati per la consegna all'oggetto dati che ha effettuato la richiesta.

#### <a name="close-the-request"></a>Chiudere la richiesta

Dopo aver eseguito le azioni necessarie per risolvere la richiesta di diritti dell'oggetto, scegliere **Chiudi la richiesta.** Verrà creato il report finale, che verrà crittografato e reso disponibile nella **scheda** Report. L'operazione potrebbe richiedere del tempo a seconda del numero di file nella richiesta.

### <a name="view-and-edit-search-queries"></a>Visualizzare e modificare query di ricerca

Per visualizzare informazioni dettagliate sulla ricerca di dati alla base di una richiesta di diritti dell'oggetto, selezionare Visualizza dettagli **query** di ricerca nella scheda di riepilogo della stima dei dati. Verrà visualizzato un riquadro che riepiloga la query e mostra ulteriori dettagli su ciò che è stato trovato.

Sarà possibile visualizzare in anteprima **i** risultati della ricerca per vedere il tipo di contenuto che verrà restituito per la query. Se si determina che si desidera modificare le proprietà di questa ricerca e non è stata avviata la fase Recupera dati, è possibile utilizzare l'opzione **Modifica query di** ricerca. Questa procedura guidata offre la possibilità di modificare o aggiungere proprietà per l'identificazione dell'oggetto dati, i filtri e le condizioni di ricerca e le posizioni in cui cercare i dati (inclusi Exchange, SharePoint, OneDrive e/o Teams). Usa queste opzioni per raggiungere il livello di specificità desiderato. È possibile esaminare la versione finale della nuova query prima di premere **Salva.**

Al termine della modifica della query di ricerca, verrà eseguita una nuova ricerca per sostituire i risultati della ricerca precedenti. In questo modo lo stato nella sezione Stato viene reimpostato sul primo passaggio, **Stima dati**. Il completamento della nuova ricerca può richiedere fino a 60 minuti. Al termine, vedrai i risultati aggiornati nella pagina dei dettagli della richiesta.

### <a name="data-retention"></a>Conservazione dei dati

I report generati tramite questo strumento e i dati associati, ad esempio i file con annotazioni salvati in Azure, vengono archiviati per un periodo di tempo specificato. Questa durata viene definita a  livello globale tramite  Impostazioni nella sezione Periodi di conservazione dei dati, che consente di scegliere tra 30 e 90 giorni. Per altre informazioni, vedi [Introduzione alla gestione della privacy.](privacy-management-setup.md)

## <a name="collaborate-on-requests-with-teams"></a>Collaborare alle richieste con Teams

La gestione della privacy supporta la collaborazione Microsoft Teams per consentire al gruppo di collaborare alle richieste di diritti dell'oggetto. Quando crei una nuova richiesta, per impostazione Teams viene creato automaticamente un canale di Teams associato alla richiesta. Qui puoi discutere la richiesta e condividere in modo sicuro input e contributi mentre si sposta verso il completamento. Per partecipare alla conversazione, apri la richiesta e usa **l'opzione Chat con i** collaboratori. Verrà aperta la Microsoft Teams e verrà posizionata all'interno del canale Generale per il sito del team della richiesta di diritti dell'oggetto.

Per esaminare l'elenco dei collaboratori attivi che possono visualizzare e contribuire al sito del team, all'interno della richiesta di diritti dell'oggetto aprire la **scheda** Collaboratori. Per aggiungere altri utenti per collaborare a questa richiesta, selezionare l'opzione Aggiungi un collaboratore.

Per modificare il comportamento predefinito della generazione di siti Teams durante la creazione di una richiesta di diritti dell'oggetto,  selezionare l'ingranaggio **Impostazioni** nell'angolo superiore destro della pagina della richiesta di diritti dell'oggetto e selezionare collaborazione Teams per modificare l'impostazione.

Puoi anche usare  l'opzione Condividi in alto a destra all'interno di una richiesta di diritti dell'oggetto per eseguire un ciclo di utenti tramite Teams o posta elettronica o per copiare il collegamento alla pagina in Gestione privacy. La condivisione tramite Teams ti consentirà di selezionare un sito di Teams esistente disponibile per il tuo account e di selezionare un canale specifico all'interno del sito in cui invierà il collegamento a questo caso insieme a qualsiasi messaggio fornito.

## <a name="automate-subject-rights-request-tasks"></a>Automatizzare le attività di richiesta dei diritti dell'oggetto

Microsoft Power Automate è un servizio di flusso di lavoro che automatizza le azioni tra applicazioni e servizi. Quando si abilitano Power Automate per la gestione della privacy, è possibile automatizzare attività importanti per casi e utenti. Per ulteriori informazioni sulle Power Automate, visitare il sito [della documentazione.](/power-automate/getting-started)

I clienti con Microsoft 365 che includono la gestione della privacy non hanno bisogno di altre licenze Power Automate per usare i modelli di gestione della privacy Power Automate consigliati. Questi modelli possono essere personalizzati per supportare l'organizzazione e coprire gli scenari di gestione della privacy di base. Se si sceglie di utilizzare le funzionalità di Power Automate premium in questi modelli, creare un modello personalizzato utilizzando il connettore di conformità di Microsoft 365 o utilizzare modelli Power Automate per altre aree di conformità in Microsoft 365, potrebbero essere necessarie altre licenze Power Automate.

I modelli Power Automate seguenti sono inclusi nella gestione della privacy:

- Creare un record per il caso di gestione della **privacy in ServiceNow**: questo modello è per le organizzazioni che desiderano utilizzare la soluzione ServiceNow per tenere traccia dei casi di richiesta di diritti dell'oggetto. Verrà richiesto di immettere i dettagli dell'istanza di ServiceNow. Una volta connessi all'istanza, gli amministratori delle richieste di diritti dell'oggetto saranno in grado di creare un record per il caso in ServiceNow e di personalizzare ciò che il modello popolerà nei campi selezionati, se necessario. Per ulteriori informazioni sul connettore, vedere la [pagina di riferimento serviceNow Connector](/connectors/service-now/).
- **Creare un promemoria del calendario:** questo modello consente di impostare i promemoria della data di scadenza nel Outlook calendario per le richieste di diritti dell'oggetto. Lo strumento popolerà alcuni dettagli dalle proprietà della richiesta, ad esempio il nome della richiesta e la data di scadenza. È possibile aggiungere dettagli descrittivi, specificare i destinatari e modificare altre impostazioni avanzate.

### <a name="create-a-new-power-automate-flow-from-a-template"></a>Creare un nuovo Power Automate flusso di lavoro da un modello

Per iniziare, aprire la richiesta di diritti **dell'oggetto** che si desidera utilizzare, selezionare **Automate** e quindi selezionare Manage Power Automate flows . Verrà aperto il riquadro a comparsa Flussi. Usa l'opzione Nuovo e scegli il modello che vuoi usare tra le opzioni disponibili. Da qui, seguire le istruzioni per completare l'installazione.

Dopo aver salvato un'istanza del modello, è necessario eseguirla dalla pagina dei dettagli della richiesta di diritti dell'oggetto in modo che l'istanza del flusso abbia il contesto e l'ID appropriati. Aprire la richiesta, tornare al menu **Automate,** selezionare il modello e selezionare **Esegui flusso.** È possibile visualizzare le attività passate selezionando Visualizza **attività di esecuzione del flusso.**

### <a name="share-a-power-automate-flow"></a>Condividere un Power Automate flusso

Condividendo un Power Automate, è possibile aggiungere un altro proprietario e consentire loro di modificare, aggiornare ed eliminare il flusso. Tutti i proprietari possono inoltre accedere alla cronologia di esecuzione e aggiungere o rimuovere altri proprietari. Per condividere un flusso, aprire la richiesta di diritti **dell'oggetto** che si desidera utilizzare, selezionare **Automate** e quindi selezionare Manage Power Automate flows . In questo riquadro è possibile selezionare un flusso esistente, quindi utilizzare l'opzione Condividi per aggiungere un utente o un gruppo.

Questo riquadro offre inoltre la possibilità di gestire le connessioni incorporate ai servizi utilizzati nel Power Automate flusso. La modifica di queste impostazioni può influire sulla capacità di eseguire il flusso.

### <a name="edit-or-delete-power-automate-flow"></a>Modificare o eliminare Power Automate flusso

Per modificare i dettagli di un flusso Power Automate, aprire la richiesta di diritti **dell'oggetto,** selezionare **Automate** e selezionare Manage Power Automate flows . In questo riquadro è possibile selezionare un flusso esistente per visualizzare i dettagli. Utilizzare Modifica in qualsiasi sezione per modificare le proprietà e quindi salvare.

Per rimuovere completamente il flusso, utilizzare **l'opzione** Elimina. Rimuoverà il flusso per tutti i proprietari e lo disinstallerà per tutti gli utenti. Le istanze del flusso precedente continueranno a essere eseguite per evitare la perdita di dati. Puoi confermare la scelta prima che l'eliminazione sia definitiva.

## <a name="data-matching"></a>Corrispondenza dati

Con la corrispondenza dei dati, le organizzazioni possono abilitare la soluzione di gestione della privacy per identificare gli interessati in base ai valori dei dati forniti. In questo modo è possibile aumentare l'accuratezza dell'individuazione del contenuto dell'oggetto dei dati sia per il personale interno che per gli utenti esterni con cui si interagisce. Semplifica inoltre la necessità di fornire manualmente i campi durante la creazione delle richieste di diritti dell'oggetto e fornisce il contesto all'interno delle richieste di diritti dell'oggetto e per il riquadro Panoramica che mostra gli elementi con il maggior numero di contenuti dell'oggetto dati. Per ulteriori informazioni su tale visualizzazione, vedere [Trovare e visualizzare i dati.](privacy-management-data-profile.md#items-with-the-most-data-subject-content)

Per utilizzare la funzionalità di corrispondenza dei dati, è necessario essere membri del gruppo di ruoli Gestione privacy. Seleziona l'icona a forma di ingranaggio delle impostazioni in alto a destra nella pagina principale delle richieste di diritti dell'oggetto e seleziona **Corrispondenza dati**. Da qui, sarà necessario definire lo schema dei dati personali e fornire un caricamento dei dati personali come illustrato di seguito. Tieni presente che puoi aggiungere elementi e puoi eliminare gli elementi aggiunti tramite l'interfaccia utente. Tuttavia, al momento non puoi modificare un elemento sul posto dall'interfaccia utente.

### <a name="prepare-for-data-import"></a>Preparare l'importazione dei dati

Prima di definire lo schema o caricare i dati, è necessario identificare l'origine delle informazioni sull'oggetto dei dati. Il formato di file richiesto è .csv, che può essere letto da un'applicazione, ad esempio Microsoft Excel. Strutturare l'esportazione in modo che le intestazioni di colonna vengano visualizzate nella prima riga. Queste intestazioni devono includere i nomi degli attributi per lo schema dei dati personali. Controllare il formato dei dati in ogni campo. Se uno dei dati contiene virgole, racchiudere questi valori tra virgolette doppie per assicurarsi che non siano analizzati in campi separati.

### <a name="define-the-personal-data-schema"></a>Definire lo schema dei dati personali

Lo schema dei dati personali descrive gli attributi per gli interessati. Upload questo schema nella prima scheda dell'area delle impostazioni di corrispondenza dei dati. I file necessari includono un file XML **dello schema** dei dati personali e un file XML **del pacchetto** di regole.

#### <a name="personal-data-schema-xml"></a>XML dello schema dei dati personali

Il file dello schema dei dati personali è un file XML che definisce i nomi di colonna previsti.

- Assegnare a questo file di schema il *nomepdm.xml*.
- Definire ogni nome di colonna utilizzando il tag Nome campo, come illustrato nell'esempio seguente.
- Utilizzare searchable = "true" per i campi che si desidera siano disponibili per la ricerca, fino a un massimo di cinque campi. Almeno uno dei nomi di campo deve essere ricercabile. Sintassi di esempio: `\<Field name="" searchable=""/>` .
- Lo schema dei dati personali include una sezione tag DataStore. È necessario mappare quattro campi obbligatori ai nomi dei campi: primaryKeyField, upnField, firstNameField, lastNameField.

Ad esempio, il file XML seguente definisce uno schema di esempio, con cinque campi specificati come ricercabili: PatientID, MRN, SSN, Telefono e DOB. PrimaryKeyField è mappato a PatientID, upnField è mappato a MRN, firstNameField è mappato a FirstName e lastNameField è mappato a LastName.

È possibile copiare, modificare e usare l'esempio.

 ```xml
<PdmSchema xmlns="http://schemas.microsoft.com/office/2020/pdm">
      <DataStore name="Patientrecords" description="Schema for patient records" version="1" primaryKeyField="PatientID" upnField="MRN" firstNameField="FirstName" lastNameField="LastName">
            <Field name="PatientID" searchable="true"/>
            <Field name="MRN" searchable="true" />
            <Field name="FirstName" />
            <Field name="LastName" />
            <Field name="SSN" searchable="true" />
            <Field name="Phone" searchable="true" />
            <Field name="DOB" searchable="true" />
            <Field name="Gender" />
            <Field name="Address" />
      </DataStore>
</PdmSchema>
 ```

#### <a name="rule-package-xml"></a>XML del pacchetto di regole

Quando si configura il pacchetto di regole, assicurarsi di fare riferimento correttamente al file dello schema dei dati personali creato in precedenza: pdm.xml. Nel codice XML del pacchetto di regole di esempio seguente, i campi seguenti devono essere personalizzati per creare il tipo di corrispondenza dati sensibile:

- **RulePack id**  &  **PrivacyMatch id:** utilizzare New-GUID per generare un GUID.
- **Archivio dati**: questo campo specifica l'archivio dati di ricerca di corrispondenza dei dati personali da utilizzare. Specificare il nome datastore definito di uno schema di dati personali configurato.
- **idMatch:** questo campo punta all'elemento principale per la corrispondenza dei dati personali.
  - **Corrisponde** a : Specifica il campo da utilizzare nella ricerca esatta. Specificare un nome di campo ricercabile dallo schema dei dati personali.
  - **Classificazione:** questo campo specifica la corrispondenza del tipo sensibile che attiva la ricerca della corrispondenza dei dati personali. È possibile specificare il nome o il GUID di un tipo di informazioni sensibili predefinito o personalizzato esistente. Per evitare problemi di prestazioni, se si utilizza un tipo di informazioni riservate personalizzato come elemento Classification nei dati personali, non utilizzare un tipo di informazioni riservate personalizzato che corrisponderà a una grande percentuale di contenuto (ad esempio "qualsiasi numero" o "qualsiasi parola di cinque lettere"). È consigliabile aggiungere parole chiave di supporto o includere la formattazione nella definizione del tipo di informazioni riservate per la classificazione personalizzata.
- **Match**: questo campo punta a prove aggiuntive trovate in prossimità di idMatch.
  - **Corrisponde** a : specificare qualsiasi nome di campo nello schema dei dati personali per DataStore.
- **Risorsa:** questa sezione specifica il nome e la descrizione per il tipo sensibile in più impostazioni locali.
  - **idRef:** specificare il GUID per l'ID ExactMatch.
  - **Nome & descrizioni**: personalizzare in base alle esigenze.

Nell'esempio XML del pacchetto di regole seguente si fa riferimento al file di esempio pdm.xml del passaggio precedente che crea l'XML dello schema dei dati personali:

- **Datastore**: il nome dataStore fa riferimento al file di schema creato in precedenza: dataStore = "PatientRecords".
- **idMatch**: il valore idMatch fa riferimento a un campo ricercabile elencato nel file pdm.xml creato in precedenza: idMatch matches = "SSN".
  - **Classificazione**: il valore di classificazione fa riferimento a un tipo di informazioni riservate esistente o personalizzato: classification = "U.S. Social Security Number (SSN)". In questo caso, viene usato il tipo di informazioni sensibili esistente del Numero di previdenza sociale degli Stati Uniti.

Crea un pacchetto di regole in formato XML (con codifica Unicode), come nel codice di esempio seguente. È possibile copiare, modificare e utilizzare questo esempio.

 ```xml
<RulePackage xmlns="http://schemas.microsoft.com/office/2020/pdm">
  <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b21">
    <Version build="0" major="2" minor="0" revision="0" />
    <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
    <Details defaultLangCode="en-us">
      <LocalizedDetails langcode="en-us">
        <PublisherName>IP DLP</PublisherName>
        <Name>Health Care PDM Rulepack</Name>
        <Description>This rule package contains the Personal Data Match sensitive type for health care sensitive types.</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  <Rules>
    <PrivacyMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB381" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="6">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </PrivacyMatch>
    <LocalizedStrings>
      <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB381">
        <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
        <Description default="true" langcode="en-us">PDM Sensitive type for detecting Patient SSN.</Description>
      </Resource>
    </LocalizedStrings>
  </Rules>
</RulePackage>
 ```

### <a name="upload-personal-data"></a>Upload personali
Dopo aver definito lo schema dei dati personali, è possibile eseguire il caricamento dei dati **personali** nella seconda scheda della pagina delle impostazioni di corrispondenza dei dati. Quando si seleziona **Aggiungi**, scegliere lo schema personale definito nel primo passaggio, quindi caricare il file contenente i dati personali.

È possibile caricare questi dati personali scegliendo un file locale o fornendo un URL della firma di accesso condiviso a un percorso Archiviazione di Microsoft Azure esistente contenente il file di dati personali.
Se è stato preparato un file come primo passaggio di questo processo conforme allo schema creato, è possibile utilizzare tale file per il caricamento.
