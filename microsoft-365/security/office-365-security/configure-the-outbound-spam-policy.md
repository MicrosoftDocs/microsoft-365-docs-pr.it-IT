---
title: Configurare il filtro posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
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
ms.openlocfilehash: 316bdcf4f7beb0af3dd71fdd3c3a2c0198a89f8d
ms.sourcegitcommit: 9d1351ea6d9942550b52132817f9f9693ddef2fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2020
ms.locfileid: "48830650"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a><span data-ttu-id="20f0d-103">Configurare il filtro della posta indesiderata in uscita in EOP</span><span class="sxs-lookup"><span data-stu-id="20f0d-103">Configure outbound spam filtering in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="20f0d-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, i messaggi di posta elettronica in uscita inviati tramite EOP vengono controllati automaticamente per la posta indesiderata e l'attività di invio inusuale.</span><span class="sxs-lookup"><span data-stu-id="20f0d-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, outbound email messages that are sent through EOP are automatically checked for spam and unusual sending activity.</span></span>

<span data-ttu-id="20f0d-105">La posta indesiderata in uscita da un utente dell'organizzazione indica in genere un account compromesso.</span><span class="sxs-lookup"><span data-stu-id="20f0d-105">Outbound spam from a user in your organization typically indicates a compromised account.</span></span> <span data-ttu-id="20f0d-106">I messaggi in uscita sospetti sono contrassegnati come posta indesiderata (indipendentemente dal livello di probabilità di posta indesiderata o SCL) e vengono instradati attraverso il [pool di recapito ad alto rischio](high-risk-delivery-pool-for-outbound-messages.md) per proteggere la reputazione del servizio, ovvero mantenere i server di posta elettronica di origine di Microsoft 365 fuori dagli elenchi di indirizzi IP bloccati.</span><span class="sxs-lookup"><span data-stu-id="20f0d-106">Suspicious outbound messages are marked as spam (regardless of the spam confidence level or SCL) and are routed through the [high-risk delivery pool](high-risk-delivery-pool-for-outbound-messages.md) to help protect the reputation of the service (that is, keep Microsoft 365 source email servers off of IP block lists).</span></span> <span data-ttu-id="20f0d-107">Gli amministratori ricevono automaticamente una notifica delle attività di posta elettronica in uscita sospette e degli utenti bloccati tramite [criteri di avviso](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="20f0d-107">Admins are automatically notified of suspicious outbound email activity and blocked users via [alert policies](../../compliance/alert-policies.md).</span></span>

<span data-ttu-id="20f0d-108">EOP utilizza i criteri di posta indesiderata in uscita come parte della difesa complessiva dell'organizzazione contro la posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="20f0d-108">EOP uses outbound spam policies as part of your organization's overall defense against spam.</span></span> <span data-ttu-id="20f0d-109">Per altre informazioni, vedere [Protezione dalla posta indesiderata](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="20f0d-109">For more information, see [Anti-spam protection](anti-spam-protection.md).</span></span>

<span data-ttu-id="20f0d-110">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio di posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="20f0d-110">Admins can view, edit, and configure (but not delete) the default outbound spam policy.</span></span> <span data-ttu-id="20f0d-111">Per una maggiore granularità, è anche possibile creare criteri di posta indesiderata in uscita personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="20f0d-111">For greater granularity, you can also create custom outbound spam policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="20f0d-112">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).</span><span class="sxs-lookup"><span data-stu-id="20f0d-112">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="20f0d-113">È possibile configurare i criteri di posta indesiderata in uscita nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per Microsoft 365 organizzazioni con cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="20f0d-113">You can configure outbound spam policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

<span data-ttu-id="20f0d-114">Gli elementi di base di un criterio di posta indesiderata in uscita in EOP sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="20f0d-114">The basic elements of an outbound spam policy in EOP are:</span></span>

- <span data-ttu-id="20f0d-115">**Criterio di filtro per la posta indesiderata in uscita** : consente di specificare le azioni per i verdetti del filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-115">**The outbound spam filter policy** : Specifies the actions for outbound spam filtering verdicts and the notification options.</span></span>
- <span data-ttu-id="20f0d-116">**Regola del filtro per la posta indesiderata in uscita** : consente di specificare i filtri priorità e destinatario (a chi si applica il criterio) per un criterio di filtro posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="20f0d-116">**The outbound spam filter rule** : Specifies the priority and recipient filters (who the policy applies to) for a outbound spam filter policy.</span></span>

<span data-ttu-id="20f0d-117">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri di posta indesiderata in uscita nel centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="20f0d-117">The difference between these two elements isn't obvious when you manage outbound spam polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="20f0d-118">Quando si crea un criterio, si sta effettivamente creando una regola di filtro per la posta indesiderata in uscita e il criterio del filtro della posta indesiderata in uscita associato contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="20f0d-118">When you create a policy, you're actually creating a outbound spam filter rule and the associated outbound spam filter policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="20f0d-119">Quando si modifica un criterio, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatario modificano la regola del filtro per la posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="20f0d-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the outbound spam filter rule.</span></span> <span data-ttu-id="20f0d-120">Tutte le altre impostazioni modificano i criteri di filtro della posta indesiderata in uscita associati.</span><span class="sxs-lookup"><span data-stu-id="20f0d-120">All other settings modify the associated outbound spam filter policy.</span></span>
- <span data-ttu-id="20f0d-121">Quando si rimuove un criterio, la regola del filtro per la posta indesiderata in uscita e i criteri di filtro della posta indesiderata associati vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="20f0d-121">When you remove a policy, the outbound spam filter rule and the associated outbound spam filter policy are removed.</span></span>

<span data-ttu-id="20f0d-122">In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="20f0d-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="20f0d-123">Per ulteriori informazioni, vedere la sezione [utilizzare Exchange Online PowerShell o standalone EOP PowerShell per configurare i criteri di posta indesiderata in uscita](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="20f0d-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) section later in this topic.</span></span>

<span data-ttu-id="20f0d-124">Ogni organizzazione dispone di un criterio di posta indesiderata in uscita incorporato denominato default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="20f0d-124">Every organization has a built-in outbound spam policy named Default that has these properties:</span></span>

- <span data-ttu-id="20f0d-125">Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se non esiste una regola di filtro per la posta indesiderata in uscita (filtri destinatario) associata al criterio.</span><span class="sxs-lookup"><span data-stu-id="20f0d-125">The policy is applied to all recipients in the organization, even though there's no outbound spam filter rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="20f0d-126">Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="20f0d-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="20f0d-127">Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta rispetto al criterio denominato Predefinito.</span><span class="sxs-lookup"><span data-stu-id="20f0d-127">Any custom policies that you create always have a higher priority than the policy named Default.</span></span>
- <span data-ttu-id="20f0d-128">Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="20f0d-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="20f0d-129">Per aumentare l'efficacia del filtro per la posta indesiderata in uscita, è possibile creare criteri di posta indesiderata in uscita personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="20f0d-129">To increase the effectiveness of outbound spam filtering, you can create custom outbound spam policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20f0d-130">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="20f0d-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="20f0d-131">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="20f0d-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="20f0d-132">Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata** , usare <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="20f0d-132">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span>

- <span data-ttu-id="20f0d-133">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="20f0d-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="20f0d-134">Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="20f0d-134">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="20f0d-135">È necessario disporre delle autorizzazioni per eseguire le procedure di questo argomento:</span><span class="sxs-lookup"><span data-stu-id="20f0d-135">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="20f0d-136">Per aggiungere, modificare ed eliminare i criteri di posta indesiderata in uscita, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="20f0d-136">To add, modify, and delete outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="20f0d-137">**Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="20f0d-137">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="20f0d-138">**Gestione organizzazione** o **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="20f0d-138">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="20f0d-139">Per l'accesso in sola lettura ai criteri di posta indesiderata in uscita, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="20f0d-139">For read-only access to outbound spam policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="20f0d-140">**Lettore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="20f0d-140">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="20f0d-141">**Gestione organizzazione in sola lettura** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="20f0d-141">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="20f0d-142">Per le impostazioni consigliate per i criteri di protezione da posta indesiderata in uscita, vedere [EOP in uscita Spam Policy Filter Settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="20f0d-142">For our recommended settings for outbound spam policies, see [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).</span></span>

- <span data-ttu-id="20f0d-143">I [criteri di avviso](../../compliance/alert-policies.md) predefiniti denominati limite di invio di posta elettronica sono stati **superati** , sono stati **rilevati modelli di invio di messaggi** di posta elettronica sospetti e non è stato possibile inviare **messaggi** di posta elettronica ai membri del gruppo **TenantAdmins** ( **Global Admins** ) sull'attività di posta elettronica in uscita inusuale e sugli utenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="20f0d-143">The default [alert policies](../../compliance/alert-policies.md) named **Email sending limit exceeded** , **Suspicious email sending patterns detected** , and **User restricted from sending email** already send email notifications to members of the **TenantAdmins** ( **Global admins** ) group about unusual outbound email activity and blocked users due to outbound spam.</span></span> <span data-ttu-id="20f0d-144">Per ulteriori informazioni, vedere [verificare le impostazioni degli avvisi per gli utenti con restrizioni](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="20f0d-144">For more information, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span> <span data-ttu-id="20f0d-145">È consigliabile utilizzare questi criteri di avviso anziché le opzioni di notifica nei criteri di posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="20f0d-145">We recommend that you use these alert policies instead of the the notification options in outbound spam policies.</span></span>

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a><span data-ttu-id="20f0d-146">Utilizzare il Centro sicurezza & conformità per creare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-146">Use the Security & Compliance Center to create outbound spam policies</span></span>

<span data-ttu-id="20f0d-147">La creazione di un criterio di posta indesiderata in uscita personalizzato nel centro sicurezza & conformità crea la regola del filtro posta indesiderata e i criteri di filtro della posta indesiderata associati allo stesso tempo utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="20f0d-147">Creating a custom outbound spam policy in the Security & Compliance Center creates the spam filter rule and the associated spam filter policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="20f0d-148">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-148">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** .</span></span>

2. <span data-ttu-id="20f0d-149">Nella pagina impostazioni di protezione da **posta indesiderata** fare clic su **Crea un criterio in uscita** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-149">On the **Anti-spam settings** page, click **Create an outbound policy** .</span></span>

3. <span data-ttu-id="20f0d-150">Nel criterio di filtro per la **posta indesiderata in uscita** che si apre, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="20f0d-150">In the **Outbound spam filter policy** fly out that opens, configure the following settings:</span></span>

   - <span data-ttu-id="20f0d-151">**Nome** : immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="20f0d-151">**Name** : Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="20f0d-152">**Descrizione** : immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="20f0d-152">**Description** : Enter an optional description for the policy.</span></span>

4. <span data-ttu-id="20f0d-153">Optional Espandere la sezione **notifiche** per configurare altri utenti che devono ricevere le copie e le notifiche dei messaggi di posta elettronica in uscita sospetti:</span><span class="sxs-lookup"><span data-stu-id="20f0d-153">(Optional) Expand the **Notifications** section to configure additional users who should receive copies and notifications of suspicious outbound email messages:</span></span>

   - <span data-ttu-id="20f0d-154">**Inviare una copia dei messaggi di posta elettronica in uscita sospetti a persone specifiche** : questa impostazione consente di aggiungere gli utenti specificati come destinatari Ccn ai messaggi in uscita sospetti.</span><span class="sxs-lookup"><span data-stu-id="20f0d-154">**Send a copy of suspicious outbound email messages to specific people** : This setting adds the specified users as Bcc recipients to the suspicious outbound messages.</span></span>

     > [!NOTE]
     > <span data-ttu-id="20f0d-155">Questa impostazione è compatibile solo con il criterio di posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="20f0d-155">This setting only works in the default outbound spam policy.</span></span> <span data-ttu-id="20f0d-156">Non è possibile utilizzare i criteri di posta indesiderata in uscita personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="20f0d-156">It doesn't work in custom outbound spam policies that you create.</span></span>

     <span data-ttu-id="20f0d-157">Per abilitare questa impostazione:</span><span class="sxs-lookup"><span data-stu-id="20f0d-157">To enable this setting:</span></span>

     1. <span data-ttu-id="20f0d-158">Selezionare la casella di controllo per abilitare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="20f0d-158">Select the check box to enable the setting.</span></span>

     1. <span data-ttu-id="20f0d-159">Fare clic su **Aggiungi utenti** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-159">Click **Add people** .</span></span> <span data-ttu-id="20f0d-160">Nel riquadro a comparsa **Aggiungi o Rimuovi destinatari** visualizzato:</span><span class="sxs-lookup"><span data-stu-id="20f0d-160">In the **Add or remove recipients** flyout that appears:</span></span>

     1. <span data-ttu-id="20f0d-161">Immettere l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="20f0d-161">Enter the sender's email address.</span></span> <span data-ttu-id="20f0d-162">È possibile specificare più indirizzi di posta elettronica separati da punti e virgola (;) o un destinatario per riga.</span><span class="sxs-lookup"><span data-stu-id="20f0d-162">You can specify multiple email addresses separated by semicolons (;) or one recipient per line.</span></span>

     1. <span data-ttu-id="20f0d-163">Scegliere</span><span class="sxs-lookup"><span data-stu-id="20f0d-163">Click</span></span> ![Icona Aggiungi](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) <span data-ttu-id="20f0d-165">per aggiungere i destinatari.</span><span class="sxs-lookup"><span data-stu-id="20f0d-165">to add the recipients.</span></span>

        <span data-ttu-id="20f0d-166">Ripetere questi passaggi tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="20f0d-166">Repeat these steps as many times as necessary.</span></span>

        <span data-ttu-id="20f0d-167">I destinatari aggiunti vengono visualizzati nella sezione **elenco dei destinatari** sul riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="20f0d-167">The recipients you added appear in the **Recipient list** section on the flyout.</span></span> <span data-ttu-id="20f0d-168">Per eliminare un destinatario, fare clic su ![ Rimuovi ](../../media/scc-remove-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="20f0d-168">To delete a recipient, click ![Remove button](../../media/scc-remove-icon.png).</span></span>

     1. <span data-ttu-id="20f0d-169">Al termine, scegliere **Salva** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-169">When you're finished, click **Save** .</span></span>

        <span data-ttu-id="20f0d-170">Per disabilitare questa impostazione, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="20f0d-170">To disable this setting, clear the check box.</span></span>

   - <span data-ttu-id="20f0d-171">**Notifica a determinate persone se un mittente è bloccato a causa dell'invio di posta indesiderata in uscita** :</span><span class="sxs-lookup"><span data-stu-id="20f0d-171">**Notify specific people if a sender is blocked due to sending outbound spam** :</span></span>

     > [!IMPORTANT]
     >
     > - <span data-ttu-id="20f0d-172">Questa impostazione è in fase di divenire obsoleta dai criteri di posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="20f0d-172">This setting is in the process of being deprecated from outbound spam policies.</span></span>
     >
     > - <span data-ttu-id="20f0d-173">Il [criterio di avviso](../../compliance/alert-policies.md) predefinito denominato utente con **restrizioni dall'invio di messaggi di posta** elettronica Invia già notifiche tramite posta elettronica ai membri del gruppo **TenantAdmins** ( **Global Admins** ) quando gli utenti vengono bloccati a causa del superamento dei limiti nella sezione **limiti dei destinatari** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-173">The default [alert policy](../../compliance/alert-policies.md) named **User restricted from sending email** already sends email notifications to members of the **TenantAdmins** ( **Global admins** ) group when users are blocked due to exceeding the limits in the **Recipient Limits** section.</span></span> <span data-ttu-id="20f0d-174">**È consigliabile utilizzare il criterio di avviso anziché questa impostazione nel criterio di posta indesiderata in uscita per inviare una notifica agli amministratori e ad altri utenti** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-174">**We strongly recommend that you use the alert policy rather than this setting in the outbound spam policy to notify admins and other users** .</span></span> <span data-ttu-id="20f0d-175">Per istruzioni, vedere [verificare le impostazioni degli avvisi per gli utenti con restrizioni](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span><span class="sxs-lookup"><span data-stu-id="20f0d-175">For instructions, see [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).</span></span>

5. <span data-ttu-id="20f0d-176">Optional Espandere la sezione **limiti dei destinatari** per configurare i limiti e le azioni per i messaggi di posta elettronica in uscita sospetti:</span><span class="sxs-lookup"><span data-stu-id="20f0d-176">(Optional) Expand the **Recipient Limits** section to configure the limits and actions for suspicious outbound email messages:</span></span>

   > [!NOTE]
   > <span data-ttu-id="20f0d-177">Queste impostazioni sono valide solo per le cassette postali basate sul cloud.</span><span class="sxs-lookup"><span data-stu-id="20f0d-177">These settings are only applicable to cloud-based mailboxes.</span></span>

   - <span data-ttu-id="20f0d-178">**Numero massimo di destinatari per utente**</span><span class="sxs-lookup"><span data-stu-id="20f0d-178">**Maximum number of recipients per user**</span></span>

     <span data-ttu-id="20f0d-179">Un valore valido è compreso tra 0 e 10000.</span><span class="sxs-lookup"><span data-stu-id="20f0d-179">A valid value is 0 to 10000.</span></span> <span data-ttu-id="20f0d-180">Il valore predefinito è 0, il che significa che vengono utilizzati i valori predefiniti del servizio.</span><span class="sxs-lookup"><span data-stu-id="20f0d-180">The default value is 0, which means the service defaults are used.</span></span> <span data-ttu-id="20f0d-181">Per ulteriori informazioni, vedere [invio di limiti](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span><span class="sxs-lookup"><span data-stu-id="20f0d-181">For more information, see [Sending limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).</span></span>

     - <span data-ttu-id="20f0d-182">**Limite orario esterno** : numero massimo di destinatari esterni all'ora.</span><span class="sxs-lookup"><span data-stu-id="20f0d-182">**External hourly limit** : The maximum number of external recipients per hour.</span></span>

     - <span data-ttu-id="20f0d-183">**Limite orario interno** : numero massimo di destinatari interni all'ora.</span><span class="sxs-lookup"><span data-stu-id="20f0d-183">**Internal hourly limit** : The maximum number of internal recipients per hour.</span></span>

     - <span data-ttu-id="20f0d-184">**Limite giornaliero** : numero totale massimo di destinatari al giorno.</span><span class="sxs-lookup"><span data-stu-id="20f0d-184">**Daily limit** : The maximum total number of recipients per day.</span></span>

   - <span data-ttu-id="20f0d-185">**Azione quando un utente supera i limiti sopra riportati** : configurare l'azione da eseguire quando si supera il **limite** di uno dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="20f0d-185">**Action when a user exceeds the limits above** : Configure the action to take when any one of the **Recipient Limits** are exceeded.</span></span> <span data-ttu-id="20f0d-186">Per tutte le azioni, i destinatari specificati nell' **utente hanno limitazioni dall'invio** dei criteri di avviso per la posta elettronica (e nell'ora ridondante **avvisano persone specifiche se un mittente è bloccato a causa** dell'impostazione della posta indesiderata in uscita nel criterio di posta indesiderata in uscita per ricevere notifiche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="20f0d-186">For all actions, the recipients specified in the **User restricted from sending email** alert policy (and in the now redundant **Notify specific people if a sender is blocked due to sending outbound spam** setting in the outbound spam policy receive email notifications.</span></span>

     - <span data-ttu-id="20f0d-187">**Impedire all'utente di inviare messaggi di posta elettronica fino al giorno seguente** : questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="20f0d-187">**Restrict the user from sending mail till the following day** : This is the default value.</span></span> <span data-ttu-id="20f0d-188">Le notifiche di posta elettronica vengono inviate e l'utente non sarà in grado di inviare altri messaggi fino al giorno seguente, in base all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="20f0d-188">Email notifications are sent, and the user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="20f0d-189">Non è possibile che l'amministratore esegua l'override di questo blocco.</span><span class="sxs-lookup"><span data-stu-id="20f0d-189">There is no way for the admin to override this block.</span></span>

       - <span data-ttu-id="20f0d-190">L'avviso attività denominato **utente con restrizioni dall'invio di messaggi di posta elettronica** informa gli amministratori (tramite posta elettronica e nella pagina **Visualizza avvisi** ).</span><span class="sxs-lookup"><span data-stu-id="20f0d-190">The activity alert named **User restricted from sending email** notifies admins (via email and on the **View alerts** page).</span></span>

       - <span data-ttu-id="20f0d-191">Tutti i destinatari specificati nella **notifica di persone specifiche se un mittente è bloccato a causa dell'impostazione della posta indesiderata in uscita** nel criterio sono anche notificati.</span><span class="sxs-lookup"><span data-stu-id="20f0d-191">Any recipients specified in the **Notify specific people if a sender is blocked due to sending outbound spam** setting in the policy are also notified.</span></span>

       - <span data-ttu-id="20f0d-192">L'utente non sarà in grado di inviare altri messaggi fino al giorno seguente, in base all'ora UTC.</span><span class="sxs-lookup"><span data-stu-id="20f0d-192">The user will be unable to send any more messages until the following day, based on UTC time.</span></span> <span data-ttu-id="20f0d-193">Non è possibile che l'amministratore esegua l'override di questo blocco.</span><span class="sxs-lookup"><span data-stu-id="20f0d-193">There is no way for the admin to override this block.</span></span>

     - <span data-ttu-id="20f0d-194">**Impedire all'utente di inviare posta** elettronica: vengono inviate notifiche tramite posta elettronica, l'utente viene aggiunto al portale **[ <https://sip.protection.office.com/restrictedusers> utenti con restrizioni]** nel centro sicurezza & compliance e l'utente non può inviare messaggi di posta elettronica fino a quando non viene rimosso dal portale **degli utenti con restrizioni** da parte di un amministratore. Dopo che un amministratore ha rimosso l'utente dall'elenco, l'utente non sarà più limitato per quel giorno.</span><span class="sxs-lookup"><span data-stu-id="20f0d-194">**Restrict the user from sending mail** : Email notifications are sent, the user is added to the **[Restricted Users]<https://sip.protection.office.com/restrictedusers>** portal in the Security & Compliance Center, and the user can't send email until they're removed from the **Restricted Users** portal by an admin. After an admin removes the user from the list, the user won't be restricted again for that day.</span></span> <span data-ttu-id="20f0d-195">Per istruzioni, vedere [rimozione di un utente dal portale degli utenti con restrizioni dopo l'invio di posta indesiderata](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="20f0d-195">For instructions, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

     - <span data-ttu-id="20f0d-196">**Nessuna azione, solo avviso** : le notifiche di posta elettronica vengono inviate.</span><span class="sxs-lookup"><span data-stu-id="20f0d-196">**No action, alert only** : Email notifications are sent.</span></span>

6. <span data-ttu-id="20f0d-197">Optional Espandere la sezione **inoltro automatico** per controllare l'inoltro automatico di messaggi di posta elettronica da parte degli utenti a mittenti esterni.</span><span class="sxs-lookup"><span data-stu-id="20f0d-197">(Optional) Expand **Automatic forwarding** section to control automatic email forwarding by users to external senders.</span></span> <span data-ttu-id="20f0d-198">Per ulteriori informazioni sull'inoltro automatico, vedere [Configure email forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="20f0d-198">For more information about automatic forwarding, see [Configure email forwarding](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding).</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="20f0d-199">Prima del settembre 2020, queste impostazioni sono disponibili, ma non vengono applicate.</span><span class="sxs-lookup"><span data-stu-id="20f0d-199">Before September 2020, these settings are available but not enforced.</span></span>
   >
   > - <span data-ttu-id="20f0d-200">Queste impostazioni si applicano solo alle cassette postali basate sul cloud.</span><span class="sxs-lookup"><span data-stu-id="20f0d-200">These settings apply only to cloud-based mailboxes.</span></span>
   >
   > - <span data-ttu-id="20f0d-201">Quando l'inoltro automatico è disattivato, il destinatario riceverà un rapporto di mancato recapito (noto anche come NDR o messaggio di rimbalzo) se i mittenti esterni inviano messaggi di posta elettronica a una cassetta postale in cui è in corso l'inoltro.</span><span class="sxs-lookup"><span data-stu-id="20f0d-201">When automatic forwarding is disabled, the recipient will receive a non-delivery report (also known as an NDR or bounce message) if external senders send email to a mailbox that has forwarding in place.</span></span> <span data-ttu-id="20f0d-202">Se il messaggio di posta elettronica viene inviato da un mittente interno, il mittente otterrà il rapporto di mancato recapito.</span><span class="sxs-lookup"><span data-stu-id="20f0d-202">If the email is sent by an internal sender, the sender will get the NDR.</span></span>

   <span data-ttu-id="20f0d-203">I valori disponibili sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="20f0d-203">The available values are:</span></span>

   - <span data-ttu-id="20f0d-204">Controllo **automatico del sistema** : consente il filtro posta indesiderata in uscita per controllare l'inoltro automatico esterno della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="20f0d-204">**Automatic - System-controlled** : Allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="20f0d-205">Questo è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="20f0d-205">This is the default value.</span></span>
   - <span data-ttu-id="20f0d-206">**On** : l'inoltro automatico esterno della posta elettronica non è disabilitato dal criterio.</span><span class="sxs-lookup"><span data-stu-id="20f0d-206">**On** : Automatic external email forwarding is not disabled by the policy.</span></span>
   - <span data-ttu-id="20f0d-207">**Disattivato** : tutti i messaggi di inoltro automatici esterni sono disabilitati dal criterio.</span><span class="sxs-lookup"><span data-stu-id="20f0d-207">**Off** : All automatic external email forwarding is disabled by the policy.</span></span>
 
7. <span data-ttu-id="20f0d-208">Necessari Espandere la sezione **applicato a** per identificare i mittenti interni ai quali si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="20f0d-208">(Required) Expand the **Applied to** section to identify the internal senders that the policy applies to.</span></span>

    <span data-ttu-id="20f0d-209">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="20f0d-209">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="20f0d-210">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<sender1\>_ o _\<sender2\>_ ).</span><span class="sxs-lookup"><span data-stu-id="20f0d-210">Multiple values of the same condition or exception use OR logic (for example, _\<sender1\>_ or _\<sender2\>_ ).</span></span> <span data-ttu-id="20f0d-211">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<sender1\>_ e _\<member of group 1\>_ ).</span><span class="sxs-lookup"><span data-stu-id="20f0d-211">Different conditions or exceptions use AND logic (for example, _\<sender1\>_ and _\<member of group 1\>_ ).</span></span>

    <span data-ttu-id="20f0d-212">È più facile fare clic su **Aggiungi una condizione** tre volte per visualizzare tutte le condizioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="20f0d-212">It's easiest to click **Add a condition** three times to see all of the available conditions.</span></span> <span data-ttu-id="20f0d-213">È possibile fare clic su ![Pulsante Rimuovi](../../media/scc-remove-icon.png) per rimuovere le condizioni che non si vogliono configurare.</span><span class="sxs-lookup"><span data-stu-id="20f0d-213">You can click ![Remove button](../../media/scc-remove-icon.png) to remove conditions that you don't want to configure.</span></span>

    - <span data-ttu-id="20f0d-214">**Il dominio del mittente è** : specifica i mittenti in uno o più dei domini accettati configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="20f0d-214">**The sender domain is** : Specifies senders in one or more of the configured accepted domains in the organization.</span></span> <span data-ttu-id="20f0d-215">Fare clic sulla casella **Aggiungi un tag** per visualizzare e selezionare un dominio.</span><span class="sxs-lookup"><span data-stu-id="20f0d-215">Click in the **Add a tag** box to see and select a domain.</span></span> <span data-ttu-id="20f0d-216">Fare nuovamente clic sulla casella **Aggiungi un tag** per selezionare altri domini se è disponibile più di un dominio.</span><span class="sxs-lookup"><span data-stu-id="20f0d-216">Click again the **Add a tag** box to select additional domains if more than one domain is available.</span></span>

    - <span data-ttu-id="20f0d-217">**Sender è** : consente di specificare uno o più utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="20f0d-217">**Sender is** : Specifies one or more users in your organization.</span></span> <span data-ttu-id="20f0d-218">Fare clic su **Aggiungi un tag** e iniziare a digitare per filtrare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="20f0d-218">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="20f0d-219">Fare di nuovo clic sulla casella **Aggiungi tag** per selezionare mittenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="20f0d-219">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="20f0d-220">**Sender è un membro di** : consente di specificare uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="20f0d-220">**Sender is a member of** : Specifies one or more groups in your organization.</span></span> <span data-ttu-id="20f0d-221">Fare clic su **Aggiungi un tag** e iniziare a digitare per filtrare l'elenco.</span><span class="sxs-lookup"><span data-stu-id="20f0d-221">Click in the **Add a tag** and start typing to filter the list.</span></span> <span data-ttu-id="20f0d-222">Fare di nuovo clic sulla casella **Aggiungi tag** per selezionare mittenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="20f0d-222">Click again the **Add a tag** box to select additional senders.</span></span>

    - <span data-ttu-id="20f0d-223">**Tranne quando** : per aggiungere eccezioni alla regola, fare clic su **Aggiungi una condizione** tre volte per visualizzare tutte le eccezioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="20f0d-223">**Except if** : To add exceptions for the rule, click **Add a condition** three times to see all of the available exceptions.</span></span> <span data-ttu-id="20f0d-224">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="20f0d-224">The settings and behavior are exactly like the conditions.</span></span>

8. <span data-ttu-id="20f0d-225">Al termine, scegliere **Salva** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-225">When you're finished, click **Save** .</span></span>

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a><span data-ttu-id="20f0d-226">Utilizzare il Centro sicurezza & conformità per visualizzare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-226">Use the Security & Compliance Center to view outbound spam policies</span></span>

1. <span data-ttu-id="20f0d-227">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-227">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** .</span></span>

2. <span data-ttu-id="20f0d-228">Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere un criterio di posta indesiderata in uscita:</span><span class="sxs-lookup"><span data-stu-id="20f0d-228">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="20f0d-229">Criterio predefinito denominato **criteri di filtro della posta indesiderata in uscita** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-229">The default policy named **Outbound spam filter policy** .</span></span>

   - <span data-ttu-id="20f0d-230">Un criterio personalizzato creato in cui il valore nella colonna **tipo** è criterio di **posta indesiderata in uscita personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-230">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy** .</span></span>

3. <span data-ttu-id="20f0d-231">Le impostazioni dei criteri vengono visualizzate nei dettagli dei criteri espansi visualizzati oppure è possibile fare clic su **modifica criterio** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-231">The policy settings are displayed in the expanded policy details that appear, or you can click **Edit policy** .</span></span>

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a><span data-ttu-id="20f0d-232">Utilizzare il Centro sicurezza & conformità per modificare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-232">Use the Security & Compliance Center to modify outbound spam policies</span></span>

1. <span data-ttu-id="20f0d-233">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-233">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** .</span></span>

2. <span data-ttu-id="20f0d-234">Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere un criterio di posta indesiderata in uscita:</span><span class="sxs-lookup"><span data-stu-id="20f0d-234">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand an outbound spam policy:</span></span>

   - <span data-ttu-id="20f0d-235">Criterio predefinito denominato **criteri di filtro della posta indesiderata in uscita** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-235">The default policy named **Outbound spam filter policy** .</span></span>

   - <span data-ttu-id="20f0d-236">Un criterio personalizzato creato in cui il valore nella colonna **tipo** è criterio di **posta indesiderata in uscita personalizzato** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-236">A custom policy that you created where the value in the **Type** column is **Custom outbound spam policy** .</span></span>

3. <span data-ttu-id="20f0d-237">Fare clic su **Modifica criterio** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-237">Click **Edit policy** .</span></span>

<span data-ttu-id="20f0d-238">Per i criteri di posta indesiderata personalizzati in uscita, le impostazioni disponibili nel riquadro a comparsa visualizzato sono identiche a quelle descritte in [use the Security & Compliance Center to create Outbound spam Policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span><span class="sxs-lookup"><span data-stu-id="20f0d-238">For custom outbound spam policies, the available settings in the flyout that appears are identical to those described in the [Use the Security & Compliance Center to create outbound spam policies](#use-the-security--compliance-center-to-create-outbound-spam-policies) section.</span></span>

<span data-ttu-id="20f0d-239">Per il criterio di protezione da posta indesiderata in uscita predefinito denominato **criterio di filtro posta** indesiderata in uscita, la sezione **applicato a** non è disponibile (il criterio si applica a tutti) e non è possibile rinominare il criterio.</span><span class="sxs-lookup"><span data-stu-id="20f0d-239">For the default outbound spam policy named **Outbound spam filter policy** , the **Applied to** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="20f0d-240">Per abilitare o disabilitare un criterio, impostare l'ordine di priorità dei criteri o configurare le notifiche di quarantena per gli utenti finali. Vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="20f0d-240">To enable or disable a policy, set the policy priority order, or configure the end-user quarantine notifications, see the following sections.</span></span>

### <a name="enable-or-disable-outbound-spam-policies"></a><span data-ttu-id="20f0d-241">Abilitare o disabilitare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-241">Enable or disable outbound spam policies</span></span>

1. <span data-ttu-id="20f0d-242">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-242">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** .</span></span>

2. <span data-ttu-id="20f0d-243">Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere un criterio personalizzato creato (il valore nella colonna **tipo** è **Custom criterio di posta indesiderata in uscita** ).</span><span class="sxs-lookup"><span data-stu-id="20f0d-243">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand a custom policy that you created (the value in the **Type** column is **Custom outbound spam policy** ).</span></span>

3. <span data-ttu-id="20f0d-244">Nei dettagli dei criteri espansi visualizzati, notare il valore nella colonna **Attivo** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-244">In the expanded policy details that appear, notice the value in the **On** column.</span></span>

   <span data-ttu-id="20f0d-245">Spostare l'interruttore a sinistra per disabilitare il criterio:</span><span class="sxs-lookup"><span data-stu-id="20f0d-245">Move the toggle to the left to disable the policy:</span></span> ![Disattiva](../../media/scc-toggle-off.png)

   <span data-ttu-id="20f0d-247">Spostare l'interruttore a destra per abilitare il criterio:</span><span class="sxs-lookup"><span data-stu-id="20f0d-247">Move the toggle to the right to enable the policy:</span></span> ![Attiva](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

<span data-ttu-id="20f0d-249">Non è possibile disabilitare il criterio di posta indesiderata in uscita predefinito.</span><span class="sxs-lookup"><span data-stu-id="20f0d-249">You can't disable the default outbound spam policy.</span></span>

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a><span data-ttu-id="20f0d-250">Impostare la priorità dei criteri di posta indesiderata in uscita personalizzati</span><span class="sxs-lookup"><span data-stu-id="20f0d-250">Set the priority of custom outbound spam policies</span></span>

<span data-ttu-id="20f0d-251">Per impostazione predefinita, ai criteri di posta indesiderata in uscita viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (le nuove politiche hanno priorità più basse rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="20f0d-251">By default, outbound spam policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="20f0d-252">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="20f0d-252">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="20f0d-253">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="20f0d-253">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="20f0d-254">I criteri di posta indesiderata in uscita personalizzati vengono visualizzati nell'ordine in cui sono stati elaborati (il primo criterio ha il valore di **priorità** 0).</span><span class="sxs-lookup"><span data-stu-id="20f0d-254">Custom outbound spam policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="20f0d-255">Il criterio di posta indesiderata in uscita predefinito denominato **criterio di filtro posta indesiderata in uscita** ha il valore di priorità **più basso** e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="20f0d-255">The default outbound spam policy named **Outbound spam filter policy** has the priority value **Lowest** , and you can't change it.</span></span>

<span data-ttu-id="20f0d-256">Per modificare la priorità di un criterio, spostare il criterio più in alto o più in basso nell'elenco (non è possibile modificare direttamente il numero **Priority** nel Centro sicurezza e conformità).</span><span class="sxs-lookup"><span data-stu-id="20f0d-256">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="20f0d-257">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-257">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** .</span></span>

2. <span data-ttu-id="20f0d-258">Nella pagina impostazioni di protezione da **posta indesiderata** individuare i criteri in cui il valore nella colonna **tipo** è **criteri di posta indesiderata personalizzati in uscita** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-258">On the **Anti-spam settings** page, find the policies where the value in the **Type** column is **Custom outbound spam policy** .</span></span> <span data-ttu-id="20f0d-259">Notare i valori nella colonna **Priorità** :</span><span class="sxs-lookup"><span data-stu-id="20f0d-259">Notice the values in the **Priority** column:</span></span>

   - <span data-ttu-id="20f0d-260">Il criterio di posta indesiderata in uscita personalizzato con la priorità più alta ha il valore ![ freccia giù (icona ](../../media/ITPro-EAC-DownArrowIcon.png) **0** ).</span><span class="sxs-lookup"><span data-stu-id="20f0d-260">The custom outbound spam policy with the highest priority has the value ![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **0** .</span></span>

   - <span data-ttu-id="20f0d-261">Il criterio di posta indesiderata in uscita personalizzato con la priorità più bassa ha il valore ![ icona freccia su ](../../media/ITPro-EAC-UpArrowIcon.png) **n** (ad esempio, ![ icona freccia su ](../../media/ITPro-EAC-UpArrowIcon.png) **3** ).</span><span class="sxs-lookup"><span data-stu-id="20f0d-261">The custom outbound spam policy with the lowest priority has the value ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png) **3** ).</span></span>

   - <span data-ttu-id="20f0d-262">Se si dispone di tre o più criteri di posta indesiderata in uscita personalizzati, i criteri tra la priorità più alta e quella più bassa sono valori su icona freccia ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ giù icona ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (ad esempio freccia ![ giù icona ](../../media/ITPro-EAC-UpArrowIcon.png)![ freccia giù ](../../media/ITPro-EAC-DownArrowIcon.png) **2** ).</span><span class="sxs-lookup"><span data-stu-id="20f0d-262">If you have three or more custom outbound spam policies, the policies between the highest and lowest priority have values ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **n** (for example, ![Up Arrow icon](../../media/ITPro-EAC-UpArrowIcon.png)![Down Arrow icon](../../media/ITPro-EAC-DownArrowIcon.png) **2** ).</span></span>

3. <span data-ttu-id="20f0d-263">Fare clic su</span><span class="sxs-lookup"><span data-stu-id="20f0d-263">Click</span></span> ![Icona Freccia SU](../../media/ITPro-EAC-UpArrowIcon.png) <span data-ttu-id="20f0d-265">oppure</span><span class="sxs-lookup"><span data-stu-id="20f0d-265">or</span></span> ![Icona Freccia GIÙ](../../media/ITPro-EAC-DownArrowIcon.png) <span data-ttu-id="20f0d-267">per spostare il criterio della posta indesiderata in uscita personalizzato verso l'alto o verso il basso nell'elenco priorità.</span><span class="sxs-lookup"><span data-stu-id="20f0d-267">to move the custom outbound spam policy up or down in the priority list.</span></span>

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a><span data-ttu-id="20f0d-268">Utilizzare il Centro sicurezza & conformità per rimuovere i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-268">Use the Security & Compliance Center to remove outbound spam policies</span></span>

1. <span data-ttu-id="20f0d-269">Nel Centro sicurezza e conformità, andare a **Gestione delle minacce** \> **Criteri** \> **Filtro della posta indesiderata** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-269">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** .</span></span>

2. <span data-ttu-id="20f0d-270">Nella pagina impostazioni di protezione da **posta indesiderata** , fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) per espandere il criterio personalizzato che si desidera eliminare (la colonna **tipo** è un **criterio di posta indesiderata in uscita personalizzato** ).</span><span class="sxs-lookup"><span data-stu-id="20f0d-270">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand the custom policy that you want to delete (the **Type** column is **Custom outbound spam policy** ).</span></span>

3. <span data-ttu-id="20f0d-271">Nei dettagli sui criteri espansi visualizzati, fare clic su **Elimina criterio** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-271">In the expanded policy details that appear, click **Delete policy** .</span></span>

4. <span data-ttu-id="20f0d-272">Fare clic su **Sì** quando viene visualizzata la finestra di dialogo di avviso.</span><span class="sxs-lookup"><span data-stu-id="20f0d-272">Click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="20f0d-273">Non è possibile rimuovere il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="20f0d-273">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a><span data-ttu-id="20f0d-274">Utilizzo di PowerShell di Exchange Online o standalone EOP PowerShell per configurare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-274">Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies</span></span>

<span data-ttu-id="20f0d-275">Come descritto in precedenza, un criterio di posta indesiderata in uscita è costituito da un criterio di filtro per la posta indesiderata in uscita e da una regola di filtro</span><span class="sxs-lookup"><span data-stu-id="20f0d-275">As previously described, an outbound spam policy consists of an outbound spam filter policy and an outbound spam filter rule.</span></span>

<span data-ttu-id="20f0d-276">In Exchange Online PowerShell o standalone EOP PowerShell, la differenza tra i criteri di filtro della posta indesiderata in uscita e le regole del filtro per la posta indesiderata è evidente.</span><span class="sxs-lookup"><span data-stu-id="20f0d-276">In Exchange Online PowerShell or standalone EOP PowerShell, the difference between outbound spam filter policies and outbound spam filter rules is apparent.</span></span> <span data-ttu-id="20f0d-277">È possibile gestire i criteri di filtro della posta indesiderata in uscita utilizzando i cmdlet **\* -HostedOutboundSpamFilterPolicy** e gestire le regole del filtro per la posta indesiderata in uscita utilizzando i cmdlet **\* -HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-277">You manage outbound spam filter policies by using the **\*-HostedOutboundSpamFilterPolicy** cmdlets, and you manage outbound spam filter rules by using the **\*-HostedOutboundSpamFilterRule** cmdlets.</span></span>

- <span data-ttu-id="20f0d-278">In PowerShell, creare innanzitutto il criterio di filtro per la posta indesiderata in uscita, quindi creare la regola di filtro posta indesiderata in uscita che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="20f0d-278">In PowerShell, you create the outbound spam filter policy first, then you create the outbound spam filter rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="20f0d-279">In PowerShell, è possibile modificare le impostazioni nel criterio di filtro della posta indesiderata in uscita e la regola di filtro posta indesiderata in uscita separatamente.</span><span class="sxs-lookup"><span data-stu-id="20f0d-279">In PowerShell, you modify the settings in the outbound spam filter policy and the outbound spam filter rule separately.</span></span>
- <span data-ttu-id="20f0d-280">Quando si rimuove un criterio di filtro per la posta indesiderata in uscita da PowerShell, la regola di filtro posta indesiderata in uscita corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="20f0d-280">When you remove a outbound spam filter policy from PowerShell, the corresponding outbound spam filter rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-outbound-spam-policies"></a><span data-ttu-id="20f0d-281">Utilizzo di PowerShell per creare i criteri di posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-281">Use PowerShell to create outbound spam policies</span></span>

<span data-ttu-id="20f0d-282">La creazione di un criterio di posta indesiderata in uscita in PowerShell è un processo in due fasi:</span><span class="sxs-lookup"><span data-stu-id="20f0d-282">Creating an outbound spam policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="20f0d-283">Creare il criterio di filtro per la posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="20f0d-283">Create the outbound spam filter policy.</span></span>
2. <span data-ttu-id="20f0d-284">Creare la regola di filtro posta indesiderata in uscita che specifica il criterio di filtro della posta indesiderata in uscita a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="20f0d-284">Create the outbound spam filter rule that specifies the outbound spam filter policy that the rule applies to.</span></span>

 <span data-ttu-id="20f0d-285">**Note** :</span><span class="sxs-lookup"><span data-stu-id="20f0d-285">**Notes** :</span></span>

- <span data-ttu-id="20f0d-286">È possibile creare una nuova regola di filtro per la posta indesiderata in uscita e assegnare un criterio di filtro per la posta indesiderata in uscita non associato.</span><span class="sxs-lookup"><span data-stu-id="20f0d-286">You can create a new outbound spam filter rule and assign an existing, unassociated outbound spam filter policy to it.</span></span> <span data-ttu-id="20f0d-287">Una regola di filtro per la posta indesiderata in uscita non può essere associata a più criteri di filtro posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="20f0d-287">An outbound spam filter rule can't be associated with more than one outbound spam filter policy.</span></span>

- <span data-ttu-id="20f0d-288">È possibile configurare le seguenti impostazioni nei nuovi criteri di filtro per la posta indesiderata in uscita in PowerShell che non sono disponibili nel centro sicurezza & conformità fino a dopo la creazione del criterio:</span><span class="sxs-lookup"><span data-stu-id="20f0d-288">You can configure the following settings on new outbound spam filter policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="20f0d-289">Creare il nuovo criterio come disabilitato ( _attivato_ `$false` nel cmdlet **New-HostedOutboundSpamFilterRule** ).</span><span class="sxs-lookup"><span data-stu-id="20f0d-289">Create the new policy as disabled ( _Enabled_ `$false` on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>
  - <span data-ttu-id="20f0d-290">Impostare la priorità del criterio durante la creazione ( _priorità_ _\<Number\>_ ) del cmdlet **New-HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-290">Set the priority of the policy during creation ( _Priority_ _\<Number\>_ ) on the **New-HostedOutboundSpamFilterRule** cmdlet).</span></span>

- <span data-ttu-id="20f0d-291">Un nuovo criterio di filtro per la posta indesiderata in uscita creato in PowerShell non è visibile nel centro sicurezza & conformità fino a quando non si assegna il criterio a una regola di filtro posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="20f0d-291">A new outbound spam filter policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a spam filter rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a><span data-ttu-id="20f0d-292">Passaggio 1: utilizzare PowerShell per creare un criterio di filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-292">Step 1: Use PowerShell to create an outbound spam filter policy</span></span>

<span data-ttu-id="20f0d-293">Per creare un criterio di filtro per la posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-293">To create an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="20f0d-294">In questo esempio viene creato un nuovo criterio di filtro per la posta indesiderata in uscita denominato contoso Executives con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="20f0d-294">This example creates a new outbound spam filter policy named Contoso Executives with the following settings:</span></span>

- <span data-ttu-id="20f0d-295">I limiti di frequenza dei destinatari sono limitati a valori inferiori a quelli predefiniti.</span><span class="sxs-lookup"><span data-stu-id="20f0d-295">The recipient rate limits are restricted to smaller values that the defaults.</span></span> <span data-ttu-id="20f0d-296">Per ulteriori informazioni, vedere [invio di limiti tra le opzioni di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span><span class="sxs-lookup"><span data-stu-id="20f0d-296">For more information, see [Sending limits across Microsoft 365 options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).</span></span>

- <span data-ttu-id="20f0d-297">Dopo che è stato raggiunto uno dei limiti, all'utente viene impedito l'invio di messaggi.</span><span class="sxs-lookup"><span data-stu-id="20f0d-297">After one of the limits is reached, the user is prevented from sending messages.</span></span>

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

<span data-ttu-id="20f0d-298">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="20f0d-298">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a><span data-ttu-id="20f0d-299">Passaggio 2: utilizzare PowerShell per creare una regola di filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-299">Step 2: Use PowerShell to create an outbound spam filter rule</span></span>

<span data-ttu-id="20f0d-300">Per creare una regola di filtro per la posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-300">To create an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="20f0d-301">In questo esempio viene creata una nuova regola di filtro per la posta indesiderata in uscita denominata Contoso Executives con queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="20f0d-301">This example creates a new outbound spam filter rule named Contoso Executives with these settings:</span></span>

- <span data-ttu-id="20f0d-302">Il criterio di filtro per la posta indesiderata in uscita denominato contoso Executives è associato alla regola.</span><span class="sxs-lookup"><span data-stu-id="20f0d-302">The outbound spam filter policy named Contoso Executives is associated with the rule.</span></span>

- <span data-ttu-id="20f0d-303">La regola viene applicata ai membri del gruppo Contoso Executives Group.</span><span class="sxs-lookup"><span data-stu-id="20f0d-303">The rule applies to members of the group named Contoso Executives Group.</span></span>

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

<span data-ttu-id="20f0d-304">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="20f0d-304">For detailed syntax and parameter information, see [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a><span data-ttu-id="20f0d-305">Utilizzo di PowerShell per visualizzare i criteri di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-305">Use PowerShell to view outbound spam filter policies</span></span>

<span data-ttu-id="20f0d-306">Per restituire un elenco riepilogativo di tutti i criteri di filtro per la posta indesiderata in uscita, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-306">To return a summary list of all outbound spam filter policies, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

<span data-ttu-id="20f0d-307">Per restituire informazioni dettagliate su uno specifico criterio di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-307">To return detailed information about a specific outbound spam filter policy, use the this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="20f0d-308">In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio di filtro della posta indesiderata in uscita denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="20f0d-308">This example returns all the property values for the outbound spam filter policy named Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

<span data-ttu-id="20f0d-309">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="20f0d-309">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a><span data-ttu-id="20f0d-310">Utilizzare PowerShell per visualizzare le regole del filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-310">Use PowerShell to view outbound spam filter rules</span></span>

<span data-ttu-id="20f0d-311">Per visualizzare le regole di filtro per la posta indesiderata in uscita esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-311">To view existing outbound spam filter rules, use the following syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

<span data-ttu-id="20f0d-312">Per restituire un elenco riepilogativo di tutte le regole del filtro per la posta indesiderata in uscita, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-312">To return a summary list of all outbound spam filter rules, run this command:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule
```

<span data-ttu-id="20f0d-313">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="20f0d-313">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

<span data-ttu-id="20f0d-314">Per restituire informazioni dettagliate su una regola di filtro della posta indesiderata in uscita specifica, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-314">To return detailed information about a specific outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

<span data-ttu-id="20f0d-315">In questo esempio vengono restituiti tutti i valori delle proprietà per la regola di filtro della posta indesiderata in uscita denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="20f0d-315">This example returns all the property values for the outbound spam filter rule named Contoso Executives.</span></span>

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="20f0d-316">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="20f0d-316">For detailed syntax and parameter information, see [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a><span data-ttu-id="20f0d-317">Utilizzo di PowerShell per modificare i criteri di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-317">Use PowerShell to modify outbound spam filter policies</span></span>

<span data-ttu-id="20f0d-318">Le stesse impostazioni sono disponibili quando si modifica un criterio di filtro antimalware in PowerShell come quando si crea il criterio come descritto nel [passaggio 1: utilizzare PowerShell per creare una sezione dei criteri di filtro per la posta indesiderata in uscita](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="20f0d-318">The same settings are available when you modify a malware filter policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an outbound spam filter policy](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) section earlier in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="20f0d-319">Non è possibile rinominare un criterio di filtro per la posta indesiderata in uscita (il cmdlet **set-HostedOutboundSpamFilterPolicy** non ha un parametro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="20f0d-319">You can't rename an outbound spam filter policy (the **Set-HostedOutboundSpamFilterPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="20f0d-320">Quando si rinomina un criterio di posta indesiderata in uscita nel centro sicurezza & conformità, viene rinominata solo la _regola_ del filtro per la posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="20f0d-320">When you rename an outbound spam policy in the Security & Compliance Center, you're only renaming the outbound spam filter _rule_ .</span></span>

<span data-ttu-id="20f0d-321">Per modificare un criterio di filtro per la posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-321">To modify an outbound spam filter policy, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="20f0d-322">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="20f0d-322">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a><span data-ttu-id="20f0d-323">Utilizzare PowerShell per modificare le regole del filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-323">Use PowerShell to modify outbound spam filter rules</span></span>

<span data-ttu-id="20f0d-324">L'unica impostazione che non è disponibile quando si modifica una regola di filtro per la posta indesiderata in uscita in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="20f0d-324">The only setting that isn't available when you modify an outbound spam filter rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="20f0d-325">Per abilitare o disabilitare le regole di filtro per la posta indesiderata in uscita esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="20f0d-325">To enable or disable existing outbound spam filter rules, see the next section.</span></span>

<span data-ttu-id="20f0d-326">In caso contrario, non sono disponibili altre impostazioni quando si modifica una regola di filtro posta indesiderata in uscita in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20f0d-326">Otherwise, no additional settings are available when you modify an outbound spam filter rule in PowerShell.</span></span> <span data-ttu-id="20f0d-327">Le stesse impostazioni sono disponibili quando si crea una regola come descritto nel [passaggio 2: utilizzare PowerShell per creare una regola di filtro di protezione da posta indesiderata in uscita](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="20f0d-327">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an outbound spam filter rule](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) section earlier in this topic.</span></span>

<span data-ttu-id="20f0d-328">Per modificare una regola di filtro posta indesiderata in uscita, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-328">To modify an outbound spam filter rule, use this syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="20f0d-329">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="20f0d-329">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a><span data-ttu-id="20f0d-330">Utilizzo di PowerShell per abilitare o disabilitare le regole di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-330">Use PowerShell to enable or disable outbound spam filter rules</span></span>

<span data-ttu-id="20f0d-331">L'abilitazione o disabilitazione di una regola di filtro per la posta indesiderata in uscita in PowerShell consente di abilitare o disabilitare l'intero criterio di posta indesiderata in uscita (la regola del filtro posta indesiderata in uscita e il criterio filtro posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="20f0d-331">Enabling or disabling an outbound spam filter rule in PowerShell enables or disables the whole outbound spam policy (the outbound spam filter rule and the assigned outbound spam filter policy).</span></span> <span data-ttu-id="20f0d-332">Non è possibile abilitare o disabilitare il criterio di posta indesiderata in uscita predefinito (viene sempre applicato sempre a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="20f0d-332">You can't enable or disable the default outbound spam policy (it's always always applied to all recipients).</span></span>

<span data-ttu-id="20f0d-333">Per abilitare o disabilitare una regola di filtro per la posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-333">To enable or disable an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

<span data-ttu-id="20f0d-334">In questo esempio viene disabilitata la regola di filtro posta indesiderata in uscita denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="20f0d-334">This example disables the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="20f0d-335">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="20f0d-335">This example enables same rule.</span></span>

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="20f0d-336">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) e [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="20f0d-336">For detailed syntax and parameter information, see [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) and [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a><span data-ttu-id="20f0d-337">Utilizzo di PowerShell per impostare la priorità delle regole del filtro per la posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-337">Use PowerShell to set the priority of outbound spam filter rules</span></span>

<span data-ttu-id="20f0d-338">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="20f0d-338">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="20f0d-339">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="20f0d-339">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="20f0d-340">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="20f0d-340">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="20f0d-341">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="20f0d-341">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="20f0d-342">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="20f0d-342">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="20f0d-343">Per impostare la priorità di una regola di filtro di protezione da posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-343">To set the priority of an outbound spam filter rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="20f0d-p140">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="20f0d-p140">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - <span data-ttu-id="20f0d-346">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-HostedOutboundSpamFilterRule** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-346">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-HostedOutboundSpamFilterRule** cmdlet instead.</span></span>
>
> - <span data-ttu-id="20f0d-347">I criteri di filtro della posta indesiderata in uscita non dispongono di una regola di filtro di posta indesiderata corrispondente e il valore di priorità immodificabile è sempre **inferiore** .</span><span class="sxs-lookup"><span data-stu-id="20f0d-347">The outbound default spam filter policy doesn't have a corresponding spam filter rule, and it always has the unmodifiable priority value **Lowest** .</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a><span data-ttu-id="20f0d-348">Utilizzo di PowerShell per rimuovere i criteri di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-348">Use PowerShell to remove outbound spam filter policies</span></span>

<span data-ttu-id="20f0d-349">Quando si utilizza PowerShell per rimuovere un criterio di filtro della posta indesiderata in uscita, la regola di filtro posta indesiderata in uscita corrispondente non viene rimossa</span><span class="sxs-lookup"><span data-stu-id="20f0d-349">When you use PowerShell to remove an outbound spam filter policy, the corresponding outbound spam filter rule isn't removed.</span></span>

<span data-ttu-id="20f0d-350">Per rimuovere un criterio di filtro per la posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-350">To remove an outbound spam filter policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="20f0d-351">In questo esempio viene rimosso il criterio di filtro per la posta indesiderata in uscita denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="20f0d-351">This example removes the outbound spam filter policy named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

<span data-ttu-id="20f0d-352">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="20f0d-352">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).</span></span>

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a><span data-ttu-id="20f0d-353">Utilizzo di PowerShell per rimuovere le regole di filtro della posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-353">Use PowerShell to remove outbound spam filter rules</span></span>

<span data-ttu-id="20f0d-354">Quando si utilizza PowerShell per rimuovere una regola di filtro per la posta indesiderata in uscita, il criterio di filtro posta indesiderata in uscita corrispondente non viene rimosso</span><span class="sxs-lookup"><span data-stu-id="20f0d-354">When you use PowerShell to remove an outbound spam filter rule, the corresponding outbound spam filter policy isn't removed.</span></span>

<span data-ttu-id="20f0d-355">Per rimuovere una regola di filtro di protezione da posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="20f0d-355">To remove an outbound spam filter rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

<span data-ttu-id="20f0d-356">In questo esempio viene rimossa la regola di filtro posta indesiderata in uscita denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="20f0d-356">This example removes the outbound spam filter rule named Marketing Department.</span></span>

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

<span data-ttu-id="20f0d-357">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span><span class="sxs-lookup"><span data-stu-id="20f0d-357">For detailed syntax and parameter information, see [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="20f0d-358">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="20f0d-358">For more information</span></span>

[<span data-ttu-id="20f0d-359">Rimuovere utenti bloccati dal portale Utenti con restrizioni</span><span class="sxs-lookup"><span data-stu-id="20f0d-359">Remove blocked users from the Restricted Users portal</span></span>](removing-user-from-restricted-users-portal-after-spam.md)

[<span data-ttu-id="20f0d-360">Pool di recapito ad alto rischio per i messaggi in uscita</span><span class="sxs-lookup"><span data-stu-id="20f0d-360">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="20f0d-361">Domande frequenti sulla protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="20f0d-361">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)

[<span data-ttu-id="20f0d-362">Report dei messaggi inoltrati automaticamente</span><span class="sxs-lookup"><span data-stu-id="20f0d-362">Auto-forwarded messages report</span></span>](mfi-auto-forwarded-messages-report.md)
