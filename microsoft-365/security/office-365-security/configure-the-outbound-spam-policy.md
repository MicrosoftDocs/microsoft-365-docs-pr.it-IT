---
title: Configurare il filtro per la posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: Il filtro di protezione da posta indesiderata in uscita è sempre abilitato se si utilizza il servizio per l'invio di messaggi di posta elettronica in uscita, proteggendo così l'organizzazione utilizzando il servizio e i destinatari previsti.
ms.openlocfilehash: e788310ae8fd3c0da7f1a39fbba2dc0d6e369d30
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893918"
---
# <a name="configure-outbound-spam-filtering-in-office-365"></a><span data-ttu-id="11ce8-103">Configurare il filtro per la posta indesiderata in uscita in Office 365</span><span class="sxs-lookup"><span data-stu-id="11ce8-103">Configure outbound spam filtering in Office 365</span></span>

<span data-ttu-id="11ce8-104">Se si è un cliente di Office 365 con cassette postali in Exchange Online o un cliente di Exchange Online Protection (EOP) autonomo senza cassette postali di Exchange Online, i messaggi di posta elettronica in uscita inviati tramite EOP vengono controllati automaticamente per la posta indesiderata e insoliti attività di invio.</span><span class="sxs-lookup"><span data-stu-id="11ce8-104">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="11ce8-105">La posta indesiderata in uscita da un utente dell'organizzazione indica in genere un account compromesso.</span><span class="sxs-lookup"><span data-stu-id="11ce8-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="11ce8-106">I messaggi in uscita sospetti sono contrassegnati come posta indesiderata (indipendentemente dal livello di probabilità di posta indesiderata o SCL) e vengono instradati attraverso il [pool di recapito ad alto rischio](high-risk-delivery-pool-for-outbound-messages.md) per proteggere la reputazione del servizio, ovvero mantenere i server di posta elettronica di origine di Office 365 fuori dagli elenchi di indirizzi IP bloccati.</span><span class="sxs-lookup"><span data-stu-id="11ce8-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Office 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="11ce8-107">Gli amministratori ricevono automaticamente una notifica delle attività di posta elettronica in uscita sospette e degli utenti bloccati tramite [criteri di avviso](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="11ce8-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="11ce8-108">EOP utilizza i criteri di posta indesiderata in uscita come parte della difesa complessiva dell'organizzazione contro la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="11ce8-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="11ce8-109">Per ulteriori informazioni, vedere [protezione da posta indesiderata in Office 365](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="11ce8-109">For more information, see [Anti-spam protection in Office 365](anti-spam-protection.md).</span></span>

<span data-ttu-id="11ce8-110">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio di posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="11ce8-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="11ce8-111">Per una maggiore granularità, è anche possibile creare criteri di posta indesiderata in uscita personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="11ce8-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="11ce8-112">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma è possibile cambiare la priorità (ordine di esecuzione) dei criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="11ce8-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="11ce8-113">È possibile configurare i criteri di posta indesiderata in uscita in Office 365 Security & Compliance Center o in PowerShell (Exchange Online PowerShell per i clienti di Office 365; PowerShell di Exchange Online Protection per clienti EOP autonomi.</span><span class="sxs-lookup"><span data-stu-id="11ce8-113">You can configure outbound spam policies in the Office 365 Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="outbound-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a><span data-ttu-id="11ce8-114">Criteri di posta indesiderata in uscita in Office 365 Security & Compliance Center vs Exchange Online PowerShell o Exchange Online Protection PowerShell</span><span class="sxs-lookup"><span data-stu-id="11ce8-114">Outbound spam policies in the Office 365 Security & Compliance Center vs Exchange Online PowerShell or Exchange Online Protection PowerShell</span></span>

<span data-ttu-id="11ce8-115">Gli elementi di base di un criterio di posta indesiderata in uscita in EOP sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="11ce8-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="11ce8-116">**Criterio di filtro per la posta indesiderata in uscita**: consente di specificare le azioni per i verdetti del filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="11ce8-117">**Regola del filtro per la posta indesiderata in uscita**: consente di specificare i filtri priorità e destinatario (a chi si applica il criterio) per un criterio di filtro posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="11ce8-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="11ce8-118">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri di posta indesiderata in uscita nel centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="11ce8-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="11ce8-119">Quando si crea un criterio di posta indesiderata in uscita nel centro sicurezza & Compliance, si sta effettivamente creando una regola di filtro per la posta indesiderata in uscita e il criterio di filtro per la posta indesiderata in uscita associato contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="11ce8-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="11ce8-120">Quando si modifica un criterio di posta indesiderata in uscita nel centro sicurezza & conformità, le impostazioni relative ai filtri nome, priorità, abilitato o disabilitato e destinatario modificano la regola del filtro per la posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="11ce8-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="11ce8-121">Tutte le altre impostazioni modificano i criteri di filtro della posta indesiderata in uscita associati.</span><span class="sxs-lookup"><span data-stu-id="11ce8-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="11ce8-122">Quando si rimuove un criterio di posta indesiderata in uscita dal centro sicurezza & conformità, la regola di filtro posta indesiderata in uscita e i criteri di filtro della posta indesiderata in uscita associati vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="11ce8-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="11ce8-123">In Exchange Online PowerShell o Exchange Online Protection PowerShell autonomo, la differenza tra i criteri di filtro della posta indesiderata in uscita e le regole del filtro per la posta indesiderata è evidente.</span><span class="sxs-lookup"><span data-stu-id="11ce8-123">In Exchange Online PowerShell or standalone Exchange Online Protection PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="11ce8-124">È possibile gestire i criteri di filtro della posta indesiderata in uscita utilizzando i \*\* \*cmdlet-HostedContentFilterPolicy\*\* e gestire le regole del filtro per la posta indesiderata in uscita utilizzando i \*\* \*cmdlet-HostedContentFilterRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="11ce8-124">You manage outbound spam filter policies by using the **\*-HostedContentFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedContentFilterRule** cmdlets.</span></span>

- <span data-ttu-id="11ce8-125">In PowerShell, creare innanzitutto il criterio di filtro per la posta indesiderata in uscita, quindi creare la regola di filtro posta indesiderata in uscita che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="11ce8-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="11ce8-126">In PowerShell, è possibile modificare le impostazioni nel criterio di filtro della posta indesiderata in uscita e la regola di filtro posta indesiderata in uscita separatamente.</span><span class="sxs-lookup"><span data-stu-id="11ce8-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="11ce8-127">Quando si rimuove un criterio di filtro per la posta indesiderata in uscita da PowerShell, la regola di filtro posta indesiderata in uscita corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="11ce8-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="11ce8-128">Criterio di posta indesiderata in uscita predefinito</span><span class="sxs-lookup"><span data-stu-id="11ce8-128">Default outbound spam policy</span></span>

<span data-ttu-id="11ce8-129">Ogni organizzazione dispone di un criterio di posta indesiderata in uscita incorporato denominato default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="11ce8-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="11ce8-130">Il criterio di filtro per la posta indesiderata in uscita denominato default viene applicato a tutti i destinatari dell'organizzazione, anche se non esiste una regola di filtro per la posta indesiderata in uscita (filtri destinatario) associata al criterio.</span><span class="sxs-lookup"><span data-stu-id="11ce8-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="11ce8-131">Il criterio denominato default ha il valore di priorità personalizzato **più basso** che non è possibile modificare (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="11ce8-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="11ce8-132">Tutti i criteri personalizzati creati hanno sempre una priorità più alta rispetto al criterio denominato default.</span><span class="sxs-lookup"><span data-stu-id="11ce8-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="11ce8-133">Il criterio denominato default è il criterio predefinito (la **proprietà IsDefault** ha il valore `True`) e non è possibile eliminare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="11ce8-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="11ce8-134">Per aumentare l'efficacia del filtro per la posta indesiderata in uscita, è possibile creare criteri di posta indesiderata in uscita personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="11ce8-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="11ce8-135">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="11ce8-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="11ce8-136">È possibile aprire il Centro sicurezza & compliance in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="11ce8-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="11ce8-137">Per passare direttamente alla pagina **delle impostazioni di protezione da posta indesiderata** , utilizzare <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="11ce8-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="11ce8-138">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="11ce8-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="11ce8-139">Per connettersi a PowerShell di Exchange Online Protection autonomo, vedere [connessione a Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="11ce8-139">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="11ce8-140">Prima di poter eseguire queste procedure, è necessario disporre delle autorizzazioni assegnate.</span><span class="sxs-lookup"><span data-stu-id="11ce8-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="11ce8-141">Per aggiungere, modificare ed eliminare i criteri di posta indesiderata in uscita, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="11ce8-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="11ce8-142">Per l'accesso in sola lettura ai criteri di posta indesiderata in uscita, è necessario essere membri del gruppo di ruoli **lettore di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="11ce8-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="11ce8-143">Per ulteriori informazioni sui gruppi di ruoli nel centro sicurezza & Compliance, vedere [Permissions in the Office 365 security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="11ce8-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="11ce8-144">Per le impostazioni consigliate per i criteri di protezione da posta indesiderata in uscita, vedere [EOP in uscita Spam Policy Filter Settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="11ce8-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="11ce8-145">I [criteri di avviso](../../compliance/alert-policies.md) predefiniti denominati limite di invio di posta elettronica sono stati **superati**, sono stati **rilevati modelli di invio di messaggi**di posta elettronica sospetti e non è stato possibile inviare **messaggi** di posta elettronica ai membri del gruppo **TenantAdmins** (**Global Admins**) sull'attività di posta elettronica in uscita inusuale e sugli utenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="11ce8-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="11ce8-146">Per ulteriori informazioni, vedere [verificare le impostazioni degli avvisi per gli utenti con restrizioni](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="11ce8-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="11ce8-147">È consigliabile utilizzare questi criteri di avviso anziché le opzioni di notifica nei criteri di posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="11ce8-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="11ce8-148">Utilizzare il Centro sicurezza & conformità per creare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="11ce8-149">La creazione di un criterio di posta indesiderata in uscita personalizzato nel centro sicurezza & conformità crea la regola del filtro posta indesiderata e i criteri di filtro della posta indesiderata associati allo stesso tempo utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="11ce8-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="11ce8-150">Nel centro sicurezza & conformità, accedere a **criteri** \> di **gestione** \> della protezione da **posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="11ce8-151">Nella pagina impostazioni di protezione da **posta indesiderata** fare clic su **Crea un criterio in uscita**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="11ce8-152">Nel criterio di filtro per la **posta indesiderata in uscita** che si apre, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="11ce8-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="11ce8-153">**Nome**: immettere un nome descrittivo univoco per il criterio.</span><span class="sxs-lookup"><span data-stu-id="11ce8-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="11ce8-154">**Descrizione**: immettere una descrizione facoltativa per il criterio.</span><span class="sxs-lookup"><span data-stu-id="11ce8-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="11ce8-155">Optional Espandere la sezione **notifiche** per configurare altri utenti che devono ricevere le copie e le notifiche dei messaggi di posta elettronica in uscita sospetti:</span><span class="sxs-lookup"><span data-stu-id="11ce8-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="11ce8-156">**Inviare una copia dei messaggi di posta elettronica in uscita sospetti a persone specifiche**: questa impostazione consente di aggiungere gli utenti specificati come destinatari Ccn ai messaggi in uscita sospetti.</span><span class="sxs-lookup"><span data-stu-id="11ce8-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span> <span data-ttu-id="11ce8-157">Per abilitare questa impostazione:</span><span class="sxs-lookup"><span data-stu-id="11ce8-157">To enable this setting:</span></span>

     <span data-ttu-id="11ce8-158">a.</span><span class="sxs-lookup"><span data-stu-id="11ce8-158">a.</span></span> <span data-ttu-id="11ce8-159">Selezionare la casella di controllo per abilitare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="11ce8-159">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="11ce8-160">b.</span><span class="sxs-lookup"><span data-stu-id="11ce8-160">b.</span></span> <span data-ttu-id="11ce8-161">Fare clic su **Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-161">Click **Add people**.</span></span> <span data-ttu-id="11ce8-162">Nel riquadro a comparsa **Aggiungi o Rimuovi destinatari** visualizzato:</span><span class="sxs-lookup"><span data-stu-id="11ce8-162">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="11ce8-163">c.</span><span class="sxs-lookup"><span data-stu-id="11ce8-163">c.</span></span> <span data-ttu-id="11ce8-164">Immettere l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="11ce8-164">Enter the sender's email address.</span></span> <span data-ttu-id="11ce8-165">È possibile specificare più indirizzi di posta elettronica separati da punti e virgola (;) o un destinatario per riga.</span><span class="sxs-lookup"><span data-stu-id="11ce8-165">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="11ce8-166">d.</span><span class="sxs-lookup"><span data-stu-id="11ce8-166">d.</span></span> <span data-ttu-id="11ce8-167">Fare clic su</span><span class="sxs-lookup"><span data-stu-id="11ce8-167">Click</span></span> ![Icona Aggiungi](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="11ce8-169">per aggiungere i destinatari.</span><span class="sxs-lookup"><span data-stu-id="11ce8-169">to add the recipients.</span></span>

        <span data-ttu-id="11ce8-170">Ripetere questi passaggi tutte le volte che è necessario.</span><span class="sxs-lookup"><span data-stu-id="11ce8-170">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="11ce8-171">I destinatari aggiunti vengono visualizzati nella sezione **elenco dei destinatari** sul riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="11ce8-171">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="11ce8-172">Per eliminare un destinatario, fare ![clic su](../../media/scc-remove-icon.png)Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="11ce8-172">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="11ce8-173">e.</span><span class="sxs-lookup"><span data-stu-id="11ce8-173">e.</span></span> <span data-ttu-id="11ce8-174">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-174">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="11ce8-175">Per disabilitare questa impostazione, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="11ce8-175">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="11ce8-176">**Notifica a determinate persone se un mittente è bloccato a causa dell'invio di posta indesiderata in uscita**:</span><span class="sxs-lookup"><span data-stu-id="11ce8-176">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="11ce8-177">Il [criterio di avviso](../../compliance/alert-policies.md) predefinito denominato utente con **restrizioni dall'invio di messaggi di posta** elettronica Invia già notifiche tramite posta elettronica ai membri del gruppo **TenantAdmins** (**Global Admins**) quando gli utenti vengono bloccati a causa del superamento dei limiti nella sezione **limiti dei destinatari** .</span><span class="sxs-lookup"><span data-stu-id="11ce8-177">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="11ce8-178">È consigliabile utilizzare il criterio di avviso anziché questa impostazione nel criterio di posta indesiderata in uscita per inviare una notifica agli amministratori e ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="11ce8-178">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="11ce8-179">Per istruzioni, vedere [verificare le impostazioni degli avvisi per gli utenti con restrizioni](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="11ce8-179">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

     <span data-ttu-id="11ce8-180">Per abilitare questa impostazione:</span><span class="sxs-lookup"><span data-stu-id="11ce8-180">To enable this setting:</span></span>

     <span data-ttu-id="11ce8-181">a.</span><span class="sxs-lookup"><span data-stu-id="11ce8-181">a.</span></span> <span data-ttu-id="11ce8-182">Selezionare la casella di controllo per abilitare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="11ce8-182">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="11ce8-183">b.</span><span class="sxs-lookup"><span data-stu-id="11ce8-183">b.</span></span> <span data-ttu-id="11ce8-184">Fare clic su **Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-184">Click **Add people**.</span></span> <span data-ttu-id="11ce8-185">Nel riquadro a comparsa **Aggiungi o Rimuovi destinatari** visualizzato:</span><span class="sxs-lookup"><span data-stu-id="11ce8-185">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="11ce8-186">c.</span><span class="sxs-lookup"><span data-stu-id="11ce8-186">c.</span></span> <span data-ttu-id="11ce8-187">Immettere l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="11ce8-187">Enter the sender's email address.</span></span> <span data-ttu-id="11ce8-188">È possibile specificare più indirizzi di posta elettronica separati da punti e virgola (;) o un destinatario per riga.</span><span class="sxs-lookup"><span data-stu-id="11ce8-188">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="11ce8-189">d.</span><span class="sxs-lookup"><span data-stu-id="11ce8-189">d.</span></span> <span data-ttu-id="11ce8-190">Fare clic su</span><span class="sxs-lookup"><span data-stu-id="11ce8-190">Click</span></span> ![Icona Aggiungi](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="11ce8-192">per aggiungere i destinatari.</span><span class="sxs-lookup"><span data-stu-id="11ce8-192">to add the recipients.</span></span>

        <span data-ttu-id="11ce8-193">Ripetere questi passaggi tutte le volte che è necessario.</span><span class="sxs-lookup"><span data-stu-id="11ce8-193">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="11ce8-194">I destinatari aggiunti vengono visualizzati nella sezione **elenco dei destinatari** sul riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="11ce8-194">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="11ce8-195">Per eliminare un destinatario, fare ![clic su](../../media/scc-remove-icon.png)Rimuovi.</span><span class="sxs-lookup"><span data-stu-id="11ce8-195">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="11ce8-196">e.</span><span class="sxs-lookup"><span data-stu-id="11ce8-196">e.</span></span> <span data-ttu-id="11ce8-197">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-197">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="11ce8-198">Per disabilitare questa impostazione, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="11ce8-198">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="11ce8-199">Optional Espandere la sezione **limiti dei destinatari** per configurare i limiti e le azioni per i messaggi di posta elettronica in uscita sospetti:]</span><span class="sxs-lookup"><span data-stu-id="11ce8-199">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages: ]</span></span>
   - <span data-ttu-id="11ce8-200">**Numero massimo di destinatari per utente**</span><span class="sxs-lookup"><span data-stu-id="11ce8-200">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="11ce8-201">Un valore valido è compreso tra 0 e 10000.</span><span class="sxs-lookup"><span data-stu-id="11ce8-201">A valid value is 0 to 10000.</span></span> <span data-ttu-id="11ce8-202">Il valore predefinito è 0, il che significa che vengono utilizzati i valori predefiniti del servizio.</span><span class="sxs-lookup"><span data-stu-id="11ce8-202">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="11ce8-203">Per ulteriori informazioni, vedere [invio di limiti tra le opzioni di Office 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="11ce8-203">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="11ce8-204">**Limite orario esterno**: numero massimo di destinatari esterni all'ora.</span><span class="sxs-lookup"><span data-stu-id="11ce8-204">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="11ce8-205">**Limite orario interno**: numero massimo di destinatari interni all'ora.</span><span class="sxs-lookup"><span data-stu-id="11ce8-205">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="11ce8-206">**Limite giornaliero**: numero totale massimo di destinatari al giorno.</span><span class="sxs-lookup"><span data-stu-id="11ce8-206">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="11ce8-207">**Azione quando un utente supera i limiti sopra riportati**: configurare l'azione da eseguire quando si supera il **limite** di uno dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="11ce8-207">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="11ce8-208">Per tutte le azioni, i destinatari specificati nell' **utente hanno limitazioni dall'invio** dei criteri di avviso per la posta elettronica (e nell'ora ridondante **avvisano persone specifiche se un mittente è bloccato a causa** dell'impostazione della posta indesiderata in uscita nel criterio di posta indesiderata in uscita per ricevere notifiche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="11ce8-208">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="11ce8-209">**Impedire all'utente di inviare messaggi di posta elettronica fino al giorno seguente**: questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="11ce8-209">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="11ce8-210">Le notifiche di posta elettronica vengono inviate e l'utente non sarà in grado di inviare altri messaggi fino al giorno seguente, in base all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="11ce8-210">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="11ce8-211">Non è possibile che l'amministratore esegua l'override di questo blocco.</span><span class="sxs-lookup"><span data-stu-id="11ce8-211">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="11ce8-212">L'avviso attività denominato **utente con restrizioni dall'invio di messaggi di posta elettronica** informa gli amministratori (tramite posta elettronica e nella pagina **Visualizza avvisi** ).</span><span class="sxs-lookup"><span data-stu-id="11ce8-212">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="11ce8-213">Tutti i destinatari specificati nella **notifica di persone specifiche se un mittente è bloccato a causa dell'impostazione della posta indesiderata in uscita** nel criterio sono anche notificati.</span><span class="sxs-lookup"><span data-stu-id="11ce8-213">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="11ce8-214">L'utente non sarà in grado di inviare altri messaggi fino al giorno seguente, in base all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="11ce8-214">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="11ce8-215">Non è possibile che l'amministratore esegua l'override di questo blocco.</span><span class="sxs-lookup"><span data-stu-id="11ce8-215">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="11ce8-216">**Impedire all'utente di inviare posta**elettronica: vengono inviate notifiche tramite posta elettronica, l'utente viene aggiunto al portale **[<https://sip.protection.office.com/restrictedusers> utenti con restrizioni]** nel centro sicurezza & compliance e l'utente non può inviare messaggi di posta elettronica fino a quando non viene rimosso dal portale **degli utenti con restrizioni** da parte di un amministratore. Dopo che un amministratore ha rimosso l'utente dall'elenco, l'utente non sarà più limitato per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="11ce8-216">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="11ce8-217">Per istruzioni, vedere [rimozione di un utente dal portale degli utenti con restrizioni dopo l'invio di posta indesiderata](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="11ce8-217">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="11ce8-218">**Nessuna azione, solo avviso**: le notifiche di posta elettronica vengono inviate.</span><span class="sxs-lookup"><span data-stu-id="11ce8-218">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="11ce8-219">Necessari Espandere la sezione **applicato a** per identificare i mittenti interni ai quali si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="11ce8-219">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="11ce8-220">È possibile utilizzare una sola condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="11ce8-220">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="11ce8-221">Più valori della stessa condizione o utilizzo o logica dell'eccezione (ad esempio, _ \<sender1\> _ o _ \<sender2\>_).</span><span class="sxs-lookup"><span data-stu-id="11ce8-221">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="11ce8-222">Utilizzo e logica di diverse condizioni o eccezioni (ad esempio _ \<,\> sender1_ e _ \<membro del gruppo\>1_).</span><span class="sxs-lookup"><span data-stu-id="11ce8-222">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="11ce8-223">È più semplice fare clic su **Aggiungi una condizione** tre volte per visualizzare tutte le condizioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="11ce8-223">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="11ce8-224">È possibile fare ![clic su](../../media/scc-remove-icon.png) Rimuovi per rimuovere le condizioni che non si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="11ce8-224">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="11ce8-225">**Il dominio del mittente è**: specifica i mittenti in uno o più dei domini accettati configurati in Office 365.</span><span class="sxs-lookup"><span data-stu-id="11ce8-225">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in Office 365.</span></span> <span data-ttu-id="11ce8-226">Fare clic nella casella **Aggiungi un tag** per visualizzare e selezionare un dominio.</span><span class="sxs-lookup"><span data-stu-id="11ce8-226">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="11ce8-227">Fare di nuovo clic sulla casella **Aggiungi tag** per selezionare domini aggiuntivi se sono disponibili più domini.</span><span class="sxs-lookup"><span data-stu-id="11ce8-227">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="11ce8-228">**Sender è**: consente di specificare uno o più utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="11ce8-228">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="11ce8-229">Fare clic sul pulsante **Aggiungi un tag** e iniziare a digitare per filtrare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="11ce8-229">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="11ce8-230">Fare di nuovo clic sulla casella **Aggiungi tag** per selezionare mittenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="11ce8-230">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="11ce8-231">**Sender è un membro di**: consente di specificare uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="11ce8-231">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="11ce8-232">Fare clic sul pulsante **Aggiungi un tag** e iniziare a digitare per filtrare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="11ce8-232">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="11ce8-233">Fare di nuovo clic sulla casella **Aggiungi tag** per selezionare mittenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="11ce8-233">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="11ce8-234">**Eccetto se**: per aggiungere eccezioni per la regola, fare clic su **Aggiungi una condizione** tre volte per visualizzare tutte le eccezioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="11ce8-234">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="11ce8-235">Le impostazioni e il comportamento sono esattamente come le condizioni.</span><span class="sxs-lookup"><span data-stu-id="11ce8-235">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="11ce8-236">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-236">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="11ce8-237">Utilizzare il Centro sicurezza & conformità per visualizzare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-237">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="11ce8-238">Nel centro sicurezza & conformità, accedere a **criteri** \> di **gestione** \> della protezione da **posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="11ce8-239">Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic ![su Espandi icona](../../media/scc-expand-icon.png) per espandere un criterio di posta indesiderata in uscita:</span><span class="sxs-lookup"><span data-stu-id="11ce8-239">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="11ce8-240">Criterio predefinito denominato **criteri di filtro della posta indesiderata in uscita**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-240">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="11ce8-241">Un criterio personalizzato creato in cui il valore nella colonna **tipo** è criterio di **posta indesiderata in uscita personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-241">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="11ce8-242">Le impostazioni dei criteri vengono visualizzate nei dettagli dei criteri espansi visualizzati oppure è possibile fare clic su **modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-242">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="11ce8-243">Utilizzare il Centro sicurezza & conformità per modificare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-243">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="11ce8-244">Nel centro sicurezza & conformità, accedere a **criteri** \> di **gestione** \> della protezione da **posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="11ce8-245">Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic ![su Espandi icona](../../media/scc-expand-icon.png) per espandere un criterio di posta indesiderata in uscita:</span><span class="sxs-lookup"><span data-stu-id="11ce8-245">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="11ce8-246">Criterio predefinito denominato **criteri di filtro della posta indesiderata in uscita**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-246">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="11ce8-247">Un criterio personalizzato creato in cui il valore nella colonna **tipo** è criterio di **posta indesiderata in uscita personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-247">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="11ce8-248">Fare clic su **modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-248">Click **Edit policy**.</span></span>

<span data-ttu-id="11ce8-249">Per i criteri di posta indesiderata personalizzati in uscita, le impostazioni disponibili nel riquadro a comparsa visualizzato sono identiche a quelle descritte in [use the Security & Compliance Center to create Outbound spam Policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span><span class="sxs-lookup"><span data-stu-id="11ce8-249">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="11ce8-250">Per il criterio di protezione da posta indesiderata in uscita predefinito denominato **criterio di filtro posta**indesiderata in uscita, la sezione **applicato a** non è disponibile (il criterio si applica a tutti) e non è possibile rinominare il criterio.</span><span class="sxs-lookup"><span data-stu-id="11ce8-250">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="11ce8-251">Per abilitare o disabilitare un criterio, impostare l'ordine di priorità dei criteri o configurare le notifiche per la quarantena dell'utente finale, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="11ce8-251">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="11ce8-252">Abilitare o disabilitare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-252">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="11ce8-253">Nel centro sicurezza & conformità, accedere a **criteri** \> di **gestione** \> della protezione da **posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="11ce8-254">Nella pagina impostazioni di protezione da **posta indesiderata** ![,](../../media/scc-expand-icon.png) fare clic su Espandi icona per espandere un criterio personalizzato creato (il valore nella colonna **tipo** è **Custom criterio di posta indesiderata in uscita**).</span><span class="sxs-lookup"><span data-stu-id="11ce8-254">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="11ce8-255">Nei dettagli del criterio espanso visualizzati, notare il valore nella colonna **su** .</span><span class="sxs-lookup"><span data-stu-id="11ce8-255">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="11ce8-256">Spostare l'interruttore verso sinistra per disabilitare il criterio:</span><span class="sxs-lookup"><span data-stu-id="11ce8-256">Move the toggle to the left to disable the policy:</span></span> ![Disattiva](../../media/scc-toggle-off.png)

   <span data-ttu-id="11ce8-258">Spostare l'interruttore verso destra per abilitare il criterio:</span><span class="sxs-lookup"><span data-stu-id="11ce8-258">Move the toggle to the right to enable the policy:</span></span> ![Attivazione/disattivazione](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="11ce8-260">Non è possibile disabilitare il criterio di posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="11ce8-260">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="11ce8-261">Impostare la priorità dei criteri di posta indesiderata in uscita personalizzati</span><span class="sxs-lookup"><span data-stu-id="11ce8-261">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="11ce8-262">Per impostazione predefinita, ai criteri di posta indesiderata in uscita viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (le nuove politiche hanno priorità più basse rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="11ce8-262">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="11ce8-263">Un numero di priorità inferiore indica una priorità più alta per il criterio (0 è il valore più alto) e i criteri vengono elaborati in ordine di priorità (i criteri con priorità più alta vengono elaborati prima di criteri di priorità più bassi).</span><span class="sxs-lookup"><span data-stu-id="11ce8-263">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="11ce8-264">Due criteri non possono avere priorità uguale.</span><span class="sxs-lookup"><span data-stu-id="11ce8-264">No two policies can have the same priority.</span></span>

<span data-ttu-id="11ce8-265">I criteri di posta indesiderata in uscita personalizzati vengono visualizzati nell'ordine in cui sono stati elaborati (il primo criterio ha il valore di **priorità** 0).</span><span class="sxs-lookup"><span data-stu-id="11ce8-265">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="11ce8-266">Il criterio di posta indesiderata in uscita predefinito denominato **criterio di filtro posta indesiderata in uscita** ha il valore di priorità **più basso**e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="11ce8-266">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="11ce8-267">Per modificare la priorità di un criterio, spostare il criterio verso l'alto o verso il basso nell'elenco (non è possibile modificare direttamente il numero di **priorità** nel centro sicurezza & conformità).</span><span class="sxs-lookup"><span data-stu-id="11ce8-267">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="11ce8-268">Nel centro sicurezza & conformità, accedere a **criteri** \> di **gestione** \> della protezione da **posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-268">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="11ce8-269">Nella pagina impostazioni di protezione da **posta indesiderata** individuare i criteri in cui il valore nella colonna **tipo** è **criteri di posta indesiderata personalizzati in uscita**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-269">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="11ce8-270">Si notino i valori nella colonna **Priority** :</span><span class="sxs-lookup"><span data-stu-id="11ce8-270">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="11ce8-271">Il criterio di posta indesiderata in uscita personalizzato con la priorità ![più alta ha](../../media/ITPro-EAC-DownArrowIcon.png) il valore freccia giù (icona **0**).</span><span class="sxs-lookup"><span data-stu-id="11ce8-271">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="11ce8-272">Il criterio di posta indesiderata in uscita personalizzato con la priorità ![più bassa ha](../../media/ITPro-EAC-UpArrowIcon.png) il valore icona freccia su ![ **n** (ad](../../media/ITPro-EAC-UpArrowIcon.png) esempio, icona freccia su **3**).</span><span class="sxs-lookup"><span data-stu-id="11ce8-272">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="11ce8-273">Se si dispone di tre o più criteri di posta indesiderata in uscita personalizzati, i criteri tra la priorità ![più alta e](../../media/ITPro-EAC-UpArrowIcon.png)![quella più bassa](../../media/ITPro-EAC-DownArrowIcon.png) sono valori su icona freccia ![giù icona **n** (ad esempio](../../media/ITPro-EAC-DownArrowIcon.png) freccia](../../media/ITPro-EAC-UpArrowIcon.png)![giù icona freccia giù **2**).</span><span class="sxs-lookup"><span data-stu-id="11ce8-273">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="11ce8-274">Fare clic su</span><span class="sxs-lookup"><span data-stu-id="11ce8-274">Click</span></span> ![Icona freccia su](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="11ce8-276">oppure</span><span class="sxs-lookup"><span data-stu-id="11ce8-276">or</span></span> ![Icona freccia giù](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="11ce8-278">per spostare il criterio della posta indesiderata in uscita personalizzato verso l'alto o verso il basso nell'elenco priorità.</span><span class="sxs-lookup"><span data-stu-id="11ce8-278">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="11ce8-279">Utilizzare il Centro sicurezza & conformità per rimuovere i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-279">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="11ce8-280">Nel centro sicurezza & conformità, accedere a **criteri** \> di **gestione** \> della protezione da **posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-280">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="11ce8-281">Nella pagina impostazioni di protezione da **posta indesiderata** ![,](../../media/scc-expand-icon.png) fare clic su Espandi icona per espandere il criterio personalizzato che si desidera eliminare (la colonna **tipo** è un **criterio di posta indesiderata in uscita personalizzato**).</span><span class="sxs-lookup"><span data-stu-id="11ce8-281">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="11ce8-282">Nei dettagli del criterio espanso visualizzati fare clic su **Elimina criteri**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-282">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="11ce8-283">Fare clic su **Sì** nella finestra di dialogo di avviso visualizzata.</span><span class="sxs-lookup"><span data-stu-id="11ce8-283">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="11ce8-284">Non è possibile rimuovere il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="11ce8-284">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="11ce8-285">Utilizzare PowerShell di Exchange Online o Exchange Online Protection PowerShell per configurare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-285">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="11ce8-286">Utilizzo di PowerShell per creare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-286">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="11ce8-287">La creazione di un criterio di posta indesiderata in uscita in PowerShell è un processo in due fasi:</span><span class="sxs-lookup"><span data-stu-id="11ce8-287">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="11ce8-288">Creare il criterio di filtro per la posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="11ce8-288">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="11ce8-289">Creare la regola di filtro posta indesiderata in uscita che specifica il criterio di filtro della posta indesiderata in uscita a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="11ce8-289">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="11ce8-290">**Note**:</span><span class="sxs-lookup"><span data-stu-id="11ce8-290">**Notes**:</span></span>

- <span data-ttu-id="11ce8-291">È possibile creare una nuova regola di filtro per la posta indesiderata in uscita e assegnare un criterio di filtro per la posta indesiderata in uscita non associato.</span><span class="sxs-lookup"><span data-stu-id="11ce8-291">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="11ce8-292">Una regola di filtro per la posta indesiderata in uscita non può essere associata a più criteri di filtro posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="11ce8-292">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="11ce8-293">È possibile configurare le seguenti impostazioni nei nuovi criteri di filtro per la posta indesiderata in uscita in PowerShell che non sono disponibili nel centro sicurezza & conformità fino a dopo la creazione del criterio:</span><span class="sxs-lookup"><span data-stu-id="11ce8-293">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="11ce8-294">Creare il nuovo criterio come disabilitato (_attivato_ `$false` nel cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="11ce8-294">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="11ce8-295">Impostare la priorità dei criteri durante la creazione (_Priority_ _ \<numero\>_ di priorità) nel cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="11ce8-295">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="11ce8-296">Un nuovo criterio di filtro per la posta indesiderata in uscita creato in PowerShell non è visibile nel centro sicurezza & conformità fino a quando non si assegna il criterio a una regola di filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="11ce8-296">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="11ce8-297">Passaggio 1: utilizzare PowerShell per creare un criterio di filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-297">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="11ce8-298">Per creare un criterio di filtro per la posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-298">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="11ce8-299">In questo esempio viene creato un nuovo criterio di filtro per la posta indesiderata in uscita denominato contoso Executives con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="11ce8-299">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="11ce8-300">I limiti di frequenza dei destinatari sono limitati a valori inferiori a quelli predefiniti.</span><span class="sxs-lookup"><span data-stu-id="11ce8-300">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="11ce8-301">Per ulteriori informazioni, vedere [invio di limiti tra le opzioni di Office 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="11ce8-301">For more information, see [Sending limits across Office 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="11ce8-302">Dopo che è stato raggiunto uno dei limiti, all'utente viene impedito l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="11ce8-302">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="11ce8-303">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="11ce8-303">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="11ce8-304">Passaggio 2: utilizzare PowerShell per creare una regola di filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-304">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="11ce8-305">Per creare una regola di filtro per la posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-305">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="11ce8-306">In questo esempio viene creata una nuova regola di filtro per la posta indesiderata in uscita denominata Contoso Executives con queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="11ce8-306">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="11ce8-307">Il criterio di filtro per la posta indesiderata in uscita denominato contoso Executives è associato alla regola.</span><span class="sxs-lookup"><span data-stu-id="11ce8-307">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="11ce8-308">La regola si applica ai membri del gruppo denominato contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="11ce8-308">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="11ce8-309">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="11ce8-309">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="11ce8-310">Utilizzo di PowerShell per visualizzare i criteri di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-310">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="11ce8-311">Per restituire un elenco riepilogativo di tutti i criteri di filtro per la posta indesiderata in uscita, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-311">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="11ce8-312">Per restituire informazioni dettagliate su uno specifico criterio di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-312">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="11ce8-313">In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio di filtro della posta indesiderata in uscita denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="11ce8-313">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="11ce8-314">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="11ce8-314">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="11ce8-315">Utilizzare PowerShell per visualizzare le regole del filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-315">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="11ce8-316">Per visualizzare le regole di filtro per la posta indesiderata in uscita esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-316">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="11ce8-317">Per restituire un elenco riepilogativo di tutte le regole del filtro per la posta indesiderata in uscita, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-317">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="11ce8-318">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="11ce8-318">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="11ce8-319">Per restituire informazioni dettagliate su una regola di filtro della posta indesiderata in uscita specifica, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-319">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="11ce8-320">In questo esempio vengono restituiti tutti i valori delle proprietà per la regola di filtro della posta indesiderata in uscita denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="11ce8-320">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="11ce8-321">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="11ce8-321">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="11ce8-322">Utilizzo di PowerShell per modificare i criteri di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-322">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="11ce8-323">Le stesse impostazioni sono disponibili quando si modifica un criterio di filtro antimalware in PowerShell come quando si crea il criterio come descritto nel [passaggio 1: utilizzare PowerShell per creare una sezione dei criteri di filtro per la posta indesiderata in uscita](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="11ce8-323">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="11ce8-324">**Nota**: non è possibile rinominare un criterio di filtro per la posta indesiderata in uscita (il cmdlet **set-HostedOutboundSpamFilterPolicy** non ha un parametro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="11ce8-324">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="11ce8-325">Quando si rinomina un criterio di posta indesiderata in uscita nel centro sicurezza & conformità, viene rinominata solo la _regola_del filtro per la posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="11ce8-325">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="11ce8-326">Per modificare un criterio di filtro per la posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-326">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="11ce8-327">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="11ce8-327">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="11ce8-328">Utilizzare PowerShell per modificare le regole del filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-328">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="11ce8-329">L'unica impostazione che non è disponibile quando si modifica una regola di filtro per la posta indesiderata in uscita in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="11ce8-329">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="11ce8-330">Per abilitare o disabilitare le regole di filtro per la posta indesiderata in uscita esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="11ce8-330">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="11ce8-331">In caso contrario, non sono disponibili altre impostazioni quando si modifica una regola di filtro posta indesiderata in uscita in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11ce8-331">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="11ce8-332">Le stesse impostazioni sono disponibili quando si crea una regola come descritto nel [passaggio 2: utilizzare PowerShell per creare una regola di filtro di protezione da posta indesiderata in uscita](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="11ce8-332">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="11ce8-333">Per modificare una regola di filtro posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-333">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="11ce8-334">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="11ce8-334">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="11ce8-335">Utilizzo di PowerShell per abilitare o disabilitare le regole di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-335">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="11ce8-336">L'abilitazione o disabilitazione di una regola di filtro per la posta indesiderata in uscita in PowerShell consente di abilitare o disabilitare l'intero criterio di posta indesiderata in uscita (la regola del filtro posta indesiderata in uscita e il criterio filtro posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="11ce8-336">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="11ce8-337">Non è possibile abilitare o disabilitare il criterio di posta indesiderata in uscita predefinito (viene sempre applicato sempre a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="11ce8-337">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="11ce8-338">Per abilitare o disabilitare una regola di filtro per la posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-338">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="11ce8-339">In questo esempio viene disabilitata la regola di filtro posta indesiderata in uscita denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="11ce8-339">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="11ce8-340">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="11ce8-340">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="11ce8-341">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) e [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="11ce8-341">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="11ce8-342">Utilizzo di PowerShell per impostare la priorità delle regole del filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-342">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="11ce8-343">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="11ce8-343">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="11ce8-344">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="11ce8-344">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="11ce8-345">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="11ce8-345">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="11ce8-346">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="11ce8-346">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="11ce8-347">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola in 2, la regola esistente con la priorità 2 viene modificata in priorità 3 e la regola con priorità 3 viene modificata in priorità 4.</span><span class="sxs-lookup"><span data-stu-id="11ce8-347">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="11ce8-348">Per impostare la priorità di una regola di filtro di protezione da posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-348">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="11ce8-p146">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="11ce8-p146">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="11ce8-351">**Note**:</span><span class="sxs-lookup"><span data-stu-id="11ce8-351">**Notes**:</span></span>

- <span data-ttu-id="11ce8-352">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="11ce8-352">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="11ce8-353">I criteri di filtro della posta indesiderata in uscita non dispongono di una regola di filtro di posta indesiderata corrispondente e il valore di priorità immodificabile è sempre **inferiore**.</span><span class="sxs-lookup"><span data-stu-id="11ce8-353">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="11ce8-354">Utilizzo di PowerShell per rimuovere i criteri di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-354">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="11ce8-355">Quando si utilizza PowerShell per rimuovere un criterio di filtro della posta indesiderata in uscita, la regola di filtro posta indesiderata in uscita corrispondente non viene rimossa</span><span class="sxs-lookup"><span data-stu-id="11ce8-355">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="11ce8-356">Per rimuovere un criterio di filtro per la posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-356">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="11ce8-357">In questo esempio viene rimosso il criterio di filtro per la posta indesiderata in uscita denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="11ce8-357">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="11ce8-358">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="11ce8-358">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="11ce8-359">Utilizzo di PowerShell per rimuovere le regole di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-359">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="11ce8-360">Quando si utilizza PowerShell per rimuovere una regola di filtro per la posta indesiderata in uscita, il criterio di filtro posta indesiderata in uscita corrispondente non viene rimosso</span><span class="sxs-lookup"><span data-stu-id="11ce8-360">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="11ce8-361">Per rimuovere una regola di filtro di protezione da posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="11ce8-361">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="11ce8-362">In questo esempio viene rimossa la regola di filtro posta indesiderata in uscita denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="11ce8-362">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="11ce8-363">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="11ce8-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="11ce8-364">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="11ce8-364">For more information</span></span>

[<span data-ttu-id="11ce8-365">Rimozione di un utente dal portale Utenti con restrizioni dopo l'invio di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="11ce8-365">Removing a user from the Restricted Users portal after sending spam email</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[<span data-ttu-id="11ce8-366">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="11ce8-366">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="11ce8-367">Domande frequenti sulla protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="11ce8-367">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
