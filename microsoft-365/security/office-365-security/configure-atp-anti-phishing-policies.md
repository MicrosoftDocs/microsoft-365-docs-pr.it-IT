---
title: Configurare i criteri anti-phishing ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come creare, modificare ed eliminare i criteri di anti-phishing avanzati disponibili nelle organizzazioni con Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: c08046bdc9e72bc824dc28acdf2443c9071236a0
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333547"
---
# <a name="configure-atp-anti-phishing-policies"></a><span data-ttu-id="b5623-103">Configurare i criteri anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="b5623-103">Configure ATP anti-phishing policies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b5623-104">I criteri di anti-phishing ATP fanno parte di [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="b5623-104">ATP anti-phishing policies are part of [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="b5623-105">I criteri di anti-phishing ATP consentono di proteggere l'organizzazione da attacchi di phishing basati sulla rappresentazione malevola e altri tipi di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="b5623-105">ATP anti-phishing policies can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="b5623-106">Per ulteriori informazioni sulle differenze tra i criteri di anti-phishing in Exchange Online Protection (EOP) e i criteri di anti-phishing ATP, vedere [protezione anti-phishing](anti-phishing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="b5623-106">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and ATP anti-phishing policies, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="b5623-107">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito del trifosfato di adenosina.</span><span class="sxs-lookup"><span data-stu-id="b5623-107">Admins can view, edit, and configure (but not delete) the default ATP anti-phishing policy.</span></span> <span data-ttu-id="b5623-108">Per una maggiore granularità, è anche possibile creare criteri di anti-phishing ATP personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5623-108">For greater granularity, you can also create custom ATP anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="b5623-109">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).</span><span class="sxs-lookup"><span data-stu-id="b5623-109">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="b5623-110">È possibile configurare i criteri di anti-phishing ATP nel centro sicurezza & Compliance o in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b5623-110">You can configure ATP anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="b5623-111">Per informazioni sulla configurazione dei criteri di anti-phishing più limitati disponibili nelle organizzazioni di protezione di Exchange Online (ovvero le organizzazioni Microsoft 365 senza Office 365 ATP), vedere [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b5623-111">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, Microsoft 365 organizations without Office 365 ATP), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

## <a name="atp-anti-phishing-policies-in-the-security--compliance-center-vs-powershell"></a><span data-ttu-id="b5623-112">Criteri di anti-phishing ATP nel centro sicurezza & Compliance vs PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5623-112">ATP anti-phishing policies in the Security & Compliance Center vs PowerShell</span></span>

<span data-ttu-id="b5623-113">Gli elementi di base di un criterio anti-phishing ATP sono:</span><span class="sxs-lookup"><span data-stu-id="b5623-113">The basic elements of an ATP anti-phishing policy are:</span></span>

- <span data-ttu-id="b5623-114">**Il criterio anti-phishing**: specifica le protezioni di phishing da abilitare o disabilitare e le azioni da applicare.</span><span class="sxs-lookup"><span data-stu-id="b5623-114">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="b5623-115">**La regola phishing**: specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="b5623-115">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="b5623-116">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri di anti-phishing ATP nel centro sicurezza & Compliance:</span><span class="sxs-lookup"><span data-stu-id="b5623-116">The difference between these two elements isn't obvious when you manage ATP anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b5623-117">Quando si crea un criterio, si sta effettivamente creando una regola anti-phishing e il criterio anti-phishing associato contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="b5623-117">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="b5623-118">Quando si modifica un criterio, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatario modificano la regola phishing.</span><span class="sxs-lookup"><span data-stu-id="b5623-118">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="b5623-119">Tutte le altre impostazioni modificano i criteri anti-phishing associati.</span><span class="sxs-lookup"><span data-stu-id="b5623-119">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="b5623-120">Quando si rimuove un criterio, la regola anti-phishing e i criteri anti-phishing associati vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="b5623-120">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="b5623-121">In Exchange Online PowerShell, è possibile gestire il criterio e la regola separatamente.</span><span class="sxs-lookup"><span data-stu-id="b5623-121">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="b5623-122">Per ulteriori informazioni, vedere la sezione [utilizzare Exchange Online PowerShell per configurare i criteri di anti-phishing ATP](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b5623-122">For more information, see the [Use Exchange Online PowerShell to configure ATP anti-phishing policies](#use-exchange-online-powershell-to-configure-atp-anti-phishing-policies) section later in this topic.</span></span>

<span data-ttu-id="b5623-123">Ogni organizzazione ATP di Office 365 ha un criterio anti-phishing incorporato denominato Office365 antiphishing default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="b5623-123">Every Office 365 ATP organization has a built-in ATP anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="b5623-124">Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se non è presente alcuna regola anti-phishing (filtri destinatario) associata al criterio.</span><span class="sxs-lookup"><span data-stu-id="b5623-124">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="b5623-125">Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="b5623-125">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="b5623-126">Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="b5623-126">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="b5623-127">Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="b5623-127">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="b5623-128">Per aumentare l'efficacia della protezione anti-phishing, è possibile creare criteri di anti-phishing ATP personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="b5623-128">To increase the effectiveness of anti-phishing protection, you can create custom ATP anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b5623-129">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="b5623-129">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b5623-130">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b5623-130">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b5623-131">Per accedere direttamente alla pagina **anti-phishing ATP** , utilizzare <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="b5623-131">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="b5623-132">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b5623-132">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b5623-133">Prima di poter eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5623-133">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="b5623-134">Per aggiungere, modificare ed eliminare i criteri di anti-phishing ATP, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5623-134">To add, modify, and delete ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="b5623-135">**Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b5623-135">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="b5623-136">**Gestione organizzazione** o **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="b5623-136">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="b5623-137">Per l'accesso in sola lettura ai criteri di anti-phishing ATP, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5623-137">For read-only access to ATP anti-phishing policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="b5623-138">**Lettore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b5623-138">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="b5623-139">**Gestione organizzazione in sola lettura** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="b5623-139">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="b5623-140">Per le impostazioni consigliate per i criteri di anti-phishing ATP, vedere [impostazioni dei criteri di anti-phishing ATP](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="b5623-140">For our recommended settings for ATP anti-phishing policies, see [ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#atp-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="b5623-141">Consentire l'applicazione di un criterio nuovo o aggiornato fino a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="b5623-141">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="b5623-142">Per informazioni su dove vengono applicati i criteri di anti-phishing nella pipeline dei filtri, vedere [ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="b5623-142">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-atp-anti-phishing-policies"></a><span data-ttu-id="b5623-143">Utilizzare il Centro sicurezza & conformità per creare criteri di anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="b5623-143">Use the Security & Compliance Center to create ATP anti-phishing policies</span></span>

<span data-ttu-id="b5623-144">La creazione di un criterio di anti-phishing ATP personalizzato nel centro sicurezza & conformità crea la regola anti-phishing e i criteri anti-phishing associati contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="b5623-144">Creating a custom ATP anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="b5623-145">Quando si crea un criterio di anti-phishing ATP, è possibile specificare solo il nome, la descrizione e il filtro destinatario che identifica gli utenti a cui si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="b5623-145">When you create an ATP anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="b5623-146">Dopo aver creato il criterio, è possibile modificare il criterio per modificare o rivedere le impostazioni di anti-phishing predefinite.</span><span class="sxs-lookup"><span data-stu-id="b5623-146">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="b5623-147">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b5623-147">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b5623-148">Nella pagina **anti-phishing** fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="b5623-148">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="b5623-149">Verrà visualizzata la procedura guidata **Crea un nuovo criterio anti-phishing** .</span><span class="sxs-lookup"><span data-stu-id="b5623-149">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="b5623-150">Nella pagina **Name Your Policy** , configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b5623-150">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="b5623-151">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="b5623-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="b5623-152">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="b5623-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="b5623-153">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b5623-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b5623-154">Nella pagina **applicata alla** pagina che viene visualizzata, identificare i destinatari interni ai quali si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="b5623-154">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="b5623-155">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b5623-155">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b5623-156">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="b5623-156">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b5623-157">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="b5623-157">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="b5623-158">Fare clic su **Aggiungi condizione**.</span><span class="sxs-lookup"><span data-stu-id="b5623-158">Click **Add a condition**.</span></span> <span data-ttu-id="b5623-159">Nell'elenco a discesa che viene visualizzato, selezionare una condizione in **applicato se**:</span><span class="sxs-lookup"><span data-stu-id="b5623-159">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="b5623-160">**Il destinatario è**: consente di specificare una o più cassette postali, utenti di posta elettronica o contatti di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5623-160">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="b5623-161">**Il destinatario è un membro di**: consente di specificare uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5623-161">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="b5623-162">**Il dominio del destinatario è**: consente di specificare i destinatari in uno o più dei domini accettati configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b5623-162">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="b5623-163">Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con una **qualsiasi di queste** caselle.</span><span class="sxs-lookup"><span data-stu-id="b5623-163">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="b5623-164">Fare clic nella casella e scorrere l'elenco di valori da selezionare.</span><span class="sxs-lookup"><span data-stu-id="b5623-164">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="b5623-165">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="b5623-165">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="b5623-166">Per aggiungere ulteriori valori, fare clic in un'area vuota nella casella.</span><span class="sxs-lookup"><span data-stu-id="b5623-166">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="b5623-167">Per rimuovere singole voci, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sul valore.</span><span class="sxs-lookup"><span data-stu-id="b5623-167">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="b5623-168">Per rimuovere l'intera condizione, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sulla condizione.</span><span class="sxs-lookup"><span data-stu-id="b5623-168">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="b5623-169">Per aggiungere una condizione aggiuntiva, fare clic su **Aggiungi condizione** e selezionare un valore restante in **applicato se**.</span><span class="sxs-lookup"><span data-stu-id="b5623-169">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="b5623-170">Per aggiungere eccezioni, fare clic su **Aggiungi condizione** e selezionare un'eccezione in **except if**.</span><span class="sxs-lookup"><span data-stu-id="b5623-170">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="b5623-171">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="b5623-171">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="b5623-172">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b5623-172">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b5623-173">Nella pagina **Verifica le impostazioni** che viene visualizzata, esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="b5623-173">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="b5623-174">È possibile fare clic su **modifica** su ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="b5623-174">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="b5623-175">Al termine, fare clic su **crea questo criterio**.</span><span class="sxs-lookup"><span data-stu-id="b5623-175">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="b5623-176">Fare clic su **OK** nella finestra di dialogo di conferma che viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="b5623-176">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="b5623-177">Dopo aver creato il criterio anti-phishing ATP con queste impostazioni generali, utilizzare le istruzioni riportate nella sezione successiva per configurare le impostazioni di protezione nel criterio.</span><span class="sxs-lookup"><span data-stu-id="b5623-177">After you create the ATP anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-atp-anti-phishing-policies"></a><span data-ttu-id="b5623-178">Utilizzare il Centro sicurezza & conformità per modificare i criteri di anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="b5623-178">Use the Security & Compliance Center to modify ATP anti-phishing policies</span></span>

<span data-ttu-id="b5623-179">Utilizzare le procedure seguenti per modificare i criteri di anti-phishing ATP: un nuovo criterio creato o criteri esistenti già personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b5623-179">Use the following procedures to modify ATP anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="b5623-180">Se non si è ancora presenti, aprire il Centro sicurezza & compliance e passare al criterio di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b5623-180">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b5623-181">Selezionare il criterio di anti-phishing ATP personalizzato che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b5623-181">Select the custom ATP anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="b5623-182">Se è già selezionata, deselezionarla e selezionarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="b5623-182">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="b5623-183">Verrà visualizzato il riquadro a comparsa \*\*modifica il criterio \<name\> \*\* .</span><span class="sxs-lookup"><span data-stu-id="b5623-183">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="b5623-184">Fare clic su **modifica** in qualsiasi sezione consente di accedere alle impostazioni di tale sezione.</span><span class="sxs-lookup"><span data-stu-id="b5623-184">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="b5623-185">I passaggi seguenti sono presentati nell'ordine in cui vengono visualizzate le sezioni, ma non sono sequenziali (è possibile selezionare e modificare le sezioni in qualsiasi ordine).</span><span class="sxs-lookup"><span data-stu-id="b5623-185">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="b5623-186">Dopo aver fatto clic su **modifica** in una sezione, le impostazioni disponibili vengono presentate in un formato di procedura guidata, ma è possibile passare all'interno delle pagine in qualsiasi ordine e fare clic su **Salva** in qualsiasi pagina oppure **annullare** o **chiudere** l' ![ icona Chiudi ](../../media/scc-remove-icon.png) per tornare alla pagina \*\*modifica il criterio \<name\> \*\* (non è necessario visitare l'ultima pagina della procedura guidata per salvare o lasciare).</span><span class="sxs-lookup"><span data-stu-id="b5623-186">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="b5623-187">**Impostazione dei criteri**: fare clic su **modifica** per modificare le stesse impostazioni disponibili quando è stato [creato il criterio](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) nella sezione precedente:</span><span class="sxs-lookup"><span data-stu-id="b5623-187">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-atp-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="b5623-188">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b5623-188">**Name**</span></span>
   - <span data-ttu-id="b5623-189">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b5623-189">**Description**</span></span>
   - <span data-ttu-id="b5623-190">**Applicato a**</span><span class="sxs-lookup"><span data-stu-id="b5623-190">**Applied to**</span></span>
   - <span data-ttu-id="b5623-191">**Esaminare le impostazioni**</span><span class="sxs-lookup"><span data-stu-id="b5623-191">**Review your settings**</span></span>

   <span data-ttu-id="b5623-192">Al termine, fare clic su **Salva** su qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="b5623-192">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="b5623-193">**Rappresentazione**: fare clic su **modifica** per modificare i mittenti protetti e i domini protetti nel criterio.</span><span class="sxs-lookup"><span data-stu-id="b5623-193">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="b5623-194">Queste impostazioni sono una condizione per i criteri che identificano i mittenti falsificati da cercare (singolarmente o in base al dominio) nell'indirizzo mittente dei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="b5623-194">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="b5623-195">Per ulteriori informazioni, vedere [impostazioni di rappresentazione nei criteri di anti-phishing ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="b5623-195">For more information, see [Impersonation settings in ATP anti-phishing policies](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="b5623-196">**Aggiungere gli utenti a Protect**: il valore predefinito è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="b5623-196">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="b5623-197">Per attivarla, scorrere l' **interruttore su attivato**e quindi fare clic sul pulsante **Aggiungi utente** visualizzato.</span><span class="sxs-lookup"><span data-stu-id="b5623-197">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="b5623-198">Nel riquadro a comparsa **utente aggiunto** che viene visualizzato, configurare i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b5623-198">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="b5623-199">**Indirizzo di posta elettronica**:</span><span class="sxs-lookup"><span data-stu-id="b5623-199">**Email address**:</span></span>

        - <span data-ttu-id="b5623-200">Fare clic nella casella e scorrere l'elenco degli utenti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="b5623-200">Click in the box and scroll through the list of users to select.</span></span>
        - <span data-ttu-id="b5623-201">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="b5623-201">Click in the box and start typing to filter the list and select a user.</span></span>
        - <span data-ttu-id="b5623-202">Per rimuovere una voce, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sull'utente.</span><span class="sxs-lookup"><span data-stu-id="b5623-202">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="b5623-203">**Nome**: questo valore viene popolato in base all'indirizzo di posta elettronica selezionato, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="b5623-203">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="b5623-204">Al termine, fare clic su **Salva** su qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="b5623-204">When you're finished, click **Save** on any page.</span></span>

    <span data-ttu-id="b5623-205">Per modificare una voce esistente, selezionare l'utente protetto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b5623-205">To edit an existing entry, select the protected user in the list.</span></span>

   - <span data-ttu-id="b5623-206">**Aggiungere i domini da proteggere**: configurare una o entrambe le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5623-206">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="b5623-207">**Includere automaticamente i domini che possiedo**: il valore predefinito è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="b5623-207">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="b5623-208">Per attivarla, fare scorrere l'interruttore **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="b5623-208">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="b5623-209">**Includi domini personalizzati**: il valore predefinito è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="b5623-209">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="b5623-210">Per attivarla, scorrere l'interruttore **su**attivato e nella casella **Aggiungi domini** immettere il nome di dominio (ad esempio, contoso.com), premere invio e ripetere il secondo caso.</span><span class="sxs-lookup"><span data-stu-id="b5623-210">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

       <span data-ttu-id="b5623-211">**Nota**: nel centro sicurezza & conformità, è possibile immettere un massimo di 20 domini.</span><span class="sxs-lookup"><span data-stu-id="b5623-211">**Note**: In the Security & Compliance Center, you can enter a maximum of 20 domains.</span></span> <span data-ttu-id="b5623-212">In Exchange Online PowerShell, è possibile immettere un massimo di 50 domini.</span><span class="sxs-lookup"><span data-stu-id="b5623-212">In Exchange Online PowerShell, you can enter a maximum of 50 domains.</span></span>

   - <span data-ttu-id="b5623-213">**Azioni**: fare clic su **modifica**</span><span class="sxs-lookup"><span data-stu-id="b5623-213">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="b5623-214">**Se il messaggio di posta elettronica viene inviato da un utente rappresentato**: configurare una delle seguenti azioni per i messaggi in cui il mittente falsificato è uno degli utenti protetti specificati in **Add Users to Protect**:</span><span class="sxs-lookup"><span data-stu-id="b5623-214">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="b5623-215">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="b5623-215">**Don't apply any action**</span></span>
       - <span data-ttu-id="b5623-216">**Reindirizza il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="b5623-216">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="b5623-217">**Sposta messaggio nella cartella Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="b5623-217">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="b5623-218">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="b5623-218">**Quarantine the message**</span></span>
       - <span data-ttu-id="b5623-219">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="b5623-219">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="b5623-220">**Eliminare il messaggio prima di essere recapitato**</span><span class="sxs-lookup"><span data-stu-id="b5623-220">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="b5623-221">**Se il messaggio di posta elettronica viene inviato da un dominio rappresentato**: configurare una delle seguenti azioni per i messaggi in cui il mittente contraffatto si trova in uno dei domini protetti specificati in **Aggiungi domini da proteggere**:</span><span class="sxs-lookup"><span data-stu-id="b5623-221">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

     - <span data-ttu-id="b5623-222">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="b5623-222">**Don't apply any action**</span></span>
     - <span data-ttu-id="b5623-223">**Reindirizza il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="b5623-223">**Redirect message to other email addresses**</span></span>
     - <span data-ttu-id="b5623-224">**Sposta messaggio nella cartella Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="b5623-224">**Move message to Junk Email folder**</span></span>
     - <span data-ttu-id="b5623-225">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="b5623-225">**Quarantine the message**</span></span>
     - <span data-ttu-id="b5623-226">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="b5623-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
     - <span data-ttu-id="b5623-227">**Eliminare il messaggio prima di essere recapitato**</span><span class="sxs-lookup"><span data-stu-id="b5623-227">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="b5623-228">Fare clic **su Attiva suggerimenti per la sicurezza della rappresentazione** e configurare una delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b5623-228">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="b5623-229">**Mostra suggerimento per gli utenti rappresentati**: il valore predefinito è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="b5623-229">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="b5623-230">Per attivarla, fare scorrere l'interruttore **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="b5623-230">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="b5623-231">**Mostra suggerimento per i domini rappresentati**: il valore predefinito è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="b5623-231">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="b5623-232">Per attivarla, fare scorrere l'interruttore **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="b5623-232">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="b5623-233">**Mostra suggerimento per i caratteri insoliti**: il valore predefinito è **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="b5623-233">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="b5623-234">Per attivarla, fare scorrere l'interruttore **su**attivato.</span><span class="sxs-lookup"><span data-stu-id="b5623-234">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="b5623-235">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b5623-235">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="b5623-236">**Intelligence delle cassette postali**:</span><span class="sxs-lookup"><span data-stu-id="b5623-236">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="b5623-237">Abilitare la funzionalità di **Intelligence delle cassette postali?**: il valore predefinito è **on**.</span><span class="sxs-lookup"><span data-stu-id="b5623-237">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="b5623-238">Per disattivarla, fare scorrere l'interruttore su **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="b5623-238">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="b5623-239">**Abilitare la protezione della rappresentazione basata sull'Intelligence delle cassette postali?**: questa impostazione è disponibile solo se abilitare la funzionalità **di** **Intelligence delle cassette postali?** è attiva.</span><span class="sxs-lookup"><span data-stu-id="b5623-239">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="b5623-240">**Se il messaggio di posta elettronica viene inviato da un utente rappresentato**, è possibile specificare una delle seguenti azioni da intraprendere per i messaggi che non riescono a utilizzare l'intelligence delle cassette postali (le stesse azioni disponibili per gli utenti protetti e i domini protetti):</span><span class="sxs-lookup"><span data-stu-id="b5623-240">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="b5623-241">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="b5623-241">**Don't apply any action**</span></span>
       - <span data-ttu-id="b5623-242">**Reindirizza il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="b5623-242">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="b5623-243">**Sposta messaggio nella cartella Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="b5623-243">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="b5623-244">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="b5623-244">**Quarantine the message**</span></span>
       - <span data-ttu-id="b5623-245">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="b5623-245">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="b5623-246">**Eliminare il messaggio prima di essere recapitato**</span><span class="sxs-lookup"><span data-stu-id="b5623-246">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="b5623-247">**Aggiungere i domini e i mittenti attendibili**: specificare le eccezioni per il criterio:</span><span class="sxs-lookup"><span data-stu-id="b5623-247">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="b5623-248">**Mittenti attendibili**:</span><span class="sxs-lookup"><span data-stu-id="b5623-248">**Trusted senders**:</span></span>

       - <span data-ttu-id="b5623-249">Fare clic nella casella e scorrere l'elenco degli utenti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="b5623-249">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="b5623-250">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="b5623-250">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="b5623-251">Per rimuovere una voce, fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/scc-remove-icon.png) sull'utente.</span><span class="sxs-lookup"><span data-stu-id="b5623-251">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="b5623-252">**Domini attendibili**: immettere il nome di dominio (ad esempio, contoso.com), premere invio e ripetere se necessario.</span><span class="sxs-lookup"><span data-stu-id="b5623-252">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="b5623-253">**Esaminare le impostazioni**: invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="b5623-253">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="b5623-254">È possibile fare clic su **modifica** in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="b5623-254">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="b5623-255">È possibile attivare o **disattivare** le seguenti impostazioni **direttamente in questa** pagina:</span><span class="sxs-lookup"><span data-stu-id="b5623-255">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="b5623-256">**Utenti protetti**</span><span class="sxs-lookup"><span data-stu-id="b5623-256">**Protected users**</span></span>
       - <span data-ttu-id="b5623-257">**Domini protetti** \> **Includere domini personali**</span><span class="sxs-lookup"><span data-stu-id="b5623-257">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="b5623-258">**Domini protetti** \> **Domini protetti** (domini personalizzati)</span><span class="sxs-lookup"><span data-stu-id="b5623-258">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="b5623-259">**Intelligence della cassetta postale**</span><span class="sxs-lookup"><span data-stu-id="b5623-259">**Mailbox intelligence**</span></span>

   <span data-ttu-id="b5623-260">Al termine, fare clic su **Salva** su qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="b5623-260">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="b5623-261">**Spoof**: fare clic su **modifica** per abilitare o disabilitare l'intelligence di spoofing, abilitare l'identificazione dei mittenti non autenticati in Outlook attivato o disattivato e configurare l'azione da applicare ai messaggi provenienti da mittenti bloccati falsificati.</span><span class="sxs-lookup"><span data-stu-id="b5623-261">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="b5623-262">Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="b5623-262">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="b5623-263">Si noti che le stesse impostazioni sono disponibili anche nei criteri di anti-phishing in EOP.</span><span class="sxs-lookup"><span data-stu-id="b5623-263">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="b5623-264">**Impostazioni del filtro di spoofing**: il valore predefinito **è attivato**e si consiglia di lasciarlo acceso.</span><span class="sxs-lookup"><span data-stu-id="b5623-264">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="b5623-265">Per disattivarla, fare scorrere l'interruttore su **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="b5623-265">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="b5623-266">Per ulteriori informazioni, vedere [Configure Spoofing Intelligence in EOP](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="b5623-266">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="b5623-267">Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Microsoft 365; è invece possibile abilitare il filtro avanzato per i connettori.</span><span class="sxs-lookup"><span data-stu-id="b5623-267">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="b5623-268">Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="b5623-268">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="b5623-269">**Abilita funzionalità mittente non autenticato** **: il valore predefinito è**attivato.</span><span class="sxs-lookup"><span data-stu-id="b5623-269">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="b5623-270">Per disattivarla, fare scorrere l'interruttore su **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="b5623-270">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="b5623-271">**Azioni**: specificare l'azione da intraprendere per i messaggi che non superano l'intelligence spoof:</span><span class="sxs-lookup"><span data-stu-id="b5623-271">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="b5623-272">**Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio**:</span><span class="sxs-lookup"><span data-stu-id="b5623-272">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="b5623-273">**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="b5623-273">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="b5623-274">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="b5623-274">**Quarantine the message**</span></span>

   - <span data-ttu-id="b5623-275">**Esaminare le impostazioni**: invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="b5623-275">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="b5623-276">È possibile fare clic su **modifica** in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="b5623-276">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="b5623-277">È possibile attivare o **disattivare** le seguenti impostazioni **direttamente in questa** pagina:</span><span class="sxs-lookup"><span data-stu-id="b5623-277">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="b5623-278">**Abilitare la protezione antispoofing**</span><span class="sxs-lookup"><span data-stu-id="b5623-278">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="b5623-279">**Abilitare la funzionalità mittente non autenticato**</span><span class="sxs-lookup"><span data-stu-id="b5623-279">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="b5623-280">Al termine, fare clic su **Salva** su qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="b5623-280">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="b5623-281">**Impostazioni avanzate**: fare clic su **modifica** per configurare le soglie di phishing avanzate.</span><span class="sxs-lookup"><span data-stu-id="b5623-281">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="b5623-282">Per ulteriori informazioni, vedere [soglie di phishing avanzate nei criteri di anti-phishing ATP](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span><span class="sxs-lookup"><span data-stu-id="b5623-282">For more information, see [Advanced phishing thresholds in ATP anti-phishing policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies).</span></span>

   - <span data-ttu-id="b5623-283">**Soglie di phishing avanzate**: selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="b5623-283">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="b5623-284">**1-standard** (questo è il valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="b5623-284">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="b5623-285">**2-aggressivo**</span><span class="sxs-lookup"><span data-stu-id="b5623-285">**2 - Aggressive**</span></span>
   - <span data-ttu-id="b5623-286">**3-maggiore aggressività**</span><span class="sxs-lookup"><span data-stu-id="b5623-286">**3 - More aggressive**</span></span>
   - <span data-ttu-id="b5623-287">**4-la più aggressiva**</span><span class="sxs-lookup"><span data-stu-id="b5623-287">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="b5623-288">**Esaminare le impostazioni**: fare clic su **modifica** per tornare alla pagina **soglie di phishing avanzate** .</span><span class="sxs-lookup"><span data-stu-id="b5623-288">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="b5623-289">Al termine, fare clic su **Salva** in una delle pagine.</span><span class="sxs-lookup"><span data-stu-id="b5623-289">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="b5623-290">Tornare alla pagina \*\*modifica il criterio \<Name\> \*\* , rivedere le impostazioni, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b5623-290">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-atp-anti-phishing-policy"></a><span data-ttu-id="b5623-291">Utilizzare il Centro sicurezza & conformità per modificare il criterio anti-phishing predefinito di ATP</span><span class="sxs-lookup"><span data-stu-id="b5623-291">Use the Security & Compliance Center to modify the default ATP anti-phishing policy</span></span>

<span data-ttu-id="b5623-292">Il criterio anti-phishing ATP predefinito è denominato Office365 antiphishing default e non viene visualizzato nell'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="b5623-292">The default ATP anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="b5623-293">Per modificare i criteri di anti-phishing predefiniti, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5623-293">To modify the default ATP anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="b5623-294">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b5623-294">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b5623-295">Nella pagina **anti-phishing** fare clic su **criteri predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="b5623-295">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="b5623-296">Viene visualizzata la pagina **modifica il criterio Office365 antiphishing predefinita** .</span><span class="sxs-lookup"><span data-stu-id="b5623-296">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="b5623-297">Sono disponibili le sezioni seguenti, che contengono impostazioni identiche per quando si [modifica un criterio personalizzato](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span><span class="sxs-lookup"><span data-stu-id="b5623-297">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-atp-anti-phishing-policies):</span></span>

   - <span data-ttu-id="b5623-298">**Rappresentazione**</span><span class="sxs-lookup"><span data-stu-id="b5623-298">**Impersonation**</span></span>
   - <span data-ttu-id="b5623-299">**Spoof**</span><span class="sxs-lookup"><span data-stu-id="b5623-299">**Spoof**</span></span>
   - <span data-ttu-id="b5623-300">**Impostazioni avanzate**</span><span class="sxs-lookup"><span data-stu-id="b5623-300">**Advanced settings**</span></span>

   <span data-ttu-id="b5623-301">Le impostazioni seguenti non sono disponibili quando si modifica il criterio predefinito:</span><span class="sxs-lookup"><span data-stu-id="b5623-301">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="b5623-302">È possibile visualizzare la sezione e i valori dell' **impostazione dei criteri** , ma non esiste alcun collegamento di **modifica** , quindi non è possibile modificare le impostazioni (nome del criterio, descrizione e l'utente a cui si applica il criterio, applicabile a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="b5623-302">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="b5623-303">Non è possibile eliminare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="b5623-303">You can't delete the default policy.</span></span>
   - <span data-ttu-id="b5623-304">Non è possibile modificare la priorità del criterio predefinito (viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="b5623-304">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="b5623-305">Nella pagina **modifica il criterio Office365 antiphishing predefinita** , esaminare le impostazioni e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b5623-305">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-atp-anti-phishing-policies"></a><span data-ttu-id="b5623-306">Abilitare o disabilitare i criteri di anti-phishing ATP personalizzati</span><span class="sxs-lookup"><span data-stu-id="b5623-306">Enable or disable custom ATP anti-phishing policies</span></span>

1. <span data-ttu-id="b5623-307">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b5623-307">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b5623-308">Si noti il valore nella colonna **stato** :</span><span class="sxs-lookup"><span data-stu-id="b5623-308">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="b5623-309">Fare scorrere l'interruttore su **disattivato** per disabilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="b5623-309">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="b5623-310">Scorrere l'interruttore **su** attivato per abilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="b5623-310">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="b5623-311">Non è possibile disabilitare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="b5623-311">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-atp-anti-phishing-policies"></a><span data-ttu-id="b5623-312">Impostare la priorità dei criteri personalizzati di anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="b5623-312">Set the priority of custom ATP anti-phishing policies</span></span>

<span data-ttu-id="b5623-313">Per impostazione predefinita, ai criteri di anti-phishing ATP viene assegnata una priorità che si basa sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="b5623-313">By default, ATP anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="b5623-314">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="b5623-314">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="b5623-315">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="b5623-315">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="b5623-316">Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="b5623-316">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="b5623-317">I criteri di anti-phishing ATP personalizzati vengono visualizzati nell'ordine in cui sono stati elaborati (il primo criterio ha il valore di **priorità** 0).</span><span class="sxs-lookup"><span data-stu-id="b5623-317">Custom ATP anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="b5623-318">Il criterio anti-phishing predefinito denominato Office365 antiphishing default ha il valore di priorità personalizzato **più basso**e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="b5623-318">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="b5623-319">**Nota**: nel centro sicurezza & conformità è possibile modificare solo la priorità dei criteri di anti-phishing ATP dopo averlo creato.</span><span class="sxs-lookup"><span data-stu-id="b5623-319">**Note**: In the Security & Compliance Center, you can only change the priority of the ATP anti-phishing policy after you create it.</span></span> <span data-ttu-id="b5623-320">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phishing (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="b5623-320">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="b5623-321">Per modificare la priorità di un criterio, fare clic su **aumenta priorità** o su **Diminuisci priorità** nelle proprietà del criterio (non è possibile modificare direttamente il numero di **priorità** nel centro sicurezza & conformità).</span><span class="sxs-lookup"><span data-stu-id="b5623-321">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="b5623-322">La modifica della priorità di un criterio ha senso solo se si dispone di più criteri.</span><span class="sxs-lookup"><span data-stu-id="b5623-322">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="b5623-323">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b5623-323">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b5623-324">Selezionare il criterio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="b5623-324">Select the policy that you want to modify.</span></span> <span data-ttu-id="b5623-325">Se è già selezionata, deselezionarla e selezionarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="b5623-325">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="b5623-326">Verrà visualizzato il riquadro a comparsa \*\*modifica il criterio \<name\> \*\* .</span><span class="sxs-lookup"><span data-stu-id="b5623-326">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="b5623-327">Il criterio di anti-phishing ATP personalizzato con il valore di **priorità** **0** ha solo il pulsante di **riduzione della priorità** disponibile.</span><span class="sxs-lookup"><span data-stu-id="b5623-327">The custom ATP anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="b5623-328">Il criterio di antiphishing personalizzato ATP con il valore di **priorità** più basso (ad esempio, **3**) ha solo il pulsante **aumenta priorità** disponibile.</span><span class="sxs-lookup"><span data-stu-id="b5623-328">The custom ATP anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="b5623-329">Se si dispone di tre o più criteri di anti-phishing personalizzati, i criteri tra i valori di priorità più alti e quelli più bassi sono disponibili per i pulsanti **aumenta priorità** e **Riduci priorità** .</span><span class="sxs-lookup"><span data-stu-id="b5623-329">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="b5623-330">Fare clic su **aumenta priorità** o su **Diminuisci priorità** per modificare il valore di **priorità** .</span><span class="sxs-lookup"><span data-stu-id="b5623-330">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="b5623-331">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b5623-331">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-atp-anti-phishing-policies"></a><span data-ttu-id="b5623-332">Utilizzare il Centro sicurezza & conformità per visualizzare i criteri di anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="b5623-332">Use the Security & Compliance Center to view ATP anti-phishing policies</span></span>

1. <span data-ttu-id="b5623-333">Nel centro sicurezza & conformità e passare a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b5623-333">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b5623-334">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5623-334">Do one of the following steps:</span></span>

   - <span data-ttu-id="b5623-335">Selezionare un criterio di anti-phishing ATP personalizzato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="b5623-335">Select a custom ATP anti-phishing policy that you want to view.</span></span> <span data-ttu-id="b5623-336">Se è già selezionata, deselezionarla e selezionarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="b5623-336">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="b5623-337">Fare clic su **criteri predefiniti** per visualizzare i criteri di anti-phishing predefiniti.</span><span class="sxs-lookup"><span data-stu-id="b5623-337">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="b5623-338">Verrà visualizzato il riquadro a comparsa \*\*modifica il criterio \<name\> \*\* , in cui è possibile visualizzare le impostazioni e i valori.</span><span class="sxs-lookup"><span data-stu-id="b5623-338">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-atp-anti-phishing-policies"></a><span data-ttu-id="b5623-339">Utilizzare il Centro sicurezza & conformità per rimuovere i criteri di anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="b5623-339">Use the Security & Compliance Center to remove ATP anti-phishing policies</span></span>

1. <span data-ttu-id="b5623-340">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b5623-340">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="b5623-341">Selezionare il criterio che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="b5623-341">Select the policy that you want to remove.</span></span> <span data-ttu-id="b5623-342">Se è già selezionata, deselezionarla e selezionarla di nuovo.</span><span class="sxs-lookup"><span data-stu-id="b5623-342">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="b5623-343">Nel riquadro a comparsa **modifica \<name\> il criterio** visualizzato, fare clic su **Elimina criteri**, quindi fare clic su **Sì** nella finestra di dialogo di avviso visualizzata.</span><span class="sxs-lookup"><span data-stu-id="b5623-343">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="b5623-344">Non è possibile rimuovere il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="b5623-344">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-atp-anti-phishing-policies"></a><span data-ttu-id="b5623-345">Utilizzare PowerShell di Exchange Online per configurare i criteri di anti-phishing ATP</span><span class="sxs-lookup"><span data-stu-id="b5623-345">Use Exchange Online PowerShell to configure ATP anti-phishing policies</span></span>

<span data-ttu-id="b5623-346">Come descritto in precedenza, un criterio di protezione da posta indesiderata ATP è costituito da un criterio anti-phishing e da una regola anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="b5623-346">As previously described, an ATP anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="b5623-347">In Exchange Online PowerShell, la differenza tra i criteri anti-phishing e le regole anti-phishing è evidente.</span><span class="sxs-lookup"><span data-stu-id="b5623-347">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="b5623-348">Per gestire i criteri anti-phishing è possibile utilizzare i cmdlet \*\* \* -AntiPhishPolicy\*\* e gestire le regole di anti-phishing utilizzando i cmdlet \*\* \* -AntiPhishRule\*\* .</span><span class="sxs-lookup"><span data-stu-id="b5623-348">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="b5623-349">In PowerShell, è necessario creare innanzitutto il criterio phishing, quindi creare la regola anti-phishing che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="b5623-349">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="b5623-350">In PowerShell, è possibile modificare le impostazioni nel criterio di phishing e la regola anti-phishing separatamente.</span><span class="sxs-lookup"><span data-stu-id="b5623-350">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="b5623-351">Quando si rimuove un criterio di phishing da PowerShell, la regola anti-phishing corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="b5623-351">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="b5623-352">Utilizzo di PowerShell per creare criteri di anti-phishing</span><span class="sxs-lookup"><span data-stu-id="b5623-352">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="b5623-353">La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="b5623-353">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="b5623-354">Creare il criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="b5623-354">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="b5623-355">Creare la regola anti-phishing che specifica i criteri anti-phishing a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="b5623-355">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="b5623-356">**Note**:</span><span class="sxs-lookup"><span data-stu-id="b5623-356">**Notes**:</span></span>

- <span data-ttu-id="b5623-357">È possibile creare una nuova regola anti-phishing e assegnargli un criterio anti-phishing esistente e non associato.</span><span class="sxs-lookup"><span data-stu-id="b5623-357">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="b5623-358">Non è possibile associare una regola anti-phishing a più di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="b5623-358">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="b5623-359">È possibile configurare le impostazioni seguenti sui nuovi criteri di phishing in PowerShell che non sono disponibili nel centro sicurezza & conformità fino a dopo la creazione del criterio:</span><span class="sxs-lookup"><span data-stu-id="b5623-359">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="b5623-360">Creare il nuovo criterio come disabilitato (_attivato_ `$false` nel cmdlet **New-AntiPhishRule** ).</span><span class="sxs-lookup"><span data-stu-id="b5623-360">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="b5623-361">Impostare la priorità del criterio durante la creazione (_priorità_ _\<Number\>_ ) del cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="b5623-361">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="b5623-362">Un nuovo criterio di phishing creato in PowerShell non è visibile nel centro sicurezza & conformità fino a quando non si assegna il criterio a una regola anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="b5623-362">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="b5623-363">Passaggio 1: utilizzare PowerShell per creare un criterio anti-phishing</span><span class="sxs-lookup"><span data-stu-id="b5623-363">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="b5623-364">Per creare un criterio di phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b5623-364">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="b5623-365">In questo esempio viene creato il criterio phishing denominato Research Quarantine con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b5623-365">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="b5623-366">Il criterio è abilitato (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="b5623-366">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="b5623-367">La descrizione è: criteri del reparto ricerche.</span><span class="sxs-lookup"><span data-stu-id="b5623-367">The description is: Research department policy.</span></span>
- <span data-ttu-id="b5623-368">Consente la protezione dei domini dell'organizzazione per tutti i domini accettati e la protezione dei domini mirati per fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="b5623-368">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="b5623-369">Specifica Mai Fujito (mfujito@fabrikam.com) come l'utente da proteggere da imitazione.</span><span class="sxs-lookup"><span data-stu-id="b5623-369">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="b5623-370">Abilita l'intelligence della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="b5623-370">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="b5623-371">Consente di abilitare la protezione dall'intelligence della cassetta postale e di specificare l'azione di quarantena.</span><span class="sxs-lookup"><span data-stu-id="b5623-371">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="b5623-372">Consente di abilitare i suggerimenti per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b5623-372">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="b5623-373">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="b5623-373">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="b5623-374">Passaggio 2: utilizzare PowerShell per creare una regola anti-phishing</span><span class="sxs-lookup"><span data-stu-id="b5623-374">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="b5623-375">Per creare una regola anti-phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b5623-375">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="b5623-376">In questo esempio viene creata una regola di phishing denominata Research Department con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5623-376">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="b5623-377">La regola è associata ai criteri anti-phishing denominati Research Quarantine.</span><span class="sxs-lookup"><span data-stu-id="b5623-377">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="b5623-378">La regola viene applicata ai membri del gruppo denominato Research Department.</span><span class="sxs-lookup"><span data-stu-id="b5623-378">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="b5623-379">Poiché non si utilizza il parametro _Priority_ , viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="b5623-379">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="b5623-380">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="b5623-380">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="b5623-381">Utilizzo di PowerShell per visualizzare i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="b5623-381">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="b5623-382">Per visualizzare i criteri anti-phishing esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b5623-382">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b5623-383">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri anti-phishing insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="b5623-383">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="b5623-384">In questo esempio vengono restituiti tutti i valori della proprietà per il criterio phishing denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="b5623-384">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="b5623-385">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="b5623-385">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="b5623-386">Utilizzo di PowerShell per visualizzare le regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="b5623-386">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="b5623-387">Per visualizzare le regole anti-phishing esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b5623-387">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="b5623-388">In questo esempio viene restituito un elenco riepilogativo di tutte le regole anti-phishing insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="b5623-388">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="b5623-389">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5623-389">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="b5623-390">In questo esempio vengono restituiti tutti i valori della proprietà per la regola phishing denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="b5623-390">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="b5623-391">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="b5623-391">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="b5623-392">Utilizzo di PowerShell per la modifica dei criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="b5623-392">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="b5623-393">A parte gli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio di phishing in PowerShell come quando si crea il criterio come descritto nel [passaggio 1: utilizzare PowerShell per creare una sezione dei criteri anti-phishing](#step-1-use-powershell-to-create-an-anti-phish-policy) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b5623-393">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this topic.</span></span>

- <span data-ttu-id="b5623-394">L'opzione _MakeDefault_ che consente di trasformare il criterio specificato nel criterio predefinito (applicato a tutti, priorità sempre **più bassa** e non è possibile eliminarla) è disponibile solo quando si modifica un criterio di protezione da phishing in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5623-394">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="b5623-395">Non è possibile rinominare un criterio anti-phishing (il cmdlet **set-AntiPhishPolicy** non ha un parametro _Name_ ).</span><span class="sxs-lookup"><span data-stu-id="b5623-395">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="b5623-396">Quando si rinomina un criterio anti-phishing nel centro sicurezza & Compliance, viene rinominata solo la _regola_anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="b5623-396">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="b5623-397">Per modificare un criterio di phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b5623-397">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="b5623-398">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="b5623-398">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="b5623-399">Utilizzo di PowerShell per modificare le regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="b5623-399">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="b5623-400">L'unica impostazione che non è disponibile quando si modifica una regola anti-phishing in PowerShell è il parametro _Enabled_ che consente di creare una regola disattivata.</span><span class="sxs-lookup"><span data-stu-id="b5623-400">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="b5623-401">Per abilitare o disabilitare le regole anti-phishing esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="b5623-401">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="b5623-402">In caso contrario, non sono disponibili ulteriori impostazioni quando si modifica una regola anti-phishing in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5623-402">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="b5623-403">Le stesse impostazioni sono disponibili quando si crea una regola come descritto nel [passaggio 2: utilizzo di PowerShell per creare una sezione di regola anti-phishing](#step-2-use-powershell-to-create-an-anti-phish-rule) più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b5623-403">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this topic.</span></span>

<span data-ttu-id="b5623-404">Per modificare una regola anti-phishing, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b5623-404">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="b5623-405">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="b5623-405">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="b5623-406">Utilizzo di PowerShell per abilitare o disabilitare le regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="b5623-406">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="b5623-407">L'abilitazione o disabilitazione di una regola anti-phishing in PowerShell consente di abilitare o disabilitare l'intero criterio anti-phishing (la regola anti-phishing e i criteri di anti-phishing assegnati).</span><span class="sxs-lookup"><span data-stu-id="b5623-407">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="b5623-408">Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="b5623-408">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="b5623-409">Per abilitare o disabilitare una regola anti-phishing in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b5623-409">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="b5623-410">In questo esempio viene disabilitata la regola anti-phishing denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b5623-410">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="b5623-411">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="b5623-411">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="b5623-412">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span><span class="sxs-lookup"><span data-stu-id="b5623-412">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="b5623-413">Utilizzo di PowerShell per impostare la priorità delle regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="b5623-413">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="b5623-414">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="b5623-414">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="b5623-415">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="b5623-415">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="b5623-416">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="b5623-416">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="b5623-417">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="b5623-417">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="b5623-418">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="b5623-418">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="b5623-419">Per impostare la priorità di una regola anti-phishing in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b5623-419">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="b5623-p145">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="b5623-p145">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="b5623-422">**Note**:</span><span class="sxs-lookup"><span data-stu-id="b5623-422">**Notes**:</span></span>

- <span data-ttu-id="b5623-423">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-AntiPhishRule** .</span><span class="sxs-lookup"><span data-stu-id="b5623-423">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="b5623-424">I criteri predefiniti di phishing non dispongono di una regola anti-phishing corrispondente e hanno sempre il valore di priorità immodificabile **più basso**.</span><span class="sxs-lookup"><span data-stu-id="b5623-424">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="b5623-425">Utilizzo di PowerShell per rimuovere i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="b5623-425">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="b5623-426">Quando si utilizza PowerShell per rimuovere un criterio phishing, la regola anti-phishing corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="b5623-426">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="b5623-427">Per rimuovere un criterio di phishing in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b5623-427">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="b5623-428">In questo esempio viene rimosso il criterio anti-phishing denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b5623-428">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="b5623-429">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="b5623-429">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="b5623-430">Utilizzo di PowerShell per rimuovere le regole anti-phishing</span><span class="sxs-lookup"><span data-stu-id="b5623-430">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="b5623-431">Quando si utilizza PowerShell per rimuovere una regola anti-phishing, i criteri di anti-phishing corrispondenti non vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="b5623-431">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="b5623-432">Per rimuovere una regola anti-phishing in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b5623-432">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="b5623-433">In questo esempio viene rimossa la regola anti-phishing denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="b5623-433">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="b5623-434">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="b5623-434">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="b5623-435">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="b5623-435">How do you know these procedures worked?</span></span>

<span data-ttu-id="b5623-436">Per verificare la corretta configurazione dei criteri di anti-phishing ATP, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5623-436">To verify that you've successfully configured ATP anti-phishing policies, do any of the following steps:</span></span>

- <span data-ttu-id="b5623-437">Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** \> **Policy** \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="b5623-437">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="b5623-438">Verificare l'elenco dei criteri, i relativi valori di **stato** e i relativi valori di **priorità** .</span><span class="sxs-lookup"><span data-stu-id="b5623-438">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="b5623-439">Per visualizzare ulteriori dettagli, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b5623-439">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="b5623-440">Selezionare il criterio dall'elenco e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="b5623-440">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="b5623-441">Fare clic su **criteri predefiniti** e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="b5623-441">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="b5623-442">In Exchange Online PowerShell, sostituire \<Name\> con il nome del criterio o della regola ed eseguire il comando riportato di seguito e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b5623-442">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
