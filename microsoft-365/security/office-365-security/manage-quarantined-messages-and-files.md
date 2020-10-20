---
title: Gestire i messaggi e i file in quarantena come amministratore
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a visualizzare e gestire i messaggi in quarantena per tutti gli utenti in Exchange Online Protection (EOP). Gli amministratori nelle organizzazioni con Office 365 Advanced Threat Protection (Office 365 ATP) possono anche gestire i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.
ms.openlocfilehash: 5e1115157ef7d67bc7a3f626eb61d01ecc0986cb
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600542"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="3d764-104">Gestire i messaggi e i file messi in quarantena come amministratore in EOP</span><span class="sxs-lookup"><span data-stu-id="3d764-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3d764-105">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="3d764-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="3d764-106">Per ulteriori informazioni, vedere [messaggi di posta elettronica in quarantena in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="3d764-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="3d764-107">Gli amministratori possono visualizzare, rilasciare ed eliminare tutti i tipi di messaggi in quarantena per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="3d764-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="3d764-108">Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena come malware, phishing ad alta sicurezza o come risultato delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="3d764-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="3d764-109">Gli amministratori possono anche segnalare falsi positivi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d764-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="3d764-110">Gli amministratori nelle organizzazioni con Office 365 Advance Threat Protection (Office 365 ATP) possono anche visualizzare, scaricare ed eliminare i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="3d764-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="3d764-111">È possibile visualizzare e gestire i messaggi in quarantena nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="3d764-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3d764-112">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3d764-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3d764-113">Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="3d764-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="3d764-114">Per aprire direttamente la pagina della quarantena, passare a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="3d764-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="3d764-115">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3d764-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3d764-116">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="3d764-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3d764-117">È necessario disporre delle autorizzazioni prima di poter gestire la quarantena come amministratore. Le autorizzazioni sono controllate dal ruolo **Quarantine** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="3d764-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="3d764-118">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli **Gestione organizzazione** (amministratori globali), **amministratori della quarantena**e **amministratore della sicurezza** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="3d764-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="3d764-119">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3d764-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="3d764-120">I messaggi in quarantena vengono mantenuti per un periodo di tempo predefinito prima di essere eliminati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="3d764-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="3d764-121">Messaggi in quarantena da criteri di protezione da posta indesiderata (posta indesiderata, phishing e posta elettronica in blocco): 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="3d764-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="3d764-122">Questo è il valore predefinito e massimo.</span><span class="sxs-lookup"><span data-stu-id="3d764-122">This is the default and maximum value.</span></span> <span data-ttu-id="3d764-123">Per configurare questo valore, vedere Configurare i criteri di protezione dalla [posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3d764-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="3d764-124">Messaggi contenenti malware: 15 giorni.</span><span class="sxs-lookup"><span data-stu-id="3d764-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="3d764-125">Quando un messaggio scade dalla quarantena, non è possibile ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="3d764-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="3d764-126">Utilizzare il Centro sicurezza & conformità per gestire i messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="3d764-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="3d764-127">Visualizzazione posta in quarantena</span><span class="sxs-lookup"><span data-stu-id="3d764-127">View quarantined email</span></span>

1. <span data-ttu-id="3d764-128">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="3d764-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="3d764-129">Verificare che la **visualizzazione in quarantena** sia impostata sul valore predefinito **e-mail**.</span><span class="sxs-lookup"><span data-stu-id="3d764-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="3d764-130">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="3d764-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="3d764-131">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="3d764-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="3d764-132">I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="3d764-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="3d764-133">**Ricevuto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-133">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-134">**Mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-134">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-135">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-135">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-136">**Motivo della quarantena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-136">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-137">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-137">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-138">**Tipo di criterio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-138">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-139">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="3d764-139">**Recipient**</span></span>
   - <span data-ttu-id="3d764-140">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="3d764-140">**Message ID**</span></span>
   - <span data-ttu-id="3d764-141">**Nome criterio**</span><span class="sxs-lookup"><span data-stu-id="3d764-141">**Policy name**</span></span>
   - <span data-ttu-id="3d764-142">**Dimensioni**</span><span class="sxs-lookup"><span data-stu-id="3d764-142">**Size**</span></span>
   - <span data-ttu-id="3d764-143">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="3d764-143">**Direction**</span></span>

   <span data-ttu-id="3d764-144">Al termine, fare clic su **Salva** o fare clic su **Imposta su valore predefinito**.</span><span class="sxs-lookup"><span data-stu-id="3d764-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="3d764-145">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="3d764-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="3d764-146">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="3d764-146">The available filters are:</span></span>

   - <span data-ttu-id="3d764-147">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="3d764-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="3d764-148">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="3d764-148">**Today**</span></span>
     - <span data-ttu-id="3d764-149">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="3d764-149">**Next 2 days**</span></span>
     - <span data-ttu-id="3d764-150">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="3d764-150">**Next 7 days**</span></span>
     - <span data-ttu-id="3d764-151">**Personalizzato**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="3d764-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="3d764-152">**Ora ricezione**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="3d764-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="3d764-153">**Motivo della quarantena**:</span><span class="sxs-lookup"><span data-stu-id="3d764-153">**Quarantine reason**:</span></span>
     - <span data-ttu-id="3d764-154">**Criterio**: il messaggio corrisponde alle condizioni di una regola del flusso di posta (nota anche come regola di trasporto).</span><span class="sxs-lookup"><span data-stu-id="3d764-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="3d764-155">**Invio in blocco**</span><span class="sxs-lookup"><span data-stu-id="3d764-155">**Bulk**</span></span>
     - <span data-ttu-id="3d764-156">**Phishing**: il verdetto del filtro di posta indesiderata è la **posta elettronica di phishing** o la protezione anti-phishing messa in quarantena del messaggio ([spoofing](set-up-anti-phishing-policies.md#spoof-settings) o [rappresentazione](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)).</span><span class="sxs-lookup"><span data-stu-id="3d764-156">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)).</span></span>
     - <span data-ttu-id="3d764-157">**Malware**</span><span class="sxs-lookup"><span data-stu-id="3d764-157">**Malware**</span></span>
     - <span data-ttu-id="3d764-158">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="3d764-158">**Spam**</span></span>
     - <span data-ttu-id="3d764-159">**Phishing ad alta sicurezza**</span><span class="sxs-lookup"><span data-stu-id="3d764-159">**High Confidence Phish**</span></span>
     
   - <span data-ttu-id="3d764-160">**Tipo di criterio**: filtrare i messaggi in base al tipo di criterio:</span><span class="sxs-lookup"><span data-stu-id="3d764-160">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="3d764-161">**Criteri anti-malware**</span><span class="sxs-lookup"><span data-stu-id="3d764-161">**Anti-malware policy**</span></span>
     - <span data-ttu-id="3d764-162">**Criteri allegati sicuri**</span><span class="sxs-lookup"><span data-stu-id="3d764-162">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="3d764-163">**Criteri anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="3d764-163">**Anti-phish policy**</span></span>
     - <span data-ttu-id="3d764-164">**Criteri di filtro contenuto ospitato**</span><span class="sxs-lookup"><span data-stu-id="3d764-164">**Hosted content filter policy**</span></span>
     - <span data-ttu-id="3d764-165">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="3d764-165">**Transport rule**</span></span>

   - <span data-ttu-id="3d764-166">**Destinatario di posta elettronica**: tutti gli utenti o solo i messaggi inviati all'utente.</span><span class="sxs-lookup"><span data-stu-id="3d764-166">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="3d764-167">Gli utenti finali possono gestire solo i messaggi in quarantena inviati.</span><span class="sxs-lookup"><span data-stu-id="3d764-167">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="3d764-168">Per cancellare il filtro, fare clic su **Cancella**.</span><span class="sxs-lookup"><span data-stu-id="3d764-168">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="3d764-169">Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="3d764-169">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="3d764-170">Utilizzare **Ordina i risultati per** (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per trovare messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="3d764-170">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="3d764-171">I caratteri jolly non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="3d764-171">Wildcards aren't supported.</span></span> <span data-ttu-id="3d764-172">È possibile cercare in base ai seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3d764-172">You can search by the following values:</span></span>

   - <span data-ttu-id="3d764-173">**ID messaggio**: identificatore univoco globale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="3d764-173">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="3d764-174">Ad esempio, è stata utilizzata la [traccia dei messaggi](message-trace-scc.md) per cercare un messaggio che è stato inviato a un utente nell'organizzazione e si determina che il messaggio è stato messo in quarantena invece di essere recapitato.</span><span class="sxs-lookup"><span data-stu-id="3d764-174">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="3d764-175">Assicurarsi di includere il valore dell'ID messaggio completo, che può includere parentesi angolari ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="3d764-175">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="3d764-176">Ad esempio: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="3d764-176">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="3d764-177">**Indirizzo di posta elettronica del mittente**: indirizzo di posta elettronica di un singolo mittente.</span><span class="sxs-lookup"><span data-stu-id="3d764-177">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="3d764-178">**Nome criterio**: utilizzare l'intero nome dei criteri del messaggio.</span><span class="sxs-lookup"><span data-stu-id="3d764-178">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="3d764-179">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="3d764-179">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="3d764-180">**Indirizzo di posta elettronica del destinatario**: indirizzo di posta elettronica di un singolo destinatario.</span><span class="sxs-lookup"><span data-stu-id="3d764-180">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="3d764-181">**Oggetto**: utilizzare l'intero oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="3d764-181">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="3d764-182">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="3d764-182">The search is not case-sensitive.</span></span>

   <span data-ttu-id="3d764-183">Dopo avere immesso i criteri di ricerca, fare clic sul ![pulsante Aggiorna](../../media/scc-quarantine-refresh.png) **Aggiorna** per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="3d764-183">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="3d764-184">Dopo aver trovato un messaggio in quarantena specifico, selezionarlo per visualizzarne i dettagli ed eseguire delle operazioni (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="3d764-184">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="3d764-185">Esportare i risultati di un messaggio</span><span class="sxs-lookup"><span data-stu-id="3d764-185">Export message results</span></span>

1. <span data-ttu-id="3d764-186">Selezionare i messaggi a cui si è interessati e quindi fare clic su **Esporta risultati**.</span><span class="sxs-lookup"><span data-stu-id="3d764-186">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="3d764-187">Fare clic su **Sì** nel messaggio di conferma che avverte di tenere aperta la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="3d764-187">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="3d764-188">Una volta completata l'esportazione, è possibile assegnare un nome e scegliere il percorso di download per il file .csv.</span><span class="sxs-lookup"><span data-stu-id="3d764-188">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="3d764-189">Visualizzare i dettagli dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="3d764-189">View quarantined message details</span></span>

<span data-ttu-id="3d764-190">Quando si seleziona un messaggio di posta elettronica nell'elenco, i seguenti dettagli del messaggio vengono visualizzati nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="3d764-190">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="3d764-191">**ID messaggio**: identificatore univoco globale per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="3d764-191">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="3d764-192">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="3d764-192">**Sender address**</span></span>

- <span data-ttu-id="3d764-193">**Ricezione**: data/ora di ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="3d764-193">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="3d764-194">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="3d764-194">**Subject**</span></span>

- <span data-ttu-id="3d764-195">**Motivo della quarantena**: indica se un messaggio è stato identificato come **posta indesiderata**, in **blocco**, **phishing**, corrisponde a una regola del flusso di posta (**regola di trasporto**) oppure è stato identificato come contenente **malware**.</span><span class="sxs-lookup"><span data-stu-id="3d764-195">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="3d764-196">**Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **Visualizza intestazione messaggio** per visualizzare l'elenco completo dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="3d764-196">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="3d764-197">**Scadenza**: data/ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="3d764-197">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="3d764-198">**Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="3d764-198">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="3d764-199">**Non ancora rilasciato in**: tutti gli eventuali messaggi di posta elettronica in cui il messaggio non è stato ancora rilasciato.</span><span class="sxs-lookup"><span data-stu-id="3d764-199">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="3d764-200">Eseguire azioni sulla posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="3d764-200">Take action on quarantined email</span></span>

<span data-ttu-id="3d764-201">Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le operazioni da eseguire con i messaggi nel riquadro a comparsa dei **Dettagli** :</span><span class="sxs-lookup"><span data-stu-id="3d764-201">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="3d764-202">**Rilascia messaggio**: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d764-202">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="3d764-203">**Segnalare i messaggi a Microsoft per l'analisi**: è selezionata per impostazione predefinita e segnala il messaggio in quarantena erroneamente a Microsoft come falso positivo.</span><span class="sxs-lookup"><span data-stu-id="3d764-203">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="3d764-204">Se il messaggio è stato messo in quarantena come posta indesiderata, rinfusa, phishing o contenente malware, il messaggio viene segnalato anche al team di analisi di posta indesiderata di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d764-204">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="3d764-205">A seconda dell'analisi, è possibile modificare le regole di filtro per la posta indesiderata a livello di servizio per consentire il passaggio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="3d764-205">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="3d764-206">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d764-206">Choose one of the following options:</span></span>
    - <span data-ttu-id="3d764-207">**Rilasciare messaggi a tutti i destinatari**</span><span class="sxs-lookup"><span data-stu-id="3d764-207">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="3d764-208">**Rilasciare messaggi a destinatari specifici**</span><span class="sxs-lookup"><span data-stu-id="3d764-208">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="3d764-209">**Rilasciare messaggi ad altri utenti**</span><span class="sxs-lookup"><span data-stu-id="3d764-209">**Release messages to other people**</span></span>

  <span data-ttu-id="3d764-210">Al termine, fare clic su **Rilascia messaggio**.</span><span class="sxs-lookup"><span data-stu-id="3d764-210">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="3d764-211">Note sul rilascio dei messaggi:</span><span class="sxs-lookup"><span data-stu-id="3d764-211">Notes about releasing messages:</span></span>

  - <span data-ttu-id="3d764-212">Non è possibile rilasciare un messaggio allo stesso destinatario più di una volta.</span><span class="sxs-lookup"><span data-stu-id="3d764-212">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="3d764-213">Solo i destinatari che non hanno ricevuto il messaggio verranno visualizzati nell'elenco dei destinatari potenziali.</span><span class="sxs-lookup"><span data-stu-id="3d764-213">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="3d764-214">**Visualizza intestazione messaggio**: scegliere questo collegamento per vedere il testo dell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="3d764-214">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="3d764-215">Per analizzare i campi dell'intestazione e i valori in modo approfondito, copiare il testo negli Appunti e poi scegliere **Microsoft Message Header Analyzer** per passare all'Analizzatore connettività remota. Fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si vuole uscire da Microsoft 365 per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="3d764-215">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="3d764-216">Incollare l'intestazione del messaggio nella pagina nella sezione Message Header Analyzer e scegliere **Analizza intestazioni**:</span><span class="sxs-lookup"><span data-stu-id="3d764-216">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="3d764-217">**Anteprima messaggio**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="3d764-217">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="3d764-218">**Visualizzazione origine**: mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.</span><span class="sxs-lookup"><span data-stu-id="3d764-218">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="3d764-219">**Visualizzazione testo**: Mostra il corpo del messaggio in testo normale.</span><span class="sxs-lookup"><span data-stu-id="3d764-219">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="3d764-220">**Rimuovi dalla quarantena**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente senza essere inviato ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="3d764-220">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="3d764-221">**Scarica il messaggio**: nel riquadro a comparsa visualizzato, selezionare **Sono consapevole dei rischi associati al download di questo messaggio** per salvare una copia locale del messaggio in formato .eml.</span><span class="sxs-lookup"><span data-stu-id="3d764-221">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="3d764-222">**Invia messaggio**: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d764-222">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="3d764-223">**Tipo di oggetto**: **posta elettronica** (impostazione predefinita), **URL**o **allegato**.</span><span class="sxs-lookup"><span data-stu-id="3d764-223">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="3d764-224">**Formato di invio**: **ID messaggio di rete** (impostazione predefinita, con il valore corrispondente nella casella **ID messaggio di rete** ) oppure **file** (passare a un file local. eml o. msg).</span><span class="sxs-lookup"><span data-stu-id="3d764-224">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="3d764-225">Si noti che se si seleziona **file** e quindi si seleziona **ID messaggio di rete**, il valore iniziale è Gone.</span><span class="sxs-lookup"><span data-stu-id="3d764-225">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="3d764-226">**Destinatari**: digitare in lease un destinatario originale del messaggio oppure fare clic su **Seleziona tutto** per identificare tutti i destinatari.</span><span class="sxs-lookup"><span data-stu-id="3d764-226">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="3d764-227">È inoltre possibile fare clic su **Seleziona tutto** e quindi rimuovere selettivamente i singoli destinatari.</span><span class="sxs-lookup"><span data-stu-id="3d764-227">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="3d764-228">**Motivo dell'invio**: **non deve essere stato bloccato** (impostazione predefinita) o **deve essere stato bloccato**.</span><span class="sxs-lookup"><span data-stu-id="3d764-228">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="3d764-229">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="3d764-229">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="3d764-230">Se il messaggio non viene rilasciato o rimosso, verrà eliminato dopo la scadenza del periodo di conservazione in quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="3d764-230">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="3d764-231">Eseguire azioni su più messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="3d764-231">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="3d764-232">Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **Azioni in blocco** che consente di eseguire le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="3d764-232">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="3d764-233">**Rilascia messaggi**: le opzioni sono le stesse del rilascio di un singolo messaggio, ma non è possibile selezionare **Rilascia i messaggi a specifici destinatari**; è possibile selezionare solo **Rilascia il messaggio a tutti i destinatari** o **Rilascia i messaggi ad altre persone**.</span><span class="sxs-lookup"><span data-stu-id="3d764-233">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3d764-234">Si consideri lo scenario seguente: john@gmail.com Invia un messaggio a faith@contoso.com e john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3d764-234">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="3d764-235">Gmail moltiplica questo messaggio in due copie che sono entrambe instradate alla quarantena come phishing in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d764-235">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="3d764-236">Un amministratore rilascia entrambi i messaggi a admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3d764-236">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="3d764-237">Il primo messaggio rilasciato che raggiunge la cassetta postale di amministrazione viene recapitato.</span><span class="sxs-lookup"><span data-stu-id="3d764-237">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="3d764-238">Il secondo messaggio rilasciato viene identificato come recapito duplicato e viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="3d764-238">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="3d764-239">I messaggi vengono identificati come duplicati se dispongono dello stesso ID messaggio e del tempo di ricezione.</span><span class="sxs-lookup"><span data-stu-id="3d764-239">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="3d764-240">**Elimina messaggi**: dopo aver fatto clic su **Sì** nell'avviso visualizzato, i messaggi saranno immediatamente eliminati senza essere inviati ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="3d764-240">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="3d764-241">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="3d764-241">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="3d764-242">Solo ATP: utilizzare il Centro sicurezza & Compliance per gestire i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="3d764-242">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="3d764-243">Le procedure per i file in quarantena in questa sezione sono disponibili solo per i sottoscrittori ATP Plan 1 e Plan 2.</span><span class="sxs-lookup"><span data-stu-id="3d764-243">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="3d764-244">Nelle organizzazioni con ATP, gli amministratori possono gestire i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="3d764-244">In organizations with ATP, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="3d764-245">Visualizzare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="3d764-245">View quarantined files</span></span>

1. <span data-ttu-id="3d764-246">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="3d764-246">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="3d764-247">Modificare la **visualizzazione in quarantena** nei **file**di valore predefiniti.</span><span class="sxs-lookup"><span data-stu-id="3d764-247">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="3d764-248">È possibile ordinare su un campo facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="3d764-248">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="3d764-249">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="3d764-249">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="3d764-250">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="3d764-250">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="3d764-251">Le colonne predefinite sono contrassegnate con un asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="3d764-251">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="3d764-252">**Utente:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-252">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-253">**Percorso**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-253">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-254">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-254">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-255">**URL file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-255">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-256">**Dimensioni file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-256">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-257">**Scadenza**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-257">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-258">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d764-258">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="3d764-259">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="3d764-259">**Detected by**</span></span>
   - <span data-ttu-id="3d764-260">**Modificato dal tempo**</span><span class="sxs-lookup"><span data-stu-id="3d764-260">**Modified by time**</span></span>

4. <span data-ttu-id="3d764-261">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="3d764-261">To filter the results, click **Filter**.</span></span> <span data-ttu-id="3d764-262">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="3d764-262">The available filters are:</span></span>

   - <span data-ttu-id="3d764-263">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="3d764-263">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="3d764-264">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="3d764-264">**Today**</span></span>
     - <span data-ttu-id="3d764-265">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="3d764-265">**Next 2 days**</span></span>
     - <span data-ttu-id="3d764-266">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="3d764-266">**Next 7 days**</span></span>
     - <span data-ttu-id="3d764-267">Un intervallo di data/ora personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3d764-267">A custom date/time range.</span></span>
   - <span data-ttu-id="3d764-268">**Tempo ricevuto**</span><span class="sxs-lookup"><span data-stu-id="3d764-268">**Received time**</span></span>
   - <span data-ttu-id="3d764-269">**Motivo della quarantena**: l'unico valore disponibile è **malware**.</span><span class="sxs-lookup"><span data-stu-id="3d764-269">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="3d764-270">Dopo aver individuato uno specifico file in quarantena, selezionare il file per visualizzarne i dettagli e per intervenire su di esso (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="3d764-270">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="3d764-271">Esportare i risultati dei file</span><span class="sxs-lookup"><span data-stu-id="3d764-271">Export file results</span></span>

1. <span data-ttu-id="3d764-272">Selezionare i file a cui si è interessati e fare clic su **Esporta risultati**.</span><span class="sxs-lookup"><span data-stu-id="3d764-272">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="3d764-273">Fare clic su **Sì** nel messaggio di conferma che avverte di tenere aperta la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="3d764-273">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="3d764-274">Una volta completata l'esportazione, è possibile assegnare un nome e scegliere il percorso di download per il file .csv.</span><span class="sxs-lookup"><span data-stu-id="3d764-274">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="3d764-275">Visualizzare i dettagli dei file in quarantena</span><span class="sxs-lookup"><span data-stu-id="3d764-275">View quarantined file details</span></span>

<span data-ttu-id="3d764-276">Quando si seleziona un file nell'elenco, nel riquadro a comparsa dei **Dettagli** vengono visualizzati i dettagli dei file seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d764-276">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="3d764-277">**FileName**</span><span class="sxs-lookup"><span data-stu-id="3d764-277">**File Name**</span></span>
- <span data-ttu-id="3d764-278">**URL file**: URL che definisce il percorso del file, ad esempio in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3d764-278">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="3d764-279">**Contenuto dannoso rilevato** La data e l'ora in cui il file è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="3d764-279">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="3d764-280">**Scade**: la data in cui il file verrà eliminato dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="3d764-280">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="3d764-281">**Rilevato da**: ATP (Advanced Threat Protection) o dal motore antimalware di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d764-281">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="3d764-282">**Rilasciato?**</span><span class="sxs-lookup"><span data-stu-id="3d764-282">**Released?**</span></span>
- <span data-ttu-id="3d764-283">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="3d764-283">**Malware Name**</span></span>
- <span data-ttu-id="3d764-284">**ID documento**: identificatore univoco per il documento.</span><span class="sxs-lookup"><span data-stu-id="3d764-284">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="3d764-285">**Dimensioni file**: in KILOBYTE (KB).</span><span class="sxs-lookup"><span data-stu-id="3d764-285">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="3d764-286">**Organizzazione** ID univoco dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3d764-286">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="3d764-287">**Data ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="3d764-287">**Last modified**</span></span>
- <span data-ttu-id="3d764-288">**Modified by**: l'ultimo utente che ha modificato il file.</span><span class="sxs-lookup"><span data-stu-id="3d764-288">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="3d764-289">**Secure Hash Algorithm 256-bit (SHA-256) valore**: è possibile utilizzare questo valore hash per identificare il file in altri archivi di reputazione o in altre posizioni nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="3d764-289">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="3d764-290">Eseguire un'azione sui file in quarantena</span><span class="sxs-lookup"><span data-stu-id="3d764-290">Take action on quarantined files</span></span>

<span data-ttu-id="3d764-291">Quando si seleziona un file nell'elenco, è possibile eseguire le azioni seguenti nel file nel riquadro a comparsa dei **Dettagli** :</span><span class="sxs-lookup"><span data-stu-id="3d764-291">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="3d764-292">**Rilasciare file**: selezionare (impostazione predefinita) o deselezionare **i file di report in Microsoft per l'analisi**e quindi fare clic su **rilascia file**.</span><span class="sxs-lookup"><span data-stu-id="3d764-292">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="3d764-293">**Scaricare il file**</span><span class="sxs-lookup"><span data-stu-id="3d764-293">**Download file**</span></span>
- <span data-ttu-id="3d764-294">**Rimuovi file dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="3d764-294">**Remove file from quarantine**</span></span>

<span data-ttu-id="3d764-295">Se i file non vengono rilasciati o rimossi, verranno eliminati dopo la scadenza del periodo di conservazione della quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="3d764-295">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="3d764-296">Azioni su più file in quarantena</span><span class="sxs-lookup"><span data-stu-id="3d764-296">Actions on multiple quarantined files</span></span>

<span data-ttu-id="3d764-297">Quando si selezionano più file in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **azioni in blocco** in cui è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d764-297">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="3d764-298">**Rilasciare i file**</span><span class="sxs-lookup"><span data-stu-id="3d764-298">**Release files**</span></span>
- <span data-ttu-id="3d764-299">**Elimina file**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, i file vengono eliminati immediatamente.</span><span class="sxs-lookup"><span data-stu-id="3d764-299">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="3d764-300">Se si utilizza un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale (o ruoli di sicurezza & conformità corretti) nell'organizzazione, accedere e [passare al centro sicurezza & conformità](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3d764-300">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="3d764-301">Utilizzare PowerShell di Exchange Online o standalone EOP PowerShell per visualizzare e gestire i messaggi e i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="3d764-301">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="3d764-302">I cmdlet utilizzati per visualizzare e gestire i messaggi e i file in quarantena sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d764-302">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="3d764-303">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="3d764-303">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="3d764-304">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="3d764-304">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="3d764-305">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="3d764-305">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="3d764-306">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): si noti che questo cmdlet è solo per i messaggi, non per i file malware da ATP per SharePoint Online, OneDrive for business o teams.</span><span class="sxs-lookup"><span data-stu-id="3d764-306">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="3d764-307">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="3d764-307">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
