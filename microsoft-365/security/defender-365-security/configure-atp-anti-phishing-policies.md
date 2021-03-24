---
title: Configurare i criteri anti-phishing in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a creare, modificare ed eliminare i criteri anti-phishing avanzati disponibili nelle organizzazioni con Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1c8d61aee9afb332a8426890560ad221a9c87c7d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065386"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db205-103">Configurare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="db205-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="db205-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="db205-104">**Applies to**</span></span>
- [<span data-ttu-id="db205-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="db205-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="db205-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="db205-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="db205-107">I criteri anti-phishing in [Microsoft Defender per Office 365](defender-for-office-365.md) consentono di proteggere l'organizzazione da attacchi di phishing dannosi basati sulla rappresentazione e da altri tipi di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="db205-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="db205-108">Per ulteriori informazioni sulle differenze tra i criteri anti-phishing in Exchange Online Protection (EOP) e i criteri anti-phishing in Microsoft Defender per Office 365, vedere [Protezione anti-phishing.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="db205-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="db205-109">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="db205-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="db205-110">Per una maggiore granularità, è inoltre possibile creare criteri anti-phishing personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="db205-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="db205-111">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).</span><span class="sxs-lookup"><span data-stu-id="db205-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="db205-112">È possibile configurare i criteri anti-phishing nel Centro sicurezza & conformità o in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="db205-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="db205-113">Per informazioni sulla configurazione dei criteri anti-phishing più limitati disponibili nelle organizzazioni di Exchange Online Protection (ovvero le organizzazioni senza Microsoft Defender per Office 365), vedere [Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="db205-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="db205-114">Gli elementi di base di un criterio anti-phishing sono:</span><span class="sxs-lookup"><span data-stu-id="db205-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="db205-115">**Il criterio anti-phishing**: Specifica le protezioni anti-phishing da abilitare o disabilitare e le azioni da applicare.</span><span class="sxs-lookup"><span data-stu-id="db205-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="db205-116">**La regola anti-phish**: Specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phish.</span><span class="sxs-lookup"><span data-stu-id="db205-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="db205-117">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri anti-phishing nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="db205-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="db205-118">Quando crei un criterio, stai creando una regola anti-phish e il criterio anti-phish associato contemporaneamente usando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="db205-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="db205-119">Quando si modifica un criterio, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="db205-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="db205-120">Tutte le altre impostazioni modificano il criterio anti-phish associato.</span><span class="sxs-lookup"><span data-stu-id="db205-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="db205-121">Quando si rimuove un criterio, vengono rimossi la regola anti-phish e il criterio anti-phish associato.</span><span class="sxs-lookup"><span data-stu-id="db205-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="db205-122">In PowerShell di Exchange Online, il criterio e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="db205-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="db205-123">Per ulteriori informazioni, vedere la sezione Utilizzare PowerShell di Exchange Online per configurare i criteri [anti-phishing in Microsoft Defender per Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="db205-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="db205-124">Ogni organizzazione di Microsoft Defender per Office 365 dispone di un criterio anti-phishing predefinito denominato Office365 AntiPhish Default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="db205-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="db205-125">Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se al criterio non è associata alcuna regola anti-phish (filtri destinatari).</span><span class="sxs-lookup"><span data-stu-id="db205-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="db205-126">Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="db205-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="db205-127">Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="db205-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="db205-128">Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="db205-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="db205-129">Per aumentare l'efficacia della protezione anti-phishing in Microsoft Defender per Office 365, è possibile creare criteri anti-phishing personalizzati con impostazioni più rigide applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="db205-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="db205-130">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="db205-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="db205-131">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="db205-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="db205-132">Per passare direttamente alla pagina **anti-phishing di ATP,** utilizzare <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="db205-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="db205-133">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="db205-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="db205-134">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="db205-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="db205-135">Per aggiungere, modificare ed eliminare criteri anti-phishing, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="db205-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="db205-136">Per l'accesso in sola lettura ai criteri anti-phishing, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="db205-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="db205-137">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="db205-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="db205-138">**Note**:</span><span class="sxs-lookup"><span data-stu-id="db205-138">**Notes**:</span></span>

  - <span data-ttu-id="db205-139">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db205-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="db205-140">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="db205-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="db205-141">Il **gruppo di ruoli Gestione organizzazione** di sola visualizzazione in Exchange [Online](/Exchange/permissions-exo/permissions-exo#role-groups) consente inoltre l'accesso in sola lettura alla funzionalità <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="db205-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="db205-142"><sup>\*</sup> Nel Centro sicurezza & conformità, l'accesso di sola lettura consente agli utenti di visualizzare le impostazioni dei criteri anti-phishing personalizzati.</span><span class="sxs-lookup"><span data-stu-id="db205-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="db205-143">Gli utenti di sola lettura non possono visualizzare le impostazioni nel criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="db205-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="db205-144">Per le impostazioni consigliate per i criteri anti-phishing in Microsoft Defender per Office 365, vedere [Criteri anti-phishing in Defender for Office 365 settings.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="db205-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="db205-145">Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.</span><span class="sxs-lookup"><span data-stu-id="db205-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="db205-146">Per informazioni su dove vengono applicati i criteri anti-phishing nella pipeline di filtro, vedere [Order and precedence of email protection.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="db205-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db205-147">Usare il Centro sicurezza & conformità per creare criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="db205-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="db205-148">La creazione di un criterio anti-phishing personalizzato nel Centro sicurezza & e conformità crea la regola anti-phishing e il criterio anti-phishing associato contemporaneamente usando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="db205-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="db205-149">Quando si crea un criterio anti-phishing, è possibile specificare solo il nome, la descrizione e il filtro destinatario che identifica a chi si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="db205-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="db205-150">Dopo aver creato il criterio, è possibile modificare il criterio per modificare o rivedere le impostazioni anti-phishing predefinite.</span><span class="sxs-lookup"><span data-stu-id="db205-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="db205-151">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db205-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db205-152">Nella pagina **Anti-phishing** fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="db205-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="db205-153">Verrà **visualizzata la procedura guidata Crea un nuovo criterio anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db205-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="db205-154">Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db205-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="db205-155">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="db205-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="db205-156">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="db205-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="db205-157">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="db205-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="db205-158">Nella pagina **Applicato a** visualizzata identificare i destinatari interni a cui si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="db205-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="db205-159">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="db205-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="db205-160">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="db205-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="db205-161">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="db205-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="db205-162">Fare **clic su Aggiungi condizione.**</span><span class="sxs-lookup"><span data-stu-id="db205-162">Click **Add a condition**.</span></span> <span data-ttu-id="db205-163">Nell'elenco a discesa visualizzato selezionare una condizione in **Applicato se**:</span><span class="sxs-lookup"><span data-stu-id="db205-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="db205-164">**Il destinatario è**: Specifica una o più cassette postali, utenti di posta o contatti di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="db205-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="db205-165">**Il destinatario è un membro di**: Specifica uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="db205-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="db205-166">**Il dominio del destinatario** è : Specifica i destinatari in uno o più domini accettati configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="db205-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="db205-167">Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con **una casella** Qualsiasi di queste.</span><span class="sxs-lookup"><span data-stu-id="db205-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="db205-168">Fare clic nella casella e scorrere l'elenco di valori da selezionare.</span><span class="sxs-lookup"><span data-stu-id="db205-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="db205-169">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="db205-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="db205-170">Per aggiungere altri valori, fare clic in un'area vuota della casella.</span><span class="sxs-lookup"><span data-stu-id="db205-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="db205-171">Per rimuovere singole voci, fare clic **su Rimuovi** ![ Icona Rimuovi sul ](../../media/scc-remove-icon.png) valore.</span><span class="sxs-lookup"><span data-stu-id="db205-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="db205-172">Per rimuovere l'intera condizione, fare **clic su Rimuovi** Icona Rimuovi nella ![ ](../../media/scc-remove-icon.png) condizione.</span><span class="sxs-lookup"><span data-stu-id="db205-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="db205-173">Per aggiungere una condizione aggiuntiva, fare clic **su Aggiungi una condizione** e selezionare un valore rimanente in Applicato **se**.</span><span class="sxs-lookup"><span data-stu-id="db205-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="db205-174">Per aggiungere eccezioni, fare clic **su Aggiungi una condizione** e selezionare un'eccezione in Tranne **se**.</span><span class="sxs-lookup"><span data-stu-id="db205-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="db205-175">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="db205-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="db205-176">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="db205-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="db205-177">Nella pagina **Rivedere le impostazioni** visualizzata esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="db205-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="db205-178">È possibile fare **clic su** Modifica per ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="db205-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="db205-179">Al termine, fare clic **su Crea questo criterio.**</span><span class="sxs-lookup"><span data-stu-id="db205-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="db205-180">Fare **clic su OK** nella finestra di dialogo di conferma visualizzata.</span><span class="sxs-lookup"><span data-stu-id="db205-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="db205-181">Dopo aver creato il criterio anti-phishing con queste impostazioni generali, seguire le istruzioni nella sezione successiva per configurare le impostazioni di protezione nel criterio.</span><span class="sxs-lookup"><span data-stu-id="db205-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db205-182">Usare il Centro sicurezza & conformità per modificare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="db205-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="db205-183">Utilizzare le procedure seguenti per modificare i criteri anti-phishing: un nuovo criterio creato dall'utente o criteri esistenti già personalizzati.</span><span class="sxs-lookup"><span data-stu-id="db205-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="db205-184">Se non si è già presenti, aprire il Centro sicurezza & conformità e passare a **Criteri** di gestione delle minacce \>  \> **ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="db205-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db205-185">Selezionare il criterio anti-phishing personalizzato che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="db205-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="db205-186">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="db205-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="db205-187">Viene **visualizzato \<name\> il riquadro a comparsa** Modifica il criterio.</span><span class="sxs-lookup"><span data-stu-id="db205-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="db205-188">Se **si** fa clic su Modifica in qualsiasi sezione, è possibile accedere alle impostazioni in tale sezione.</span><span class="sxs-lookup"><span data-stu-id="db205-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="db205-189">I passaggi seguenti vengono presentati nell'ordine in cui vengono visualizzate le sezioni, ma non sono sequenziali (è possibile selezionare e modificare le sezioni in qualsiasi ordine).</span><span class="sxs-lookup"><span data-stu-id="db205-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="db205-190">Dopo aver fatto clic su Modifica **in** una sezione, le impostazioni disponibili vengono presentate in un  formato di procedura guidata,  ma è possibile passare all'interno delle pagine in qualsiasi ordine e fare clic su Salva in qualsiasi pagina (o  ![ ](../../media/scc-remove-icon.png) **\<name\>** Icona Annulla o Chiudi chiudi per tornare alla pagina Modifica i criteri (non è necessario visitare l'ultima pagina della procedura guidata per salvare o uscire).</span><span class="sxs-lookup"><span data-stu-id="db205-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="db205-191">**Impostazione dei criteri:** **fare** clic su Modifica per modificare le stesse impostazioni disponibili al momento della [creazione](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) del criterio nella sezione precedente:</span><span class="sxs-lookup"><span data-stu-id="db205-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="db205-192">**Nome**</span><span class="sxs-lookup"><span data-stu-id="db205-192">**Name**</span></span>
   - <span data-ttu-id="db205-193">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="db205-193">**Description**</span></span>
   - <span data-ttu-id="db205-194">**Applicato a**</span><span class="sxs-lookup"><span data-stu-id="db205-194">**Applied to**</span></span>
   - <span data-ttu-id="db205-195">**Rivedere le impostazioni**</span><span class="sxs-lookup"><span data-stu-id="db205-195">**Review your settings**</span></span>

   <span data-ttu-id="db205-196">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="db205-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="db205-197">**Rappresentazione:** fare **clic su** Modifica per modificare i mittenti protetti e i domini protetti nel criterio.</span><span class="sxs-lookup"><span data-stu-id="db205-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="db205-198">Queste impostazioni sono una condizione per il criterio che identifica i mittenti contraffatti da cercare (singolarmente o per dominio) nell'indirizzo mittente dei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="db205-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="db205-199">Per ulteriori informazioni, vedere [Impostazioni di rappresentazione nei criteri anti-phishing in Microsoft Defender per Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="db205-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="db205-200">**Aggiungere utenti da proteggere**: il valore predefinito è **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="db205-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="db205-201">Per attivarlo, fai scorrere l'interruttore su **Attivato** e quindi fai clic sul **pulsante** Aggiungi utente visualizzato.</span><span class="sxs-lookup"><span data-stu-id="db205-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="db205-202">Nel riquadro **a comparsa** Aggiungi utente visualizzato configurare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="db205-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="db205-203">**Indirizzo di posta elettronica**:</span><span class="sxs-lookup"><span data-stu-id="db205-203">**Email address**:</span></span>

       - <span data-ttu-id="db205-204">Fare clic nella casella e scorrere l'elenco di utenti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="db205-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="db205-205">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="db205-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="db205-206">Per rimuovere una voce, fare clic **su Rimuovi** Icona ![ Rimuovi ](../../media/scc-remove-icon.png) nell'utente.</span><span class="sxs-lookup"><span data-stu-id="db205-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="db205-207">**Nome**: questo valore viene popolato in base all'indirizzo di posta elettronica selezionato, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="db205-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="db205-208">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="db205-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="db205-209">Per modificare una voce esistente, selezionare l'utente protetto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="db205-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="db205-210">In ogni criterio anti-phishing, è possibile specificare un massimo di 60 utenti protetti (indirizzi di posta elettronica del mittente).</span><span class="sxs-lookup"><span data-stu-id="db205-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="db205-211">Non è possibile specificare lo stesso utente protetto in più criteri.</span><span class="sxs-lookup"><span data-stu-id="db205-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="db205-212">La protezione della rappresentazione dell'utente non funziona se il mittente e il destinatario hanno precedentemente comunicato tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="db205-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="db205-213">Se il mittente e il destinatario non hanno mai comunicato tramite posta elettronica, il messaggio verrà identificato come tentativo di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="db205-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="db205-214">**Aggiungere domini da proteggere**: configurare una o entrambe le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db205-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="db205-215">**Includi automaticamente i domini di cui sono proprietario**: il valore predefinito è **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="db205-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="db205-216">Per attivarlo, fai scorrere l'interruttore su **On.**</span><span class="sxs-lookup"><span data-stu-id="db205-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="db205-217">**Includi domini personalizzati**: il valore predefinito è **Off**.</span><span class="sxs-lookup"><span data-stu-id="db205-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="db205-218">Per attivarlo, fai scorrere l'interruttore su **On** e nella casella **Aggiungi** domini immetti il nome di dominio (ad esempio, contoso.com), premi INVIO e ripeti se necessario.</span><span class="sxs-lookup"><span data-stu-id="db205-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="db205-219">È possibile avere un massimo di 50 domini in tutti i criteri anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="db205-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="db205-220">**Azioni**: fare clic su **Modifica**</span><span class="sxs-lookup"><span data-stu-id="db205-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="db205-221">**Se la posta elettronica** viene inviata da un utente rappresentato: configurare una delle azioni seguenti per i messaggi in cui il mittente contraffatto è uno degli utenti protetti specificati in Aggiungere utenti **da proteggere:**</span><span class="sxs-lookup"><span data-stu-id="db205-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="db205-222">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="db205-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="db205-223">**Reindirizzare il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="db205-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="db205-224">**Sposta messaggio nella cartella Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="db205-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="db205-225">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="db205-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="db205-226">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="db205-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="db205-227">**Eliminare il messaggio prima che venga recapitato**</span><span class="sxs-lookup"><span data-stu-id="db205-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="db205-228">**Se la posta elettronica** viene inviata da un dominio rappresentato: configurare una delle azioni seguenti per i messaggi in cui il mittente contraffatto si trova in uno dei domini protetti specificati in Aggiungere domini **per proteggere**:</span><span class="sxs-lookup"><span data-stu-id="db205-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="db205-229">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="db205-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="db205-230">**Reindirizzare il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="db205-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="db205-231">**Sposta messaggio nella cartella Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="db205-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="db205-232">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="db205-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="db205-233">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="db205-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="db205-234">**Eliminare il messaggio prima che venga recapitato**</span><span class="sxs-lookup"><span data-stu-id="db205-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="db205-235">Fare **clic su Attiva suggerimenti per la sicurezza della rappresentazione** e configurare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db205-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="db205-236">**Mostra suggerimento per gli utenti rappresentati**: il valore predefinito è **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="db205-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="db205-237">Per attivarlo, fai scorrere l'interruttore su **On.**</span><span class="sxs-lookup"><span data-stu-id="db205-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="db205-238">**Show tip for impersonated domains**: The default value is **Off**.</span><span class="sxs-lookup"><span data-stu-id="db205-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="db205-239">Per attivarlo, fai scorrere l'interruttore su **On.**</span><span class="sxs-lookup"><span data-stu-id="db205-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="db205-240">**Mostra suggerimento per caratteri insoliti**: il valore predefinito è **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="db205-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="db205-241">Per attivarlo, fai scorrere l'interruttore su **On.**</span><span class="sxs-lookup"><span data-stu-id="db205-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="db205-242">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="db205-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="db205-243">**Intelligence delle cassette postali**:</span><span class="sxs-lookup"><span data-stu-id="db205-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="db205-244">**Abilitare l'intelligence delle cassette postali?**: il valore predefinito è **On**.</span><span class="sxs-lookup"><span data-stu-id="db205-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="db205-245">Per disattivarlo, fai scorrere l'interruttore su **Off.**</span><span class="sxs-lookup"><span data-stu-id="db205-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="db205-246">**Abilitare la protezione della rappresentazione basata sull'intelligence delle** cassette postali? : Questa impostazione è disponibile solo se **Abilita intelligence cassetta postale?** è **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="db205-246">**Enable mailbox intelligence based impersonation protection?**: This setting is available only if **Enable mailbox intelligence?** is **On**.</span></span> <span data-ttu-id="db205-247">Attivare questa impostazione per specificare l'azione da eseguire sui messaggi per i rilevamenti di rappresentazione dai risultati dell'intelligence delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="db205-247">Turn on this setting to specify the action to take on messages for impersonation detections from mailbox intelligence results.</span></span>

       <span data-ttu-id="db205-248">In **Se la posta elettronica** viene inviata da un utente rappresentato, è possibile specificare una delle azioni seguenti (le stesse azioni disponibili per gli utenti protetti e i domini protetti):</span><span class="sxs-lookup"><span data-stu-id="db205-248">In **If email is sent by an impersonated user**, you can specify one of the following actions (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="db205-249">Non applicare alcuna azione: si noti che questo valore ha lo stesso risultato dell'attivazione di Abilita intelligence cassetta **postale?** ma disattivando Abilita protezione della rappresentazione basata **sull'intelligence** delle cassette **postali?**.</span><span class="sxs-lookup"><span data-stu-id="db205-249">**Don't apply any action**: Note that this value has the same result as turning on **Enable mailbox intelligence?** but turning off **Enable mailbox intelligence based impersonation protection?**.</span></span>
       - <span data-ttu-id="db205-250">**Reindirizzare il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="db205-250">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="db205-251">**Sposta messaggio nella cartella Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="db205-251">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="db205-252">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="db205-252">**Quarantine the message**</span></span>
       - <span data-ttu-id="db205-253">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="db205-253">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="db205-254">**Eliminare il messaggio prima che venga recapitato**</span><span class="sxs-lookup"><span data-stu-id="db205-254">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="db205-255">**Aggiungere mittenti e domini attendibili**: specificare le eccezioni per il criterio:</span><span class="sxs-lookup"><span data-stu-id="db205-255">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="db205-256">**Mittenti attendibili**:</span><span class="sxs-lookup"><span data-stu-id="db205-256">**Trusted senders**:</span></span>

       - <span data-ttu-id="db205-257">Fare clic nella casella e scorrere l'elenco di utenti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="db205-257">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="db205-258">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="db205-258">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="db205-259">Per rimuovere una voce, fare clic **su Rimuovi** Icona ![ Rimuovi ](../../media/scc-remove-icon.png) nell'utente.</span><span class="sxs-lookup"><span data-stu-id="db205-259">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="db205-260">**Domini trusted:** immettere il nome di dominio (ad esempio, contoso.com), premere INVIO e ripetere l'operazione in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="db205-260">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="db205-261">**Rivedere le impostazioni:** invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="db205-261">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="db205-262">È possibile fare **clic su** Modifica in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="db205-262">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="db205-263">È possibile attivare o **disattivare** le impostazioni seguenti **direttamente** in questa pagina:</span><span class="sxs-lookup"><span data-stu-id="db205-263">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="db205-264">**Utenti protetti**</span><span class="sxs-lookup"><span data-stu-id="db205-264">**Protected users**</span></span>
       - <span data-ttu-id="db205-265">**Domini protetti** \> **Includere i domini di cui sono proprietario**</span><span class="sxs-lookup"><span data-stu-id="db205-265">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="db205-266">**Domini protetti** \> **Domini protetti** (domini personalizzati)</span><span class="sxs-lookup"><span data-stu-id="db205-266">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="db205-267">**Intelligence della cassetta postale**</span><span class="sxs-lookup"><span data-stu-id="db205-267">**Mailbox intelligence**</span></span>

   <span data-ttu-id="db205-268">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="db205-268">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="db205-269">**Spoof**: **fare** clic su Modifica per attivare o disattivare l'intelligence spoofing, attivare o disattivare l'identificazione del mittente non autenticato in Outlook e configurare l'azione da applicare ai messaggi provenienti da mittenti falsificati bloccati.</span><span class="sxs-lookup"><span data-stu-id="db205-269">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="db205-270">Per ulteriori informazioni, vedere [Spoofing settings in anti-phishing policies.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="db205-270">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="db205-271">Si noti che queste stesse impostazioni sono disponibili anche nei criteri anti-phishing in EOP.</span><span class="sxs-lookup"><span data-stu-id="db205-271">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="db205-272">**Impostazioni del filtro di spoofing**: il valore predefinito è **On** e si consiglia di lasciarlo.</span><span class="sxs-lookup"><span data-stu-id="db205-272">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="db205-273">Per disattivarlo, fai scorrere l'interruttore su **Off.**</span><span class="sxs-lookup"><span data-stu-id="db205-273">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="db205-274">Per ulteriori informazioni, vedere [Configure spoof intelligence in EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="db205-274">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="db205-275">Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Microsoft 365. si abilita invece il filtro avanzato per i connettori.</span><span class="sxs-lookup"><span data-stu-id="db205-275">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="db205-276">Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="db205-276">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="db205-277">**Abilita funzionalità mittente non autenticato**: il valore predefinito è **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="db205-277">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="db205-278">Per disattivarlo, fai scorrere l'interruttore su **Off.**</span><span class="sxs-lookup"><span data-stu-id="db205-278">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="db205-279">**Azioni**: specificare l'azione da eseguire sui messaggi che non riescono a spoof intelligence:</span><span class="sxs-lookup"><span data-stu-id="db205-279">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="db205-280">**Se la posta elettronica viene inviata da un utente a cui non è consentito effettuare lo spoofing del dominio:**</span><span class="sxs-lookup"><span data-stu-id="db205-280">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="db205-281">**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="db205-281">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="db205-282">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="db205-282">**Quarantine the message**</span></span>

   - <span data-ttu-id="db205-283">**Rivedere le impostazioni:** invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="db205-283">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="db205-284">È possibile fare **clic su** Modifica in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="db205-284">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="db205-285">È possibile attivare o **disattivare** le impostazioni seguenti **direttamente** in questa pagina:</span><span class="sxs-lookup"><span data-stu-id="db205-285">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="db205-286">**Abilitare la protezione antispoofing**</span><span class="sxs-lookup"><span data-stu-id="db205-286">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="db205-287">**Abilitare la funzionalità Mittente non autenticato**</span><span class="sxs-lookup"><span data-stu-id="db205-287">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="db205-288">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="db205-288">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="db205-289">**Impostazioni avanzate**: fare clic **su Modifica** per configurare le soglie di phishing avanzate.</span><span class="sxs-lookup"><span data-stu-id="db205-289">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="db205-290">Per ulteriori informazioni, vedere [Soglie avanzate di phishing nei criteri anti-phishing in Microsoft Defender per Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="db205-290">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="db205-291">**Soglie di phishing avanzate**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="db205-291">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="db205-292">**1 - Standard** (questo è il valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="db205-292">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="db205-293">**2 - Aggressivo**</span><span class="sxs-lookup"><span data-stu-id="db205-293">**2 - Aggressive**</span></span>
   - <span data-ttu-id="db205-294">**3 - Più aggressivo**</span><span class="sxs-lookup"><span data-stu-id="db205-294">**3 - More aggressive**</span></span>
   - <span data-ttu-id="db205-295">**4 - Più aggressivo**</span><span class="sxs-lookup"><span data-stu-id="db205-295">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="db205-296">**Rivedere le impostazioni:** fare clic **su Modifica** per tornare alla **pagina Soglie di phishing** avanzate.</span><span class="sxs-lookup"><span data-stu-id="db205-296">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="db205-297">Al termine, fare clic su **Salva** in entrambe le pagine.</span><span class="sxs-lookup"><span data-stu-id="db205-297">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="db205-298">Tornare alla pagina **Modifica i \<Name\> criteri,** rivedere le impostazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="db205-298">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db205-299">Usare il Centro sicurezza & conformità per modificare i criteri anti-phishing predefiniti in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="db205-299">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="db205-300">Il criterio anti-phishing predefinito in Microsoft Defender per Office 365 è denominato Office365 AntiPhish Default e non viene visualizzato nell'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="db205-300">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="db205-301">Per modificare il criterio anti-phishing predefinito, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="db205-301">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="db205-302">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db205-302">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db205-303">Nella pagina **Anti-phishing** fare clic su **Criterio predefinito.**</span><span class="sxs-lookup"><span data-stu-id="db205-303">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="db205-304">Viene visualizzata la pagina Modifica il criterio **Office365 AntiPhish Default.**</span><span class="sxs-lookup"><span data-stu-id="db205-304">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="db205-305">Sono disponibili le sezioni seguenti, che contengono impostazioni identiche per quando si [modifica un criterio personalizzato:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="db205-305">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="db205-306">**Rappresentazione**</span><span class="sxs-lookup"><span data-stu-id="db205-306">**Impersonation**</span></span>
   - <span data-ttu-id="db205-307">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="db205-307">**Spoof**</span></span>
   - <span data-ttu-id="db205-308">**Impostazioni avanzate**</span><span class="sxs-lookup"><span data-stu-id="db205-308">**Advanced settings**</span></span>

   <span data-ttu-id="db205-309">Le impostazioni seguenti non sono disponibili quando si modifica il criterio predefinito:</span><span class="sxs-lookup"><span data-stu-id="db205-309">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="db205-310">È possibile  visualizzare la sezione Impostazioni criteri e  i valori, ma non è disponibile alcun collegamento Modifica, quindi non è possibile modificare le impostazioni (nome del criterio, descrizione e a chi si applica il criterio (si applica a tutti i destinatari)).</span><span class="sxs-lookup"><span data-stu-id="db205-310">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="db205-311">Non è possibile eliminare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="db205-311">You can't delete the default policy.</span></span>
   - <span data-ttu-id="db205-312">Non è possibile modificare la priorità del criterio predefinito (viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="db205-312">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="db205-313">Nella pagina **Modifica i criteri Office365 AntiPhish Default** rivedere le impostazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="db205-313">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db205-314">Abilitare o disabilitare i criteri anti-phishing personalizzati in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="db205-314">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="db205-315">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db205-315">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db205-316">Notare il valore nella **colonna** Stato:</span><span class="sxs-lookup"><span data-stu-id="db205-316">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="db205-317">Fai scorrere **l'interruttore su Off** per disabilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="db205-317">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="db205-318">Fai scorrere **l'interruttore su Attivato** per abilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="db205-318">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="db205-319">Non è possibile disabilitare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="db205-319">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db205-320">Impostare la priorità dei criteri anti-phishing personalizzati in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="db205-320">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="db205-321">Per impostazione predefinita, ai criteri anti-phishing viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="db205-321">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="db205-322">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="db205-322">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="db205-323">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="db205-323">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="db205-324">Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="db205-324">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="db205-325">I criteri anti-phishing personalizzati vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="db205-325">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="db205-326">Il criterio anti-phishing predefinito denominato Office365 AntiPhish Default ha il valore di priorità personalizzato **Lowest** e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="db205-326">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="db205-327">**Nota:** nel Centro sicurezza & conformità, è possibile modificare la priorità del criterio anti-phishing solo dopo aver creato il criterio.</span><span class="sxs-lookup"><span data-stu-id="db205-327">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="db205-328">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phish (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="db205-328">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="db205-329">Per modificare la priorità di  un criterio, fare clic su Aumenta priorità o Riduci  priorità nelle proprietà del criterio (non è possibile modificare direttamente il numero di priorità nel Centro sicurezza & conformità). </span><span class="sxs-lookup"><span data-stu-id="db205-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="db205-330">La modifica della priorità di un criterio ha senso solo se si dispone di più criteri.</span><span class="sxs-lookup"><span data-stu-id="db205-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="db205-331">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db205-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db205-332">Selezionare il criterio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="db205-332">Select the policy that you want to modify.</span></span> <span data-ttu-id="db205-333">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="db205-333">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="db205-334">Viene **visualizzato \<name\> il riquadro a comparsa** Modifica il criterio.</span><span class="sxs-lookup"><span data-stu-id="db205-334">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="db205-335">Il criterio anti-phishing personalizzato con **il valore Priority** **0** ha solo il **pulsante Riduci** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="db205-335">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="db205-336">Il criterio anti-phishing personalizzato con il valore **priority** più basso (ad esempio, **3**) ha solo il **pulsante Aumenta** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="db205-336">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="db205-337">Se si dispone di tre o più criteri anti-phishing personalizzati,  i criteri  tra i valori di priorità più alta e più bassa hanno entrambi i pulsanti Aumenta priorità e Riduci priorità disponibili.</span><span class="sxs-lookup"><span data-stu-id="db205-337">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="db205-338">Fare **clic su Aumenta priorità** o **Diminuisci priorità** per modificare il valore **Priorità.**</span><span class="sxs-lookup"><span data-stu-id="db205-338">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="db205-339">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="db205-339">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db205-340">Usare il Centro sicurezza & conformità per visualizzare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="db205-340">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="db205-341">Nel Centro sicurezza & conformità e passare a **Gestione** delle minacce \>  \> **Criteri ATP anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="db205-341">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db205-342">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db205-342">Do one of the following steps:</span></span>

   - <span data-ttu-id="db205-343">Selezionare un criterio anti-phishing personalizzato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="db205-343">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="db205-344">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="db205-344">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="db205-345">Fare **clic su Criterio** predefinito per visualizzare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="db205-345">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="db205-346">Viene **visualizzato \<name\> il riquadro a** comparsa Modifica il criterio, in cui è possibile visualizzare le impostazioni e i valori.</span><span class="sxs-lookup"><span data-stu-id="db205-346">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db205-347">Usare il Centro sicurezza & conformità per rimuovere i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="db205-347">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="db205-348">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db205-348">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="db205-349">Selezionare il criterio che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="db205-349">Select the policy that you want to remove.</span></span> <span data-ttu-id="db205-350">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="db205-350">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="db205-351">Nel riquadro **a \<name\> comparsa Modifica criterio** visualizzato fare clic **su** Elimina criterio e quindi su **Sì** nella finestra di dialogo di avviso visualizzata.</span><span class="sxs-lookup"><span data-stu-id="db205-351">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="db205-352">Non è possibile rimuovere il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="db205-352">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="db205-353">Utilizzare PowerShell di Exchange Online per configurare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="db205-353">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="db205-354">Come descritto in precedenza, un criterio di protezione da posta indesiderata è costituito da un criterio anti-phish e da una regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="db205-354">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="db205-355">In PowerShell di Exchange Online, la differenza tra i criteri anti-phish e le regole anti-phish è evidente.</span><span class="sxs-lookup"><span data-stu-id="db205-355">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="db205-356">È possibile gestire i criteri anti-phish utilizzando i cmdlet **\* -AntiPhishPolicy** e gestire le regole anti-phish utilizzando i cmdlet **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="db205-356">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="db205-357">In PowerShell, si crea prima il criterio anti-phish, quindi si crea la regola anti-phish che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="db205-357">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="db205-358">In PowerShell, le impostazioni dei criteri anti-phish e della regola anti-phish vengono modificate separatamente.</span><span class="sxs-lookup"><span data-stu-id="db205-358">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="db205-359">Quando si rimuove un criterio anti-phish da PowerShell, la regola anti-phish corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="db205-359">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="db205-360">Utilizzare PowerShell per creare criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="db205-360">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="db205-361">La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="db205-361">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="db205-362">Creare i criteri anti-phish.</span><span class="sxs-lookup"><span data-stu-id="db205-362">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="db205-363">Creare la regola anti-phish che specifica il criterio anti-phish a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="db205-363">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="db205-364">**Note**:</span><span class="sxs-lookup"><span data-stu-id="db205-364">**Notes**:</span></span>

- <span data-ttu-id="db205-365">È possibile creare una nuova regola anti-phish e assegnarle un criterio anti-phish esistente e non associazione.</span><span class="sxs-lookup"><span data-stu-id="db205-365">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="db205-366">Una regola anti-phish non può essere associata a più di un criterio anti-phish.</span><span class="sxs-lookup"><span data-stu-id="db205-366">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="db205-367">È possibile configurare le impostazioni seguenti nei nuovi criteri anti-phish in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:</span><span class="sxs-lookup"><span data-stu-id="db205-367">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="db205-368">Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="db205-368">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="db205-369">Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="db205-369">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="db205-370">Un nuovo criterio anti-phish creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="db205-370">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="db205-371">Passaggio 1: Usare PowerShell per creare un criterio anti-phish</span><span class="sxs-lookup"><span data-stu-id="db205-371">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="db205-372">Per creare un criterio anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db205-372">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="db205-373">In questo esempio viene creato un criterio anti-phish denominato Research Quarantine con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db205-373">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="db205-374">Il criterio è abilitato (non viene utilizzato il _parametro Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="db205-374">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="db205-375">La descrizione è: Criteri del reparto di ricerca.</span><span class="sxs-lookup"><span data-stu-id="db205-375">The description is: Research department policy.</span></span>
- <span data-ttu-id="db205-376">Abilita la protezione dei domini dell'organizzazione per tutti i domini accettati e la protezione dei domini di destinazione per fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="db205-376">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="db205-377">Specifica Mai Fujito (mfujito@fabrikam.com) come l'utente da proteggere da imitazione.</span><span class="sxs-lookup"><span data-stu-id="db205-377">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="db205-378">Abilita l'intelligence della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="db205-378">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="db205-379">Abilita la protezione dell'intelligence delle cassette postali e specifica l'azione di quarantena.</span><span class="sxs-lookup"><span data-stu-id="db205-379">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="db205-380">Abilita i suggerimenti per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="db205-380">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="db205-381">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="db205-381">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="db205-382">Passaggio 2: Usare PowerShell per creare una regola anti-phish</span><span class="sxs-lookup"><span data-stu-id="db205-382">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="db205-383">Per creare una regola anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db205-383">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="db205-384">In questo esempio viene creata una regola anti-phish denominata Research Department con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db205-384">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="db205-385">La regola è associata al criterio anti-phish denominato Quarantena ricerche.</span><span class="sxs-lookup"><span data-stu-id="db205-385">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="db205-386">La regola viene applicata ai membri del gruppo denominato Research Department.</span><span class="sxs-lookup"><span data-stu-id="db205-386">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="db205-387">Poiché non si utilizza il parametro _Priority,_ viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="db205-387">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="db205-388">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="db205-388">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="db205-389">Usare PowerShell per visualizzare i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="db205-389">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="db205-390">Per visualizzare i criteri anti-phish esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db205-390">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="db205-391">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri anti-phish insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="db205-391">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="db205-392">In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio anti-phish denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="db205-392">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="db205-393">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="db205-393">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="db205-394">Usare PowerShell per visualizzare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="db205-394">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="db205-395">Per visualizzare le regole anti-phish esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db205-395">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="db205-396">In questo esempio viene restituito un elenco riepilogativo di tutte le regole anti-phish insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="db205-396">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="db205-397">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="db205-397">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="db205-398">In questo esempio vengono restituiti tutti i valori delle proprietà per la regola anti-phish denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="db205-398">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="db205-399">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="db205-399">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="db205-400">Utilizzare PowerShell per modificare i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="db205-400">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="db205-401">Oltre agli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio anti-phish in PowerShell come quando si crea il criterio come descritto nella sezione Passaggio 1: utilizzare PowerShell per creare un criterio [anti-phish](#step-1-use-powershell-to-create-an-anti-phish-policy) in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="db205-401">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="db205-402">L'opzione _MakeDefault_ che trasforma il criterio specificato nel  criterio predefinito (applicato a tutti, sempre con priorità minima e non è possibile eliminarlo) è disponibile solo quando si modifica un criterio anti-phish in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db205-402">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="db205-403">Non è possibile rinominare un criterio anti-phish (il cmdlet **Set-AntiPhishPolicy** non dispone di _alcun parametro Name)._</span><span class="sxs-lookup"><span data-stu-id="db205-403">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="db205-404">Quando si rinomina un criterio anti-phishing nel Centro sicurezza & conformità, si rinomina solo la regola _anti-phishing._</span><span class="sxs-lookup"><span data-stu-id="db205-404">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="db205-405">Per modificare un criterio anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db205-405">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="db205-406">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="db205-406">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="db205-407">Utilizzare PowerShell per modificare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="db205-407">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="db205-408">L'unica impostazione non disponibile quando si modifica una regola anti-phish in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="db205-408">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="db205-409">Per abilitare o disabilitare le regole anti-phish esistenti, vedi la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="db205-409">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="db205-410">In caso contrario, non sono disponibili impostazioni aggiuntive quando si modifica una regola anti-phish in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db205-410">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="db205-411">Le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione Passaggio 2: Utilizzare PowerShell per creare una regola [anti-phish](#step-2-use-powershell-to-create-an-anti-phish-rule) in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="db205-411">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="db205-412">Per modificare una regola anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db205-412">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="db205-413">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="db205-413">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="db205-414">Usare PowerShell per abilitare o disabilitare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="db205-414">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="db205-415">L'abilitazione o la disabilitazione di una regola anti-phishing in PowerShell abilita o disabilita l'intero criterio anti-phishing (la regola anti-phishing e il criterio anti-phishing assegnato).</span><span class="sxs-lookup"><span data-stu-id="db205-415">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="db205-416">Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="db205-416">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="db205-417">Per abilitare o disabilitare una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db205-417">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="db205-418">In questo esempio viene disabilitata la regola anti-phish denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="db205-418">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="db205-419">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="db205-419">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="db205-420">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="db205-420">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="db205-421">Usare PowerShell per impostare la priorità delle regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="db205-421">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="db205-422">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="db205-422">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="db205-423">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="db205-423">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="db205-424">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="db205-424">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="db205-425">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="db205-425">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="db205-426">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="db205-426">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="db205-427">Per impostare la priorità di una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db205-427">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="db205-p149">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="db205-p149">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="db205-430">**Note**:</span><span class="sxs-lookup"><span data-stu-id="db205-430">**Notes**:</span></span>

- <span data-ttu-id="db205-431">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare invece il parametro _Priority_ nel cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="db205-431">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="db205-432">Il criterio anti-phish predefinito non dispone di una regola anti-phish corrispondente e ha sempre il valore di priorità non modificabile **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="db205-432">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="db205-433">Usare PowerShell per rimuovere i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="db205-433">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="db205-434">Quando si utilizza PowerShell per rimuovere un criterio anti-phish, la regola anti-phish corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="db205-434">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="db205-435">Per rimuovere un criterio anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db205-435">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="db205-436">In questo esempio viene rimosso il criterio anti-phish denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="db205-436">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="db205-437">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="db205-437">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="db205-438">Usare PowerShell per rimuovere le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="db205-438">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="db205-439">Quando si utilizza PowerShell per rimuovere una regola anti-phish, il criterio anti-phish corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="db205-439">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="db205-440">Per rimuovere una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="db205-440">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="db205-441">In questo esempio viene rimossa la regola anti-phish denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="db205-441">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="db205-442">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="db205-442">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="db205-443">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="db205-443">How do you know these procedures worked?</span></span>

<span data-ttu-id="db205-444">Per verificare la corretta configurazione dei criteri anti-phishing in Microsoft Defender per Office 365, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db205-444">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="db205-445">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="db205-445">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="db205-446">Verificare l'elenco dei criteri, i **relativi valori status** e i relativi valori **Priority.**</span><span class="sxs-lookup"><span data-stu-id="db205-446">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="db205-447">Per visualizzare ulteriori dettagli, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="db205-447">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="db205-448">Selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="db205-448">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="db205-449">Fare **clic su** Criterio predefinito e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="db205-449">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="db205-450">In PowerShell di Exchange Online, sostituire con il nome del criterio o della regola ed eseguire \<Name\> il comando seguente e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="db205-450">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```