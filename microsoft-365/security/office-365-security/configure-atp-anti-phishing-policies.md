---
title: Configurare i criteri anti-phishing ATP
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
description: Gli amministratori possono ottenere informazioni su come creare, modificare ed eliminare i criteri di anti-phishing avanzati disponibili nelle organizzazioni con Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: 458a4eac348598d1b752267ed7d79b97bc594580
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726761"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="170e6-103">Configurare i criteri anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="170e6-103">Configure ATP anti-phishing policies</span></span>

<span data-ttu-id="170e6-104">I criteri di anti-phishing ATP fanno parte di [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="170e6-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="170e6-105">I criteri di anti-phishing ATP consentono di proteggere l'organizzazione da attacchi di phishing basati sulla rappresentazione malevola e altri tipi di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="170e6-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="170e6-106">Per ulteriori informazioni sulle differenze tra i criteri di anti-phishing in Exchange Online Protection (EOP) e i criteri di anti-phishing ATP, vedere [protezione anti-phishing](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="170e6-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="170e6-107">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito del trifosfato di adenosina.</span><span class="sxs-lookup"><span data-stu-id="170e6-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="170e6-108">Per una maggiore granularità, è anche possibile creare criteri di anti-phishing ATP personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="170e6-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="170e6-109">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).</span><span class="sxs-lookup"><span data-stu-id="170e6-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="170e6-110">È possibile configurare i criteri di anti-phishing ATP nel centro sicurezza & Compliance o in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="170e6-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="170e6-111">Per informazioni sulla configurazione dei criteri di anti-phishing più limitati disponibili nelle organizzazioni di protezione di Exchange Online (ovvero le organizzazioni Microsoft 365 senza Office 365 ATP), vedere [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="170e6-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="170e6-112">Criteri di anti-phishing ATP nel centro sicurezza & Compliance vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="170e6-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="170e6-113">Gli elementi di base di un criterio anti-phishing ATP sono:</span><span class="sxs-lookup"><span data-stu-id="170e6-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="170e6-114">**Il criterio anti-phishing**: specifica le protezioni di phishing da abilitare o disabilitare e le azioni da applicare.</span><span class="sxs-lookup"><span data-stu-id="170e6-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>

- <span data-ttu-id="170e6-115">**La regola phishing**: specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="170e6-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="170e6-116">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri di anti-phishing ATP nel centro sicurezza & Compliance:</span><span class="sxs-lookup"><span data-stu-id="170e6-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="170e6-117">Quando si crea un criterio anti-phishing ATP nel centro sicurezza & Compliance, si sta effettivamente creando una regola anti-phishing e i criteri anti-phishing associati contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="170e6-117">When you create an ATP anti-phishing policy in the Security & Compliance Center, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

- <span data-ttu-id="170e6-118">Quando si modifica un criterio anti-phishing ATP nel centro sicurezza & Compliance, le impostazioni relative ai filtri nome, priorità, abilitato o disabilitato e destinatario modificano la regola phishing.</span><span class="sxs-lookup"><span data-stu-id="170e6-118">When you modify an ATP anti-phishing policy in the Security & Compliance Center, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="170e6-119">Tutte le altre impostazioni modificano i criteri anti-phishing associati.</span><span class="sxs-lookup"><span data-stu-id="170e6-119">All other settings modify the associated anti-phish policy.</span></span>

- <span data-ttu-id="170e6-120">Quando si rimuove un criterio anti-phishing ATP dal centro sicurezza & conformità, la regola anti-phishing e i criteri anti-phishing associati vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="170e6-120">When you remove an ATP anti-phishing policy from the Security & Compliance Center, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="170e6-121">In Exchange Online PowerShell, la differenza tra i criteri anti-phishing e le regole anti-phishing è evidente.</span><span class="sxs-lookup"><span data-stu-id="170e6-121">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="170e6-122">Per gestire i criteri anti-phishing è possibile utilizzare i cmdlet \*\* \* -AntiPhishPolicy\*\* e gestire le regole di anti-phishing utilizzando i cmdlet \*\* \* -AntiPhishRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="170e6-122">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="170e6-123">In PowerShell, è necessario creare innanzitutto il criterio phishing, quindi creare la regola anti-phishing che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="170e6-123">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>

- <span data-ttu-id="170e6-124">In PowerShell, è possibile modificare le impostazioni nel criterio di phishing e la regola anti-phishing separatamente.</span><span class="sxs-lookup"><span data-stu-id="170e6-124">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>

- <span data-ttu-id="170e6-125">Quando si rimuove un criterio di phishing da PowerShell, la regola anti-phishing corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="170e6-125">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="default-atp-anti-phishing-policy"></a><span data-ttu-id="170e6-126">Criteri di anti-phishing predefiniti del trifosfato di adenosina</span><span class="sxs-lookup"><span data-stu-id="170e6-126">Default ATP anti-phishing policy</span></span>

<span data-ttu-id="170e6-127">Ogni organizzazione ATP ha un criterio anti-phishing incorporato denominato Office365 antiphishing default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="170e6-127">Every ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="170e6-128">Il criterio di phishing denominato Office365 antiphishing default viene applicato a tutti i destinatari dell'organizzazione, anche se non è presente alcuna regola anti-phishing (filtri destinatario) associata al criterio.</span><span class="sxs-lookup"><span data-stu-id="170e6-128">The anti-phish policy named Office365 AntiPhish Default is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>

- <span data-ttu-id="170e6-129">Il criterio denominato Office365 antiphishing default ha il valore di priorità personalizzato **più basso** che non è possibile modificare (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="170e6-129">The policy named Office365 AntiPhish Default has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="170e6-130">Tutti i criteri personalizzati creati hanno sempre una priorità più alta rispetto al criterio denominato Office365 antiphishing default.</span><span class="sxs-lookup"><span data-stu-id="170e6-130">Any custom policies that you create always have a higher priority than the policy named Office365 AntiPhish Default.</span></span>

- <span data-ttu-id="170e6-131">Il criterio denominato Office365 antiphishing default è il criterio predefinito (la **proprietà IsDefault** ha il valore `True` ) e non è possibile eliminare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="170e6-131">The policy named Office365 AntiPhish Default is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="170e6-132">Per aumentare l'efficacia della protezione anti-phishing, è possibile creare criteri di anti-phishing ATP personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="170e6-132">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="170e6-133">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="170e6-133">What do you need to know before you begin?</span></span>

- <span data-ttu-id="170e6-134">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="170e6-134">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="170e6-135">Per accedere direttamente alla pagina **anti-phishing ATP** , utilizzare <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="170e6-135">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="170e6-136">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="170e6-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="170e6-137">Prima di poter eseguire le procedure descritte in questo argomento, è necessario assegnare le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="170e6-137">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="170e6-138">Per aggiungere, modificare ed eliminare i criteri di anti-phishing ATP, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="170e6-138">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="170e6-139">**Gestione organizzazione** o **amministratore della sicurezza** nel [Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="170e6-139">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="170e6-140">Gestione dell' **organizzazione** o **gestione dell'igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="170e6-140">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="170e6-141">Per l'accesso in sola lettura ai criteri di anti-phishing ATP, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="170e6-141">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="170e6-142">**Lettore di sicurezza** nel [Centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="170e6-142">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="170e6-143">**Gestione dell'organizzazione in sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="170e6-143">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="170e6-144">Per le impostazioni consigliate per i criteri di anti-phishing ATP, vedere [Office ATP anti-phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="170e6-144">For our recommended settings for ATP anti-phishing policies, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="170e6-145">Consentire l'applicazione di un criterio nuovo o aggiornato fino a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="170e6-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="170e6-146">Per informazioni su dove vengono applicati i criteri di anti-phishing nella pipeline dei filtri, vedere [ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="170e6-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="170e6-147">Utilizzare il Centro sicurezza & conformità per creare criteri di anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="170e6-147">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="170e6-148">La creazione di un criterio di anti-phishing ATP personalizzato nel centro sicurezza & conformità crea la regola anti-phishing e i criteri anti-phishing associati contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="170e6-148">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="170e6-149">Quando si crea un criterio di anti-phishing ATP, è possibile specificare solo il nome, la descrizione e il filtro destinatario che identifica gli utenti a cui si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="170e6-149">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="170e6-150">Dopo aver creato il criterio, è possibile modificare il criterio per modificare o rivedere le impostazioni di anti-phishing predefinite.</span><span class="sxs-lookup"><span data-stu-id="170e6-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="170e6-151">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="170e6-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="170e6-152">Nella pagina **anti-phishing** fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="170e6-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="170e6-153">Verrà visualizzata la procedura guidata **Crea un nuovo criterio anti-phishing** .</span><span class="sxs-lookup"><span data-stu-id="170e6-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="170e6-154">Nella pagina **Name Your Policy** , configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="170e6-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="170e6-155">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="170e6-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="170e6-156">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="170e6-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="170e6-157">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="170e6-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="170e6-158">Nella pagina **applicata alla** pagina che viene visualizzata, identificare i destinatari interni ai quali si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="170e6-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="170e6-159">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="170e6-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="170e6-160">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="170e6-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="170e6-161">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="170e6-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="170e6-162">Fare clic su **Aggiungi condizione**.</span><span class="sxs-lookup"><span data-stu-id="170e6-162">Click **Add a condition**.</span></span> <span data-ttu-id="170e6-163">Nell'elenco a discesa che viene visualizzato, selezionare una condizione in **applicato se**:</span><span class="sxs-lookup"><span data-stu-id="170e6-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="170e6-164">**Il destinatario è**: consente di specificare una o più cassette postali, utenti di posta elettronica o contatti di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="170e6-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="170e6-165">**Il destinatario è un membro di**: consente di specificare uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="170e6-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="170e6-166">**Il dominio del destinatario è**: consente di specificare i destinatari in uno o più dei domini accettati configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="170e6-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="170e6-167">Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con una **qualsiasi di queste** caselle.</span><span class="sxs-lookup"><span data-stu-id="170e6-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="170e6-168">Fare clic nella casella e scorrere l'elenco di valori da selezionare.</span><span class="sxs-lookup"><span data-stu-id="170e6-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="170e6-169">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="170e6-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="170e6-170">Per aggiungere ulteriori valori, fare clic in un'area vuota nella casella.</span><span class="sxs-lookup"><span data-stu-id="170e6-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="170e6-171">Per rimuovere singole voci, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sul valore.</span><span class="sxs-lookup"><span data-stu-id="170e6-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="170e6-172">Per rimuovere l'intera condizione, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sulla condizione.</span><span class="sxs-lookup"><span data-stu-id="170e6-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="170e6-173">Per aggiungere una condizione aggiuntiva, fare clic su **Aggiungi condizione** e selezionare un valore restante in **applicato se**.</span><span class="sxs-lookup"><span data-stu-id="170e6-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="170e6-174">Per aggiungere eccezioni, fare clic su **Aggiungi condizione** e selezionare un'eccezione in **except if**.</span><span class="sxs-lookup"><span data-stu-id="170e6-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="170e6-175">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="170e6-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="170e6-176">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="170e6-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="170e6-177">Nella pagina **Verifica le impostazioni** che viene visualizzata, esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="170e6-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="170e6-178">È possibile fare clic su **modifica** su ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="170e6-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="170e6-179">Al termine, fare clic su **crea questo criterio**.</span><span class="sxs-lookup"><span data-stu-id="170e6-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="170e6-180">Fare clic su **OK** nella finestra di dialogo di conferma che viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="170e6-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="170e6-181">Dopo aver creato il criterio anti-phishing ATP con queste impostazioni generali, utilizzare le istruzioni riportate nella sezione successiva per configurare le impostazioni di protezione nel criterio.</span><span class="sxs-lookup"><span data-stu-id="170e6-181">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="170e6-182">Utilizzare il Centro sicurezza & conformità per modificare i criteri di anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="170e6-182">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="170e6-183">Utilizzare le procedure seguenti per modificare i criteri di anti-phishing ATP: un nuovo criterio creato o criteri esistenti già personalizzati.</span><span class="sxs-lookup"><span data-stu-id="170e6-183">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="170e6-184">Se non si è ancora presenti, aprire il Centro sicurezza & compliance e passare al criterio di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="170e6-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="170e6-185">Selezionare il criterio di anti-phishing ATP personalizzato che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="170e6-185">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="170e6-186">Se è già selezionata, deselezionarla e selezionarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="170e6-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="170e6-187">Verrà visualizzato il riquadro a comparsa \*\*modifica il criterio \<name\> \*\* .</span><span class="sxs-lookup"><span data-stu-id="170e6-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="170e6-188">Fare clic su **modifica** in qualsiasi sezione consente di accedere alle impostazioni di tale sezione.</span><span class="sxs-lookup"><span data-stu-id="170e6-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="170e6-189">I passaggi seguenti sono presentati nell'ordine in cui vengono visualizzate le sezioni, ma non sono sequenziali (è possibile selezionare e modificare le sezioni in qualsiasi ordine).</span><span class="sxs-lookup"><span data-stu-id="170e6-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="170e6-190">Dopo aver fatto clic su **modifica** in una sezione, le impostazioni disponibili vengono presentate in un formato di procedura guidata, ma è possibile passare all'interno delle pagine in qualsiasi ordine e fare clic su **Salva** in qualsiasi pagina oppure **annullare** o **chiudere** l' ![ icona Chiudi ](../../media/scc-remove-icon.png) per tornare alla pagina \*\*modifica il criterio \<name\> \*\* (non è necessario visitare l'ultima pagina della procedura guidata per salvare o lasciare).</span><span class="sxs-lookup"><span data-stu-id="170e6-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="170e6-191">**Impostazione dei criteri**: fare clic su **modifica** per modificare le stesse impostazioni disponibili quando è stato [creato il criterio](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) nella sezione precedente:</span><span class="sxs-lookup"><span data-stu-id="170e6-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="170e6-192">**Nome**</span><span class="sxs-lookup"><span data-stu-id="170e6-192">**Name**</span></span>
   - <span data-ttu-id="170e6-193">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="170e6-193">**Description**</span></span>
   - <span data-ttu-id="170e6-194">**Applicato a**</span><span class="sxs-lookup"><span data-stu-id="170e6-194">**Applied to**</span></span>
   - <span data-ttu-id="170e6-195">**Esaminare le impostazioni**</span><span class="sxs-lookup"><span data-stu-id="170e6-195">**Review your settings**</span></span>

   <span data-ttu-id="170e6-196">Al termine, fare clic su **Salva** su qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="170e6-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="170e6-197">**Rappresentazione**: fare clic su **modifica** per modificare i mittenti protetti e i domini protetti nel criterio.</span><span class="sxs-lookup"><span data-stu-id="170e6-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="170e6-198">Queste impostazioni sono una condizione per i criteri che identificano i mittenti falsificati da cercare (singolarmente o in base al dominio) nell'indirizzo mittente dei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="170e6-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="170e6-199">Per ulteriori informazioni, vedere [impostazioni di rappresentazione nei criteri di anti-phishing ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="170e6-199">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="170e6-200">**Aggiungere gli utenti a Protect**: il valore predefinito è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="170e6-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="170e6-201">Per attivarla, scorrere l' **interruttore su attivato**e quindi fare clic sul pulsante **Aggiungi utente** visualizzato.</span><span class="sxs-lookup"><span data-stu-id="170e6-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="170e6-202">Nel riquadro a comparsa **utente aggiunto** che viene visualizzato, configurare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="170e6-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="170e6-203">**Indirizzo di posta elettronica**:</span><span class="sxs-lookup"><span data-stu-id="170e6-203">**Email address**:</span></span>

        - <span data-ttu-id="170e6-204">Fare clic nella casella e scorrere l'elenco degli utenti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="170e6-204">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="170e6-205">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="170e6-205">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="170e6-206">Per rimuovere una voce, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sull'utente.</span><span class="sxs-lookup"><span data-stu-id="170e6-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="170e6-207">**Nome**: questo valore viene popolato in base all'indirizzo di posta elettronica selezionato, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="170e6-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="170e6-208">Al termine, fare clic su **Salva** su qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="170e6-208">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="170e6-209">Per modificare una voce esistente, selezionare l'utente protetto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="170e6-209">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="170e6-210">**Aggiungere i domini da proteggere**: configurare una o entrambe le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="170e6-210">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="170e6-211">**Includere automaticamente i domini che possiedo**: il valore predefinito è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="170e6-211">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="170e6-212">Per attivarla, fare scorrere l'interruttore **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="170e6-212">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="170e6-213">**Includi domini personalizzati**: il valore predefinito è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="170e6-213">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="170e6-214">Per attivarla, scorrere l'interruttore **su**attivato e nella casella **Aggiungi domini** immettere il nome di dominio (ad esempio, contoso.com), premere invio e ripetere il secondo caso.</span><span class="sxs-lookup"><span data-stu-id="170e6-214">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="170e6-215">**Azioni**: fare clic su **modifica**</span><span class="sxs-lookup"><span data-stu-id="170e6-215">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="170e6-216">**Se il messaggio di posta elettronica viene inviato da un utente rappresentato**: configurare una delle seguenti azioni per i messaggi in cui il mittente falsificato è uno degli utenti protetti specificati in **Add Users to Protect**:</span><span class="sxs-lookup"><span data-stu-id="170e6-216">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="170e6-217">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="170e6-217">**Don't apply any action**</span></span>
       - <span data-ttu-id="170e6-218">**Reindirizza il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="170e6-218">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="170e6-219">**Sposta messaggio nella cartella Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="170e6-219">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="170e6-220">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="170e6-220">**Quarantine the message**</span></span>
       - <span data-ttu-id="170e6-221">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="170e6-221">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="170e6-222">**Eliminare il messaggio prima di essere recapitato**</span><span class="sxs-lookup"><span data-stu-id="170e6-222">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="170e6-223">**Se il messaggio di posta elettronica viene inviato da un dominio rappresentato**: configurare una delle seguenti azioni per i messaggi in cui il mittente contraffatto si trova in uno dei domini protetti specificati in **Aggiungi domini da proteggere**:</span><span class="sxs-lookup"><span data-stu-id="170e6-223">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="170e6-224">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="170e6-224">**Don't apply any action**</span></span>
     - <span data-ttu-id="170e6-225">**Reindirizza il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="170e6-225">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="170e6-226">**Sposta messaggio nella cartella Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="170e6-226">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="170e6-227">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="170e6-227">**Quarantine the message**</span></span>
     - <span data-ttu-id="170e6-228">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="170e6-228">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="170e6-229">**Eliminare il messaggio prima di essere recapitato**</span><span class="sxs-lookup"><span data-stu-id="170e6-229">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="170e6-230">Fare clic **su Attiva suggerimenti per la sicurezza della rappresentazione** e configurare una delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="170e6-230">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="170e6-231">**Mostra suggerimento per gli utenti rappresentati**: il valore predefinito è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="170e6-231">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="170e6-232">Per attivarla, fare scorrere l'interruttore **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="170e6-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="170e6-233">**Mostra suggerimento per i domini rappresentati**: il valore predefinito è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="170e6-233">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="170e6-234">Per attivarla, fare scorrere l'interruttore **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="170e6-234">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="170e6-235">**Mostra suggerimento per i caratteri insoliti**: il valore predefinito è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="170e6-235">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="170e6-236">Per attivarla, fare scorrere l'interruttore **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="170e6-236">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="170e6-237">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="170e6-237">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="170e6-238">**Intelligence delle cassette postali**:</span><span class="sxs-lookup"><span data-stu-id="170e6-238">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="170e6-239">Abilitare la funzionalità di **Intelligence delle cassette postali?**: il valore predefinito è **on**.</span><span class="sxs-lookup"><span data-stu-id="170e6-239">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="170e6-240">Per disattivarla, fare scorrere l'interruttore su **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="170e6-240">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="170e6-241">**Abilitare la protezione della rappresentazione basata sull'Intelligence delle cassette postali?**: questa impostazione è disponibile solo se abilitare la funzionalità **di** **Intelligence delle cassette postali?** è attiva.</span><span class="sxs-lookup"><span data-stu-id="170e6-241">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="170e6-242">**Se il messaggio di posta elettronica viene inviato da un utente rappresentato**, è possibile specificare una delle seguenti azioni da intraprendere per i messaggi che non riescono a utilizzare l'intelligence delle cassette postali (le stesse azioni disponibili per gli utenti protetti e i domini protetti):</span><span class="sxs-lookup"><span data-stu-id="170e6-242">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="170e6-243">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="170e6-243">**Don't apply any action**</span></span>
       - <span data-ttu-id="170e6-244">**Reindirizza il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="170e6-244">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="170e6-245">**Sposta messaggio nella cartella Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="170e6-245">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="170e6-246">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="170e6-246">**Quarantine the message**</span></span>
       - <span data-ttu-id="170e6-247">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="170e6-247">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="170e6-248">**Eliminare il messaggio prima di essere recapitato**</span><span class="sxs-lookup"><span data-stu-id="170e6-248">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="170e6-249">**Aggiungere i domini e i mittenti attendibili**: specificare le eccezioni per il criterio:</span><span class="sxs-lookup"><span data-stu-id="170e6-249">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="170e6-250">**Mittenti attendibili**:</span><span class="sxs-lookup"><span data-stu-id="170e6-250">**Trusted senders**:</span></span>

       - <span data-ttu-id="170e6-251">Fare clic nella casella e scorrere l'elenco degli utenti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="170e6-251">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="170e6-252">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="170e6-252">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="170e6-253">Per rimuovere una voce, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sull'utente.</span><span class="sxs-lookup"><span data-stu-id="170e6-253">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="170e6-254">**Domini attendibili**: immettere il nome di dominio (ad esempio, contoso.com), premere invio e ripetere se necessario.</span><span class="sxs-lookup"><span data-stu-id="170e6-254">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="170e6-255">**Esaminare le impostazioni**: invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="170e6-255">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="170e6-256">È possibile fare clic su **modifica** in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="170e6-256">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="170e6-257">È possibile attivare o **disattivare** le seguenti impostazioni **direttamente in questa** pagina:</span><span class="sxs-lookup"><span data-stu-id="170e6-257">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="170e6-258">**Utenti protetti**</span><span class="sxs-lookup"><span data-stu-id="170e6-258">**Protected users**</span></span>
       - <span data-ttu-id="170e6-259">**Domini protetti** \> **Includere domini personali**</span><span class="sxs-lookup"><span data-stu-id="170e6-259">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="170e6-260">**Domini protetti** \> **Domini protetti** (domini personalizzati)</span><span class="sxs-lookup"><span data-stu-id="170e6-260">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="170e6-261">**Intelligence della cassetta postale**</span><span class="sxs-lookup"><span data-stu-id="170e6-261">**Mailbox intelligence**</span></span>

   <span data-ttu-id="170e6-262">Al termine, fare clic su **Salva** su qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="170e6-262">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="170e6-263">**Spoof**: fare clic su **modifica** per abilitare o disabilitare l'intelligence di spoofing, abilitare l'identificazione dei mittenti non autenticati in Outlook attivato o disattivato e configurare l'azione da applicare ai messaggi provenienti da mittenti bloccati falsificati.</span><span class="sxs-lookup"><span data-stu-id="170e6-263">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="170e6-264">Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="170e6-264">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="170e6-265">Si noti che le stesse impostazioni sono disponibili anche nei criteri di anti-phishing in EOP.</span><span class="sxs-lookup"><span data-stu-id="170e6-265">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="170e6-266">**Impostazioni del filtro di spoofing**: il valore predefinito **è attivato**e si consiglia di lasciarlo acceso.</span><span class="sxs-lookup"><span data-stu-id="170e6-266">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="170e6-267">Per disattivarla, fare scorrere l'interruttore su **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="170e6-267">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="170e6-268">Per ulteriori informazioni, vedere [Configure Spoofing Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="170e6-268">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="170e6-269">Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Microsoft 365; è invece possibile abilitare il filtro avanzato per i connettori.</span><span class="sxs-lookup"><span data-stu-id="170e6-269">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="170e6-270">Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="170e6-270">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="170e6-271">**Abilita funzionalità mittente non autenticato** **: il valore predefinito è**attivato.</span><span class="sxs-lookup"><span data-stu-id="170e6-271">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="170e6-272">Per disattivarla, fare scorrere l'interruttore su **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="170e6-272">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="170e6-273">**Azioni**: specificare l'azione da intraprendere per i messaggi che non superano l'intelligence spoof:</span><span class="sxs-lookup"><span data-stu-id="170e6-273">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="170e6-274">**Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio**:</span><span class="sxs-lookup"><span data-stu-id="170e6-274">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="170e6-275">**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="170e6-275">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="170e6-276">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="170e6-276">**Quarantine the message**</span></span>

   - <span data-ttu-id="170e6-277">**Esaminare le impostazioni**: invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="170e6-277">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="170e6-278">È possibile fare clic su **modifica** in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="170e6-278">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="170e6-279">È possibile attivare o **disattivare** le seguenti impostazioni **direttamente in questa** pagina:</span><span class="sxs-lookup"><span data-stu-id="170e6-279">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="170e6-280">**Abilitare la protezione antispoofing**</span><span class="sxs-lookup"><span data-stu-id="170e6-280">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="170e6-281">**Abilitare la funzionalità mittente non autenticato**</span><span class="sxs-lookup"><span data-stu-id="170e6-281">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="170e6-282">Al termine, fare clic su **Salva** su qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="170e6-282">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="170e6-283">**Impostazioni avanzate**: fare clic su **modifica** per configurare le soglie di phishing avanzate.</span><span class="sxs-lookup"><span data-stu-id="170e6-283">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="170e6-284">Per ulteriori informazioni, vedere [soglie di phishing avanzate nei criteri di anti-phishing ATP](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="170e6-284">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="170e6-285">**Soglie di phishing avanzate**: selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="170e6-285">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="170e6-286">**1-standard** (questo è il valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="170e6-286">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="170e6-287">**2-aggressivo**</span><span class="sxs-lookup"><span data-stu-id="170e6-287">**2 - Aggressive**</span></span>
   - <span data-ttu-id="170e6-288">**3-maggiore aggressività**</span><span class="sxs-lookup"><span data-stu-id="170e6-288">**3 - More aggressive**</span></span>
   - <span data-ttu-id="170e6-289">**4-la più aggressiva**</span><span class="sxs-lookup"><span data-stu-id="170e6-289">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="170e6-290">**Esaminare le impostazioni**: fare clic su **modifica** per tornare alla pagina **soglie di phishing avanzate** .</span><span class="sxs-lookup"><span data-stu-id="170e6-290">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="170e6-291">Al termine, fare clic su **Salva** in una delle pagine.</span><span class="sxs-lookup"><span data-stu-id="170e6-291">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="170e6-292">Tornare alla pagina \*\*modifica il criterio \<Name\> \*\* , rivedere le impostazioni, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="170e6-292">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="170e6-293">Utilizzare il Centro sicurezza & conformità per modificare il criterio anti-phishing predefinito di ATP</span><span class="sxs-lookup"><span data-stu-id="170e6-293">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="170e6-294">Il criterio anti-phishing ATP predefinito è denominato Office365 antiphishing default e non viene visualizzato nell'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="170e6-294">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="170e6-295">Per modificare i criteri di anti-phishing predefiniti, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="170e6-295">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="170e6-296">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="170e6-296">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="170e6-297">Nella pagina **anti-phishing** fare clic su **criteri predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="170e6-297">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="170e6-298">Viene visualizzata la pagina **modifica il criterio Office365 antiphishing predefinita** .</span><span class="sxs-lookup"><span data-stu-id="170e6-298">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="170e6-299">Sono disponibili le sezioni seguenti, che contengono impostazioni identiche per quando si [modifica un criterio personalizzato](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span><span class="sxs-lookup"><span data-stu-id="170e6-299">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="170e6-300">**Rappresentazione**</span><span class="sxs-lookup"><span data-stu-id="170e6-300">**Impersonation**</span></span>
   - <span data-ttu-id="170e6-301">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="170e6-301">**Spoof**</span></span>
   - <span data-ttu-id="170e6-302">**Impostazioni avanzate**</span><span class="sxs-lookup"><span data-stu-id="170e6-302">**Advanced settings**</span></span>

   <span data-ttu-id="170e6-303">Le impostazioni seguenti non sono disponibili quando si modifica il criterio predefinito:</span><span class="sxs-lookup"><span data-stu-id="170e6-303">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="170e6-304">È possibile visualizzare la sezione e i valori dell' **impostazione dei criteri** , ma non esiste alcun collegamento di **modifica** , quindi non è possibile modificare le impostazioni (nome del criterio, descrizione e l'utente a cui si applica il criterio, applicabile a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="170e6-304">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="170e6-305">Non è possibile eliminare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="170e6-305">You can't delete the default policy.</span></span>
   - <span data-ttu-id="170e6-306">Non è possibile modificare la priorità del criterio predefinito (viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="170e6-306">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="170e6-307">Nella pagina **modifica il criterio Office365 antiphishing predefinita** , esaminare le impostazioni e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="170e6-307">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="170e6-308">Abilitare o disabilitare i criteri di anti-phishing ATP personalizzati</span><span class="sxs-lookup"><span data-stu-id="170e6-308">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="170e6-309">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="170e6-309">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="170e6-310">Si noti il valore nella colonna **stato** :</span><span class="sxs-lookup"><span data-stu-id="170e6-310">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="170e6-311">Fare scorrere l'interruttore su **disattivato** per disabilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="170e6-311">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="170e6-312">Scorrere l'interruttore **su** attivato per abilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="170e6-312">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="170e6-313">Non è possibile disabilitare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="170e6-313">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="170e6-314">Impostare la priorità dei criteri personalizzati di anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="170e6-314">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="170e6-315">Per impostazione predefinita, ai criteri di anti-phishing ATP viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="170e6-315">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="170e6-316">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="170e6-316">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="170e6-317">Due criteri non possono avere priorità uguale.</span><span class="sxs-lookup"><span data-stu-id="170e6-317">No two policies can have the same priority.</span></span>

<span data-ttu-id="170e6-318">I criteri di anti-phishing ATP personalizzati vengono visualizzati nell'ordine in cui sono stati elaborati (il primo criterio ha il valore di **priorità** 0).</span><span class="sxs-lookup"><span data-stu-id="170e6-318">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="170e6-319">Il criterio anti-phishing predefinito denominato Office365 antiphishing default ha il valore di priorità personalizzato **più basso**e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="170e6-319">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="170e6-320">**Nota**: nel centro sicurezza & conformità è possibile modificare solo la priorità dei criteri di anti-phishing ATP dopo averlo creato.</span><span class="sxs-lookup"><span data-stu-id="170e6-320">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="170e6-321">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phishing (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="170e6-321">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="170e6-322">Per modificare la priorità di un criterio, fare clic su **aumenta priorità** o su **Diminuisci priorità** nelle proprietà del criterio (non è possibile modificare direttamente il numero di **priorità** nel centro sicurezza & conformità).</span><span class="sxs-lookup"><span data-stu-id="170e6-322">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="170e6-323">La modifica della priorità di un criterio ha senso solo se si dispone di più criteri.</span><span class="sxs-lookup"><span data-stu-id="170e6-323">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="170e6-324">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="170e6-324">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="170e6-325">Selezionare il criterio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="170e6-325">Select the policy that you want to modify.</span></span> <span data-ttu-id="170e6-326">Se è già selezionata, deselezionarla e selezionarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="170e6-326">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="170e6-327">Verrà visualizzato il riquadro a comparsa \*\*modifica il criterio \<name\> \*\* .</span><span class="sxs-lookup"><span data-stu-id="170e6-327">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="170e6-328">Il criterio di anti-phishing ATP personalizzato con il valore di **priorità** **0** ha solo il pulsante di **riduzione della priorità** disponibile.</span><span class="sxs-lookup"><span data-stu-id="170e6-328">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="170e6-329">Il criterio di antiphishing personalizzato ATP con il valore di **priorità** più basso (ad esempio, **3**) ha solo il pulsante **aumenta priorità** disponibile.</span><span class="sxs-lookup"><span data-stu-id="170e6-329">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="170e6-330">Se si dispone di tre o più criteri di anti-phishing personalizzati, i criteri tra i valori di priorità più alti e quelli più bassi sono disponibili per i pulsanti **aumenta priorità** e **Riduci priorità** .</span><span class="sxs-lookup"><span data-stu-id="170e6-330">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="170e6-331">Fare clic su **aumenta priorità** o su **Diminuisci priorità** per modificare il valore di **priorità** .</span><span class="sxs-lookup"><span data-stu-id="170e6-331">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="170e6-332">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="170e6-332">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="170e6-333">Utilizzare il Centro sicurezza & conformità per visualizzare i criteri di anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="170e6-333">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="170e6-334">Nel centro sicurezza & conformità e passare a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="170e6-334">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="170e6-335">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="170e6-335">Do one of the following steps:</span></span>

   - <span data-ttu-id="170e6-336">Selezionare un criterio di anti-phishing ATP personalizzato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="170e6-336">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="170e6-337">Se è già selezionata, deselezionarla e selezionarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="170e6-337">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="170e6-338">Fare clic su **criteri predefiniti** per visualizzare i criteri di anti-phishing predefiniti.</span><span class="sxs-lookup"><span data-stu-id="170e6-338">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="170e6-339">Verrà visualizzato il riquadro a comparsa \*\*modifica il criterio \<name\> \*\* , in cui è possibile visualizzare le impostazioni e i valori.</span><span class="sxs-lookup"><span data-stu-id="170e6-339">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="170e6-340">Utilizzare il Centro sicurezza & conformità per rimuovere i criteri di anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="170e6-340">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="170e6-341">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="170e6-341">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="170e6-342">Selezionare il criterio che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="170e6-342">Select the policy that you want to remove.</span></span> <span data-ttu-id="170e6-343">Se è già selezionata, deselezionarla e selezionarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="170e6-343">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="170e6-344">Nel riquadro a comparsa **modifica \<name\> il criterio** visualizzato, fare clic su **Elimina criteri**, quindi fare clic su **Sì** nella finestra di dialogo di avviso visualizzata.</span><span class="sxs-lookup"><span data-stu-id="170e6-344">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="170e6-345">Non è possibile rimuovere il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="170e6-345">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="170e6-346">Utilizzare PowerShell di Exchange Online per configurare i criteri di anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="170e6-346">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="170e6-347">Utilizzo di PowerShell per creare criteri di anti-phishing</span><span class="sxs-lookup"><span data-stu-id="170e6-347">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="170e6-348">La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="170e6-348">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="170e6-349">Creare il criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="170e6-349">Create the anti-phish policy.</span></span>

2. <span data-ttu-id="170e6-350">Creare la regola anti-phishing che specifica i criteri anti-phishing a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="170e6-350">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="170e6-351">**Note**:</span><span class="sxs-lookup"><span data-stu-id="170e6-351">**Notes**:</span></span>

- <span data-ttu-id="170e6-352">È possibile creare una nuova regola anti-phishing e assegnargli un criterio anti-phishing esistente e non associato.</span><span class="sxs-lookup"><span data-stu-id="170e6-352">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="170e6-353">Non è possibile associare una regola anti-phishing a più di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="170e6-353">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="170e6-354">È possibile configurare le impostazioni seguenti sui nuovi criteri di phishing in PowerShell che non sono disponibili nel centro sicurezza & conformità fino a dopo la creazione del criterio:</span><span class="sxs-lookup"><span data-stu-id="170e6-354">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="170e6-355">Creare il nuovo criterio come disabilitato (_attivato_ `$false` nel cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="170e6-355">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>

  - <span data-ttu-id="170e6-356">Impostare la priorità del criterio durante la creazione (_priorità_ _\<Number\>_ ) del cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="170e6-356">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="170e6-357">Un nuovo criterio di phishing creato in PowerShell non è visibile nel centro sicurezza & conformità fino a quando non si assegna il criterio a una regola anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="170e6-357">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="170e6-358">Passaggio 1: utilizzare PowerShell per creare un criterio anti-phishing</span><span class="sxs-lookup"><span data-stu-id="170e6-358">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="170e6-359">Per creare un criterio di phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="170e6-359">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="170e6-360">In questo esempio viene creato il criterio phishing denominato Research Quarantine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="170e6-360">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="170e6-361">Il criterio è abilitato (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="170e6-361">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="170e6-362">La descrizione è: criteri del reparto ricerche.</span><span class="sxs-lookup"><span data-stu-id="170e6-362">The description is: Research department policy.</span></span>
- <span data-ttu-id="170e6-363">Consente la protezione dei domini dell'organizzazione per tutti i domini accettati e la protezione dei domini mirati per fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="170e6-363">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="170e6-364">Specifica Mai Fujito (mfujito@fabrikam.com) come l'utente da proteggere da imitazione.</span><span class="sxs-lookup"><span data-stu-id="170e6-364">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="170e6-365">Abilita l'intelligence della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="170e6-365">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="170e6-366">Consente di abilitare la protezione dall'intelligence della cassetta postale e di specificare l'azione di quarantena.</span><span class="sxs-lookup"><span data-stu-id="170e6-366">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="170e6-367">Consente di abilitare i suggerimenti per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="170e6-367">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="170e6-368">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="170e6-368">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="170e6-369">Passaggio 2: utilizzare PowerShell per creare una regola anti-phishing</span><span class="sxs-lookup"><span data-stu-id="170e6-369">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="170e6-370">Per creare una regola anti-phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="170e6-370">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="170e6-371">In questo esempio viene creata una regola di phishing denominata Research Department con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="170e6-371">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="170e6-372">La regola è associata ai criteri anti-phishing denominati Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="170e6-372">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="170e6-373">La regola viene applicata ai membri del gruppo denominato Research Department.</span><span class="sxs-lookup"><span data-stu-id="170e6-373">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="170e6-374">Poiché non si utilizza il parametro _Priority_ , viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="170e6-374">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="170e6-375">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="170e6-375">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="170e6-376">Utilizzo di PowerShell per visualizzare i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="170e6-376">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="170e6-377">Per visualizzare i criteri anti-phishing esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="170e6-377">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="170e6-378">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri anti-phishing insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="170e6-378">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="170e6-379">In questo esempio vengono restituiti tutti i valori della proprietà per il criterio phishing denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="170e6-379">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="170e6-380">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="170e6-380">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="170e6-381">Utilizzo di PowerShell per visualizzare le regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="170e6-381">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="170e6-382">Per visualizzare le regole anti-phishing esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="170e6-382">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="170e6-383">In questo esempio viene restituito un elenco riepilogativo di tutte le regole anti-phishing insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="170e6-383">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="170e6-384">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="170e6-384">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="170e6-385">In questo esempio vengono restituiti tutti i valori della proprietà per la regola phishing denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="170e6-385">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="170e6-386">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="170e6-386">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="170e6-387">Utilizzo di PowerShell per la modifica dei criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="170e6-387">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="170e6-388">A parte gli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio di phishing in PowerShell come quando si crea il criterio come descritto nel [passaggio 1: utilizzare PowerShell per creare una sezione dei criteri anti-phishing](#step-1-use-powershell-to-create-an-anti-phish-policy) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="170e6-388">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="170e6-389">L'opzione _MakeDefault_ che consente di trasformare il criterio specificato nel criterio predefinito (applicato a tutti, priorità sempre **più bassa** e non è possibile eliminarla) è disponibile solo quando si modifica un criterio di protezione da phishing in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="170e6-389">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="170e6-390">Non è possibile rinominare un criterio anti-phishing (il cmdlet **set-AntiPhishPolicy** non ha un parametro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="170e6-390">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="170e6-391">Quando si rinomina un criterio anti-phishing nel centro sicurezza & Compliance, viene rinominata solo la _regola_anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="170e6-391">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="170e6-392">Per modificare un criterio di phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="170e6-392">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="170e6-393">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="170e6-393">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="170e6-394">Utilizzo di PowerShell per modificare le regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="170e6-394">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="170e6-395">L'unica impostazione che non è disponibile quando si modifica una regola anti-phishing in PowerShell è il parametro _Enabled_ che consente di creare una regola disattivata.</span><span class="sxs-lookup"><span data-stu-id="170e6-395">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="170e6-396">Per abilitare o disabilitare le regole anti-phishing esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="170e6-396">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="170e6-397">In caso contrario, non sono disponibili ulteriori impostazioni quando si modifica una regola anti-phishing in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="170e6-397">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="170e6-398">Le stesse impostazioni sono disponibili quando si crea una regola come descritto nel [passaggio 2: utilizzo di PowerShell per creare una sezione di regola anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="170e6-398">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="170e6-399">Per modificare una regola anti-phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="170e6-399">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="170e6-400">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="170e6-400">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="170e6-401">Utilizzo di PowerShell per abilitare o disabilitare le regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="170e6-401">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="170e6-402">L'abilitazione o disabilitazione di una regola anti-phishing in PowerShell consente di abilitare o disabilitare l'intero criterio anti-phishing (la regola anti-phishing e i criteri di anti-phishing assegnati).</span><span class="sxs-lookup"><span data-stu-id="170e6-402">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="170e6-403">Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="170e6-403">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="170e6-404">Per abilitare o disabilitare una regola anti-phishing in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="170e6-404">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="170e6-405">In questo esempio viene disabilitata la regola anti-phishing denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="170e6-405">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="170e6-406">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="170e6-406">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="170e6-407">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) e [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="170e6-407">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="170e6-408">Utilizzo di PowerShell per impostare la priorità delle regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="170e6-408">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="170e6-409">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="170e6-409">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="170e6-410">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="170e6-410">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="170e6-411">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="170e6-411">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="170e6-412">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="170e6-412">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="170e6-413">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="170e6-413">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="170e6-414">Per impostare la priorità di una regola anti-phishing in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="170e6-414">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="170e6-p143">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="170e6-p143">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="170e6-417">**Note**:</span><span class="sxs-lookup"><span data-stu-id="170e6-417">**Notes**:</span></span>

- <span data-ttu-id="170e6-418">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="170e6-418">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="170e6-419">I criteri predefiniti di phishing non dispongono di una regola anti-phishing corrispondente e hanno sempre il valore di priorità immodificabile **più basso**.</span><span class="sxs-lookup"><span data-stu-id="170e6-419">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="170e6-420">Utilizzo di PowerShell per rimuovere i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="170e6-420">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="170e6-421">Quando si utilizza PowerShell per rimuovere un criterio phishing, la regola anti-phishing corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="170e6-421">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="170e6-422">Per rimuovere un criterio di phishing in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="170e6-422">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="170e6-423">In questo esempio viene rimosso il criterio anti-phishing denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="170e6-423">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="170e6-424">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="170e6-424">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="170e6-425">Utilizzo di PowerShell per rimuovere le regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="170e6-425">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="170e6-426">Quando si utilizza PowerShell per rimuovere una regola anti-phishing, i criteri di anti-phishing corrispondenti non vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="170e6-426">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="170e6-427">Per rimuovere una regola anti-phishing in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="170e6-427">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="170e6-428">In questo esempio viene rimossa la regola anti-phishing denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="170e6-428">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="170e6-429">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="170e6-429">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="170e6-430">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="170e6-430">How do you know these procedures worked?</span></span>

<span data-ttu-id="170e6-431">Per verificare la corretta configurazione dei criteri di anti-phishing ATP, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="170e6-431">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="170e6-432">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="170e6-432">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="170e6-433">Verificare l'elenco dei criteri, i relativi valori di **stato** e i relativi valori di **priorità** .</span><span class="sxs-lookup"><span data-stu-id="170e6-433">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="170e6-434">Per visualizzare ulteriori dettagli, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="170e6-434">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="170e6-435">Selezionare il criterio dall'elenco e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="170e6-435">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="170e6-436">Fare clic su **criteri predefiniti** e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="170e6-436">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="170e6-437">In Exchange Online PowerShell, sostituire \<Name\> con il nome del criterio o della regola ed eseguire il comando riportato di seguito e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="170e6-437">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
