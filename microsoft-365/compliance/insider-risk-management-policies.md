---
title: Criteri di gestione dei rischi Insider
description: Informazioni sui criteri di gestione dei rischi insider in Microsoft 365
keywords: Microsoft 365, gestione dei rischi Insider, gestione dei rischi, conformità
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 5e81c9ff65db6ecd4a1ac1995c8a592f4377ae1c
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2020
ms.locfileid: "42543552"
---
# <a name="insider-risk-management-policies"></a>Criteri di gestione dei rischi Insider

I criteri di gestione dei rischi Insider determinano quali dipendenti sono in ambito e quali tipi di indicatori di rischio sono configurati per gli avvisi. È possibile creare rapidamente un criterio che si applica a tutti gli utenti dell'organizzazione oppure definire singoli utenti o gruppi per la gestione in un criterio. I criteri supportano le priorità del contenuto per concentrare le condizioni dei criteri su più o specifici team Microsoft, siti di SharePoint, tipi di sensibilità dei dati e etichette dati. Utilizzando i modelli, sono inclusi indicatori di rischio specifici e la quantità di peso assegnato all'interno di un criterio, determinando in modo efficace il peso di ogni trigger di avviso nel criterio. Criteri le finestre consentono di definire la tempistica per applicare il criterio alle attività di avviso e vengono utilizzate per determinare la durata del criterio, una volta attivato. Il limite massimo di criteri è costituito da cinque criteri attivi contemporaneamente. Tuttavia, è possibile configurare criteri aggiuntivi e attivare e disattivare i criteri in base alle esigenze.

## <a name="policy-dashboard"></a>Dashboard di criteri

Il **dashboard dei criteri** consente di visualizzare rapidamente i criteri dell'organizzazione e lo stato corrente degli avvisi associati a ogni criterio.

- **Nome criterio**: il nome assegnato al criterio nella procedura guidata per i criteri.
- **Avvisi attivi**: il numero di avvisi attivi per ogni criterio.
- **Avvisi confermati**: il numero totale di avvisi restituiti nei casi dal criterio negli ultimi 365 giorni.
- **Azioni intraprese sugli avvisi**: il numero totale di avvisi che sono stati confermati o scartati negli ultimi 365 giorni.
- **Efficacia dei criteri**: la percentuale determinata dal totale degli avvisi confermati diviso per le azioni totali eseguite sugli avvisi (ovvero la somma degli avvisi che sono stati confermati o scartati nell'ultimo anno).
- **Attivo**: lo stato del caso, ovvero *Sì* o *No*.

![Dashboard dei criteri di gestione del rischio Insider](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Modelli dei criteri

I modelli di gestione dei rischi Insider sono condizioni di criteri predefinite che definiscono i tipi di indicatori di rischio monitorati da un criterio. Ogni criterio deve disporre di un modello assegnato nella procedura guidata per la creazione dei criteri prima di creare il criterio. Quando si crea un nuovo criterio di rischio Insider, è possibile scegliere uno dei modelli seguenti.

### <a name="departing-employee-data-theft"></a>Furto dei dati del dipendente in partenza

Quando i dipendenti lasciano la propria organizzazione, esistono indicatori di rischio specifici tipicamente associati al furto dei dati da parte dei dipendenti. Questo modello di criteri consente di assegnare una priorità a questi indicatori e di individuare gli avvisi e i punti di interesse per questa area di rischio Il furto dei dati per i dipendenti in partenza può includere il download di file da SharePoint Online, la copia di file su dispositivi portatili come unità USB, la stampa di file e la copia dei dati in servizi di archiviazione e messaggistica cloud personali vicino alle dimissioni di lavoro e date di fine. Questo modello privilegia gli indicatori di rischio relativi a queste attività e la correlazione con lo stato occupazionale dei dipendenti.

>[!IMPORTANT]
>Quando si utilizza questo modello, è necessario configurare un connettore Microsoft 365 HR per importare periodicamente le informazioni sulle dimissioni e la data di fine per i dipendenti dell'organizzazione. Per informazioni dettagliate su come configurare il connettore Microsoft 365 HR per l'organizzazione, vedere l'argomento [Import Data with the HR Connector](import-hr-data.md) .

### <a name="data-leaks"></a>Perdite di dati

La protezione dei dati e la prevenzione della perdita di dati è una sfida costante per la maggior parte delle organizzazioni, in particolare con la rapida crescita dei nuovi dati creati da dipendenti, dispositivi e servizi. I dipendenti sono autorizzati a creare, archiviare e condividere informazioni tra i servizi e i dispositivi che rendono la gestione delle perdite di dati sempre più complesse e difficili. Le perdite di dati possono includere la sovracondivisione accidentale di informazioni all'esterno dell'organizzazione o il furto di dati con intenti dolosi. Questo modello determina la priorità del rilevamento in tempo reale dei download di dati di SharePoint online sospetti, la condivisione di file e cartelle, la copia di file su dispositivi portatili, come unità USB, la stampa di file e la copia dei dati in servizi di archiviazione e messaggistica cloud personali.

>[!IMPORTANT]
>Quando si utilizza questo modello, è necessario configurare almeno un criterio di prevenzione della perdita di dati (DLP) per definire le informazioni riservate nell'organizzazione. Per informazioni dettagliate su come configurare i criteri DLP per la propria organizzazione, vedere l'argomento [creare, testare e ottimizzare un criterio DLP](create-test-tune-dlp-policy.md) .

### <a name="offensive-language-in-email"></a>Lingua offensiva nel messaggio di posta elettronica

Il rilevamento e l'esecuzione di operazioni per impedire comportamenti offensivi e abusivi sono una componente fondamentale della prevenzione dei rischi. I classificatori di lingua offensiva incorporati in Microsoft 365 possono analizzare i messaggi di posta elettronica inviati dalle cassette postali di Exchange Online nell'organizzazione per diversi tipi di problemi di conformità. Questi classificatori utilizzano una combinazione di intelligenza artificiale e parole chiave per identificare la lingua nella posta elettronica che potrebbe violare i criteri di anti-molestia. Utilizzare questo modello per creare rapidamente un criterio che utilizza questi classificatori per rilevare automaticamente il contenuto del messaggio di posta elettronica che può essere considerato abusivo o offensivo. Insider Risk Management utilizza classificatori che analizzano i messaggi di posta elettronica inviati per i termini e i sentimenti di lingua inglese per il linguaggio offensivo.

## <a name="policy-settings"></a>Impostazioni dei criteri

Le impostazioni dei rischi Insider si applicano a tutti i criteri di gestione dei rischi Insider, indipendentemente dal modello scelto quando si crea un criterio. Le impostazioni vengono configurate utilizzando il controllo **Insider Risk Settings* posizionato all'inizio di tutte le schede di gestione dei rischi Insider. Queste impostazioni controllano la privacy, gli indicatori, le finestre di monitoraggio e i rilevamenti intelligenti.

### <a name="privacy"></a>Privacy

La protezione della privacy degli utenti che dispongono di corrispondenze di criteri è importante e può contribuire a promuovere l'oggettività nelle analisi dei dati e nelle recensioni degli analizzatori dei rischi Insider Per gli utenti con corrispondenze di criteri di rischio Insider, è possibile scegliere una delle seguenti impostazioni:

- **Mostrare le versioni di anonimi dei**nomi utente: i denominati degli utenti sono anonimi per impedire agli amministratori, ai ricercatori di dati e ai revisori di vedere gli utenti associati agli avvisi dei criteri. Ad esempio, un utente ' Grace Taylor ' verrebbe visualizzato con un psuedonym randomizzato come ' AnonIS8-988' in tutte le aree dell'esperienza di gestione dei rischi Insider. Se si sceglie questa impostazione, anonimizza tutti gli utenti con le corrispondenze di criteri correnti e precedenti e si applica a tutti i criteri. Le informazioni sui profili utente nell'avviso del rischio Insider e nei dettagli del caso non saranno disponibili quando si sceglie questa opzione. Tuttavia, i nomi utente vengono visualizzati quando si aggiungono nuovi utenti ai criteri esistenti o quando si assegnano gli utenti ai nuovi criteri. Se si sceglie di disattivare questa impostazione, i nomi utente verranno visualizzati per tutti gli utenti che hanno corrispondenze di criteri correnti o precedenti.
- Non vengono visualizzate le **versioni di anonimi dei nomi utente**: i nomi utente vengono visualizzati per tutte le corrispondenze di criteri correnti e precedenti per gli avvisi e i casi. Le informazioni sui profili utente, ovvero il nome, il titolo, l'alias e l'organizzazione o il reparto, vengono visualizzate per tutti gli avvisi e i casi di gestione dei rischi Insider.

### <a name="indicators"></a>Indicatori

I modelli di criteri per i rischi Insider definiscono il tipo di attività di rischio che si desidera rilevare ed esaminare. Ogni modello di criteri si basa su indicatori specifici che corrispondono a particolari attività a rischio e gli avvisi vengono attivati dai criteri quando gli utenti eseguono attività relative a tali indicatori. In alcuni casi, è possibile limitare gli indicatori applicati ai criteri di rischio Insider nell'organizzazione. È possibile disattivare gli indicatori per aree specifiche disattivando da tutti i criteri di rischio Insider.

Per definire gli indicatori abilitati in tutti i criteri, passare a > **indicatori** **delle impostazioni dei rischi Insider**e selezionare uno o più indicatori. Gli indicatori selezionati nella pagina impostazioni **indicatori** non possono essere configurati singolarmente quando si crea o si modifica un criterio di rischio Insider nella procedura guidata dei criteri.

>[!IMPORTANT]
>Per ricevere gli avvisi per le attività a rischio definite nei criteri, è necessario selezionare uno o più indicatori prima di configurare un criterio di rischio Insider.

### <a name="policy-timeframes"></a>Intervalli di tempo per i criteri

Gli intervalli di tempo dei criteri consentono di definire i periodi di revisione precedenti e futuri che vengono attivati dopo le corrispondenze dei criteri in base a eventi e attività per i modelli di criteri di gestione del rischio Insider. A seconda del modello di criteri scelto, sono disponibili i seguenti tempi di criteri:

- **Finestra di attivazione**: disponibile per tutti i modelli di criteri, la *finestra di attivazione* è il numero definito di giorni in cui la finestra viene attivata **dopo** un evento di trigger. La finestra viene attivata da 1 a 30 giorni dopo che si è verificato un evento di attivazione per qualsiasi utente assegnato al criterio. Ad esempio, è stato configurato un criterio di gestione dei rischi Insider e impostare la *finestra di attivazione* su 30 giorni. Sono passati diversi mesi da quando è stato configurato il criterio e si verifica un evento di attivazione per uno degli utenti inclusi nel criterio. L'evento triggering attiva la *finestra di attivazione* e il criterio è attivo per l'utente per 30 giorni dopo l'evento triggering.
- **Rilevamento attività precedenti**: disponibile per tutti i modelli di criteri, il *rilevamento delle attività precedenti* è il numero definito di giorni in cui la finestra viene attivata **prima** di un evento di attivazione. La finestra viene attivata da 0 a 180 giorni prima che si verifichi un evento di attivazione per qualsiasi utente assegnato al criterio. Ad esempio, è stato configurato un criterio di gestione dei rischi Insider e il *rilevamento delle attività precedenti* è stato impostato su 90 giorni. Sono passati diversi mesi da quando è stato configurato il criterio e si verifica un evento di attivazione per uno degli utenti inclusi nel criterio. L'evento triggering attiva il *rilevamento delle attività precedenti* e il criterio raccoglie le attività storiche per quell'utente per 90 giorni prima dell'evento triggering.

### <a name="intelligent-detections"></a>Rilevamenti intelligenti

Le impostazioni di rilevamento intelligente consentono di affinare la modalità di elaborazione del rilevamento delle attività rischiose per gli avvisi. In alcuni casi, potrebbe essere necessario definire i tipi di file da ignorare o si desidera applicare un livello di rilevamento per i file che consentono di definire una barra minima per gli avvisi. Quando si utilizzano criteri di linguaggio offensivi, potrebbe essere necessario aumentare o diminuire la sensibilità di rilevamento per controllare la quantità di corrispondenze di criteri segnalate. Utilizzare queste impostazioni per controllare le esclusioni di tipi di file, i limiti del volume dei file e la sensibilità di rilevamento di lingua offensiva.

#### <a name="anomaly-detections"></a>Rilevamenti di anomalia

I rilevamenti anomali includono le impostazioni per le esclusioni dei tipi di file e i limiti del volume file.

- **Esclusioni**dei tipi di file: per escludere tipi di file specifici da tutti i criteri di gestione dei rischi Insider, immettere le estensioni del tipo di file separate da virgole. Ad esempio, per escludere determinati tipi di file musicali dalle corrispondenze di criteri, è possibile immettere *AAC, MP3, WAV, WMA* nel campo **esclusioni tipo di file** . I file con queste estensioni verrebbero ignorati da tutti i criteri di gestione dei rischi Insider.
- **Limite del volume dei file**: per definire un livello di file minimo prima che vengano segnalati avvisi di attività nei criteri di rischio Insider, immettere il numero di file. Ad esempio, è necessario immettere '10 ' se non si desidera generare avvisi di rischio Insider quando un utente Scarica 10 file o meno, anche se i criteri considerati sono un'anomalia.

#### <a name="offensive-language-detections"></a>Rilevamenti di lingua offensiva

Per modificare la sensibilità del classificatore dei linguaggi offensivi per i criteri che utilizzano la *lingua offensiva nel modello di posta elettronica* , scegliere una delle seguenti impostazioni:

- **Low**: il livello di sensibilità più basso con l'intervallo più ampio per il rilevamento del linguaggio offensivo e del sentimento. La probabilità di falsi positivi per la corrispondenza di lingua offensiva è elevata.
- **Medium**: livello di sensibilità medio-livello con un intervallo bilanciato per il rilevamento del linguaggio offensivo e del sentimento. La probabilità di falsi positivi per la corrispondenza dei linguaggi offensivi è media.
- **High**: il livello di sensibilità più alto con un intervallo ristretto per il rilevamento del linguaggio offensivo e del sentimento. La probabilità di falsi positivi per la corrispondenza di lingua offensiva è bassa.

## <a name="create-a-new-policy"></a>Creare un nuovo criterio

Per creare un nuovo criterio di gestione dei rischi Insider, è possibile utilizzare la creazione guidata criteri in soluzione di **gestione dei rischi Insider** nel centro conformità Microsoft 365.

Completare la procedura seguente per creare un nuovo criterio:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **criteri** .
2. Selezionare **create Policy** per aprire la procedura guidata per i criteri
3. Nel **nome dei criteri e scegliere una pagina modello** , completare i seguenti campi:
    - **Nome (obbligatorio)**: immettere un nome descrittivo per il criterio
    - **Description (facoltativo)**: immettere una descrizione per il criterio.
    - **Scegliere il modello di criteri (obbligatorio)**: selezionare uno dei [modelli di criteri](insider-risk-management-policies.md#policy-templates) per definire i tipi di indicatori di rischio sono monitorati dal criterio.

    >[!IMPORTANT]
    >Se si seleziona il modello per le *perdite di dati* , sarà necessario configurare almeno un criterio DLP che verrà assegnato in un secondo momento nella procedura guidata. Se si seleziona il modello di *furto dei dati* per i dipendenti in partenza, è necessario configurare il connettore HR per utilizzare le funzionalità di rilevamento completo del segnale del modello di criteri.

4. Fare clic su **Avanti** per continuare.
5. Nella pagina Selezione **utenti e gruppi** selezionare Seleziona **utenti o gruppi** per definire quali utenti sono inclusi nel criterio o seleziona **tutti gli utenti e i gruppi abilitati alla posta elettronica** . Fare clic su **Avanti** per continuare.
6. Nella pagina **specificare il contenuto di cui assegnare la priorità (facoltativo)** , è possibile assegnare punteggi di rischio superiori all'attività rilevata in base alla posizione in cui si trova il contenuto correlato, quali informazioni riservate sono incluse e quali etichette di riservatezza vengono applicate:
    - Siti di SharePoint: selezionare **scegliere i siti di SharePoint** e selezionare le organizzazioni di SharePoint a cui si desidera assegnare la priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - Tipo di informazioni riservate: selezionare **Scegli tipi di informazioni riservate** e selezionare i tipi di sensibilità che si desidera definire come prioritari. Ad esempio, *"numero di conto corrente bancario statunitense"* e *"numero di carta di credito"*.
    - Etichette di riservatezza: selezionare **Scegli etichette sensibili** e selezionare le etichette che si desidera definire come prioritarie. Ad esempio, *"confidenziale"* e *"segreto"*.
7. Fare clic su **Avanti** per continuare.
8. Nella pagina **indicatori di avviso** , verranno visualizzati gli indicatori definiti nella pagina > **indicatori** **impostazioni di rischio Insider**. Se all'inizio della procedura guidata è stato selezionato il modello per le *perdite di dati* , è necessario selezionare un criterio DLP dall'elenco a discesa dei **criteri DLP** .
9. Nella pagina **selezione finestra di monitoraggio** , vengono visualizzate le [condizioni della finestra di monitoraggio](insider-risk-management-policies.md#policy-timeframes) per i criteri configurati in impostazioni di rischio Insider. Se è stato selezionato il modello dei criteri per il *furto dei dati* per i dipendenti in uscita, è possibile selezionare la casella di *controllo Controlla la terminazione del post attività* per rilevare l'attività dopo la data di fine importata dal connettore Microsoft 365 HR.
10. Fare clic su **Avanti** per continuare.
11. Nella pagina **Revisione** rivedere le impostazioni selezionate per il criterio. Selezionare **modifica** per modificare i valori dei criteri o selezionare **Invia** per creare e attivare il criterio.

## <a name="update-a-policy"></a>Aggiornare un criterio

Per aggiornare un criterio di gestione dei rischi Insider esistente, è possibile utilizzare la procedura guidata criteri nella soluzione di **gestione dei rischi Insider** nel centro conformità Microsoft 365.

Completare la procedura seguente per gestire un criterio esistente:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **criteri** .
2. Nel dashboard dei criteri selezionare il criterio che si desidera gestire.
3. Nella pagina dei dettagli del criterio, selezionare **modifica criterio**
4. Nella creazione guidata criteri non è possibile modificare i campi seguenti:
    - **Nome**: nome descrittivo per il criterio
    - **Selezionare PlayBook**: il modello utilizzato per definire i tipi di indicatori di rischio monitorati dal criterio.
5. Immettere una nuova descrizione per il criterio nel campo **Descrizione** . Fare clic su **Avanti** per continuare.
6. Nella pagina Selezione **utenti e gruppi** selezionare Seleziona **utenti o gruppi** per definire quali utenti sono inclusi nel criterio o seleziona **tutti gli utenti e i gruppi abilitati alla posta elettronica** . Fare clic su **Avanti** per continuare
7. Nella pagina **specificare il contenuto da assegnare in modo prioritario (facoltativo)** aggiornare le origini per assegnare priorità alle attività degli utenti a rischio:
    - Siti di SharePoint: selezionare **scegliere i siti di SharePoint** e selezionare le organizzazioni di SharePoint a cui si desidera assegnare la priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - Tipo di informazioni riservate: selezionare **Scegli tipi di informazioni riservate** e selezionare i tipi di sensibilità che si desidera definire come prioritari. Ad esempio, *"numero di conto corrente bancario statunitense"* e *"numero di carta di credito"*.
    - Etichette di riservatezza: selezionare **Scegli etichette sensibili** e selezionare le etichette che si desidera definire come prioritarie. Ad esempio, *"confidenziale"* e *"segreto"*.
8. Fare clic su **Avanti** per continuare.
9. Nella pagina **indicatori di avviso** , verranno visualizzati gli indicatori definiti nella pagina > **indicatori** **impostazioni di rischio Insider**. Se all'inizio della procedura guidata è stato selezionato il modello per le *perdite di dati* , è necessario selezionare un criterio DLP dall'elenco a discesa dei **criteri DLP** .
10. Nella pagina **selezione finestra di monitoraggio** , vengono visualizzate le [condizioni della finestra di monitoraggio](insider-risk-management-policies.md#policy-timeframes) per i criteri configurati in impostazioni di rischio Insider. Se è stato selezionato il modello dei criteri per il *furto dei dati* per i dipendenti in uscita, è possibile selezionare la casella di *controllo Controlla la terminazione del post attività* per rilevare l'attività dopo la data di fine importata dal connettore Microsoft 365 HR.
11. Nella pagina **Revisione** rivedere le impostazioni selezionate per il criterio. Selezionare **modifica** per modificare i valori dei criteri o selezionare **Invia** per aggiornare e attivare le modifiche apportate al criterio.

## <a name="delete-a-policy"></a>Eliminare un criterio

>[!NOTE]
>L'eliminazione di un criterio non comporta l'eliminazione di avvisi attivi o archiviati generati dal criterio.

Per eliminare un criterio di gestione dei rischi Insider esistente, completare i passaggi seguenti:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **criteri** .
2. Nel dashboard dei criteri selezionare il criterio che si desidera gestire.
3. Selezionare **Delete** sulla barra degli strumenti del dashboard.
4. Nella finestra di dialogo **Elimina** selezionare **Sì** per eliminare il criterio oppure fare clic su **Annulla** per chiudere la finestra di dialogo.
