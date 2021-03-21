---
title: Gestire i messaggi e i file in quarantena come amministratore
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Gli amministratori possono imparare a visualizzare e gestire i messaggi in quarantena per tutti gli utenti in Exchange Online Protection (EOP). Gli amministratori delle organizzazioni con Microsoft Defender per Office 365 possono anche gestire i file in quarantena in SharePoint Online, OneDrive for Business e Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7fef752e8a02f7ed0dd4ed51854810a0d36d718b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926797"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="cd762-104">Gestire i messaggi e i file messi in quarantena come amministratore in EOP</span><span class="sxs-lookup"><span data-stu-id="cd762-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cd762-105">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="cd762-105">**Applies to**</span></span>
- [<span data-ttu-id="cd762-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cd762-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cd762-107">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="cd762-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="cd762-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd762-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="cd762-109">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="cd762-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="cd762-110">Per ulteriori informazioni, vedere [Quarantined email messages in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="cd762-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="cd762-111">Gli amministratori possono visualizzare, rilasciare ed eliminare tutti i tipi di messaggi in quarantena per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="cd762-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="cd762-112">Solo gli amministratori possono gestire i messaggi messi in quarantena come malware, phishing ad alta probabilità o come risultato delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="cd762-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="cd762-113">Gli amministratori possono anche segnalare falsi positivi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cd762-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="cd762-114">Gli amministratori delle organizzazioni con Microsoft Defender per Office 365 possono anche visualizzare, scaricare ed eliminare i file in quarantena in SharePoint Online, OneDrive for Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd762-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="cd762-115">È possibile visualizzare e gestire i messaggi in quarantena nel Centro sicurezza & conformità o in PowerShell (Exchange Online PowerShell per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="cd762-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cd762-116">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="cd762-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cd762-117">Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="cd762-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="cd762-118">Per aprire direttamente la pagina della quarantena, passare a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="cd762-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="cd762-119">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="cd762-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="cd762-120">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="cd762-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="cd762-121">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="cd762-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="cd762-122">Per eseguire un'azione sui messaggi in quarantena per tutti gli utenti, è necessario essere membri dei gruppi **di** ruoli Gestione **organizzazione,** Amministratore sicurezza o **Amministratore quarantena.** <sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="cd762-123">Per l'accesso in sola lettura ai messaggi in quarantena per tutti gli utenti, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="cd762-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="cd762-124">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="cd762-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="cd762-125">**Note**:</span><span class="sxs-lookup"><span data-stu-id="cd762-125">**Notes**:</span></span>

  - <span data-ttu-id="cd762-126">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cd762-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cd762-127">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cd762-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="cd762-128">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="cd762-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="cd762-129"><sup>\*</sup>I membri del **gruppo di** ruoli Amministratore  quarantena devono inoltre essere membri del gruppo di ruoli Gestione igiene in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) per eseguire le procedure di quarantena in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cd762-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="cd762-130">I messaggi in quarantena vengono conservati per un periodo di tempo predefinito prima di essere eliminati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="cd762-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="cd762-131">30 giorni per i messaggi messi in quarantena dai criteri di protezione da posta indesiderata (posta indesiderata, phishing e posta elettronica in blocco).</span><span class="sxs-lookup"><span data-stu-id="cd762-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="cd762-132">Questo è il valore predefinito e il valore massimo.</span><span class="sxs-lookup"><span data-stu-id="cd762-132">This is the default and maximum value.</span></span> <span data-ttu-id="cd762-133">Per configurare (inferiore) questo valore, vedere [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cd762-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="cd762-134">15 giorni per i messaggi che contengono malware.</span><span class="sxs-lookup"><span data-stu-id="cd762-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="cd762-135">15 giorni per i file messi in quarantena dagli allegati sicuri per SharePoint, OneDrive e Microsoft Teams in Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd762-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="cd762-136">Quando un messaggio scade dalla quarantena, non è possibile recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="cd762-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="cd762-137">Utilizzare il Centro sicurezza & conformità per gestire i messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="cd762-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="cd762-138">Visualizzare la posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="cd762-138">View quarantined email</span></span>

1. <span data-ttu-id="cd762-139">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="cd762-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="cd762-140">Verificare che **l'opzione Visualizza in** quarantena sia impostata sul valore predefinito **e-mail.**</span><span class="sxs-lookup"><span data-stu-id="cd762-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="cd762-141">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="cd762-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="cd762-142">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="cd762-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="cd762-143">I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="cd762-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="cd762-144">**Ricevuto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-145">**Mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-146">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-147">**Motivo della quarantena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-148">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-149">**Tipo di criterio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-150">**Scadenza**</span><span class="sxs-lookup"><span data-stu-id="cd762-150">**Expires**</span></span>
   - <span data-ttu-id="cd762-151">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="cd762-151">**Recipient**</span></span>
   - <span data-ttu-id="cd762-152">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="cd762-152">**Message ID**</span></span>
   - <span data-ttu-id="cd762-153">**Nome criterio**</span><span class="sxs-lookup"><span data-stu-id="cd762-153">**Policy name**</span></span>
   - <span data-ttu-id="cd762-154">**Dimensioni**</span><span class="sxs-lookup"><span data-stu-id="cd762-154">**Size**</span></span>
   - <span data-ttu-id="cd762-155">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="cd762-155">**Direction**</span></span>

   <span data-ttu-id="cd762-156">Al termine, fare clic su **Salva** o fare clic su **Imposta su valore predefinito**.</span><span class="sxs-lookup"><span data-stu-id="cd762-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="cd762-157">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="cd762-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="cd762-158">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="cd762-158">The available filters are:</span></span>

   - <span data-ttu-id="cd762-159">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="cd762-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="cd762-160">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="cd762-160">**Today**</span></span>
     - <span data-ttu-id="cd762-161">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="cd762-161">**Next 2 days**</span></span>
     - <span data-ttu-id="cd762-162">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="cd762-162">**Next 7 days**</span></span>
     - <span data-ttu-id="cd762-163">**Personalizzato**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="cd762-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="cd762-164">**Ora ricezione**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="cd762-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="cd762-165">**Motivo della quarantena**:</span><span class="sxs-lookup"><span data-stu-id="cd762-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="cd762-166">**Criterio**: il messaggio soddisfa le condizioni di una regola del flusso di posta (nota anche come regola di trasporto).</span><span class="sxs-lookup"><span data-stu-id="cd762-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="cd762-167">**Invio in blocco**</span><span class="sxs-lookup"><span data-stu-id="cd762-167">**Bulk**</span></span>
     - <span data-ttu-id="cd762-168">**Phish**: Il verdetto del filtro della posta indesiderata è stato **posta** elettronica di phishing o protezione anti-phishing messo in quarantena il messaggio ([impostazioni di spoofing](set-up-anti-phishing-policies.md#spoof-settings) o [protezione della rappresentazione).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="cd762-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="cd762-169">**Malware**</span><span class="sxs-lookup"><span data-stu-id="cd762-169">**Malware**</span></span>
     - <span data-ttu-id="cd762-170">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="cd762-170">**Spam**</span></span>
     - <span data-ttu-id="cd762-171">**Phish ad alta confidenza**</span><span class="sxs-lookup"><span data-stu-id="cd762-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="cd762-172">**Tipo di criteri**: filtrare i messaggi in base al tipo di criteri:</span><span class="sxs-lookup"><span data-stu-id="cd762-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="cd762-173">**Criteri antimalware**</span><span class="sxs-lookup"><span data-stu-id="cd762-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="cd762-174">**Criteri allegati sicuri**</span><span class="sxs-lookup"><span data-stu-id="cd762-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="cd762-175">**Criteri anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="cd762-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="cd762-176">**Criteri filtro contenuti ospitati** (criteri di protezione dalla posta indesiderata)</span><span class="sxs-lookup"><span data-stu-id="cd762-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="cd762-177">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="cd762-177">**Transport rule**</span></span>

   - <span data-ttu-id="cd762-178">**Destinatario di** posta elettronica : tutti gli utenti o solo i messaggi inviati all'utente.</span><span class="sxs-lookup"><span data-stu-id="cd762-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="cd762-179">Gli utenti finali possono gestire solo i messaggi in quarantena inviati.</span><span class="sxs-lookup"><span data-stu-id="cd762-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="cd762-180">Per cancellare il filtro, fare clic su **Cancella**.</span><span class="sxs-lookup"><span data-stu-id="cd762-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="cd762-181">Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="cd762-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="cd762-182">Utilizzare **Ordina i risultati per** (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per trovare messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="cd762-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="cd762-183">I caratteri jolly non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="cd762-183">Wildcards aren't supported.</span></span> <span data-ttu-id="cd762-184">È possibile cercare in base ai seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="cd762-184">You can search by the following values:</span></span>

   - <span data-ttu-id="cd762-185">**ID messaggio**: identificatore univoco globale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="cd762-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="cd762-186">Ad esempio, è [stata](message-trace-scc.md) utilizzata la traccia dei messaggi per cercare un messaggio inviato a un utente dell'organizzazione e si determina che il messaggio è stato messo in quarantena anziché recapitato.</span><span class="sxs-lookup"><span data-stu-id="cd762-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="cd762-187">Assicurarsi di includere il valore completo dell'ID messaggio, che potrebbe includere parentesi angolari ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="cd762-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="cd762-188">Ad esempio: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="cd762-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="cd762-189">**Indirizzo di posta elettronica del mittente**: indirizzo di posta elettronica di un singolo mittente.</span><span class="sxs-lookup"><span data-stu-id="cd762-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="cd762-190">**Nome dei criteri**: usare l'intero nome dei criteri del messaggio.</span><span class="sxs-lookup"><span data-stu-id="cd762-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="cd762-191">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="cd762-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="cd762-192">**Indirizzo di posta elettronica del destinatario**: indirizzo di posta elettronica di un singolo destinatario.</span><span class="sxs-lookup"><span data-stu-id="cd762-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="cd762-193">**Oggetto**: utilizzare l'intero oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="cd762-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="cd762-194">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="cd762-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="cd762-195">**Nome criterio**: Nome del criterio responsabile della messa in quaranta del messaggio.</span><span class="sxs-lookup"><span data-stu-id="cd762-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="cd762-196">Dopo avere immesso i criteri di ricerca, fare clic sul ![pulsante Aggiorna](../../media/scc-quarantine-refresh.png) **Aggiorna** per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="cd762-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="cd762-197">Dopo aver trovato un messaggio in quarantena specifico, selezionarlo per visualizzarne i dettagli ed eseguire delle operazioni (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="cd762-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="cd762-198">Visualizzare i dettagli dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="cd762-198">View quarantined message details</span></span>

<span data-ttu-id="cd762-199">Quando si seleziona un messaggio di posta elettronica nell'elenco, i seguenti dettagli del messaggio vengono visualizzati nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="cd762-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cd762-200">**ID messaggio**: identificatore univoco globale per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="cd762-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="cd762-201">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="cd762-201">**Sender address**</span></span>

- <span data-ttu-id="cd762-202">**Ricezione**: data/ora di ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="cd762-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="cd762-203">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="cd762-203">**Subject**</span></span>

- <span data-ttu-id="cd762-204">**Motivo quarantena:** indica se un messaggio è stato identificato come Posta **indesiderata,** In **blocco,** **Phish,** corrispondente a una regola del flusso di posta **(** Regola di trasporto ) o è stato identificato come contenente **malware.**</span><span class="sxs-lookup"><span data-stu-id="cd762-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="cd762-205">**Numero destinatari**</span><span class="sxs-lookup"><span data-stu-id="cd762-205">**Recipient count**</span></span>

- <span data-ttu-id="cd762-206">**Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **Visualizza intestazione messaggio** per visualizzare l'elenco completo dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="cd762-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="cd762-207">**Scadenza**: data/ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="cd762-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="cd762-208">**Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="cd762-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="cd762-209">**Non ancora rilasciato in**: tutti gli eventuali messaggi di posta elettronica in cui il messaggio non è stato ancora rilasciato.</span><span class="sxs-lookup"><span data-stu-id="cd762-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="cd762-210">Eseguire azioni sulla posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="cd762-210">Take action on quarantined email</span></span>

<span data-ttu-id="cd762-211">Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le azioni da eseguire con i messaggi **nel** riquadro a comparsa Dettagli:</span><span class="sxs-lookup"><span data-stu-id="cd762-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cd762-212">**Messaggio di** rilascio : nel riquadro a comparsa visualizzato scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd762-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="cd762-213">**Segnala i messaggi a Microsoft** per l'analisi: questa opzione è selezionata per impostazione predefinita e segnala il messaggio erroneamente messo in quarantena a Microsoft come falso positivo.</span><span class="sxs-lookup"><span data-stu-id="cd762-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="cd762-214">Se il messaggio è stato messo in quarantena come posta indesiderata, in blocco, phishing o contenente malware, il messaggio viene segnalato anche al team di analisi della posta indesiderata di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cd762-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="cd762-215">A seconda dell'analisi, le regole di filtro della posta indesiderata a livello di servizio potrebbero essere modificate per consentire l'invio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="cd762-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="cd762-216">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd762-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="cd762-217">**Rilasciare messaggi a tutti i destinatari**</span><span class="sxs-lookup"><span data-stu-id="cd762-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="cd762-218">**Rilasciare messaggi a destinatari specifici**</span><span class="sxs-lookup"><span data-stu-id="cd762-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="cd762-219">**Rilasciare messaggi ad altre persone:** si noti che il rilascio di messaggi di malware a persone diverse dai destinatari originali non è supportato.</span><span class="sxs-lookup"><span data-stu-id="cd762-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="cd762-220">Al termine, fare clic su **Rilascia messaggio**.</span><span class="sxs-lookup"><span data-stu-id="cd762-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="cd762-221">Note sul rilascio dei messaggi:</span><span class="sxs-lookup"><span data-stu-id="cd762-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="cd762-222">Non è possibile rilasciare un messaggio allo stesso destinatario più di una volta.</span><span class="sxs-lookup"><span data-stu-id="cd762-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="cd762-223">Solo i destinatari che non hanno ricevuto il messaggio verranno visualizzati nell'elenco dei potenziali destinatari.</span><span class="sxs-lookup"><span data-stu-id="cd762-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="cd762-224">**Visualizza intestazione messaggio**: scegliere questo collegamento per vedere il testo dell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="cd762-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="cd762-225">Per analizzare i campi dell'intestazione e i valori in modo approfondito, copiare il testo negli Appunti e poi scegliere **Microsoft Message Header Analyzer** per passare all'Analizzatore connettività remota. Fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si vuole uscire da Microsoft 365 per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="cd762-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="cd762-226">Incollare l'intestazione del messaggio nella pagina nella sezione Message Header Analyzer e scegliere **Analizza intestazioni**:</span><span class="sxs-lookup"><span data-stu-id="cd762-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="cd762-227">**Anteprima messaggio**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="cd762-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="cd762-228">**Visualizzazione origine**: mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.</span><span class="sxs-lookup"><span data-stu-id="cd762-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="cd762-229">**Visualizzazione testo**: Mostra il corpo del messaggio in testo normale.</span><span class="sxs-lookup"><span data-stu-id="cd762-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="cd762-230">**Rimuovi dalla quarantena:** dopo aver fatto clic su **Sì** nell'avviso visualizzato, il messaggio viene immediatamente eliminato senza essere inviato ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="cd762-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="cd762-231">**Scarica il messaggio**: nel riquadro a comparsa visualizzato, selezionare **Sono consapevole dei rischi associati al download di questo messaggio** per salvare una copia locale del messaggio in formato .eml.</span><span class="sxs-lookup"><span data-stu-id="cd762-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="cd762-232">**Invia messaggio**: nel riquadro a comparsa visualizzato scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd762-232">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="cd762-233">**Tipo di oggetto**: **Posta** elettronica (impostazione predefinita), **URL** o **Allegato.**</span><span class="sxs-lookup"><span data-stu-id="cd762-233">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="cd762-234">**Formato invio**: **ID messaggio** di rete (impostazione predefinita, con il valore corrispondente nella casella **ID** messaggio di rete) o **File** (passare a un file con estensione eml o msg locale).</span><span class="sxs-lookup"><span data-stu-id="cd762-234">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="cd762-235">Si noti che se si seleziona **File** e quindi si seleziona **ID messaggio di** rete , il valore iniziale non è più disponibile.</span><span class="sxs-lookup"><span data-stu-id="cd762-235">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="cd762-236">**Destinatari**: digitare in lease un destinatario originale del messaggio oppure fare clic **su Seleziona** tutto per identificare tutti i destinatari.</span><span class="sxs-lookup"><span data-stu-id="cd762-236">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="cd762-237">È inoltre possibile fare clic **su Seleziona tutto** e quindi rimuovere in modo selettivo singoli destinatari.</span><span class="sxs-lookup"><span data-stu-id="cd762-237">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="cd762-238">**Motivo dell'invio:** **non deve essere stato bloccato** (impostazione predefinita) o Deve essere **bloccato**.</span><span class="sxs-lookup"><span data-stu-id="cd762-238">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="cd762-239">Al termine, fare clic su **Invia.**</span><span class="sxs-lookup"><span data-stu-id="cd762-239">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="cd762-240">Se il messaggio non viene rilasciato o rimosso, verrà eliminato dopo la scadenza del periodo di conservazione in quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="cd762-240">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="cd762-241">Eseguire azioni su più messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="cd762-241">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="cd762-242">Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **Azioni in blocco** che consente di eseguire le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="cd762-242">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="cd762-243">**Rilascia messaggi**: le opzioni sono le stesse del rilascio di un singolo messaggio, ma non è possibile selezionare **Rilascia i messaggi a specifici destinatari**; è possibile selezionare solo **Rilascia il messaggio a tutti i destinatari** o **Rilascia i messaggi ad altre persone**.</span><span class="sxs-lookup"><span data-stu-id="cd762-243">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cd762-244">Considerare lo scenario seguente: john@gmail.com un messaggio a faith@contoso.com e john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cd762-244">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="cd762-245">Gmail biforca questo messaggio in due copie che vengono entrambe instradati in quarantena come phishing in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cd762-245">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="cd762-246">Un amministratore rilascia entrambi questi messaggi a admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="cd762-246">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="cd762-247">Viene recapitato il primo messaggio rilasciato che raggiunge la cassetta postale dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="cd762-247">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="cd762-248">Il secondo messaggio rilasciato viene identificato come recapito duplicato e viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="cd762-248">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="cd762-249">I messaggi vengono identificati come duplicati se hanno lo stesso ID messaggio e l'ora di ricezione.</span><span class="sxs-lookup"><span data-stu-id="cd762-249">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="cd762-250">**Elimina messaggi**: Dopo aver fatto clic su **Sì** nell'avviso visualizzato, i messaggi vengono immediatamente eliminati senza essere inviati ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="cd762-250">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="cd762-251">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="cd762-251">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="cd762-252">Solo Microsoft Defender per Office 365: usare il Centro sicurezza & conformità per gestire i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="cd762-252">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="cd762-253">Le procedure per i file in quarantena in questa sezione sono disponibili solo per gli abbonati a Microsoft Defender per Office 365 Piano 1 e Piano 2.</span><span class="sxs-lookup"><span data-stu-id="cd762-253">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="cd762-254">Nelle organizzazioni con Defender per Office 365, gli amministratori possono gestire i file in quarantena in SharePoint Online, OneDrive for Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd762-254">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="cd762-255">Per abilitare la protezione per questi file, vedere Attivare allegati sicuri [per SharePoint, OneDrive e Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="cd762-255">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="cd762-256">Visualizzare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="cd762-256">View quarantined files</span></span>

1. <span data-ttu-id="cd762-257">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="cd762-257">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="cd762-258">Modificare **La visualizzazione in quarantena** per i file di **valore**.</span><span class="sxs-lookup"><span data-stu-id="cd762-258">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="cd762-259">È possibile ordinare un campo facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="cd762-259">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="cd762-260">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="cd762-260">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="cd762-261">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="cd762-261">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="cd762-262">Le colonne predefinite sono contrassegnate con un asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="cd762-262">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="cd762-263">**Utente:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-263">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-264">**Posizione**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-264">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-265">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-265">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-266">**File URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-266">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-267">**Dimensioni file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-267">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-268">**Scadenza**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-268">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-269">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="cd762-269">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="cd762-270">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="cd762-270">**Detected by**</span></span>
   - <span data-ttu-id="cd762-271">**Modificato in base all'ora**</span><span class="sxs-lookup"><span data-stu-id="cd762-271">**Modified by time**</span></span>

4. <span data-ttu-id="cd762-272">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="cd762-272">To filter the results, click **Filter**.</span></span> <span data-ttu-id="cd762-273">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="cd762-273">The available filters are:</span></span>

   - <span data-ttu-id="cd762-274">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="cd762-274">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="cd762-275">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="cd762-275">**Today**</span></span>
     - <span data-ttu-id="cd762-276">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="cd762-276">**Next 2 days**</span></span>
     - <span data-ttu-id="cd762-277">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="cd762-277">**Next 7 days**</span></span>
     - <span data-ttu-id="cd762-278">Intervallo di data/ora personalizzato.</span><span class="sxs-lookup"><span data-stu-id="cd762-278">A custom date/time range.</span></span>
   - <span data-ttu-id="cd762-279">**Ora ricezione**</span><span class="sxs-lookup"><span data-stu-id="cd762-279">**Received time**</span></span>
   - <span data-ttu-id="cd762-280">**Motivo quarantena:** l'unico valore disponibile è **Malware.**</span><span class="sxs-lookup"><span data-stu-id="cd762-280">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="cd762-281">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="cd762-281">**Policy type**</span></span>

<span data-ttu-id="cd762-282">Dopo aver trovato un file in quarantena specifico, selezionare il file per visualizzare i dettagli su di esso e per eseguire un'azione su di esso (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="cd762-282">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="cd762-283">Visualizzare i dettagli dei file in quarantena</span><span class="sxs-lookup"><span data-stu-id="cd762-283">View quarantined file details</span></span>

<span data-ttu-id="cd762-284">Quando si seleziona un file nell'elenco, nel  riquadro a comparsa Dettagli vengono visualizzati i dettagli del file seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd762-284">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cd762-285">**FileName**</span><span class="sxs-lookup"><span data-stu-id="cd762-285">**File Name**</span></span>
- <span data-ttu-id="cd762-286">**URL file**: URL che definisce il percorso del file, ad esempio in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cd762-286">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="cd762-287">**Contenuto dannoso rilevato in** Data/ora in cui il file è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="cd762-287">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="cd762-288">**Scadenza: data** in cui il file verrà eliminato dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="cd762-288">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="cd762-289">**Rilevato da**: Defender per Office 365 o il motore antimalware di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cd762-289">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="cd762-290">**Rilasciato?**</span><span class="sxs-lookup"><span data-stu-id="cd762-290">**Released?**</span></span>
- <span data-ttu-id="cd762-291">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="cd762-291">**Malware Name**</span></span>
- <span data-ttu-id="cd762-292">**ID documento:** identificatore univoco per il documento.</span><span class="sxs-lookup"><span data-stu-id="cd762-292">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="cd762-293">**Dimensioni file**: in kilobyte (KB).</span><span class="sxs-lookup"><span data-stu-id="cd762-293">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="cd762-294">**Organizzazione** ID univoco dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cd762-294">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="cd762-295">**Data ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="cd762-295">**Last modified**</span></span>
- <span data-ttu-id="cd762-296">**Modified By**: L'ultimo utente che ha modificato il file.</span><span class="sxs-lookup"><span data-stu-id="cd762-296">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="cd762-297">**Valore SECURE Hash Algorithm a 256 bit (SHA-256):** è possibile utilizzare questo valore hash per identificare il file in altri archivi di reputazione o in altre posizioni dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="cd762-297">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="cd762-298">Eseguire un'azione sui file in quarantena</span><span class="sxs-lookup"><span data-stu-id="cd762-298">Take action on quarantined files</span></span>

<span data-ttu-id="cd762-299">Quando si seleziona un file nell'elenco, è possibile eseguire le azioni seguenti sul file nel **riquadro a** comparsa Dettagli:</span><span class="sxs-lookup"><span data-stu-id="cd762-299">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="cd762-300">**Release files**: Selezionare (impostazione predefinita) o deselezionare **Segnala file a Microsoft per** l'analisi e quindi fare clic su Rilascia **file**.</span><span class="sxs-lookup"><span data-stu-id="cd762-300">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="cd762-301">**Scarica file**</span><span class="sxs-lookup"><span data-stu-id="cd762-301">**Download file**</span></span>
- <span data-ttu-id="cd762-302">**Rimuovi file dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="cd762-302">**Remove file from quarantine**</span></span>

<span data-ttu-id="cd762-303">Se non si rilasciano o non si rimuovono i file, questi verranno eliminati dopo la scadenza del periodo di conservazione della quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="cd762-303">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="cd762-304">Azioni su più file in quarantena</span><span class="sxs-lookup"><span data-stu-id="cd762-304">Actions on multiple quarantined files</span></span>

<span data-ttu-id="cd762-305">Quando si selezionano più file in quarantena nell'elenco  (fino a 100), viene visualizzato il riquadro a comparsa Azioni in blocco in cui è possibile eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cd762-305">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="cd762-306">**Rilascia file**</span><span class="sxs-lookup"><span data-stu-id="cd762-306">**Release files**</span></span>
- <span data-ttu-id="cd762-307">**Elimina file**: Dopo aver fatto clic su **Sì** nell'avviso visualizzato, i file vengono eliminati immediatamente.</span><span class="sxs-lookup"><span data-stu-id="cd762-307">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="cd762-308">Utilizzare PowerShell di Exchange Online o PowerShell EOP autonomo per visualizzare e gestire i messaggi e i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="cd762-308">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="cd762-309">I cmdlet utilizzati per visualizzare e gestire i messaggi e i file in quarantena sono:</span><span class="sxs-lookup"><span data-stu-id="cd762-309">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="cd762-310">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="cd762-310">Delete-QuarantineMessage</span></span>](/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="cd762-311">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="cd762-311">Export-QuarantineMessage</span></span>](/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="cd762-312">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="cd762-312">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="cd762-313">[Preview-QuarantineMessage:](/powershell/module/exchange/preview-quarantinemessage)si noti che questo cmdlet è solo per i messaggi, non per i file di malware provenienti da Allegati sicuri per SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cd762-313">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="cd762-314">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="cd762-314">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)