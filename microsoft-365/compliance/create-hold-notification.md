---
title: Creare un avviso per la conservazione legale
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Utilizzare lo strumento di comunicazione in un caso avanzato di eDiscovery per inviare, raccogliere e tenere presenti le notifiche di archiviazione legale.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0bcbdef1c1393ff3e7f3baf30279909ed3a663f5
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035788"
---
# <a name="create-a-legal-hold-notice"></a>Creare un avviso per la conservazione legale

Utilizzando le comunicazioni del custode di eDiscovery avanzate, le organizzazioni possono gestire il flusso di lavoro attorno alla comunicazione con i depositari. Tramite lo strumento di comunicazione, i team legali possono inviare, raccogliere e tenere presenti sistematicamente le notifiche per la conservazione legale. Il processo di creazione flessibile consente inoltre ai team di personalizzare il flusso di lavoro di notifica di archiviazione e il contenuto nelle notifiche inviate ai depositari. 

![Pagina comunicazioni](../media/CommunicationPage.PNG)

In questo articolo vengono illustrati i passaggi del flusso di lavoro di notifica di blocco.

## <a name="step-1-specify-communication-details"></a>Passaggio 1: specificare i dettagli della comunicazione

Il primo passaggio consiste nel specificare i dettagli adeguati per le notifiche di archiviazione legale o altre comunicazioni del custode.

![Pagina di comunicazione del nome](../media/NameCommunication.PNG)

1. Nel centro sicurezza & conformità, accedere a **eDiscovery > Advanced eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione.

2. Selezionare un caso, fare clic sulla scheda **comunicazioni** , quindi fare clic su **nuova comunicazione**.

3. Nella pagina **nome comunicazione** specificare i seguenti dettagli di comunicazione (necessari).

    - **Nome**: questo è il nome della comunicazione.

    - **Responsabile del rilascio**: nell'elenco a discesa viene visualizzato un elenco di membri del caso. Ogni avviso inviato ai depositari verrà inviato per conto del responsabile del rilascio specificato.

4. Fare clic su **Avanti**.

## <a name="step-2-define-the-portal-content"></a>Passaggio 2: definire il contenuto del portale

Successivamente, è possibile creare e aggiungere il contenuto dell'avviso di blocco. Nella pagina **Definisci contenuto portale** della creazione guidata **comunicazione** , specificare il contenuto della notifica di blocco. Questo contenuto verrà accodato automaticamente agli avvisi di emissione, riemissione, sollecito e escalation. Inoltre, questo contenuto verrà visualizzato nel portale di conformità del custode. 

![Pagina contenuto portale](../media/PortalContent.PNG)

Per creare il contenuto del portale:

1. Digitare (o tagliare e incollare da un altro documento) la notifica di blocco nella casella di testo per il contenuto del portale. 

2. Inserire le variabili di Unione nell'avviso per personalizzare l'avviso e condividere il portale di conformità dei depositari.

3. Fare clic su **Avanti**.

  >[!Tip]
  >Per ulteriori informazioni su come personalizzare il contenuto e il formato del contenuto del portale, vedere [use the Communications editor](using-communications-editor.md).

## <a name="step-3-set-the-required-notifications"></a>Passaggio 3: impostare le notifiche obbligatorie

Dopo aver definito il contenuto della notifica di blocco, è possibile configurare i flussi di lavoro per l'invio e la gestione del processo di notifica. Le notifiche sono messaggi di posta elettronica inviati per la notifica e il follow-up con i depositari. Ogni custode aggiunto alla comunicazione riceverà la stessa notifica. 

Per impostare e inviare una notifica di blocco, è necessario includere le notifiche di emissione, riemissione e rilascio.

### <a name="issuance-notification"></a>Notifica di rilascio 

Dopo aver creato la comunicazione, la **notifica di rilascio** viene avviata dal responsabile del rilascio specificato. La notifica di rilascio è la prima comunicazione inviata al custode per informarli dei loro obblighi di conservazione. 

Per creare una notifica di rilascio:

1. Nel riquadro **rilascio** , fare clic su **modifica**.

2. Se necessario, aggiungere ulteriori membri del caso o personale ai campi **CC** e **Ccn** . Per aggiungere più utenti a tali campi, separare gli indirizzi di posta elettronica con un punto e virgola.

3. Specificare l' **oggetto** per l'avviso (obbligatorio).

4. Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio). Il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di pubblicazione. 

5. Fare clic su **Salva**.

### <a name="re-issuance-notification"></a>Notifica di riemissione

Quando il caso progredisce, potrebbe essere necessario che i depositari possano conservare dati aggiuntivi o meno rispetto a quelli precedentemente istruiti. Dopo aver aggiornato il contenuto del portale, viene inviata la notifica di riemissione e vengono avvisati i depositari delle modifiche apportate ai propri obblighi di conservazione.

Per creare una notifica di riemissione:

1. Nel riquadro **ristampa** fare clic su **modifica**.

2. Se necessario, aggiungere ulteriori membri del caso o personale ai campi **CC** e **Ccn** . Per aggiungere più utenti a tali campi, separare gli indirizzi di posta elettronica con un punto e virgola.

3. Specificare l' **oggetto** per l'avviso (obbligatorio).

4. Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio). Il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di riemissione.

5. Fare clic su **Salva**.

> [!NOTE]
> Se il contenuto del portale viene modificato (nella pagina **definire il contenuto del portale** nella procedura guidata di modifica della **comunicazione** ), la notifica di riemissione verrà inviata automaticamente a tutti i depositari assegnati alla notifica. Dopo che la notifica viene inviata, ai depositari verrà chiesto di riconfermare il proprio avviso di esenzione. Se sono stati configurati eventuali flussi di lavoro di promemoria o escalation, anche questi verranno riavviati. Per ulteriori informazioni su ciò che gli altri eventi di gestione dei casi attivano le comunicazioni, vedere [eventi che attivano le notifiche](#events-that-trigger-notifications).

### <a name="release-notification"></a>Notifica di rilascio

Dopo aver risolto un problema o se un custode non è più soggetto alla conservazione del contenuto, è possibile rilasciare il custode da un caso. Se il custode ha precedentemente emesso un avviso di esenzione, la notifica di rilascio può essere utilizzata per avvisare i depositari che sono stati rilasciati dall'obbligo.

Per creare una notifica di rilascio: 

1. Nella sezione **rilascia** fare clic su **modifica**.

2. Se necessario, aggiungere ulteriori membri del caso o personale ai campi **CC** e **Ccn** . Per aggiungere più utenti a tali campi, separare gli indirizzi di posta elettronica con un punto e virgola.

3. Specificare l' **oggetto** per l'avviso (obbligatorio).

4. Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio).

5. Fare clic su **Salva** e passare al passaggio successivo.

## <a name="optional-step-4-set-the-optional-notifications"></a>Optional Passaggio 4: impostare le notifiche facoltative

Facoltativamente, è possibile semplificare il flusso di lavoro per la creazione e la pianificazione delle notifiche di promemoria automatica e di escalation.

![Pagina promemoria/escalation](../media/ReminderEscalations.PNG)

### <a name="reminders"></a>Promemoria

Dopo aver inviato una notifica di blocco, è possibile eseguire il follow-up con i depositari non rispondenti definendo un flusso di lavoro di sollecito.

Per pianificare i promemoria:

1. Nel riquadro **promemoria** fare clic su **modifica**.

2. Abilitare il flusso di lavoro di **sollecito** attivando l'interruttore di **stato** (obbligatorio).

3. Specificare l' **intervallo di sollecito (in giorni)** (obbligatorio). Questo è il numero di giorni di attesa prima dell'invio delle notifiche del primo e del promemoria di follow-up. Se ad esempio si imposta l'intervallo di sollecito su sette giorni, il primo sollecito verrebbe inviato sette giorni dopo l'invio iniziale della notifica di blocco. Tutti i promemoria successivi vengono inviati anche ogni sette giorni.

4. Specificare il **numero di promemoria** (obbligatorio). Questo campo consente di specificare il numero di promemoria da inviare ai depositari non rispondenti. Ad esempio, se si imposta il numero di promemoria su 3, un custode riceverà un massimo di tre promemoria. Dopo che un custode riconosce la notifica di blocco, i promemoria non verranno più inviati a quell'utente.

5. Specificare l' **oggetto** per l'avviso (obbligatorio). 

6. Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio). Il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine della notifica di sollecito.

7. Fare clic su **Salva** e passare al passaggio successivo.

### <a name="escalations"></a>Escalation

In alcuni casi, potrebbero essere necessari ulteriori modi per eseguire il follow-up con i depositari non rispondenti. Se un custode non riconosce una notifica di blocco dopo aver ricevuto il numero specificato di promemoria, il team legale può specificare un flusso di lavoro per inviare automaticamente un avviso di escalation al custode e al relativo responsabile.

Per pianificare le escalation:

1. Nel riquadro **escalation** fare clic su **modifica**.

2. Abilitare il flusso di lavoro per l' **escalation** attivando l'interruttore di **stato** .

3. Specificare l' **intervallo di escalation (in giorni)** (obbligatorio).

4. Specificare il **numero di escalation** (obbligatorio). Questo campo consente di specificare il numero di escalation da inviare ai depositari non rispondenti. Ad esempio, se si imposta il numero di escalation su 3, un avviso di escalation verrebbe inviato al custode e al relativo Manager al massimo tre volte. Dopo che un custode riconosce la notifica di blocco, le escalation non verranno più inviate.

5. Specificare l' **oggetto** per l'avviso (obbligatorio). 

6. Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio). Il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di escalation.

7. Fare clic su **Salva** e passare al passaggio successivo.

## <a name="step-5-assign-custodians-to-receive-notifications"></a>Passaggio 5: assegnare i depositari per la ricezione delle notifiche

Dopo aver finalizzato il contenuto per le notifiche, selezionare i depositari ai quali si desidera inviare notifiche. 

![Pagina Selezione depositari](../media/SelectCustodians.PNG)

Per aggiungere i depositari:

1. Assegnare i depositari alla comunicazione facendo clic sulla casella di controllo accanto al nome.

    Dopo la creazione della comunicazione, il flusso di lavoro di notifica verrà applicato automaticamente ai depositari selezionati.

2. Fare clic su **Avanti** per esaminare le impostazioni di comunicazione e i dettagli.

>[!NOTE]
>È possibile aggiungere solo i depositari che sono stati aggiunti al caso e non sono stati inviati un'altra notifica all'interno del caso.

## <a name="step-6-review-settings"></a>Passaggio 6: rivedere le impostazioni

Dopo aver esaminato le impostazioni e fare clic su **Invia** per completare la comunicazione, il sistema avvierà automaticamente il flusso di lavoro di comunicazione inviando la notifica di rilascio.

## <a name="events-that-trigger-notifications"></a>Eventi che attivano le notifiche

Nella tabella seguente vengono descritti gli eventi del processo di gestione dei casi che si attivano quando i diversi tipi di notifiche vengono inviati ai depositari.

|Tipo di comunicazione|Trigger |
|:---------|:---------|
|Notifiche di emissione|La creazione iniziale della notifica. È inoltre possibile rinviare manualmente una notifica di blocco. |
|Notifiche di riemissione|Aggiornamento del contenuto del portale nella pagina **definire il contenuto del portale** nella procedura guidata **modifica comunicazione** .|
|Notifiche di rilascio|Il custode viene rilasciato dal caso.|
|Promemoria|L'intervallo e il numero di promemoria configurati per il promemoria.|
|Escalation|L'intervallo e il numero di promemoria configurati per l'escalation.|
|||
