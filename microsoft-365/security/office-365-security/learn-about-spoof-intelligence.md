---
title: Configurare spoof intelligence
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni sulla spoof intelligence in Exchange Online Protection (EOP), dove è possibile consentire o bloccare specifici mittenti falsificati.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 482978e93325344d897fcf907b026743fc393d47
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406641"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="16b44-103">Configurare spoof intelligence in EOP</span><span class="sxs-lookup"><span data-stu-id="16b44-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="16b44-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="16b44-104">**Applies to**</span></span>
- [<span data-ttu-id="16b44-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="16b44-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="16b44-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="16b44-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="16b44-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16b44-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="16b44-108">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, i messaggi di posta elettronica in ingresso vengono automaticamente protetti dallo spoofing da EOP a partire da ottobre 2018.</span><span class="sxs-lookup"><span data-stu-id="16b44-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="16b44-109">EOP utilizza spoof intelligence come parte della difesa generale dell'organizzazione contro il phishing.</span><span class="sxs-lookup"><span data-stu-id="16b44-109">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="16b44-110">Per ulteriori informazioni, vedere [Protezione anti-spoofing in EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="16b44-110">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="16b44-111">Quando un mittente effettua lo spoofing di un indirizzo di posta elettronica, sembra essere un utente in uno dei domini dell'organizzazione o un utente in un dominio esterno che invia posta elettronica all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="16b44-111">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="16b44-112">Gli utenti malintenzionati che effettuano lo spoofing dei mittenti per inviare posta indesiderata o phishing devono essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="16b44-112">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="16b44-113">Esistono tuttavia scenari in cui i mittenti legittimi effettuano lo spoofing.</span><span class="sxs-lookup"><span data-stu-id="16b44-113">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="16b44-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="16b44-114">For example:</span></span>

- <span data-ttu-id="16b44-115">Scenari legittimi per lo spoofing dei domini interni:</span><span class="sxs-lookup"><span data-stu-id="16b44-115">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="16b44-116">I mittenti di terze parti usano il dominio per inviare posta inviata in blocco ai dipendenti per sondaggi aziendali.</span><span class="sxs-lookup"><span data-stu-id="16b44-116">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="16b44-117">Una società esterna genera e invia annunci o aggiornamenti dei prodotti per tuo conto.</span><span class="sxs-lookup"><span data-stu-id="16b44-117">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="16b44-118">Un assistente deve inviare regolarmente messaggi di posta elettronica a un'altra persona all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="16b44-118">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="16b44-119">Un'applicazione interna invia notifiche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="16b44-119">An internal application sends email notifications.</span></span>

- <span data-ttu-id="16b44-120">Scenari legittimi per lo spoofing di domini esterni:</span><span class="sxs-lookup"><span data-stu-id="16b44-120">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="16b44-121">Il mittente si trova in una lista di distribuzione (nota anche come elenco di discussione) e la lista di distribuzione inoltra la posta elettronica dal mittente originale a tutti i partecipanti della lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="16b44-121">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="16b44-122">Una società esterna invia messaggi di posta elettronica per conto di un'altra società (ad esempio, un report automatizzato o una società software-as-a-service).</span><span class="sxs-lookup"><span data-stu-id="16b44-122">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="16b44-123">Spoof intelligence, e in particolare il criterio di spoof intelligence predefinito (e solo), aiuta a garantire che i messaggi di posta elettronica falsificati inviati da mittenti legittimi non siano coinvolti nei filtri di posta indesiderata di EOP o nei sistemi di posta elettronica esterni, proteggendo gli utenti da attacchi di posta indesiderata o phishing.</span><span class="sxs-lookup"><span data-stu-id="16b44-123">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="16b44-124">È possibile gestire lo spoof intelligence nel Centro sicurezza & e conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="16b44-124">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="16b44-125">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="16b44-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="16b44-126">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="16b44-126">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="16b44-127">Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata**, usare <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="16b44-127">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="16b44-128">Per passare direttamente alla pagina **anti-phishing,** utilizzare <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="16b44-128">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="16b44-129">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="16b44-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="16b44-130">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="16b44-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="16b44-131">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in **Exchange Online:**</span><span class="sxs-lookup"><span data-stu-id="16b44-131">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="16b44-132">Per modificare i criteri di spoof intelligence o abilitare o disabilitare spoof intelligence, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o **Amministratore** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="16b44-132">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="16b44-133">Per l'accesso in sola lettura ai criteri di spoof intelligence, è necessario essere membri dei gruppi di ruoli **Lettore** globale o Lettore **di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="16b44-133">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="16b44-134">Per ulteriori informazioni, vedere [Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="16b44-134">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="16b44-135">**Note**:</span><span class="sxs-lookup"><span data-stu-id="16b44-135">**Notes**:</span></span>

  - <span data-ttu-id="16b44-136">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 offre agli utenti le autorizzazioni e le autorizzazioni necessarie per altre funzionalità di Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="16b44-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="16b44-137">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="16b44-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="16b44-138">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="16b44-138">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="16b44-139">Per le impostazioni consigliate per spoof intelligence, vedere [Impostazioni dei criteri anti-phishing predefiniti di EOP.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="16b44-139">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="16b44-140">Usare il Centro sicurezza & conformità per gestire i mittenti falsificati</span><span class="sxs-lookup"><span data-stu-id="16b44-140">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="16b44-141">Se si dispone di un abbonamento a Microsoft 365 Enterprise E5 o se è stato acquistato separatamente un componente aggiuntivo di Microsoft Defender per Office 365, è anche possibile gestire i mittenti che effettuano lo spoofing del dominio tramite spoof [intelligence.](walkthrough-spoof-intelligence-insight.md)</span><span class="sxs-lookup"><span data-stu-id="16b44-141">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="16b44-142">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="16b44-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="16b44-143">Nella pagina **Impostazioni protezione posta indesiderata** fare clic sull'icona Espandi per espandere Criteri di ![ ](../../media/scc-expand-icon.png) **spoofing intelligence.**</span><span class="sxs-lookup"><span data-stu-id="16b44-143">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Selezionare i criteri di spoof intelligence](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="16b44-145">Effettuare una delle seguenti selezioni:</span><span class="sxs-lookup"><span data-stu-id="16b44-145">Make one of the following selections:</span></span>

   - <span data-ttu-id="16b44-146">**Rivedere i nuovi mittenti**</span><span class="sxs-lookup"><span data-stu-id="16b44-146">**Review new senders**</span></span>
   - <span data-ttu-id="16b44-147">**Mostra mittenti già esaminati**</span><span class="sxs-lookup"><span data-stu-id="16b44-147">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="16b44-148">Nel riquadro a comparsa Decidere se a questi mittenti è consentito **effettuare lo spoofing** del riquadro a comparsa degli utenti visualizzato, selezionare una delle schede seguenti:</span><span class="sxs-lookup"><span data-stu-id="16b44-148">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="16b44-149">**Domini:** mittenti che effettuano lo spoofing degli utenti nei domini interni.</span><span class="sxs-lookup"><span data-stu-id="16b44-149">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="16b44-150">**Domini esterni:** mittenti che effettuano lo spoofing di utenti in domini esterni.</span><span class="sxs-lookup"><span data-stu-id="16b44-150">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="16b44-151">Fare ![ clic ](../../media/scc-expand-icon.png) sull'icona Espandi nella colonna Consenti lo **spoofing?**</span><span class="sxs-lookup"><span data-stu-id="16b44-151">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="16b44-152">Scegliere **Sì** per consentire il mittente falsificato oppure **No** per contrassegnare il messaggio come falsificato.</span><span class="sxs-lookup"><span data-stu-id="16b44-152">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="16b44-153">L'azione è controllata dal criterio anti-phishing predefinito o dai criteri anti-phishing personalizzati (il valore predefinito è Sposta messaggio **nella cartella Posta indesiderata).**</span><span class="sxs-lookup"><span data-stu-id="16b44-153">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="16b44-154">Per ulteriori informazioni, vedere [Impostazioni di spoofing nei criteri anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="16b44-154">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Screenshot showing the spoofed senders flyout, and whether the sender is allowed to spoofing](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="16b44-156">Le colonne e i valori visualizzati sono illustrati nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="16b44-156">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="16b44-157">**Utente falsificato:** l'account utente oggetto di spoofing.</span><span class="sxs-lookup"><span data-stu-id="16b44-157">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="16b44-158">Si tratta del mittente del messaggio nell'indirizzo mittente (noto anche come indirizzo) visualizzato `5322.From` nei client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="16b44-158">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="16b44-159">La validità di questo indirizzo non viene controllata da SPF.</span><span class="sxs-lookup"><span data-stu-id="16b44-159">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="16b44-160">Nella scheda **Your Domains** il valore contiene un singolo indirizzo di posta elettronica oppure, se il server di posta elettronica di origine effettua lo spoofing di più account utente, ne contiene più **di uno.**</span><span class="sxs-lookup"><span data-stu-id="16b44-160">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="16b44-161">Nella scheda **Domini esterni** il valore contiene il dominio dell'utente falsificato, non l'indirizzo di posta elettronica completo.</span><span class="sxs-lookup"><span data-stu-id="16b44-161">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="16b44-162">**Infrastruttura di invio:** dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine.</span><span class="sxs-lookup"><span data-stu-id="16b44-162">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="16b44-163">Se l'indirizzo IP di origine non dispone di un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="16b44-163">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="16b44-164">Per ulteriori informazioni sulle origini dei messaggi e sui mittenti dei messaggi, vedere [Una panoramica degli standard dei messaggi di posta elettronica.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="16b44-164">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="16b44-165">**Numero di messaggi**: numero di messaggi dall'infrastruttura di invio all'organizzazione che contengono il mittente o i mittenti falsificati specificati negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="16b44-165">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="16b44-166">**# di reclami degli utenti:** reclami presentata dagli utenti contro questo mittente negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="16b44-166">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="16b44-167">I reclami sono in genere sotto forma di invii di posta indesiderata a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16b44-167">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="16b44-168">**Risultato dell'autenticazione:** uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="16b44-168">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="16b44-169">**Superato:** il mittente ha superato i controlli di autenticazione della posta elettronica del mittente (SPF o DKIM).</span><span class="sxs-lookup"><span data-stu-id="16b44-169">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="16b44-170">**Failed:** il mittente non ha superato i controlli di autenticazione del mittente EOP.</span><span class="sxs-lookup"><span data-stu-id="16b44-170">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="16b44-171">**Sconosciuto:** il risultato di questi controlli non è noto.</span><span class="sxs-lookup"><span data-stu-id="16b44-171">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="16b44-172">**Decisione impostata da**: indica chi ha determinato se l'infrastruttura di invio è autorizzata a effettuare lo spoofing dell'utente:</span><span class="sxs-lookup"><span data-stu-id="16b44-172">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="16b44-173">**Criteri di spoof intelligence** (automatici)</span><span class="sxs-lookup"><span data-stu-id="16b44-173">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="16b44-174">**Amministratore** (manuale)</span><span class="sxs-lookup"><span data-stu-id="16b44-174">**Admin** (manual)</span></span>

   - <span data-ttu-id="16b44-175">**Ultimo messaggio visualizzato:** l'ultima data in cui un messaggio è stato ricevuto dall'infrastruttura di invio che contiene l'utente falsificato.</span><span class="sxs-lookup"><span data-stu-id="16b44-175">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="16b44-176">**Consentito lo spoofing?**: I valori visualizzati qui sono:</span><span class="sxs-lookup"><span data-stu-id="16b44-176">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="16b44-177">**Sì:** i messaggi provenienti dalla combinazione di utente falsificato e infrastruttura di invio sono consentiti e non trattati come messaggi di posta elettronica falsificati.</span><span class="sxs-lookup"><span data-stu-id="16b44-177">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="16b44-178">**No:** i messaggi provenienti dalla combinazione di utente falsificato e infrastruttura di invio vengono contrassegnati come falsificati.</span><span class="sxs-lookup"><span data-stu-id="16b44-178">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="16b44-179">L'azione è controllata dal criterio anti-phishing predefinito o dai criteri anti-phishing personalizzati (il valore predefinito è Sposta messaggio **nella cartella Posta indesiderata).**</span><span class="sxs-lookup"><span data-stu-id="16b44-179">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="16b44-180">Per ulteriori informazioni, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="16b44-180">See the next section for more information.</span></span>

     - <span data-ttu-id="16b44-181">**Alcuni utenti** **(solo scheda Domini):** un'infrastruttura di invio effettua lo spoofing di più utenti, in cui alcuni utenti falsificati sono consentiti e altri no.</span><span class="sxs-lookup"><span data-stu-id="16b44-181">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="16b44-182">Utilizzare la **scheda Dettagli** per visualizzare gli indirizzi specifici.</span><span class="sxs-lookup"><span data-stu-id="16b44-182">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="16b44-183">Nella parte inferiore della pagina fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="16b44-183">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="16b44-184">Utilizzare PowerShell per gestire i mittenti falsificati</span><span class="sxs-lookup"><span data-stu-id="16b44-184">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="16b44-185">Per visualizzare i mittenti consentiti e bloccati in spoof intelligence, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="16b44-185">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="16b44-186">In questo esempio vengono restituite informazioni dettagliate su tutti i mittenti autorizzati a effettuare lo spoofing degli utenti nei domini.</span><span class="sxs-lookup"><span data-stu-id="16b44-186">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="16b44-187">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-PhishFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="16b44-187">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="16b44-188">Per configurare i mittenti consentiti e bloccati in spoof intelligence, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="16b44-188">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="16b44-189">Acquisire l'elenco corrente dei mittenti falsificati rilevati scrivendo l'output del cmdlet **Get-PhishFilterPolicy** in un file CSV:</span><span class="sxs-lookup"><span data-stu-id="16b44-189">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="16b44-190">Modificare il file CSV per aggiungere o modificare i valori **SpoofedUser** (indirizzo di posta elettronica) e **AllowedToSpoof** (Sì o No).</span><span class="sxs-lookup"><span data-stu-id="16b44-190">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="16b44-191">Salvare il file, leggere il file e archiviare il contenuto come variabile denominata `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="16b44-191">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="16b44-192">Utilizzare la `$UpdateSpoofedSenders` variabile per configurare i criteri di spoof intelligence:</span><span class="sxs-lookup"><span data-stu-id="16b44-192">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="16b44-193">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-PhishFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="16b44-193">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="16b44-194">Usare il Centro sicurezza & conformità per configurare spoof intelligence</span><span class="sxs-lookup"><span data-stu-id="16b44-194">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="16b44-195">Le opzioni di configurazione per spoof intelligence sono descritte nelle [impostazioni di spoofing nei criteri anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="16b44-195">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="16b44-196">È possibile configurare le impostazioni di spoof intelligence nel criterio anti-phishing predefinito e anche nei criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="16b44-196">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="16b44-197">Per istruzioni in base all'abbonamento, vedere uno dei seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="16b44-197">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="16b44-198">[Configurare i criteri anti-phishing in EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="16b44-198">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="16b44-199">[Configurare i criteri anti-phishing in Microsoft Defender per Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="16b44-199">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="16b44-200">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="16b44-200">How do you know these procedures worked?</span></span>

<span data-ttu-id="16b44-201">Per verificare di aver configurato spoof intelligence con mittenti autorizzati e non autorizzati a effettuare lo spoofing e che siano state configurate le impostazioni di spoof intelligence, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="16b44-201">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="16b44-202">Nel Centro sicurezza & conformità, andare  a Criteri di gestione delle minacce - Protezione da posta indesiderata espandere Criteri di spoof intelligence selezionare Mostra i mittenti che ho già esaminato selezionare la scheda Domini o domini esterni e verificare il valore Consentito per \>  \>  \>  \> lo  \> **spoofing?**   per il mittente.</span><span class="sxs-lookup"><span data-stu-id="16b44-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="16b44-203">In PowerShell, eseguire i comandi seguenti per visualizzare i mittenti consentiti e non autorizzati a effettuare lo spoofing:</span><span class="sxs-lookup"><span data-stu-id="16b44-203">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="16b44-204">In PowerShell, eseguire il comando seguente per esportare l'elenco di tutti i mittenti falsificati in un file CSV:</span><span class="sxs-lookup"><span data-stu-id="16b44-204">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="16b44-205">Nel Centro sicurezza & conformità passare  a Anti-phishing dei criteri di gestione delle minacce o \>  \>  **anti-phishing ATP** ed eseguire una delle operazioni seguenti:  </span><span class="sxs-lookup"><span data-stu-id="16b44-205">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="16b44-206">Selezionare un criterio dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="16b44-206">Select a policy from the list.</span></span> <span data-ttu-id="16b44-207">Nel riquadro a comparsa visualizzato, verificare i valori nella sezione **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="16b44-207">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="16b44-208">Fare **clic su Criterio predefinito.**</span><span class="sxs-lookup"><span data-stu-id="16b44-208">Click **Default policy**.</span></span> <span data-ttu-id="16b44-209">Nel riquadro a comparsa visualizzato, verificare i valori nella sezione **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="16b44-209">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="16b44-210">In PowerShell di Exchange Online, sostituire con Office365 AntiPhish Default o il nome di un criterio personalizzato ed eseguire il comando seguente per \<Name\> verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="16b44-210">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="16b44-211">Altri modi per gestire lo spoofing e il phishing</span><span class="sxs-lookup"><span data-stu-id="16b44-211">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="16b44-212">Essere accurati sulla protezione da spoofing e phishing.</span><span class="sxs-lookup"><span data-stu-id="16b44-212">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="16b44-213">Ecco alcuni modi correlati per controllare i mittenti che effettuano lo spoofing del dominio e impedire loro di danneggiare l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="16b44-213">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="16b44-214">Controllare il **Rapporto messaggi falsificati.**</span><span class="sxs-lookup"><span data-stu-id="16b44-214">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="16b44-215">È possibile utilizzare questo report spesso per visualizzare e gestire i mittenti falsificati.</span><span class="sxs-lookup"><span data-stu-id="16b44-215">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="16b44-216">Per informazioni, vedere [il report Falsificazioni.](view-email-security-reports.md#spoof-detections-report)</span><span class="sxs-lookup"><span data-stu-id="16b44-216">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="16b44-217">Esaminare la configurazione di Sender Policy Framework (SPF).</span><span class="sxs-lookup"><span data-stu-id="16b44-217">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="16b44-218">Per una rapida introduzione a SPF e le istruzioni di configurazione, vedere [Configurare SPF in Microsoft 365 per prevenire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="16b44-218">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="16b44-219">Per informazioni più dettagliate su come Office 365 utilizza SPF oppure per risolvere i problemi o per eseguire distribuzioni non standard (ad esempio, le distribuzioni ibride), iniziare da [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="16b44-219">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="16b44-220">Esaminare la configurazione DKIM (DomainKeys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="16b44-220">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="16b44-221">È consigliabile utilizzare DKIM oltre a SPF e DMARC per impedire agli utenti malintenzionati di inviare messaggi che sembrano provenienti dal dominio.</span><span class="sxs-lookup"><span data-stu-id="16b44-221">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="16b44-222">DKIM consente di aggiungere una firma digitale nell'intestazione dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="16b44-222">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="16b44-223">Per informazioni, vedere Usare DKIM per convalidare la posta elettronica in uscita [inviata dal dominio personalizzato in Office 365.](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="16b44-223">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="16b44-224">Esaminare la configurazione DMARC (Domain-based Message Authentication, Reporting, and Conformance).</span><span class="sxs-lookup"><span data-stu-id="16b44-224">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="16b44-225">L'implementazione di DMARC con SPF e DKIM fornisce un'ulteriore protezione dallo spoofing e dal phishing.</span><span class="sxs-lookup"><span data-stu-id="16b44-225">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="16b44-226">DMARC consente ai sistemi di posta di ricezione di determinare cosa fare con i messaggi inviati dal dominio che non supera i controlli SPF o DKIM.</span><span class="sxs-lookup"><span data-stu-id="16b44-226">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="16b44-227">Per informazioni, vedere [Usare DMARC per convalidare la posta elettronica in Office 365.](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="16b44-227">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
