---
title: 'Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware'
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: Zero-hour auto Purge (ZAP) è una funzionalità di protezione della posta elettronica che consente di rilevare i messaggi con posta indesiderata o malware che sono già stati recapitati alle cassette postali degli utenti e quindi di eseguire il rendering del contenuto dannoso innocuo. La modalità di utilizzo di ZAP dipende dal tipo di contenuto dannoso rilevato.
ms.openlocfilehash: f43826614def99f8807d8777f128d5bc66f7b46a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084351"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="ded4a-104">Zero-Hour Auto Purge: protezione contro la posta indesiderata e il malware</span><span class="sxs-lookup"><span data-stu-id="ded4a-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="ded4a-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="ded4a-105">Overview</span></span>

<span data-ttu-id="ded4a-106">Zero-hour auto Purge (ZAP) è una funzionalità di protezione della posta elettronica che consente di rilevare messaggi con phishing, posta indesiderata o malware che sono già stati recapitati alle cassette postali degli utenti e quindi viene eseguito il rendering del contenuto dannoso innocuo.</span><span class="sxs-lookup"><span data-stu-id="ded4a-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="ded4a-107">La modalità di utilizzo di ZAP dipende dal tipo di contenuto dannoso rilevato. la posta può essere zapped a causa di contenuto, URL o allegati di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ded4a-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="ded4a-108">ZAP è disponibile con la protezione Exchange Online predefinita inclusa con qualsiasi sottoscrizione di Office 365 che contiene cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ded4a-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="ded4a-109">L'opzione ZAP è attivata per impostazione predefinita, ma devono essere soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ded4a-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="ded4a-110">**Azione di posta** indesiderata è impostata per **spostare il messaggio nella cartella posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="ded4a-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <span data-ttu-id="ded4a-111">È inoltre possibile creare un nuovo criterio di filtro per la posta indesiderata che si applica solo a un gruppo di utenti se non si desidera che tutte le cassette postali vengano schermate da ZAP.</span><span class="sxs-lookup"><span data-stu-id="ded4a-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="ded4a-112">Gli utenti hanno mantenuto le impostazioni predefinite della posta indesiderata e non sono state disattivate la protezione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ded4a-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="ded4a-113">Per informazioni dettagliate sulle opzioni utente in Outlook, vedere [modificare il livello di protezione del filtro della posta indesiderata](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) .</span><span class="sxs-lookup"><span data-stu-id="ded4a-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span>
  
## <a name="how-zap-works"></a><span data-ttu-id="ded4a-114">Funzionamento di ZAP</span><span class="sxs-lookup"><span data-stu-id="ded4a-114">How ZAP works</span></span>

<span data-ttu-id="ded4a-115">Office 365 aggiorna le firme di malware e del motore di protezione da posta indesiderata in tempo reale su base giornaliera.</span><span class="sxs-lookup"><span data-stu-id="ded4a-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="ded4a-116">Tuttavia, gli utenti possono comunque ottenere messaggi dannosi recapitati alle cassette postali per una serie di motivi, incluso se il contenuto è armato dopo essere stato recapitato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="ded4a-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="ded4a-117">ZAP risolve questo monitoraggio continuamente gli aggiornamenti alle firme di posta indesiderata e malware di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ded4a-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="ded4a-118">ZAP è in grado di trovare e rimuovere i messaggi precedentemente recapitati che sono già presenti nelle cassette postali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ded4a-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

<span data-ttu-id="ded4a-119">L'azione ZAP è senza problemi per l'utente della cassetta postale; non vengono notificati se viene spostato un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ded4a-119">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="ded4a-120">Il messaggio non deve superare i 2 giorni.</span><span class="sxs-lookup"><span data-stu-id="ded4a-120">Message must not be older than 2 days.</span></span>
  
<span data-ttu-id="ded4a-121">Gli elenchi consentiti, [le regole del flusso di posta](https://go.microsoft.com/fwlink/p/?LinkId=722755) (note anche come regole di trasporto) e le regole degli utenti finali o i filtri aggiuntivi hanno la precedenza su Zap.</span><span class="sxs-lookup"><span data-stu-id="ded4a-121">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755) (also known as transport rules), and end user rules or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="ded4a-122">Malware ZAP</span><span class="sxs-lookup"><span data-stu-id="ded4a-122">Malware ZAP</span></span>

<span data-ttu-id="ded4a-123">Per il malware appena rilevato, ZAP rimuove gli allegati dai messaggi di posta elettronica, lasciando il corpo del messaggio nella cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ded4a-123">For newly detected malware, ZAP removes attachments from email messages, leaving the body of the message in the user's mailbox.</span></span> <span data-ttu-id="ded4a-124">Gli allegati vengono rimossi indipendentemente dallo stato di lettura della posta.</span><span class="sxs-lookup"><span data-stu-id="ded4a-124">Attachments are removed regardless of the read status of the mail.</span></span>

<span data-ttu-id="ded4a-125">Il malware ZAP è abilitato per impostazione predefinita nel criterio di malware.</span><span class="sxs-lookup"><span data-stu-id="ded4a-125">Malware ZAP is enabled by default in the Malware Policy.</span></span> <span data-ttu-id="ded4a-126">È possibile disabilitare lo ZAP antimalware utilizzando il parametro *ZapEnabled* nel cmdlet [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) in PowerShell di Exchange Online o Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ded4a-126">You can disable Malware ZAP by using the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="phish-zap"></a><span data-ttu-id="ded4a-127">Phishing ZAP</span><span class="sxs-lookup"><span data-stu-id="ded4a-127">Phish ZAP</span></span>

<span data-ttu-id="ded4a-128">Per la posta identificata come phishing dopo il recapito, ZAP esegue un'azione in base ai criteri di posta indesiderata che l'utente deve coprire.</span><span class="sxs-lookup"><span data-stu-id="ded4a-128">For mail that is identified as phish after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="ded4a-129">Se l'azione phishing del criterio è impostata per eseguire un'azione su un messaggio di posta elettronica (redirect, DELETE, Quarantine, Move to Junk), ZAP sposterà il messaggio nella cartella posta indesiderata della posta in arrivo dell'utente, indipendentemente dallo stato di lettura della posta.</span><span class="sxs-lookup"><span data-stu-id="ded4a-129">If the policy Phish action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, regardless of the read status of the mail.</span></span> <span data-ttu-id="ded4a-130">Se l'azione phishing del criterio non è impostata su azione (aggiungere X-header, Modify Subject, No Action), ZAP non eseguirà alcuna azione per la posta.</span><span class="sxs-lookup"><span data-stu-id="ded4a-130">If the policy Phish action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="ded4a-131">Per ulteriori informazioni su come [configurare i criteri di filtro posta indesiderata](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) , vedere qui.</span><span class="sxs-lookup"><span data-stu-id="ded4a-131">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="ded4a-132">Phishing ZAP è abilitato per impostazione predefinita nei criteri di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ded4a-132">Phish ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="ded4a-133">È possibile disabilitare phishing ZAP utilizzando il parametro *ZapEnabled* nel cmdlet [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) in PowerShell di Exchange Online o Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ded4a-133">You can disable Phish ZAP by using the *ZapEnabled* parameter on the [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="spam-zap"></a><span data-ttu-id="ded4a-134">Spam ZAP</span><span class="sxs-lookup"><span data-stu-id="ded4a-134">Spam ZAP</span></span>

<span data-ttu-id="ded4a-135">Per la posta elettronica identificata come posta indesiderata dopo il recapito, ZAP esegue un'azione in base ai criteri di posta indesiderata che l'utente deve coprire.</span><span class="sxs-lookup"><span data-stu-id="ded4a-135">For mail that is identified as spam after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="ded4a-136">Se l'azione dei criteri di posta indesiderata è impostata per eseguire un'azione su una posta (redirect, DELETE, Quarantine, Move to Junk), ZAP sposterà il messaggio nella cartella posta indesiderata della posta in arrivo dell'utente, se il messaggio non è stato letto.</span><span class="sxs-lookup"><span data-stu-id="ded4a-136">If the policy Spam action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, if the message is unread.</span></span> <span data-ttu-id="ded4a-137">Se l'azione dei criteri di posta indesiderata non è impostata su azione (Aggiungi X-header, modifica oggetto, nessuna azione), ZAP non interverrà sulla posta.</span><span class="sxs-lookup"><span data-stu-id="ded4a-137">If the policy Spam action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="ded4a-138">Per ulteriori informazioni su come [configurare i criteri di filtro posta indesiderata](configure-your-spam-filter-policies.md) , vedere qui.</span><span class="sxs-lookup"><span data-stu-id="ded4a-138">Learn more about how to [Configure your spam filter policies](configure-your-spam-filter-policies.md) here.</span></span>

<span data-ttu-id="ded4a-139">Spam ZAP è abilitato per impostazione predefinita nei criteri di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ded4a-139">Spam ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="ded4a-140">È possibile disabilitare la posta indesiderata utilizzando il parametro *ZapEnabled* del cmdlet [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) in PowerShell di Exchange Online o Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ded4a-140">You can disable Spam ZAP by using the *ZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="ded4a-141">Il parametro *ZapEnabled* del cmdlet **Set-HostedContentFilterPolicy** disattiva o attiva sia phishing zap che spam zap per il criterio.</span><span class="sxs-lookup"><span data-stu-id="ded4a-141">The *ZapEnabled* parameter on the **Set-HostedContentFilterPolicy** cmdlet disables or enables both Phish ZAP and Spam ZAP for the policy.</span></span> <span data-ttu-id="ded4a-142">Non è possibile abilitare o disabilitare in modo indipendente phishing ZAP e spam ZAP all'interno dello stesso criterio.</span><span class="sxs-lookup"><span data-stu-id="ded4a-142">You can't independently enable or disable Phish ZAP and Spam ZAP within the same policy.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="ded4a-143">Come vedere se ZAP ha spostato il messaggio</span><span class="sxs-lookup"><span data-stu-id="ded4a-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="ded4a-144">Per determinare se il messaggio è stato spostato da ZAP, è possibile utilizzare il [rapporto sullo stato di protezione di minacce](../../compliance/view-email-security-reports.md#threat-protection-status-report) o l' [esploratore di minacce (e i rilevamenti in tempo reale)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="ded4a-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](../../compliance/view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span>

## <a name="disable-zap"></a><span data-ttu-id="ded4a-145">Disabilitare ZAP</span><span class="sxs-lookup"><span data-stu-id="ded4a-145">Disable ZAP</span></span>

<span data-ttu-id="ded4a-146">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="ded4a-146">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span> <span data-ttu-id="ded4a-147">Per connettersi a PowerShell di Exchange Online Protection, vedere [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span><span class="sxs-lookup"><span data-stu-id="ded4a-147">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span>

### <a name="disable-malware-zap"></a><span data-ttu-id="ded4a-148">Disabilitare il malware ZAP \* \*</span><span class="sxs-lookup"><span data-stu-id="ded4a-148">Disable Malware ZAP\*\*</span></span>

<span data-ttu-id="ded4a-149">In questo esempio viene disabilitato ZAP nel criterio di filtro antimalware denominato "test".</span><span class="sxs-lookup"><span data-stu-id="ded4a-149">This example disables ZAP in the malware filter policy named "Test".</span></span>

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="ded4a-150">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ded4a-150">For detailed syntax and parameter information, see [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span></span>

### <a name="disable-phish-zap-and-spam-zap"></a><span data-ttu-id="ded4a-151">Disabilitare phishing ZAP e spam ZAP</span><span class="sxs-lookup"><span data-stu-id="ded4a-151">Disable Phish ZAP and Spam ZAP</span></span>

<span data-ttu-id="ded4a-152">In questo esempio viene disabilitato phishing ZAP e spam ZAP nel criterio di filtro dei contenuti denominato "test".</span><span class="sxs-lookup"><span data-stu-id="ded4a-152">This example disables Phish ZAP and Spam ZAP in the content filter policy named "Test".</span></span>

```Powershell
Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="ded4a-153">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span><span class="sxs-lookup"><span data-stu-id="ded4a-153">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span></span>

## <a name="faq"></a><span data-ttu-id="ded4a-154">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="ded4a-154">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="ded4a-155">Cosa succede se un messaggio legittimo viene spostato nella cartella posta indesiderata?</span><span class="sxs-lookup"><span data-stu-id="ded4a-155">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="ded4a-156">È consigliabile seguire la procedura di creazione di report normale per i [falsi positivi](../../compliance/prevent-email-from-being-marked-as-spam.md).</span><span class="sxs-lookup"><span data-stu-id="ded4a-156">You should follow the normal reporting process for [false-positives](../../compliance/prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="ded4a-157">L'unico motivo per il quale il messaggio verrebbe spostato dalla posta in arrivo alla cartella posta indesiderata sarebbe perché il servizio ha determinato che il messaggio era posta indesiderata o dannoso.</span><span class="sxs-lookup"><span data-stu-id="ded4a-157">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="ded4a-158">Che cosa fare se si utilizza la quarantena di Office 365 anziché la cartella posta indesiderata?</span><span class="sxs-lookup"><span data-stu-id="ded4a-158">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="ded4a-159">ZAP non sposta i messaggi in quarantena dalla posta in arrivo in questo momento.</span><span class="sxs-lookup"><span data-stu-id="ded4a-159">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="ded4a-160">Cosa succede se si dispone di una regola del flusso di posta personalizzata (blocco/Consenti regola)?</span><span class="sxs-lookup"><span data-stu-id="ded4a-160">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="ded4a-161">Le regole create dagli amministratori (regole del flusso di posta) o blocca e Consenti hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="ded4a-161">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="ded4a-162">Tali messaggi sono esclusi dai criteri di funzionalità in modo che il flusso di posta seguirà l'azione della regola (blocco/Consenti regola).</span><span class="sxs-lookup"><span data-stu-id="ded4a-162">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="ded4a-163">Cosa succede se un messaggio viene spostato in un'altra cartella (ad esempio, la regola di posta in arrivo)?</span><span class="sxs-lookup"><span data-stu-id="ded4a-163">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>

<span data-ttu-id="ded4a-164">ZAP continua a funzionare in questo caso, a meno che il messaggio non sia stato eliminato o sia indesiderato.</span><span class="sxs-lookup"><span data-stu-id="ded4a-164">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ded4a-165">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ded4a-165">Related Topics</span></span>

[<span data-ttu-id="ded4a-166">Protezione dalla posta indesiderata in Office 365</span><span class="sxs-lookup"><span data-stu-id="ded4a-166">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="ded4a-167">Bloccare la posta indesiderata utilizzando il filtro di Office 365 al fine di evitare problemi di falsi negativi</span><span class="sxs-lookup"><span data-stu-id="ded4a-167">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
