---
title: Gestire i messaggi e i file in quarantena come amministratore
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
ms.openlocfilehash: 1ae64b71d29f9e2d973f5a73cc19790fe0736913
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635355"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator"></a><span data-ttu-id="30a4a-104">Gestire i messaggi e i file in quarantena come amministratore</span><span class="sxs-lookup"><span data-stu-id="30a4a-104">Manage quarantined messages and files as an administrator</span></span>

<span data-ttu-id="30a4a-105">La quarantena contiene messaggi potenzialmente pericolosi o indesiderati nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) senza cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="30a4a-105">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="30a4a-106">Per altre informazioni, vedere [Quarantena in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="30a4a-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="30a4a-107">Gli amministratori possono visualizzare, rilasciare ed eliminare tutti i tipi di messaggi in quarantena per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="30a4a-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="30a4a-108">Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena come malware, phishing ad alta sicurezza o come risultato delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="30a4a-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="30a4a-109">Gli amministratori possono anche segnalare falsi positivi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="30a4a-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="30a4a-110">Gli amministratori nelle organizzazioni con Office 365 Advance Threat Protection (ATP) possono anche visualizzare, scaricare ed eliminare i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="30a4a-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="30a4a-111">È possibile visualizzare e gestire i messaggi in quarantena nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per i clienti di Microsoft 365; PowerShell di Exchange Online Protection per clienti EOP autonomi.</span><span class="sxs-lookup"><span data-stu-id="30a4a-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="30a4a-112">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="30a4a-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="30a4a-113">Per aprire il Centro sicurezza & conformità, accedere a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="30a4a-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="30a4a-114">Per aprire direttamente la pagina della quarantena, passare a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="30a4a-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="30a4a-115">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="30a4a-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="30a4a-116">Per connettersi a PowerShell di Exchange Online Protection, vedere [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="30a4a-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="30a4a-117">È necessario disporre delle autorizzazioni prima di poter gestire la quarantena come amministratore. Le autorizzazioni sono controllate dal ruolo **Quarantine** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="30a4a-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="30a4a-118">Per impostazione predefinita, questo ruolo viene assegnato ai gruppi di ruoli **Gestione organizzazione** (amministratori globali), **amministratori della quarantena**e **amministratore della sicurezza** nel centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="30a4a-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="30a4a-119">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="30a4a-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="30a4a-120">I messaggi in quarantena vengono mantenuti per un periodo di tempo predefinito prima di essere eliminati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="30a4a-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="30a4a-121">Messaggi in quarantena da criteri di protezione da posta indesiderata (posta indesiderata, phishing e posta elettronica in blocco): 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="30a4a-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="30a4a-122">Questo è il valore predefinito e massimo.</span><span class="sxs-lookup"><span data-stu-id="30a4a-122">This is the default and maximum value.</span></span> <span data-ttu-id="30a4a-123">Per configurare questo valore, vedere Configurare i criteri di protezione dalla [posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="30a4a-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="30a4a-124">Se si utilizza un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale (o ruoli di sicurezza & conformità corretti) nell'organizzazione, accedere e [passare al centro sicurezza & conformità](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="30a4a-124">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

  - <span data-ttu-id="30a4a-125">Messaggi contenenti malware: 15 giorni.</span><span class="sxs-lookup"><span data-stu-id="30a4a-125">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="30a4a-126">Quando un messaggio scade dalla quarantena, non è possibile ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="30a4a-126">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="30a4a-127">Utilizzare il Centro sicurezza & conformità per gestire i messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="30a4a-127">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="30a4a-128">Visualizzazione posta in quarantena</span><span class="sxs-lookup"><span data-stu-id="30a4a-128">View quarantined email</span></span>

1. <span data-ttu-id="30a4a-129">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-129">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="30a4a-130">Verificare che la **visualizzazione in quarantena** sia impostata sul valore predefinito **e-mail**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-130">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="30a4a-131">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="30a4a-131">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="30a4a-132">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="30a4a-132">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="30a4a-133">I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="30a4a-133">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="30a4a-134">**Ricevuto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-134">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="30a4a-135">**Mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-135">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="30a4a-136">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-136">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="30a4a-137">**Motivo della quarantena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-137">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="30a4a-138">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-138">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="30a4a-139">**Tipo di criterio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-139">**Policy type**<sup>\*</sup></span></span>

1. <span data-ttu-id="30a4a-140">Se si utilizza un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale (o ruoli di sicurezza & conformità corretti) nell'organizzazione, accedere e [passare al centro sicurezza & conformità](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="30a4a-140">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

   - <span data-ttu-id="30a4a-141">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="30a4a-141">**Recipient**</span></span>

   - <span data-ttu-id="30a4a-142">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="30a4a-142">**Message ID**</span></span>

   - <span data-ttu-id="30a4a-143">**Nome criterio**</span><span class="sxs-lookup"><span data-stu-id="30a4a-143">**Policy name**</span></span>

   - <span data-ttu-id="30a4a-144">**Dimensioni**</span><span class="sxs-lookup"><span data-stu-id="30a4a-144">**Size**</span></span>

   - <span data-ttu-id="30a4a-145">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="30a4a-145">**Direction**</span></span>

   <span data-ttu-id="30a4a-146">Al termine, fare clic su **Salva** o fare clic su **Imposta su valore predefinito**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-146">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="30a4a-147">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-147">To filter the results, click **Filter**.</span></span> <span data-ttu-id="30a4a-148">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="30a4a-148">The available filters are:</span></span>

   - <span data-ttu-id="30a4a-149">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="30a4a-149">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="30a4a-150">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="30a4a-150">**Today**</span></span>

     - <span data-ttu-id="30a4a-151">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="30a4a-151">**Next 2 days**</span></span>

     - <span data-ttu-id="30a4a-152">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="30a4a-152">**Next 7 days**</span></span>

     - <span data-ttu-id="30a4a-153">**Personalizzato**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-153">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="30a4a-154">**Ora ricezione**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-154">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="30a4a-155">**Motivo della quarantena**:</span><span class="sxs-lookup"><span data-stu-id="30a4a-155">**Quarantine reason**:</span></span>

     - <span data-ttu-id="30a4a-156">**Criterio**: il messaggio corrisponde alle condizioni di una regola del flusso di posta (nota anche come regola di trasporto).</span><span class="sxs-lookup"><span data-stu-id="30a4a-156">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="30a4a-157">**Invio in blocco**</span><span class="sxs-lookup"><span data-stu-id="30a4a-157">**Bulk**</span></span>

     - <span data-ttu-id="30a4a-158">**Phishing**</span><span class="sxs-lookup"><span data-stu-id="30a4a-158">**Phish**</span></span>

     - <span data-ttu-id="30a4a-159">**Malware**</span><span class="sxs-lookup"><span data-stu-id="30a4a-159">**Malware**</span></span>

     - <span data-ttu-id="30a4a-160">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="30a4a-160">**Spam**</span></span>

     - <span data-ttu-id="30a4a-161">**Phishing ad alta sicurezza**</span><span class="sxs-lookup"><span data-stu-id="30a4a-161">**High Confidence Phish**</span></span>

   - <span data-ttu-id="30a4a-162">**Destinatario di posta elettronica**: tutti gli utenti o solo i messaggi inviati all'utente.</span><span class="sxs-lookup"><span data-stu-id="30a4a-162">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="30a4a-163">Gli utenti finali possono gestire solo i messaggi in quarantena inviati.</span><span class="sxs-lookup"><span data-stu-id="30a4a-163">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="30a4a-164">Per cancellare il filtro, fare clic su **Cancella**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-164">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="30a4a-165">Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-165">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="30a4a-166">Utilizzare **Ordina i risultati per** (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per trovare messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="30a4a-166">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="30a4a-167">I caratteri jolly non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="30a4a-167">Wildcards aren't supported.</span></span> <span data-ttu-id="30a4a-168">È possibile cercare in base ai seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="30a4a-168">You can search by the following values:</span></span>

   - <span data-ttu-id="30a4a-169">**ID messaggio**: identificatore univoco globale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="30a4a-169">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="30a4a-170">Ad esempio, è stata utilizzata la [traccia dei messaggi](message-trace-scc.md) per cercare un messaggio che è stato inviato a un utente nell'organizzazione e si determina che il messaggio è stato messo in quarantena invece di essere recapitato.</span><span class="sxs-lookup"><span data-stu-id="30a4a-170">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="30a4a-171">Assicurarsi di includere il valore dell'ID messaggio completo, che può includere parentesi angolari\<\>().</span><span class="sxs-lookup"><span data-stu-id="30a4a-171">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="30a4a-172">Ad esempio: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="30a4a-172">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="30a4a-173">**Indirizzo di posta elettronica del mittente**: indirizzo di posta elettronica di un singolo mittente.</span><span class="sxs-lookup"><span data-stu-id="30a4a-173">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="30a4a-174">**Indirizzo di posta elettronica del destinatario**: indirizzo di posta elettronica di un singolo destinatario.</span><span class="sxs-lookup"><span data-stu-id="30a4a-174">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="30a4a-175">**Oggetto**: utilizzare l'intero oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="30a4a-175">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="30a4a-176">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="30a4a-176">The search is not case-sensitive.</span></span>

   <span data-ttu-id="30a4a-177">Dopo avere immesso i criteri di ricerca, fare clic sul ![pulsante Aggiorna](../../media/scc-quarantine-refresh.png) **Aggiorna** per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="30a4a-177">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="30a4a-178">Dopo aver trovato un messaggio in quarantena specifico, selezionarlo per visualizzarne i dettagli ed eseguire delle operazioni (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="30a4a-178">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="30a4a-179">Esportare i risultati di un messaggio</span><span class="sxs-lookup"><span data-stu-id="30a4a-179">Export message results</span></span>

1. <span data-ttu-id="30a4a-180">Selezionare i messaggi a cui si è interessati e quindi fare clic su **Esporta risultati**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-180">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="30a4a-181">Fare clic su **Sì** nel messaggio di conferma che avverte di tenere aperta la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="30a4a-181">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="30a4a-182">Una volta completata l'esportazione, è possibile assegnare un nome e scegliere il percorso di download per il file .csv.</span><span class="sxs-lookup"><span data-stu-id="30a4a-182">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="30a4a-183">Visualizzare i dettagli dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="30a4a-183">View quarantined message details</span></span>

<span data-ttu-id="30a4a-184">Quando si seleziona un messaggio di posta elettronica nell'elenco, i seguenti dettagli del messaggio vengono visualizzati nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="30a4a-184">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="30a4a-185">**ID messaggio**: identificatore univoco globale per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="30a4a-185">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="30a4a-186">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="30a4a-186">**Sender address**</span></span>

- <span data-ttu-id="30a4a-187">**Ricezione**: data/ora di ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="30a4a-187">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="30a4a-188">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="30a4a-188">**Subject**</span></span>

- <span data-ttu-id="30a4a-189">**Motivo della quarantena**: indica se un messaggio è stato identificato come **posta indesiderata**, in **blocco**, **phishing**, corrisponde a una regola del flusso di posta (**regola di trasporto**) oppure è stato identificato come contenente **malware**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-189">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="30a4a-190">**Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **Visualizza intestazione messaggio** per visualizzare l'elenco completo dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="30a4a-190">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="30a4a-191">**Scadenza**: data/ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="30a4a-191">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="30a4a-192">**Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="30a4a-192">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="30a4a-193">**Non ancora rilasciato in**: tutti gli eventuali messaggi di posta elettronica in cui il messaggio non è stato ancora rilasciato.</span><span class="sxs-lookup"><span data-stu-id="30a4a-193">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="30a4a-194">Eseguire azioni sulla posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="30a4a-194">Take action on quarantined email</span></span>

<span data-ttu-id="30a4a-195">Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le operazioni da eseguire con i messaggi nel riquadro a comparsa dei **Dettagli** :</span><span class="sxs-lookup"><span data-stu-id="30a4a-195">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="30a4a-196">**Rilascia messaggio**: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="30a4a-196">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="30a4a-197">**Segnalare i messaggi a Microsoft per l'analisi**: è selezionata per impostazione predefinita e segnala il messaggio in quarantena erroneamente a Microsoft come falso positivo.</span><span class="sxs-lookup"><span data-stu-id="30a4a-197">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="30a4a-198">Se il messaggio è stato messo in quarantena come posta indesiderata, rinfusa, phishing o contenente malware, il messaggio viene segnalato anche al team di analisi di posta indesiderata di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="30a4a-198">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="30a4a-199">A seconda dell'analisi, è possibile modificare le regole di filtro per la posta indesiderata a livello di servizio per consentire il passaggio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="30a4a-199">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="30a4a-200">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="30a4a-200">Choose one of the following options:</span></span>

    - <span data-ttu-id="30a4a-201">**Rilasciare messaggi a tutti i destinatari**</span><span class="sxs-lookup"><span data-stu-id="30a4a-201">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="30a4a-202">**Rilasciare messaggi a destinatari specifici**</span><span class="sxs-lookup"><span data-stu-id="30a4a-202">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="30a4a-203">**Rilasciare messaggi ad altri utenti**</span><span class="sxs-lookup"><span data-stu-id="30a4a-203">**Release messages to other people**</span></span>

  <span data-ttu-id="30a4a-204">Al termine, fare clic su **Rilascia messaggio**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-204">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="30a4a-205">Note sul rilascio dei messaggi:</span><span class="sxs-lookup"><span data-stu-id="30a4a-205">Notes about releasing messages:</span></span>

  - <span data-ttu-id="30a4a-206">Non è possibile rilasciare un messaggio allo stesso destinatario più di una volta.</span><span class="sxs-lookup"><span data-stu-id="30a4a-206">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="30a4a-207">Solo i destinatari che non hanno ricevuto il messaggio verranno visualizzati nell'elenco dei destinatari potenziali.</span><span class="sxs-lookup"><span data-stu-id="30a4a-207">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="30a4a-208">**Visualizza intestazione messaggio**: scegliere questo collegamento per vedere il testo dell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="30a4a-208">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="30a4a-209">Per analizzare i campi e i valori di intestazione in profondità, copiare il testo dell'intestazione del messaggio negli Appunti e quindi scegliere **analizzatore intestazione messaggio Microsoft** per accedere all'analizzatore connettività remota (fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si desidera lasciare Microsoft 365 per completare questa attività).</span><span class="sxs-lookup"><span data-stu-id="30a4a-209">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="30a4a-210">Incollare l'intestazione del messaggio nella pagina nella sezione Message Header Analyzer e scegliere **Analizza intestazioni**:</span><span class="sxs-lookup"><span data-stu-id="30a4a-210">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="30a4a-211">**Anteprima messaggio**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="30a4a-211">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="30a4a-212">**Visualizzazione origine**: mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.</span><span class="sxs-lookup"><span data-stu-id="30a4a-212">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="30a4a-213">**Visualizzazione testo**: Mostra il corpo del messaggio in testo normale.</span><span class="sxs-lookup"><span data-stu-id="30a4a-213">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="30a4a-214">**Rimuovi dalla quarantena**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente senza essere inviato ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="30a4a-214">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="30a4a-215">**Scarica il messaggio**: nel riquadro a comparsa visualizzato, selezionare **Sono consapevole dei rischi associati al download di questo messaggio** per salvare una copia locale del messaggio in formato .eml.</span><span class="sxs-lookup"><span data-stu-id="30a4a-215">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="30a4a-216">**Invia messaggio**: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="30a4a-216">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="30a4a-217">**Tipo di oggetto**: **posta elettronica** (impostazione predefinita), **URL**o **allegato**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-217">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="30a4a-218">**Formato di invio**: **ID messaggio di rete** (impostazione predefinita, con il valore corrispondente nella casella **ID messaggio di rete** ) oppure **file** (passare a un file local. eml o. msg).</span><span class="sxs-lookup"><span data-stu-id="30a4a-218">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="30a4a-219">Si noti che se si seleziona **file** e quindi si seleziona **ID messaggio di rete**, il valore iniziale è Gone.</span><span class="sxs-lookup"><span data-stu-id="30a4a-219">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="30a4a-220">**Destinatari**: digitare in lease un destinatario originale del messaggio oppure fare clic su **Seleziona tutto** per identificare tutti i destinatari.</span><span class="sxs-lookup"><span data-stu-id="30a4a-220">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="30a4a-221">È inoltre possibile fare clic su **Seleziona tutto** e quindi rimuovere selettivamente i singoli destinatari.</span><span class="sxs-lookup"><span data-stu-id="30a4a-221">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="30a4a-222">**Motivo dell'invio**: **non deve essere stato bloccato** (impostazione predefinita) o **deve essere stato bloccato**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-222">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="30a4a-223">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-223">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="30a4a-224">Se il messaggio non viene rilasciato o rimosso, verrà eliminato dopo la scadenza del periodo di conservazione in quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="30a4a-224">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="30a4a-225">Eseguire azioni su più messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="30a4a-225">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="30a4a-226">Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **Azioni in blocco** che consente di eseguire le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="30a4a-226">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="30a4a-227">**Rilascia messaggi**: le opzioni sono le stesse del rilascio di un singolo messaggio, ma non è possibile selezionare **Rilascia i messaggi a specifici destinatari**; è possibile selezionare solo **Rilascia il messaggio a tutti i destinatari** o **Rilascia i messaggi ad altre persone**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-227">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="30a4a-228">**Elimina messaggi**: dopo aver fatto clic su **Sì** nell'avviso visualizzato, i messaggi saranno immediatamente eliminati senza essere inviati ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="30a4a-228">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="30a4a-229">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-229">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="30a4a-230">Solo ATP: utilizzare il Centro sicurezza & Compliance per gestire i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="30a4a-230">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="30a4a-231">Le procedure per i file in quarantena in questa sezione sono disponibili solo per i sottoscrittori ATP Plan 1 e Plan 2.</span><span class="sxs-lookup"><span data-stu-id="30a4a-231">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="30a4a-232">Nelle organizzazioni con ATP, gli amministratori possono gestire i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="30a4a-232">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="30a4a-233">Visualizzare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="30a4a-233">View quarantined files</span></span>

1. <span data-ttu-id="30a4a-234">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-234">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="30a4a-235">Modificare la **visualizzazione in quarantena** nei **file**di valore predefiniti.</span><span class="sxs-lookup"><span data-stu-id="30a4a-235">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="30a4a-236">È possibile ordinare su un campo facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="30a4a-236">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="30a4a-237">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="30a4a-237">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="30a4a-238">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="30a4a-238">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="30a4a-239">Le colonne predefinite sono contrassegnate con un asterisco<sup>\*</sup>():</span><span class="sxs-lookup"><span data-stu-id="30a4a-239">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="30a4a-240">**Utente:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-240">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="30a4a-241">**Percorso**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-241">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="30a4a-242">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-242">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="30a4a-243">**URL file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-243">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="30a4a-244">**Dimensioni file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-244">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="30a4a-245">**Scadenza**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-245">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="30a4a-246">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="30a4a-246">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="30a4a-247">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="30a4a-247">**Detected by**</span></span>

   - <span data-ttu-id="30a4a-248">**Modificato dal tempo**</span><span class="sxs-lookup"><span data-stu-id="30a4a-248">**Modified by time**</span></span>

4. <span data-ttu-id="30a4a-249">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-249">To filter the results, click **Filter**.</span></span> <span data-ttu-id="30a4a-250">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="30a4a-250">The available filters are:</span></span>

   - <span data-ttu-id="30a4a-251">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="30a4a-251">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="30a4a-252">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="30a4a-252">**Today**</span></span>

     - <span data-ttu-id="30a4a-253">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="30a4a-253">**Next 2 days**</span></span>

     - <span data-ttu-id="30a4a-254">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="30a4a-254">**Next 7 days**</span></span>

     - <span data-ttu-id="30a4a-255">Un intervallo di data/ora personalizzato.</span><span class="sxs-lookup"><span data-stu-id="30a4a-255">A custom date/time range.</span></span>

   - <span data-ttu-id="30a4a-256">**Tempo ricevuto**</span><span class="sxs-lookup"><span data-stu-id="30a4a-256">**Received time**</span></span>

   - <span data-ttu-id="30a4a-257">**Motivo della quarantena**: l'unico valore disponibile è **malware**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-257">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="30a4a-258">Dopo aver individuato uno specifico file in quarantena, selezionare il file per visualizzarne i dettagli e per intervenire su di esso (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="30a4a-258">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="30a4a-259">Esportare i risultati dei file</span><span class="sxs-lookup"><span data-stu-id="30a4a-259">Export file results</span></span>

1. <span data-ttu-id="30a4a-260">Selezionare i file a cui si è interessati e fare clic su **Esporta risultati**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-260">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="30a4a-261">Fare clic su **Sì** nel messaggio di conferma che avverte di tenere aperta la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="30a4a-261">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="30a4a-262">Una volta completata l'esportazione, è possibile assegnare un nome e scegliere il percorso di download per il file .csv.</span><span class="sxs-lookup"><span data-stu-id="30a4a-262">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="30a4a-263">Visualizzare i dettagli dei file in quarantena</span><span class="sxs-lookup"><span data-stu-id="30a4a-263">View quarantined file details</span></span>

<span data-ttu-id="30a4a-264">Quando si seleziona un file nell'elenco, nel riquadro a comparsa dei **Dettagli** vengono visualizzati i dettagli dei file seguenti:</span><span class="sxs-lookup"><span data-stu-id="30a4a-264">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="30a4a-265">**FileName**</span><span class="sxs-lookup"><span data-stu-id="30a4a-265">**File Name**</span></span>

- <span data-ttu-id="30a4a-266">**URL file**: URL che definisce il percorso del file, ad esempio in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="30a4a-266">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="30a4a-267">**Contenuto dannoso rilevato** La data e l'ora in cui il file è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="30a4a-267">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="30a4a-268">**Scade**: la data in cui il file verrà eliminato dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="30a4a-268">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="30a4a-269">**Rilevato da**: ATP (Advanced Threat Protection) o dal motore antimalware di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="30a4a-269">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="30a4a-270">**Rilasciato?**</span><span class="sxs-lookup"><span data-stu-id="30a4a-270">**Released?**</span></span>

- <span data-ttu-id="30a4a-271">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="30a4a-271">**Malware Name**</span></span>

- <span data-ttu-id="30a4a-272">**ID documento**: identificatore univoco per il documento.</span><span class="sxs-lookup"><span data-stu-id="30a4a-272">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="30a4a-273">**Dimensioni file**: in KILOBYTE (KB).</span><span class="sxs-lookup"><span data-stu-id="30a4a-273">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="30a4a-274">**Organizzazione** ID univoco dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="30a4a-274">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="30a4a-275">**Data ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="30a4a-275">**Last modified**</span></span>

- <span data-ttu-id="30a4a-276">**Modified by**: l'ultimo utente che ha modificato il file.</span><span class="sxs-lookup"><span data-stu-id="30a4a-276">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="30a4a-277">**Secure Hash Algorithm 256-bit (SHA-256) valore**: è possibile utilizzare questo valore hash per identificare il file in altri archivi di reputazione o in altre posizioni nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="30a4a-277">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="30a4a-278">Eseguire un'azione sui file in quarantena</span><span class="sxs-lookup"><span data-stu-id="30a4a-278">Take action on quarantined files</span></span>

<span data-ttu-id="30a4a-279">Quando si seleziona un file nell'elenco, è possibile eseguire le azioni seguenti nel file nel riquadro a comparsa dei **Dettagli** :</span><span class="sxs-lookup"><span data-stu-id="30a4a-279">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="30a4a-280">**Rilasciare file**: selezionare (impostazione predefinita) o deselezionare **i file di report in Microsoft per l'analisi**e quindi fare clic su **rilascia file**.</span><span class="sxs-lookup"><span data-stu-id="30a4a-280">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="30a4a-281">**Scaricare il file**</span><span class="sxs-lookup"><span data-stu-id="30a4a-281">**Download file**</span></span>

- <span data-ttu-id="30a4a-282">**Rimuovi file dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="30a4a-282">**Remove file from quarantine**</span></span>

<span data-ttu-id="30a4a-283">Se i file non vengono rilasciati o rimossi, verranno eliminati dopo la scadenza del periodo di conservazione della quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="30a4a-283">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="30a4a-284">Azioni su più file in quarantena</span><span class="sxs-lookup"><span data-stu-id="30a4a-284">Actions on multiple quarantined files</span></span>

<span data-ttu-id="30a4a-285">Quando si selezionano più file in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **azioni in blocco** in cui è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="30a4a-285">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="30a4a-286">**Rilasciare i file**</span><span class="sxs-lookup"><span data-stu-id="30a4a-286">**Release files**</span></span>

- <span data-ttu-id="30a4a-287">**Elimina file**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, i file vengono eliminati immediatamente.</span><span class="sxs-lookup"><span data-stu-id="30a4a-287">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="30a4a-288">Se si utilizza un account aziendale o dell'Istituto di istruzione con privilegi di amministratore globale (o ruoli di sicurezza & conformità corretti) nell'organizzazione, accedere e [passare al centro sicurezza & conformità](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="30a4a-288">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="30a4a-289">Utilizzare Exchange Online PowerShell o standalone Exchange Online Protection PowerShell per visualizzare e gestire i messaggi e i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="30a4a-289">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="30a4a-290">I cmdlet utilizzati per visualizzare e gestire i messaggi e i file in quarantena sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="30a4a-290">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="30a4a-291">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="30a4a-291">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="30a4a-292">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="30a4a-292">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="30a4a-293">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="30a4a-293">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="30a4a-294">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): si noti che questo cmdlet è solo per i messaggi, non per i file malware da ATP per SharePoint Online, OneDrive for business o teams.</span><span class="sxs-lookup"><span data-stu-id="30a4a-294">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="30a4a-295">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="30a4a-295">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
