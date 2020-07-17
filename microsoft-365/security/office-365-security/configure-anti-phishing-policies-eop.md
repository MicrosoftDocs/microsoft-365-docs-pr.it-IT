---
title: Configurazione dei criteri di anti-phishing in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come creare, modificare ed eliminare i criteri di anti-phishing disponibili nelle organizzazioni di Exchange Online Protection (EOP) con o senza cassette postali di Exchange Online.
ms.openlocfilehash: b6b95515ad44a65dbdd8a7516d8e6c8b2a386450
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726782"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="f891e-103">Configurazione dei criteri di anti-phishing in EOP</span><span class="sxs-lookup"><span data-stu-id="f891e-103">Configure anti-phishing policies in EOP</span></span>

<span data-ttu-id="f891e-104">In Microsoft 365 organizzazioni con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, è presente un criterio anti-phishing predefinito che contiene un numero limitato di funzionalità di anti-spoofing che sono abilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f891e-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="f891e-105">Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="f891e-105">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="f891e-106">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="f891e-106">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="f891e-107">Per una maggiore granularità, è anche possibile creare criteri di anti-phishing personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f891e-107">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="f891e-108">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).</span><span class="sxs-lookup"><span data-stu-id="f891e-108">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="f891e-109">Le organizzazioni con cassette postali di Exchange Online possono configurare criteri di anti-phishing nel centro sicurezza & conformità o in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f891e-109">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="f891e-110">Le organizzazioni di EOP autonome possono utilizzare solo il Centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="f891e-110">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="f891e-111">Per informazioni sulla creazione e la modifica dei criteri di anti-phishing ATP più avanzati disponibili in Office 365 Advanced Threat Protection (Office 365 ATP), vedere [Configure ATP anti-phishing Policies](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f891e-111">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection (Office 365 ATP), see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="f891e-112">Criteri di anti-phishing nel centro sicurezza & Compliance vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="f891e-112">Anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="f891e-113">Gli elementi di base di un criterio anti-phishing sono:</span><span class="sxs-lookup"><span data-stu-id="f891e-113">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="f891e-114">**Il criterio anti-phishing**: specifica le protezioni di phishing da abilitare o disabilitare e le azioni da applicare.</span><span class="sxs-lookup"><span data-stu-id="f891e-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="f891e-115">**La regola phishing**: specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="f891e-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="f891e-116">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri di anti-phishing nel centro sicurezza & Compliance:</span><span class="sxs-lookup"><span data-stu-id="f891e-116">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="f891e-117">Quando si crea un criterio anti-phishing nel centro sicurezza & Compliance, si sta effettivamente creando una regola anti-phishing e i criteri anti-phishing associati contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="f891e-117">When you create an anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="f891e-118">Quando si modifica un criterio anti-phishing nel centro sicurezza & conformità, le impostazioni relative ai filtri nome, priorità, abilitato o disabilitato e destinatario modificano la regola phishing.</span><span class="sxs-lookup"><span data-stu-id="f891e-118">When you modify an anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="f891e-119">Tutte le altre impostazioni modificano i criteri anti-phishing associati.</span><span class="sxs-lookup"><span data-stu-id="f891e-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="f891e-120">Quando si rimuove un criterio anti-phishing dal centro sicurezza & conformità, la regola anti-phishing e i criteri anti-phishing associati vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="f891e-120">When you remove an anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="f891e-121">In Exchange Online PowerShell, la differenza tra i criteri anti-phishing e le regole anti-phishing è evidente.</span><span class="sxs-lookup"><span data-stu-id="f891e-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="f891e-122">Per gestire i criteri anti-phishing è possibile utilizzare i cmdlet \*\* \* -AntiPhishPolicy\*\* e gestire le regole di anti-phishing utilizzando i cmdlet \*\* \* -AntiPhishRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="f891e-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="f891e-123">In PowerShell, è necessario creare innanzitutto il criterio phishing, quindi creare la regola anti-phishing che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="f891e-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="f891e-124">In PowerShell, è possibile modificare le impostazioni nel criterio di phishing e la regola anti-phishing separatamente.</span><span class="sxs-lookup"><span data-stu-id="f891e-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="f891e-125">Criteri di anti-phishing predefiniti del trifosfato di adenosina</span><span class="sxs-lookup"><span data-stu-id="f891e-125">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="f891e-126">Ogni organizzazione dispone di un criterio di anti-phishing incorporato denominato Office365 antiphishing default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="f891e-126">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="f891e-127">Il criterio denominato Office365 antiphishing default viene applicato a tutti i destinatari dell'organizzazione, anche se non è presente alcuna regola anti-phishing (filtri destinatario) associata al criterio.</span><span class="sxs-lookup"><span data-stu-id="f891e-127">The policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="f891e-128">Il criterio denominato Office365 antiphishing default ha il valore di priorità personalizzato **più basso** che non è possibile modificare (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="f891e-128">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="f891e-129">Tutti i criteri personalizzati creati hanno sempre una priorità più alta rispetto al criterio denominato Office365 antiphishing default.</span><span class="sxs-lookup"><span data-stu-id="f891e-129">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="f891e-130">Il criterio denominato Office365 antiphishing default è il criterio predefinito (la **proprietà IsDefault** ha il valore `True` ) e non è possibile eliminare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="f891e-130">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="f891e-131">Per aumentare l'efficacia della protezione anti-phishing, è possibile creare criteri di anti-phishing personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="f891e-131">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f891e-132">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="f891e-132">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f891e-133">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f891e-133">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f891e-134">Per passare direttamente alla pagina **anti-phishing** , utilizzare <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="f891e-134">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="f891e-135">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f891e-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="f891e-136">Non è possibile gestire i criteri di anti-phishing in standalone EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f891e-136">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="f891e-137">Prima di poter eseguire le procedure descritte in questo argomento, è necessario assegnare le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f891e-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="f891e-138">Per aggiungere, modificare ed eliminare i criteri di anti-phishing, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f891e-138">To add, modify, and delete anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f891e-139">**Gestione organizzazione** o **amministratore della sicurezza** nel [Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f891e-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f891e-140">Gestione dell' **organizzazione** o **gestione dell'igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f891e-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f891e-141">Per l'accesso in sola lettura ai criteri di anti-phishing, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="f891e-141">For read-only access to anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f891e-142">**Lettore di sicurezza** nel [Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f891e-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f891e-143">**Gestione dell'organizzazione in sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f891e-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="f891e-144">Per poter creare e modificare i criteri di protezione dalla posta indesiderata in EOP autonomo, è necessario eseguire un'operazione che richiede l' _idratazione_ per il tenant.</span><span class="sxs-lookup"><span data-stu-id="f891e-144">To be able to create and modify anti-spam policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="f891e-145">Ad esempio, nell'interfaccia di amministrazione di Exchange (EAC), è possibile accedere alla scheda **autorizzazioni** , selezionare un gruppo di ruoli esistente, fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) e rimuovere un ruolo (che verrà infine aggiunto di nuovo).</span><span class="sxs-lookup"><span data-stu-id="f891e-145">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="f891e-146">Se il tenant non è mai stato idratato, viene visualizzata una finestra di dialogo denominata **Impostazioni organizzazione di aggiornamento** con una barra di avanzamento che deve essere completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f891e-146">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="f891e-147">Per ulteriori informazioni sull'idratazione, vedere il cmdlet [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) (che non è disponibile in standalone EOP PowerShell o nel Security & Compliance Center).</span><span class="sxs-lookup"><span data-stu-id="f891e-147">For more information about hydration, see the [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="f891e-148">Per le impostazioni consigliate per i criteri di anti-phishing, vedere [EOP default anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="f891e-148">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="f891e-149">Consentire l'applicazione dei criteri aggiornati fino a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="f891e-149">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="f891e-150">Per informazioni su dove vengono applicati i criteri di anti-phishing nella pipeline dei filtri, vedere [ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="f891e-150">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="f891e-151">Utilizzare il Centro sicurezza & conformità per creare criteri di anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-151">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="f891e-152">La creazione di un criterio anti-phishing personalizzato nel centro sicurezza & conformità crea la regola anti-phishing e i criteri anti-phishing associati contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="f891e-152">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="f891e-153">Quando si crea un criterio anti-phishing, è possibile specificare solo il nome, la descrizione e il filtro destinatario che identifica gli utenti a cui si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="f891e-153">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="f891e-154">Dopo aver creato il criterio, è possibile modificare il criterio per modificare o rivedere le impostazioni di anti-phishing predefinite.</span><span class="sxs-lookup"><span data-stu-id="f891e-154">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="f891e-155">Nel centro sicurezza & conformità, accedere a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="f891e-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f891e-156">Nella pagina **anti-phishing** fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f891e-156">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="f891e-157">Verrà visualizzata la procedura guidata **Crea un nuovo criterio anti-phishing** .</span><span class="sxs-lookup"><span data-stu-id="f891e-157">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="f891e-158">Nella pagina **Name Your Policy** , configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="f891e-158">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="f891e-159">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="f891e-159">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="f891e-160">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="f891e-160">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="f891e-161">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f891e-161">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f891e-162">Nella pagina **applicata alla** pagina che viene visualizzata, identificare i destinatari interni ai quali si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="f891e-162">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="f891e-163">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="f891e-163">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="f891e-164">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="f891e-164">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="f891e-165">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="f891e-165">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="f891e-166">Fare clic su **Aggiungi condizione**.</span><span class="sxs-lookup"><span data-stu-id="f891e-166">Click **Add a condition**.</span></span> <span data-ttu-id="f891e-167">Nell'elenco a discesa che viene visualizzato, selezionare una condizione in **applicato se**:</span><span class="sxs-lookup"><span data-stu-id="f891e-167">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="f891e-168">**Il destinatario è**: consente di specificare una o più cassette postali, utenti di posta elettronica o contatti di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f891e-168">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="f891e-169">**Il destinatario è un membro di**: consente di specificare uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f891e-169">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="f891e-170">**Il dominio del destinatario è**: specifica i destinatari in uno o più dei domini configurati accettati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f891e-170">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="f891e-171">Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con una **qualsiasi di queste** caselle.</span><span class="sxs-lookup"><span data-stu-id="f891e-171">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="f891e-172">Fare clic nella casella e scorrere l'elenco di valori da selezionare.</span><span class="sxs-lookup"><span data-stu-id="f891e-172">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="f891e-173">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="f891e-173">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="f891e-174">Per aggiungere ulteriori valori, fare clic in un'area vuota nella casella.</span><span class="sxs-lookup"><span data-stu-id="f891e-174">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="f891e-175">Per rimuovere singole voci, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sul valore.</span><span class="sxs-lookup"><span data-stu-id="f891e-175">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="f891e-176">Per rimuovere l'intera condizione, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sulla condizione.</span><span class="sxs-lookup"><span data-stu-id="f891e-176">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="f891e-177">Per aggiungere una condizione aggiuntiva, fare clic su **Aggiungi condizione** e selezionare un valore restante in **applicato se**.</span><span class="sxs-lookup"><span data-stu-id="f891e-177">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="f891e-178">Per aggiungere eccezioni, fare clic su **Aggiungi condizione** e selezionare un'eccezione in **except if**.</span><span class="sxs-lookup"><span data-stu-id="f891e-178">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="f891e-179">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="f891e-179">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="f891e-180">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f891e-180">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f891e-181">Nella pagina **Verifica le impostazioni** che viene visualizzata, esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="f891e-181">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="f891e-182">È possibile fare clic su **modifica** su ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="f891e-182">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="f891e-183">Al termine, fare clic su **crea questo criterio**.</span><span class="sxs-lookup"><span data-stu-id="f891e-183">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="f891e-184">Fare clic su **OK** nella finestra di dialogo di conferma che viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="f891e-184">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="f891e-185">Dopo aver creato il criterio di anti-phishing con queste impostazioni di criteri generali, utilizzare le istruzioni nella sezione successiva per configurare le impostazioni di protezione nel criterio.</span><span class="sxs-lookup"><span data-stu-id="f891e-185">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="f891e-186">Utilizzare il Centro sicurezza & conformità per modificare i criteri di anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-186">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="f891e-187">Per modificare i criteri di anti-phishing, utilizzare le procedure seguenti: un nuovo criterio creato o criteri esistenti già personalizzati.</span><span class="sxs-lookup"><span data-stu-id="f891e-187">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="f891e-188">Se non si è ancora presenti, aprire il Centro sicurezza & compliance e passare a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="f891e-188">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f891e-189">Selezionare il criterio di anti-phishing personalizzato che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="f891e-189">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="f891e-190">Se è già selezionata, deselezionarla e selezionarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f891e-190">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="f891e-191">Verrà visualizzato il riquadro a comparsa \*\*modifica il criterio \<name\> \*\* .</span><span class="sxs-lookup"><span data-stu-id="f891e-191">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="f891e-192">Fare clic su **modifica** in qualsiasi sezione consente di accedere alle impostazioni di tale sezione.</span><span class="sxs-lookup"><span data-stu-id="f891e-192">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="f891e-193">I passaggi seguenti sono presentati nell'ordine in cui vengono visualizzate le sezioni, ma non sono sequenziali (è possibile selezionare e modificare le sezioni in qualsiasi ordine).</span><span class="sxs-lookup"><span data-stu-id="f891e-193">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="f891e-194">Dopo aver fatto clic su **modifica** in una sezione, le impostazioni disponibili vengono presentate in un formato di procedura guidata, ma è possibile passare all'interno delle pagine in qualsiasi ordine e fare clic su **Salva** in qualsiasi pagina oppure **annullare** o **chiudere** l' ![ icona Chiudi ](../../media/scc-remove-icon.png) per tornare alla pagina \*\*modifica il criterio \<name\> \*\* (non è necessario visitare l'ultima pagina della procedura guidata per salvare o lasciare).</span><span class="sxs-lookup"><span data-stu-id="f891e-194">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="f891e-195">**Impostazione dei criteri**: fare clic su **modifica** per modificare le stesse impostazioni disponibili quando è stato [creato il criterio](#use-the-security--compliance-center-to-create-anti-phishing-policies) nella sezione precedente:</span><span class="sxs-lookup"><span data-stu-id="f891e-195">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="f891e-196">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f891e-196">**Name**</span></span>
   - <span data-ttu-id="f891e-197">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="f891e-197">**Description**</span></span>
   - <span data-ttu-id="f891e-198">**Applicato a**</span><span class="sxs-lookup"><span data-stu-id="f891e-198">**Applied to**</span></span>
   - <span data-ttu-id="f891e-199">**Esaminare le impostazioni**</span><span class="sxs-lookup"><span data-stu-id="f891e-199">**Review your settings**</span></span>

   <span data-ttu-id="f891e-200">Al termine, fare clic su **Salva** su qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="f891e-200">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="f891e-201">**Spoof**: fare clic su **modifica** per abilitare o disabilitare l'intelligence di spoofing, abilitare l'identificazione dei mittenti non autenticati in Outlook attivato o disattivato e configurare l'azione da applicare ai messaggi provenienti da mittenti bloccati falsificati.</span><span class="sxs-lookup"><span data-stu-id="f891e-201">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="f891e-202">Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="f891e-202">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="f891e-203">Si noti che le stesse impostazioni sono disponibili anche nei criteri di anti-phishing ATP.</span><span class="sxs-lookup"><span data-stu-id="f891e-203">Note that these same settings are also available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="f891e-204">**Impostazioni del filtro di spoofing**: il valore predefinito **è attivato**e si consiglia di lasciarlo acceso.</span><span class="sxs-lookup"><span data-stu-id="f891e-204">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="f891e-205">Per disattivarla, fare scorrere l'interruttore su **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="f891e-205">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="f891e-206">Per ulteriori informazioni, vedere [Configure Spoofing Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="f891e-206">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="f891e-207">Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Microsoft 365; è invece possibile abilitare il filtro avanzato per i connettori.</span><span class="sxs-lookup"><span data-stu-id="f891e-207">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="f891e-208">Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="f891e-208">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="f891e-209">**Abilita funzionalità mittente non autenticato** **: il valore predefinito è**attivato.</span><span class="sxs-lookup"><span data-stu-id="f891e-209">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="f891e-210">Per disattivarla, fare scorrere l'interruttore su **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="f891e-210">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="f891e-211">**Azioni**: specificare l'azione da intraprendere per i messaggi che non superano l'intelligence spoof:</span><span class="sxs-lookup"><span data-stu-id="f891e-211">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="f891e-212">**Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio**:</span><span class="sxs-lookup"><span data-stu-id="f891e-212">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="f891e-213">**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="f891e-213">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="f891e-214">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="f891e-214">**Quarantine the message**</span></span>

   - <span data-ttu-id="f891e-215">**Esaminare le impostazioni**: invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="f891e-215">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="f891e-216">È possibile fare clic su **modifica** in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="f891e-216">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="f891e-217">È possibile attivare o **disattivare** le seguenti impostazioni **direttamente in questa** pagina:</span><span class="sxs-lookup"><span data-stu-id="f891e-217">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="f891e-218">**Abilitare la protezione antispoofing**</span><span class="sxs-lookup"><span data-stu-id="f891e-218">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="f891e-219">**Abilitare la funzionalità mittente non autenticato**</span><span class="sxs-lookup"><span data-stu-id="f891e-219">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="f891e-220">Al termine, fare clic su **Salva** su qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="f891e-220">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="f891e-221">Tornare alla pagina \*\*modifica il criterio \<Name\> \*\* , rivedere le impostazioni, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f891e-221">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="f891e-222">Utilizzare il Centro sicurezza & conformità per modificare il criterio anti-phishing predefinito</span><span class="sxs-lookup"><span data-stu-id="f891e-222">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="f891e-223">Il criterio anti-phishing predefinito è denominato Office365 antiphishing default e non viene visualizzato nell'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="f891e-223">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="f891e-224">Per modificare il criterio anti-phishing predefinito, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f891e-224">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="f891e-225">Nel centro sicurezza & conformità, accedere a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="f891e-225">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f891e-226">Nella pagina **anti-phishing** fare clic su **criteri predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="f891e-226">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="f891e-227">Viene visualizzata la pagina **modifica il criterio Office365 antiphishing predefinita** .</span><span class="sxs-lookup"><span data-stu-id="f891e-227">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="f891e-228">Sono disponibili le sezioni seguenti, che contengono impostazioni identiche per il momento in cui si [modifica un criterio personalizzato](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="f891e-228">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="f891e-229">**Rappresentazione**</span><span class="sxs-lookup"><span data-stu-id="f891e-229">**Impersonation**</span></span>
   - <span data-ttu-id="f891e-230">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="f891e-230">**Spoof**</span></span>
   - <span data-ttu-id="f891e-231">**Impostazioni avanzate**</span><span class="sxs-lookup"><span data-stu-id="f891e-231">**Advanced settings**</span></span>

   <span data-ttu-id="f891e-232">Le impostazioni seguenti non sono disponibili quando si modifica il criterio predefinito:</span><span class="sxs-lookup"><span data-stu-id="f891e-232">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="f891e-233">È possibile visualizzare la sezione e i valori dell' **impostazione dei criteri** , ma non esiste alcun collegamento di **modifica** , quindi non è possibile modificare le impostazioni (nome del criterio, descrizione e l'utente a cui si applica il criterio, applicabile a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="f891e-233">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="f891e-234">Non è possibile eliminare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="f891e-234">You can't delete the default policy.</span></span>
   - <span data-ttu-id="f891e-235">Non è possibile modificare la priorità del criterio predefinito (viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="f891e-235">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="f891e-236">Nella pagina **modifica il criterio Office365 antiphishing predefinita** , esaminare le impostazioni e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f891e-236">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="f891e-237">Abilitazione o disabilitazione dei criteri di anti-phishing personalizzati</span><span class="sxs-lookup"><span data-stu-id="f891e-237">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="f891e-238">Nel centro sicurezza & conformità, accedere a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="f891e-238">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f891e-239">Si noti il valore nella colonna **stato** :</span><span class="sxs-lookup"><span data-stu-id="f891e-239">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="f891e-240">Fare scorrere l'interruttore su **disattivato** per disabilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="f891e-240">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="f891e-241">Scorrere l'interruttore **su** attivato per abilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="f891e-241">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="f891e-242">Non è possibile disabilitare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="f891e-242">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="f891e-243">Impostare la priorità dei criteri di anti-phishing personalizzati</span><span class="sxs-lookup"><span data-stu-id="f891e-243">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="f891e-244">Per impostazione predefinita, ai criteri di anti-phishing viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="f891e-244">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="f891e-245">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="f891e-245">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="f891e-246">Due criteri non possono avere priorità uguale.</span><span class="sxs-lookup"><span data-stu-id="f891e-246">No two policies can have the same priority.</span></span>

<span data-ttu-id="f891e-247">I criteri di anti-phishing personalizzati vengono visualizzati nell'ordine in cui sono stati elaborati (il primo criterio ha il valore di **priorità** 0).</span><span class="sxs-lookup"><span data-stu-id="f891e-247">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="f891e-248">Il criterio anti-phishing predefinito denominato Office365 antiphishing default ha il valore di priorità personalizzato **più basso**e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="f891e-248">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="f891e-249">**Nota**: nel centro sicurezza & conformità è possibile modificare solo la priorità dei criteri di anti-phishing dopo averlo creato.</span><span class="sxs-lookup"><span data-stu-id="f891e-249">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="f891e-250">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phishing (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="f891e-250">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="f891e-251">Per modificare la priorità di un criterio, fare clic su **aumenta priorità** o su **Diminuisci priorità** nelle proprietà del criterio (non è possibile modificare direttamente il numero di **priorità** nel centro sicurezza & conformità).</span><span class="sxs-lookup"><span data-stu-id="f891e-251">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="f891e-252">La modifica della priorità di un criterio ha senso solo se si dispone di più criteri.</span><span class="sxs-lookup"><span data-stu-id="f891e-252">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="f891e-253">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="f891e-253">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="f891e-254">Selezionare il criterio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="f891e-254">Select the policy that you want to modify.</span></span> <span data-ttu-id="f891e-255">Se è già selezionata, deselezionarla e selezionarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f891e-255">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="f891e-256">Verrà visualizzato il riquadro a comparsa \*\*modifica il criterio \<name\> \*\* .</span><span class="sxs-lookup"><span data-stu-id="f891e-256">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="f891e-257">Il criterio di anti-phishing personalizzato con il valore di **priorità** **0** ha solo il pulsante di **riduzione della priorità** disponibile.</span><span class="sxs-lookup"><span data-stu-id="f891e-257">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="f891e-258">Il criterio di anti-phishing personalizzato con il valore di **priorità** più basso (ad esempio, **3**) ha solo il pulsante **aumenta priorità** disponibile.</span><span class="sxs-lookup"><span data-stu-id="f891e-258">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="f891e-259">Se si dispone di tre o più criteri di anti-phishing personalizzati, i criteri tra i valori di priorità più alti e quelli più bassi sono disponibili per i pulsanti **aumenta priorità** e **Riduci priorità** .</span><span class="sxs-lookup"><span data-stu-id="f891e-259">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="f891e-260">Fare clic su **aumenta priorità** o su **Diminuisci priorità** per modificare il valore di **priorità** .</span><span class="sxs-lookup"><span data-stu-id="f891e-260">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="f891e-261">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="f891e-261">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="f891e-262">Utilizzare il Centro sicurezza & conformità per visualizzare i criteri di anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-262">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="f891e-263">Nel centro sicurezza & compliance e passare al criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="f891e-263">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f891e-264">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f891e-264">Do one of the following steps:</span></span>

   - <span data-ttu-id="f891e-265">Selezionare un criterio di anti-phishing personalizzato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="f891e-265">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="f891e-266">Se è già selezionata, deselezionarla e selezionarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f891e-266">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="f891e-267">Fare clic su **criteri predefiniti** per visualizzare i criteri di anti-phishing predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f891e-267">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="f891e-268">Verrà visualizzato il riquadro a comparsa \*\*modifica il criterio \<name\> \*\* , in cui è possibile visualizzare le impostazioni e i valori.</span><span class="sxs-lookup"><span data-stu-id="f891e-268">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="f891e-269">Utilizzare il Centro sicurezza & conformità per rimuovere i criteri di anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-269">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="f891e-270">Nel centro sicurezza & conformità, accedere a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="f891e-270">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="f891e-271">Selezionare il criterio che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="f891e-271">Select the policy that you want to remove.</span></span> <span data-ttu-id="f891e-272">Se è già selezionata, deselezionarla e selezionarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="f891e-272">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="f891e-273">Nel riquadro a comparsa **modifica \<name\> il criterio** visualizzato, fare clic su **Elimina criteri**, quindi fare clic su **Sì** nella finestra di dialogo di avviso visualizzata.</span><span class="sxs-lookup"><span data-stu-id="f891e-273">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="f891e-274">Non è possibile rimuovere il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="f891e-274">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="f891e-275">Utilizzare PowerShell di Exchange Online per configurare i criteri di anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-275">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="f891e-276">Le procedure seguenti non sono disponibili nelle organizzazioni di EOP autonome.</span><span class="sxs-lookup"><span data-stu-id="f891e-276">The following procedures aren't available in standalone EOP organizations.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="f891e-277">Utilizzo di PowerShell per creare criteri di anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-277">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="f891e-278">La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="f891e-278">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="f891e-279">Creare il criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="f891e-279">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="f891e-280">Creare la regola anti-phishing che specifica i criteri anti-phishing a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="f891e-280">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="f891e-281">**Note**:</span><span class="sxs-lookup"><span data-stu-id="f891e-281">**Notes**:</span></span>

- <span data-ttu-id="f891e-282">È possibile creare una nuova regola anti-phishing e assegnargli un criterio anti-phishing esistente e non associato.</span><span class="sxs-lookup"><span data-stu-id="f891e-282">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="f891e-283">Non è possibile associare una regola anti-phishing a più di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="f891e-283">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="f891e-284">È possibile configurare le impostazioni seguenti sui nuovi criteri di phishing in PowerShell che non sono disponibili nel centro sicurezza & conformità fino a dopo la creazione del criterio:</span><span class="sxs-lookup"><span data-stu-id="f891e-284">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="f891e-285">Creare il nuovo criterio come disabilitato (_attivato_ `$false` nel cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="f891e-285">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="f891e-286">Impostare la priorità del criterio durante la creazione (_priorità_ _\<Number\>_ ) del cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="f891e-286">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="f891e-287">Un nuovo criterio di phishing creato in PowerShell non è visibile nel centro sicurezza & conformità fino a quando non si assegna il criterio a una regola anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="f891e-287">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="f891e-288">Passaggio 1: utilizzare PowerShell per creare un criterio anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-288">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="f891e-289">Per creare un criterio di phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f891e-289">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="f891e-290">In questo esempio viene creato il criterio phishing denominato Research Quarantine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="f891e-290">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="f891e-291">Il criterio è abilitato (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="f891e-291">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="f891e-292">La descrizione è: criteri del reparto ricerche.</span><span class="sxs-lookup"><span data-stu-id="f891e-292">The description is: Research department policy.</span></span>
- <span data-ttu-id="f891e-293">Consente di modificare l'azione predefinita per lo spoofing in quarantena.</span><span class="sxs-lookup"><span data-stu-id="f891e-293">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="f891e-294">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="f891e-294">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="f891e-295">Passaggio 2: utilizzare PowerShell per creare una regola anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-295">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="f891e-296">Per creare una regola anti-phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f891e-296">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="f891e-297">In questo esempio viene creata una regola di phishing denominata Research Department con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f891e-297">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="f891e-298">La regola è associata ai criteri anti-phishing denominati Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="f891e-298">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="f891e-299">La regola viene applicata ai membri del gruppo denominato Research Department.</span><span class="sxs-lookup"><span data-stu-id="f891e-299">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="f891e-300">Poiché non si utilizza il parametro _Priority_ , viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="f891e-300">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="f891e-301">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="f891e-301">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="f891e-302">Utilizzo di PowerShell per visualizzare i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-302">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="f891e-303">Per visualizzare i criteri anti-phishing esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f891e-303">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f891e-304">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri anti-phishing insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="f891e-304">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="f891e-305">In questo esempio vengono restituiti tutti i valori della proprietà per il criterio phishing denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="f891e-305">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="f891e-306">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="f891e-306">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="f891e-307">Utilizzo di PowerShell per visualizzare le regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-307">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="f891e-308">Per visualizzare le regole anti-phishing esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f891e-308">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="f891e-309">In questo esempio viene restituito un elenco riepilogativo di tutte le regole anti-phishing insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="f891e-309">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="f891e-310">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f891e-310">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="f891e-311">In questo esempio vengono restituiti tutti i valori della proprietà per la regola phishing denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="f891e-311">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="f891e-312">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="f891e-312">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="f891e-313">Utilizzo di PowerShell per la modifica dei criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-313">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="f891e-314">A parte gli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio di phishing in PowerShell come quando si crea il criterio come descritto nel [passaggio 1: utilizzare PowerShell per creare una sezione dei criteri anti-phishing](#step-1-use-powershell-to-create-an-anti-phish-policy) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f891e-314">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="f891e-315">L'opzione _MakeDefault_ che consente di trasformare il criterio specificato nel criterio predefinito (applicato a tutti, priorità sempre **più bassa** e non è possibile eliminarla) è disponibile solo quando si modifica un criterio di protezione da phishing in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f891e-315">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="f891e-316">Non è possibile rinominare un criterio anti-phishing (il cmdlet **set-AntiPhishPolicy** non ha un parametro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="f891e-316">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="f891e-317">Quando si rinomina un criterio anti-phishing nel centro sicurezza & Compliance, viene rinominata solo la _regola_anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="f891e-317">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="f891e-318">Per modificare un criterio di phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f891e-318">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="f891e-319">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="f891e-319">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="f891e-320">Utilizzo di PowerShell per modificare le regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-320">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="f891e-321">L'unica impostazione che non è disponibile quando si modifica una regola anti-phishing in PowerShell è il parametro _Enabled_ che consente di creare una regola disattivata.</span><span class="sxs-lookup"><span data-stu-id="f891e-321">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="f891e-322">Per abilitare o disabilitare le regole anti-phishing esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="f891e-322">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="f891e-323">In caso contrario, non sono disponibili ulteriori impostazioni quando si modifica una regola anti-phishing in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f891e-323">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="f891e-324">Le stesse impostazioni sono disponibili quando si crea una regola come descritto nel [passaggio 2: utilizzo di PowerShell per creare una sezione di regola anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f891e-324">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="f891e-325">Per modificare una regola anti-phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f891e-325">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="f891e-326">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="f891e-326">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="f891e-327">Utilizzo di PowerShell per abilitare o disabilitare le regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-327">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="f891e-328">L'abilitazione o disabilitazione di una regola anti-phishing in PowerShell consente di abilitare o disabilitare l'intero criterio anti-phishing (la regola anti-phishing e i criteri di anti-phishing assegnati).</span><span class="sxs-lookup"><span data-stu-id="f891e-328">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="f891e-329">Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="f891e-329">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="f891e-330">Per abilitare o disabilitare una regola anti-phishing in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f891e-330">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="f891e-331">In questo esempio viene disabilitata la regola anti-phishing denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="f891e-331">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="f891e-332">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="f891e-332">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="f891e-333">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) e [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="f891e-333">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="f891e-334">Utilizzo di PowerShell per impostare la priorità delle regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-334">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="f891e-335">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="f891e-335">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="f891e-336">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="f891e-336">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="f891e-337">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="f891e-337">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="f891e-338">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="f891e-338">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="f891e-339">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="f891e-339">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="f891e-340">Per impostare la priorità di una regola anti-phishing in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f891e-340">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="f891e-p136">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="f891e-p136">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="f891e-343">**Note**:</span><span class="sxs-lookup"><span data-stu-id="f891e-343">**Notes**:</span></span>

- <span data-ttu-id="f891e-344">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="f891e-344">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="f891e-345">I criteri predefiniti di phishing non dispongono di una regola anti-phishing corrispondente e hanno sempre il valore di priorità immodificabile **più basso**.</span><span class="sxs-lookup"><span data-stu-id="f891e-345">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="f891e-346">Utilizzo di PowerShell per rimuovere i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-346">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="f891e-347">Quando si utilizza PowerShell per rimuovere un criterio phishing, la regola anti-phishing corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="f891e-347">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="f891e-348">Per rimuovere un criterio di phishing in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f891e-348">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="f891e-349">In questo esempio viene rimosso il criterio anti-phishing denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="f891e-349">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="f891e-350">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="f891e-350">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="f891e-351">Utilizzo di PowerShell per rimuovere le regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="f891e-351">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="f891e-352">Quando si utilizza PowerShell per rimuovere una regola anti-phishing, i criteri di anti-phishing corrispondenti non vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="f891e-352">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="f891e-353">Per rimuovere una regola anti-phishing in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f891e-353">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="f891e-354">In questo esempio viene rimossa la regola anti-phishing denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="f891e-354">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="f891e-355">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="f891e-355">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f891e-356">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="f891e-356">How do you know these procedures worked?</span></span>

<span data-ttu-id="f891e-357">Per verificare la corretta configurazione dei criteri di anti-phishing ATP, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f891e-357">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="f891e-358">Nel centro sicurezza & conformità, accedere a criterio di **gestione delle minacce** \> **Policy** \> **anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="f891e-358">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="f891e-359">Verificare l'elenco dei criteri, i relativi valori di **stato** e i relativi valori di **priorità** .</span><span class="sxs-lookup"><span data-stu-id="f891e-359">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="f891e-360">Per visualizzare ulteriori dettagli, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f891e-360">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="f891e-361">Selezionare il criterio dall'elenco e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="f891e-361">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="f891e-362">Fare clic su **criteri predefiniti** e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="f891e-362">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="f891e-363">In Exchange Online PowerShell, sostituire \<Name\> con il nome del criterio o della regola ed eseguire il comando riportato di seguito e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="f891e-363">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
