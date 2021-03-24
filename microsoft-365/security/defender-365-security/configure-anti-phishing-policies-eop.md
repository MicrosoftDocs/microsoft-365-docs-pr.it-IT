---
title: Configurare i criteri anti-phishing in Exchange Online Protection
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
description: Gli amministratori possono imparare a creare, modificare ed eliminare i criteri anti-phishing disponibili nelle organizzazioni di Exchange Online Protection (EOP) con o senza cassette postali di Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c277558bad32e1926030483d202b70ae3c910315
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065394"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="2cd2f-103">Configurare i criteri anti-phishing in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2cd2f-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2cd2f-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-104">**Applies to**</span></span>
- [<span data-ttu-id="2cd2f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2cd2f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="2cd2f-106">Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, esiste un criterio anti-phishing predefinito che contiene un numero limitato di funzionalità anti-spoofing abilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="2cd2f-107">Per ulteriori informazioni, vedere [Spoofing settings in anti-phishing policies.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="2cd2f-108">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="2cd2f-109">Per una maggiore granularità, è inoltre possibile creare criteri anti-phishing personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="2cd2f-110">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="2cd2f-111">Le organizzazioni con cassette postali di Exchange Online possono configurare i criteri anti-phishing nel Centro sicurezza & conformità o in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="2cd2f-112">Le organizzazioni EOP autonome possono utilizzare solo il Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-112">Standalone EOP organizations can only use the Security & Compliance Center.</span></span>

<span data-ttu-id="2cd2f-113">Per informazioni sulla creazione e la modifica dei criteri anti-phishing più avanzati in Microsoft Defender per Office 365 disponibili in Defender per Office 365, vedere [Configure anti-phishing policies in Microsoft Defender for Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-113">For information about creating and modifying the more advanced anti-phishing policies in Microsoft Defender for Office 365 that are available in Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

<span data-ttu-id="2cd2f-114">Gli elementi di base di un criterio anti-phishing sono:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="2cd2f-115">**Il criterio anti-phishing**: Specifica le protezioni anti-phishing da abilitare o disabilitare e le azioni da applicare.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="2cd2f-116">**La regola anti-phish**: Specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phish.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="2cd2f-117">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri anti-phishing nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="2cd2f-118">Quando crei un criterio anti-phishing, stai creando una regola anti-phishing e il criterio anti-phishing associato contemporaneamente usando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="2cd2f-119">Quando si modifica un criterio anti-phishing, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="2cd2f-120">Tutte le altre impostazioni modificano il criterio anti-phish associato.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="2cd2f-121">Quando si rimuove un criterio anti-phishing, la regola anti-phishing e il criterio anti-phishing associato vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="2cd2f-122">In PowerShell di Exchange Online, il criterio e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="2cd2f-123">Per ulteriori informazioni, vedere la sezione Utilizzare PowerShell di Exchange Online per configurare i criteri [anti-phishing](#use-exchange-online-powershell-to-configure-anti-phishing-policies) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="2cd2f-124">Ogni organizzazione dispone di un criterio anti-phishing predefinito denominato Office365 AntiPhish Default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="2cd2f-125">Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se al criterio non è associata alcuna regola anti-phish (filtri destinatari).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="2cd2f-126">Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="2cd2f-127">Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="2cd2f-128">Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="2cd2f-129">Per aumentare l'efficacia della protezione anti-phishing, è possibile creare criteri anti-phishing personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2cd2f-130">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2cd2f-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2cd2f-131">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2cd2f-132">Per passare direttamente alla pagina **Anti-phishing,** utilizzare <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="2cd2f-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="2cd2f-133">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="2cd2f-134">Non è possibile gestire i criteri anti-phishing in PowerShell EOP autonomo.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="2cd2f-135">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="2cd2f-136">Per aggiungere, modificare ed eliminare criteri anti-phishing, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="2cd2f-137">Per l'accesso in sola lettura ai criteri anti-phishing, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="2cd2f-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="2cd2f-138">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="2cd2f-139">**Note**:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-139">**Notes**:</span></span>

  - <span data-ttu-id="2cd2f-140">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2cd2f-141">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="2cd2f-142">Il **gruppo di ruoli Gestione organizzazione** di sola visualizzazione in Exchange [Online](/Exchange/permissions-exo/permissions-exo#role-groups) consente inoltre l'accesso in sola lettura alla funzionalità <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="2cd2f-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="2cd2f-143"><sup>\*</sup> Nel Centro sicurezza & conformità, l'accesso di sola lettura consente agli utenti di visualizzare le impostazioni dei criteri anti-phishing personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-143"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="2cd2f-144">Gli utenti di sola lettura non possono visualizzare le impostazioni nel criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-144">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="2cd2f-145">Per creare e modificare i criteri anti-phishing in EOP autonomo, è necessario eseguire un'operazione che richiede l'idratazione _per_ il tenant.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-145">To create and modify anti-phishing policies in standalone EOP, you need to do something that requires _hydration_ for your tenant.</span></span> <span data-ttu-id="2cd2f-146">Ad esempio,   ![ nell'interfaccia di amministrazione di Exchange (EAC), è possibile passare alla scheda Autorizzazioni, selezionare un gruppo di ruoli esistente, fare clic su Modifica icona Modifica e rimuovere un ruolo (che verrà infine aggiunto ](../../media/ITPro-EAC-EditIcon.png) di nuovo).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-146">For example, in the Exchange admin center (EAC), you can go to the **Permissions** tab, select an existing role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and remove a role (which you'll ultimately add back).</span></span> <span data-ttu-id="2cd2f-147">Se il tenant non è mai stato idratato, viene visualizzata una finestra di dialogo denominata **Aggiorna** impostazioni organizzazione con un indicatore di stato che dovrebbe essere completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-147">If your tenant has never been hydrated, you get a dialog named **Update Organization Settings** with a progress bar that should complete successfully.</span></span> <span data-ttu-id="2cd2f-148">Per ulteriori informazioni sull'idratazione, vedere il cmdlet [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) (che non è disponibile in PowerShell EOP autonomo o nel Centro sicurezza & conformità).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-148">For more information about hydration, see the [Enable-OrganizationCustomization](/powershell/module/exchange/enable-organizationcustomization) cmdlet (which isn't available in standalone EOP PowerShell or in the Security & Compliance Center).</span></span>

- <span data-ttu-id="2cd2f-149">Per le impostazioni consigliate per i criteri anti-phishing, vedere Impostazioni dei [criteri anti-phishing predefiniti di EOP.](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-149">For our recommended settings for anti-phishing policies, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="2cd2f-150">Consentire fino a 30 minuti per l'applicazione del criterio aggiornato.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-150">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="2cd2f-151">Per informazioni su dove vengono applicati i criteri anti-phishing nella pipeline di filtro, vedere [Order and precedence of email protection.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-151">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a><span data-ttu-id="2cd2f-152">Usare il Centro sicurezza & conformità per creare criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="2cd2f-152">Use the Security & Compliance Center to create anti-phishing policies</span></span>

<span data-ttu-id="2cd2f-153">La creazione di un criterio anti-phishing personalizzato nel Centro sicurezza & e conformità crea la regola anti-phishing e il criterio anti-phishing associato contemporaneamente usando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-153">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="2cd2f-154">Quando si crea un criterio anti-phishing, è possibile specificare solo il nome, la descrizione e il filtro destinatario che identifica a chi si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-154">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="2cd2f-155">Dopo aver creato il criterio, è possibile modificare il criterio per modificare o rivedere le impostazioni anti-phishing predefinite.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-155">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="2cd2f-156">Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-156">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2cd2f-157">Nella pagina **Anti-phishing** fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-157">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="2cd2f-158">Verrà **visualizzata la procedura guidata Crea un nuovo criterio anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-158">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="2cd2f-159">Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-159">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="2cd2f-160">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-160">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="2cd2f-161">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-161">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="2cd2f-162">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-162">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="2cd2f-163">Nella pagina **Applicato a** visualizzata identificare i destinatari interni a cui si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-163">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="2cd2f-164">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-164">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="2cd2f-165">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-165">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="2cd2f-166">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-166">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="2cd2f-167">Fare **clic su Aggiungi condizione.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-167">Click **Add a condition**.</span></span> <span data-ttu-id="2cd2f-168">Nell'elenco a discesa visualizzato selezionare una condizione in **Applicato se**:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-168">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="2cd2f-169">**Il destinatario è**: Specifica una o più cassette postali, utenti di posta o contatti di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-169">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="2cd2f-170">**Il destinatario è un membro di**: Specifica uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-170">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="2cd2f-171">**Il dominio del destinatario è**: specifica i destinatari in uno o più dei domini configurati accettati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-171">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="2cd2f-172">Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con **una casella** Qualsiasi di queste.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-172">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="2cd2f-173">Fare clic nella casella e scorrere l'elenco di valori da selezionare.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-173">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="2cd2f-174">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-174">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="2cd2f-175">Per aggiungere altri valori, fare clic in un'area vuota della casella.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-175">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="2cd2f-176">Per rimuovere singole voci, fare clic **su Rimuovi** ![ Icona Rimuovi sul ](../../media/scc-remove-icon.png) valore.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-176">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="2cd2f-177">Per rimuovere l'intera condizione, fare **clic su Rimuovi** Icona Rimuovi nella ![ ](../../media/scc-remove-icon.png) condizione.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-177">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="2cd2f-178">Per aggiungere una condizione aggiuntiva, fare clic **su Aggiungi una condizione** e selezionare un valore rimanente in Applicato **se**.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-178">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="2cd2f-179">Per aggiungere eccezioni, fare clic **su Aggiungi una condizione** e selezionare un'eccezione in Tranne **se**.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-179">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="2cd2f-180">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-180">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="2cd2f-181">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-181">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2cd2f-182">Nella pagina **Rivedere le impostazioni** visualizzata esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-182">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="2cd2f-183">È possibile fare **clic su** Modifica per ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-183">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="2cd2f-184">Al termine, fare clic **su Crea questo criterio.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-184">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="2cd2f-185">Fare **clic su OK** nella finestra di dialogo di conferma visualizzata.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-185">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="2cd2f-186">Dopo aver creato il criterio anti-phishing con queste impostazioni generali, seguire le istruzioni nella sezione successiva per configurare le impostazioni di protezione nel criterio.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-186">After you create the anti-phishing policy with these general policy settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a><span data-ttu-id="2cd2f-187">Utilizzare il Centro sicurezza & conformità per modificare i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="2cd2f-187">Use the Security & Compliance Center to modify anti-phishing policies</span></span>

<span data-ttu-id="2cd2f-188">Utilizzare le procedure seguenti per modificare i criteri anti-phishing: un nuovo criterio creato dall'utente o criteri esistenti già personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-188">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="2cd2f-189">Se non si è già presenti, aprire il Centro sicurezza & conformità e passare a **Criteri** di gestione delle minacce \>  \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-189">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2cd2f-190">Selezionare il criterio anti-phishing personalizzato che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-190">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="2cd2f-191">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-191">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="2cd2f-192">Viene **visualizzato \<name\> il riquadro a comparsa** Modifica il criterio.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-192">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="2cd2f-193">Se **si** fa clic su Modifica in qualsiasi sezione, è possibile accedere alle impostazioni in tale sezione.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-193">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="2cd2f-194">I passaggi seguenti vengono presentati nell'ordine in cui vengono visualizzate le sezioni, ma non sono sequenziali (è possibile selezionare e modificare le sezioni in qualsiasi ordine).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-194">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="2cd2f-195">Dopo aver fatto clic su Modifica **in** una sezione, le impostazioni disponibili vengono presentate in un  formato di procedura guidata,  ma è possibile passare all'interno delle pagine in qualsiasi ordine e fare clic su Salva in qualsiasi pagina (o  ![ ](../../media/scc-remove-icon.png) **\<name\>** Icona Annulla o Chiudi chiudi per tornare alla pagina Modifica i criteri (non è necessario visitare l'ultima pagina della procedura guidata per salvare o uscire).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-195">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="2cd2f-196">**Impostazione dei criteri:** **fare** clic su Modifica per modificare le stesse impostazioni disponibili al momento della [creazione](#use-the-security--compliance-center-to-create-anti-phishing-policies) del criterio nella sezione precedente:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-196">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies) in the previous section:</span></span>

   - <span data-ttu-id="2cd2f-197">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-197">**Name**</span></span>
   - <span data-ttu-id="2cd2f-198">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-198">**Description**</span></span>
   - <span data-ttu-id="2cd2f-199">**Applicato a**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-199">**Applied to**</span></span>
   - <span data-ttu-id="2cd2f-200">**Rivedere le impostazioni**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-200">**Review your settings**</span></span>

   <span data-ttu-id="2cd2f-201">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-201">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="2cd2f-202">**Spoof**: **fare** clic su Modifica per attivare o disattivare l'intelligence spoofing, attivare o disattivare l'identificazione del mittente non autenticato in Outlook e configurare l'azione da applicare ai messaggi provenienti da mittenti falsificati bloccati.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-202">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="2cd2f-203">Per ulteriori informazioni, vedere [Spoofing settings in anti-phishing policies.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-203">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="2cd2f-204">Si noti che queste stesse impostazioni sono disponibili anche nei criteri anti-phishing in Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-204">Note that these same settings are also available in anti-phishing policies in Defender for Office 365.</span></span>

   - <span data-ttu-id="2cd2f-205">**Impostazioni del filtro di spoofing**: il valore predefinito è **On** e si consiglia di lasciarlo.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-205">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="2cd2f-206">Per disattivarlo, fai scorrere l'interruttore su **Off.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-206">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="2cd2f-207">Per ulteriori informazioni, vedere [Configure spoof intelligence in EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-207">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="2cd2f-208">Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Microsoft 365. si abilita invece il filtro avanzato per i connettori.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-208">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="2cd2f-209">Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-209">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="2cd2f-210">**Abilita funzionalità mittente non autenticato**: il valore predefinito è **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-210">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="2cd2f-211">Per disattivarlo, fai scorrere l'interruttore su **Off.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-211">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="2cd2f-212">**Azioni**: specificare l'azione da eseguire sui messaggi che non riescono a spoof intelligence:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-212">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="2cd2f-213">**Se la posta elettronica viene inviata da un utente a cui non è consentito effettuare lo spoofing del dominio:**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-213">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="2cd2f-214">**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-214">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="2cd2f-215">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-215">**Quarantine the message**</span></span>

   - <span data-ttu-id="2cd2f-216">**Rivedere le impostazioni:** invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-216">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="2cd2f-217">È possibile fare **clic su** Modifica in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-217">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="2cd2f-218">È possibile attivare o **disattivare** le impostazioni seguenti **direttamente** in questa pagina:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-218">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="2cd2f-219">**Abilitare la protezione antispoofing**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-219">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="2cd2f-220">**Abilitare la funzionalità Mittente non autenticato**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-220">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="2cd2f-221">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-221">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="2cd2f-222">Tornare alla pagina **Modifica i \<Name\> criteri,** rivedere le impostazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-222">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="2cd2f-223">Utilizzare il Centro sicurezza & conformità per modificare il criterio anti-phishing predefinito</span><span class="sxs-lookup"><span data-stu-id="2cd2f-223">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="2cd2f-224">Il criterio anti-phishing predefinito è denominato Office365 AntiPhish Default e non viene visualizzato nell'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-224">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="2cd2f-225">Per modificare il criterio anti-phishing predefinito, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-225">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="2cd2f-226">Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-226">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2cd2f-227">Nella pagina **Anti-phishing** fare clic su **Criterio predefinito.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-227">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="2cd2f-228">Viene visualizzata la pagina Modifica il criterio **Office365 AntiPhish Default.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-228">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="2cd2f-229">Sono disponibili le sezioni seguenti, che contengono impostazioni identiche per quando si [modifica un criterio personalizzato.](#use-the-security--compliance-center-to-modify-anti-phishing-policies)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-229">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies).</span></span>

   - <span data-ttu-id="2cd2f-230">**Rappresentazione**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-230">**Impersonation**</span></span>
   - <span data-ttu-id="2cd2f-231">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-231">**Spoof**</span></span>
   - <span data-ttu-id="2cd2f-232">**Impostazioni avanzate**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-232">**Advanced settings**</span></span>

   <span data-ttu-id="2cd2f-233">Le impostazioni seguenti non sono disponibili quando si modifica il criterio predefinito:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-233">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="2cd2f-234">È possibile  visualizzare la sezione Impostazioni criteri e  i valori, ma non è disponibile alcun collegamento Modifica, quindi non è possibile modificare le impostazioni (nome del criterio, descrizione e a chi si applica il criterio (si applica a tutti i destinatari)).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-234">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="2cd2f-235">Non è possibile eliminare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-235">You can't delete the default policy.</span></span>
   - <span data-ttu-id="2cd2f-236">Non è possibile modificare la priorità del criterio predefinito (viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-236">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="2cd2f-237">Nella pagina **Modifica i criteri Office365 AntiPhish Default** rivedere le impostazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-237">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="2cd2f-238">Abilitare o disabilitare i criteri anti-phishing personalizzati</span><span class="sxs-lookup"><span data-stu-id="2cd2f-238">Enable or disable custom anti-phishing policies</span></span>

1. <span data-ttu-id="2cd2f-239">Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-239">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2cd2f-240">Notare il valore nella **colonna** Stato:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-240">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="2cd2f-241">Fai scorrere **l'interruttore su Off** per disabilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-241">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="2cd2f-242">Fai scorrere **l'interruttore su Attivato** per abilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-242">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="2cd2f-243">Non è possibile disabilitare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-243">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="2cd2f-244">Impostare la priorità dei criteri anti-phishing personalizzati</span><span class="sxs-lookup"><span data-stu-id="2cd2f-244">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="2cd2f-245">Per impostazione predefinita, ai criteri anti-phishing viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-245">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="2cd2f-246">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-246">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="2cd2f-247">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-247">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="2cd2f-248">Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-248">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="2cd2f-249">I criteri anti-phishing personalizzati vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-249">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="2cd2f-250">Il criterio anti-phishing predefinito denominato Office365 AntiPhish Default ha il valore di priorità personalizzato **Lowest** e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-250">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="2cd2f-251">**Nota:** nel Centro sicurezza & conformità, è possibile modificare la priorità del criterio anti-phishing solo dopo aver creato il criterio.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-251">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="2cd2f-252">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phish (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-252">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="2cd2f-253">Per modificare la priorità di  un criterio, fare clic su Aumenta priorità o Riduci  priorità nelle proprietà del criterio (non è possibile modificare direttamente il numero di priorità nel Centro sicurezza & conformità). </span><span class="sxs-lookup"><span data-stu-id="2cd2f-253">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="2cd2f-254">La modifica della priorità di un criterio ha senso solo se si dispone di più criteri.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-254">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="2cd2f-255">Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce \>  \> **ATP anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-255">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="2cd2f-256">Selezionare il criterio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-256">Select the policy that you want to modify.</span></span> <span data-ttu-id="2cd2f-257">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-257">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="2cd2f-258">Viene **visualizzato \<name\> il riquadro a comparsa** Modifica il criterio.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-258">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="2cd2f-259">Il criterio anti-phishing personalizzato con **il valore Priority** **0** ha solo il **pulsante Riduci** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-259">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="2cd2f-260">Il criterio anti-phishing personalizzato con il valore **priority** più basso (ad esempio, **3**) ha solo il **pulsante Aumenta** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-260">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="2cd2f-261">Se si dispone di tre o più criteri anti-phishing personalizzati,  i criteri  tra i valori di priorità più alta e più bassa hanno entrambi i pulsanti Aumenta priorità e Riduci priorità disponibili.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-261">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="2cd2f-262">Fare **clic su Aumenta priorità** o **Diminuisci priorità** per modificare il valore **Priorità.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-262">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="2cd2f-263">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-263">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a><span data-ttu-id="2cd2f-264">Usare il Centro sicurezza & conformità per visualizzare i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="2cd2f-264">Use the Security & Compliance Center to view anti-phishing policies</span></span>

1. <span data-ttu-id="2cd2f-265">Nel Centro sicurezza & conformità e passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-265">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2cd2f-266">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-266">Do one of the following steps:</span></span>

   - <span data-ttu-id="2cd2f-267">Selezionare un criterio anti-phishing personalizzato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-267">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="2cd2f-268">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-268">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="2cd2f-269">Fare **clic su Criterio** predefinito per visualizzare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-269">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="2cd2f-270">Viene **visualizzato \<name\> il riquadro a** comparsa Modifica il criterio, in cui è possibile visualizzare le impostazioni e i valori.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-270">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a><span data-ttu-id="2cd2f-271">Usare il Centro sicurezza & conformità per rimuovere i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="2cd2f-271">Use the Security & Compliance Center to remove anti-phishing policies</span></span>

1. <span data-ttu-id="2cd2f-272">Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-272">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2cd2f-273">Selezionare il criterio che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-273">Select the policy that you want to remove.</span></span> <span data-ttu-id="2cd2f-274">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-274">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="2cd2f-275">Nel riquadro **a \<name\> comparsa Modifica criterio** visualizzato fare clic **su** Elimina criterio e quindi su **Sì** nella finestra di dialogo di avviso visualizzata.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-275">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="2cd2f-276">Non è possibile rimuovere il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-276">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="2cd2f-277">Utilizzare PowerShell di Exchange Online per configurare i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="2cd2f-277">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="2cd2f-278">Come descritto in precedenza, un criterio anti-phishing è costituito da un criterio anti-phishing e da una regola anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-278">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="2cd2f-279">In PowerShell di Exchange Online, la differenza tra i criteri anti-phish e le regole anti-phish è evidente.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-279">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="2cd2f-280">È possibile gestire i criteri anti-phish utilizzando i cmdlet **\* -AntiPhishPolicy** e gestire le regole anti-phish utilizzando i cmdlet **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-280">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="2cd2f-281">In PowerShell, si crea prima il criterio anti-phish, quindi si crea la regola anti-phish che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-281">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="2cd2f-282">In PowerShell, le impostazioni dei criteri anti-phish e della regola anti-phish vengono modificate separatamente.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-282">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="2cd2f-283">Quando si rimuove un criterio anti-phish da PowerShell, la regola anti-phish corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-283">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="2cd2f-284">Le procedure di PowerShell seguenti non sono disponibili nelle organizzazioni EOP autonome che utilizzano PowerShell di Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-284">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="2cd2f-285">Utilizzare PowerShell per creare criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="2cd2f-285">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="2cd2f-286">La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-286">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="2cd2f-287">Creare i criteri anti-phish.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-287">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="2cd2f-288">Creare la regola anti-phish che specifica il criterio anti-phish a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-288">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="2cd2f-289">**Note**:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-289">**Notes**:</span></span>

- <span data-ttu-id="2cd2f-290">È possibile creare una nuova regola anti-phish e assegnarle un criterio anti-phish esistente e non associazione.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-290">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="2cd2f-291">Una regola anti-phish non può essere associata a più di un criterio anti-phish.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-291">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="2cd2f-292">È possibile configurare le impostazioni seguenti nei nuovi criteri anti-phish in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-292">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="2cd2f-293">Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-293">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="2cd2f-294">Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-294">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="2cd2f-295">Un nuovo criterio anti-phish creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-295">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="2cd2f-296">Passaggio 1: Usare PowerShell per creare un criterio anti-phish</span><span class="sxs-lookup"><span data-stu-id="2cd2f-296">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="2cd2f-297">Per creare un criterio anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-297">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="2cd2f-298">In questo esempio viene creato un criterio anti-phish denominato Research Quarantine con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-298">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="2cd2f-299">La descrizione è: Criteri del reparto di ricerca.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-299">The description is: Research department policy.</span></span>
- <span data-ttu-id="2cd2f-300">Modifica l'azione predefinita per lo spoofing in Quarantena.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-300">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="2cd2f-301">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-301">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="2cd2f-302">Passaggio 2: Usare PowerShell per creare una regola anti-phish</span><span class="sxs-lookup"><span data-stu-id="2cd2f-302">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="2cd2f-303">Per creare una regola anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-303">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="2cd2f-304">In questo esempio viene creata una regola anti-phish denominata Research Department con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-304">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="2cd2f-305">La regola è associata al criterio anti-phish denominato Quarantena ricerche.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-305">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="2cd2f-306">La regola viene applicata ai membri del gruppo denominato Research Department.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-306">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="2cd2f-307">Poiché non si utilizza il parametro _Priority,_ viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-307">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="2cd2f-308">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-308">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="2cd2f-309">Usare PowerShell per visualizzare i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="2cd2f-309">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="2cd2f-310">Per visualizzare i criteri anti-phish esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-310">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="2cd2f-311">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri anti-phish insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-311">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="2cd2f-312">In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio anti-phish denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-312">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="2cd2f-313">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-313">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="2cd2f-314">Usare PowerShell per visualizzare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="2cd2f-314">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="2cd2f-315">Per visualizzare le regole anti-phish esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-315">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="2cd2f-316">In questo esempio viene restituito un elenco riepilogativo di tutte le regole anti-phish insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-316">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="2cd2f-317">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-317">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="2cd2f-318">In questo esempio vengono restituiti tutti i valori delle proprietà per la regola anti-phish denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-318">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="2cd2f-319">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-319">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="2cd2f-320">Utilizzare PowerShell per modificare i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="2cd2f-320">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="2cd2f-321">Oltre agli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio anti-phish in PowerShell come quando si crea un criterio come descritto in [Passaggio 1: Utilizzare PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) per creare un criterio anti-phish più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-321">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="2cd2f-322">L'opzione _MakeDefault_ che trasforma il criterio specificato nel  criterio predefinito (applicato a tutti, sempre con priorità minima e non è possibile eliminarlo) è disponibile solo quando si modifica un criterio anti-phish in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-322">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="2cd2f-323">Non è possibile rinominare un criterio anti-phish (il cmdlet **Set-AntiPhishPolicy** non dispone di _alcun parametro Name)._</span><span class="sxs-lookup"><span data-stu-id="2cd2f-323">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="2cd2f-324">Quando si rinomina un criterio anti-phishing nel Centro sicurezza & conformità, si rinomina solo la regola _anti-phishing._</span><span class="sxs-lookup"><span data-stu-id="2cd2f-324">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="2cd2f-325">Per modificare un criterio anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-325">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="2cd2f-326">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-326">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="2cd2f-327">Utilizzare PowerShell per modificare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="2cd2f-327">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="2cd2f-328">L'unica impostazione non disponibile quando si modifica una regola anti-phish in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-328">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="2cd2f-329">Per abilitare o disabilitare le regole anti-phish esistenti, vedi la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-329">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="2cd2f-330">In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione Passaggio 2: utilizzare PowerShell per creare una regola [anti-phish](#step-2-use-powershell-to-create-an-anti-phish-rule) in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-330">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="2cd2f-331">Per modificare una regola anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-331">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="2cd2f-332">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-332">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="2cd2f-333">Usare PowerShell per abilitare o disabilitare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="2cd2f-333">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="2cd2f-334">L'abilitazione o la disabilitazione di una regola anti-phishing in PowerShell abilita o disabilita l'intero criterio anti-phishing (la regola anti-phishing e il criterio anti-phishing assegnato).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-334">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="2cd2f-335">Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-335">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="2cd2f-336">Per abilitare o disabilitare una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-336">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="2cd2f-337">In questo esempio viene disabilitata la regola anti-phish denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-337">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="2cd2f-338">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-338">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="2cd2f-339">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-339">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="2cd2f-340">Usare PowerShell per impostare la priorità delle regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="2cd2f-340">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="2cd2f-341">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-341">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="2cd2f-342">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-342">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="2cd2f-343">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-343">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="2cd2f-344">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-344">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="2cd2f-345">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-345">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="2cd2f-346">Per impostare la priorità di una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-346">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="2cd2f-p138">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="2cd2f-p138">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="2cd2f-349">**Note**:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-349">**Notes**:</span></span>

- <span data-ttu-id="2cd2f-350">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare invece il parametro _Priority_ nel cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-350">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="2cd2f-351">Il criterio anti-phish predefinito non dispone di una regola anti-phish corrispondente e ha sempre il valore di priorità non modificabile **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-351">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="2cd2f-352">Usare PowerShell per rimuovere i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="2cd2f-352">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="2cd2f-353">Quando si utilizza PowerShell per rimuovere un criterio anti-phish, la regola anti-phish corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-353">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="2cd2f-354">Per rimuovere un criterio anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-354">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="2cd2f-355">In questo esempio viene rimosso il criterio anti-phish denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-355">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="2cd2f-356">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-356">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="2cd2f-357">Usare PowerShell per rimuovere le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="2cd2f-357">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="2cd2f-358">Quando si utilizza PowerShell per rimuovere una regola anti-phish, il criterio anti-phish corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-358">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="2cd2f-359">Per rimuovere una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-359">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="2cd2f-360">In questo esempio viene rimossa la regola anti-phish denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-360">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="2cd2f-361">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="2cd2f-361">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="2cd2f-362">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="2cd2f-362">How do you know these procedures worked?</span></span>

<span data-ttu-id="2cd2f-363">Per verificare la corretta configurazione dei criteri anti-phishing in Microsoft Defender per Office 365, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-363">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="2cd2f-364">Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-364">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="2cd2f-365">Verificare l'elenco dei criteri, i **relativi valori status** e i relativi valori **Priority.**</span><span class="sxs-lookup"><span data-stu-id="2cd2f-365">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="2cd2f-366">Per visualizzare ulteriori dettagli, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-366">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="2cd2f-367">Selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-367">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="2cd2f-368">Fare **clic su** Criterio predefinito e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="2cd2f-368">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="2cd2f-369">In PowerShell di Exchange Online, sostituire con il nome del criterio o della regola, eseguire \<Name\> il comando seguente e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="2cd2f-369">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```