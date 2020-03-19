---
title: Gestire i messaggi e i file in quarantena come amministratore in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: Gli amministratori possono visualizzare, rilasciare ed eliminare tutti i tipi di messaggi in quarantena per tutti gli utenti. Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena come malware, phishing ad alta sicurezza o come risultato delle regole del flusso di posta (regole di trasporto).
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857074"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a><span data-ttu-id="12368-104">Gestire i messaggi e i file in quarantena come amministratore in Office 365</span><span class="sxs-lookup"><span data-stu-id="12368-104">Manage quarantined messages and files as an admin in Office 365</span></span>

<span data-ttu-id="12368-105">La quarantena contiene messaggi potenzialmente pericolosi o indesiderati in Office 365 organizzazioni con cassette postali in Exchange Online o standalone Exchange Online Protection (EOP) organizzazioni senza cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="12368-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="12368-106">Per ulteriori informazioni, vedere [Quarantine in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="12368-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="12368-107">Gli amministratori possono visualizzare, rilasciare ed eliminare tutti i tipi di messaggi in quarantena per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="12368-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="12368-108">Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena come malware, phishing ad alta sicurezza o come risultato delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="12368-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="12368-109">Gli amministratori possono anche segnalare falsi positivi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="12368-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="12368-110">Gli amministratori nelle organizzazioni con Office 365 Advance Threat Protection (ATP) possono anche visualizzare, scaricare ed eliminare i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="12368-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="12368-111">È possibile visualizzare e gestire i messaggi in quarantena nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per i clienti di Office 365; PowerShell di Exchange Online Protection per clienti EOP autonomi.</span><span class="sxs-lookup"><span data-stu-id="12368-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="12368-112">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="12368-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="12368-113">Per aprire il centro conformità & sicurezza di Office 365, passare <https://protection.office.com>a.</span><span class="sxs-lookup"><span data-stu-id="12368-113">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="12368-114">Per aprire direttamente la pagina di quarantena, andare <https://protection.office.com/quarantine>a.</span><span class="sxs-lookup"><span data-stu-id="12368-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="12368-115">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="12368-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="12368-116">Per connettersi a PowerShell di Exchange Online Protection, vedere [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="12368-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="12368-117">È necessario disporre delle autorizzazioni prima di poter gestire la quarantena come amministratore. Le autorizzazioni sono controllate dal ruolo **Quarantine** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="12368-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="12368-118">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli **Gestione organizzazione** (amministratori globali), **amministratori della quarantena**e **amministratore della sicurezza** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="12368-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="12368-119">Per ulteriori informazioni, vedere [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="12368-119">For more information, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="12368-120">I messaggi in quarantena vengono mantenuti per un periodo di tempo predefinito prima di essere eliminati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="12368-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="12368-121">Messaggi in quarantena da criteri di protezione da posta indesiderata (posta indesiderata, phishing e posta elettronica in blocco): 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="12368-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="12368-122">Questo è il valore predefinito e massimo.</span><span class="sxs-lookup"><span data-stu-id="12368-122">This is the default and maximum value.</span></span> <span data-ttu-id="12368-123">Per configurare questo valore, vedere [configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="12368-123">To configure this value, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="12368-124">Messaggi messi in quarantena dalle regole del flusso di posta (l'azione della regola è **recapitare il messaggio alla quarantena ospitata**): 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="12368-124">Messages quarantined by mail flow rules (the rule action is **Deliver the message to the hosted quarantine**): 30 days.</span></span> <span data-ttu-id="12368-125">Non è possibile modificare questo valore.</span><span class="sxs-lookup"><span data-stu-id="12368-125">You can't change this value.</span></span>

  - <span data-ttu-id="12368-126">Messaggi contenenti malware: 15 giorni.</span><span class="sxs-lookup"><span data-stu-id="12368-126">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="12368-127">Quando un messaggio scade dalla quarantena, non è possibile ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="12368-127">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="12368-128">Utilizzare il Centro sicurezza & conformità per gestire i messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="12368-128">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="12368-129">Visualizzazione posta in quarantena</span><span class="sxs-lookup"><span data-stu-id="12368-129">View quarantined email</span></span>

1. <span data-ttu-id="12368-130">Nel centro sicurezza e conformità, passare alla **quarantena**di **Verifica** \> **della gestione** \> delle minacce.</span><span class="sxs-lookup"><span data-stu-id="12368-130">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="12368-131">Verificare che la **visualizzazione in quarantena** sia impostata sul valore predefinito **e-mail**.</span><span class="sxs-lookup"><span data-stu-id="12368-131">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="12368-132">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="12368-132">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="12368-133">Fare clic su **modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="12368-133">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="12368-134">I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="12368-134">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="12368-135">**Ricevuto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-135">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-136">**Mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-136">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-137">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-137">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-138">**Motivo della quarantena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-138">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-139">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-139">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-140">**Tipo di criterio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-140">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-141">**Scade**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-141">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-142">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="12368-142">**Recipient**</span></span>

   - <span data-ttu-id="12368-143">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="12368-143">**Message ID**</span></span>

   - <span data-ttu-id="12368-144">**Nome criterio**</span><span class="sxs-lookup"><span data-stu-id="12368-144">**Policy name**</span></span>

   - <span data-ttu-id="12368-145">**Dimensioni**</span><span class="sxs-lookup"><span data-stu-id="12368-145">**Size**</span></span>

   - <span data-ttu-id="12368-146">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="12368-146">**Direction**</span></span>

   <span data-ttu-id="12368-147">Al termine, fare clic su **Salva**o su **Imposta come predefinito**.</span><span class="sxs-lookup"><span data-stu-id="12368-147">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="12368-148">Per filtrare i risultati, fare clic su **filtro**.</span><span class="sxs-lookup"><span data-stu-id="12368-148">To filter the results, click **Filter**.</span></span> <span data-ttu-id="12368-149">I filtri disponibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="12368-149">The available filters are:</span></span>

   - <span data-ttu-id="12368-150">**Scade il tempo**: filtrare i messaggi quando scadranno dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="12368-150">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="12368-151">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="12368-151">**Today**</span></span>

     - <span data-ttu-id="12368-152">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="12368-152">**Next 2 days**</span></span>

     - <span data-ttu-id="12368-153">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="12368-153">**Next 7 days**</span></span>

     - <span data-ttu-id="12368-154">**Personalizzato**: immettere una data di **inizio** e una **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="12368-154">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="12368-155">**Tempo ricevuto**: immettere una data di **inizio** e una **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="12368-155">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="12368-156">**Motivo della quarantena**:</span><span class="sxs-lookup"><span data-stu-id="12368-156">**Quarantine reason**:</span></span>

     - <span data-ttu-id="12368-157">**Criterio**: il messaggio corrisponde alle condizioni di una regola del flusso di posta (nota anche come regola di trasporto).</span><span class="sxs-lookup"><span data-stu-id="12368-157">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="12368-158">**Bulk**</span><span class="sxs-lookup"><span data-stu-id="12368-158">**Bulk**</span></span>

     - <span data-ttu-id="12368-159">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="12368-159">**Phish**</span></span>

     - <span data-ttu-id="12368-160">**Malware**</span><span class="sxs-lookup"><span data-stu-id="12368-160">**Malware**</span></span>

     - <span data-ttu-id="12368-161">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="12368-161">**Spam**</span></span>

     - <span data-ttu-id="12368-162">**Phishing ad alta sicurezza**</span><span class="sxs-lookup"><span data-stu-id="12368-162">**High Confidence Phish**</span></span>

   - <span data-ttu-id="12368-163">**Destinatario di posta elettronica**: tutti gli utenti o solo i messaggi inviati all'utente.</span><span class="sxs-lookup"><span data-stu-id="12368-163">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="12368-164">Gli utenti finali possono gestire solo i messaggi in quarantena inviati.</span><span class="sxs-lookup"><span data-stu-id="12368-164">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="12368-165">Per cancellare il filtro, fare clic su **Pulisci**.</span><span class="sxs-lookup"><span data-stu-id="12368-165">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="12368-166">Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtra** .</span><span class="sxs-lookup"><span data-stu-id="12368-166">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="12368-167">Utilizzare i **risultati di ordinamento** per (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per individuare messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="12368-167">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="12368-168">I caratteri jolly non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="12368-168">Wildcards aren't supported.</span></span> <span data-ttu-id="12368-169">È possibile eseguire una ricerca in base ai valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="12368-169">You can search by the following values:</span></span>

   - <span data-ttu-id="12368-170">**ID messaggio**: identificatore univoco globale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="12368-170">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="12368-171">Ad esempio, è stata utilizzata la [traccia dei messaggi](message-trace-scc.md) per cercare un messaggio che è stato inviato a un utente nell'organizzazione e si determina che il messaggio è stato messo in quarantena invece di essere recapitato.</span><span class="sxs-lookup"><span data-stu-id="12368-171">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="12368-172">Assicurarsi di includere il valore dell'ID messaggio completo, che può includere parentesi angolari\<\>().</span><span class="sxs-lookup"><span data-stu-id="12368-172">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="12368-173">Ad esempio: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="12368-173">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="12368-174">**Indirizzo di posta elettronica del mittente**: l'indirizzo di posta elettronica di un singolo mittente.</span><span class="sxs-lookup"><span data-stu-id="12368-174">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="12368-175">**Indirizzo di posta elettronica del destinatario**: l'indirizzo di posta elettronica di un singolo destinatario.</span><span class="sxs-lookup"><span data-stu-id="12368-175">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="12368-176">**Oggetto**: utilizzare l'intero oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="12368-176">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="12368-177">La ricerca non è con distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="12368-177">The search is not case-sensitive.</span></span>

   <span data-ttu-id="12368-178">Dopo aver immesso i criteri di ricerca, ![fare clic](../media/scc-quarantine-refresh.png) su **Aggiorna pulsante di aggiornamento per** filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="12368-178">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="12368-179">Dopo aver individuato uno specifico messaggio in quarantena, selezionare il messaggio per visualizzarne i dettagli e per intervenire su di esso (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="12368-179">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="12368-180">Esportare i risultati dei messaggi</span><span class="sxs-lookup"><span data-stu-id="12368-180">Export message results</span></span>

1. <span data-ttu-id="12368-181">Selezionare i messaggi a cui si è interessati e fare clic su **Esporta risultati**.</span><span class="sxs-lookup"><span data-stu-id="12368-181">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="12368-182">Fare clic su **Sì** nel messaggio di conferma che avvisa di mantenere aperta la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="12368-182">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="12368-183">Quando l'esportazione è pronta, è possibile assegnare un nome e scegliere il percorso di download del file. csv.</span><span class="sxs-lookup"><span data-stu-id="12368-183">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="12368-184">Visualizzare i dettagli dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="12368-184">View quarantined message details</span></span>

<span data-ttu-id="12368-185">Quando si seleziona un messaggio di posta elettronica nell'elenco, nel riquadro a comparsa dei **Dettagli** vengono visualizzati i dettagli del messaggio seguenti:</span><span class="sxs-lookup"><span data-stu-id="12368-185">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="12368-186">**ID messaggio**: identificatore univoco globale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="12368-186">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="12368-187">**Indirizzo mittente**</span><span class="sxs-lookup"><span data-stu-id="12368-187">**Sender address**</span></span>

- <span data-ttu-id="12368-188">**Received**: la data e l'ora in cui il messaggio è stato ricevuto.</span><span class="sxs-lookup"><span data-stu-id="12368-188">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="12368-189">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="12368-189">**Subject**</span></span>

- <span data-ttu-id="12368-190">**Motivo della quarantena**: indica se un messaggio è stato identificato come **posta indesiderata**, in **blocco**, **phishing**, corrisponde a una regola del flusso di posta (**regola di trasporto**) oppure è stato identificato come contenente **malware**.</span><span class="sxs-lookup"><span data-stu-id="12368-190">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="12368-191">**Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **visualizzare l'intestazione del messaggio** per visualizzare l'elenco completo dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="12368-191">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="12368-192">**Scade**: la data e l'ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="12368-192">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="12368-193">**Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="12368-193">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="12368-194">**Non ancora rilasciato**: tutti gli indirizzi di posta elettronica (se presenti) a cui il messaggio non è stato ancora rilasciato.</span><span class="sxs-lookup"><span data-stu-id="12368-194">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="12368-195">Eseguire un'azione sulla posta in quarantena</span><span class="sxs-lookup"><span data-stu-id="12368-195">Take action on quarantined email</span></span>

<span data-ttu-id="12368-196">Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le operazioni da eseguire con i messaggi nel riquadro a comparsa dei **Dettagli** :</span><span class="sxs-lookup"><span data-stu-id="12368-196">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="12368-197">**Rilascia messaggio**: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="12368-197">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="12368-198">**Segnalare i messaggi a Microsoft per l'analisi**: è selezionata per impostazione predefinita e segnala il messaggio in quarantena erroneamente a Microsoft come falso positivo.</span><span class="sxs-lookup"><span data-stu-id="12368-198">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="12368-199">Se il messaggio è stato messo in quarantena come posta indesiderata, rinfusa, phishing o contenente malware, il messaggio viene segnalato anche al team di analisi di posta indesiderata di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="12368-199">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="12368-200">A seconda dell'analisi, è possibile modificare le regole di filtro per la posta indesiderata a livello di servizio per consentire il passaggio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="12368-200">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="12368-201">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="12368-201">Choose one of the following options:</span></span>

    - <span data-ttu-id="12368-202">**Rilasciare messaggi a tutti i destinatari**</span><span class="sxs-lookup"><span data-stu-id="12368-202">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="12368-203">**Rilasciare messaggi a destinatari specifici**</span><span class="sxs-lookup"><span data-stu-id="12368-203">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="12368-204">**Rilasciare messaggi ad altri utenti**</span><span class="sxs-lookup"><span data-stu-id="12368-204">**Release messages to other people**</span></span>

  <span data-ttu-id="12368-205">Al termine, fare clic su **rilascia messaggi**.</span><span class="sxs-lookup"><span data-stu-id="12368-205">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="12368-206">Note sul rilascio dei messaggi:</span><span class="sxs-lookup"><span data-stu-id="12368-206">Notes about releasing messages:</span></span>

  - <span data-ttu-id="12368-207">Non è possibile rilasciare un messaggio allo stesso destinatario più di una volta.</span><span class="sxs-lookup"><span data-stu-id="12368-207">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="12368-208">Solo i destinatari che non hanno ricevuto il messaggio verranno visualizzati nell'elenco dei destinatari potenziali.</span><span class="sxs-lookup"><span data-stu-id="12368-208">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="12368-209">**Visualizza intestazione messaggio**: scegliere questo collegamento per visualizzare il testo dell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="12368-209">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="12368-210">Per analizzare i campi e i valori di intestazione in profondità, copiare il testo dell'intestazione del messaggio negli Appunti e quindi scegliere **analizzatore intestazione messaggio Microsoft** per accedere all'analizzatore connettività remota (fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si desidera lasciare Office 365 per completare questa attività).</span><span class="sxs-lookup"><span data-stu-id="12368-210">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="12368-211">Incollare l'intestazione del messaggio nella pagina nella sezione Analizzatore intestazioni del messaggio e scegliere **Analyze Headers**:</span><span class="sxs-lookup"><span data-stu-id="12368-211">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="12368-212">**Messaggio di anteprima**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="12368-212">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="12368-213">**Visualizzazione origine**: Mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.</span><span class="sxs-lookup"><span data-stu-id="12368-213">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="12368-214">**Visualizzazione testo**: Mostra il corpo del messaggio in formato testo normale.</span><span class="sxs-lookup"><span data-stu-id="12368-214">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="12368-215">**Rimuovi dalla quarantena**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente senza essere inviato ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="12368-215">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="12368-216">**Scarica messaggio**: nel riquadro a comparsa visualizzato, selezionare i **rischi per il download di questo messaggio** per salvare una copia locale del messaggio in formato. eml.</span><span class="sxs-lookup"><span data-stu-id="12368-216">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="12368-217">**Invia messaggio**: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="12368-217">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="12368-218">**Tipo di oggetto**: **posta elettronica** (impostazione predefinita), **URL**o **allegato**.</span><span class="sxs-lookup"><span data-stu-id="12368-218">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="12368-219">**Formato di invio**: **ID messaggio di rete** (impostazione predefinita, con il valore corrispondente nella casella **ID messaggio di rete** ) oppure **file** (passare a un file local. eml o. msg).</span><span class="sxs-lookup"><span data-stu-id="12368-219">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="12368-220">Si noti che se si seleziona **file** e quindi si seleziona **ID messaggio di rete**, il valore iniziale è Gone.</span><span class="sxs-lookup"><span data-stu-id="12368-220">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="12368-221">**Destinatari**: digitare in lease un destinatario originale del messaggio oppure fare clic su **Seleziona tutto** per identificare tutti i destinatari.</span><span class="sxs-lookup"><span data-stu-id="12368-221">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="12368-222">È inoltre possibile fare clic su **Seleziona tutto** e quindi rimuovere selettivamente i singoli destinatari.</span><span class="sxs-lookup"><span data-stu-id="12368-222">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="12368-223">**Motivo dell'invio**: **non deve essere stato bloccato** (impostazione predefinita) o **deve essere stato bloccato**.</span><span class="sxs-lookup"><span data-stu-id="12368-223">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="12368-224">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="12368-224">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="12368-225">Se non si rilascia o si rimuove il messaggio, verrà eliminato dopo la scadenza del periodo di conservazione della quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="12368-225">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="12368-226">Eseguire un'azione su più messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="12368-226">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="12368-227">Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **azioni in blocco** in cui è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="12368-227">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="12368-228">**Rilascia messaggi**: le opzioni sono uguali a quelle rilasciate da un singolo messaggio, tranne per il fatto che non è possibile selezionare **rilascia messaggi a destinatari specifici**. è possibile selezionare rilascia solo il **messaggio a tutti i destinatari** o **rilascia messaggi ad altri utenti**.</span><span class="sxs-lookup"><span data-stu-id="12368-228">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="12368-229">**Elimina messaggi**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente senza essere inviato ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="12368-229">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="12368-230">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="12368-230">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="12368-231">Solo ATP: utilizzare il Centro sicurezza & Compliance per gestire i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="12368-231">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="12368-232">Le procedure per i file in quarantena in questa sezione sono disponibili solo per i sottoscrittori ATP Plan 1 e Plan 2.</span><span class="sxs-lookup"><span data-stu-id="12368-232">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="12368-233">Nelle organizzazioni con ATP, gli amministratori possono gestire i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="12368-233">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="12368-234">Visualizzare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="12368-234">View quarantined files</span></span>

1. <span data-ttu-id="12368-235">Nel centro sicurezza e conformità, passare alla **quarantena**di **Verifica** \> **della gestione** \> delle minacce.</span><span class="sxs-lookup"><span data-stu-id="12368-235">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="12368-236">Modificare la **visualizzazione in quarantena** nei **file**di valore predefiniti.</span><span class="sxs-lookup"><span data-stu-id="12368-236">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="12368-237">È possibile ordinare su un campo facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="12368-237">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="12368-238">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="12368-238">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="12368-239">Fare clic su **modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="12368-239">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="12368-240">Le colonne predefinite sono contrassegnate con un asterisco<sup>\*</sup>():</span><span class="sxs-lookup"><span data-stu-id="12368-240">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="12368-241">**Utente:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-241">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-242">**Percorso**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-242">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-243">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-243">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-244">**URL file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-244">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-245">**Dimensioni file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-245">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-246">**Scade**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-246">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-247">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="12368-247">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="12368-248">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="12368-248">**Detected by**</span></span>

   - <span data-ttu-id="12368-249">**Modificato dal tempo**</span><span class="sxs-lookup"><span data-stu-id="12368-249">**Modified by time**</span></span>

4. <span data-ttu-id="12368-250">Per filtrare i risultati, fare clic su **filtro**.</span><span class="sxs-lookup"><span data-stu-id="12368-250">To filter the results, click **Filter**.</span></span> <span data-ttu-id="12368-251">I filtri disponibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="12368-251">The available filters are:</span></span>

   - <span data-ttu-id="12368-252">**Scade il tempo**: filtrare i messaggi quando scadranno dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="12368-252">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="12368-253">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="12368-253">**Today**</span></span>

     - <span data-ttu-id="12368-254">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="12368-254">**Next 2 days**</span></span>

     - <span data-ttu-id="12368-255">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="12368-255">**Next 7 days**</span></span>

     - <span data-ttu-id="12368-256">Un intervallo di data/ora personalizzato.</span><span class="sxs-lookup"><span data-stu-id="12368-256">A custom date/time range.</span></span>

   - <span data-ttu-id="12368-257">**Tempo ricevuto**</span><span class="sxs-lookup"><span data-stu-id="12368-257">**Received time**</span></span>

   - <span data-ttu-id="12368-258">**Motivo della quarantena**: l'unico valore disponibile è **malware**.</span><span class="sxs-lookup"><span data-stu-id="12368-258">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="12368-259">Dopo aver individuato uno specifico file in quarantena, selezionare il file per visualizzarne i dettagli e per intervenire su di esso (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="12368-259">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="12368-260">Esportare i risultati dei file</span><span class="sxs-lookup"><span data-stu-id="12368-260">Export file results</span></span>

1. <span data-ttu-id="12368-261">Selezionare i file a cui si è interessati e fare clic su **Esporta risultati**.</span><span class="sxs-lookup"><span data-stu-id="12368-261">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="12368-262">Fare clic su **Sì** nel messaggio di conferma che avvisa di mantenere aperta la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="12368-262">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="12368-263">Quando l'esportazione è pronta, è possibile assegnare un nome e scegliere il percorso di download del file. csv.</span><span class="sxs-lookup"><span data-stu-id="12368-263">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="12368-264">Visualizzare i dettagli dei file in quarantena</span><span class="sxs-lookup"><span data-stu-id="12368-264">View quarantined file details</span></span>

<span data-ttu-id="12368-265">Quando si seleziona un file nell'elenco, nel riquadro a comparsa dei **Dettagli** vengono visualizzati i dettagli dei file seguenti:</span><span class="sxs-lookup"><span data-stu-id="12368-265">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="12368-266">**FileName**</span><span class="sxs-lookup"><span data-stu-id="12368-266">**File Name**</span></span>

- <span data-ttu-id="12368-267">**URL file**: URL che definisce il percorso del file, ad esempio in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="12368-267">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="12368-268">**Contenuto dannoso rilevato** La data e l'ora in cui il file è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="12368-268">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="12368-269">**Scade**: la data in cui il file verrà eliminato dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="12368-269">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="12368-270">**Rilevato da**: ATP (Advanced Threat Protection) o dal motore antimalware di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="12368-270">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="12368-271">**Rilasciato?**</span><span class="sxs-lookup"><span data-stu-id="12368-271">**Released?**</span></span>

- <span data-ttu-id="12368-272">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="12368-272">**Malware Name**</span></span>

- <span data-ttu-id="12368-273">**ID documento**: identificatore univoco per il documento.</span><span class="sxs-lookup"><span data-stu-id="12368-273">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="12368-274">**Dimensioni file**: in KILOBYTE (KB).</span><span class="sxs-lookup"><span data-stu-id="12368-274">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="12368-275">**Organizzazione** ID univoco dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="12368-275">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="12368-276">**Data ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="12368-276">**Last modified**</span></span>

- <span data-ttu-id="12368-277">**Modified by**: l'ultimo utente che ha modificato il file.</span><span class="sxs-lookup"><span data-stu-id="12368-277">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="12368-278">**Secure Hash Algorithm 256-bit (SHA-256) valore**: è possibile utilizzare questo valore hash per identificare il file in altri archivi di reputazione o in altre posizioni nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="12368-278">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="12368-279">Eseguire un'azione sui file in quarantena</span><span class="sxs-lookup"><span data-stu-id="12368-279">Take action on quarantined files</span></span>

<span data-ttu-id="12368-280">Quando si seleziona un file nell'elenco, è possibile eseguire le azioni seguenti nel file nel riquadro a comparsa dei **Dettagli** :</span><span class="sxs-lookup"><span data-stu-id="12368-280">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="12368-281">**Rilasciare file**: selezionare (impostazione predefinita) o deselezionare **i file di report in Microsoft per l'analisi**e quindi fare clic su **rilascia file**.</span><span class="sxs-lookup"><span data-stu-id="12368-281">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="12368-282">**Scaricare il file**</span><span class="sxs-lookup"><span data-stu-id="12368-282">**Download file**</span></span>

- <span data-ttu-id="12368-283">**Rimuovi file dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="12368-283">**Remove file from quarantine**</span></span>

<span data-ttu-id="12368-284">Se i file non vengono rilasciati o rimossi, verranno eliminati dopo la scadenza del periodo di conservazione della quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="12368-284">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="12368-285">Azioni su più file in quarantena</span><span class="sxs-lookup"><span data-stu-id="12368-285">Actions on multiple quarantined files</span></span>

<span data-ttu-id="12368-286">Quando si selezionano più file in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **azioni in blocco** in cui è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="12368-286">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="12368-287">**Rilasciare i file**</span><span class="sxs-lookup"><span data-stu-id="12368-287">**Release files**</span></span>

- <span data-ttu-id="12368-288">**Elimina file**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, i file vengono eliminati immediatamente.</span><span class="sxs-lookup"><span data-stu-id="12368-288">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

<span data-ttu-id="12368-289">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="12368-289">When you're finished, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="12368-290">Utilizzare Exchange Online PowerShell o standalone Exchange Online Protection PowerShell per visualizzare e gestire i messaggi e i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="12368-290">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="12368-291">I cmdlet utilizzati per visualizzare e gestire i messaggi e i file in quarantena sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="12368-291">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="12368-292">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="12368-292">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="12368-293">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="12368-293">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="12368-294">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="12368-294">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="12368-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): si noti che questo cmdlet è solo per i messaggi, non per i file malware da ATP per SharePoint Online, OneDrive for business o teams.</span><span class="sxs-lookup"><span data-stu-id="12368-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="12368-296">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="12368-296">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
