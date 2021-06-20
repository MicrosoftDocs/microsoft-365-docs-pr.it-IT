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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c0f95561977c453d7040d84ba0c779c3d33e07f0
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029826"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="1da59-103">Trovare e rilasciare i messaggi messi in quarantena come utente di EOP</span><span class="sxs-lookup"><span data-stu-id="1da59-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1da59-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="1da59-104">**Applies to**</span></span>
- [<span data-ttu-id="1da59-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1da59-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1da59-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="1da59-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1da59-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1da59-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1da59-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="1da59-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="1da59-109">Per altre informazioni, vedere [Quarantena in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="1da59-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="1da59-110">Come destinatario di un messaggio in quarantena, le operazioni che è possibile eseguire per il messaggio come utente non amministratore sono descritte nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="1da59-110">As a recipient of a quarantined message, what you can do to the message as a non-admin user is described in the following table:</span></span>

<br>

****

|<span data-ttu-id="1da59-111">Motivo della quarantena</span><span class="sxs-lookup"><span data-stu-id="1da59-111">Quarantine reason</span></span>|<span data-ttu-id="1da59-112">Visualizzare</span><span class="sxs-lookup"><span data-stu-id="1da59-112">View</span></span>|<span data-ttu-id="1da59-113">Rilascia</span><span class="sxs-lookup"><span data-stu-id="1da59-113">Release</span></span>|<span data-ttu-id="1da59-114">Elimina</span><span class="sxs-lookup"><span data-stu-id="1da59-114">Delete</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="1da59-115">Invio in blocco</span><span class="sxs-lookup"><span data-stu-id="1da59-115">Bulk</span></span>|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="1da59-119">Posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="1da59-119">Spam</span></span>|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|![Segno di spunta](../../media/checkmark.png)|
|<span data-ttu-id="1da59-123">Phising (non phishing con alta confidenza)</span><span class="sxs-lookup"><span data-stu-id="1da59-123">Phishing (not high confidence phishing)</span></span>|![Segno di spunta](../../media/checkmark.png)||![Segno di spunta](../../media/checkmark.png)|
|

<span data-ttu-id="1da59-126">È possibile visualizzare e gestire i messaggi in quarantena nel Portale di Microsoft 365 Defender o, nel caso in cui un amministratore l'abbia configurato, nelle [notifiche di posta indesiderata per l'utente finale](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="1da59-126">You view and manage your quarantined messages in the Microsoft 365 Defender portal or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1da59-127">Informazioni necessarie prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1da59-127">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1da59-128">Per aprire il portale di Microsoft 365 Defender, andare a <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="1da59-128">To open the Microsoft 365 Defender portal, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="1da59-129">Per aprire direttamente la pagina della quarantena, passare a <https://security.microsoft.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="1da59-129">To open the Quarantine page directly, go to <https://security.microsoft.com/quarantine>.</span></span>

- <span data-ttu-id="1da59-130">Gli amministratori possono configurare per quanto tempo i messaggi vengono tenuti in quarantena prima di essere eliminati definitivamente nei criteri di protezione dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="1da59-130">Admins can configure how long messages are kept in quarantine before they're permanently deleted in anti-spam policies.</span></span> <span data-ttu-id="1da59-131">I messaggi scaduti dalla quarantena non sono recuperabili.</span><span class="sxs-lookup"><span data-stu-id="1da59-131">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="1da59-132">Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1da59-132">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="1da59-133">Gli amministratori possono anche [abilitare le notifiche di posta indesiderata per l'utente finale](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) nei criteri di protezione dalla posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="1da59-133">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="1da59-134">Gli utenti possono rilasciare messaggi di posta indesiderata in quarantena direttamente da queste notifiche.</span><span class="sxs-lookup"><span data-stu-id="1da59-134">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="1da59-135">Gli utenti possono rivedere i messaggi di phishing in quarantena, non messaggi di phishing con probabilità elevata, direttamente da queste notifiche.</span><span class="sxs-lookup"><span data-stu-id="1da59-135">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="1da59-136">Per altre informazioni, vedere [Notifiche di posta indesiderata per l'utente finale in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="1da59-136">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="1da59-137">I messaggi messi in quarantena per alta probabilà di phishing, malware o regole del flusso di posta (note anche come regole di trasporto) sono disponibili solo per gli amministratori e non sono visibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="1da59-137">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="1da59-138">Per altre informazioni, vedere [Gestione dei messaggi e dei file in quarantena come amministratore in EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="1da59-138">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="1da59-139">È possibile rilasciare un messaggio e segnalarlo come falso positivo (non indesiderato) solo una volta.</span><span class="sxs-lookup"><span data-stu-id="1da59-139">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="1da59-140">Visualizzazione dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="1da59-140">View your quarantined messages</span></span>

1. <span data-ttu-id="1da59-141">Nel portale di Microsoft 365 Defender, passare a **Posta elettronica e collaborazione** \> **Rivedi**\> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="1da59-141">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="1da59-142">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="1da59-142">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="1da59-143">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="1da59-143">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="1da59-144">I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="1da59-144">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="1da59-145">**Ricevuto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1da59-145">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="1da59-146">**Mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1da59-146">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="1da59-147">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1da59-147">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="1da59-148">**Motivo della quarantena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1da59-148">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="1da59-149">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1da59-149">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="1da59-150">**Tipo di criterio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1da59-150">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="1da59-151">**Scadenza**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="1da59-151">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="1da59-152">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="1da59-152">**Recipient**</span></span>
   - <span data-ttu-id="1da59-153">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="1da59-153">**Message ID**</span></span>
   - <span data-ttu-id="1da59-154">**Nome criterio**</span><span class="sxs-lookup"><span data-stu-id="1da59-154">**Policy name**</span></span>
   - <span data-ttu-id="1da59-155">**Dimensioni**</span><span class="sxs-lookup"><span data-stu-id="1da59-155">**Size**</span></span>
   - <span data-ttu-id="1da59-156">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="1da59-156">**Direction**</span></span>

   <span data-ttu-id="1da59-157">Al termine, fare clic su **Salva** o fare clic su **Imposta su valore predefinito**.</span><span class="sxs-lookup"><span data-stu-id="1da59-157">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="1da59-158">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="1da59-158">To filter the results, click **Filter**.</span></span> <span data-ttu-id="1da59-159">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="1da59-159">The available filters are:</span></span>

   - <span data-ttu-id="1da59-160">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="1da59-160">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="1da59-161">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="1da59-161">**Today**</span></span>
     - <span data-ttu-id="1da59-162">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="1da59-162">**Next 2 days**</span></span>
     - <span data-ttu-id="1da59-163">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="1da59-163">**Next 7 days**</span></span>
     - <span data-ttu-id="1da59-164">**Personalizzato**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="1da59-164">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="1da59-165">**Ora ricezione**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="1da59-165">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="1da59-166">**Motivo della quarantena**:</span><span class="sxs-lookup"><span data-stu-id="1da59-166">**Quarantine reason**:</span></span>
     - <span data-ttu-id="1da59-167">**Invio in blocco**</span><span class="sxs-lookup"><span data-stu-id="1da59-167">**Bulk**</span></span>
     - <span data-ttu-id="1da59-168">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="1da59-168">**Spam**</span></span>
     - <span data-ttu-id="1da59-169">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="1da59-169">**Phish**</span></span>

   - <span data-ttu-id="1da59-170">**Tipo di criteri**: filtrare i messaggi in base al tipo di criteri:</span><span class="sxs-lookup"><span data-stu-id="1da59-170">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="1da59-171">**Criteri antimalware**</span><span class="sxs-lookup"><span data-stu-id="1da59-171">**Anti-malware policy**</span></span>
     - <span data-ttu-id="1da59-172">**Criteri Allegati sicuri** (Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="1da59-172">**Safe Attachments policy** (Defender for Office 365)</span></span>
     - <span data-ttu-id="1da59-173">**Criteri anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="1da59-173">**Anti-phish policy**</span></span>
     - <span data-ttu-id="1da59-174">**Criteri filtro contenuti ospitati** (criteri di protezione dalla posta indesiderata)</span><span class="sxs-lookup"><span data-stu-id="1da59-174">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="1da59-175">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="1da59-175">**Transport rule**</span></span>

     <sup>\*</sup>

   <span data-ttu-id="1da59-176">Per cancellare il filtro, fare clic su **Cancella**.</span><span class="sxs-lookup"><span data-stu-id="1da59-176">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="1da59-177">Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="1da59-177">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="1da59-178">Utilizzare **Ordina i risultati per** (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per trovare messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="1da59-178">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="1da59-179">I caratteri jolly non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="1da59-179">Wildcards aren't supported.</span></span> <span data-ttu-id="1da59-180">È possibile cercare in base ai seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="1da59-180">You can search by the following values:</span></span>

   - <span data-ttu-id="1da59-181">**ID messaggio**: identificatore univoco globale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1da59-181">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="1da59-182">Se si seleziona un messaggio nell'elenco, il valore **ID messaggio** viene visualizzato nel riquadro a comparsa **Dettagli**.</span><span class="sxs-lookup"><span data-stu-id="1da59-182">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="1da59-183">Gli amministratori possono usare [Traccia messaggio](message-trace-scc.md) per trovare i messaggi e i valori ID messaggio corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="1da59-183">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>
   - <span data-ttu-id="1da59-184">**Indirizzo di posta elettronica del mittente**: indirizzo di posta elettronica di un singolo mittente.</span><span class="sxs-lookup"><span data-stu-id="1da59-184">**Sender email address**: A single sender's email address.</span></span>
   - <span data-ttu-id="1da59-185">**Nome dei criteri**: usare l'intero nome dei criteri del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1da59-185">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="1da59-186">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="1da59-186">The search is not case-sensitive.</span></span>
   - <span data-ttu-id="1da59-187">**Indirizzo di posta elettronica del destinatario**: indirizzo di posta elettronica di un singolo destinatario.</span><span class="sxs-lookup"><span data-stu-id="1da59-187">**Recipient email address**: A single recipient's email address.</span></span>
   - <span data-ttu-id="1da59-188">**Oggetto**: utilizzare l'intero oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1da59-188">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="1da59-189">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="1da59-189">The search is not case-sensitive.</span></span>

   <span data-ttu-id="1da59-190">Dopo avere immesso i criteri di ricerca, fare clic sul ![pulsante Aggiorna](../../media/scc-quarantine-refresh.png) **Aggiorna** per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="1da59-190">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="1da59-191">Dopo aver trovato un messaggio in quarantena specifico, selezionarlo per visualizzarne i dettagli ed eseguire delle operazioni (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="1da59-191">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="1da59-192">Esportare i risultati di un messaggio</span><span class="sxs-lookup"><span data-stu-id="1da59-192">Export message results</span></span>

1. <span data-ttu-id="1da59-193">Selezionare i messaggi a cui si è interessati e quindi fare clic su **Esporta risultati**.</span><span class="sxs-lookup"><span data-stu-id="1da59-193">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="1da59-194">Fare clic su **Sì** nel messaggio di conferma che avverte di tenere aperta la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="1da59-194">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="1da59-195">Una volta completata l'esportazione, è possibile assegnare un nome e scegliere il percorso di download per il file .csv.</span><span class="sxs-lookup"><span data-stu-id="1da59-195">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="1da59-196">Visualizzare i dettagli dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="1da59-196">View quarantined message details</span></span>

<span data-ttu-id="1da59-197">Quando si seleziona un messaggio di posta elettronica nell'elenco, i seguenti dettagli del messaggio vengono visualizzati nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="1da59-197">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="1da59-198">**ID messaggio**: identificatore univoco globale per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="1da59-198">**Message ID**: The globally unique identifier for the message.</span></span>
- <span data-ttu-id="1da59-199">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="1da59-199">**Sender address**</span></span>
- <span data-ttu-id="1da59-200">**Ricezione**: data/ora di ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1da59-200">**Received**: The date/time when the message was received.</span></span>
- <span data-ttu-id="1da59-201">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="1da59-201">**Subject**</span></span>
- <span data-ttu-id="1da59-202">**Motivo quarantena**: indica se un messaggio è stato identificato come **Posta indesiderata**, **Invio in blocco** o **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="1da59-202">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>
- <span data-ttu-id="1da59-203">**Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **Visualizza intestazione messaggio** per visualizzare l'elenco completo dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="1da59-203">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>
- <span data-ttu-id="1da59-204">**Scadenza**: data/ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="1da59-204">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>
- <span data-ttu-id="1da59-205">**Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="1da59-205">**Released to**: All email addresses (if any) to which the message has been released.</span></span>
- <span data-ttu-id="1da59-206">**Non ancora rilasciato in**: tutti gli eventuali messaggi di posta elettronica in cui il messaggio non è stato ancora rilasciato.</span><span class="sxs-lookup"><span data-stu-id="1da59-206">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="1da59-207">Eseguire azioni sulla posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="1da59-207">Take action on quarantined email</span></span>

<span data-ttu-id="1da59-208">Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le operazioni da eseguire con i messaggi nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="1da59-208">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="1da59-209">**Rilascia messaggio**: nel riquadro a comparsa visualizzato, scegliere se **segnalare i messaggi a Microsoft per l'analisi**.</span><span class="sxs-lookup"><span data-stu-id="1da59-209">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="1da59-210">Questa opzione è selezionata per impostazione predefinita e riporta il messaggio messo in quarantena per errore a Microsoft come falso positivo.</span><span class="sxs-lookup"><span data-stu-id="1da59-210">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="1da59-211">Al termine, fare clic su **Rilascia messaggio**.</span><span class="sxs-lookup"><span data-stu-id="1da59-211">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="1da59-212">**Visualizza intestazione messaggio**: scegliere questo collegamento per vedere il testo dell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1da59-212">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="1da59-213">Per analizzare i campi dell'intestazione e i valori in modo approfondito, copiare il testo negli Appunti e poi scegliere **Microsoft Message Header Analyzer** per passare all'Analizzatore connettività remota. Fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si vuole uscire da Microsoft 365 per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="1da59-213">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="1da59-214">Incollare l'intestazione del messaggio nella pagina nella sezione Message Header Analyzer e scegliere **Analizza intestazioni**:</span><span class="sxs-lookup"><span data-stu-id="1da59-214">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="1da59-215">**Anteprima messaggio**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="1da59-215">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="1da59-216">**Visualizzazione origine**: mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.</span><span class="sxs-lookup"><span data-stu-id="1da59-216">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="1da59-217">**Visualizzazione testo**: Mostra il corpo del messaggio in testo normale.</span><span class="sxs-lookup"><span data-stu-id="1da59-217">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="1da59-218">**Rimuovi da quarantena**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente.</span><span class="sxs-lookup"><span data-stu-id="1da59-218">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

- <span data-ttu-id="1da59-219">**Blocca mittente**: aggiungere il mittente all'elenco Mittenti bloccati della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="1da59-219">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="1da59-220">Per ulteriori informazioni, vedere [Blocca mittente di posta](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="1da59-220">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="1da59-221">Aggiungere il mittente all'elenco Mittenti bloccati della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="1da59-221">Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="1da59-222">Per ulteriori informazioni, vedere [Blocca mittente di posta](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="1da59-222">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

<span data-ttu-id="1da59-223">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="1da59-223">When you're finished, click **Close**.</span></span>

<span data-ttu-id="1da59-224">Se il messaggio non viene rilasciato o rimosso, verrà eliminato dopo la scadenza del periodo di conservazione in quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="1da59-224">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="1da59-225">Eseguire azioni su più messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="1da59-225">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="1da59-226">Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **Azioni in blocco** che consente di eseguire le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="1da59-226">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="1da59-227">**Rilascia messaggi**: le opzioni sono le stesse del rilascio di un singolo messaggio, ma non è possibile selezionare **Rilascia i messaggi a specifici destinatari**; è possibile selezionare solo **Rilascia il messaggio a tutti i destinatari** o **Rilascia i messaggi ad altre persone**.</span><span class="sxs-lookup"><span data-stu-id="1da59-227">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>
- <span data-ttu-id="1da59-228">**Elimina messaggi**: dopo aver fatto clic su **Sì** nell'avviso visualizzato, i messaggi saranno immediatamente eliminati senza essere inviati ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="1da59-228">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="1da59-229">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="1da59-229">When you're finished, click **Close**.</span></span>
