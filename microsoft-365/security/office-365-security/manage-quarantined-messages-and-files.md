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
description: Gli amministratori possono imparare a visualizzare e gestire i messaggi in quarantena per tutti gli utenti in Exchange Online Protection (EOP). Gli amministratori nelle organizzazioni con Microsoft Defender per Office 365 possono anche gestire i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.
ms.openlocfilehash: 94dfc8503d61c16aadc8e9d0ccfd295e2684fbba
ms.sourcegitcommit: 1db81b85d327fe423695ce675ad325e538417211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2020
ms.locfileid: "49349281"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="19759-104">Gestire i messaggi e i file messi in quarantena come amministratore in EOP</span><span class="sxs-lookup"><span data-stu-id="19759-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="19759-105">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="19759-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="19759-106">Per ulteriori informazioni, vedere [messaggi di posta elettronica in quarantena in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="19759-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="19759-107">Gli amministratori possono visualizzare, rilasciare ed eliminare tutti i tipi di messaggi in quarantena per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="19759-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="19759-108">Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena come malware, phishing ad alta sicurezza o come risultato delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="19759-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="19759-109">Gli amministratori possono anche segnalare falsi positivi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19759-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="19759-110">Gli amministratori nelle organizzazioni con Microsoft Defender per Office 365 possono anche visualizzare, scaricare ed eliminare i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="19759-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="19759-111">È possibile visualizzare e gestire i messaggi in quarantena nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="19759-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="19759-112">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="19759-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="19759-113">Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="19759-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="19759-114">Per aprire direttamente la pagina della quarantena, passare a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="19759-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="19759-115">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="19759-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="19759-116">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="19759-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="19759-117">È necessario disporre delle autorizzazioni prima di poter gestire la quarantena come amministratore. Le autorizzazioni sono controllate dal ruolo **Quarantine** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="19759-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="19759-118">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli **Gestione organizzazione** (amministratori globali), **amministratori della quarantena** e **amministratore della sicurezza** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="19759-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="19759-119">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="19759-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="19759-120">I messaggi in quarantena vengono mantenuti per un periodo di tempo predefinito prima di essere eliminati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="19759-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="19759-121">30 giorni per i messaggi messi in quarantena dai criteri di protezione dalla posta indesiderata (posta indesiderata, phishing e massa).</span><span class="sxs-lookup"><span data-stu-id="19759-121">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="19759-122">Questo è il valore predefinito e massimo.</span><span class="sxs-lookup"><span data-stu-id="19759-122">This is the default and maximum value.</span></span> <span data-ttu-id="19759-123">Per configurare (abbassare) questo valore, vedere Configurare i criteri di protezione dalla [posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="19759-123">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="19759-124">15 giorni per i messaggi che contengono malware.</span><span class="sxs-lookup"><span data-stu-id="19759-124">15 days for messages that contain malware.</span></span>

  - <span data-ttu-id="19759-125">15 giorni per i file messi in quarantena da ATP per SharePoint, OneDrive e Microsoft teams in Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="19759-125">15 days for files quarantined by ATP for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="19759-126">Quando un messaggio scade dalla quarantena, non è possibile ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="19759-126">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="19759-127">Utilizzare il Centro sicurezza & conformità per gestire i messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="19759-127">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="19759-128">Visualizzazione posta in quarantena</span><span class="sxs-lookup"><span data-stu-id="19759-128">View quarantined email</span></span>

1. <span data-ttu-id="19759-129">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="19759-129">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="19759-130">Verificare che la **visualizzazione in quarantena** sia impostata sul valore predefinito **e-mail**.</span><span class="sxs-lookup"><span data-stu-id="19759-130">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="19759-131">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="19759-131">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="19759-132">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="19759-132">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="19759-133">I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="19759-133">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="19759-134">**Ricevuto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-134">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-135">**Mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-135">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-136">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-136">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-137">**Motivo della quarantena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-137">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-138">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-138">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-139">**Tipo di criterio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-139">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-140">**Scadenza**</span><span class="sxs-lookup"><span data-stu-id="19759-140">**Expires**</span></span>
   - <span data-ttu-id="19759-141">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="19759-141">**Recipient**</span></span>
   - <span data-ttu-id="19759-142">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="19759-142">**Message ID**</span></span>
   - <span data-ttu-id="19759-143">**Nome criterio**</span><span class="sxs-lookup"><span data-stu-id="19759-143">**Policy name**</span></span>
   - <span data-ttu-id="19759-144">**Dimensioni**</span><span class="sxs-lookup"><span data-stu-id="19759-144">**Size**</span></span>
   - <span data-ttu-id="19759-145">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="19759-145">**Direction**</span></span>

   <span data-ttu-id="19759-146">Al termine, fare clic su **Salva** o fare clic su **Imposta su valore predefinito**.</span><span class="sxs-lookup"><span data-stu-id="19759-146">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="19759-147">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="19759-147">To filter the results, click **Filter**.</span></span> <span data-ttu-id="19759-148">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="19759-148">The available filters are:</span></span>

   - <span data-ttu-id="19759-149">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="19759-149">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="19759-150">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="19759-150">**Today**</span></span>
     - <span data-ttu-id="19759-151">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="19759-151">**Next 2 days**</span></span>
     - <span data-ttu-id="19759-152">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="19759-152">**Next 7 days**</span></span>
     - <span data-ttu-id="19759-153">**Personalizzato**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="19759-153">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="19759-154">**Ora ricezione**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="19759-154">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="19759-155">**Motivo della quarantena**:</span><span class="sxs-lookup"><span data-stu-id="19759-155">**Quarantine reason**:</span></span>
     - <span data-ttu-id="19759-156">**Criterio**: il messaggio corrisponde alle condizioni di una regola del flusso di posta (nota anche come regola di trasporto).</span><span class="sxs-lookup"><span data-stu-id="19759-156">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="19759-157">**Invio in blocco**</span><span class="sxs-lookup"><span data-stu-id="19759-157">**Bulk**</span></span>
     - <span data-ttu-id="19759-158">**Phishing**: il verdetto del filtro di posta indesiderata è la **posta elettronica di phishing** o la protezione anti-phishing messa in quarantena del messaggio ([spoofing](set-up-anti-phishing-policies.md#spoof-settings) o [rappresentazione](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="19759-158">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="19759-159">**Malware**</span><span class="sxs-lookup"><span data-stu-id="19759-159">**Malware**</span></span>
     - <span data-ttu-id="19759-160">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="19759-160">**Spam**</span></span>
     - <span data-ttu-id="19759-161">**Phishing ad alta sicurezza**</span><span class="sxs-lookup"><span data-stu-id="19759-161">**High Confidence Phish**</span></span>

   - <span data-ttu-id="19759-162">**Tipo di criteri**: filtrare i messaggi in base al tipo di criteri:</span><span class="sxs-lookup"><span data-stu-id="19759-162">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="19759-163">**Criteri anti-malware**</span><span class="sxs-lookup"><span data-stu-id="19759-163">**Anti-malware policy**</span></span>
     - <span data-ttu-id="19759-164">**Criteri allegati sicuri**</span><span class="sxs-lookup"><span data-stu-id="19759-164">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="19759-165">**Criteri anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="19759-165">**Anti-phish policy**</span></span>
     - <span data-ttu-id="19759-166">**Criteri di filtro contenuto ospitati** (criteri di protezione da posta indesiderata)</span><span class="sxs-lookup"><span data-stu-id="19759-166">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="19759-167">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="19759-167">**Transport rule**</span></span>

   - <span data-ttu-id="19759-168">**Destinatario di posta elettronica**: tutti gli utenti o solo i messaggi inviati all'utente.</span><span class="sxs-lookup"><span data-stu-id="19759-168">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="19759-169">Gli utenti finali possono gestire solo i messaggi in quarantena inviati.</span><span class="sxs-lookup"><span data-stu-id="19759-169">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="19759-170">Per cancellare il filtro, fare clic su **Cancella**.</span><span class="sxs-lookup"><span data-stu-id="19759-170">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="19759-171">Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="19759-171">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="19759-172">Utilizzare **Ordina i risultati per** (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per trovare messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="19759-172">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="19759-173">I caratteri jolly non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="19759-173">Wildcards aren't supported.</span></span> <span data-ttu-id="19759-174">È possibile cercare in base ai seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="19759-174">You can search by the following values:</span></span>

   - <span data-ttu-id="19759-175">**ID messaggio**: identificatore univoco globale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="19759-175">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="19759-176">Ad esempio, è stata utilizzata la [traccia dei messaggi](message-trace-scc.md) per cercare un messaggio che è stato inviato a un utente nell'organizzazione e si determina che il messaggio è stato messo in quarantena invece di essere recapitato.</span><span class="sxs-lookup"><span data-stu-id="19759-176">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="19759-177">Assicurarsi di includere il valore dell'ID messaggio completo, che può includere parentesi angolari ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="19759-177">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="19759-178">Ad esempio: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="19759-178">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="19759-179">**Indirizzo di posta elettronica del mittente**: indirizzo di posta elettronica di un singolo mittente.</span><span class="sxs-lookup"><span data-stu-id="19759-179">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="19759-180">**Nome dei criteri**: usare l'intero nome dei criteri del messaggio.</span><span class="sxs-lookup"><span data-stu-id="19759-180">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="19759-181">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="19759-181">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="19759-182">**Indirizzo di posta elettronica del destinatario**: indirizzo di posta elettronica di un singolo destinatario.</span><span class="sxs-lookup"><span data-stu-id="19759-182">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="19759-183">**Oggetto**: utilizzare l'intero oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="19759-183">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="19759-184">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="19759-184">The search is not case-sensitive.</span></span>
  
   - <span data-ttu-id="19759-185">**Nome criterio**: il nome del criterio responsabile della messa in quarantena del messaggio.</span><span class="sxs-lookup"><span data-stu-id="19759-185">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="19759-186">Dopo avere immesso i criteri di ricerca, fare clic sul ![pulsante Aggiorna](../../media/scc-quarantine-refresh.png) **Aggiorna** per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="19759-186">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="19759-187">Dopo aver trovato un messaggio in quarantena specifico, selezionarlo per visualizzarne i dettagli ed eseguire delle operazioni (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="19759-187">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="19759-188">Visualizzare i dettagli dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="19759-188">View quarantined message details</span></span>

<span data-ttu-id="19759-189">Quando si seleziona un messaggio di posta elettronica nell'elenco, i seguenti dettagli del messaggio vengono visualizzati nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="19759-189">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="19759-190">**ID messaggio**: identificatore univoco globale per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="19759-190">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="19759-191">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="19759-191">**Sender address**</span></span>

- <span data-ttu-id="19759-192">**Ricezione**: data/ora di ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="19759-192">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="19759-193">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="19759-193">**Subject**</span></span>

- <span data-ttu-id="19759-194">**Motivo della quarantena**: indica se un messaggio è stato identificato come **posta indesiderata**, in **blocco**, **phishing**, corrisponde a una regola del flusso di posta (**regola di trasporto**) oppure è stato identificato come contenente **malware**.</span><span class="sxs-lookup"><span data-stu-id="19759-194">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="19759-195">**Numero destinatari**</span><span class="sxs-lookup"><span data-stu-id="19759-195">**Recipient count**</span></span>

- <span data-ttu-id="19759-196">**Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **Visualizza intestazione messaggio** per visualizzare l'elenco completo dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="19759-196">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="19759-197">**Scadenza**: data/ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="19759-197">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="19759-198">**Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="19759-198">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="19759-199">**Non ancora rilasciato in**: tutti gli eventuali messaggi di posta elettronica in cui il messaggio non è stato ancora rilasciato.</span><span class="sxs-lookup"><span data-stu-id="19759-199">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="19759-200">Eseguire azioni sulla posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="19759-200">Take action on quarantined email</span></span>

<span data-ttu-id="19759-201">Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le operazioni da eseguire con i messaggi nel riquadro a comparsa dei **Dettagli** :</span><span class="sxs-lookup"><span data-stu-id="19759-201">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="19759-202">**Rilascia messaggio**: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="19759-202">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="19759-203">**Segnalare i messaggi a Microsoft per l'analisi**: è selezionata per impostazione predefinita e segnala il messaggio in quarantena erroneamente a Microsoft come falso positivo.</span><span class="sxs-lookup"><span data-stu-id="19759-203">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="19759-204">Se il messaggio è stato messo in quarantena come posta indesiderata, rinfusa, phishing o contenente malware, il messaggio viene segnalato anche al team di analisi di posta indesiderata di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19759-204">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="19759-205">A seconda dell'analisi, è possibile modificare le regole di filtro per la posta indesiderata a livello di servizio per consentire il passaggio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="19759-205">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="19759-206">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="19759-206">Choose one of the following options:</span></span>
    - <span data-ttu-id="19759-207">**Rilasciare messaggi a tutti i destinatari**</span><span class="sxs-lookup"><span data-stu-id="19759-207">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="19759-208">**Rilasciare messaggi a destinatari specifici**</span><span class="sxs-lookup"><span data-stu-id="19759-208">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="19759-209">**Rilasciare messaggi ad altri utenti**</span><span class="sxs-lookup"><span data-stu-id="19759-209">**Release messages to other people**</span></span>

  <span data-ttu-id="19759-210">Al termine, fare clic su **Rilascia messaggio**.</span><span class="sxs-lookup"><span data-stu-id="19759-210">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="19759-211">Note sul rilascio dei messaggi:</span><span class="sxs-lookup"><span data-stu-id="19759-211">Notes about releasing messages:</span></span>

  - <span data-ttu-id="19759-212">Non è possibile rilasciare un messaggio allo stesso destinatario più di una volta.</span><span class="sxs-lookup"><span data-stu-id="19759-212">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="19759-213">Solo i destinatari che non hanno ricevuto il messaggio verranno visualizzati nell'elenco dei destinatari potenziali.</span><span class="sxs-lookup"><span data-stu-id="19759-213">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="19759-214">**Visualizza intestazione messaggio**: scegliere questo collegamento per vedere il testo dell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="19759-214">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="19759-215">Per analizzare i campi dell'intestazione e i valori in modo approfondito, copiare il testo negli Appunti e poi scegliere **Microsoft Message Header Analyzer** per passare all'Analizzatore connettività remota. Fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si vuole uscire da Microsoft 365 per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="19759-215">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="19759-216">Incollare l'intestazione del messaggio nella pagina nella sezione Message Header Analyzer e scegliere **Analizza intestazioni**:</span><span class="sxs-lookup"><span data-stu-id="19759-216">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="19759-217">**Anteprima messaggio**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="19759-217">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="19759-218">**Visualizzazione origine**: mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.</span><span class="sxs-lookup"><span data-stu-id="19759-218">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="19759-219">**Visualizzazione testo**: Mostra il corpo del messaggio in testo normale.</span><span class="sxs-lookup"><span data-stu-id="19759-219">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="19759-220">**Rimuovi dalla quarantena**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente senza essere inviato ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="19759-220">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="19759-221">**Scarica il messaggio**: nel riquadro a comparsa visualizzato, selezionare **Sono consapevole dei rischi associati al download di questo messaggio** per salvare una copia locale del messaggio in formato .eml.</span><span class="sxs-lookup"><span data-stu-id="19759-221">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="19759-222">**Invia messaggio**: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="19759-222">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="19759-223">**Tipo di oggetto**: **posta elettronica** (impostazione predefinita), **URL** o **allegato**.</span><span class="sxs-lookup"><span data-stu-id="19759-223">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="19759-224">**Formato di invio**: **ID messaggio di rete** (impostazione predefinita, con il valore corrispondente nella casella **ID messaggio di rete** ) oppure **file** (passare a un file local. eml o. msg).</span><span class="sxs-lookup"><span data-stu-id="19759-224">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="19759-225">Si noti che se si seleziona **file** e quindi si seleziona **ID messaggio di rete**, il valore iniziale è Gone.</span><span class="sxs-lookup"><span data-stu-id="19759-225">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="19759-226">**Destinatari**: digitare in lease un destinatario originale del messaggio oppure fare clic su **Seleziona tutto** per identificare tutti i destinatari.</span><span class="sxs-lookup"><span data-stu-id="19759-226">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="19759-227">È inoltre possibile fare clic su **Seleziona tutto** e quindi rimuovere selettivamente i singoli destinatari.</span><span class="sxs-lookup"><span data-stu-id="19759-227">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="19759-228">**Motivo dell'invio**: **non deve essere stato bloccato** (impostazione predefinita) o **deve essere stato bloccato**.</span><span class="sxs-lookup"><span data-stu-id="19759-228">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="19759-229">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="19759-229">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="19759-230">Se il messaggio non viene rilasciato o rimosso, verrà eliminato dopo la scadenza del periodo di conservazione in quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="19759-230">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="19759-231">Eseguire azioni su più messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="19759-231">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="19759-232">Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **Azioni in blocco** che consente di eseguire le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="19759-232">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="19759-233">**Rilascia messaggi**: le opzioni sono le stesse del rilascio di un singolo messaggio, ma non è possibile selezionare **Rilascia i messaggi a specifici destinatari**; è possibile selezionare solo **Rilascia il messaggio a tutti i destinatari** o **Rilascia i messaggi ad altre persone**.</span><span class="sxs-lookup"><span data-stu-id="19759-233">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="19759-234">Si consideri lo scenario seguente: john@gmail.com Invia un messaggio a faith@contoso.com e john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="19759-234">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="19759-235">Gmail moltiplica questo messaggio in due copie che sono entrambe instradate alla quarantena come phishing in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19759-235">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="19759-236">Un amministratore rilascia entrambi i messaggi a admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="19759-236">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="19759-237">Il primo messaggio rilasciato che raggiunge la cassetta postale di amministrazione viene recapitato.</span><span class="sxs-lookup"><span data-stu-id="19759-237">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="19759-238">Il secondo messaggio rilasciato viene identificato come recapito duplicato e viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="19759-238">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="19759-239">I messaggi vengono identificati come duplicati se dispongono dello stesso ID messaggio e del tempo di ricezione.</span><span class="sxs-lookup"><span data-stu-id="19759-239">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="19759-240">**Elimina messaggi**: dopo aver fatto clic su **Sì** nell'avviso visualizzato, i messaggi saranno immediatamente eliminati senza essere inviati ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="19759-240">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="19759-241">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="19759-241">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="19759-242">Microsoft Defender solo per Office 365: utilizzare il Centro sicurezza & conformità per gestire i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="19759-242">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="19759-243">Le procedure per i file in quarantena in questa sezione sono disponibili solo per i Sottoscrittori Microsoft Defender per Office 365 piano 1 e Plan 2.</span><span class="sxs-lookup"><span data-stu-id="19759-243">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="19759-244">Nelle organizzazioni con Defender per Office 365, gli amministratori possono gestire i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="19759-244">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="19759-245">Per abilitare la protezione per questi file, vedere [attivare ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="19759-245">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="19759-246">Visualizzare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="19759-246">View quarantined files</span></span>

1. <span data-ttu-id="19759-247">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="19759-247">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="19759-248">Modificare la **visualizzazione in quarantena** nei **file** di valore.</span><span class="sxs-lookup"><span data-stu-id="19759-248">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="19759-249">È possibile ordinare su un campo facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="19759-249">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="19759-250">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="19759-250">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="19759-251">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="19759-251">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="19759-252">Le colonne predefinite sono contrassegnate con un asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="19759-252">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="19759-253">**Utente:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-253">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-254">**Percorso**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-254">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-255">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-255">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-256">**URL file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-256">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-257">**Dimensioni file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-257">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-258">**Scadenza**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-258">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-259">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19759-259">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="19759-260">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="19759-260">**Detected by**</span></span>
   - <span data-ttu-id="19759-261">**Modificato dal tempo**</span><span class="sxs-lookup"><span data-stu-id="19759-261">**Modified by time**</span></span>

4. <span data-ttu-id="19759-262">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="19759-262">To filter the results, click **Filter**.</span></span> <span data-ttu-id="19759-263">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="19759-263">The available filters are:</span></span>

   - <span data-ttu-id="19759-264">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="19759-264">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="19759-265">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="19759-265">**Today**</span></span>
     - <span data-ttu-id="19759-266">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="19759-266">**Next 2 days**</span></span>
     - <span data-ttu-id="19759-267">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="19759-267">**Next 7 days**</span></span>
     - <span data-ttu-id="19759-268">Un intervallo di data/ora personalizzato.</span><span class="sxs-lookup"><span data-stu-id="19759-268">A custom date/time range.</span></span>
   - <span data-ttu-id="19759-269">**Tempo ricevuto**</span><span class="sxs-lookup"><span data-stu-id="19759-269">**Received time**</span></span>
   - <span data-ttu-id="19759-270">**Motivo della quarantena**: l'unico valore disponibile è **malware**.</span><span class="sxs-lookup"><span data-stu-id="19759-270">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="19759-271">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="19759-271">**Policy type**</span></span>

<span data-ttu-id="19759-272">Dopo aver individuato uno specifico file in quarantena, selezionare il file per visualizzarne i dettagli e per intervenire su di esso (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="19759-272">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="19759-273">Visualizzare i dettagli dei file in quarantena</span><span class="sxs-lookup"><span data-stu-id="19759-273">View quarantined file details</span></span>

<span data-ttu-id="19759-274">Quando si seleziona un file nell'elenco, nel riquadro a comparsa dei **Dettagli** vengono visualizzati i dettagli dei file seguenti:</span><span class="sxs-lookup"><span data-stu-id="19759-274">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="19759-275">**FileName**</span><span class="sxs-lookup"><span data-stu-id="19759-275">**File Name**</span></span>
- <span data-ttu-id="19759-276">**URL file**: URL che definisce il percorso del file, ad esempio in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="19759-276">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="19759-277">**Contenuto dannoso rilevato** La data e l'ora in cui il file è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="19759-277">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="19759-278">**Scade**: la data in cui il file verrà eliminato dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="19759-278">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="19759-279">**Rilevato da**: Defender per Office 365 o il motore antimalware di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="19759-279">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="19759-280">**Rilasciato?**</span><span class="sxs-lookup"><span data-stu-id="19759-280">**Released?**</span></span>
- <span data-ttu-id="19759-281">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="19759-281">**Malware Name**</span></span>
- <span data-ttu-id="19759-282">**ID documento**: identificatore univoco per il documento.</span><span class="sxs-lookup"><span data-stu-id="19759-282">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="19759-283">**Dimensioni file**: in KILOBYTE (KB).</span><span class="sxs-lookup"><span data-stu-id="19759-283">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="19759-284">**Organizzazione** ID univoco dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="19759-284">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="19759-285">**Data ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="19759-285">**Last modified**</span></span>
- <span data-ttu-id="19759-286">**Modified by**: l'ultimo utente che ha modificato il file.</span><span class="sxs-lookup"><span data-stu-id="19759-286">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="19759-287">**Secure Hash Algorithm 256-bit (SHA-256) valore**: è possibile utilizzare questo valore hash per identificare il file in altri archivi di reputazione o in altre posizioni nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="19759-287">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="19759-288">Eseguire un'azione sui file in quarantena</span><span class="sxs-lookup"><span data-stu-id="19759-288">Take action on quarantined files</span></span>

<span data-ttu-id="19759-289">Quando si seleziona un file nell'elenco, è possibile eseguire le azioni seguenti nel file nel riquadro a comparsa dei **Dettagli** :</span><span class="sxs-lookup"><span data-stu-id="19759-289">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="19759-290">**Rilasciare file**: selezionare (impostazione predefinita) o deselezionare **i file di report in Microsoft per l'analisi** e quindi fare clic su **rilascia file**.</span><span class="sxs-lookup"><span data-stu-id="19759-290">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="19759-291">**Scaricare il file**</span><span class="sxs-lookup"><span data-stu-id="19759-291">**Download file**</span></span>
- <span data-ttu-id="19759-292">**Rimuovi file dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="19759-292">**Remove file from quarantine**</span></span>

<span data-ttu-id="19759-293">Se i file non vengono rilasciati o rimossi, verranno eliminati dopo la scadenza del periodo di conservazione della quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="19759-293">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="19759-294">Azioni su più file in quarantena</span><span class="sxs-lookup"><span data-stu-id="19759-294">Actions on multiple quarantined files</span></span>

<span data-ttu-id="19759-295">Quando si selezionano più file in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **azioni in blocco** in cui è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="19759-295">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="19759-296">**Rilasciare i file**</span><span class="sxs-lookup"><span data-stu-id="19759-296">**Release files**</span></span>
- <span data-ttu-id="19759-297">**Elimina file**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, i file vengono eliminati immediatamente.</span><span class="sxs-lookup"><span data-stu-id="19759-297">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="19759-298">Utilizzare PowerShell di Exchange Online o standalone EOP PowerShell per visualizzare e gestire i messaggi e i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="19759-298">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="19759-299">I cmdlet utilizzati per visualizzare e gestire i messaggi e i file in quarantena sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="19759-299">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="19759-300">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="19759-300">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="19759-301">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="19759-301">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="19759-302">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="19759-302">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="19759-303">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): si noti che questo cmdlet è solo per i messaggi, non per i file malware da ATP per SharePoint Online, OneDrive for business o teams.</span><span class="sxs-lookup"><span data-stu-id="19759-303">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="19759-304">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="19759-304">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
