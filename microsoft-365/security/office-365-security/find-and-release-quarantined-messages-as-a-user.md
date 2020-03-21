---
title: Trovare e rilasciare i messaggi messi in quarantena come utente di Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: L'utente di Office 365 può visualizzare, rilasciare ed eliminare i messaggi in quarantena (messaggi di cui si è destinatari e che il filtro della posta indesiderata ha messo in quarantena come posta indesiderata o posta inviata in blocco). È possibile visualizzare e gestire i messaggi in quarantena nel Centro sicurezza e conformità.
ms.openlocfilehash: e74358d57b96c8655fbf6a3f7f0b6eedb5e65ede
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857334"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="b3042-104">Trovare e rilasciare i messaggi messi in quarantena come utente di Office 365</span><span class="sxs-lookup"><span data-stu-id="b3042-104">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="b3042-105">La quarantena contiene messaggi potenzialmente pericolosi o indesiderati nelle organizzazioni di Office 365 con cassette postali nelle organizzazioni Exchange Online o Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b3042-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="b3042-106">Per altre informazioni, vedere [Quarantena in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="b3042-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="b3042-107">L'utente può visualizzare, rilasciare ed eliminare i messaggi in quarantena di cui si è destinatari e che sono stati messi in quarantena come posta indesiderata, posta inviata in blocco o phishing (a partire da aprile 2020).</span><span class="sxs-lookup"><span data-stu-id="b3042-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="b3042-108">È anche possibile segnalare falsi positivi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b3042-108">You can also report false positives to Microsoft.</span></span>

<span data-ttu-id="b3042-109">È possibile visualizzare e gestire i messaggi in quarantena nel Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="b3042-109">You view and manage your quarantined messages in the Security & Compliance Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b3042-110">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b3042-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b3042-111">Per aprire il Centro sicurezza e conformità di Office 365, passare a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="b3042-111">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="b3042-112">Per aprire direttamente la pagina della quarantena, passare a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="b3042-112">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="b3042-113">Gli amministratori possono configurare per quanto tempo i messaggi vengono tenuti in quarantena prima di essere eliminati definitivamente (criteri di protezione dalla posta indesiderata).</span><span class="sxs-lookup"><span data-stu-id="b3042-113">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="b3042-114">I messaggi scaduti dalla quarantena non sono recuperabili.</span><span class="sxs-lookup"><span data-stu-id="b3042-114">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="b3042-115">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b3042-115">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="b3042-116">Gli amministratori possono anche [abilitare le notifiche di posta indesiderata per l'utente finale](configure-your-spam-filter-policies.md) nei criteri di protezione dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="b3042-116">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md) in anti-spam policies.</span></span> <span data-ttu-id="b3042-117">A partire da ottobre 2019, non è più possibile rilasciare messaggi in quarantena direttamente da queste notifiche.</span><span class="sxs-lookup"><span data-stu-id="b3042-117">As of October 2019, you can no longer release quarantined messages directly from these notifications.</span></span> <span data-ttu-id="b3042-118">È possibile fare clic su **Rivedi** nella notifica, che indirizza a Quarantena nel Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="b3042-118">You can click **Review** in the notification, which will take you to Quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="b3042-119">Per altre informazioni, vedere [Notifiche di posta indesiderata per l'utente finale in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="b3042-119">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="b3042-120">I messaggi messi in quarantena per phishing con alta confidenza, malware o regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="b3042-120">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="b3042-121">Per altre informazioni, vedere [Individuazione e rilascio dei messaggi in quarantena come amministratore in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span><span class="sxs-lookup"><span data-stu-id="b3042-121">For more information, see [Find and release quarantined messages as an admin in Office 365](find-and-release-quarantined-messages-as-an-administrator.md).</span></span>

- <span data-ttu-id="b3042-122">È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.</span><span class="sxs-lookup"><span data-stu-id="b3042-122">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="b3042-123">Visualizzazione dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="b3042-123">View your quarantined messages</span></span>

1. <span data-ttu-id="b3042-124">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="b3042-124">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="b3042-125">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="b3042-125">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="b3042-126">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="b3042-126">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="b3042-127">I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="b3042-127">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="b3042-128">**Ricevuto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3042-128">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="b3042-129">**Mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3042-129">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="b3042-130">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3042-130">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="b3042-131">**Motivo della quarantena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3042-131">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="b3042-132">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3042-132">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="b3042-133">**Tipo di criterio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3042-133">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="b3042-134">**Scadenza**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b3042-134">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="b3042-135">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="b3042-135">**Recipient**</span></span>

   - <span data-ttu-id="b3042-136">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="b3042-136">**Message ID**</span></span>

   - <span data-ttu-id="b3042-137">**Nome criterio**</span><span class="sxs-lookup"><span data-stu-id="b3042-137">**Policy name**</span></span>

   - <span data-ttu-id="b3042-138">**Dimensioni**</span><span class="sxs-lookup"><span data-stu-id="b3042-138">**Size**</span></span>

   - <span data-ttu-id="b3042-139">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="b3042-139">**Direction**</span></span>

   <span data-ttu-id="b3042-140">Al termine, fare clic su **Salva** o fare clic su **Imposta su valore predefinito**.</span><span class="sxs-lookup"><span data-stu-id="b3042-140">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="b3042-141">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="b3042-141">To filter the results, click **Filter**.</span></span> <span data-ttu-id="b3042-142">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="b3042-142">The available filters are:</span></span>

   - <span data-ttu-id="b3042-143">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="b3042-143">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="b3042-144">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="b3042-144">**Today**</span></span>

     - <span data-ttu-id="b3042-145">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="b3042-145">**Next 2 days**</span></span>

     - <span data-ttu-id="b3042-146">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="b3042-146">**Next 7 days**</span></span>

     - <span data-ttu-id="b3042-147">**Personalizzato**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="b3042-147">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="b3042-148">**Ora ricezione**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="b3042-148">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="b3042-149">**Motivo della quarantena**:</span><span class="sxs-lookup"><span data-stu-id="b3042-149">**Quarantine reason**:</span></span>

     - <span data-ttu-id="b3042-150">**Invio in blocco**</span><span class="sxs-lookup"><span data-stu-id="b3042-150">**Bulk**</span></span>

     - <span data-ttu-id="b3042-151">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="b3042-151">**Spam**</span></span>

     - <span data-ttu-id="b3042-152">**Phishing** (a partire da aprile 2020)</span><span class="sxs-lookup"><span data-stu-id="b3042-152">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="b3042-153">Per cancellare il filtro, fare clic su **Cancella**.</span><span class="sxs-lookup"><span data-stu-id="b3042-153">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="b3042-154">Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="b3042-154">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="b3042-155">Utilizzare **Ordina i risultati per** (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per trovare messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="b3042-155">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="b3042-156">I caratteri jolly non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="b3042-156">Wildcards aren't supported.</span></span> <span data-ttu-id="b3042-157">È possibile cercare in base ai seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b3042-157">You can search by the following values:</span></span>

   - <span data-ttu-id="b3042-158">**ID messaggio**: identificatore univoco globale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b3042-158">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="b3042-159">Se si seleziona un messaggio nell'elenco, il valore **ID messaggio** viene visualizzato nel riquadro a comparsa **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="b3042-159">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="b3042-160">Gli amministratori possono usare [Traccia messaggio](message-trace-scc.md) per trovare i messaggi e i valori ID messaggio corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b3042-160">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="b3042-161">**Indirizzo di posta elettronica del mittente**: indirizzo di posta elettronica di un singolo mittente.</span><span class="sxs-lookup"><span data-stu-id="b3042-161">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="b3042-162">**Indirizzo di posta elettronica del destinatario**: indirizzo di posta elettronica di un singolo destinatario.</span><span class="sxs-lookup"><span data-stu-id="b3042-162">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="b3042-163">**Oggetto**: utilizzare l'intero oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b3042-163">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="b3042-164">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b3042-164">The search is not case-sensitive.</span></span>

   <span data-ttu-id="b3042-165">Dopo avere immesso i criteri di ricerca, fare clic sul ![pulsante Aggiorna](../media/scc-quarantine-refresh.png) **Aggiorna** per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="b3042-165">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="b3042-166">Dopo aver trovato un messaggio in quarantena specifico, selezionarlo per visualizzarne i dettagli ed eseguire delle operazioni (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="b3042-166">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="b3042-167">Esportare i risultati di un messaggio</span><span class="sxs-lookup"><span data-stu-id="b3042-167">Export message results</span></span>

1. <span data-ttu-id="b3042-168">Selezionare i messaggi a cui si è interessati e quindi fare clic su **Esporta risultati**.</span><span class="sxs-lookup"><span data-stu-id="b3042-168">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="b3042-169">Fare clic su **Sì** nel messaggio di conferma che avverte di tenere aperta la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="b3042-169">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="b3042-170">Una volta completata l'esportazione, è possibile assegnare un nome e scegliere il percorso di download per il file .csv.</span><span class="sxs-lookup"><span data-stu-id="b3042-170">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="b3042-171">Visualizzare i dettagli dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="b3042-171">View quarantined message details</span></span>

<span data-ttu-id="b3042-172">Quando si seleziona un messaggio di posta elettronica nell'elenco, i seguenti dettagli del messaggio vengono visualizzati nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="b3042-172">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="b3042-173">**ID messaggio**: identificatore univoco globale per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b3042-173">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="b3042-174">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="b3042-174">**Sender address**</span></span>

- <span data-ttu-id="b3042-175">**Ricezione**: data/ora di ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b3042-175">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="b3042-176">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="b3042-176">**Subject**</span></span>

- <span data-ttu-id="b3042-177">**Motivo della quarantena**: indica se un messaggio è stato identificato come **Posta indesiderata**, **Invio in blocco** o **Phishing** (a partire da aprile 2020).</span><span class="sxs-lookup"><span data-stu-id="b3042-177">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="b3042-178">**Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **Visualizza intestazione messaggio** per visualizzare l'elenco completo dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="b3042-178">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="b3042-179">**Scadenza**: data/ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="b3042-179">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="b3042-180">**Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="b3042-180">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="b3042-181">**Non ancora rilasciato in**: tutti gli eventuali messaggi di posta elettronica in cui il messaggio non è stato ancora rilasciato.</span><span class="sxs-lookup"><span data-stu-id="b3042-181">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="b3042-182">Eseguire azioni sulla posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="b3042-182">Take action on quarantined email</span></span>

<span data-ttu-id="b3042-183">Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le operazioni da eseguire con i messaggi nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="b3042-183">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="b3042-184">**Rilascia messaggio**: nel riquadro a comparsa visualizzato, scegliere se **segnalare i messaggi a Microsoft per l'analisi**.</span><span class="sxs-lookup"><span data-stu-id="b3042-184">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="b3042-185">Questa opzione è selezionata per impostazione predefinita e riporta il messaggio messo in quarantena per errore a Microsoft come falso positivo.</span><span class="sxs-lookup"><span data-stu-id="b3042-185">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="b3042-186">Al termine, fare clic su **Rilascia messaggio**.</span><span class="sxs-lookup"><span data-stu-id="b3042-186">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="b3042-187">**Visualizza intestazione messaggio**: scegliere questo collegamento per vedere il testo dell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b3042-187">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="b3042-188">Per analizzare i campi dell'intestazione e i valori in modo approfondito, copiare il testo negli Appunti e poi scegliere **Microsoft Message Header Analyzer** per passare all'Analizzatore connettività remota. Fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si vuole uscire da Office 365 per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="b3042-188">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="b3042-189">Incollare l'intestazione del messaggio nella pagina nella sezione Message Header Analyzer e scegliere **Analizza intestazioni**:</span><span class="sxs-lookup"><span data-stu-id="b3042-189">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="b3042-190">**Anteprima messaggio**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="b3042-190">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="b3042-191">**Visualizzazione origine**: mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.</span><span class="sxs-lookup"><span data-stu-id="b3042-191">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="b3042-192">**Visualizzazione testo**: Mostra il corpo del messaggio in testo normale.</span><span class="sxs-lookup"><span data-stu-id="b3042-192">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="b3042-193">**Scarica il messaggio**: nel riquadro a comparsa visualizzato, selezionare **Sono consapevole dei rischi associati al download di questo messaggio** per salvare una copia locale del messaggio in formato .eml.</span><span class="sxs-lookup"><span data-stu-id="b3042-193">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="b3042-194">**Rimuovi da quarantena**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="b3042-194">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="b3042-195">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b3042-195">When you're finished, click **Close**.</span></span>

<span data-ttu-id="b3042-196">Se il messaggio non viene rilasciato o rimosso, verrà eliminato dopo la scadenza del periodo di conservazione in quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="b3042-196">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="b3042-197">Eseguire azioni su più messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="b3042-197">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="b3042-198">Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **Azioni in blocco** che consente di eseguire le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="b3042-198">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="b3042-199">**Rilascia messaggi**: le opzioni sono le stesse del rilascio di un singolo messaggio, ma non è possibile selezionare **Rilascia i messaggi a specifici destinatari**; è possibile selezionare solo **Rilascia il messaggio a tutti i destinatari** o **Rilascia i messaggi ad altre persone**.</span><span class="sxs-lookup"><span data-stu-id="b3042-199">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="b3042-200">**Elimina messaggi**: dopo aver fatto clic su **Sì** nell'avviso visualizzato, i messaggi saranno immediatamente eliminati senza essere inviati ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="b3042-200">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="b3042-201">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b3042-201">When you're finished, click **Close**.</span></span>
