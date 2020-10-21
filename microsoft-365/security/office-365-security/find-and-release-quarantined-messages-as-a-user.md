---
title: Trovare e rilasciare messaggi in quarantena come utente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
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
description: Informazioni su come gli utenti possono visualizzare e gestire i messaggi in quarantena in Exchange Online Protection (EOP) che avrebbero dovuto essere recapitati.
ms.openlocfilehash: 2a8e37dc430af5b3d3c47179c721d83832f01184
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600346"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="15b9c-103">Trovare e rilasciare i messaggi messi in quarantena come utente di EOP</span><span class="sxs-lookup"><span data-stu-id="15b9c-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="15b9c-104">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="15b9c-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="15b9c-105">Per altre informazioni, vedere [Quarantena in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="15b9c-105">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="15b9c-106">L'utente può visualizzare, rilasciare ed eliminare i messaggi in quarantena di cui si è destinatari e che sono stati messi in quarantena come posta indesiderata o posta inviata in blocco.</span><span class="sxs-lookup"><span data-stu-id="15b9c-106">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="15b9c-107">A partire da aprile 2020 è possibile visualizzare o eliminare i messaggi di phishing in quarantena, ad esclusione del phishing con alta confidenza, di cui si è destinatari.</span><span class="sxs-lookup"><span data-stu-id="15b9c-107">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="15b9c-108">È possibile visualizzare e gestire i messaggi in quarantena nel Centro sicurezza e conformità oppure, nel caso in cui un amministratore l'abbia configurato, nelle [notifiche di posta indesiderata per l'utente finale](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="15b9c-108">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="15b9c-109">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="15b9c-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="15b9c-110">Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="15b9c-110">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="15b9c-111">Per aprire direttamente la pagina della quarantena, passare a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="15b9c-111">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="15b9c-112">Gli amministratori possono configurare per quanto tempo i messaggi vengono tenuti in quarantena prima di essere eliminati definitivamente (criteri di protezione dalla posta indesiderata).</span><span class="sxs-lookup"><span data-stu-id="15b9c-112">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="15b9c-113">I messaggi scaduti dalla quarantena non sono recuperabili.</span><span class="sxs-lookup"><span data-stu-id="15b9c-113">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="15b9c-114">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="15b9c-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="15b9c-115">Gli amministratori possono anche [abilitare le notifiche di posta indesiderata per l'utente finale](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) nei criteri di protezione dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="15b9c-115">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="15b9c-116">Gli utenti possono rilasciare messaggi di posta indesiderata in quarantena direttamente da queste notifiche.</span><span class="sxs-lookup"><span data-stu-id="15b9c-116">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="15b9c-117">Gli utenti possono rivedere i messaggi di phishing in quarantena, non messaggi di phishing con probabilità elevata, direttamente da queste notifiche.</span><span class="sxs-lookup"><span data-stu-id="15b9c-117">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="15b9c-118">Per altre informazioni, vedere [Notifiche di posta indesiderata per l'utente finale in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="15b9c-118">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="15b9c-119">I messaggi messi in quarantena per alta probabilà di phishing, malware o regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori e non sono visibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="15b9c-119">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="15b9c-120">Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="15b9c-120">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="15b9c-121">È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.</span><span class="sxs-lookup"><span data-stu-id="15b9c-121">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="15b9c-122">Visualizzazione dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="15b9c-122">View your quarantined messages</span></span>

1. <span data-ttu-id="15b9c-123">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-123">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="15b9c-124">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="15b9c-124">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="15b9c-125">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="15b9c-125">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="15b9c-126">I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="15b9c-126">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="15b9c-127">**Ricevuto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15b9c-127">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="15b9c-128">**Mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15b9c-128">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="15b9c-129">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15b9c-129">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="15b9c-130">**Motivo della quarantena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15b9c-130">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="15b9c-131">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15b9c-131">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="15b9c-132">**Tipo di criterio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15b9c-132">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="15b9c-133">**Scadenza**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="15b9c-133">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="15b9c-134">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="15b9c-134">**Recipient**</span></span>

   - <span data-ttu-id="15b9c-135">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="15b9c-135">**Message ID**</span></span>

   - <span data-ttu-id="15b9c-136">**Nome criterio**</span><span class="sxs-lookup"><span data-stu-id="15b9c-136">**Policy name**</span></span>

   - <span data-ttu-id="15b9c-137">**Dimensioni**</span><span class="sxs-lookup"><span data-stu-id="15b9c-137">**Size**</span></span>

   - <span data-ttu-id="15b9c-138">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="15b9c-138">**Direction**</span></span>

   <span data-ttu-id="15b9c-139">Al termine, fare clic su **Salva** o fare clic su **Imposta su valore predefinito**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-139">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="15b9c-140">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-140">To filter the results, click **Filter**.</span></span> <span data-ttu-id="15b9c-141">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="15b9c-141">The available filters are:</span></span>

   - <span data-ttu-id="15b9c-142">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="15b9c-142">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="15b9c-143">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="15b9c-143">**Today**</span></span>

     - <span data-ttu-id="15b9c-144">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="15b9c-144">**Next 2 days**</span></span>

     - <span data-ttu-id="15b9c-145">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="15b9c-145">**Next 7 days**</span></span>

     - <span data-ttu-id="15b9c-146">**Personalizzato**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-146">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="15b9c-147">**Ora ricezione**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-147">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="15b9c-148">**Motivo della quarantena**:</span><span class="sxs-lookup"><span data-stu-id="15b9c-148">**Quarantine reason**:</span></span>

     - <span data-ttu-id="15b9c-149">**Invio in blocco**</span><span class="sxs-lookup"><span data-stu-id="15b9c-149">**Bulk**</span></span>

     - <span data-ttu-id="15b9c-150">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="15b9c-150">**Spam**</span></span>

     - <span data-ttu-id="15b9c-151">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="15b9c-151">**Phish**</span></span>
     
   - <span data-ttu-id="15b9c-152">**Tipo di criteri**: filtrare i messaggi in base al tipo di criteri:</span><span class="sxs-lookup"><span data-stu-id="15b9c-152">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="15b9c-153">**Criteri anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="15b9c-153">**Anti-phish policy**</span></span>
     - <span data-ttu-id="15b9c-154">**Criteri filtro contenuti ospitati**</span><span class="sxs-lookup"><span data-stu-id="15b9c-154">**Hosted content filter policy**</span></span>
     

   <span data-ttu-id="15b9c-155">Per cancellare il filtro, fare clic su **Cancella**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-155">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="15b9c-156">Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-156">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="15b9c-157">Utilizzare **Ordina i risultati per** (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per trovare messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="15b9c-157">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="15b9c-158">I caratteri jolly non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="15b9c-158">Wildcards aren't supported.</span></span> <span data-ttu-id="15b9c-159">È possibile cercare in base ai seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="15b9c-159">You can search by the following values:</span></span>

   - <span data-ttu-id="15b9c-160">**ID messaggio**: identificatore univoco globale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="15b9c-160">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="15b9c-161">Se si seleziona un messaggio nell'elenco, il valore **ID messaggio** viene visualizzato nel riquadro a comparsa **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-161">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="15b9c-162">Gli amministratori possono usare [Traccia messaggio](message-trace-scc.md) per trovare i messaggi e i valori ID messaggio corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="15b9c-162">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="15b9c-163">**Indirizzo di posta elettronica del mittente**: indirizzo di posta elettronica di un singolo mittente.</span><span class="sxs-lookup"><span data-stu-id="15b9c-163">**Sender email address**: A single sender's email address.</span></span>
   
   - <span data-ttu-id="15b9c-164">**Nome dei criteri**: usare l'intero nome dei criteri del messaggio.</span><span class="sxs-lookup"><span data-stu-id="15b9c-164">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="15b9c-165">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="15b9c-165">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="15b9c-166">**Indirizzo di posta elettronica del destinatario**: indirizzo di posta elettronica di un singolo destinatario.</span><span class="sxs-lookup"><span data-stu-id="15b9c-166">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="15b9c-167">**Oggetto**: utilizzare l'intero oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="15b9c-167">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="15b9c-168">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="15b9c-168">The search is not case-sensitive.</span></span>

   <span data-ttu-id="15b9c-169">Dopo avere immesso i criteri di ricerca, fare clic sul ![pulsante Aggiorna](../../media/scc-quarantine-refresh.png) **Aggiorna** per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="15b9c-169">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="15b9c-170">Dopo aver trovato un messaggio in quarantena specifico, selezionarlo per visualizzarne i dettagli ed eseguire delle operazioni (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="15b9c-170">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="15b9c-171">Esportare i risultati di un messaggio</span><span class="sxs-lookup"><span data-stu-id="15b9c-171">Export message results</span></span>

1. <span data-ttu-id="15b9c-172">Selezionare i messaggi a cui si è interessati e quindi fare clic su **Esporta risultati**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-172">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="15b9c-173">Fare clic su **Sì** nel messaggio di conferma che avverte di tenere aperta la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="15b9c-173">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="15b9c-174">Una volta completata l'esportazione, è possibile assegnare un nome e scegliere il percorso di download per il file .csv.</span><span class="sxs-lookup"><span data-stu-id="15b9c-174">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="15b9c-175">Visualizzare i dettagli dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="15b9c-175">View quarantined message details</span></span>

<span data-ttu-id="15b9c-176">Quando si seleziona un messaggio di posta elettronica nell'elenco, i seguenti dettagli del messaggio vengono visualizzati nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="15b9c-176">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="15b9c-177">**ID messaggio**: identificatore univoco globale per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="15b9c-177">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="15b9c-178">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="15b9c-178">**Sender address**</span></span>

- <span data-ttu-id="15b9c-179">**Ricezione**: data/ora di ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="15b9c-179">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="15b9c-180">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="15b9c-180">**Subject**</span></span>

- <span data-ttu-id="15b9c-181">**Motivo quarantena**: indica se un messaggio è stato identificato come **Posta indesiderata**, **Invio in blocco** o **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-181">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>

- <span data-ttu-id="15b9c-182">**Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **Visualizza intestazione messaggio** per visualizzare l'elenco completo dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="15b9c-182">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="15b9c-183">**Scadenza**: data/ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="15b9c-183">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="15b9c-184">**Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="15b9c-184">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="15b9c-185">**Non ancora rilasciato in**: tutti gli eventuali messaggi di posta elettronica in cui il messaggio non è stato ancora rilasciato.</span><span class="sxs-lookup"><span data-stu-id="15b9c-185">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="15b9c-186">Eseguire azioni sulla posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="15b9c-186">Take action on quarantined email</span></span>

<span data-ttu-id="15b9c-187">Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le operazioni da eseguire con i messaggi nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="15b9c-187">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="15b9c-188">**Rilascia messaggio**: nel riquadro a comparsa visualizzato, scegliere se **segnalare i messaggi a Microsoft per l'analisi**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-188">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="15b9c-189">Questa opzione è selezionata per impostazione predefinita e riporta il messaggio messo in quarantena per errore a Microsoft come falso positivo.</span><span class="sxs-lookup"><span data-stu-id="15b9c-189">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="15b9c-190">Al termine, fare clic su **Rilascia messaggio**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-190">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="15b9c-191">**Visualizza intestazione messaggio**: scegliere questo collegamento per vedere il testo dell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="15b9c-191">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="15b9c-192">Per analizzare i campi dell'intestazione e i valori in modo approfondito, copiare il testo negli Appunti e poi scegliere **Microsoft Message Header Analyzer** per passare all'Analizzatore connettività remota. Fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si vuole uscire da Microsoft 365 per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="15b9c-192">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="15b9c-193">Incollare l'intestazione del messaggio nella pagina nella sezione Message Header Analyzer e scegliere **Analizza intestazioni**:</span><span class="sxs-lookup"><span data-stu-id="15b9c-193">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="15b9c-194">**Anteprima messaggio**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="15b9c-194">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="15b9c-195">**Visualizzazione origine**: mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.</span><span class="sxs-lookup"><span data-stu-id="15b9c-195">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="15b9c-196">**Visualizzazione testo**: Mostra il corpo del messaggio in testo normale.</span><span class="sxs-lookup"><span data-stu-id="15b9c-196">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="15b9c-197">**Scarica il messaggio**: nel riquadro a comparsa visualizzato, selezionare **Sono consapevole dei rischi associati al download di questo messaggio** per salvare una copia locale del messaggio in formato .eml.</span><span class="sxs-lookup"><span data-stu-id="15b9c-197">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="15b9c-198">**Rimuovi da quarantena**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="15b9c-198">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="15b9c-199">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-199">When you're finished, click **Close**.</span></span>

<span data-ttu-id="15b9c-200">Se il messaggio non viene rilasciato o rimosso, verrà eliminato dopo la scadenza del periodo di conservazione in quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="15b9c-200">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="15b9c-201">Eseguire azioni su più messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="15b9c-201">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="15b9c-202">Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **Azioni in blocco** che consente di eseguire le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="15b9c-202">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="15b9c-203">**Rilascia messaggi**: le opzioni sono le stesse del rilascio di un singolo messaggio, ma non è possibile selezionare **Rilascia i messaggi a specifici destinatari**; è possibile selezionare solo **Rilascia il messaggio a tutti i destinatari** o **Rilascia i messaggi ad altre persone**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-203">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="15b9c-204">**Elimina messaggi**: dopo aver fatto clic su **Sì** nell'avviso visualizzato, i messaggi saranno immediatamente eliminati senza essere inviati ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="15b9c-204">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="15b9c-205">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="15b9c-205">When you're finished, click **Close**.</span></span>
