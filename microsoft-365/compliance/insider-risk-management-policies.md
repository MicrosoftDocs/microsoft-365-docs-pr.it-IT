---
title: Criteri di gestione dei rischi Insider (Preview)
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
ms.openlocfilehash: 161118bb8ff8a5c79ee507d329e20bad1421d8fd
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41590617"
---
# <a name="insider-risk-management-policies-preview"></a>Criteri di gestione dei rischi Insider (Preview)

I criteri di gestione dei rischi Insider determinano quali dipendenti sono in ambito e quali tipi di indicatori di rischio sono configurati per gli avvisi. È possibile creare rapidamente un criterio che si applica a tutti gli utenti dell'organizzazione oppure definire singoli utenti o gruppi per la gestione in un criterio. I criteri supportano le priorità del contenuto per concentrare le condizioni dei criteri su più o specifici team Microsoft, siti di SharePoint, tipi di sensibilità dei dati e etichette dati. Utilizzando i modelli, sono inclusi indicatori di rischio specifici e la quantità di peso assegnato all'interno di un criterio, determinando in modo efficace il peso di ogni trigger di avviso nel criterio. Criteri le finestre consentono di definire la tempistica per applicare il criterio alle attività di avviso e vengono utilizzate per determinare la durata del criterio, una volta attivato. Il limite massimo di criteri è costituito da cinque criteri attivi contemporaneamente. Tuttavia, è possibile configurare criteri aggiuntivi e attivare e disattivare i criteri in base alle esigenze.

## <a name="policy-dashboard"></a>Dashboard di criteri

Il **dashboard dei criteri** consente di visualizzare rapidamente i criteri dell'organizzazione e lo stato corrente degli avvisi associati a ogni criterio.

- **Nome criterio**: il nome assegnato al criterio nella procedura guidata per i criteri.
- **Avvisi attivi**: il numero di avvisi attivi per ogni criterio.
- **Avvisi confermati**: il numero totale di avvisi restituiti nei casi dal criterio negli ultimi 365 giorni.
- **Azioni intraprese sugli avvisi**: il numero totale di avvisi che sono stati confermati o scartati negli ultimi 365 giorni.
- **Efficacia dei criteri**: la percentuale determinata dal totale degli avvisi confermati diviso per le azioni totali eseguite sugli avvisi (ovvero la somma degli avvisi che sono stati confermati o scartati nell'ultimo anno).
- **Attivo**: lo stato del caso, ovvero *Sì* o *No*.

![Dashboard dei criteri di gestione del rischio Insider](media/insider-risk-policy-dashboard.png)

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

## <a name="monitoring-windows"></a>Monitoraggio di Windows

I criteri di monitoraggio di Windows consentono di definire periodi di tempo che attivano l'attivazione dei criteri in base a eventi e attività dei modelli di criteri di gestione del rischio Insider. A seconda del modello di criteri scelto, sono disponibili le seguenti finestre di monitoraggio:

- **TimeSpan nell'ambito**: disponibile per tutti i modelli di criteri, l'oggetto *TimeSpan nell'ambito* è il numero definito di giorni in cui la finestra viene attivata **dopo** un evento di attivazione. La finestra viene attivata da 1 a 30 giorni dopo che si è verificato un evento di attivazione per qualsiasi utente assegnato al criterio. Ad esempio, si è configurato un criterio di gestione dei rischi Insider e impostare l'intervallo di tempo *tra gli intervalli* su 30 giorni. Sono passati diversi mesi da quando è stato configurato il criterio e si verifica un evento di attivazione per uno degli utenti inclusi nel criterio. L'evento triggering attiva l'oggetto *TimeSpan nell'ambito* e il criterio è attivo per l'utente per 30 giorni dopo l'evento triggering.
- **TimeSpan storico**: disponibile per tutti i modelli di criteri, lo *storico TimeSpan* è il numero definito di giorni in cui la finestra viene attivata **prima** di un evento di attivazione. La finestra viene attivata da 0 a 180 giorni prima che si verifichi un evento di attivazione per qualsiasi utente assegnato al criterio. Ad esempio, è stato configurato un criterio di gestione dei rischi Insider e impostare lo *storico TimeSpan* su 90 giorni. Sono passati diversi mesi da quando è stato configurato il criterio e si verifica un evento di attivazione per uno degli utenti inclusi nel criterio. L'evento triggering attiva lo *storico TimeSpan* e il criterio raccoglie le attività storiche per l'utente per 90 giorni prima dell'evento triggering.
- **Finestra di terminazione futura**: questa impostazione viene visualizzata nell'anteprima pubica, ma non viene applicata a nessun criterio e verrà rimossa per la versione di produzione di questa soluzione.
- **Finestra terminazione passata**: questa impostazione viene visualizzata nell'anteprima pubica, ma non viene applicata a nessun criterio e verrà rimossa per la versione di produzione di questa soluzione.

## <a name="create-a-new-policy"></a>Creare un nuovo criterio

Per creare un nuovo criterio di gestione dei rischi Insider, è possibile utilizzare la creazione guidata criteri in soluzione di **gestione dei rischi Insider** nel centro conformità Microsoft 365.

Completare la procedura seguente per creare un nuovo criterio:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **criteri** .
2. Selezionare **create Policy** per aprire la procedura guidata per i criteri
3. Nella pagina **nuovo criterio di rischio Insider** completare i seguenti campi:
    - **Nome (obbligatorio)**: immettere un nome descrittivo per il criterio
    - **Description (facoltativo)**: immettere una descrizione per il criterio.
    - **Scegliere il modello di criteri (obbligatorio)**: selezionare uno dei [modelli di criteri](insider-risk-management-policies.md#policy-templates) per definire i tipi di indicatori di rischio sono monitorati dal criterio.

    >[!IMPORTANT]
    >Se si seleziona il modello per le *perdite di dati* , sarà necessario configurare almeno un criterio DLP che verrà assegnato in un secondo momento nella procedura guidata. Se si seleziona il modello di *furto dei dati* per i dipendenti in partenza, è necessario configurare il connettore HR per utilizzare le funzionalità di rilevamento completo del segnale del modello di criteri.

4. Fare clic su **Avanti** per continuare.
5. Nella pagina **utenti** selezionare **Aggiungi utente o gruppo** per definire quali utenti sono inclusi nel criterio oppure selezionare **tutti gli utenti e i gruppi abilitati alla posta elettronica** . Fare clic su **Avanti** per continuare.
6. Nella pagina **specificare il contenuto di cui definire la priorità (facoltativa)** , è possibile assegnare le origini a priorità per le attività degli utenti a rischio:
    - Siti di SharePoint: selezionare **Aggiungi sito di SharePoint** e selezionare le organizzazioni di SharePoint a cui si desidera assegnare la priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - Tipo di informazioni riservate: selezionare **Aggiungi tipo di informazioni riservate** e selezionare i tipi di sensibilità che si desidera impostare come priorità. Ad esempio, *"numero di conto corrente bancario statunitense"* e *"numero di carta di credito"*.
    - Etichette di riservatezza: selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette che si desidera impostare come priorità. Ad esempio, *"confidenziale"* e *"segreto"*.
7. Fare clic su **Avanti** per continuare.
8. Nella pagina **Scegli** gli indicatori di avviso verranno visualizzati gli indicatori inclusi nel modello scelto per questo criterio. Se all'inizio della procedura guidata è stato selezionato il modello per le *perdite di dati* , è necessario selezionare un criterio DLP dall'elenco a discesa dei **criteri DLP** .
9. Nella pagina **selezione finestra di monitoraggio** vengono definite le condizioni per la [finestra di monitoraggio](insider-risk-management-policies.md#monitoring-windows) per il criterio. Configurare le finestre di monitoraggio in base alle esigenze.
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
6. Nella pagina **utenti** selezionare **Aggiungi utente o gruppo** per definire quali utenti sono inclusi nel criterio oppure selezionare **tutti gli utenti e i gruppi abilitati alla posta elettronica** . Fare clic su **Avanti** per continuare
7. Nella pagina **specificare il contenuto da assegnare in modo prioritario (facoltativo)** aggiornare le origini per assegnare priorità alle attività degli utenti a rischio:
    - Siti di SharePoint: selezionare **Aggiungi sito di SharePoint** e selezionare le organizzazioni di SharePoint a cui si desidera assegnare la priorità. Ad esempio, *"group1@contoso.sharepoint.com/sites/group1"*.
    - Tipo di informazioni riservate: selezionare **Aggiungi tipo di informazioni riservate** e selezionare i tipi di sensibilità che si desidera impostare come priorità. Ad esempio, *"numero di conto corrente bancario statunitense"* e *"numero di carta di credito"*.
    - Etichette di riservatezza: selezionare **Aggiungi etichetta di riservatezza** e selezionare le etichette che si desidera impostare come priorità. Ad esempio, *"confidenziale"* e *"segreto"*.
8. Fare clic su **Avanti** per continuare.
9. Nella pagina **Scegli** gli indicatori di avviso verranno visualizzati gli indicatori inclusi nel modello scelto per questo criterio. Se all'inizio della procedura guidata è stato selezionato il modello per le *perdite di dati* , è necessario selezionare un criterio DLP dall'elenco a discesa dei **criteri DLP** .
10. Nella pagina **selezione finestra di monitoraggio** vengono definite le condizioni per la [finestra di monitoraggio](insider-risk-management-policies.md#monitoring-windows) per il criterio. Configurare le finestre di monitoraggio in base alle esigenze.
11. Nella pagina **Revisione** rivedere le impostazioni selezionate per il criterio. Selezionare **modifica** per modificare i valori dei criteri o selezionare **Invia** per aggiornare e attivare le modifiche apportate al criterio.

## <a name="delete-a-policy"></a>Eliminare un criterio

>[!NOTE]
>L'eliminazione di un criterio non comporta l'eliminazione di avvisi attivi o archiviati generati dal criterio.

Per eliminare un criterio di gestione dei rischi Insider esistente, completare i passaggi seguenti:

1. Nel [centro conformità di Microsoft 365](https://compliance.microsoft.com)accedere a **gestione dei rischi Insider** e selezionare la scheda **criteri** .
2. Nel dashboard dei criteri selezionare il criterio che si desidera gestire.
3. Selezionare **Delete** sulla barra degli strumenti del dashboard.
4. Nella finestra di dialogo **Elimina** selezionare **Sì** per eliminare il criterio oppure fare clic su **Annulla** per chiudere la finestra di dialogo.