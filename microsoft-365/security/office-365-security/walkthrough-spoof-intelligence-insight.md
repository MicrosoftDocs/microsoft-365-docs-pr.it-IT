---
title: Gestire i mittenti contraffatti utilizzando i criteri di spoof intelligence e informazioni di spoof intelligence
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a usare i criteri di spoof intelligence e le informazioni di spoof intelligence per consentire o bloccare i mittenti falsificati rilevati.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0e5c83bc50197e30c12f8f7aeedc83930d7ff5e
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793209"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a><span data-ttu-id="4d266-103">Gestire i mittenti contraffatti utilizzando i criteri di spoof intelligence e informazioni di spoof intelligence in EOP</span><span class="sxs-lookup"><span data-stu-id="4d266-103">Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4d266-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="4d266-104">**Applies to**</span></span>
- [<span data-ttu-id="4d266-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="4d266-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4d266-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d266-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="4d266-107">In questo articolo viene descritta la precedente esperienza di gestione dei mittenti falsificati che viene sostituita.</span><span class="sxs-lookup"><span data-stu-id="4d266-107">This article describes the older spoofed sender management experience that's being replaced.</span></span> <span data-ttu-id="4d266-108">Per ulteriori informazioni sulla nuova esperienza, vedere [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="4d266-108">For more information about the new experience, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)</span></span>

<span data-ttu-id="4d266-109">Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, i messaggi di posta elettronica in ingresso vengono automaticamente protetti da spoofing da EOP a partire da ottobre 2018.</span><span class="sxs-lookup"><span data-stu-id="4d266-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="4d266-110">EOP usa **l'intelligence spoofing** come parte della difesa generale dell'organizzazione contro il phishing.</span><span class="sxs-lookup"><span data-stu-id="4d266-110">EOP uses **spoof intelligence** as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="4d266-111">Per ulteriori informazioni, vedere [Protezione anti-spoofing in EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="4d266-111">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="4d266-112">Il criterio di **spoof intelligence** predefinito (e solo) garantisce che i messaggi di posta elettronica falsificati inviati da mittenti legittimi non siano coinvolti nei filtri di posta indesiderata di EOP proteggendo gli utenti da attacchi di posta indesiderata o phishing.</span><span class="sxs-lookup"><span data-stu-id="4d266-112">The default (and only) **spoof intelligence policy** helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters while protecting your users from spam or phishing attacks.</span></span> <span data-ttu-id="4d266-113">È inoltre possibile utilizzare le informazioni **di intelligence spoofing** per determinare rapidamente quali mittenti esterni stanno inviando legittimamente messaggi di posta elettronica non autenticati (messaggi provenienti da domini che non superano i controlli SPF, DKIM o DMARC).</span><span class="sxs-lookup"><span data-stu-id="4d266-113">You can also use the **Spoof intelligence insight** to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="4d266-114">È possibile gestire l'intelligence di spoofing nel Centro sicurezza & e conformità o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con cassette postali in Exchange Online, PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="4d266-114">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4d266-115">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="4d266-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4d266-116">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4d266-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span>
  - <span data-ttu-id="4d266-117">Per passare direttamente alla pagina **Impostazioni protezione da** posta indesiderata per il criterio di spoofing intelligence, utilizzare <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="4d266-117">To go directly to the **Anti-spam settings** page for the spoof intelligence policy, use <https://protection.office.com/antispam>.</span></span>
  - <span data-ttu-id="4d266-118">Per passare direttamente alla pagina **Dashboard di sicurezza** per le informazioni di spoofing intelligence, utilizzare <https://protection.office.com/searchandinvestigation/dashboard> .</span><span class="sxs-lookup"><span data-stu-id="4d266-118">To go directly to the **Security dashboard** page for the spoof intelligence insight, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

- <span data-ttu-id="4d266-119">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4d266-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="4d266-120">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="4d266-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4d266-121">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="4d266-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4d266-122">Per modificare i criteri di spoof intelligence o abilitare o disabilitare l'intelligence spoofing, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o **Amministratore** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4d266-122">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="4d266-123">Per l'accesso in sola lettura al criterio di spoof intelligence, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4d266-123">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4d266-124">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="4d266-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="4d266-125">**Note**:</span><span class="sxs-lookup"><span data-stu-id="4d266-125">**Notes**:</span></span>

  - <span data-ttu-id="4d266-126">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d266-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4d266-127">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="4d266-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="4d266-128">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4d266-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="4d266-129">Le opzioni per spoof intelligence sono descritte in [Impostazioni spoofing nei criteri anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="4d266-129">The options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="4d266-130">È possibile abilitare, disabilitare e configurare le impostazioni di spoof intelligence nei criteri anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="4d266-130">You can enable, disable, and configure the spoof intelligence settings in anti-phishing policies.</span></span> <span data-ttu-id="4d266-131">Per istruzioni basate sull'abbonamento, vedere uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d266-131">For instructions based on your subscription, see one of the following topics:</span></span>

  - <span data-ttu-id="4d266-132">[Configurare i criteri anti-phishing in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4d266-132">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>
  - <span data-ttu-id="4d266-133">[Configurare i criteri anti-phishing in Microsoft Defender per Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4d266-133">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="4d266-134">Per le impostazioni consigliate per spoof intelligence, vedere [Impostazioni dei criteri anti-phishing EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="4d266-134">For our recommended settings for spoof intelligence, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

## <a name="manage-spoofed-senders"></a><span data-ttu-id="4d266-135">Gestire mittenti contraffatti</span><span class="sxs-lookup"><span data-stu-id="4d266-135">Manage spoofed senders</span></span>

<span data-ttu-id="4d266-136">Esistono due modi per consentire e bloccare i mittenti contraffatti:</span><span class="sxs-lookup"><span data-stu-id="4d266-136">There are two ways to allow and block spoofed senders:</span></span>

- [<span data-ttu-id="4d266-137">Usare i criteri di spoof intelligence</span><span class="sxs-lookup"><span data-stu-id="4d266-137">Use the spoof intelligence policy</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [<span data-ttu-id="4d266-138">Usare le informazioni dettagliate di spoof intelligence</span><span class="sxs-lookup"><span data-stu-id="4d266-138">Use the spoof intelligence insight</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a><span data-ttu-id="4d266-139">Gestire i mittenti falsificati nel criterio di spoof intelligence</span><span class="sxs-lookup"><span data-stu-id="4d266-139">Manage spoofed senders in the spoof intelligence policy</span></span>

1. <span data-ttu-id="4d266-140">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="4d266-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="4d266-141">Nella pagina **Impostazioni protezione da posta indesiderata** fare clic su Espandi icona per espandere Criteri di ![ ](../../media/scc-expand-icon.png) **spoofing intelligence.**</span><span class="sxs-lookup"><span data-stu-id="4d266-141">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Selezionare i criteri di spoof intelligence](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="4d266-143">Effettuare una delle seguenti selezioni:</span><span class="sxs-lookup"><span data-stu-id="4d266-143">Make one of the following selections:</span></span>

   - <span data-ttu-id="4d266-144">**Rivedere i nuovi mittenti**</span><span class="sxs-lookup"><span data-stu-id="4d266-144">**Review new senders**</span></span>
   - <span data-ttu-id="4d266-145">**Mostra mittenti già esaminati**</span><span class="sxs-lookup"><span data-stu-id="4d266-145">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="4d266-146">Nel riquadro a comparsa Decidi se questi mittenti sono autorizzati a **eseguire lo spoofing** dei tuoi utenti, seleziona una delle schede seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d266-146">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="4d266-147">**Domini:** mittenti che effettuano spoofing degli utenti nei domini interni.</span><span class="sxs-lookup"><span data-stu-id="4d266-147">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="4d266-148">**Domini esterni:** mittenti che effettuano lo spoofing di utenti in domini esterni.</span><span class="sxs-lookup"><span data-stu-id="4d266-148">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="4d266-149">Fare ![ clic ](../../media/scc-expand-icon.png) sull'icona Espandi nella colonna Consenti **spoofing?** .</span><span class="sxs-lookup"><span data-stu-id="4d266-149">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="4d266-150">Scegliere **Sì** per consentire il mittente contraffatto oppure **No** per contrassegnare il messaggio come contraffatto.</span><span class="sxs-lookup"><span data-stu-id="4d266-150">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="4d266-151">L'azione è controllata dal criterio anti-phishing predefinito o dai criteri anti-phishing personalizzati (il valore predefinito è Sposta il messaggio **nella cartella Posta indesiderata**).</span><span class="sxs-lookup"><span data-stu-id="4d266-151">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="4d266-152">Per altre informazioni, vedere [Impostazioni di spoofing nei criteri anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="4d266-152">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Screenshot che mostra il riquadro a comparsa dei mittenti contraffatti e se il mittente è autorizzato a effettuare lo spoofing](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="4d266-154">Le colonne e i valori visualizzati sono illustrati nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="4d266-154">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="4d266-155">**Utente contraffatto:** account utente che viene contraffatto.</span><span class="sxs-lookup"><span data-stu-id="4d266-155">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="4d266-156">Si tratta del mittente del messaggio nell'indirizzo mittente (noto anche come indirizzo) visualizzato `5322.From` nei client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4d266-156">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="4d266-157">La validità di questo indirizzo non viene controllata da SPF.</span><span class="sxs-lookup"><span data-stu-id="4d266-157">The validity of this address is not checked by SPF.</span></span>
     - <span data-ttu-id="4d266-158">Nella scheda **Domini,** il valore contiene un singolo indirizzo di posta elettronica oppure, se il server di posta elettronica di origine esegue lo spoofing di più account utente, contiene **più di un**.</span><span class="sxs-lookup"><span data-stu-id="4d266-158">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>
     - <span data-ttu-id="4d266-159">Nella scheda **Domini esterni** il valore contiene il dominio dell'utente contraffatto, non l'indirizzo di posta elettronica completo.</span><span class="sxs-lookup"><span data-stu-id="4d266-159">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="4d266-160">**Infrastruttura di invio:** dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine.</span><span class="sxs-lookup"><span data-stu-id="4d266-160">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="4d266-161">Se l'indirizzo IP di origine non ha un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="4d266-161">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="4d266-162">Per ulteriori informazioni sulle origini dei messaggi e sui mittenti dei messaggi, vedere [Panoramica degli standard dei messaggi di posta elettronica.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="4d266-162">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="4d266-163">**# di messaggi**: Numero di messaggi dall'infrastruttura di invio all'organizzazione che contengono il mittente o i mittenti contraffatti specificati negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="4d266-163">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="4d266-164">**Numero di reclami degli** utenti: reclami da parte degli utenti nei confronti di questo mittente negli ultimi 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="4d266-164">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="4d266-165">I reclami sono in genere sotto forma di invii indesiderati a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d266-165">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="4d266-166">**Risultato dell'autenticazione:** uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d266-166">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="4d266-167">**Superato**: il mittente ha superato i controlli di autenticazione della posta elettronica del mittente (SPF o DKIM).</span><span class="sxs-lookup"><span data-stu-id="4d266-167">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="4d266-168">**Failed**: Il mittente non ha superato i controlli di autenticazione del mittente EOP.</span><span class="sxs-lookup"><span data-stu-id="4d266-168">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="4d266-169">**Sconosciuto:** il risultato di questi controlli non è noto.</span><span class="sxs-lookup"><span data-stu-id="4d266-169">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="4d266-170">**Decision set by**: Mostra chi ha determinato se l'infrastruttura di invio è autorizzata a effettuare lo spoofing dell'utente:</span><span class="sxs-lookup"><span data-stu-id="4d266-170">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="4d266-171">**Criteri di spoofing intelligence** (automatico)</span><span class="sxs-lookup"><span data-stu-id="4d266-171">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="4d266-172">**Amministratore** (manuale)</span><span class="sxs-lookup"><span data-stu-id="4d266-172">**Admin** (manual)</span></span>

   - <span data-ttu-id="4d266-173">**Last seen**: Data dell'ultima ricezione di un messaggio dall'infrastruttura di invio contenente l'utente contraffatto.</span><span class="sxs-lookup"><span data-stu-id="4d266-173">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="4d266-174">**Consentito lo spoofing?**: I valori visualizzati qui sono:</span><span class="sxs-lookup"><span data-stu-id="4d266-174">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="4d266-175">**Sì:** i messaggi provenienti dalla combinazione di utenti contraffatti e infrastruttura di invio sono consentiti e non considerati messaggi di posta elettronica contraffatti.</span><span class="sxs-lookup"><span data-stu-id="4d266-175">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="4d266-176">**No**: i messaggi provenienti dalla combinazione di utenti contraffatti e infrastruttura di invio vengono contrassegnati come contraffatti.</span><span class="sxs-lookup"><span data-stu-id="4d266-176">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="4d266-177">L'azione è controllata dal criterio anti-phishing predefinito o dai criteri anti-phishing personalizzati (il valore predefinito è Sposta il messaggio **nella cartella Posta indesiderata**).</span><span class="sxs-lookup"><span data-stu-id="4d266-177">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="4d266-178">Per ulteriori informazioni, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="4d266-178">See the next section for more information.</span></span>

     - <span data-ttu-id="4d266-179">**Alcuni utenti** **(solo scheda Domini):** un'infrastruttura di invio sta effettuando lo spoofing di più utenti, in cui alcuni utenti contraffatti sono consentiti e altri no.</span><span class="sxs-lookup"><span data-stu-id="4d266-179">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="4d266-180">Utilizzare la **scheda Dettagli** per visualizzare gli indirizzi specifici.</span><span class="sxs-lookup"><span data-stu-id="4d266-180">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="4d266-181">Nella parte inferiore della pagina fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4d266-181">At the bottom of the page, click **Save**.</span></span>

#### <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="4d266-182">Utilizzare PowerShell per gestire i mittenti contraffatti</span><span class="sxs-lookup"><span data-stu-id="4d266-182">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="4d266-183">Per visualizzare i mittenti consentiti e bloccati in spoof intelligence, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="4d266-183">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="4d266-184">In questo esempio vengono restituite informazioni dettagliate su tutti i mittenti autorizzati a effettuare lo spoofing degli utenti nei domini.</span><span class="sxs-lookup"><span data-stu-id="4d266-184">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="4d266-185">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="4d266-185">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="4d266-186">Per configurare i mittenti consentiti e bloccati in spoof intelligence, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="4d266-186">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="4d266-187">Acquisire l'elenco corrente dei mittenti contraffatti rilevati scrivendo l'output del cmdlet **Get-PhishFilterPolicy** in un file CSV eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d266-187">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file by running the following command:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="4d266-188">Modificare il file CSV per aggiungere o modificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d266-188">Edit the CSV file to add or modify the following values:</span></span>
   - <span data-ttu-id="4d266-189">**Mittente** (dominio nel record PTR del server di origine o nell'indirizzo IP/24)</span><span class="sxs-lookup"><span data-stu-id="4d266-189">**Sender** (domain in source server's PTR record or IP/24 address)</span></span>
   - <span data-ttu-id="4d266-190">**SpoofedUser**: Uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d266-190">**SpoofedUser**: One of the following values:</span></span>
     - <span data-ttu-id="4d266-191">Indirizzo di posta elettronica dell'utente interno.</span><span class="sxs-lookup"><span data-stu-id="4d266-191">The internal user's email address.</span></span>
     - <span data-ttu-id="4d266-192">Dominio di posta elettronica dell'utente esterno.</span><span class="sxs-lookup"><span data-stu-id="4d266-192">The external user's email domain.</span></span>
     - <span data-ttu-id="4d266-193">Valore vuoto che indica se si desidera bloccare o consentire tutti i messaggi falsificati provenienti dal mittente **specificato,** indipendentemente dall'indirizzo di posta elettronica contraffatto.</span><span class="sxs-lookup"><span data-stu-id="4d266-193">A blank value that indicates you want to block or allow any and all spoofed messages from the specified **Sender**, regardless of the spoofed email address.</span></span>
   - <span data-ttu-id="4d266-194">**AllowedToSpoof** (Sì o No)</span><span class="sxs-lookup"><span data-stu-id="4d266-194">**AllowedToSpoof** (Yes or No)</span></span>
   - <span data-ttu-id="4d266-195">**SpoofType** (interno o esterno)</span><span class="sxs-lookup"><span data-stu-id="4d266-195">**SpoofType** (Internal or External)</span></span>

   <span data-ttu-id="4d266-196">Salvare il file, leggere il file e archiviare il contenuto come variabile denominata `$UpdateSpoofedSenders` eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d266-196">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders` by running the following command:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="4d266-197">Utilizzare la `$UpdateSpoofedSenders` variabile per configurare i criteri di spoof intelligence eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="4d266-197">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy by running the following command:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="4d266-198">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-PhishFilterPolicy.](/powershell/module/exchange/set-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="4d266-198">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span></span>

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a><span data-ttu-id="4d266-199">Gestire i mittenti falsificati nell'analisi di spoof intelligence</span><span class="sxs-lookup"><span data-stu-id="4d266-199">Manage spoofed senders in the spoof intelligence insight</span></span>

1. <span data-ttu-id="4d266-200">Nel Centro sicurezza & conformità passare a **Dashboard di gestione delle** \> **minacce**.</span><span class="sxs-lookup"><span data-stu-id="4d266-200">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard**.</span></span>

2. <span data-ttu-id="4d266-201">Nella riga **Insights** cercare uno degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d266-201">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="4d266-202">**Domini contraffatti probabilmente negli ultimi sette** giorni: questa informazione indica che l'intelligence di spoofing è abilitata (è abilitata per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="4d266-202">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="4d266-203">**Abilita protezione da spoofing**: questa informazione indica che l'intelligence di spoofing è disabilitata e fare clic sull'analisi consente di abilitare l'intelligence di spoofing.</span><span class="sxs-lookup"><span data-stu-id="4d266-203">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="4d266-204">Le informazioni dettagliate nel dashboard mostrano informazioni come queste:</span><span class="sxs-lookup"><span data-stu-id="4d266-204">The insight on the dashboard shows you information like this:</span></span>

   ![Screenshot of spoof intelligence insight](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="4d266-206">Questa panoramica ha due modalità:</span><span class="sxs-lookup"><span data-stu-id="4d266-206">This insight has two modes:</span></span>

   - <span data-ttu-id="4d266-207">**Modalità di analisi:** se l'intelligence di spoofing è abilitata, le informazioni dettagliate mostrano quanti messaggi sono stati influenzati dalle funzionalità di spoof intelligence negli ultimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="4d266-207">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="4d266-208">**Cosa succede se la** modalità : se l'intelligence  di spoofing è disabilitata, le informazioni dettagliate mostrano quanti messaggi sarebbero stati influenzati dalle funzionalità di spoof intelligence negli ultimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="4d266-208">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="4d266-209">In entrambi i casi, i domini contraffatti visualizzati nell'analisi sono suddivisi in due categorie: **domini** sospetti **e domini non sospetti.**</span><span class="sxs-lookup"><span data-stu-id="4d266-209">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="4d266-210">**Domini sospetti**:</span><span class="sxs-lookup"><span data-stu-id="4d266-210">**Suspicious domains**:</span></span>
     - <span data-ttu-id="4d266-211">**Spoofing** ad alta probabilità : in base ai modelli di invio cronologici e al punteggio di reputazione dei domini, è molto probabile che i domini siano contraffatti e che i messaggi provenienti da questi domini siano più dannosi.</span><span class="sxs-lookup"><span data-stu-id="4d266-211">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>
     - <span data-ttu-id="4d266-212">**Spoofing** di probabilità moderato : in base ai modelli di invio cronologici e al punteggio di reputazione dei domini, siamo moderatamente sicuri che i domini siano contraffatti e che i messaggi inviati da questi domini siano legittimi.</span><span class="sxs-lookup"><span data-stu-id="4d266-212">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="4d266-213">I falsi positivi sono più probabili in questa categoria rispetto allo spoofing ad alta probabilità.</span><span class="sxs-lookup"><span data-stu-id="4d266-213">False positives are more likely in this category than high-confidence spoof.</span></span>
   - <span data-ttu-id="4d266-214">**Domini non sospetti:** il dominio non ha superato l'autenticazione esplicita della posta elettronica [controlla SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="4d266-214">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="4d266-215">Tuttavia, il dominio ha superato i controlli impliciti di autenticazione della posta elettronica ([autenticazione composita](email-validation-and-authentication.md#composite-authentication)).</span><span class="sxs-lookup"><span data-stu-id="4d266-215">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="4d266-216">Di conseguenza, non è stata eseguita alcuna azione anti-spoofing sul messaggio.</span><span class="sxs-lookup"><span data-stu-id="4d266-216">As a result, no anti-spoofing action was taken on the message.</span></span>

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a><span data-ttu-id="4d266-217">Visualizzare informazioni dettagliate sui domini sospetti e non sospetti</span><span class="sxs-lookup"><span data-stu-id="4d266-217">View detailed information about suspicious and nonsuspicious domains</span></span>

1. <span data-ttu-id="4d266-218">Nella pagina Spoof intelligence insight fare clic **su Domini sospetti** o Domini **non** sospetti per passare alla pagina Spoof **intelligence insight.**</span><span class="sxs-lookup"><span data-stu-id="4d266-218">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="4d266-219">La **pagina Informazioni di spoofing** intelligence contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d266-219">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="4d266-220">**Dominio contraffatto**: Dominio dell'utente contraffatto visualizzato  nella casella Da nei client di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4d266-220">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="4d266-221">Questo indirizzo è noto anche come `5322.From` indirizzo.</span><span class="sxs-lookup"><span data-stu-id="4d266-221">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="4d266-222">**Infrastruttura**: nota anche come infrastruttura _di invio._</span><span class="sxs-lookup"><span data-stu-id="4d266-222">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="4d266-223">Dominio trovato in una ricerca DNS inversa (record PTR) dell'indirizzo IP del server di posta elettronica di origine.</span><span class="sxs-lookup"><span data-stu-id="4d266-223">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="4d266-224">Se l'indirizzo IP di origine non ha un record PTR, l'infrastruttura di invio viene identificata come \<source IP\> /24 (ad esempio, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="4d266-224">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="4d266-225">**Numero messaggi**: numero di messaggi dall'infrastruttura di invio all'organizzazione che contengono il dominio contraffatto specificato negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="4d266-225">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="4d266-226">**Last seen**: Data dell'ultima ricezione di un messaggio dall'infrastruttura di invio contenente il dominio contraffatto.</span><span class="sxs-lookup"><span data-stu-id="4d266-226">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="4d266-227">**Tipo spoof**: questo valore è **External.**</span><span class="sxs-lookup"><span data-stu-id="4d266-227">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="4d266-228">**Consentito lo spoofing?**: I valori visualizzati qui sono:</span><span class="sxs-lookup"><span data-stu-id="4d266-228">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="4d266-229">**Sì:** i messaggi provenienti dalla combinazione del dominio dell'utente contraffatto e dell'infrastruttura di invio sono consentiti e non considerati messaggi di posta elettronica contraffatti.</span><span class="sxs-lookup"><span data-stu-id="4d266-229">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="4d266-230">**No**: i messaggi provenienti dalla combinazione del dominio dell'utente contraffatto e dell'infrastruttura di invio vengono contrassegnati come contraffatti.</span><span class="sxs-lookup"><span data-stu-id="4d266-230">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="4d266-231">L'azione è controllata dal criterio anti-phishing predefinito o dai criteri anti-phishing personalizzati (il valore predefinito è Sposta il messaggio **nella cartella Posta indesiderata**).</span><span class="sxs-lookup"><span data-stu-id="4d266-231">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

2. <span data-ttu-id="4d266-232">Selezionare un elemento nell'elenco per visualizzare i dettagli sulla coppia dominio/infrastruttura di invio in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="4d266-232">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="4d266-233">Le informazioni includono:</span><span class="sxs-lookup"><span data-stu-id="4d266-233">The information includes:</span></span>
   - <span data-ttu-id="4d266-234">Perché l'abbiamo preso.</span><span class="sxs-lookup"><span data-stu-id="4d266-234">Why we caught this.</span></span>
   - <span data-ttu-id="4d266-235">Cosa è necessario fare.</span><span class="sxs-lookup"><span data-stu-id="4d266-235">What you need to do.</span></span>
   - <span data-ttu-id="4d266-236">Riepilogo del dominio.</span><span class="sxs-lookup"><span data-stu-id="4d266-236">A domain summary.</span></span>
   - <span data-ttu-id="4d266-237">WhoIs i dati sul mittente.</span><span class="sxs-lookup"><span data-stu-id="4d266-237">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="4d266-238">Messaggi simili che abbiamo visto nel tenant dallo stesso mittente.</span><span class="sxs-lookup"><span data-stu-id="4d266-238">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="4d266-239">Da qui puoi anche scegliere di aggiungere o rimuovere la coppia dominio/infrastruttura di invio **dall'elenco Consenti spoofing** dei mittenti consentiti.</span><span class="sxs-lookup"><span data-stu-id="4d266-239">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="4d266-240">È sufficiente impostare l'interruttore di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="4d266-240">Simply set the toggle accordingly.</span></span>

   ![Screenshot of a domain in the Spoof intelligence insight details pane](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4d266-242">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="4d266-242">How do you know these procedures worked?</span></span>

<span data-ttu-id="4d266-243">Per verificare di aver configurato l'intelligence di spoofing con i mittenti autorizzati e non autorizzati a effettuare lo spoofing, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d266-243">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, use any of the following steps:</span></span>

- <span data-ttu-id="4d266-244">Nel Centro sicurezza & conformità, andare  a Gestione delle minacce Criteri Di protezione da posta indesiderata Espandere Criteri di spoofing intelligence selezionare Mostra mittenti già esaminati selezionare la scheda Domini o domini esterni e verificare il valore Consentito per \>  \>  \>  \> lo  \> **spoofing?**   per il mittente.</span><span class="sxs-lookup"><span data-stu-id="4d266-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="4d266-245">In PowerShell, eseguire i comandi seguenti per visualizzare i mittenti consentiti e non autorizzati a effettuare lo spoofing:</span><span class="sxs-lookup"><span data-stu-id="4d266-245">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="4d266-246">In PowerShell, eseguire il comando seguente per esportare l'elenco di tutti i mittenti falsificati in un file CSV:</span><span class="sxs-lookup"><span data-stu-id="4d266-246">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
