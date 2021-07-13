---
title: Creare e gestire criteri nella gestione della privacy Microsoft (anteprima)
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
description: Informazioni su come creare e gestire criteri per la gestione dei dati personali dell'organizzazione in Microsoft 365, rispondere agli avvisi e risolvere i problemi.
ms.openlocfilehash: f9df027d01ffe4629654db1ddd006d141d57e387
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378573"
---
# <a name="create-and-manage-policies-in-privacy-management-preview"></a>Creare e gestire criteri nella gestione della privacy (anteprima)

In questo articolo: informazioni su  come creare e personalizzare  i criteri per la gestione dei dati personali, ottenere avvisi sulle corrispondenze dei criteri e risolvere i **problemi.**

## <a name="purpose-of-policies"></a>Scopo dei criteri

I criteri consentono di definire i tipi di rischi per la privacy da cercare nei dati Microsoft 365 aziendali e di stabilire i risultati preferiti per gli scenari in cui vengono trovate corrispondenze. L'organizzazione può utilizzare gli avvisi risultanti per esaminare i dati corrispondenti e risolvere i problemi, il tutto dall'interno della soluzione di gestione della privacy.

La gestione della privacy offre modelli che consentono di iniziare facilmente la creazione di criteri e di ottimizzare l'approccio tramite ampie opzioni di personalizzazione. Di seguito sono riportati gli scenari principali trattati dai modelli di gestione della privacy:

- **Sovraesposizione dei dati**: rileva i dati personali sovraesposizione e richiede agli utenti di proteggerlo.
- **Trasferimento dei dati**: consente di limitare i trasferimenti di dati personali tra reparti o confini regionali.
- **Riduzione dei dati**: consente agli utenti di identificare e ridurre la quantità di dati personali inutilizzati.

Per altre informazioni sulle funzionalità di ogni modello, vedi di seguito.

## <a name="policy-types"></a>Tipi di criteri

### <a name="data-overexposure"></a>Sovraesposizione dei dati

La gestione della privacy consente di rilevare e gestire situazioni in cui i dati archiviati non sono sufficientemente sicuri. Ad esempio, se l'accesso a un sito interno è aperto a un gruppo troppo ampio o le impostazioni delle autorizzazioni non sono state mantenute aggiornate, i dati personali archiviati in tale sito potrebbero essere vulnerabili a una violazione. È possibile utilizzare il modello di criteri per la gestione della privacy per valutare i dati e avvisare l'utente in caso di potenziali problemi.

### <a name="data-transfer"></a>Trasferimento dei dati

Il trasferimento di dati tra reparti o confini regionali può aumentare il rischio di esposizione dei dati, ad esempio se vengono inviati tramite messaggi di posta elettronica non crittografati o a destinatari non autorizzati. Tali azioni possono avere un impatto normativo o possono andare contro le procedure stabilite per la privacy. L'uso del modello di trasferimento dei dati per creare criteri di gestione della privacy può individuare e limitare tali trasferimenti.

> [!NOTE]
> Durante l'anteprima pubblica, alcuni tenant che eseguono criteri di trasferimento dati per rilevare i trasferimenti tra aree geografiche possono riscontrare problemi di sincronizzazione che influiscono sulla visibilità delle corrispondenze dei criteri in Exchange e Teams dati. Ti consigliamo di concentrarti sui SharePoint e OneDrive durante l'anteprima di questo tipo di criteri. Un aggiornamento per questo problema è previsto nell'autunno 2021.

### <a name="data-minimization"></a>Riduzione dei dati

Nel tempo, le aziende possono raccogliere grandi quantità di dati personali da clienti o dipendenti. A volte sono inclusi i dati raccolti in eccesso o inutilizzati e che devono essere ridotti per limitare i rischi per la privacy relativi a tali informazioni. Il modello di riduzione dei dati può essere utilizzato per affrontare i rischi di questo tipo.

## <a name="get-started-with-default-templates"></a>Introduzione ai modelli predefiniti

La gestione della privacy consente di avviare il processo di valutazione dei dati creando tre criteri con impostazioni predefinite, utilizzando i modelli per la minimizzazione dei dati, la sovraesposizione dei dati e i trasferimenti di dati. Questi criteri saranno attivati per impostazione predefinita, ma non attiveranno automaticamente messaggi di notifica o richieste di correzione. Dopo la configurazione iniziale, è possibile procedere alla creazione e alla personalizzazione dei propri criteri.

## <a name="create-a-privacy-management-policy"></a>Creare criteri di gestione della privacy

Esistono due percorsi per la creazione di criteri di gestione della privacy. La prima opzione è scegliere tra l'insieme di modelli predefiniti. Puoi anche personalizzare i tuoi criteri, usando uno qualsiasi di questi modelli come punto di partenza.

### <a name="create-a-policy-from-a-template"></a>Creare un criterio da un modello

Per iniziare subito a usare un criterio, selezionare uno dei tre tipi di criteri pre-impostati. Per esaminare i dettagli relativi a una qualsiasi di esse, è possibile selezionare Visualizza impostazioni per visualizzare le proprietà specifiche che costituiscono il criterio, inclusi i tipi di dati, le posizioni dei dati e le condizioni che attivano le corrispondenze dei criteri.

Quando si crea un criterio direttamente da un modello, verranno scelte automaticamente molte impostazioni. Ciò include l'attivazione del criterio per impostazione predefinita. Se vuoi visualizzare in anteprima il criterio in azione prima di attivarlo completamente, individualo nell'elenco dopo la creazione, modifica il criterio e passa alla modalità di test. Per ulteriori informazioni, vedere [Test your policy](#test-your-policy).

### <a name="create-custom-policy"></a>Creare criteri personalizzati

Per assumere un controllo granulare delle impostazioni di un criterio, è possibile creare un criterio personalizzato utilizzando uno dei modelli esistenti come base. La gestione della privacy fornisce una procedura guidata per guidare l'utente attraverso questi passaggi.

Le proprietà personalizzabili includono:

- **Nome e tipo:** scegli il modello su cui creare i criteri, quindi denoti e descrivi la versione.
- **Dati da monitorare:** selezionare il tipo di dati personali che verranno monitorati dal criterio. Scegliere uno dei gruppi di classificazione disponibili oppure scegliere tra i singoli tipi di informazioni riservate. Per altre informazioni, vedi Scegliere le opzioni di monitoraggio dei dati di seguito.
- **Utenti**: selezionare se questo criterio si applica a tutti gli utenti o a utenti selezionati. Se scegli la seconda opzione, puoi selezionare fino a 300 utenti di tua scelta nell'elenco fornito.
- **Posizioni**: scegliere le posizioni all'interno Microsoft 365 che i criteri devono coprire, ad esempio i dati SharePoint o Exchange'organizzazione.
- **Condizioni**: selezionare le condizioni pertinenti per il tipo di criterio. Ad esempio, è possibile specificare quali tipi di trasferimenti devono essere cercati da un criterio di trasferimento dei dati o l'ultimo utilizzo dei dati per un criterio di minimizzazione dei dati.
- **Risultati**: definire i risultati quando viene rilevata una corrispondenza dei criteri. Le opzioni dipendono dal tipo di criterio da cui si inizia. I possibili risultati includono:
  - **Notifiche tramite posta** elettronica : questa impostazione consente di attivare le notifiche di posta elettronica digest, inclusi i collegamenti alla formazione correlata. Per altre informazioni, vedi Impostare le notifiche tramite posta elettronica degli utenti di seguito.
  - **Teams**: fornire agli utenti Teams suggerimenti e suggerimenti sui criteri, insieme ai collegamenti alla formazione correlata. Questa opzione è disponibile per i criteri di trasferimento dei dati.
- **Avvisi**: decidere la frequenza degli avvisi per gli amministratori quando viene rilevata una corrispondenza dei criteri. Le opzioni non includono avvisi, avvisi per ogni corrispondenza dei criteri o avvisi quando viene raggiunta una soglia specifica. Se scegli l'opzione di soglia, imposta i parametri desiderati.
- **Mode:** decidi se eseguire un criterio prima in modalità test o attivarlo immediatamente. Per altre informazioni, vedi Testare i criteri.
Dopo aver esaminato tutte le impostazioni della procedura guidata, rivedere le impostazioni, apportare eventuali modifiche finali, se necessario, e salvare i criteri.

#### <a name="choose-data-monitoring-options"></a>Scegliere le opzioni di monitoraggio dei dati

Quando si configura un criterio personalizzato, verrà richiesto di selezionare i tipi di dati da monitorare. Le opzioni sono le seguenti:

- **Gruppi di classificazione:** elenco di set di dati ricercabili in base alle normative chiave sulla privacy, ad esempio GDPR o HIPAA. Visualizza i dettagli di qualsiasi gruppo per sapere quali tipi di informazioni riservate copre. Seleziona uno o più di questi set per usarli così come sono. I gruppi attualmente disponibili sono i seguenti:
  - Australia Health Records Act (HRIP Act) Enhanced
  - Australia Privacy Act Enhanced
  - (UE) General Data Protection Regulation (GDPR) Enhanced
  - Dati personali (PII) del Giappone migliorati
  - Japan Protection of Personal Information Enhanced
  - U.S. Gramm-Leach-Bliley Act (GLBA) Enhanced
  - U.S. Health Insurance Act (HIPAA) Enhanced
  - Stati Uniti Patriot Act Enhanced
  - Dati personali (PII) statunitensi migliorati
  - Leggi sulla notifica di violazione dello stato degli Stati Uniti migliorate
- **Tipi di informazioni** riservate individuali: scegliendo tipi di informazioni sensibili specifici, ad esempio numeri di previdenza sociale o informazioni sulla patente di guida, è possibile personalizzare il proprio gruppo o gruppi di dati di cui cercare. Questa procedura guidata consente di selezionare dall'elenco completo dei tipi di informazioni riservate all'interno della gestione della privacy. Ogni tipo di informazioni dispone di proprietà specifiche. Usa il pulsante info accanto a uno di essi per informazioni dettagliate e note sulle impostazioni consigliate. Se si creano più gruppi, la procedura guidata consente di applicare operatori booleani per correlarli e definire l'ordine delle operazioni.

Se si utilizzano gruppi di classificazione pre-impostati, non è inoltre possibile selezionare singoli tipi o creare gruppi personalizzati. Per la massima flessibilità, scegli singoli tipi di informazioni riservate. Per utilizzare gli standard più comuni, scegliere tra i gruppi di classificazione.

#### <a name="test-your-policy"></a>Testare i criteri

Se si desidera valutare un nuovo criterio prima di attivarlo completamente, impostare il criterio sulla modalità test. La modalità test consente di cercare corrispondenze degli ultimi 30 giorni, valutare il comportamento del criterio ed esaminare i tipi di avvisi generati. È consigliabile eseguire criteri di test per almeno cinque giorni per ottenere risultati rappresentativi. Durante la fase di test è possibile modificare e modificare le impostazioni del criterio. Dopo aver ottenuto informazioni dettagliate dall'esecuzione del test, puoi procedere con l'attivazione del criterio. Mentre un criterio è in esecuzione in modalità test, non verrà recapitato alcun messaggio di notifica utente.

#### <a name="set-user-email-notifications"></a>Impostare le notifiche di posta elettronica degli utenti

Con le notifiche tramite posta elettronica, gli utenti ricevono notifiche dirette sulle corrispondenze dei criteri e sulle attività importanti da completare. I destinatari riceveranno digest di posta elettronica che riepilogano i dati da esaminare e le possibili azioni, ad esempio rendere privati i documenti, mantenerli nei file, segnalare eventuali corrispondenze false positive e aggiungere note per riferimento futuro. Questi messaggi di posta elettronica includono anche collegamenti per i destinatari della formazione su come gestire questi casi. La fornitura di questi collegamenti è necessaria quando inizialmente si configurano le notifiche e deve puntare alla propria documentazione interna sui processi e sulle procedure consigliate.

Le notifiche possono essere abilitate per singoli criteri durante la creazione di criteri personalizzati o durante la modifica di qualsiasi criterio. Usa la sezione Risultati per definire cosa accade quando viene rilevata una corrispondenza dei criteri, inclusa l'opzione per abilitare queste notifiche, e impostare la frequenza con cui vuoi che questi digest siano recapitati.

La funzionalità di notifica tramite posta elettronica è controllata a livello globale all'interno Impostazioni. È disabilitato per impostazione predefinita. Se si disattiva questa impostazione, tutti i messaggi di posta elettronica verranno disattivati anche se sono state configurate notifiche specifiche a livello di singolo criterio. Per ulteriori informazioni, vedere Configurare le impostazioni in [Introduzione alla gestione della privacy.](privacy-management-setup.md#configure-settings)

## <a name="view-policy-details"></a>Visualizzare i dettagli dei criteri

Dopo aver creato il criterio, selezionarlo nella pagina **principale Criteri** per visualizzarne la panoramica completa. La pagina dei dettagli dei criteri fornirà informazioni dettagliate sui dati, ti consentirà di visualizzare il contenuto sulle corrispondenze specifiche dei criteri e ti consiglierà sui passaggi successivi. Se il criterio è in esecuzione in modalità test, questa pagina è anche la posizione in cui è possibile attivare i criteri al termine del test.

Dopo aver attivato i criteri, è possibile continuare a esaminare la relativa pagina dei dettagli dei criteri per visualizzare informazioni dettagliate sulle aree del problema, la gravità e le tendenze degli avvisi e le azioni correttive intraprese.

## <a name="resolve-policy-alerts-and-issues"></a>Risolvere gli avvisi e i problemi relativi ai criteri

Una volta attivati i criteri, la gestione della privacy ti permetterà di tenere traccia di importanti individuazioni avvisandoti delle corrispondenze dei criteri, classificando la loro gravità e consentendoti di intervenire creando e risolvendo i problemi.

La pagina Panoramica della gestione della privacy fornisce una panoramica di questi risultati con aggiornamenti dinamici sulle aree di interesse chiave, ad esempio i criteri con il maggior numero di corrispondenze e gli avvisi dei criteri attualmente attivi. Puoi anche accedere ai dettagli relativi agli avvisi e ai problemi tramite la pagina principale Criteri.

### <a name="alerts"></a>Avvisi

Per valutare gli avvisi attivi e specificare quali problemi richiedono il follow-up, accedere alla **pagina Avvisi.** Fornisce un elenco filtrabile degli avvisi generati dai criteri, che è possibile esaminare singolarmente per determinare le circostanze in cui sono stati attivati.

Se si seleziona un avviso, verrà aperto un riquadro a comparsa con ulteriori dettagli, ad esempio il tipo di criterio, il numero di elementi corrispondenti e la gravità in base alle impostazioni dei criteri. Nella scheda **Contenuto** è possibile esaminare i file coinvolti in questo avviso. Queste informazioni possono fornire ulteriori informazioni sull'evento specifico che ha attivato l'avviso, sulla posizione in cui si trovano i file e sui tipi di dati personali coinvolti. I trigger per gli avvisi sono determinati dalle condizioni specifiche di ogni criterio. Ad esempio, un avviso potrebbe essere attivato su un criterio di trasferimento dei dati se la gestione della privacy rileva un trasferimento tra i reparti o le aree geografiche specificati del criterio.

Dopo aver valutato qualsiasi avviso nell'elenco, è possibile utilizzare l'azione Crea problema per richiedere ulteriori indagini e azioni.  Verrà richiesto di assegnare un nome al problema e di aggiungere eventuali commenti rilevanti per il contesto. Puoi anche ignorare gli avvisi qui se non richiedono un follow-up.

### <a name="issues"></a>Problemi

Come descritto nella sezione Avvisi, vengono creati problemi durante la valutazione degli avvisi relativi alle corrispondenze dei criteri. Per seguire e risolvere i problemi indicati, visitare la pagina Problemi. Da qui è possibile esaminare i singoli problemi, analizzare le condizioni di istigazione, esaminare i dati ed eseguire i passaggi necessari per chiudere il caso.

Questa pagina fornisce un elenco di tutti i problemi aperti. I problemi sono elencati per nome e ordinati in base alla gravità per aiutarti a definire la priorità dei casi, incluse le categorie alta, media e bassa, insieme a quelle non assegnate. Selezionare qualsiasi problema nell'elenco per esaminarne il contenuto ed eseguire un'azione per risolverlo. È possibile assegnare ai problemi non assegnati un livello di gravità durante la revisione.

#### <a name="issue-overview"></a>Panoramica del problema

Le pagine dei dettagli del problema guidano l'utente nel processo di gestione dei rischi per la privacy identificati e della corretta gestione dei file indicati. Nella scheda **Panoramica** è possibile visualizzare il passaggio corrente da eseguire, che indica lo stato del problema e le azioni consigliate seguenti. Puoi anche esaminare le informazioni essenziali sul contenuto coinvolto, sui criteri associati, sui dettagli sull'avviso e sulla sequenza temporale.

Le schede successive forniscono ulteriori dettagli sugli avvisi e sul contenuto associati, insieme alle note di altri membri del team che stanno lavorando al problema. Puoi gestire l'elenco dei collaboratori attivi tramite la **scheda** Collaboratori.

#### <a name="share-the-issue"></a>Condividere il problema

L'aggiunta di persone come collaboratori consente di condividere il problema con altri membri dell'organizzazione tramite un canale Microsoft Teams sicuro, un messaggio di posta elettronica aziendale o condividendo un collegamento direttamente alla pagina del problema nella gestione della privacy. Queste opzioni sono disponibili nel **pulsante** Condividi. Quando si condivide tramite Teams, verrà richiesto di selezionare tra i team disponibili nell'organizzazione, selezionare il canale specifico e lasciare un messaggio sul problema, che verrà condiviso con il canale specificato.

#### <a name="review-content-and-remediate"></a>Esaminare il contenuto e correggere

Per esaminare il contenuto associato a un problema, scegliere **l'azione** Rivedi contenuto se richiesto o aprire la scheda Contenuto. Selezionare un file nell'elenco per visualizzarlo per intero. Qui è possibile visualizzare i dettagli relativi al file, alle attività nel record e alla cronologia delle correzioni, se sono stati evasi passaggi precedenti per gestire il file.

Usa il **pulsante Correzione per** prendere le tue decisioni di gestione dei dati per questo contenuto. La selezione del pulsante consente di scegliere tra una o più azioni di correzione. Le opzioni disponibili sono:

**Tutti i criteri**

- **Notify**: notifica al proprietario del contenuto il problema rilevato.
- **Applica etichetta di conservazione**: aggiungere un'etichetta sulla conservazione dei dati per questo elemento. 
- **Applica etichetta di riservatezza**: aggiungere un'etichetta sulla riservatezza dei dati di questo elemento.
- **Contrassegna come non corrispondente**: identificare un risultato di ricerca come falso positivo per rimuovere l'elemento di contenuto dalla considerazione.

**Riduzione dei dati**

- **Ricicla/elimina**: utilizzare questa opzione per un'eliminazione recidiva dei dati. Il contenuto viene spostato nella cartella degli elementi eliminati o nel Cestino (Exchange, SharePoint, OneDrive) o eliminato con un'opzione per il ripristino (Teams messaggi). L'eliminazione può essere annullata entro un determinato periodo di tempo, a seconda delle impostazioni del servizio.

**Sovraesposizione dei dati e trasferimento dei dati**

- **Annulla condivisione:** interrompe la condivisione di un collegamento a questo elemento di contenuto.

Ogni opzione ti chiederà di lasciare commenti e altre informazioni di supporto necessarie per il proprietario del contenuto prima di confermare la scelta.

Dopo aver effettuato tutti i passaggi di correzione e aver risolto il problema, usa il pulsante Risolvi e aggiungi i commenti finali prima di inviarlo.

## <a name="delete-a-policy"></a>Eliminare un criterio

Se devi rimuovere un criterio di gestione della privacy esistente, individualo nell'elenco nella pagina Criteri, seleziona il menu azione (puntini di sospensione verticali) e scegli l'azione Elimina criterio. Ti verrà chiesto di confermare la scelta prima che l'eliminazione sia definitiva e che il criterio venga rimosso definitivamente. L'eliminazione di un criterio non influirà sui file precedentemente valutati dal criterio e i problemi e gli avvisi generati dal criterio rimarranno.
