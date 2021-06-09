---
title: Creare un avviso di blocco legale
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
description: Usa lo strumento Comunicazioni in un caso Advanced eDiscovery per inviare, raccogliere e tenere traccia delle notifiche di blocco legale.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: df1b2d962e83110c62ccac871f669bbc0d3bfe02
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840561"
---
# <a name="create-a-legal-hold-notice"></a>Creare un avviso di blocco legale

Utilizzando Advanced eDiscovery di archiviazione, le organizzazioni possono gestire il flusso di lavoro per comunicare con i depositario. Tramite lo strumento di comunicazione, i team legali possono inviare, raccogliere e tenere traccia sistematicamente delle notifiche di blocco legale. Il processo di creazione flessibile consente inoltre ai team di personalizzare il flusso di lavoro delle notifiche di blocco e il contenuto delle notifiche inviate ai custodi.

![Pagina Comunicazioni](../media/CommunicationPage.PNG)

L'articolo descrive i passaggi del flusso di lavoro delle notifiche di blocco.

## <a name="step-1-specify-communication-details"></a>Passaggio 1: Specificare i dettagli di comunicazione

Il primo passaggio consiste nel specificare i dettagli appropriati per gli avvisi di blocco legale o altre comunicazioni di custodia.

![Name Communication Page](../media/NameCommunication.PNG)

1. Nel Centro sicurezza & conformità passare a **eDiscovery > Advanced eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione.

2. Selezionare un caso, fare clic **sulla scheda** Comunicazioni e quindi su **Nuova comunicazione.**

3. Nella pagina **Comunicazione nome** specificare i dettagli di comunicazione seguenti (obbligatorio).

    - **Nome**: questo è il nome della comunicazione.

    - **Responsabile dell'emissione:** nell'elenco a discesa viene visualizzato un elenco di membri del caso. Per ulteriori informazioni su come aggiungere nuovi membri a un caso, vedere [Create an Advanced eDiscovery case](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case). Ogni avviso inviato ai custodi verrà inviato per conto del responsabile emittente specificato.

> [!NOTE]
> Il responsabile emittente deve disporre di una **cassetta postale attiva** da visualizzare nell'elenco a discesa Responsabile emittente


4. Fare clic su **Avanti**.

## <a name="step-2-define-the-portal-content"></a>Passaggio 2: Definire il contenuto del portale

Successivamente, è possibile creare e aggiungere il contenuto dell'avviso di blocco. Nella pagina **Definisci contenuto portale** della procedura guidata **Crea** comunicazione specificare il contenuto dell'avviso di blocco. Questo contenuto verrà aggiunto automaticamente agli avvisi di rilascio, riemissione, promemoria e escalation. Inoltre, questo contenuto verrà visualizzato nel Portale di conformità del responsabile. 

![Pagina contenuto portale](../media/PortalContent.PNG)

Per creare il contenuto del portale:

1. Digitare (o tagliare e incollare da un altro documento) l'avviso di blocco nella casella di testo per il contenuto del portale. 

2. Inserire variabili di unione nell'avviso per personalizzare l'avviso e condividere il Portale di conformità del responsabile.

3. Fare clic su **Avanti**.

  >[!Tip]
  >Per ulteriori informazioni su come personalizzare il contenuto e il formato del contenuto del portale, vedere [Use the Communications Editor.](using-communications-editor.md)

## <a name="step-3-set-the-required-notifications"></a>Passaggio 3: Impostare le notifiche necessarie

Dopo aver definito il contenuto dell'avviso di blocco, è possibile configurare i flussi di lavoro per l'invio e la gestione del processo di notifica. Le notifiche sono messaggi di posta elettronica inviati per notificare e seguire i custodi. Ogni responsabile aggiunto alla comunicazione riceverà la stessa notifica. 

Per configurare e inviare un avviso di blocco, devi includere le notifiche di rilascio, rilascio e rilascio.

### <a name="issuance-notification"></a>Notifica di rilascio 

Dopo la creazione della comunicazione, la **notifica** di rilascio viene avviata dal responsabile del rilascio specificato. La notifica di rilascio è la prima comunicazione inviata al depositario per informarli degli obblighi di conservazione. 

Per creare una notifica di rilascio:

1. Nel riquadro **Rilascio** fare clic su **Modifica.**

2. Se necessario, aggiungere altri membri del caso o personale ai **campi Cc** **e Ccn.** Per aggiungere più utenti a questi campi, separare gli indirizzi di posta elettronica con un punto e virgola.

3. Specificare **l'oggetto** per l'avviso (obbligatorio).

4. Specificare il contenuto o istruzioni aggiuntive che si desidera fornire al responsabile (obbligatorio). Il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di rilascio. 

5. Fare clic su **Salva**.

### <a name="re-issuance-notification"></a>Re-Issuance notifica

Con l'avanzamento del caso, i custodi potrebbero essere tenuti a conservare dati aggiuntivi o meno di quelli precedentemente richiesti. Dopo l'aggiornamento del contenuto del portale, viene inviata la notifica di riemissione e i custodi vengono avvisati di eventuali modifiche agli obblighi di conservazione.

Per creare una notifica di riemissione:

1. Nel riquadro **Riemissione** fare clic su **Modifica.**

2. Se necessario, aggiungere altri membri del caso o personale ai **campi Cc** **e Ccn.** Per aggiungere più utenti a questi campi, separare gli indirizzi di posta elettronica con un punto e virgola.

3. Specificare **l'oggetto** per l'avviso (obbligatorio).

4. Specificare il contenuto o istruzioni aggiuntive che si desidera fornire al responsabile (obbligatorio). Il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di riemissione.

5. Fare clic su **Salva**.

> [!NOTE]
> Se il contenuto del portale  viene modificato (nella pagina Definisci contenuto portale della procedura guidata Modifica comunicazione), la notifica di riemissione verrà inviata automaticamente a tutti i custodi assegnati alla notifica.  Dopo l'invio della notifica, ai custodi verrà chiesto di confermare nuovamente l'avviso di blocco. Se sono stati impostati flussi di lavoro di promemoria o escalation, anche questi verranno ripartire. Per ulteriori informazioni sugli altri eventi di gestione dei casi che attivano le comunicazioni, vedere [Eventi che attivano le notifiche.](#events-that-trigger-notifications)

### <a name="release-notification"></a>Notifica di rilascio

Una volta risolta una questione o se un responsabile non è più soggetto a conservare il contenuto, è possibile rilasciare il responsabile da un caso. Se il responsabile è stato precedentemente emesso un avviso di blocco, la notifica di rilascio può essere usata per avvisare i custodi che sono stati rilasciati dall'obbligo.

Per creare una notifica di rilascio: 

1. Nel riquadro **Rilascia** fai clic su **Modifica.**

2. Se necessario, aggiungere altri membri del caso o personale ai **campi Cc** **e Ccn.** Per aggiungere più utenti a questi campi, separare gli indirizzi di posta elettronica con un punto e virgola.

3. Specificare **l'oggetto** per l'avviso (obbligatorio).

4. Specificare il contenuto o istruzioni aggiuntive che si desidera fornire al responsabile (obbligatorio).

5. Fare **clic su** Salva e andare al passaggio successivo.

## <a name="optional-step-4-set-the-optional-notifications"></a>(Facoltativo) Passaggio 4: Impostare le notifiche facoltative

Facoltativamente, è possibile semplificare il flusso di lavoro per seguire i responsabili che non rispondono creando e pianificando notifiche di promemoria e escalation automatizzate.

![Pagina Promemoria/Escalation](../media/ReminderEscalations.PNG)

### <a name="reminders"></a>Promemoria

Dopo aver inviato una notifica di blocco, è possibile seguire i responsabili che non rispondono definendo un flusso di lavoro promemoria.

Per pianificare i promemoria:

1. Nel riquadro **Promemoria** fare clic su **Modifica.**

2. Abilita il **flusso di lavoro** Promemoria attivando l'interruttore **Stato** (obbligatorio).

3. Specificare **l'intervallo promemoria (in giorni)** (obbligatorio). Questo è il numero di giorni di attesa prima di inviare le notifiche di promemoria di primo e completamento. Ad esempio, se si imposta l'intervallo del promemoria su sette giorni, il primo promemoria verrà inviato sette giorni dopo l'emissione iniziale della notifica di blocco. Tutti i promemoria successivi verranno inviati ogni sette giorni.

4. Specificare il **numero di promemoria** (obbligatorio). Questo campo specifica il numero di promemoria da inviare ai responsabili che non rispondono. Ad esempio, se si imposta il numero di promemoria su 3, un responsabile riceverà un massimo di tre promemoria. Dopo che un responsabile ha riconosciuto la notifica di blocco, i promemoria non verranno più inviati a tale utente.

5. Specificare **l'oggetto** per l'avviso (obbligatorio). 

6. Specificare il contenuto o istruzioni aggiuntive che si desidera fornire al responsabile (obbligatorio). Il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di promemoria.

7. Fare **clic su** Salva e andare al passaggio successivo.

### <a name="escalations"></a>Escalation

In alcuni casi, potrebbero essere necessari altri modi per seguire i responsabili che non rispondono. Se un responsabile non riconosce una notifica di blocco dopo aver ricevuto il numero specificato di promemoria, il team legale può specificare un flusso di lavoro per inviare automaticamente una notifica di escalation al responsabile e al responsabile.

Per pianificare le escalation:

1. Nel riquadro **Escalation** fare clic su **Modifica.**

2. Abilita il **flusso di lavoro Escalation** attivando l'interruttore **Stato.**

3. Specificare **l'intervallo di escalation (in giorni)** (obbligatorio).

4. Specificare il **numero di escalation** (obbligatorio). Questo campo specifica il numero di escalation da inviare ai responsabili che non rispondono. Se ad esempio si imposta il numero di escalation su 3, al responsabile e al responsabile verrà inviato un avviso di escalation per un massimo di tre volte. Dopo che un responsabile ha riconosciuto la notifica di blocco, le escalation non verranno più inviate.

5. Specificare **l'oggetto** per l'avviso (obbligatorio). 

6. Specificare il contenuto o istruzioni aggiuntive che si desidera fornire al responsabile (obbligatorio). Il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di escalation.

7. Fare **clic su** Salva e andare al passaggio successivo.

## <a name="step-5-assign-custodians-to-receive-notifications"></a>Passaggio 5: Assegnare i custodi per ricevere le notifiche

Dopo aver finalizzato il contenuto per le notifiche, selezionare i custodi a cui si desidera inviare le notifiche. 

![Pagina Seleziona custodi](../media/SelectCustodians.PNG)

Per aggiungere i custodi:

1. Assegnare i custodi alla comunicazione facendo clic sulla casella di controllo accanto al nome.

    Dopo la creazione della comunicazione, il flusso di lavoro di notifica verrà applicato automaticamente ai custodi selezionati.

2. Fare **clic su** Avanti per esaminare le impostazioni e i dettagli di comunicazione.

>[!NOTE]
>Puoi aggiungere solo i custodi che sono stati aggiunti al caso e non sono stati inviati un'altra notifica all'interno del caso.

## <a name="step-6-review-settings"></a>Passaggio 6: rivedere le impostazioni

Dopo aver esaminato le impostazioni e aver fatto clic su **Invia** per completare la comunicazione, il sistema avvia automaticamente il flusso di lavoro di comunicazione inviando l'avviso di rilascio.

## <a name="events-that-trigger-notifications"></a>Eventi che attivano le notifiche

Nella tabella seguente vengono descritti gli eventi del processo di gestione dei casi che vengono attivati quando i diversi tipi di notifiche vengono inviati ai custodi.

|Tipo di comunicazione|Trigger |
|:---------|:---------|
|Avvisi di rilascio|Creazione iniziale della notifica. Puoi anche inviare di nuovo manualmente una notifica di blocco. |
|Avvisi di riemissione|Aggiornamento del contenuto del portale nella **pagina Definisci contenuto portale** della procedura guidata **Modifica** comunicazione.|
|Note sulla versione|Il responsabile viene rilasciato dal caso.|
|Promemoria|Intervallo e numero di promemoria configurati per il promemoria.|
|Escalation|Intervallo e numero di promemoria configurati per l'escalation.|
|||
