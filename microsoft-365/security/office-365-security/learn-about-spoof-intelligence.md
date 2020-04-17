---
title: Configurare l'intelligence spoof
f1.keywords:
- NOCSH
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
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come configurare i mittenti falsificati per consentire o meno l'autorizzazione e altre impostazioni di intelligence spoof in Exchange Online e Exchange Online Protection (EOP).
ms.openlocfilehash: 96a1442c893444108aaf6814484bc4e4d55aa731
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528738"
---
# <a name="configure-spoof-intelligence-in-office-365"></a><span data-ttu-id="b5463-103">Configurare l'intelligence di spoofing in Office 365</span><span class="sxs-lookup"><span data-stu-id="b5463-103">Configure spoof intelligence in Office 365</span></span>

<span data-ttu-id="b5463-104">Se si è un cliente di Office 365 con cassette postali in Exchange Online o un cliente di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, i messaggi di posta elettronica in ingresso vengono automaticamente protetti dallo spoofing da EOP a ottobre 2018.</span><span class="sxs-lookup"><span data-stu-id="b5463-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="b5463-105">EOP utilizza l'intelligence spoof come parte della difesa complessiva dell'organizzazione dal phishing.</span><span class="sxs-lookup"><span data-stu-id="b5463-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="b5463-106">Per ulteriori informazioni, vedere [protezione anti-spoofing in Office 365](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="b5463-106">For more information, see [Anti-spoofing protection in Office 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="b5463-107">Quando un mittente falsifica un indirizzo di posta elettronica, sembra essere un utente in uno dei domini dell'organizzazione o un utente in un dominio esterno che invia messaggi di posta elettronica all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5463-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="b5463-108">I pirati informatici che falsificano i mittenti per inviare posta indesiderata o phishing devono essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="b5463-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="b5463-109">Tuttavia, esistono scenari in cui i mittenti legittimi eseguono lo spoofing.</span><span class="sxs-lookup"><span data-stu-id="b5463-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="b5463-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b5463-110">For example:</span></span>

- <span data-ttu-id="b5463-111">Scenari legittimi per lo spoofing dei domini interni:</span><span class="sxs-lookup"><span data-stu-id="b5463-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="b5463-112">I mittenti di terze parti utilizzano il dominio per inviare messaggi di posta elettronica in blocco ai propri dipendenti per i sondaggi dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="b5463-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>

  - <span data-ttu-id="b5463-113">Una società esterna genera e invia gli aggiornamenti pubblicitari o di prodotto per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b5463-113">An external company generates and sends advertising or product updates on your behalf.</span></span>

  - <span data-ttu-id="b5463-114">Un assistente deve regolarmente inviare messaggi di posta elettronica per un'altra persona all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5463-114">An assistant regularly needs to send email for another person within your organization.</span></span>

  - <span data-ttu-id="b5463-115">Un'applicazione interna Invia notifiche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b5463-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="b5463-116">Scenari legittimi per lo spoofing dei domini esterni:</span><span class="sxs-lookup"><span data-stu-id="b5463-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="b5463-117">Il mittente è presente in una mailing list (noto anche come elenco di discussione) e la mailing list inoltra la posta elettronica dal mittente originale a tutti i partecipanti nella mailing list.</span><span class="sxs-lookup"><span data-stu-id="b5463-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>

  - <span data-ttu-id="b5463-118">Una società esterna invia messaggi di posta elettronica per conto di un'altra società (ad esempio, un report automatizzato o un'azienda software-as-a-Service).</span><span class="sxs-lookup"><span data-stu-id="b5463-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="b5463-119">L'intelligenza contraffatta e, in particolare, il criterio di intelligence spoof predefinito (e solo), aiuta a garantire che la posta elettronica contraffatta inviata da mittenti legittimi non venga interferita nei filtri di posta indesiderata nei sistemi di posta elettronica di Office 365 o esterni, proteggendo gli utenti da attacchi di posta indesiderata o di phishing</span><span class="sxs-lookup"><span data-stu-id="b5463-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in spam filters in Office 365 or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="b5463-120">È possibile gestire l'intelligence spoof nel centro sicurezza & conformità di Office 365 o in PowerShell (Exchange Online PowerShell per i clienti di Office 365; PowerShell di Exchange Online Protection per clienti EOP autonomi.</span><span class="sxs-lookup"><span data-stu-id="b5463-120">You can manage spoof intelligence in the Office 365 Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b5463-121">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b5463-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b5463-122">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b5463-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b5463-123">Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata**, usare <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="b5463-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="b5463-124">Per passare direttamente alla pagina **anti-phishing** , utilizzare <https://protection.office.com/antiphishing>.</span><span class="sxs-lookup"><span data-stu-id="b5463-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="b5463-125">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b5463-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b5463-126">Per connettersi a PowerShell per Exchange Online Protection autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b5463-126">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b5463-127">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="b5463-127">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="b5463-128">Per modificare il criterio di intelligence di spoofing o abilitare o disabilitare l'intelligence di spoofing, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="b5463-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="b5463-129">Per l'accesso in sola lettura ai criteri di intelligence spoof, è necessario essere membri del gruppo di ruoli **lettore di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="b5463-129">For read-only access to the spoof intelligence policy, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="b5463-130">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità di Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b5463-130">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="b5463-131">Per le impostazioni consigliate per l'intelligence spoof, [EOP impostazioni dei criteri anti-phishing predefinite](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="b5463-131">For our recommended settings for spoof intelligence, [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="b5463-132">Utilizzare il Centro sicurezza & conformità per gestire i mittenti falsificati</span><span class="sxs-lookup"><span data-stu-id="b5463-132">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="b5463-133">Se si dispone di un abbonamento a Office 365 Enterprise E5 o di un componente aggiuntivo acquistato e Advanced Threat Protection (ATP), è possibile gestire anche i mittenti che eseguono lo spoofing del dominio tramite l' [Insight di intelligence di spoofing](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="b5463-133">If you have an Office 365 Enterprise E5 subscription or have separately purchased and Advanced Threat Protection (ATP) add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="b5463-134">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="b5463-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="b5463-135">Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic ![su Espandi icona](../../media/scc-expand-icon.png) per espandere il criterio di **Intelligence spoof**.</span><span class="sxs-lookup"><span data-stu-id="b5463-135">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Selezionare il criterio di intelligence spoof](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="b5463-137">Eseguire una delle selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5463-137">Make one of the following selections:</span></span>

   - <span data-ttu-id="b5463-138">**Esaminare i nuovi mittenti**</span><span class="sxs-lookup"><span data-stu-id="b5463-138">**Review new senders**</span></span>
   - <span data-ttu-id="b5463-139">**Visualizza I mittenti già recensiti**</span><span class="sxs-lookup"><span data-stu-id="b5463-139">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="b5463-140">Nel **decidere se questi mittenti sono autorizzati a falsificare il riquadro a comparsa degli utenti** visualizzato, selezionare una delle seguenti schede:</span><span class="sxs-lookup"><span data-stu-id="b5463-140">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="b5463-141">**Domini: i**mittenti che eseguono lo spoofing degli utenti nei domini interni.</span><span class="sxs-lookup"><span data-stu-id="b5463-141">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="b5463-142">**Domini esterni**: mittenti che eseguono lo spoofing degli utenti nei domini esterni.</span><span class="sxs-lookup"><span data-stu-id="b5463-142">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="b5463-143">Fare ![clic su](../../media/scc-expand-icon.png) Espandi icona nella colonna **consentito di falsificazione?** .</span><span class="sxs-lookup"><span data-stu-id="b5463-143">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="b5463-144">Scegliere **Sì** per consentire il mittente contraffatto oppure scegliere **No** per contrassegnare il messaggio come falsificato.</span><span class="sxs-lookup"><span data-stu-id="b5463-144">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="b5463-145">L'azione è controllata dal criterio anti-phishing predefinito o dai criteri di anti-phishing ATP personalizzati (il valore predefinito è **Move Message to junk email Folder**).</span><span class="sxs-lookup"><span data-stu-id="b5463-145">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="b5463-146">Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="b5463-146">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Schermata che mostra il riquadro a comparsa di mittenti contraffatti e se il mittente è autorizzato a eseguire la falsificazione](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="b5463-148">Le colonne e i valori visualizzati sono illustrati nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="b5463-148">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="b5463-149">**Utente contraffatto**: l'account utente contraffatto.</span><span class="sxs-lookup"><span data-stu-id="b5463-149">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="b5463-150">Si tratta del mittente del messaggio nell'indirizzo from (noto anche come `5322.From` indirizzo) visualizzato nei client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b5463-150">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="b5463-151">La validità di questo indirizzo non è controllata da SPF.</span><span class="sxs-lookup"><span data-stu-id="b5463-151">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="b5463-152">Nella scheda **domini** , il valore contiene un singolo indirizzo di posta elettronica o se il server di posta elettronica di origine falsifica più account utente, ne contiene **più di uno**.</span><span class="sxs-lookup"><span data-stu-id="b5463-152">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="b5463-153">Nella scheda **domini esterni** , il valore contiene il dominio dell'utente contraffatto, non l'indirizzo di posta elettronica completo.</span><span class="sxs-lookup"><span data-stu-id="b5463-153">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="b5463-154">**Infrastruttura di invio**: il dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine o l'indirizzo IP se l'origine non ha un record PTR.</span><span class="sxs-lookup"><span data-stu-id="b5463-154">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="b5463-155">Per ulteriori informazioni sulle origini dei messaggi e sui mittenti di messaggi, vedere [una panoramica degli standard per i messaggi di posta elettronica](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span><span class="sxs-lookup"><span data-stu-id="b5463-155">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="b5463-156">**# dei messaggi**: il numero di messaggi dall'infrastruttura di invio all'organizzazione che contengono il mittente o i mittenti falsificati specificati negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="b5463-156">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="b5463-157">**# dei reclami degli**utenti: denunce presentate dagli utenti nei confronti del mittente negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="b5463-157">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="b5463-158">I reclami sono di solito sotto forma di invii di posta indesiderata a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5463-158">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="b5463-159">**Risultato dell'autenticazione**: uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b5463-159">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="b5463-160">**Superato**: il mittente ha superato i controlli di autenticazione della posta elettronica del mittente (SPF o DKIM).</span><span class="sxs-lookup"><span data-stu-id="b5463-160">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="b5463-161">**Errore**: il mittente ha superato i controlli di autenticazione del mittente EOP.</span><span class="sxs-lookup"><span data-stu-id="b5463-161">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="b5463-162">**Unknown**: il risultato di questi controlli non è noto.</span><span class="sxs-lookup"><span data-stu-id="b5463-162">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="b5463-163">**Decision set by**: indica chi ha determinato se l'infrastruttura di invio è consentita per la falsificazione dell'utente:</span><span class="sxs-lookup"><span data-stu-id="b5463-163">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="b5463-164">**Criteri di intelligence spoof** (automatici)</span><span class="sxs-lookup"><span data-stu-id="b5463-164">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="b5463-165">**Amministratore** (manuale)</span><span class="sxs-lookup"><span data-stu-id="b5463-165">**Admin** (manual)</span></span>

   - <span data-ttu-id="b5463-166">**Ultimo**aggiornamento: l'ultima data in cui un messaggio è stato ricevuto dall'infrastruttura di invio che contiene l'utente falsificato.</span><span class="sxs-lookup"><span data-stu-id="b5463-166">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="b5463-167">**Consentita la falsificazione?**: i valori visualizzati qui sono:</span><span class="sxs-lookup"><span data-stu-id="b5463-167">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="b5463-168">**Yes**: i messaggi provenienti dalla combinazione di utenti falsificati e dell'infrastruttura di invio sono consentiti e non vengono considerati come posta elettronica contraffatta.</span><span class="sxs-lookup"><span data-stu-id="b5463-168">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="b5463-169">**No**: i messaggi provenienti dalla combinazione di utenti falsificati e dell'infrastruttura di invio sono contrassegnati come falsificati.</span><span class="sxs-lookup"><span data-stu-id="b5463-169">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="b5463-170">L'azione è controllata dal criterio anti-phishing predefinito o dai criteri di anti-phishing ATP personalizzati (il valore predefinito è **Move Message to junk email Folder**).</span><span class="sxs-lookup"><span data-stu-id="b5463-170">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="b5463-171">Per ulteriori informazioni, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="b5463-171">See the next section for more information.</span></span>

     - <span data-ttu-id="b5463-172">**Alcuni utenti** (solo**la scheda domini** ): un'infrastruttura di invio è spoofing di più utenti, in cui alcuni utenti falsificati sono consentiti e altri no.</span><span class="sxs-lookup"><span data-stu-id="b5463-172">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="b5463-173">Utilizzare la scheda **Dettagli** per visualizzare gli indirizzi specifici.</span><span class="sxs-lookup"><span data-stu-id="b5463-173">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="b5463-174">Nella parte inferiore della pagina fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b5463-174">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="b5463-175">Utilizzo di PowerShell per gestire i mittenti falsificati</span><span class="sxs-lookup"><span data-stu-id="b5463-175">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="b5463-176">Per visualizzare i mittenti consentiti e bloccati in Intelligence spoof, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b5463-176">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="b5463-177">In questo esempio vengono restituite informazioni dettagliate su tutti i mittenti autorizzati a eseguire la falsificazione degli utenti nei domini.</span><span class="sxs-lookup"><span data-stu-id="b5463-177">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilter -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="b5463-178">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b5463-178">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy).</span></span>

<span data-ttu-id="b5463-179">Per configurare i mittenti consentiti e bloccati in Intelligence contraffatta, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="b5463-179">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="b5463-180">Acquisire l'elenco corrente dei mittenti falsificati rilevati scrivendo l'output del cmdlet **Get-PhishFilterPolicy** in un file CSV:</span><span class="sxs-lookup"><span data-stu-id="b5463-180">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="b5463-181">Modificare il file CSV per aggiungere o modificare i valori di **SpoofedUser** (indirizzo di posta elettronica) e **AllowedToSpoof** (Sì o no).</span><span class="sxs-lookup"><span data-stu-id="b5463-181">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="b5463-182">Salvare il file, leggere il file e archiviarlo come variabile denominato `$UpdateSpoofedSenders`:</span><span class="sxs-lookup"><span data-stu-id="b5463-182">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="b5463-183">Utilizzare la `$UpdateSpoofedSenders` variabile per configurare il criterio di intelligence di spoofing:</span><span class="sxs-lookup"><span data-stu-id="b5463-183">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="b5463-184">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="b5463-184">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="b5463-185">Utilizzare il Centro sicurezza & Compliance per configurare l'intelligence spoof</span><span class="sxs-lookup"><span data-stu-id="b5463-185">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="b5463-186">Le opzioni di configurazione per l'intelligence spoof sono descritte in [Impostazioni spoof nei criteri di anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="b5463-186">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="b5463-187">Le opzioni disponibili dipendono dall'abbonamento:</span><span class="sxs-lookup"><span data-stu-id="b5463-187">Your available options depend on your subscription:</span></span>

- <span data-ttu-id="b5463-188">Le organizzazioni di EOP autonome senza cassette postali di Exchange Online non possono configurare le impostazioni di intelligence spoof</span><span class="sxs-lookup"><span data-stu-id="b5463-188">Standalone EOP organizations without Exchange Online mailboxes can't configure spoof intelligence settings.</span></span>

- <span data-ttu-id="b5463-189">Le organizzazioni di Office 365 con cassette postali di Exchange Online sono in grado di configurare le impostazioni di intelligence spoof nei criteri di anti-phishing predefiniti.</span><span class="sxs-lookup"><span data-stu-id="b5463-189">Office 365 organizations with Exchange Online mailboxes can configure spoof intelligence settings in the default (and only) anti-phishing policy.</span></span> <span data-ttu-id="b5463-190">Per istruzioni, vedere [Configure the default anti-phishing Policy in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b5463-190">For instructions, see [Configure the default anti-phishing policy in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="b5463-191">Le organizzazioni di Office 365 con ATP possono configurare le impostazioni di intelligence spoof nei criteri di anti-phishing predefiniti e anche nei criteri di anti-phishing personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b5463-191">Office 365 organizations with ATP can configure spoof intelligence settings in the default ATP anti-phishing policy, and also in custom ATP anti-phishing policies.</span></span> <span data-ttu-id="b5463-192">Per istruzioni, vedere [configurare i criteri di anti-phishing ATP in Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b5463-192">For instructions, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b5463-193">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="b5463-193">How do you know these procedures worked?</span></span>

<span data-ttu-id="b5463-194">Per verificare di aver configurato l'intelligence spoof con i mittenti autorizzati e non autorizzati allo spoofing e di aver configurato le impostazioni di intelligence di spoofing, utilizzare una delle seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="b5463-194">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="b5463-195">Nel centro sicurezza & conformità, accedere a **criteri** \> di **gestione** \> delle minacce protezione da **posta indesiderata** \> Espandi **criteri** \> di intelligence spoof selezionare **Mostra me mittenti già Recensito** \> selezionare la scheda **domini** o **domini esterni** e verificare il valore **consentito per la falsificazione** del mittente.</span><span class="sxs-lookup"><span data-stu-id="b5463-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="b5463-196">In PowerShell, eseguire i seguenti comandi per visualizzare i mittenti consentiti e non consentiti per la falsificazione:</span><span class="sxs-lookup"><span data-stu-id="b5463-196">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilter -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="b5463-197">In PowerShell, eseguire il comando riportato di seguito per esportare l'elenco di tutti i mittenti falsificati in un file CSV:</span><span class="sxs-lookup"><span data-stu-id="b5463-197">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="b5463-198">Nelle organizzazioni di Office 365 con le cassette postali di Exchange Online, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5463-198">In Office 365 organizations with Exchange Online mailboxes, do either of the following steps:</span></span>

  - <span data-ttu-id="b5463-199">Nel centro sicurezza & conformità, accedere **a criterio di** \> **gestione** \> delle minacce **anti-phishing** \> fare clic su **criteri predefiniti** e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="b5463-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

  - <span data-ttu-id="b5463-200">In PowerShell di Exchange Online, eseguire il comando riportato di seguito e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b5463-200">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

    ```PowerShell
    Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
    ```

- <span data-ttu-id="b5463-201">Nelle organizzazioni ATP di Office 365 eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5463-201">In Office 365 ATP organizations, do either of the following steps:</span></span>

  - <span data-ttu-id="b5463-202">Nel centro sicurezza & conformità, accedere a **criteri** \> di **gestione** \> delle minacce **ATP anti-phishing** ed eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5463-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** and do either of the following steps:</span></span>

    - <span data-ttu-id="b5463-203">Selezionare un criterio dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="b5463-203">Select a policy from the list.</span></span> <span data-ttu-id="b5463-204">Nel riquadro a comparsa visualizzato, verificare i valori nella sezione **spoofing** .</span><span class="sxs-lookup"><span data-stu-id="b5463-204">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
    - <span data-ttu-id="b5463-205">Fare clic su **criteri predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="b5463-205">Click **Default policy**.</span></span> <span data-ttu-id="b5463-206">Nel riquadro a comparsa visualizzato, verificare i valori nella sezione **spoofing** .</span><span class="sxs-lookup"><span data-stu-id="b5463-206">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

  - <span data-ttu-id="b5463-207">In Exchange Online PowerShell, sostituire \<Name\> con Office365 antiphishing default o il nome di un criterio di anti-phishing ATP personalizzato ed eseguire il comando seguente e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b5463-207">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom ATP anti-phishing policy, and run the following command and verify the settings:</span></span>

    ```PowerShell
    Get-AntiPhishPolicy -Identity "<Name>"
    ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="b5463-208">Altre modalità di gestione dello spoofing e del phishing</span><span class="sxs-lookup"><span data-stu-id="b5463-208">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="b5463-209">Essere diligenti sullo spoofing e la protezione da phishing.</span><span class="sxs-lookup"><span data-stu-id="b5463-209">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="b5463-210">Di seguito sono riportati alcuni modi per verificare se i mittenti eseguono lo spoofing del dominio e impediscono loro di danneggiare l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="b5463-210">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="b5463-211">Controllare il **report di posta contraffatta**.</span><span class="sxs-lookup"><span data-stu-id="b5463-211">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="b5463-212">È possibile utilizzare questo rapporto spesso per visualizzare e facilitare la gestione dei mittenti falsificati.</span><span class="sxs-lookup"><span data-stu-id="b5463-212">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="b5463-213">Per informazioni, vedere [spoofing detections report](view-email-security-reports.md#spoof-detections-report).</span><span class="sxs-lookup"><span data-stu-id="b5463-213">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="b5463-214">Esaminare la configurazione di Sender Policy Framework (SPF).</span><span class="sxs-lookup"><span data-stu-id="b5463-214">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="b5463-215">Per una rapida introduzione a SPF e per le istruzioni di configurazione, vedere [Configurare SPF in Office 365 per prevenire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="b5463-215">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="b5463-216">Per informazioni più dettagliate su come Office 365 utilizza SPF oppure per risolvere i problemi o per eseguire distribuzioni non standard (ad esempio, le distribuzioni ibride), iniziare da [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="b5463-216">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="b5463-217">Esaminare la configurazione della posta DomainKeys (DKIM) identificata.</span><span class="sxs-lookup"><span data-stu-id="b5463-217">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="b5463-218">È consigliabile utilizzare DKIM oltre a SPF e DMARC per impedire agli aggressori di inviare messaggi che sembrano provenienti dal proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="b5463-218">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="b5463-219">DKIM consente di aggiungere una firma digitale ai messaggi di posta elettronica nell'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b5463-219">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="b5463-220">Per ulteriori informazioni, vedere [utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="b5463-220">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="b5463-221">Esaminare la configurazione dell'autenticazione dei messaggi basata sul dominio, della creazione di report e della conformità (DMARC).</span><span class="sxs-lookup"><span data-stu-id="b5463-221">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="b5463-222">L'implementazione di DMARC con SPF e DKIM fornisce un'ulteriore protezione dallo spoofing e dal phishing.</span><span class="sxs-lookup"><span data-stu-id="b5463-222">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="b5463-223">DMARC consente ai sistemi di posta di ricezione di determinare cosa fare con i messaggi inviati dal dominio che non supera i controlli SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="b5463-223">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="b5463-224">Per informazioni, vedere [utilizzare DMARC per convalidare la posta elettronica in Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="b5463-224">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
