---
title: Configurare il filtro posta indesiderata in uscita
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
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono ottenere informazioni su come visualizzare, creare, modificare ed eliminare i criteri di posta indesiderata in uscita in Exchange Online Protection (EOP).
ms.openlocfilehash: 6a15e33033643f99fc8aeb51036ddac7beba7b71
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616579"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="17321-103">Configurare il filtro della posta indesiderata in uscita in EOP</span><span class="sxs-lookup"><span data-stu-id="17321-103">Configure outbound spam filtering in EOP</span></span>

<span data-ttu-id="17321-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, i messaggi di posta elettronica in uscita inviati tramite EOP vengono controllati automaticamente per la posta indesiderata e l'attività di invio inusuale.</span><span class="sxs-lookup"><span data-stu-id="17321-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="17321-105">La posta indesiderata in uscita da un utente dell'organizzazione indica in genere un account compromesso.</span><span class="sxs-lookup"><span data-stu-id="17321-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="17321-106">I messaggi in uscita sospetti sono contrassegnati come posta indesiderata (indipendentemente dal livello di probabilità di posta indesiderata o SCL) e vengono instradati attraverso il [pool di recapito ad alto rischio](high-risk-delivery-pool-for-outbound-messages.md) per proteggere la reputazione del servizio, ovvero mantenere i server di posta elettronica di origine di Microsoft 365 fuori dagli elenchi di indirizzi IP bloccati.</span><span class="sxs-lookup"><span data-stu-id="17321-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="17321-107">Gli amministratori ricevono automaticamente una notifica delle attività di posta elettronica in uscita sospette e degli utenti bloccati tramite [criteri di avviso](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="17321-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="17321-108">EOP utilizza i criteri di posta indesiderata in uscita come parte della difesa complessiva dell'organizzazione contro la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="17321-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="17321-109">Per altre informazioni, vedere [Protezione dalla posta indesiderata](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="17321-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="17321-110">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio di posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="17321-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="17321-111">Per una maggiore granularità, è anche possibile creare criteri di posta indesiderata in uscita personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="17321-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="17321-112">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).</span><span class="sxs-lookup"><span data-stu-id="17321-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="17321-113">È possibile configurare i criteri di posta indesiderata in uscita nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="17321-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="outbound-spam-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="17321-114">Criteri di posta indesiderata in uscita nel centro sicurezza & Compliance vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="17321-114">Outbound spam policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="17321-115">Gli elementi di base di un criterio di posta indesiderata in uscita in EOP sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="17321-115">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="17321-116">**Criterio di filtro per la posta indesiderata in uscita**: consente di specificare le azioni per i verdetti del filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-116">**The outbound spam filter policy**: Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>

- <span data-ttu-id="17321-117">**Regola del filtro per la posta indesiderata in uscita**: consente di specificare i filtri priorità e destinatario (a chi si applica il criterio) per un criterio di filtro posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="17321-117">**The outbound spam filter rule**: Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="17321-118">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri di posta indesiderata in uscita nel centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="17321-118">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="17321-119">Quando si crea un criterio di posta indesiderata in uscita nel centro sicurezza & Compliance, si sta effettivamente creando una regola di filtro per la posta indesiderata in uscita e il criterio di filtro per la posta indesiderata in uscita associato contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="17321-119">When you create an outbound spam policy in the Security & Compliance Center, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="17321-120">Quando si modifica un criterio di posta indesiderata in uscita nel centro sicurezza & conformità, le impostazioni relative ai filtri nome, priorità, abilitato o disabilitato e destinatario modificano la regola del filtro per la posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="17321-120">When you modify an outbound spam policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="17321-121">Tutte le altre impostazioni modificano i criteri di filtro della posta indesiderata in uscita associati.</span><span class="sxs-lookup"><span data-stu-id="17321-121">All other settings modify the associated outbound spam filter policy.</span></span>

- <span data-ttu-id="17321-122">Quando si rimuove un criterio di posta indesiderata in uscita dal centro sicurezza & conformità, la regola di filtro posta indesiderata in uscita e i criteri di filtro della posta indesiderata in uscita associati vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="17321-122">When you remove an outbound spam policy from the Security & Compliance Center, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="17321-123">In Exchange Online PowerShell o standalone EOP PowerShell, la differenza tra i criteri di filtro della posta indesiderata in uscita e le regole del filtro per la posta indesiderata è evidente.</span><span class="sxs-lookup"><span data-stu-id="17321-123">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="17321-124">È possibile gestire i criteri di filtro della posta indesiderata in uscita utilizzando i cmdlet \*\* \* -HostedOutboundSpamFilterPolicy\*\* e gestire le regole del filtro per la posta indesiderata in uscita utilizzando i cmdlet \*\* \* -HostedOutboundSpamFilterRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="17321-124">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="17321-125">In PowerShell, creare innanzitutto il criterio di filtro per la posta indesiderata in uscita, quindi creare la regola di filtro posta indesiderata in uscita che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="17321-125">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="17321-126">In PowerShell, è possibile modificare le impostazioni nel criterio di filtro della posta indesiderata in uscita e la regola di filtro posta indesiderata in uscita separatamente.</span><span class="sxs-lookup"><span data-stu-id="17321-126">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>

- <span data-ttu-id="17321-127">Quando si rimuove un criterio di filtro per la posta indesiderata in uscita da PowerShell, la regola di filtro posta indesiderata in uscita corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="17321-127">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-outbound-spam-policy"></a><span data-ttu-id="17321-128">Criterio di posta indesiderata in uscita predefinito</span><span class="sxs-lookup"><span data-stu-id="17321-128">Default outbound spam policy</span></span>

<span data-ttu-id="17321-129">Ogni organizzazione dispone di un criterio di posta indesiderata in uscita incorporato denominato default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="17321-129">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="17321-130">Il criterio di filtro per la posta indesiderata in uscita denominato default viene applicato a tutti i destinatari dell'organizzazione, anche se non esiste una regola di filtro per la posta indesiderata in uscita (filtri destinatario) associata al criterio.</span><span class="sxs-lookup"><span data-stu-id="17321-130">The outbound spam filter policy named Default is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="17321-131">Il valore personalizzato della priorità del criterio denominato Predefinito è **Lowest** e non può essere modificato (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="17321-131">The policy named Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="17321-132">Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta rispetto al criterio denominato Predefinito.</span><span class="sxs-lookup"><span data-stu-id="17321-132">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>

- <span data-ttu-id="17321-133">Il criterio denominato Predefinito è il criterio predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="17321-133">The policy named Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="17321-134">Per aumentare l'efficacia del filtro per la posta indesiderata in uscita, è possibile creare criteri di posta indesiderata in uscita personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="17321-134">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="17321-135">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="17321-135">What do you need to know before you begin?</span></span>

- <span data-ttu-id="17321-136">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="17321-136">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="17321-137">Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata**, usare <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="17321-137">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="17321-138">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="17321-138">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="17321-139">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="17321-139">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="17321-140">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="17321-140">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="17321-141">Per aggiungere, modificare ed eliminare i criteri di posta indesiderata in uscita, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="17321-141">To add, modify, and delete outbound spam policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="17321-142">Per l'accesso in sola lettura ai criteri di posta indesiderata in uscita, è necessario essere membri del gruppo di ruoli **lettore di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="17321-142">For read-only access to outbound spam policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="17321-143">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="17321-143">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="17321-144">Per le impostazioni consigliate per i criteri di protezione da posta indesiderata in uscita, vedere [EOP in uscita Spam Policy Filter Settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="17321-144">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="17321-145">I [criteri di avviso](../../compliance/alert-policies.md) predefiniti denominati limite di invio di posta elettronica sono stati **superati**, sono stati **rilevati modelli di invio di messaggi**di posta elettronica sospetti e non è stato possibile inviare **messaggi** di posta elettronica ai membri del gruppo **TenantAdmins** (**Global Admins**) sull'attività di posta elettronica in uscita inusuale e sugli utenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="17321-145">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded**, **Suspicious email sending patterns detected**, and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** (**Global admins**) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="17321-146">Per ulteriori informazioni, vedere [verificare le impostazioni degli avvisi per gli utenti con restrizioni](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="17321-146">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="17321-147">È consigliabile utilizzare questi criteri di avviso anziché le opzioni di notifica nei criteri di posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="17321-147">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="17321-148">Utilizzare il Centro sicurezza & conformità per creare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-148">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="17321-149">La creazione di un criterio di posta indesiderata in uscita personalizzato nel centro sicurezza & conformità crea la regola del filtro posta indesiderata e i criteri di filtro della posta indesiderata associati allo stesso tempo utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="17321-149">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="17321-150">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="17321-150">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="17321-151">Nella pagina impostazioni di protezione da **posta indesiderata** fare clic su **Crea un criterio in uscita**.</span><span class="sxs-lookup"><span data-stu-id="17321-151">On the **Anti-spam settings** page, click **Create an outbound policy**.</span></span>

3. <span data-ttu-id="17321-152">Nel criterio di filtro per la **posta indesiderata in uscita** che si apre, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="17321-152">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="17321-153">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="17321-153">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="17321-154">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="17321-154">**Description**: Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="17321-155">Optional Espandere la sezione **notifiche** per configurare altri utenti che devono ricevere le copie e le notifiche dei messaggi di posta elettronica in uscita sospetti:</span><span class="sxs-lookup"><span data-stu-id="17321-155">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="17321-156">**Inviare una copia dei messaggi di posta elettronica in uscita sospetti a persone specifiche**: questa impostazione consente di aggiungere gli utenti specificati come destinatari Ccn ai messaggi in uscita sospetti.</span><span class="sxs-lookup"><span data-stu-id="17321-156">**Send a copy of suspicious outbound email messages to specific people**: This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="17321-157">Questa impostazione è compatibile solo con il criterio di posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="17321-157">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="17321-158">Non è possibile utilizzare i criteri di posta indesiderata in uscita personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="17321-158">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="17321-159">Per abilitare questa impostazione:</span><span class="sxs-lookup"><span data-stu-id="17321-159">To enable this setting:</span></span>

     <span data-ttu-id="17321-160">a.</span><span class="sxs-lookup"><span data-stu-id="17321-160">a.</span></span> <span data-ttu-id="17321-161">Selezionare la casella di controllo per abilitare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="17321-161">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="17321-162">b.</span><span class="sxs-lookup"><span data-stu-id="17321-162">b.</span></span> <span data-ttu-id="17321-163">Fare clic su **Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="17321-163">Click **Add people**.</span></span> <span data-ttu-id="17321-164">Nel riquadro a comparsa **Aggiungi o Rimuovi destinatari** visualizzato:</span><span class="sxs-lookup"><span data-stu-id="17321-164">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="17321-165">c.</span><span class="sxs-lookup"><span data-stu-id="17321-165">c.</span></span> <span data-ttu-id="17321-166">Immettere l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="17321-166">Enter the sender's email address.</span></span> <span data-ttu-id="17321-167">È possibile specificare più indirizzi di posta elettronica separati da punti e virgola (;) o un destinatario per riga.</span><span class="sxs-lookup"><span data-stu-id="17321-167">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="17321-168">d.</span><span class="sxs-lookup"><span data-stu-id="17321-168">d.</span></span> <span data-ttu-id="17321-169">Scegliere</span><span class="sxs-lookup"><span data-stu-id="17321-169">Click</span></span> ![Icona Aggiungi](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="17321-171">per aggiungere i destinatari.</span><span class="sxs-lookup"><span data-stu-id="17321-171">to add the recipients.</span></span>

        <span data-ttu-id="17321-172">Ripetere questi passaggi tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="17321-172">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="17321-173">I destinatari aggiunti vengono visualizzati nella sezione **elenco dei destinatari** sul riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="17321-173">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="17321-174">Per eliminare un destinatario, fare clic su ![ Rimuovi ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="17321-174">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="17321-175">e.</span><span class="sxs-lookup"><span data-stu-id="17321-175">e.</span></span> <span data-ttu-id="17321-176">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="17321-176">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="17321-177">Per disabilitare questa impostazione, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="17321-177">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="17321-178">**Notifica a determinate persone se un mittente è bloccato a causa dell'invio di posta indesiderata in uscita**:</span><span class="sxs-lookup"><span data-stu-id="17321-178">**Notify specific people if a sender is blocked due to sending outbound spam**:</span></span>

     > [!NOTE]
     > <span data-ttu-id="17321-179">Il [criterio di avviso](../../compliance/alert-policies.md) predefinito denominato utente con **restrizioni dall'invio di messaggi di posta** elettronica Invia già notifiche tramite posta elettronica ai membri del gruppo **TenantAdmins** (**Global Admins**) quando gli utenti vengono bloccati a causa del superamento dei limiti nella sezione **limiti dei destinatari** .</span><span class="sxs-lookup"><span data-stu-id="17321-179">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** (**Global admins**) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="17321-180">È consigliabile utilizzare il criterio di avviso anziché questa impostazione nel criterio di posta indesiderata in uscita per inviare una notifica agli amministratori e ad altri utenti.</span><span class="sxs-lookup"><span data-stu-id="17321-180">We recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users.</span></span> <span data-ttu-id="17321-181">Per istruzioni, vedere [verificare le impostazioni degli avvisi per gli utenti con restrizioni](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="17321-181">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <br/><br/> <span data-ttu-id="17321-182">Questa impostazione è compatibile solo con il criterio di posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="17321-182">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="17321-183">Non è possibile utilizzare i criteri di posta indesiderata in uscita personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="17321-183">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="17321-184">Per abilitare questa impostazione:</span><span class="sxs-lookup"><span data-stu-id="17321-184">To enable this setting:</span></span>

     <span data-ttu-id="17321-185">a.</span><span class="sxs-lookup"><span data-stu-id="17321-185">a.</span></span> <span data-ttu-id="17321-186">Selezionare la casella di controllo per abilitare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="17321-186">Select the check box to enable the setting.</span></span>

     <span data-ttu-id="17321-187">b.</span><span class="sxs-lookup"><span data-stu-id="17321-187">b.</span></span> <span data-ttu-id="17321-188">Fare clic su **Aggiungi utenti**.</span><span class="sxs-lookup"><span data-stu-id="17321-188">Click **Add people**.</span></span> <span data-ttu-id="17321-189">Nel riquadro a comparsa **Aggiungi o Rimuovi destinatari** visualizzato:</span><span class="sxs-lookup"><span data-stu-id="17321-189">In the **Add or remove recipients** flyout that appears:</span></span>

     <span data-ttu-id="17321-190">c.</span><span class="sxs-lookup"><span data-stu-id="17321-190">c.</span></span> <span data-ttu-id="17321-191">Immettere l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="17321-191">Enter the sender's email address.</span></span> <span data-ttu-id="17321-192">È possibile specificare più indirizzi di posta elettronica separati da punti e virgola (;) o un destinatario per riga.</span><span class="sxs-lookup"><span data-stu-id="17321-192">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     <span data-ttu-id="17321-193">d.</span><span class="sxs-lookup"><span data-stu-id="17321-193">d.</span></span> <span data-ttu-id="17321-194">Scegliere</span><span class="sxs-lookup"><span data-stu-id="17321-194">Click</span></span> ![Icona Aggiungi](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="17321-196">per aggiungere i destinatari.</span><span class="sxs-lookup"><span data-stu-id="17321-196">to add the recipients.</span></span>

        <span data-ttu-id="17321-197">Ripetere questi passaggi tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="17321-197">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="17321-198">I destinatari aggiunti vengono visualizzati nella sezione **elenco dei destinatari** sul riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="17321-198">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="17321-199">Per eliminare un destinatario, fare clic su ![ Rimuovi ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="17321-199">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     <span data-ttu-id="17321-200">e.</span><span class="sxs-lookup"><span data-stu-id="17321-200">e.</span></span> <span data-ttu-id="17321-201">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="17321-201">When you're finished, click **Save**.</span></span>

     <span data-ttu-id="17321-202">Per disabilitare questa impostazione, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="17321-202">To disable this setting, clear the check box.</span></span>

5. <span data-ttu-id="17321-203">Optional Espandere la sezione **limiti dei destinatari** per configurare i limiti e le azioni per i messaggi di posta elettronica in uscita sospetti:</span><span class="sxs-lookup"><span data-stu-id="17321-203">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="17321-204">Queste impostazioni sono valide solo per le cassette postali basate sul cloud.</span><span class="sxs-lookup"><span data-stu-id="17321-204">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="17321-205">**Numero massimo di destinatari per utente**</span><span class="sxs-lookup"><span data-stu-id="17321-205">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="17321-206">Un valore valido è compreso tra 0 e 10000.</span><span class="sxs-lookup"><span data-stu-id="17321-206">A valid value is 0 to 10000.</span></span> <span data-ttu-id="17321-207">Il valore predefinito è 0, il che significa che vengono utilizzati i valori predefiniti del servizio.</span><span class="sxs-lookup"><span data-stu-id="17321-207">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="17321-208">Per ulteriori informazioni, vedere [invio di limiti tra le opzioni di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="17321-208">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

     - <span data-ttu-id="17321-209">**Limite orario esterno**: numero massimo di destinatari esterni all'ora.</span><span class="sxs-lookup"><span data-stu-id="17321-209">**External hourly limit**: The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="17321-210">**Limite orario interno**: numero massimo di destinatari interni all'ora.</span><span class="sxs-lookup"><span data-stu-id="17321-210">**Internal hourly limit**: The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="17321-211">**Limite giornaliero**: numero totale massimo di destinatari al giorno.</span><span class="sxs-lookup"><span data-stu-id="17321-211">**Daily limit**: The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="17321-212">**Azione quando un utente supera i limiti sopra riportati**: configurare l'azione da eseguire quando si supera il **limite** di uno dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="17321-212">**Action when a user exceeds the limits above**: Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="17321-213">Per tutte le azioni, i destinatari specificati nell' **utente hanno limitazioni dall'invio** dei criteri di avviso per la posta elettronica (e nell'ora ridondante **avvisano persone specifiche se un mittente è bloccato a causa** dell'impostazione della posta indesiderata in uscita nel criterio di posta indesiderata in uscita per ricevere notifiche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="17321-213">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="17321-214">**Impedire all'utente di inviare messaggi di posta elettronica fino al giorno seguente**: questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="17321-214">**Restrict the user from sending mail till the following day**: This is the default value.</span></span> <span data-ttu-id="17321-215">Le notifiche di posta elettronica vengono inviate e l'utente non sarà in grado di inviare altri messaggi fino al giorno seguente, in base all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="17321-215">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="17321-216">Non è possibile che l'amministratore esegua l'override di questo blocco.</span><span class="sxs-lookup"><span data-stu-id="17321-216">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="17321-217">L'avviso attività denominato **utente con restrizioni dall'invio di messaggi di posta elettronica** informa gli amministratori (tramite posta elettronica e nella pagina **Visualizza avvisi** ).</span><span class="sxs-lookup"><span data-stu-id="17321-217">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="17321-218">Tutti i destinatari specificati nella **notifica di persone specifiche se un mittente è bloccato a causa dell'impostazione della posta indesiderata in uscita** nel criterio sono anche notificati.</span><span class="sxs-lookup"><span data-stu-id="17321-218">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="17321-219">L'utente non sarà in grado di inviare altri messaggi fino al giorno seguente, in base all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="17321-219">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="17321-220">Non è possibile che l'amministratore esegua l'override di questo blocco.</span><span class="sxs-lookup"><span data-stu-id="17321-220">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="17321-221">**Impedire all'utente di inviare posta**elettronica: vengono inviate notifiche tramite posta elettronica, l'utente viene aggiunto al portale **[ <https://sip.protection.office.com/restrictedusers> utenti con restrizioni]** nel centro sicurezza & compliance e l'utente non può inviare messaggi di posta elettronica fino a quando non viene rimosso dal portale **degli utenti con restrizioni** da parte di un amministratore. Dopo che un amministratore ha rimosso l'utente dall'elenco, l'utente non sarà più limitato per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="17321-221">**Restrict the user from sending mail**: Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="17321-222">Per istruzioni, vedere [rimozione di un utente dal portale degli utenti con restrizioni dopo l'invio di posta indesiderata](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="17321-222">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="17321-223">**Nessuna azione, solo avviso**: le notifiche di posta elettronica vengono inviate.</span><span class="sxs-lookup"><span data-stu-id="17321-223">**No action, alert only**: Email notifications are sent.</span></span>

6. <span data-ttu-id="17321-224">Necessari Espandere la sezione **applicato a** per identificare i mittenti interni ai quali si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="17321-224">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="17321-225">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="17321-225">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="17321-226">Più valori della stessa condizione o utilizzo o logica dell'eccezione (ad esempio, _\<sender1\>_ o _\<sender2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="17321-226">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_).</span></span> <span data-ttu-id="17321-227">Utilizzo e logica di diverse condizioni o eccezioni (ad esempio, _\<sender1\>_ e _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="17321-227">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_).</span></span>

    <span data-ttu-id="17321-228">È più facile fare clic su **Aggiungi una condizione** tre volte per visualizzare tutte le condizioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="17321-228">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="17321-229">È possibile fare clic su ![Pulsante Rimuovi](../../media/scc-remove-icon.png) per rimuovere le condizioni che non si vogliono configurare.</span><span class="sxs-lookup"><span data-stu-id="17321-229">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="17321-230">**Il dominio del mittente è**: specifica i mittenti in uno o più dei domini accettati configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="17321-230">**The sender domain is**: Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="17321-231">Fare clic sulla casella **Aggiungi un tag** per visualizzare e selezionare un dominio.</span><span class="sxs-lookup"><span data-stu-id="17321-231">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="17321-232">Fare nuovamente clic sulla casella **Aggiungi un tag** per selezionare altri domini se è disponibile più di un dominio.</span><span class="sxs-lookup"><span data-stu-id="17321-232">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="17321-233">**Sender è**: consente di specificare uno o più utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="17321-233">**Sender is**: Specifies one or more users in your organization.</span></span> <span data-ttu-id="17321-234">Fare clic su **Aggiungi un tag** e iniziare a digitare per filtrare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="17321-234">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="17321-235">Fare di nuovo clic sulla casella **Aggiungi tag** per selezionare mittenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="17321-235">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="17321-236">**Sender è un membro di**: consente di specificare uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="17321-236">**Sender is a member of**: Specifies one or more groups in your organization.</span></span> <span data-ttu-id="17321-237">Fare clic su **Aggiungi un tag** e iniziare a digitare per filtrare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="17321-237">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="17321-238">Fare di nuovo clic sulla casella **Aggiungi tag** per selezionare mittenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="17321-238">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="17321-239">**Tranne quando**: per aggiungere eccezioni alla regola, fare clic su **Aggiungi una condizione** tre volte per visualizzare tutte le eccezioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="17321-239">**Except if**: To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="17321-240">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="17321-240">The settings and behavior are exactly like the conditions.</span></span>

7. <span data-ttu-id="17321-241">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="17321-241">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="17321-242">Utilizzare il Centro sicurezza & conformità per visualizzare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-242">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="17321-243">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="17321-243">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="17321-244">Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere un criterio di posta indesiderata in uscita:</span><span class="sxs-lookup"><span data-stu-id="17321-244">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="17321-245">Criterio predefinito denominato **criteri di filtro della posta indesiderata in uscita**.</span><span class="sxs-lookup"><span data-stu-id="17321-245">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="17321-246">Un criterio personalizzato creato in cui il valore nella colonna **tipo** è criterio di **posta indesiderata in uscita personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="17321-246">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="17321-247">Le impostazioni dei criteri vengono visualizzate nei dettagli dei criteri espansi visualizzati oppure è possibile fare clic su **modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="17321-247">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="17321-248">Utilizzare il Centro sicurezza & conformità per modificare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-248">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="17321-249">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="17321-249">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="17321-250">Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere un criterio di posta indesiderata in uscita:</span><span class="sxs-lookup"><span data-stu-id="17321-250">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="17321-251">Criterio predefinito denominato **criteri di filtro della posta indesiderata in uscita**.</span><span class="sxs-lookup"><span data-stu-id="17321-251">The default policy named **Outbound spam filter policy**.</span></span>

   - <span data-ttu-id="17321-252">Un criterio personalizzato creato in cui il valore nella colonna **tipo** è criterio di **posta indesiderata in uscita personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="17321-252">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy**.</span></span>

3. <span data-ttu-id="17321-253">Fare clic su **Modifica criterio**.</span><span class="sxs-lookup"><span data-stu-id="17321-253">Click **Edit policy**.</span></span>

<span data-ttu-id="17321-254">Per i criteri di posta indesiderata personalizzati in uscita, le impostazioni disponibili nel riquadro a comparsa visualizzato sono identiche a quelle descritte in [use the Security & Compliance Center to create Outbound spam Policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span><span class="sxs-lookup"><span data-stu-id="17321-254">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="17321-255">Per il criterio di protezione da posta indesiderata in uscita predefinito denominato **criterio di filtro posta**indesiderata in uscita, la sezione **applicato a** non è disponibile (il criterio si applica a tutti) e non è possibile rinominare il criterio.</span><span class="sxs-lookup"><span data-stu-id="17321-255">For the default outbound spam policy named **Outbound spam filter policy**, the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="17321-256">Per abilitare o disabilitare un criterio, impostare l'ordine di priorità dei criteri o configurare le notifiche di quarantena per gli utenti finali. Vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="17321-256">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="17321-257">Abilitare o disabilitare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-257">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="17321-258">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="17321-258">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="17321-259">Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere un criterio personalizzato creato (il valore nella colonna **tipo** è **Custom criterio di posta indesiderata in uscita**).</span><span class="sxs-lookup"><span data-stu-id="17321-259">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="17321-260">Nei dettagli dei criteri espansi visualizzati, notare il valore nella colonna **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="17321-260">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="17321-261">Spostare l'interruttore a sinistra per disabilitare il criterio:</span><span class="sxs-lookup"><span data-stu-id="17321-261">Move the toggle to the left to disable the policy:</span></span> ![Disattiva](../../media/scc-toggle-off.png)

   <span data-ttu-id="17321-263">Spostare l'interruttore a destra per abilitare il criterio:</span><span class="sxs-lookup"><span data-stu-id="17321-263">Move the toggle to the right to enable the policy:</span></span> ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="17321-265">Non è possibile disabilitare il criterio di posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="17321-265">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="17321-266">Impostare la priorità dei criteri di posta indesiderata in uscita personalizzati</span><span class="sxs-lookup"><span data-stu-id="17321-266">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="17321-267">Per impostazione predefinita, ai criteri di posta indesiderata in uscita viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (le nuove politiche hanno priorità più basse rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="17321-267">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="17321-268">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="17321-268">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="17321-269">Due criteri non possono avere priorità uguale.</span><span class="sxs-lookup"><span data-stu-id="17321-269">No two policies can have the same priority.</span></span>

<span data-ttu-id="17321-270">I criteri di posta indesiderata in uscita personalizzati vengono visualizzati nell'ordine in cui sono stati elaborati (il primo criterio ha il valore di **priorità** 0).</span><span class="sxs-lookup"><span data-stu-id="17321-270">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="17321-271">Il criterio di posta indesiderata in uscita predefinito denominato **criterio di filtro posta indesiderata in uscita** ha il valore di priorità **più basso**e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="17321-271">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest**, and you can't change it.</span></span>

<span data-ttu-id="17321-272">Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).</span><span class="sxs-lookup"><span data-stu-id="17321-272">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="17321-273">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="17321-273">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="17321-274">Nella pagina impostazioni di protezione da **posta indesiderata** individuare i criteri in cui il valore nella colonna **tipo** è **criteri di posta indesiderata personalizzati in uscita**.</span><span class="sxs-lookup"><span data-stu-id="17321-274">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy**.</span></span> <span data-ttu-id="17321-275">Notare i valori nella colonna **Priorità**:</span><span class="sxs-lookup"><span data-stu-id="17321-275">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="17321-276">Il criterio di posta indesiderata in uscita personalizzato con la priorità più alta ha il valore ![ freccia giù (icona ](../../media/ITPro-EAC-DownArrowIcon.png) **0**).</span><span class="sxs-lookup"><span data-stu-id="17321-276">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0**.</span></span>

   - <span data-ttu-id="17321-277">Il criterio di posta indesiderata in uscita personalizzato con la priorità più bassa ha il valore ![ icona freccia su ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (ad esempio, ![ icona freccia su ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span><span class="sxs-lookup"><span data-stu-id="17321-277">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3**).</span></span>

   - <span data-ttu-id="17321-278">Se si dispone di tre o più criteri di posta indesiderata in uscita personalizzati, i criteri tra la priorità più alta e quella più bassa sono valori su icona freccia ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ giù icona ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (ad esempio freccia ![ giù icona ](../../media/ITPro-EAC-UpArrowIcon.png)![ freccia giù ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span><span class="sxs-lookup"><span data-stu-id="17321-278">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2**).</span></span>

3. <span data-ttu-id="17321-279">Fare clic su</span><span class="sxs-lookup"><span data-stu-id="17321-279">Click</span></span> ![Icona Freccia SU](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="17321-281">oppure</span><span class="sxs-lookup"><span data-stu-id="17321-281">or</span></span> ![Icona Freccia GIÙ](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="17321-283">per spostare il criterio della posta indesiderata in uscita personalizzato verso l'alto o verso il basso nell'elenco priorità.</span><span class="sxs-lookup"><span data-stu-id="17321-283">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="17321-284">Utilizzare il Centro sicurezza & conformità per rimuovere i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-284">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="17321-285">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="17321-285">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="17321-286">Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere il criterio personalizzato che si desidera eliminare (la colonna **tipo** è un **criterio di posta indesiderata in uscita personalizzato**).</span><span class="sxs-lookup"><span data-stu-id="17321-286">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy**).</span></span>

3. <span data-ttu-id="17321-287">Nei dettagli sui criteri espansi visualizzati, fare clic su **Elimina criterio**.</span><span class="sxs-lookup"><span data-stu-id="17321-287">In the expanded policy details that appear, click **Delete policy**.</span></span>

4. <span data-ttu-id="17321-288">Fare clic su **Sì** quando viene visualizzata la finestra di dialogo di avviso.</span><span class="sxs-lookup"><span data-stu-id="17321-288">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="17321-289">Non è possibile rimuovere il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="17321-289">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="17321-290">Utilizzo di PowerShell di Exchange Online o standalone EOP PowerShell per configurare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="17321-291">Utilizzo di PowerShell per creare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-291">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="17321-292">La creazione di un criterio di posta indesiderata in uscita in PowerShell è un processo in due fasi:</span><span class="sxs-lookup"><span data-stu-id="17321-292">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="17321-293">Creare il criterio di filtro per la posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="17321-293">Create the outbound spam filter policy.</span></span>

2. <span data-ttu-id="17321-294">Creare la regola di filtro posta indesiderata in uscita che specifica il criterio di filtro della posta indesiderata in uscita a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="17321-294">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="17321-295">**Note**:</span><span class="sxs-lookup"><span data-stu-id="17321-295">**Notes**:</span></span>

- <span data-ttu-id="17321-296">È possibile creare una nuova regola di filtro per la posta indesiderata in uscita e assegnare un criterio di filtro per la posta indesiderata in uscita non associato.</span><span class="sxs-lookup"><span data-stu-id="17321-296">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="17321-297">Una regola di filtro per la posta indesiderata in uscita non può essere associata a più criteri di filtro posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="17321-297">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="17321-298">È possibile configurare le seguenti impostazioni nei nuovi criteri di filtro per la posta indesiderata in uscita in PowerShell che non sono disponibili nel centro sicurezza & conformità fino a dopo la creazione del criterio:</span><span class="sxs-lookup"><span data-stu-id="17321-298">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="17321-299">Creare il nuovo criterio come disabilitato (_attivato_ `$false` nel cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="17321-299">Create the new policy as disabled (_Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

  - <span data-ttu-id="17321-300">Impostare la priorità del criterio durante la creazione (_priorità_ _\<Number\>_ ) del cmdlet **New-HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="17321-300">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="17321-301">Un nuovo criterio di filtro per la posta indesiderata in uscita creato in PowerShell non è visibile nel centro sicurezza & conformità fino a quando non si assegna il criterio a una regola di filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="17321-301">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="17321-302">Passaggio 1: utilizzare PowerShell per creare un criterio di filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-302">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="17321-303">Per creare un criterio di filtro per la posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-303">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="17321-304">In questo esempio viene creato un nuovo criterio di filtro per la posta indesiderata in uscita denominato contoso Executives con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="17321-304">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="17321-305">I limiti di frequenza dei destinatari sono limitati a valori inferiori a quelli predefiniti.</span><span class="sxs-lookup"><span data-stu-id="17321-305">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="17321-306">Per ulteriori informazioni, vedere [invio di limiti tra le opzioni di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="17321-306">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="17321-307">Dopo che è stato raggiunto uno dei limiti, all'utente viene impedito l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="17321-307">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="17321-308">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="17321-308">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="17321-309">Passaggio 2: utilizzare PowerShell per creare una regola di filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-309">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="17321-310">Per creare una regola di filtro per la posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-310">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="17321-311">In questo esempio viene creata una nuova regola di filtro per la posta indesiderata in uscita denominata Contoso Executives con queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="17321-311">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="17321-312">Il criterio di filtro per la posta indesiderata in uscita denominato contoso Executives è associato alla regola.</span><span class="sxs-lookup"><span data-stu-id="17321-312">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="17321-313">La regola viene applicata ai membri del gruppo Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="17321-313">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="17321-314">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="17321-314">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="17321-315">Utilizzo di PowerShell per visualizzare i criteri di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-315">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="17321-316">Per restituire un elenco riepilogativo di tutti i criteri di filtro per la posta indesiderata in uscita, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-316">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="17321-317">Per restituire informazioni dettagliate su uno specifico criterio di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-317">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="17321-318">In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio di filtro della posta indesiderata in uscita denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="17321-318">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="17321-319">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="17321-319">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="17321-320">Utilizzare PowerShell per visualizzare le regole del filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-320">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="17321-321">Per visualizzare le regole di filtro per la posta indesiderata in uscita esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-321">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

<span data-ttu-id="17321-322">Per restituire un elenco riepilogativo di tutte le regole del filtro per la posta indesiderata in uscita, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-322">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="17321-323">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="17321-323">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="17321-324">Per restituire informazioni dettagliate su una regola di filtro della posta indesiderata in uscita specifica, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-324">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="17321-325">In questo esempio vengono restituiti tutti i valori delle proprietà per la regola di filtro della posta indesiderata in uscita denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="17321-325">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="17321-326">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="17321-326">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="17321-327">Utilizzo di PowerShell per modificare i criteri di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-327">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="17321-328">Le stesse impostazioni sono disponibili quando si modifica un criterio di filtro antimalware in PowerShell come quando si crea il criterio come descritto nel [passaggio 1: utilizzare PowerShell per creare una sezione dei criteri di filtro per la posta indesiderata in uscita](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="17321-328">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

<span data-ttu-id="17321-329">**Nota**: non è possibile rinominare un criterio di filtro per la posta indesiderata in uscita (il cmdlet **set-HostedOutboundSpamFilterPolicy** non ha un parametro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="17321-329">**Note**: You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="17321-330">Quando si rinomina un criterio di posta indesiderata in uscita nel centro sicurezza & conformità, viene rinominata solo la _regola_del filtro per la posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="17321-330">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_.</span></span>

<span data-ttu-id="17321-331">Per modificare un criterio di filtro per la posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-331">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="17321-332">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="17321-332">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="17321-333">Utilizzare PowerShell per modificare le regole del filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-333">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="17321-334">L'unica impostazione che non è disponibile quando si modifica una regola di filtro per la posta indesiderata in uscita in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="17321-334">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="17321-335">Per abilitare o disabilitare le regole di filtro per la posta indesiderata in uscita esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="17321-335">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="17321-336">In caso contrario, non sono disponibili altre impostazioni quando si modifica una regola di filtro posta indesiderata in uscita in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17321-336">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="17321-337">Le stesse impostazioni sono disponibili quando si crea una regola come descritto nel [passaggio 2: utilizzare PowerShell per creare una regola di filtro di protezione da posta indesiderata in uscita](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="17321-337">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="17321-338">Per modificare una regola di filtro posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-338">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="17321-339">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="17321-339">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="17321-340">Utilizzo di PowerShell per abilitare o disabilitare le regole di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-340">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="17321-341">L'abilitazione o disabilitazione di una regola di filtro per la posta indesiderata in uscita in PowerShell consente di abilitare o disabilitare l'intero criterio di posta indesiderata in uscita (la regola del filtro posta indesiderata in uscita e il criterio filtro posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="17321-341">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="17321-342">Non è possibile abilitare o disabilitare il criterio di posta indesiderata in uscita predefinito (viene sempre applicato sempre a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="17321-342">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="17321-343">Per abilitare o disabilitare una regola di filtro per la posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-343">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="17321-344">In questo esempio viene disabilitata la regola di filtro posta indesiderata in uscita denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="17321-344">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="17321-345">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="17321-345">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="17321-346">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) e [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="17321-346">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="17321-347">Utilizzo di PowerShell per impostare la priorità delle regole del filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-347">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="17321-348">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="17321-348">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="17321-349">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="17321-349">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="17321-350">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="17321-350">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="17321-351">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="17321-351">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="17321-352">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="17321-352">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="17321-353">Per impostare la priorità di una regola di filtro di protezione da posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-353">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="17321-p147">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="17321-p147">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="17321-356">**Note**:</span><span class="sxs-lookup"><span data-stu-id="17321-356">**Notes**:</span></span>

- <span data-ttu-id="17321-357">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="17321-357">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>

- <span data-ttu-id="17321-358">I criteri di filtro della posta indesiderata in uscita non dispongono di una regola di filtro di posta indesiderata corrispondente e il valore di priorità immodificabile è sempre **inferiore**.</span><span class="sxs-lookup"><span data-stu-id="17321-358">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="17321-359">Utilizzo di PowerShell per rimuovere i criteri di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-359">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="17321-360">Quando si utilizza PowerShell per rimuovere un criterio di filtro della posta indesiderata in uscita, la regola di filtro posta indesiderata in uscita corrispondente non viene rimossa</span><span class="sxs-lookup"><span data-stu-id="17321-360">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="17321-361">Per rimuovere un criterio di filtro per la posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-361">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="17321-362">In questo esempio viene rimosso il criterio di filtro per la posta indesiderata in uscita denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="17321-362">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="17321-363">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="17321-363">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="17321-364">Utilizzo di PowerShell per rimuovere le regole di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-364">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="17321-365">Quando si utilizza PowerShell per rimuovere una regola di filtro per la posta indesiderata in uscita, il criterio di filtro posta indesiderata in uscita corrispondente non viene rimosso</span><span class="sxs-lookup"><span data-stu-id="17321-365">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="17321-366">Per rimuovere una regola di filtro di protezione da posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="17321-366">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="17321-367">In questo esempio viene rimossa la regola di filtro posta indesiderata in uscita denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="17321-367">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="17321-368">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="17321-368">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="17321-369">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="17321-369">For more information</span></span>

[<span data-ttu-id="17321-370">Rimuovere utenti bloccati dal portale Utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="17321-370">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="17321-371">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="17321-371">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="17321-372">Domande frequenti sulla protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="17321-372">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
