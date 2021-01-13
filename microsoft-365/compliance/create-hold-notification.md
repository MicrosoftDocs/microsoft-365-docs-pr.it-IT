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
ms.openlocfilehash: df1b2d962e83110c62ccac871f669bbc0d3bfe02
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840561"
---
# <a name="create-a-legal-hold-notice"></a><span data-ttu-id="a3520-103">Creare un avviso per la conservazione legale</span><span class="sxs-lookup"><span data-stu-id="a3520-103">Create a legal hold notice</span></span>

<span data-ttu-id="a3520-104">Utilizzando le comunicazioni del custode di eDiscovery avanzate, le organizzazioni possono gestire il flusso di lavoro attorno alla comunicazione con i depositari.</span><span class="sxs-lookup"><span data-stu-id="a3520-104">Using Advanced eDiscovery custodian communications, organizations can manage their workflow around communicating with custodians.</span></span> <span data-ttu-id="a3520-105">Tramite lo strumento di comunicazione, i team legali possono inviare, raccogliere e tenere presenti sistematicamente le notifiche per la conservazione legale.</span><span class="sxs-lookup"><span data-stu-id="a3520-105">Through the Communications tool, legal teams can systematically send, collect, and track legal hold notifications.</span></span> <span data-ttu-id="a3520-106">Il processo di creazione flessibile consente inoltre ai team di personalizzare il flusso di lavoro di notifica di archiviazione e il contenuto nelle notifiche inviate ai depositari.</span><span class="sxs-lookup"><span data-stu-id="a3520-106">The flexible creation process also allows teams to customize the hold notification workflow and the content in the notices sent to custodians.</span></span>

![Pagina comunicazioni](../media/CommunicationPage.PNG)

<span data-ttu-id="a3520-108">In questo articolo vengono illustrati i passaggi del flusso di lavoro di notifica di blocco.</span><span class="sxs-lookup"><span data-stu-id="a3520-108">The article outlines the steps in the hold notification workflow.</span></span>

## <a name="step-1-specify-communication-details"></a><span data-ttu-id="a3520-109">Passaggio 1: specificare i dettagli della comunicazione</span><span class="sxs-lookup"><span data-stu-id="a3520-109">Step 1: Specify communication details</span></span>

<span data-ttu-id="a3520-110">Il primo passaggio consiste nel specificare i dettagli adeguati per le notifiche di archiviazione legale o altre comunicazioni del custode.</span><span class="sxs-lookup"><span data-stu-id="a3520-110">The first step is to specify the appropriate details for legal hold notices or other custodian communications.</span></span>

![Pagina di comunicazione del nome](../media/NameCommunication.PNG)

1. <span data-ttu-id="a3520-112">Nel centro sicurezza & conformità, accedere a **eDiscovery > Advanced eDiscovery** per visualizzare l'elenco dei casi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a3520-112">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>

2. <span data-ttu-id="a3520-113">Selezionare un caso, fare clic sulla scheda **comunicazioni** , quindi fare clic su **nuova comunicazione**.</span><span class="sxs-lookup"><span data-stu-id="a3520-113">Select a case, click the **Communications** tab, and then click **New communication**.</span></span>

3. <span data-ttu-id="a3520-114">Nella pagina **nome comunicazione** specificare i seguenti dettagli di comunicazione (necessari).</span><span class="sxs-lookup"><span data-stu-id="a3520-114">On the **Name communication** page, specify the following (required) communication details.</span></span>

    - <span data-ttu-id="a3520-115">**Nome**: questo è il nome della comunicazione.</span><span class="sxs-lookup"><span data-stu-id="a3520-115">**Name**: This is the name for the communication.</span></span>

    - <span data-ttu-id="a3520-116">**Responsabile del rilascio**: nell'elenco a discesa viene visualizzato un elenco di membri del caso.</span><span class="sxs-lookup"><span data-stu-id="a3520-116">**Issuing officer**: The dropdown list displays a list of case members.</span></span> <span data-ttu-id="a3520-117">Per ulteriori informazioni su come aggiungere nuovi membri a un caso, vedere [creare un caso avanzato di eDiscovery](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case).</span><span class="sxs-lookup"><span data-stu-id="a3520-117">For more information on how to add new members to a case, see [Create an Advanced eDiscovery case](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case).</span></span> <span data-ttu-id="a3520-118">Ogni avviso inviato ai depositari verrà inviato per conto del responsabile del rilascio specificato.</span><span class="sxs-lookup"><span data-stu-id="a3520-118">Each notice sent to custodians will be sent on behalf of the specified issuing officer.</span></span>

> [!NOTE]
> <span data-ttu-id="a3520-119">Il responsabile del rilascio deve disporre di una **cassetta postale attiva** da visualizzare nell'elenco a discesa dell'ufficiale emittente</span><span class="sxs-lookup"><span data-stu-id="a3520-119">The issuing officer must have an **active mailbox** to show up in the Issuing Officer dropdown</span></span>


4. <span data-ttu-id="a3520-120">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a3520-120">Click **Next**.</span></span>

## <a name="step-2-define-the-portal-content"></a><span data-ttu-id="a3520-121">Passaggio 2: definire il contenuto del portale</span><span class="sxs-lookup"><span data-stu-id="a3520-121">Step 2: Define the portal content</span></span>

<span data-ttu-id="a3520-122">Successivamente, è possibile creare e aggiungere il contenuto dell'avviso di blocco.</span><span class="sxs-lookup"><span data-stu-id="a3520-122">Next, you can create and add the content of the hold notice.</span></span> <span data-ttu-id="a3520-123">Nella pagina **Definisci contenuto portale** della creazione guidata **comunicazione** , specificare il contenuto della notifica di blocco.</span><span class="sxs-lookup"><span data-stu-id="a3520-123">On the **Define portal content** page in the **Create communication** wizard, specify the contents of the hold notice.</span></span> <span data-ttu-id="a3520-124">Questo contenuto verrà accodato automaticamente agli avvisi di emissione, riemissione, sollecito e escalation.</span><span class="sxs-lookup"><span data-stu-id="a3520-124">This content will be automatically appended to the Issuance, Re-Issue, Reminder, and Escalation notices.</span></span> <span data-ttu-id="a3520-125">Inoltre, questo contenuto verrà visualizzato nel portale di conformità del custode.</span><span class="sxs-lookup"><span data-stu-id="a3520-125">Additionally, this content will appear in the custodian's Compliance Portal.</span></span> 

![Pagina contenuto portale](../media/PortalContent.PNG)

<span data-ttu-id="a3520-127">Per creare il contenuto del portale:</span><span class="sxs-lookup"><span data-stu-id="a3520-127">To create the portal content:</span></span>

1. <span data-ttu-id="a3520-128">Digitare (o tagliare e incollare da un altro documento) la notifica di blocco nella casella di testo per il contenuto del portale.</span><span class="sxs-lookup"><span data-stu-id="a3520-128">Type (or cut and paste from another document) your hold notice in the textbox for the portal content.</span></span> 

2. <span data-ttu-id="a3520-129">Inserire le variabili di Unione nell'avviso per personalizzare l'avviso e condividere il portale di conformità dei depositari.</span><span class="sxs-lookup"><span data-stu-id="a3520-129">Insert merge variables into your notice to customize the notice and share the Custodian Compliance Portal.</span></span>

3. <span data-ttu-id="a3520-130">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a3520-130">Click **Next**.</span></span>

  >[!Tip]
  ><span data-ttu-id="a3520-131">Per ulteriori informazioni su come personalizzare il contenuto e il formato del contenuto del portale, vedere [use the Communications editor](using-communications-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a3520-131">To learn more about how to can customize the content and format of the portal content, see [Use the Communications Editor](using-communications-editor.md).</span></span>

## <a name="step-3-set-the-required-notifications"></a><span data-ttu-id="a3520-132">Passaggio 3: impostare le notifiche obbligatorie</span><span class="sxs-lookup"><span data-stu-id="a3520-132">Step 3: Set the required notifications</span></span>

<span data-ttu-id="a3520-133">Dopo aver definito il contenuto della notifica di blocco, è possibile configurare i flussi di lavoro per l'invio e la gestione del processo di notifica.</span><span class="sxs-lookup"><span data-stu-id="a3520-133">After you've defined the contents of the hold notice, you can set up the workflows around sending and managing the notification process.</span></span> <span data-ttu-id="a3520-134">Le notifiche sono messaggi di posta elettronica inviati per la notifica e il follow-up con i depositari.</span><span class="sxs-lookup"><span data-stu-id="a3520-134">Notifications are email messages that are sent to notify and follow up with custodians.</span></span> <span data-ttu-id="a3520-135">Ogni custode aggiunto alla comunicazione riceverà la stessa notifica.</span><span class="sxs-lookup"><span data-stu-id="a3520-135">Every custodian added to the communication will receive the same notification.</span></span> 

<span data-ttu-id="a3520-136">Per impostare e inviare una notifica di blocco, è necessario includere le notifiche di emissione, riemissione e rilascio.</span><span class="sxs-lookup"><span data-stu-id="a3520-136">To set up and send a hold notice, you must include Issuance, Re-Issuance, and Release notifications.</span></span>

### <a name="issuance-notification"></a><span data-ttu-id="a3520-137">Notifica di rilascio</span><span class="sxs-lookup"><span data-stu-id="a3520-137">Issuance notification</span></span> 

<span data-ttu-id="a3520-138">Dopo aver creato la comunicazione, la **notifica di rilascio** viene avviata dal responsabile del rilascio specificato.</span><span class="sxs-lookup"><span data-stu-id="a3520-138">After the communication is created, the **Issuance Notification** is initiated by the specified Issuing Officer.</span></span> <span data-ttu-id="a3520-139">La notifica di rilascio è la prima comunicazione inviata al custode per informarli dei loro obblighi di conservazione.</span><span class="sxs-lookup"><span data-stu-id="a3520-139">The Issuance notification is the first communication sent to the custodian to inform them about their preservation obligations.</span></span> 

<span data-ttu-id="a3520-140">Per creare una notifica di rilascio:</span><span class="sxs-lookup"><span data-stu-id="a3520-140">To create an issuance notification:</span></span>

1. <span data-ttu-id="a3520-141">Nel riquadro **rilascio** , fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a3520-141">In the **Issuance** tile, click **Edit**.</span></span>

2. <span data-ttu-id="a3520-142">Se necessario, aggiungere ulteriori membri del caso o personale ai campi **CC** e **Ccn** .</span><span class="sxs-lookup"><span data-stu-id="a3520-142">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="a3520-143">Per aggiungere più utenti a tali campi, separare gli indirizzi di posta elettronica con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="a3520-143">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="a3520-144">Specificare l' **oggetto** per l'avviso (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-144">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="a3520-145">Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-145">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="a3520-146">Il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="a3520-146">The portal content you defined in Step 2 is added to the end of the issuance notice.</span></span> 

5. <span data-ttu-id="a3520-147">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a3520-147">Click **Save**.</span></span>

### <a name="re-issuance-notification"></a><span data-ttu-id="a3520-148">Notifica Re-Issuance</span><span class="sxs-lookup"><span data-stu-id="a3520-148">Re-Issuance notification</span></span>

<span data-ttu-id="a3520-149">Quando il caso progredisce, potrebbe essere necessario che i depositari possano conservare dati aggiuntivi o meno rispetto a quelli precedentemente istruiti.</span><span class="sxs-lookup"><span data-stu-id="a3520-149">As the case progresses, custodians may be required to preserve additional or less data than was previously instructed.</span></span> <span data-ttu-id="a3520-150">Dopo aver aggiornato il contenuto del portale, viene inviata la notifica di riemissione e vengono avvisati i depositari delle modifiche apportate ai propri obblighi di conservazione.</span><span class="sxs-lookup"><span data-stu-id="a3520-150">After you update the portal content, the re-issuance notification is sent and alerts custodians about any changes to their preservation obligations.</span></span>

<span data-ttu-id="a3520-151">Per creare una notifica di riemissione:</span><span class="sxs-lookup"><span data-stu-id="a3520-151">To create a re-issuance notification:</span></span>

1. <span data-ttu-id="a3520-152">Nel riquadro **ristampa** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a3520-152">In the **Reissue** tile, click **Edit**.</span></span>

2. <span data-ttu-id="a3520-153">Se necessario, aggiungere ulteriori membri del caso o personale ai campi **CC** e **Ccn** .</span><span class="sxs-lookup"><span data-stu-id="a3520-153">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="a3520-154">Per aggiungere più utenti a tali campi, separare gli indirizzi di posta elettronica con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="a3520-154">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="a3520-155">Specificare l' **oggetto** per l'avviso (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-155">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="a3520-156">Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-156">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="a3520-157">Il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di riemissione.</span><span class="sxs-lookup"><span data-stu-id="a3520-157">The portal content you defined in Step 2 is added to the end of the re-issuance notice.</span></span>

5. <span data-ttu-id="a3520-158">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a3520-158">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="a3520-159">Se il contenuto del portale viene modificato (nella pagina **definire il contenuto del portale** nella procedura guidata di modifica della **comunicazione** ), la notifica di riemissione verrà inviata automaticamente a tutti i depositari assegnati alla notifica.</span><span class="sxs-lookup"><span data-stu-id="a3520-159">If the portal content is modified (on the **Define Portal Content** page in the **Edit communication** wizard), the re-issuance notification will be automatically sent to all custodians assigned to the notice.</span></span> <span data-ttu-id="a3520-160">Dopo che la notifica viene inviata, ai depositari verrà chiesto di riconfermare il proprio avviso di esenzione.</span><span class="sxs-lookup"><span data-stu-id="a3520-160">After the notification is sent, custodians will be asked to re-acknowledge their hold notice.</span></span> <span data-ttu-id="a3520-161">Se sono stati configurati eventuali flussi di lavoro di promemoria o escalation, anche questi verranno riavviati.</span><span class="sxs-lookup"><span data-stu-id="a3520-161">If you have set up any reminder or escalation workflows, these will also re-start.</span></span> <span data-ttu-id="a3520-162">Per ulteriori informazioni su ciò che gli altri eventi di gestione dei casi attivano le comunicazioni, vedere [eventi che attivano le notifiche](#events-that-trigger-notifications).</span><span class="sxs-lookup"><span data-stu-id="a3520-162">For more information about what other case management events trigger communications, see [Events that trigger notifications](#events-that-trigger-notifications).</span></span>

### <a name="release-notification"></a><span data-ttu-id="a3520-163">Notifica di rilascio</span><span class="sxs-lookup"><span data-stu-id="a3520-163">Release notification</span></span>

<span data-ttu-id="a3520-164">Dopo aver risolto un problema o se un custode non è più soggetto alla conservazione del contenuto, è possibile rilasciare il custode da un caso.</span><span class="sxs-lookup"><span data-stu-id="a3520-164">After a matter is resolved or if a custodian is no longer subject to preserve content, you can release the custodian from a case.</span></span> <span data-ttu-id="a3520-165">Se il custode ha precedentemente emesso un avviso di esenzione, la notifica di rilascio può essere utilizzata per avvisare i depositari che sono stati rilasciati dall'obbligo.</span><span class="sxs-lookup"><span data-stu-id="a3520-165">If the custodian was previously issued a hold notice, the release notification can be used to alert custodians that they have been released from their obligation.</span></span>

<span data-ttu-id="a3520-166">Per creare una notifica di rilascio:</span><span class="sxs-lookup"><span data-stu-id="a3520-166">To create a release notification:</span></span> 

1. <span data-ttu-id="a3520-167">Nella sezione **rilascia** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a3520-167">In the **Release** tile, click **Edit**.</span></span>

2. <span data-ttu-id="a3520-168">Se necessario, aggiungere ulteriori membri del caso o personale ai campi **CC** e **Ccn** .</span><span class="sxs-lookup"><span data-stu-id="a3520-168">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="a3520-169">Per aggiungere più utenti a tali campi, separare gli indirizzi di posta elettronica con un punto e virgola.</span><span class="sxs-lookup"><span data-stu-id="a3520-169">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="a3520-170">Specificare l' **oggetto** per l'avviso (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-170">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="a3520-171">Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-171">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span>

5. <span data-ttu-id="a3520-172">Fare clic su **Salva** e passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="a3520-172">Click **Save** and go to the next step.</span></span>

## <a name="optional-step-4-set-the-optional-notifications"></a><span data-ttu-id="a3520-173">Optional Passaggio 4: impostare le notifiche facoltative</span><span class="sxs-lookup"><span data-stu-id="a3520-173">(Optional) Step 4: Set the optional notifications</span></span>

<span data-ttu-id="a3520-174">Facoltativamente, è possibile semplificare il flusso di lavoro per la creazione e la pianificazione delle notifiche di promemoria automatica e di escalation.</span><span class="sxs-lookup"><span data-stu-id="a3520-174">Optionally, you can simplify the workflow for following up with unresponsive custodians by creating and scheduling automated reminder and escalation notifications.</span></span>

![Pagina promemoria/escalation](../media/ReminderEscalations.PNG)

### <a name="reminders"></a><span data-ttu-id="a3520-176">Promemoria</span><span class="sxs-lookup"><span data-stu-id="a3520-176">Reminders</span></span>

<span data-ttu-id="a3520-177">Dopo aver inviato una notifica di blocco, è possibile eseguire il follow-up con i depositari non rispondenti definendo un flusso di lavoro di sollecito.</span><span class="sxs-lookup"><span data-stu-id="a3520-177">After you have sent a hold notification, you can follow up with unresponsive custodians by defining a reminder workflow.</span></span>

<span data-ttu-id="a3520-178">Per pianificare i promemoria:</span><span class="sxs-lookup"><span data-stu-id="a3520-178">To schedule reminders:</span></span>

1. <span data-ttu-id="a3520-179">Nel riquadro **promemoria** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a3520-179">In the **Reminder** tile, click **Edit**.</span></span>

2. <span data-ttu-id="a3520-180">Abilitare il flusso di lavoro di **sollecito** attivando l'interruttore di **stato** (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-180">Enable the **Reminder** workflow by turning on the **Status** toggle (required).</span></span>

3. <span data-ttu-id="a3520-181">Specificare l' **intervallo di sollecito (in giorni)** (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-181">Specify the **Reminder interval (in days)** (required).</span></span> <span data-ttu-id="a3520-182">Questo è il numero di giorni di attesa prima dell'invio delle notifiche del primo e del promemoria di follow-up.</span><span class="sxs-lookup"><span data-stu-id="a3520-182">This is the number of days to wait before sending the first and follow-up reminder notifications.</span></span> <span data-ttu-id="a3520-183">Se ad esempio si imposta l'intervallo di sollecito su sette giorni, il primo sollecito verrebbe inviato sette giorni dopo l'invio iniziale della notifica di blocco.</span><span class="sxs-lookup"><span data-stu-id="a3520-183">For example, if you set the reminder interval to seven days, then the first reminder would be sent seven days after the hold notification was initially issued.</span></span> <span data-ttu-id="a3520-184">Tutti i promemoria successivi vengono inviati anche ogni sette giorni.</span><span class="sxs-lookup"><span data-stu-id="a3520-184">All subsequent reminders would also be sent every seven days.</span></span>

4. <span data-ttu-id="a3520-185">Specificare il **numero di promemoria** (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-185">Specify the **Number of reminders** (required).</span></span> <span data-ttu-id="a3520-186">Questo campo consente di specificare il numero di promemoria da inviare ai depositari non rispondenti.</span><span class="sxs-lookup"><span data-stu-id="a3520-186">This field specifies how many reminders to send to unresponsive custodians.</span></span> <span data-ttu-id="a3520-187">Ad esempio, se si imposta il numero di promemoria su 3, un custode riceverà un massimo di tre promemoria.</span><span class="sxs-lookup"><span data-stu-id="a3520-187">For example, if you set the number of reminders to 3, then a custodian would receive a maximum of three reminders.</span></span> <span data-ttu-id="a3520-188">Dopo che un custode riconosce la notifica di blocco, i promemoria non verranno più inviati a quell'utente.</span><span class="sxs-lookup"><span data-stu-id="a3520-188">After a custodian acknowledges the hold notification, reminders will no longer be sent to that user.</span></span>

5. <span data-ttu-id="a3520-189">Specificare l' **oggetto** per l'avviso (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-189">Specify the **Subject** for the notice (required).</span></span> 

6. <span data-ttu-id="a3520-190">Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-190">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="a3520-191">Il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine della notifica di sollecito.</span><span class="sxs-lookup"><span data-stu-id="a3520-191">The portal content you defined in Step 2 is added to the end of the reminder notice.</span></span>

7. <span data-ttu-id="a3520-192">Fare clic su **Salva** e passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="a3520-192">Click **Save** and go the next step.</span></span>

### <a name="escalations"></a><span data-ttu-id="a3520-193">Escalation</span><span class="sxs-lookup"><span data-stu-id="a3520-193">Escalations</span></span>

<span data-ttu-id="a3520-194">In alcuni casi, potrebbero essere necessari ulteriori modi per eseguire il follow-up con i depositari non rispondenti.</span><span class="sxs-lookup"><span data-stu-id="a3520-194">In some situations, you may need additional ways to follow up with unresponsive custodians.</span></span> <span data-ttu-id="a3520-195">Se un custode non riconosce una notifica di blocco dopo aver ricevuto il numero specificato di promemoria, il team legale può specificare un flusso di lavoro per inviare automaticamente un avviso di escalation al custode e al relativo responsabile.</span><span class="sxs-lookup"><span data-stu-id="a3520-195">If a custodian doesn't acknowledge a hold notification after receiving the specified number of reminders, the legal team can specify a workflow to automatically send an escalation notice to the custodian and their manager.</span></span>

<span data-ttu-id="a3520-196">Per pianificare le escalation:</span><span class="sxs-lookup"><span data-stu-id="a3520-196">To schedule escalations:</span></span>

1. <span data-ttu-id="a3520-197">Nel riquadro **escalation** fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="a3520-197">In the **Escalation** tile, click **Edit**.</span></span>

2. <span data-ttu-id="a3520-198">Abilitare il flusso di lavoro per l' **escalation** attivando l'interruttore di **stato** .</span><span class="sxs-lookup"><span data-stu-id="a3520-198">Enable the **Escalation** workflow by turning on the **Status** toggle.</span></span>

3. <span data-ttu-id="a3520-199">Specificare l' **intervallo di escalation (in giorni)** (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-199">Specify the **Escalation interval (in days)** (required).</span></span>

4. <span data-ttu-id="a3520-200">Specificare il **numero di escalation** (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-200">Specify the **Number of escalations** (required).</span></span> <span data-ttu-id="a3520-201">Questo campo consente di specificare il numero di escalation da inviare ai depositari non rispondenti.</span><span class="sxs-lookup"><span data-stu-id="a3520-201">This field specifies how many escalations to send to unresponsive custodians.</span></span> <span data-ttu-id="a3520-202">Ad esempio, se si imposta il numero di escalation su 3, un avviso di escalation verrebbe inviato al custode e al relativo Manager al massimo tre volte.</span><span class="sxs-lookup"><span data-stu-id="a3520-202">For example, if you set the number of escalations to 3, then an escalation notice would be sent to the custodian and their manager a maximum of three times.</span></span> <span data-ttu-id="a3520-203">Dopo che un custode riconosce la notifica di blocco, le escalation non verranno più inviate.</span><span class="sxs-lookup"><span data-stu-id="a3520-203">After a custodian acknowledges the hold notification, escalations will no longer be sent.</span></span>

5. <span data-ttu-id="a3520-204">Specificare l' **oggetto** per l'avviso (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-204">Specify the **Subject** for the notice (required).</span></span> 

6. <span data-ttu-id="a3520-205">Specificare il contenuto o altre istruzioni che si desidera fornire al custode (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="a3520-205">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="a3520-206">Il contenuto del portale definito nel passaggio 2 viene aggiunto alla fine dell'avviso di escalation.</span><span class="sxs-lookup"><span data-stu-id="a3520-206">The portal content you defined in Step 2 is added to the end of the escalation notice.</span></span>

7. <span data-ttu-id="a3520-207">Fare clic su **Salva** e passare al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="a3520-207">Click **Save** and go the next step.</span></span>

## <a name="step-5-assign-custodians-to-receive-notifications"></a><span data-ttu-id="a3520-208">Passaggio 5: assegnare i depositari per la ricezione delle notifiche</span><span class="sxs-lookup"><span data-stu-id="a3520-208">Step 5: Assign custodians to receive notifications</span></span>

<span data-ttu-id="a3520-209">Dopo aver finalizzato il contenuto per le notifiche, selezionare i depositari ai quali si desidera inviare notifiche.</span><span class="sxs-lookup"><span data-stu-id="a3520-209">After you have finalized the content for notifications, select the custodians that you would like to send notifications to.</span></span> 

![Pagina Selezione depositari](../media/SelectCustodians.PNG)

<span data-ttu-id="a3520-211">Per aggiungere i depositari:</span><span class="sxs-lookup"><span data-stu-id="a3520-211">To add custodians:</span></span>

1. <span data-ttu-id="a3520-212">Assegnare i depositari alla comunicazione facendo clic sulla casella di controllo accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="a3520-212">Assign custodians to the communication by clicking the checkbox next to their name.</span></span>

    <span data-ttu-id="a3520-213">Dopo la creazione della comunicazione, il flusso di lavoro di notifica verrà applicato automaticamente ai depositari selezionati.</span><span class="sxs-lookup"><span data-stu-id="a3520-213">After the communication is created, the notification workflow will automatically apply to the selected custodians.</span></span>

2. <span data-ttu-id="a3520-214">Fare clic su **Avanti** per esaminare le impostazioni di comunicazione e i dettagli.</span><span class="sxs-lookup"><span data-stu-id="a3520-214">Click **Next** to review the communication settings and details.</span></span>

>[!NOTE]
><span data-ttu-id="a3520-215">È possibile aggiungere solo i depositari che sono stati aggiunti al caso e non sono stati inviati un'altra notifica all'interno del caso.</span><span class="sxs-lookup"><span data-stu-id="a3520-215">You can only add custodians who have been added to the case and haven't been sent another notification within the case.</span></span>

## <a name="step-6-review-settings"></a><span data-ttu-id="a3520-216">Passaggio 6: rivedere le impostazioni</span><span class="sxs-lookup"><span data-stu-id="a3520-216">Step 6: Review settings</span></span>

<span data-ttu-id="a3520-217">Dopo aver esaminato le impostazioni e fare clic su **Invia** per completare la comunicazione, il sistema avvierà automaticamente il flusso di lavoro di comunicazione inviando la notifica di rilascio.</span><span class="sxs-lookup"><span data-stu-id="a3520-217">After you review the settings and click **Send** to complete the communication, the system will automatically start the communication workflow by sending the issuance notice.</span></span>

## <a name="events-that-trigger-notifications"></a><span data-ttu-id="a3520-218">Eventi che attivano le notifiche</span><span class="sxs-lookup"><span data-stu-id="a3520-218">Events that trigger notifications</span></span>

<span data-ttu-id="a3520-219">Nella tabella seguente vengono descritti gli eventi del processo di gestione dei casi che si attivano quando i diversi tipi di notifiche vengono inviati ai depositari.</span><span class="sxs-lookup"><span data-stu-id="a3520-219">The following table describes events in the case management process that trigger when the different types of notifications are sent to custodians.</span></span>

|<span data-ttu-id="a3520-220">Tipo di comunicazione</span><span class="sxs-lookup"><span data-stu-id="a3520-220">Type of communication</span></span>|<span data-ttu-id="a3520-221">Trigger</span><span class="sxs-lookup"><span data-stu-id="a3520-221">Trigger</span></span> |
|:---------|:---------|
|<span data-ttu-id="a3520-222">Notifiche di emissione</span><span class="sxs-lookup"><span data-stu-id="a3520-222">Issuance notices</span></span>|<span data-ttu-id="a3520-223">La creazione iniziale della notifica.</span><span class="sxs-lookup"><span data-stu-id="a3520-223">The initial creation of the notification.</span></span> <span data-ttu-id="a3520-224">È inoltre possibile rinviare manualmente una notifica di blocco.</span><span class="sxs-lookup"><span data-stu-id="a3520-224">You can also manually resend a hold notification.</span></span> |
|<span data-ttu-id="a3520-225">Notifiche di riemissione</span><span class="sxs-lookup"><span data-stu-id="a3520-225">Re-issuance notices</span></span>|<span data-ttu-id="a3520-226">Aggiornamento del contenuto del portale nella pagina **definire il contenuto del portale** nella procedura guidata **modifica comunicazione** .</span><span class="sxs-lookup"><span data-stu-id="a3520-226">Updating the portal content on the **Define Portal Content** page in the **Edit communication** wizard.</span></span>|
|<span data-ttu-id="a3520-227">Notifiche di rilascio</span><span class="sxs-lookup"><span data-stu-id="a3520-227">Release notices</span></span>|<span data-ttu-id="a3520-228">Il custode viene rilasciato dal caso.</span><span class="sxs-lookup"><span data-stu-id="a3520-228">The custodian is released from the case.</span></span>|
|<span data-ttu-id="a3520-229">Promemoria</span><span class="sxs-lookup"><span data-stu-id="a3520-229">Reminders</span></span>|<span data-ttu-id="a3520-230">L'intervallo e il numero di promemoria configurati per il promemoria.</span><span class="sxs-lookup"><span data-stu-id="a3520-230">The interval and number of reminders configured for the reminder.</span></span>|
|<span data-ttu-id="a3520-231">Escalation</span><span class="sxs-lookup"><span data-stu-id="a3520-231">Escalations</span></span>|<span data-ttu-id="a3520-232">L'intervallo e il numero di promemoria configurati per l'escalation.</span><span class="sxs-lookup"><span data-stu-id="a3520-232">The interval and number of reminders configured for the escalation.</span></span>|
|||
