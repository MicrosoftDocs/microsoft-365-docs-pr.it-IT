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
ms.openlocfilehash: 5f4d63576e57ac50abe1ec1eb378221c4d457280
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659987"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="e4465-104">Gestire i messaggi e i file messi in quarantena come amministratore in EOP</span><span class="sxs-lookup"><span data-stu-id="e4465-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e4465-105">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, la quarantena contiene messaggi potenzialmente pericolosi o indesiderati.</span><span class="sxs-lookup"><span data-stu-id="e4465-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="e4465-106">Per ulteriori informazioni, vedere [messaggi di posta elettronica in quarantena in EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e4465-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e4465-107">Gli amministratori possono visualizzare, rilasciare ed eliminare tutti i tipi di messaggi in quarantena per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="e4465-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="e4465-108">Solo gli amministratori possono gestire i messaggi che sono stati messi in quarantena come malware, phishing ad alta sicurezza o come risultato delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="e4465-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="e4465-109">Gli amministratori possono anche segnalare falsi positivi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4465-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="e4465-110">Gli amministratori nelle organizzazioni con Microsoft Defender per Office 365 possono anche visualizzare, scaricare ed eliminare i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="e4465-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="e4465-111">È possibile visualizzare e gestire i messaggi in quarantena nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="e4465-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e4465-112">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e4465-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e4465-113">Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="e4465-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="e4465-114">Per aprire direttamente la pagina della quarantena, passare a <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="e4465-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="e4465-115">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e4465-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e4465-116">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e4465-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e4465-117">Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:</span><span class="sxs-lookup"><span data-stu-id="e4465-117">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e4465-118">Per eseguire un'azione sui messaggi in quarantena per tutti gli utenti, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione**, **amministratore sicurezza** o **quarantena amministratore** <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="e4465-118">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="e4465-119">Per l'accesso in sola lettura ai messaggi in quarantena per tutti gli utenti, è necessario essere membri dei gruppi di ruoli **lettore globale** o **lettore di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="e4465-119">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e4465-120">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e4465-120">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="e4465-121">**Note**:</span><span class="sxs-lookup"><span data-stu-id="e4465-121">**Notes**:</span></span>

  - <span data-ttu-id="e4465-122">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4465-122">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e4465-123">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="e4465-123">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="e4465-124">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e4465-124">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="e4465-125"><sup>\*</sup> I membri del gruppo di ruoli **amministratore di quarantena** devono essere anche membri del gruppo di ruoli **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) per eseguire le procedure di quarantena in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e4465-125"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="e4465-126">I messaggi in quarantena vengono mantenuti per un periodo di tempo predefinito prima di essere eliminati automaticamente:</span><span class="sxs-lookup"><span data-stu-id="e4465-126">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="e4465-127">30 giorni per i messaggi messi in quarantena dai criteri di protezione dalla posta indesiderata (posta indesiderata, phishing e massa).</span><span class="sxs-lookup"><span data-stu-id="e4465-127">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="e4465-128">Questo è il valore predefinito e massimo.</span><span class="sxs-lookup"><span data-stu-id="e4465-128">This is the default and maximum value.</span></span> <span data-ttu-id="e4465-129">Per configurare (abbassare) questo valore, vedere Configurare i criteri di protezione dalla [posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e4465-129">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="e4465-130">15 giorni per i messaggi che contengono malware.</span><span class="sxs-lookup"><span data-stu-id="e4465-130">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="e4465-131">15 giorni per i file messi in quarantena da ATP per SharePoint, OneDrive e Microsoft teams in Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4465-131">15 days for files quarantined by ATP for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="e4465-132">Quando un messaggio scade dalla quarantena, non è possibile ripristinarlo.</span><span class="sxs-lookup"><span data-stu-id="e4465-132">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="e4465-133">Utilizzare il Centro sicurezza & conformità per gestire i messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="e4465-133">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="e4465-134">Visualizzazione posta in quarantena</span><span class="sxs-lookup"><span data-stu-id="e4465-134">View quarantined email</span></span>

1. <span data-ttu-id="e4465-135">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="e4465-135">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e4465-136">Verificare che la **visualizzazione in quarantena** sia impostata sul valore predefinito **e-mail**.</span><span class="sxs-lookup"><span data-stu-id="e4465-136">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="e4465-137">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="e4465-137">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e4465-138">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="e4465-138">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e4465-139">I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="e4465-139">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e4465-140">**Ricevuto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-140">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-141">**Mittente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-141">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-142">**Oggetto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-142">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-143">**Motivo della quarantena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-143">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-144">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-144">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-145">**Tipo di criterio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-145">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-146">**Scadenza**</span><span class="sxs-lookup"><span data-stu-id="e4465-146">**Expires**</span></span>
   - <span data-ttu-id="e4465-147">**Destinatario**</span><span class="sxs-lookup"><span data-stu-id="e4465-147">**Recipient**</span></span>
   - <span data-ttu-id="e4465-148">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="e4465-148">**Message ID**</span></span>
   - <span data-ttu-id="e4465-149">**Nome criterio**</span><span class="sxs-lookup"><span data-stu-id="e4465-149">**Policy name**</span></span>
   - <span data-ttu-id="e4465-150">**Dimensioni**</span><span class="sxs-lookup"><span data-stu-id="e4465-150">**Size**</span></span>
   - <span data-ttu-id="e4465-151">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="e4465-151">**Direction**</span></span>

   <span data-ttu-id="e4465-152">Al termine, fare clic su **Salva** o fare clic su **Imposta su valore predefinito**.</span><span class="sxs-lookup"><span data-stu-id="e4465-152">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="e4465-153">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="e4465-153">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e4465-154">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="e4465-154">The available filters are:</span></span>

   - <span data-ttu-id="e4465-155">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="e4465-155">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="e4465-156">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="e4465-156">**Today**</span></span>
     - <span data-ttu-id="e4465-157">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="e4465-157">**Next 2 days**</span></span>
     - <span data-ttu-id="e4465-158">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="e4465-158">**Next 7 days**</span></span>
     - <span data-ttu-id="e4465-159">**Personalizzato**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="e4465-159">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e4465-160">**Ora ricezione**: immettere una **data di inizio** e una **data di fine**.</span><span class="sxs-lookup"><span data-stu-id="e4465-160">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e4465-161">**Motivo della quarantena**:</span><span class="sxs-lookup"><span data-stu-id="e4465-161">**Quarantine reason**:</span></span>
     - <span data-ttu-id="e4465-162">**Criterio**: il messaggio corrisponde alle condizioni di una regola del flusso di posta (nota anche come regola di trasporto).</span><span class="sxs-lookup"><span data-stu-id="e4465-162">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="e4465-163">**Invio in blocco**</span><span class="sxs-lookup"><span data-stu-id="e4465-163">**Bulk**</span></span>
     - <span data-ttu-id="e4465-164">**Phishing**: il verdetto del filtro di posta indesiderata è la **posta elettronica di phishing** o la protezione anti-phishing messa in quarantena del messaggio ([spoofing](set-up-anti-phishing-policies.md#spoof-settings) o [rappresentazione](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="e4465-164">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="e4465-165">**Malware**</span><span class="sxs-lookup"><span data-stu-id="e4465-165">**Malware**</span></span>
     - <span data-ttu-id="e4465-166">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="e4465-166">**Spam**</span></span>
     - <span data-ttu-id="e4465-167">**Phishing ad alta sicurezza**</span><span class="sxs-lookup"><span data-stu-id="e4465-167">**High Confidence Phish**</span></span>

   - <span data-ttu-id="e4465-168">**Tipo di criteri**: filtrare i messaggi in base al tipo di criteri:</span><span class="sxs-lookup"><span data-stu-id="e4465-168">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="e4465-169">**Criteri anti-malware**</span><span class="sxs-lookup"><span data-stu-id="e4465-169">**Anti-malware policy**</span></span>
     - <span data-ttu-id="e4465-170">**Criteri allegati sicuri**</span><span class="sxs-lookup"><span data-stu-id="e4465-170">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="e4465-171">**Criteri anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="e4465-171">**Anti-phish policy**</span></span>
     - <span data-ttu-id="e4465-172">**Criteri filtro contenuti ospitati** (criteri di protezione dalla posta indesiderata)</span><span class="sxs-lookup"><span data-stu-id="e4465-172">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="e4465-173">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="e4465-173">**Transport rule**</span></span>

   - <span data-ttu-id="e4465-174">**Destinatario di posta elettronica**: tutti gli utenti o solo i messaggi inviati all'utente.</span><span class="sxs-lookup"><span data-stu-id="e4465-174">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="e4465-175">Gli utenti finali possono gestire solo i messaggi in quarantena inviati.</span><span class="sxs-lookup"><span data-stu-id="e4465-175">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="e4465-176">Per cancellare il filtro, fare clic su **Cancella**.</span><span class="sxs-lookup"><span data-stu-id="e4465-176">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="e4465-177">Per nascondere il riquadro a comparsa del filtro, fare di nuovo clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="e4465-177">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="e4465-178">Utilizzare **Ordina i risultati per** (il pulsante **ID messaggio** per impostazione predefinita) e un valore corrispondente per trovare messaggi specifici.</span><span class="sxs-lookup"><span data-stu-id="e4465-178">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="e4465-179">I caratteri jolly non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="e4465-179">Wildcards aren't supported.</span></span> <span data-ttu-id="e4465-180">È possibile cercare in base ai seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="e4465-180">You can search by the following values:</span></span>

   - <span data-ttu-id="e4465-181">**ID messaggio**: identificatore univoco globale del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e4465-181">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="e4465-182">Ad esempio, è stata utilizzata la [traccia dei messaggi](message-trace-scc.md) per cercare un messaggio che è stato inviato a un utente nell'organizzazione e si determina che il messaggio è stato messo in quarantena invece di essere recapitato.</span><span class="sxs-lookup"><span data-stu-id="e4465-182">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="e4465-183">Assicurarsi di includere il valore dell'ID messaggio completo, che può includere parentesi angolari ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="e4465-183">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="e4465-184">Ad esempio: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>` .</span><span class="sxs-lookup"><span data-stu-id="e4465-184">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="e4465-185">**Indirizzo di posta elettronica del mittente**: indirizzo di posta elettronica di un singolo mittente.</span><span class="sxs-lookup"><span data-stu-id="e4465-185">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="e4465-186">**Nome dei criteri**: usare l'intero nome dei criteri del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e4465-186">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="e4465-187">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="e4465-187">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="e4465-188">**Indirizzo di posta elettronica del destinatario**: indirizzo di posta elettronica di un singolo destinatario.</span><span class="sxs-lookup"><span data-stu-id="e4465-188">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="e4465-189">**Oggetto**: utilizzare l'intero oggetto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e4465-189">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="e4465-190">Per la ricerca non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="e4465-190">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="e4465-191">**Nome criterio**: il nome del criterio responsabile della messa in quarantena del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e4465-191">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="e4465-192">Dopo avere immesso i criteri di ricerca, fare clic sul ![pulsante Aggiorna](../../media/scc-quarantine-refresh.png) **Aggiorna** per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e4465-192">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="e4465-193">Dopo aver trovato un messaggio in quarantena specifico, selezionarlo per visualizzarne i dettagli ed eseguire delle operazioni (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="e4465-193">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="e4465-194">Visualizzare i dettagli dei messaggi in quarantena</span><span class="sxs-lookup"><span data-stu-id="e4465-194">View quarantined message details</span></span>

<span data-ttu-id="e4465-195">Quando si seleziona un messaggio di posta elettronica nell'elenco, i seguenti dettagli del messaggio vengono visualizzati nel riquadro a comparsa **Dettagli**:</span><span class="sxs-lookup"><span data-stu-id="e4465-195">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e4465-196">**ID messaggio**: identificatore univoco globale per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="e4465-196">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="e4465-197">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="e4465-197">**Sender address**</span></span>

- <span data-ttu-id="e4465-198">**Ricezione**: data/ora di ricezione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e4465-198">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="e4465-199">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="e4465-199">**Subject**</span></span>

- <span data-ttu-id="e4465-200">**Motivo della quarantena**: indica se un messaggio è stato identificato come **posta indesiderata**, in **blocco**, **phishing**, corrisponde a una regola del flusso di posta (**regola di trasporto**) oppure è stato identificato come contenente **malware**.</span><span class="sxs-lookup"><span data-stu-id="e4465-200">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="e4465-201">**Numero destinatari**</span><span class="sxs-lookup"><span data-stu-id="e4465-201">**Recipient count**</span></span>

- <span data-ttu-id="e4465-202">**Destinatari**: se il messaggio contiene più destinatari, è necessario fare clic su **Anteprima messaggio** o **Visualizza intestazione messaggio** per visualizzare l'elenco completo dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="e4465-202">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="e4465-203">**Scadenza**: data/ora in cui il messaggio verrà eliminato automaticamente e definitivamente dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="e4465-203">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="e4465-204">**Rilasciato a**: tutti gli eventuali indirizzi di posta elettronica a cui il messaggio è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="e4465-204">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="e4465-205">**Non ancora rilasciato in**: tutti gli eventuali messaggi di posta elettronica in cui il messaggio non è stato ancora rilasciato.</span><span class="sxs-lookup"><span data-stu-id="e4465-205">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="e4465-206">Eseguire azioni sulla posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="e4465-206">Take action on quarantined email</span></span>

<span data-ttu-id="e4465-207">Dopo aver selezionato un messaggio, sono disponibili diverse opzioni per le operazioni da eseguire con i messaggi nel riquadro a comparsa dei **Dettagli** :</span><span class="sxs-lookup"><span data-stu-id="e4465-207">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e4465-208">**Rilascia messaggio**: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4465-208">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e4465-209">**Segnalare i messaggi a Microsoft per l'analisi**: è selezionata per impostazione predefinita e segnala il messaggio in quarantena erroneamente a Microsoft come falso positivo.</span><span class="sxs-lookup"><span data-stu-id="e4465-209">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="e4465-210">Se il messaggio è stato messo in quarantena come posta indesiderata, rinfusa, phishing o contenente malware, il messaggio viene segnalato anche al team di analisi di posta indesiderata di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4465-210">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="e4465-211">A seconda dell'analisi, è possibile modificare le regole di filtro per la posta indesiderata a livello di servizio per consentire il passaggio del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e4465-211">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="e4465-212">Scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4465-212">Choose one of the following options:</span></span>
    - <span data-ttu-id="e4465-213">**Rilasciare messaggi a tutti i destinatari**</span><span class="sxs-lookup"><span data-stu-id="e4465-213">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="e4465-214">**Rilasciare messaggi a destinatari specifici**</span><span class="sxs-lookup"><span data-stu-id="e4465-214">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="e4465-215">**Rilasciare messaggi ad altre persone**: si noti che il rilascio di messaggi di malware a utenti diversi dai destinatari originali non è supportato.</span><span class="sxs-lookup"><span data-stu-id="e4465-215">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="e4465-216">Al termine, fare clic su **Rilascia messaggio**.</span><span class="sxs-lookup"><span data-stu-id="e4465-216">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="e4465-217">Note sul rilascio dei messaggi:</span><span class="sxs-lookup"><span data-stu-id="e4465-217">Notes about releasing messages:</span></span>

  - <span data-ttu-id="e4465-218">Non è possibile rilasciare un messaggio allo stesso destinatario più di una volta.</span><span class="sxs-lookup"><span data-stu-id="e4465-218">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="e4465-219">Solo i destinatari che non hanno ricevuto il messaggio verranno visualizzati nell'elenco dei destinatari potenziali.</span><span class="sxs-lookup"><span data-stu-id="e4465-219">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="e4465-220">**Visualizza intestazione messaggio**: scegliere questo collegamento per vedere il testo dell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e4465-220">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="e4465-221">Per analizzare i campi dell'intestazione e i valori in modo approfondito, copiare il testo negli Appunti e poi scegliere **Microsoft Message Header Analyzer** per passare all'Analizzatore connettività remota. Fare clic con il pulsante destro del mouse e scegliere **Apri in una nuova scheda** se non si vuole uscire da Microsoft 365 per completare questa attività.</span><span class="sxs-lookup"><span data-stu-id="e4465-221">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="e4465-222">Incollare l'intestazione del messaggio nella pagina nella sezione Message Header Analyzer e scegliere **Analizza intestazioni**:</span><span class="sxs-lookup"><span data-stu-id="e4465-222">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="e4465-223">**Anteprima messaggio**: nel riquadro a comparsa visualizzato, scegliere una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="e4465-223">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="e4465-224">**Visualizzazione origine**: mostra la versione HTML del corpo del messaggio con tutti i collegamenti disabilitati.</span><span class="sxs-lookup"><span data-stu-id="e4465-224">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="e4465-225">**Visualizzazione testo**: Mostra il corpo del messaggio in testo normale.</span><span class="sxs-lookup"><span data-stu-id="e4465-225">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="e4465-226">**Rimuovi dalla quarantena**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, il messaggio viene eliminato immediatamente senza essere inviato ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="e4465-226">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="e4465-227">**Scarica il messaggio**: nel riquadro a comparsa visualizzato, selezionare **Sono consapevole dei rischi associati al download di questo messaggio** per salvare una copia locale del messaggio in formato .eml.</span><span class="sxs-lookup"><span data-stu-id="e4465-227">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="e4465-228">**Invia messaggio**: nel riquadro a comparsa visualizzato, scegliere le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4465-228">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e4465-229">**Tipo di oggetto**: **posta elettronica** (impostazione predefinita), **URL** o **allegato**.</span><span class="sxs-lookup"><span data-stu-id="e4465-229">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="e4465-230">**Formato di invio**: **ID messaggio di rete** (impostazione predefinita, con il valore corrispondente nella casella **ID messaggio di rete** ) oppure **file** (passare a un file local. eml o. msg).</span><span class="sxs-lookup"><span data-stu-id="e4465-230">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="e4465-231">Si noti che se si seleziona **file** e quindi si seleziona **ID messaggio di rete**, il valore iniziale è Gone.</span><span class="sxs-lookup"><span data-stu-id="e4465-231">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="e4465-232">**Destinatari**: digitare in lease un destinatario originale del messaggio oppure fare clic su **Seleziona tutto** per identificare tutti i destinatari.</span><span class="sxs-lookup"><span data-stu-id="e4465-232">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="e4465-233">È inoltre possibile fare clic su **Seleziona tutto** e quindi rimuovere selettivamente i singoli destinatari.</span><span class="sxs-lookup"><span data-stu-id="e4465-233">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="e4465-234">**Motivo dell'invio**: **non deve essere stato bloccato** (impostazione predefinita) o **deve essere stato bloccato**.</span><span class="sxs-lookup"><span data-stu-id="e4465-234">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="e4465-235">Al termine, fare clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="e4465-235">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="e4465-236">Se il messaggio non viene rilasciato o rimosso, verrà eliminato dopo la scadenza del periodo di conservazione in quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="e4465-236">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="e4465-237">Eseguire azioni su più messaggi di posta elettronica in quarantena</span><span class="sxs-lookup"><span data-stu-id="e4465-237">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="e4465-238">Quando si selezionano più messaggi in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **Azioni in blocco** che consente di eseguire le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="e4465-238">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e4465-239">**Rilascia messaggi**: le opzioni sono le stesse del rilascio di un singolo messaggio, ma non è possibile selezionare **Rilascia i messaggi a specifici destinatari**; è possibile selezionare solo **Rilascia il messaggio a tutti i destinatari** o **Rilascia i messaggi ad altre persone**.</span><span class="sxs-lookup"><span data-stu-id="e4465-239">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e4465-240">Si consideri lo scenario seguente: john@gmail.com Invia un messaggio a faith@contoso.com e john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e4465-240">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="e4465-241">Gmail moltiplica questo messaggio in due copie che sono entrambe instradate alla quarantena come phishing in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4465-241">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="e4465-242">Un amministratore rilascia entrambi i messaggi a admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e4465-242">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="e4465-243">Il primo messaggio rilasciato che raggiunge la cassetta postale di amministrazione viene recapitato.</span><span class="sxs-lookup"><span data-stu-id="e4465-243">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="e4465-244">Il secondo messaggio rilasciato viene identificato come recapito duplicato e viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="e4465-244">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="e4465-245">I messaggi vengono identificati come duplicati se dispongono dello stesso ID messaggio e del tempo di ricezione.</span><span class="sxs-lookup"><span data-stu-id="e4465-245">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="e4465-246">**Elimina messaggi**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, i messaggi vengono immediatamente eliminati senza che vengano inviati ai destinatari originali.</span><span class="sxs-lookup"><span data-stu-id="e4465-246">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="e4465-247">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="e4465-247">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="e4465-248">Microsoft Defender solo per Office 365: utilizzare il Centro sicurezza & conformità per gestire i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="e4465-248">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="e4465-249">Le procedure per i file in quarantena in questa sezione sono disponibili solo per i Sottoscrittori Microsoft Defender per Office 365 piano 1 e Plan 2.</span><span class="sxs-lookup"><span data-stu-id="e4465-249">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="e4465-250">Nelle organizzazioni con Defender per Office 365, gli amministratori possono gestire i file in quarantena in SharePoint Online, OneDrive for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="e4465-250">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="e4465-251">Per abilitare la protezione per questi file, vedere [attivare ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e4465-251">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="e4465-252">Visualizzare i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="e4465-252">View quarantined files</span></span>

1. <span data-ttu-id="e4465-253">Nel Centro sicurezza e conformità, passare a **Gestione delle minacce** \> **Rivedi** \> **Quarantena**.</span><span class="sxs-lookup"><span data-stu-id="e4465-253">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e4465-254">Modificare la **visualizzazione in quarantena** nei **file** di valore.</span><span class="sxs-lookup"><span data-stu-id="e4465-254">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="e4465-255">È possibile ordinare su un campo facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="e4465-255">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="e4465-256">È possibile ordinare i risultati facendo clic su un'intestazione di colonna disponibile.</span><span class="sxs-lookup"><span data-stu-id="e4465-256">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e4465-257">Fare clic su **Modifica colonne** per visualizzare un massimo di sette colonne.</span><span class="sxs-lookup"><span data-stu-id="e4465-257">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e4465-258">Le colonne predefinite sono contrassegnate con un asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="e4465-258">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e4465-259">**Utente:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-259">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-260">**Percorso**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-260">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-261">**Nome file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-261">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-262">**URL file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-262">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-263">**Dimensioni file**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-263">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-264">**Scadenza**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-264">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-265">**Rilasciato?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e4465-265">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="e4465-266">**Rilevato da**</span><span class="sxs-lookup"><span data-stu-id="e4465-266">**Detected by**</span></span>
   - <span data-ttu-id="e4465-267">**Modificato dal tempo**</span><span class="sxs-lookup"><span data-stu-id="e4465-267">**Modified by time**</span></span>

4. <span data-ttu-id="e4465-268">Per filtrare i risultati, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="e4465-268">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e4465-269">I filtri disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="e4465-269">The available filters are:</span></span>

   - <span data-ttu-id="e4465-270">**Ora di scadenza**: filtrare i messaggi in base alla scadenza dalla quarantena:</span><span class="sxs-lookup"><span data-stu-id="e4465-270">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="e4465-271">**Oggi**</span><span class="sxs-lookup"><span data-stu-id="e4465-271">**Today**</span></span>
     - <span data-ttu-id="e4465-272">**Prossimi 2 giorni**</span><span class="sxs-lookup"><span data-stu-id="e4465-272">**Next 2 days**</span></span>
     - <span data-ttu-id="e4465-273">**Prossimi 7 giorni**</span><span class="sxs-lookup"><span data-stu-id="e4465-273">**Next 7 days**</span></span>
     - <span data-ttu-id="e4465-274">Un intervallo di data/ora personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e4465-274">A custom date/time range.</span></span>
   - <span data-ttu-id="e4465-275">**Tempo ricevuto**</span><span class="sxs-lookup"><span data-stu-id="e4465-275">**Received time**</span></span>
   - <span data-ttu-id="e4465-276">**Motivo della quarantena**: l'unico valore disponibile è **malware**.</span><span class="sxs-lookup"><span data-stu-id="e4465-276">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="e4465-277">**Tipo di criterio**</span><span class="sxs-lookup"><span data-stu-id="e4465-277">**Policy type**</span></span>

<span data-ttu-id="e4465-278">Dopo aver individuato uno specifico file in quarantena, selezionare il file per visualizzarne i dettagli e per intervenire su di esso (ad esempio, visualizzare, rilasciare, scaricare o eliminare il messaggio).</span><span class="sxs-lookup"><span data-stu-id="e4465-278">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="e4465-279">Visualizzare i dettagli dei file in quarantena</span><span class="sxs-lookup"><span data-stu-id="e4465-279">View quarantined file details</span></span>

<span data-ttu-id="e4465-280">Quando si seleziona un file nell'elenco, nel riquadro a comparsa dei **Dettagli** vengono visualizzati i dettagli dei file seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4465-280">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e4465-281">**FileName**</span><span class="sxs-lookup"><span data-stu-id="e4465-281">**File Name**</span></span>
- <span data-ttu-id="e4465-282">**URL file**: URL che definisce il percorso del file, ad esempio in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e4465-282">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="e4465-283">**Contenuto dannoso rilevato** La data e l'ora in cui il file è stato messo in quarantena.</span><span class="sxs-lookup"><span data-stu-id="e4465-283">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="e4465-284">**Scade**: la data in cui il file verrà eliminato dalla quarantena.</span><span class="sxs-lookup"><span data-stu-id="e4465-284">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="e4465-285">**Rilevato da**: Defender per Office 365 o il motore antimalware di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4465-285">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="e4465-286">**Rilasciato?**</span><span class="sxs-lookup"><span data-stu-id="e4465-286">**Released?**</span></span>
- <span data-ttu-id="e4465-287">**Nome malware**</span><span class="sxs-lookup"><span data-stu-id="e4465-287">**Malware Name**</span></span>
- <span data-ttu-id="e4465-288">**ID documento**: identificatore univoco per il documento.</span><span class="sxs-lookup"><span data-stu-id="e4465-288">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="e4465-289">**Dimensioni file**: in KILOBYTE (KB).</span><span class="sxs-lookup"><span data-stu-id="e4465-289">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="e4465-290">**Organizzazione** ID univoco dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e4465-290">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="e4465-291">**Data ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="e4465-291">**Last modified**</span></span>
- <span data-ttu-id="e4465-292">**Modified by**: l'ultimo utente che ha modificato il file.</span><span class="sxs-lookup"><span data-stu-id="e4465-292">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="e4465-293">**Secure Hash Algorithm 256-bit (SHA-256) valore**: è possibile utilizzare questo valore hash per identificare il file in altri archivi di reputazione o in altre posizioni nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="e4465-293">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="e4465-294">Eseguire un'azione sui file in quarantena</span><span class="sxs-lookup"><span data-stu-id="e4465-294">Take action on quarantined files</span></span>

<span data-ttu-id="e4465-295">Quando si seleziona un file nell'elenco, è possibile eseguire le azioni seguenti nel file nel riquadro a comparsa dei **Dettagli** :</span><span class="sxs-lookup"><span data-stu-id="e4465-295">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e4465-296">**Rilasciare file**: selezionare (impostazione predefinita) o deselezionare **i file di report in Microsoft per l'analisi** e quindi fare clic su **rilascia file**.</span><span class="sxs-lookup"><span data-stu-id="e4465-296">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="e4465-297">**Scaricare il file**</span><span class="sxs-lookup"><span data-stu-id="e4465-297">**Download file**</span></span>
- <span data-ttu-id="e4465-298">**Rimuovi file dalla quarantena**</span><span class="sxs-lookup"><span data-stu-id="e4465-298">**Remove file from quarantine**</span></span>

<span data-ttu-id="e4465-299">Se i file non vengono rilasciati o rimossi, verranno eliminati dopo la scadenza del periodo di conservazione della quarantena predefinito.</span><span class="sxs-lookup"><span data-stu-id="e4465-299">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="e4465-300">Azioni su più file in quarantena</span><span class="sxs-lookup"><span data-stu-id="e4465-300">Actions on multiple quarantined files</span></span>

<span data-ttu-id="e4465-301">Quando si selezionano più file in quarantena nell'elenco (fino a 100), viene visualizzato il riquadro a comparsa **azioni in blocco** in cui è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4465-301">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e4465-302">**Rilasciare i file**</span><span class="sxs-lookup"><span data-stu-id="e4465-302">**Release files**</span></span>
- <span data-ttu-id="e4465-303">**Elimina file**: dopo aver fatto clic su **Sì** nell'avviso che viene visualizzato, i file vengono eliminati immediatamente.</span><span class="sxs-lookup"><span data-stu-id="e4465-303">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="e4465-304">Utilizzare PowerShell di Exchange Online o standalone EOP PowerShell per visualizzare e gestire i messaggi e i file in quarantena</span><span class="sxs-lookup"><span data-stu-id="e4465-304">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="e4465-305">I cmdlet utilizzati per visualizzare e gestire i messaggi e i file in quarantena sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4465-305">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="e4465-306">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e4465-306">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="e4465-307">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e4465-307">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="e4465-308">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e4465-308">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="e4465-309">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): si noti che questo cmdlet è solo per i messaggi, non per i file malware da ATP per SharePoint Online, OneDrive for business o teams.</span><span class="sxs-lookup"><span data-stu-id="e4465-309">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="e4465-310">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e4465-310">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
