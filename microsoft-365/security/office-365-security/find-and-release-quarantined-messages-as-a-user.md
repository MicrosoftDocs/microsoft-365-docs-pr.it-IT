---
title: Trovare e rilasciare messaggi in quarantena come utente
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
ms.custom:
- seo-marvel-apr2020
description: Questo articolo illustra come visualizzare e gestire i messaggi posti in quarantena nel Centro sicurezza e conformità di Microsoft 365.
ms.openlocfilehash: 177f60f1fccc764d74ec0374249a62c602cb84aa
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036513"
---
# <a name="find-and-release-quarantined-messages-as-a-user"></a><span data-ttu-id="e2b63-103">Trovare e rilasciare messaggi in quarantena come utente</span><span class="sxs-lookup"><span data-stu-id="e2b63-103">Find and release quarantined messages as a user</span></span>

<span data-ttu-id="e2b63-104">La quarantena contiene messaggi potenzialmente pericolosi o indesiderati nelle organizzazioni di Microsoft 365 con cassette postali nelle organizzazioni Exchange Online o Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e2b63-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="e2b63-105">Per altre informazioni, vedere [Quarantena in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e2b63-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e2b63-106">L'utente può visualizzare, rilasciare ed eliminare i messaggi in quarantena di cui si è destinatari e che sono stati messi in quarantena come posta indesiderata, posta inviata in blocco o phishing (a partire da aprile 2020).</span><span class="sxs-lookup"><span data-stu-id="e2b63-106">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="e2b63-107">È possibile visualizzare e gestire i messaggi in quarantena nel Centro sicurezza e conformità oppure, nel caso in cui un amministratore l'abbia configurato, nelle [notifiche di posta indesiderata per l'utente finale](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e2b63-107">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e2b63-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e2b63-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e2b63-109">Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="e2b63-109">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="e2b63-110">Per aprire direttamente la pagina della quarantena, passare a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="e2b63-110">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="e2b63-111">Gli amministratori possono configurare per quanto tempo i messaggi vengono tenuti in quarantena prima di essere eliminati definitivamente (criteri di protezione dalla posta indesiderata).</span><span class="sxs-lookup"><span data-stu-id="e2b63-111">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="e2b63-112">I messaggi scaduti dalla quarantena non sono recuperabili.</span><span class="sxs-lookup"><span data-stu-id="e2b63-112">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="e2b63-113">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e2b63-113">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="e2b63-114">Gli amministratori possono anche [abilitare le notifiche di posta indesiderata per l'utente finale](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) nei criteri di protezione dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="e2b63-114">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="e2b63-115">Gli utenti possono rilasciare messaggi di posta indesiderata in quarantena (ma non messaggi di phishing in quarantena) direttamente da queste notifiche.</span><span class="sxs-lookup"><span data-stu-id="e2b63-115">Users can release spam quarantined messages but not phish quarantined messages directly from these notifications.</span></span> <span data-ttu-id="e2b63-116">Per altre informazioni, vedere [Notifiche di posta indesiderata per l'utente finale in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e2b63-116">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="e2b63-117">I messaggi messi in quarantena per phishing con alta confidenza, malware o regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="e2b63-117">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="e2b63-118">I messaggi di phishing possono essere revisionati dagli utenti, ma rilasciati unicamente dagli amministratori.</span><span class="sxs-lookup"><span data-stu-id="e2b63-118">Phish messages can be reviewed by users but only released by admins.</span></span> <span data-ttu-id="e2b63-119">Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="e2b63-119">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="e2b63-120">È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.</span><span class="sxs-lookup"><span data-stu-id="e2b63-120">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="e2b63-121">Visualizzazione dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="e2b63-121">View your quarantined messages</span></span>

1. <span data-ttu-id="e2b63-122">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-122">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e2b63-123">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="e2b63-123">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e2b63-124">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="e2b63-124">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e2b63-125">I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="e2b63-125">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e2b63-126">**Ricevuto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e2b63-126">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="e2b63-127">**Mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e2b63-127">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="e2b63-128">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e2b63-128">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="e2b63-129">**Motivo della quarantena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e2b63-129">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="e2b63-130">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e2b63-130">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="e2b63-131">**Tipo di criterio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e2b63-131">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="e2b63-132">**Scadenza**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e2b63-132">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="e2b63-133">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="e2b63-133">**Recipient**</span></span>

   - <span data-ttu-id="e2b63-134">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="e2b63-134">**Message ID**</span></span>

   - <span data-ttu-id="e2b63-135">**Nome criterio**</span><span class="sxs-lookup"><span data-stu-id="e2b63-135">**Policy name**</span></span>

   - <span data-ttu-id="e2b63-136">**Dimensioni**</span><span class="sxs-lookup"><span data-stu-id="e2b63-136">**Size**</span></span>

   - <span data-ttu-id="e2b63-137">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="e2b63-137">**Direction**</span></span>

   <span data-ttu-id="e2b63-138">Al termine, fare clic su **Salva** o fare clic su **Imposta su valore predefinito**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-138">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="e2b63-139">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-139">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e2b63-140">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="e2b63-140">The available filters are:</span></span>

   - <span data-ttu-id="e2b63-141">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="e2b63-141">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="e2b63-142">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="e2b63-142">**Today**</span></span>

     - <span data-ttu-id="e2b63-143">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="e2b63-143">**Next 2 days**</span></span>

     - <span data-ttu-id="e2b63-144">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="e2b63-144">**Next 7 days**</span></span>

     - <span data-ttu-id="e2b63-145">**Personalizzato**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-145">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e2b63-146">**Ora ricezione**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-146">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e2b63-147">**Motivo della quarantena**:</span><span class="sxs-lookup"><span data-stu-id="e2b63-147">**Quarantine reason**:</span></span>

     - <span data-ttu-id="e2b63-148">**Invio in blocco**</span><span class="sxs-lookup"><span data-stu-id="e2b63-148">**Bulk**</span></span>

     - <span data-ttu-id="e2b63-149">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="e2b63-149">**Spam**</span></span>

     - <span data-ttu-id="e2b63-150">**Phishing** (a partire da aprile 2020)</span><span class="sxs-lookup"><span data-stu-id="e2b63-150">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="e2b63-151">Per cancellare il filtro, fare clic su **Cancella**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-151">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="e2b63-152">Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-152">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="e2b63-153">Utilizzare **Ordina i risultati per** (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per trovare messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="e2b63-153">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="e2b63-154">I caratteri jolly non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="e2b63-154">Wildcards aren't supported.</span></span> <span data-ttu-id="e2b63-155">È possibile cercare in base ai seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="e2b63-155">You can search by the following values:</span></span>

   - <span data-ttu-id="e2b63-156">**ID messaggio**: identificatore univoco globale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e2b63-156">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="e2b63-157">Se si seleziona un messaggio nell'elenco, il valore **ID messaggio** viene visualizzato nel riquadro a comparsa **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-157">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="e2b63-158">Gli amministratori possono usare [Traccia messaggio](message-trace-scc.md) per trovare i messaggi e i valori ID messaggio corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e2b63-158">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="e2b63-159">**Indirizzo di posta elettronica del mittente**: indirizzo di posta elettronica di un singolo mittente.</span><span class="sxs-lookup"><span data-stu-id="e2b63-159">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="e2b63-160">**Indirizzo di posta elettronica del destinatario**: indirizzo di posta elettronica di un singolo destinatario.</span><span class="sxs-lookup"><span data-stu-id="e2b63-160">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="e2b63-161">**Oggetto**: utilizzare l'intero oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e2b63-161">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="e2b63-162">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="e2b63-162">The search is not case-sensitive.</span></span>

   <span data-ttu-id="e2b63-163">Dopo avere immesso i criteri di ricerca, fare clic sul ![pulsante Aggiorna](../../media/scc-quarantine-refresh.png) **Aggiorna** per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e2b63-163">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="e2b63-164">Dopo aver trovato un messaggio in quarantena specifico, selezionarlo per visualizzarne i dettagli ed eseguire delle operazioni (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="e2b63-164">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="e2b63-165">Esportare i risultati di un messaggio</span><span class="sxs-lookup"><span data-stu-id="e2b63-165">Export message results</span></span>

1. <span data-ttu-id="e2b63-166">Selezionare i messaggi a cui si è interessati e quindi fare clic su **Esporta risultati**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-166">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="e2b63-167">Fare clic su **Sì** nel messaggio di conferma che avverte di tenere aperta la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="e2b63-167">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="e2b63-168">Una volta completata l'esportazione, è possibile assegnare un nome e scegliere il percorso di download per il file .csv.</span><span class="sxs-lookup"><span data-stu-id="e2b63-168">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="e2b63-169">Visualizzare i dettagli dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="e2b63-169">View quarantined message details</span></span>

<span data-ttu-id="e2b63-170">Quando si seleziona un messaggio di posta elettronica nell'elenco, i seguenti dettagli del messaggio vengono visualizzati nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="e2b63-170">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e2b63-171">**ID messaggio**: identificatore univoco globale per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="e2b63-171">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="e2b63-172">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="e2b63-172">**Sender address**</span></span>

- <span data-ttu-id="e2b63-173">**Ricezione**: data/ora di ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e2b63-173">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="e2b63-174">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="e2b63-174">**Subject**</span></span>

- <span data-ttu-id="e2b63-175">**Motivo della quarantena**: indica se un messaggio è stato identificato come **Posta indesiderata**, **Invio in blocco** o **Phishing** (a partire da aprile 2020).</span><span class="sxs-lookup"><span data-stu-id="e2b63-175">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="e2b63-176">**Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **Visualizza intestazione messaggio** per visualizzare l'elenco completo dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="e2b63-176">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="e2b63-177">**Scadenza**: data/ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="e2b63-177">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="e2b63-178">**Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="e2b63-178">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="e2b63-179">**Non ancora rilasciato in**: tutti gli eventuali messaggi di posta elettronica in cui il messaggio non è stato ancora rilasciato.</span><span class="sxs-lookup"><span data-stu-id="e2b63-179">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="e2b63-180">Eseguire azioni sulla posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="e2b63-180">Take action on quarantined email</span></span>

<span data-ttu-id="e2b63-181">Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le operazioni da eseguire con i messaggi nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="e2b63-181">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e2b63-182">**Rilascia messaggio**: nel riquadro a comparsa visualizzato, scegliere se **segnalare i messaggi a Microsoft per l'analisi**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-182">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="e2b63-183">Questa opzione è selezionata per impostazione predefinita e riporta il messaggio messo in quarantena per errore a Microsoft come falso positivo.</span><span class="sxs-lookup"><span data-stu-id="e2b63-183">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="e2b63-184">Al termine, fare clic su **Rilascia messaggio**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-184">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="e2b63-185">**Visualizza intestazione messaggio**: scegliere questo collegamento per vedere il testo dell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e2b63-185">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="e2b63-186">Per analizzare i campi dell'intestazione e i valori in modo approfondito, copiare il testo negli Appunti e poi scegliere **Microsoft Message Header Analyzer** per passare all'Analizzatore connettività remota. Fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si vuole uscire da Microsoft 365 per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="e2b63-186">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="e2b63-187">Incollare l'intestazione del messaggio nella pagina nella sezione Message Header Analyzer e scegliere **Analizza intestazioni**:</span><span class="sxs-lookup"><span data-stu-id="e2b63-187">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="e2b63-188">**Anteprima messaggio**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="e2b63-188">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="e2b63-189">**Visualizzazione origine**: mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.</span><span class="sxs-lookup"><span data-stu-id="e2b63-189">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="e2b63-190">**Visualizzazione testo**: Mostra il corpo del messaggio in testo normale.</span><span class="sxs-lookup"><span data-stu-id="e2b63-190">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="e2b63-191">**Scarica il messaggio**: nel riquadro a comparsa visualizzato, selezionare **Sono consapevole dei rischi associati al download di questo messaggio** per salvare una copia locale del messaggio in formato .eml.</span><span class="sxs-lookup"><span data-stu-id="e2b63-191">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="e2b63-192">**Rimuovi da quarantena**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="e2b63-192">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="e2b63-193">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-193">When you're finished, click **Close**.</span></span>

<span data-ttu-id="e2b63-194">Se il messaggio non viene rilasciato o rimosso, verrà eliminato dopo la scadenza del periodo di conservazione in quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="e2b63-194">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="e2b63-195">Eseguire azioni su più messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="e2b63-195">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="e2b63-196">Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **Azioni in blocco** che consente di eseguire le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="e2b63-196">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e2b63-197">**Rilascia messaggi**: le opzioni sono le stesse del rilascio di un singolo messaggio, ma non è possibile selezionare **Rilascia i messaggi a specifici destinatari**; è possibile selezionare solo **Rilascia il messaggio a tutti i destinatari** o **Rilascia i messaggi ad altre persone**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-197">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="e2b63-198">**Elimina messaggi**: dopo aver fatto clic su **Sì** nell'avviso visualizzato, i messaggi saranno immediatamente eliminati senza essere inviati ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="e2b63-198">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="e2b63-199">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e2b63-199">When you're finished, click **Close**.</span></span>
