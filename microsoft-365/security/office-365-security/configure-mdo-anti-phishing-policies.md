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
ms.openlocfilehash: 3660b9574f4faf4ee9c0602ac23b36f8634650dc
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537908"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2d40f-103">Configurare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2d40f-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2d40f-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="2d40f-104">**Applies to**</span></span>
- [<span data-ttu-id="2d40f-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="2d40f-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2d40f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d40f-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="2d40f-107">I criteri anti-phishing in [Microsoft Defender per Office 365](defender-for-office-365.md) possono aiutare a proteggere l'organizzazione da attacchi di phishing dannosi basati sulla rappresentazione e da altri tipi di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="2d40f-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="2d40f-108">Per ulteriori informazioni sulle differenze tra i criteri anti-phishing in Exchange Online Protection (EOP) e i criteri anti-phishing in Microsoft Defender per Office 365, vedere [Protezione anti-phishing.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="2d40f-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="2d40f-109">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="2d40f-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="2d40f-110">Per una maggiore granularità, è inoltre possibile creare criteri anti-phishing personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2d40f-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="2d40f-111">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).</span><span class="sxs-lookup"><span data-stu-id="2d40f-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="2d40f-112">È possibile configurare i criteri anti-phishing nel Centro sicurezza & conformità o in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d40f-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="2d40f-113">Per informazioni sulla configurazione dei criteri anti-phishing più limitati disponibili nelle organizzazioni di Exchange Online Protection (ovvero le organizzazioni senza Microsoft Defender per Office 365), vedere [Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="2d40f-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="2d40f-114">Gli elementi di base di un criterio anti-phishing sono:</span><span class="sxs-lookup"><span data-stu-id="2d40f-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="2d40f-115">**Il criterio anti-phishing**: Specifica le protezioni anti-phishing da abilitare o disabilitare e le azioni da applicare.</span><span class="sxs-lookup"><span data-stu-id="2d40f-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="2d40f-116">**La regola anti-phish**: Specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phish.</span><span class="sxs-lookup"><span data-stu-id="2d40f-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="2d40f-117">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri anti-phishing nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="2d40f-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="2d40f-118">Quando crei un criterio, stai creando una regola anti-phish e il criterio anti-phish associato contemporaneamente usando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="2d40f-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="2d40f-119">Quando si modifica un criterio, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="2d40f-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="2d40f-120">Tutte le altre impostazioni modificano il criterio anti-phish associato.</span><span class="sxs-lookup"><span data-stu-id="2d40f-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="2d40f-121">Quando si rimuove un criterio, vengono rimossi la regola anti-phish e il criterio anti-phish associato.</span><span class="sxs-lookup"><span data-stu-id="2d40f-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="2d40f-122">In Exchange Online PowerShell, il criterio e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="2d40f-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="2d40f-123">Per ulteriori informazioni, vedere la sezione Usare Exchange Online PowerShell per configurare i criteri [anti-phishing in Microsoft Defender per Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="2d40f-124">Ogni organizzazione di Microsoft Defender per Office 365 dispone di un criterio anti-phishing predefinito denominato Office365 AntiPhish Default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="2d40f-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="2d40f-125">Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se al criterio non è associata alcuna regola anti-phish (filtri destinatari).</span><span class="sxs-lookup"><span data-stu-id="2d40f-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="2d40f-126">Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="2d40f-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="2d40f-127">Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="2d40f-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="2d40f-128">Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="2d40f-129">Per aumentare l'efficacia della protezione anti-phishing in Microsoft Defender per Office 365, è possibile creare criteri anti-phishing personalizzati con impostazioni più restrittive applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="2d40f-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2d40f-130">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2d40f-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2d40f-131">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2d40f-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2d40f-132">Per passare direttamente alla pagina **Anti-phishing,** utilizzare <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="2d40f-132">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="2d40f-133">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2d40f-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2d40f-134">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="2d40f-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="2d40f-135">Per aggiungere, modificare ed eliminare criteri anti-phishing, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="2d40f-136">Per l'accesso in sola lettura ai criteri anti-phishing, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="2d40f-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="2d40f-137">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="2d40f-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="2d40f-138">**Note**:</span><span class="sxs-lookup"><span data-stu-id="2d40f-138">**Notes**:</span></span>

  - <span data-ttu-id="2d40f-139">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d40f-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2d40f-140">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2d40f-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="2d40f-141">Il **gruppo di ruoli Gestione organizzazione** di sola visualizzazione in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) consente inoltre l'accesso in sola lettura alla funzionalità <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="2d40f-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="2d40f-142"><sup>\*</sup> Nel Centro sicurezza & conformità, l'accesso di sola lettura consente agli utenti di visualizzare le impostazioni dei criteri anti-phishing personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2d40f-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="2d40f-143">Gli utenti di sola lettura non possono visualizzare le impostazioni nel criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="2d40f-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="2d40f-144">Per le impostazioni consigliate per i criteri anti-phishing in Microsoft Defender per Office 365, vedere [Criteri anti-phishing in Defender per Office 365 impostazioni](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="2d40f-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="2d40f-145">Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.</span><span class="sxs-lookup"><span data-stu-id="2d40f-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="2d40f-146">Per informazioni su dove vengono applicati i criteri anti-phishing nella pipeline di filtro, vedere [Order and precedence of email protection.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="2d40f-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2d40f-147">Usare il Centro sicurezza & conformità per creare criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2d40f-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2d40f-148">La creazione di un criterio anti-phishing personalizzato nel Centro sicurezza & e conformità crea la regola anti-phishing e il criterio anti-phishing associato contemporaneamente usando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="2d40f-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="2d40f-149">Quando si crea un criterio anti-phishing, è possibile specificare solo il nome, la descrizione e il filtro destinatario che identifica a chi si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="2d40f-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="2d40f-150">Dopo aver creato il criterio, è possibile modificare il criterio per modificare o rivedere le impostazioni anti-phishing predefinite.</span><span class="sxs-lookup"><span data-stu-id="2d40f-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="2d40f-151">Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2d40f-152">Nella pagina **Anti-phishing** fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="2d40f-153">Verrà **visualizzata la procedura guidata Crea un nuovo criterio anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="2d40f-154">Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d40f-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="2d40f-155">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="2d40f-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="2d40f-156">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="2d40f-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="2d40f-157">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="2d40f-158">Nella pagina **Applicato a** visualizzata identificare i destinatari interni a cui si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="2d40f-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="2d40f-159">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="2d40f-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="2d40f-160">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="2d40f-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="2d40f-161">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="2d40f-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="2d40f-162">Fare **clic su Aggiungi condizione.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-162">Click **Add a condition**.</span></span> <span data-ttu-id="2d40f-163">Nell'elenco a discesa visualizzato selezionare una condizione in **Applicato se**:</span><span class="sxs-lookup"><span data-stu-id="2d40f-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="2d40f-164">**Il destinatario è**: Specifica una o più cassette postali, utenti di posta o contatti di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2d40f-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="2d40f-165">**Il destinatario è un membro di**: Specifica uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2d40f-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="2d40f-166">**Il dominio del destinatario** è : Specifica i destinatari in uno o più domini accettati configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2d40f-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="2d40f-167">Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con **una casella** Qualsiasi di queste.</span><span class="sxs-lookup"><span data-stu-id="2d40f-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="2d40f-168">Fare clic nella casella e scorrere l'elenco di valori da selezionare.</span><span class="sxs-lookup"><span data-stu-id="2d40f-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="2d40f-169">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="2d40f-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="2d40f-170">Per aggiungere altri valori, fare clic in un'area vuota della casella.</span><span class="sxs-lookup"><span data-stu-id="2d40f-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="2d40f-171">Per rimuovere singole voci, fare clic **su Rimuovi** ![ Icona Rimuovi sul ](../../media/scc-remove-icon.png) valore.</span><span class="sxs-lookup"><span data-stu-id="2d40f-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="2d40f-172">Per rimuovere l'intera condizione, fare **clic su Rimuovi** Icona Rimuovi nella ![ ](../../media/scc-remove-icon.png) condizione.</span><span class="sxs-lookup"><span data-stu-id="2d40f-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="2d40f-173">Per aggiungere una condizione aggiuntiva, fare clic **su Aggiungi una condizione** e selezionare un valore rimanente in Applicato **se**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="2d40f-174">Per aggiungere eccezioni, fare clic **su Aggiungi una condizione** e selezionare un'eccezione in Tranne **se**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="2d40f-175">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="2d40f-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="2d40f-176">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2d40f-177">Nella pagina **Rivedere le impostazioni** visualizzata esaminare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2d40f-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="2d40f-178">È possibile fare **clic su** Modifica per ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="2d40f-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="2d40f-179">Al termine, fare clic **su Crea questo criterio.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="2d40f-180">Fare **clic su OK** nella finestra di dialogo di conferma visualizzata.</span><span class="sxs-lookup"><span data-stu-id="2d40f-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="2d40f-181">Dopo aver creato il criterio anti-phishing con queste impostazioni generali, seguire le istruzioni nella sezione successiva per configurare le impostazioni di protezione nel criterio.</span><span class="sxs-lookup"><span data-stu-id="2d40f-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2d40f-182">Utilizzare il Centro sicurezza & conformità per modificare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2d40f-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2d40f-183">Utilizzare le procedure seguenti per modificare i criteri anti-phishing: un nuovo criterio creato dall'utente o criteri esistenti già personalizzati.</span><span class="sxs-lookup"><span data-stu-id="2d40f-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="2d40f-184">Se non si è già presenti, aprire il Centro sicurezza & conformità e passare a **Criteri** di gestione delle minacce \>  \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2d40f-185">Selezionare il criterio anti-phishing personalizzato che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="2d40f-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="2d40f-186">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="2d40f-187">Viene **visualizzato \<name\> il riquadro a comparsa** Modifica il criterio.</span><span class="sxs-lookup"><span data-stu-id="2d40f-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="2d40f-188">Se **si** fa clic su Modifica in qualsiasi sezione, è possibile accedere alle impostazioni in tale sezione.</span><span class="sxs-lookup"><span data-stu-id="2d40f-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="2d40f-189">I passaggi seguenti vengono presentati nell'ordine in cui vengono visualizzate le sezioni, ma non sono sequenziali (è possibile selezionare e modificare le sezioni in qualsiasi ordine).</span><span class="sxs-lookup"><span data-stu-id="2d40f-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="2d40f-190">Dopo aver fatto clic su Modifica **in** una sezione, le impostazioni disponibili vengono presentate in un  formato di procedura guidata,  ma è possibile passare all'interno delle pagine in qualsiasi ordine e fare clic su Salva in qualsiasi pagina (o  ![ ](../../media/scc-remove-icon.png) **\<name\>** Icona Annulla o Chiudi chiudi per tornare alla pagina Modifica i criteri (non è necessario visitare l'ultima pagina della procedura guidata per salvare o uscire).</span><span class="sxs-lookup"><span data-stu-id="2d40f-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="2d40f-191">**Impostazione dei criteri:** **fare** clic su Modifica per modificare le stesse impostazioni disponibili al momento della [creazione](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) del criterio nella sezione precedente:</span><span class="sxs-lookup"><span data-stu-id="2d40f-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="2d40f-192">**Nome**</span><span class="sxs-lookup"><span data-stu-id="2d40f-192">**Name**</span></span>
   - <span data-ttu-id="2d40f-193">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2d40f-193">**Description**</span></span>
   - <span data-ttu-id="2d40f-194">**Applicato a**</span><span class="sxs-lookup"><span data-stu-id="2d40f-194">**Applied to**</span></span>
   - <span data-ttu-id="2d40f-195">**Rivedere le impostazioni**</span><span class="sxs-lookup"><span data-stu-id="2d40f-195">**Review your settings**</span></span>

   <span data-ttu-id="2d40f-196">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="2d40f-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="2d40f-197">**Rappresentazione:** fare **clic su Modifica** per modificare i mittenti protetti e i domini dei mittenti protetti nel criterio.</span><span class="sxs-lookup"><span data-stu-id="2d40f-197">**Impersonation**: Click **Edit** to modify the protected senders and protected sender domains in the policy.</span></span> <span data-ttu-id="2d40f-198">Queste impostazioni sono una condizione per il criterio che identifica mittenti specifici da cercare (singolarmente o per dominio) nell'indirizzo mittente dei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="2d40f-198">These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="2d40f-199">Per ulteriori informazioni, vedere [Impostazioni di rappresentazione nei criteri anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="2d40f-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="2d40f-200">**Aggiungere utenti da proteggere**: il valore predefinito è **Off** ![ Toggle ](../../media/scc-toggle-off.png) Off.</span><span class="sxs-lookup"><span data-stu-id="2d40f-200">**Add users to protect**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="2d40f-201">Per attivarlo, fai scorrere  l'interruttore su ![ Attiva/Disattiva ](../../media/scc-toggle-on.png) e quindi fai clic sul **pulsante** Aggiungi utente visualizzato.</span><span class="sxs-lookup"><span data-stu-id="2d40f-201">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png), and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="2d40f-202">Nel riquadro **a comparsa** Aggiungi utente visualizzato configurare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d40f-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="2d40f-203">**Indirizzo di posta elettronica**:</span><span class="sxs-lookup"><span data-stu-id="2d40f-203">**Email address**:</span></span>

       - <span data-ttu-id="2d40f-204">Fare clic nella casella e scorrere l'elenco di utenti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="2d40f-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="2d40f-205">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="2d40f-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="2d40f-206">Per rimuovere una voce, fare clic **su Rimuovi** Icona ![ Rimuovi ](../../media/scc-remove-icon.png) nell'utente.</span><span class="sxs-lookup"><span data-stu-id="2d40f-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="2d40f-207">**Nome**: questo valore viene popolato in base all'indirizzo di posta elettronica selezionato, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="2d40f-208">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="2d40f-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="2d40f-209">Per modificare una voce esistente, selezionare l'utente protetto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2d40f-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="2d40f-210">In ogni criterio anti-phishing, è possibile specificare un massimo di 60 utenti protetti (indirizzi di posta elettronica del mittente).</span><span class="sxs-lookup"><span data-stu-id="2d40f-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="2d40f-211">Non è possibile specificare lo stesso utente protetto in più criteri.</span><span class="sxs-lookup"><span data-stu-id="2d40f-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="2d40f-212">La protezione della rappresentazione dell'utente non funziona se il mittente e il destinatario hanno precedentemente comunicato tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="2d40f-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="2d40f-213">Se il mittente e il destinatario non hanno mai comunicato tramite posta elettronica, il messaggio verrà identificato come tentativo di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="2d40f-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="2d40f-214">**Aggiungere domini da proteggere**: configurare una o entrambe le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d40f-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="2d40f-215">**Includi automaticamente i domini di cui sono proprietario**: il valore predefinito è **Off** ![ Toggle ](../../media/scc-toggle-off.png) Off.</span><span class="sxs-lookup"><span data-stu-id="2d40f-215">**Automatically include the domains I own**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="2d40f-216">Per attivarlo, fai scorrere l'interruttore **su** ![ ](../../media/scc-toggle-on.png) Attiva/Disattiva.</span><span class="sxs-lookup"><span data-stu-id="2d40f-216">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png).</span></span>

       <span data-ttu-id="2d40f-217">Per visualizzare i domini di cui si è proprietari, selezionare **Visualizza domini di cui si è proprietari.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-217">To view the domains that you own, select **View domains I own**.</span></span>

     - <span data-ttu-id="2d40f-218">**Includi domini personalizzati**: il valore predefinito è **Off** ![ Toggle ](../../media/scc-toggle-off.png) Off.</span><span class="sxs-lookup"><span data-stu-id="2d40f-218">**Include custom domains**: The default value is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="2d40f-219">Per attivarlo, fai scorrere  l'interruttore su Attiva/Disattiva e nella casella Aggiungi domini immetti il nome di dominio ![ ](../../media/scc-toggle-on.png) (ad esempio, contoso.com),  premi INVIO e ripeti se necessario.</span><span class="sxs-lookup"><span data-stu-id="2d40f-219">To turn it on, slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png), and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="2d40f-220">È possibile avere un massimo di 50 domini in tutti i criteri anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="2d40f-220">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="2d40f-221">**Azioni**: fare clic su **Modifica**</span><span class="sxs-lookup"><span data-stu-id="2d40f-221">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="2d40f-222">**Se la posta elettronica viene** inviata da un utente rappresentato: configurare una delle azioni seguenti per i messaggi in cui il mittente è uno degli utenti protetti specificati in Aggiungere utenti da **proteggere:**</span><span class="sxs-lookup"><span data-stu-id="2d40f-222">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="2d40f-223">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="2d40f-223">**Don't apply any action**</span></span>
       - <span data-ttu-id="2d40f-224">**Reindirizzare il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="2d40f-224">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="2d40f-225">**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="2d40f-225">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="2d40f-226">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="2d40f-226">**Quarantine the message**</span></span>
       - <span data-ttu-id="2d40f-227">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="2d40f-227">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="2d40f-228">**Eliminare il messaggio prima che venga recapitato**</span><span class="sxs-lookup"><span data-stu-id="2d40f-228">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="2d40f-229">**Se la posta elettronica** viene inviata da un dominio rappresentato: configurare una delle azioni seguenti per i messaggi in cui il dominio del mittente si trova in uno dei domini protetti specificati in Aggiungere domini per **proteggere**:</span><span class="sxs-lookup"><span data-stu-id="2d40f-229">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the sender's domain is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="2d40f-230">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="2d40f-230">**Don't apply any action**</span></span>
       - <span data-ttu-id="2d40f-231">**Reindirizzare il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="2d40f-231">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="2d40f-232">**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="2d40f-232">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="2d40f-233">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="2d40f-233">**Quarantine the message**</span></span>
       - <span data-ttu-id="2d40f-234">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="2d40f-234">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="2d40f-235">**Eliminare il messaggio prima che venga recapitato**</span><span class="sxs-lookup"><span data-stu-id="2d40f-235">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="2d40f-236">Fare **clic su Attiva suggerimenti per la sicurezza della rappresentazione** e configurare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d40f-236">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="2d40f-237">**Mostra suggerimento per gli utenti impersonati**</span><span class="sxs-lookup"><span data-stu-id="2d40f-237">**Show tip for impersonated users**</span></span>
     - <span data-ttu-id="2d40f-238">**Mostra suggerimento per i domini impersonati**</span><span class="sxs-lookup"><span data-stu-id="2d40f-238">**Show tip for impersonated domains**</span></span>
     - <span data-ttu-id="2d40f-239">**Mostra suggerimento per caratteri insoliti**</span><span class="sxs-lookup"><span data-stu-id="2d40f-239">**Show tip for unusual characters**</span></span>

     <span data-ttu-id="2d40f-240">Il valore predefinito per tutti i suggerimenti è **Off** ![ Toggle ](../../media/scc-toggle-off.png) Off.</span><span class="sxs-lookup"><span data-stu-id="2d40f-240">The default value for all tips is **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span> <span data-ttu-id="2d40f-241">Per attivarli, fai scorrere l'interruttore **su** [Attiva/Disattiva.](../../media/scc-toggle-on.png)</span><span class="sxs-lookup"><span data-stu-id="2d40f-241">To turn any of them on, slide the toggle to **On** [Toggle On](../../media/scc-toggle-on.png).</span></span>

     <span data-ttu-id="2d40f-242">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="2d40f-243">**Intelligence delle cassette postali**:</span><span class="sxs-lookup"><span data-stu-id="2d40f-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="2d40f-244">**Enable mailbox intelligence?**: Il valore predefinito è **On** [Toggle On](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="2d40f-244">**Enable mailbox intelligence?**: The default value is **On** [Toggle On](../../media/scc-toggle-on.png).</span></span> <span data-ttu-id="2d40f-245">Per disattivarlo, fai scorrere l'interruttore su **Disattiva** ![ ](../../media/scc-toggle-off.png) Disattiva.</span><span class="sxs-lookup"><span data-stu-id="2d40f-245">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     - <span data-ttu-id="2d40f-246">**Abilitare la protezione della rappresentazione basata sull'intelligence delle** cassette postali? : Questa impostazione è disponibile solo se **Abilita intelligence cassetta postale?** è **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-246">**Enable mailbox intelligence based impersonation protection?**: This setting is available only if **Enable mailbox intelligence?** is **On**.</span></span> <span data-ttu-id="2d40f-247">Attivare questa impostazione per specificare l'azione da eseguire sui messaggi per i rilevamenti di rappresentazione dai risultati dell'intelligence delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="2d40f-247">Turn on this setting to specify the action to take on messages for impersonation detections from mailbox intelligence results.</span></span>

       <span data-ttu-id="2d40f-248">In **Se la posta elettronica** viene inviata da un utente rappresentato, è possibile specificare una delle azioni seguenti (le stesse azioni disponibili per gli utenti protetti e i domini protetti):</span><span class="sxs-lookup"><span data-stu-id="2d40f-248">In **If email is sent by an impersonated user**, you can specify one of the following actions (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="2d40f-249">Non applicare alcuna azione: si noti che questo valore ha lo stesso risultato dell'attivazione di Abilita intelligence cassetta **postale?** ma disattivando Abilita protezione della rappresentazione basata **sull'intelligence** delle cassette **postali?**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-249">**Don't apply any action**: Note that this value has the same result as turning on **Enable mailbox intelligence?** but turning off **Enable mailbox intelligence based impersonation protection?**.</span></span>
       - <span data-ttu-id="2d40f-250">**Reindirizzare il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="2d40f-250">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="2d40f-251">**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="2d40f-251">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="2d40f-252">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="2d40f-252">**Quarantine the message**</span></span>
       - <span data-ttu-id="2d40f-253">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="2d40f-253">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="2d40f-254">**Eliminare il messaggio prima che venga recapitato**</span><span class="sxs-lookup"><span data-stu-id="2d40f-254">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="2d40f-255">**Aggiungere mittenti e domini attendibili**: specificare le eccezioni per il criterio:</span><span class="sxs-lookup"><span data-stu-id="2d40f-255">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="2d40f-256">**Mittenti attendibili**:</span><span class="sxs-lookup"><span data-stu-id="2d40f-256">**Trusted senders**:</span></span>

       - <span data-ttu-id="2d40f-257">Fare clic nella casella e scorrere l'elenco di utenti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="2d40f-257">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="2d40f-258">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="2d40f-258">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="2d40f-259">Per rimuovere una voce, fare clic **su Rimuovi** Icona ![ Rimuovi ](../../media/scc-remove-icon.png) nell'utente.</span><span class="sxs-lookup"><span data-stu-id="2d40f-259">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="2d40f-260">**Domini trusted:** immettere il nome di dominio (ad esempio, contoso.com), premere INVIO e ripetere l'operazione in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="2d40f-260">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="2d40f-261">**Rivedere le impostazioni:** invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-261">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="2d40f-262">È possibile fare **clic su** Modifica in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="2d40f-262">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="2d40f-263">È possibile attivare o **disattivare** le impostazioni seguenti **direttamente** in questa pagina:</span><span class="sxs-lookup"><span data-stu-id="2d40f-263">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="2d40f-264">**Utenti protetti**</span><span class="sxs-lookup"><span data-stu-id="2d40f-264">**Protected users**</span></span>
       - <span data-ttu-id="2d40f-265">**Domini protetti** \> **Includere i domini di cui sono proprietario**</span><span class="sxs-lookup"><span data-stu-id="2d40f-265">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="2d40f-266">**Domini protetti** \> **Domini protetti** (domini personalizzati)</span><span class="sxs-lookup"><span data-stu-id="2d40f-266">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="2d40f-267">**Intelligence della cassetta postale**</span><span class="sxs-lookup"><span data-stu-id="2d40f-267">**Mailbox intelligence**</span></span>

   <span data-ttu-id="2d40f-268">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="2d40f-268">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="2d40f-269">**Spoof**:  fare clic su Modifica per attivare o disattivare l'intelligence spoofing, attivare o disattivare l'identificazione del mittente non autenticato in Outlook e configurare l'azione da applicare ai messaggi provenienti da mittenti falsificati bloccati.</span><span class="sxs-lookup"><span data-stu-id="2d40f-269">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="2d40f-270">Per ulteriori informazioni su queste impostazioni, vedere [Spoofing settings in anti-phishing policies.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="2d40f-270">For more information about these settings, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="2d40f-271">Si noti che queste stesse impostazioni sono disponibili anche nei criteri anti-phishing in EOP.</span><span class="sxs-lookup"><span data-stu-id="2d40f-271">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="2d40f-272">**Impostazioni filtro spoofing**: utilizzare l'impostazione **Abilita spoof intelligence?** per attivare o disattivare l'intelligence spoofing.</span><span class="sxs-lookup"><span data-stu-id="2d40f-272">**Spoofing filter settings**: Use the **Enable spoof intelligence?** setting to turn spoof intelligence on or off.</span></span> <span data-ttu-id="2d40f-273">Il valore predefinito è **On** e si consiglia di lasciarlo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-273">The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="2d40f-274">Per disattivarlo, fai scorrere l'interruttore su **Disattiva** ![ ](../../media/scc-toggle-off.png) Disattiva.</span><span class="sxs-lookup"><span data-stu-id="2d40f-274">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

     > [!NOTE]
     > <span data-ttu-id="2d40f-275">Non è necessario disattivare la protezione anti-spoofing se il record MX non punta a Microsoft 365; si abilita invece il filtro avanzato per i connettori.</span><span class="sxs-lookup"><span data-stu-id="2d40f-275">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="2d40f-276">Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="2d40f-276">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="2d40f-277">**Impostazioni mittente non autenticato**: è possibile configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d40f-277">**Unauthenticated sender settings**: You can configure the following settings:</span></span>
     - <span data-ttu-id="2d40f-278">Abilitare il simbolo del punto interrogativo **(?)** del mittente non autenticato? : aggiungere un punto interrogativo alla foto del mittente  nella casella Da di Outlook se il messaggio non supera i controlli SPF o DKIM e il messaggio non supera L'autenticazione composita o DMARC. [](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="2d40f-278">**Enable unauthenticated sender question mark (?) symbol?**: Add a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span> <span data-ttu-id="2d40f-279">Il valore predefinito è **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-279">The default value is **On**.</span></span> <span data-ttu-id="2d40f-280">Per disattivarlo, fai scorrere l'interruttore su **Disattiva** ![ ](../../media/scc-toggle-off.png) Disattiva.</span><span class="sxs-lookup"><span data-stu-id="2d40f-280">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>
     - <span data-ttu-id="2d40f-281">**Abilitare il tag "via"?**: aggiungere il tag via (chris@contoso.com tramite fabrikam.com) se l'indirizzo di posta elettronica nella casella Da è diverso dal dominio nella firma DKIM o nell'indirizzo **MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-281">**Enable "via" tag?**: Add the via tag (chris@contoso.com via fabrikam.com) if the email address in the From box is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="2d40f-282">Il valore predefinito è **Attivato**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-282">The default value is **On**.</span></span> <span data-ttu-id="2d40f-283">Per disattivarlo, fai scorrere l'interruttore su **Disattiva** ![ ](../../media/scc-toggle-off.png) Disattiva.</span><span class="sxs-lookup"><span data-stu-id="2d40f-283">To turn it off, slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="2d40f-284">**Azioni**: specificare l'azione da eseguire sui messaggi provenienti da mittenti falsificati bloccati:</span><span class="sxs-lookup"><span data-stu-id="2d40f-284">**Actions**: Specify the action to take on messages from blocked spoofed senders:</span></span>

     <span data-ttu-id="2d40f-285">**Se la posta elettronica viene inviata da un utente a cui non è consentito effettuare lo spoofing del dominio:**</span><span class="sxs-lookup"><span data-stu-id="2d40f-285">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="2d40f-286">**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="2d40f-286">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="2d40f-287">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="2d40f-287">**Quarantine the message**</span></span>

   - <span data-ttu-id="2d40f-288">**Rivedere le impostazioni:** invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-288">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="2d40f-289">È possibile fare **clic su** Modifica in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="2d40f-289">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="2d40f-290">È possibile attivare o **disattivare** le impostazioni seguenti **direttamente** in questa pagina:</span><span class="sxs-lookup"><span data-stu-id="2d40f-290">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="2d40f-291">**Impostazioni di filtro spoofing**</span><span class="sxs-lookup"><span data-stu-id="2d40f-291">**Spoof filter settings**</span></span>
       - <span data-ttu-id="2d40f-292">**Impostazioni mittente non autenticato**</span><span class="sxs-lookup"><span data-stu-id="2d40f-292">**Unauthenticated sender settings**</span></span>
       - <span data-ttu-id="2d40f-293">**Azioni**</span><span class="sxs-lookup"><span data-stu-id="2d40f-293">**Actions**</span></span>

   <span data-ttu-id="2d40f-294">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="2d40f-294">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="2d40f-295">**Impostazioni avanzate**: fare clic **su Modifica** per configurare le soglie di phishing avanzate.</span><span class="sxs-lookup"><span data-stu-id="2d40f-295">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="2d40f-296">Per ulteriori informazioni, vedere [Soglie avanzate di phishing nei criteri anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="2d40f-296">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="2d40f-297">**Soglie di phishing avanzate**: selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d40f-297">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="2d40f-298">**1 - Standard** (questo è il valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="2d40f-298">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="2d40f-299">**2 - Aggressivo**</span><span class="sxs-lookup"><span data-stu-id="2d40f-299">**2 - Aggressive**</span></span>
   - <span data-ttu-id="2d40f-300">**3 - Più aggressivo**</span><span class="sxs-lookup"><span data-stu-id="2d40f-300">**3 - More aggressive**</span></span>
   - <span data-ttu-id="2d40f-301">**4 - Più aggressivo**</span><span class="sxs-lookup"><span data-stu-id="2d40f-301">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="2d40f-302">**Rivedere le impostazioni:** fare clic **su Modifica** per tornare alla **pagina Soglie di phishing** avanzate.</span><span class="sxs-lookup"><span data-stu-id="2d40f-302">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="2d40f-303">Al termine, fare clic su **Salva** in entrambe le pagine.</span><span class="sxs-lookup"><span data-stu-id="2d40f-303">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="2d40f-304">Tornare alla pagina **Modifica i \<Name\> criteri,** rivedere le impostazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-304">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2d40f-305">Utilizzare il Centro sicurezza & conformità per modificare il criterio anti-phishing predefinito in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2d40f-305">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2d40f-306">Il criterio anti-phishing predefinito in Microsoft Defender per Office 365 è denominato Office365 AntiPhish Default e non viene visualizzato nell'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="2d40f-306">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="2d40f-307">Per modificare il criterio anti-phishing predefinito, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="2d40f-307">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="2d40f-308">Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-308">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2d40f-309">Nella pagina **Anti-phishing** fare clic su **Criterio predefinito.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-309">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="2d40f-310">Viene visualizzata la pagina Modifica il criterio **Office365 AntiPhish Default.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-310">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="2d40f-311">Sono disponibili le sezioni seguenti, che contengono impostazioni identiche per quando si [modifica un criterio personalizzato:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="2d40f-311">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="2d40f-312">**Rappresentazione**</span><span class="sxs-lookup"><span data-stu-id="2d40f-312">**Impersonation**</span></span>
   - <span data-ttu-id="2d40f-313">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="2d40f-313">**Spoof**</span></span>
   - <span data-ttu-id="2d40f-314">**Impostazioni avanzate**</span><span class="sxs-lookup"><span data-stu-id="2d40f-314">**Advanced settings**</span></span>

   <span data-ttu-id="2d40f-315">Le impostazioni seguenti non sono disponibili quando si modifica il criterio predefinito:</span><span class="sxs-lookup"><span data-stu-id="2d40f-315">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="2d40f-316">È possibile  visualizzare la sezione Impostazioni criteri e  i valori, ma non è disponibile alcun collegamento Modifica, quindi non è possibile modificare le impostazioni (nome del criterio, descrizione e a chi si applica il criterio (si applica a tutti i destinatari)).</span><span class="sxs-lookup"><span data-stu-id="2d40f-316">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="2d40f-317">Non è possibile eliminare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="2d40f-317">You can't delete the default policy.</span></span>
   - <span data-ttu-id="2d40f-318">Non è possibile modificare la priorità del criterio predefinito (viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="2d40f-318">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="2d40f-319">Nella pagina **Modifica i criteri Office365 AntiPhish Default** rivedere le impostazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-319">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2d40f-320">Abilitare o disabilitare i criteri anti-phishing personalizzati in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2d40f-320">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="2d40f-321">Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-321">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2d40f-322">Notare il valore nella **colonna** Stato:</span><span class="sxs-lookup"><span data-stu-id="2d40f-322">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="2d40f-323">Fai scorrere l'interruttore **su Disattiva** Disattiva ![ per ](../../media/scc-toggle-off.png) disabilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="2d40f-323">Slide the toggle to **Off** ![Toggle Off](../../media/scc-toggle-off.png) to disable the policy.</span></span>

   - <span data-ttu-id="2d40f-324">Fai scorrere l'interruttore **su** ![ Attiva/Disattiva ](../../media/scc-toggle-on.png) per abilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="2d40f-324">Slide the toggle to **On** ![Toggle On](../../media/scc-toggle-on.png) to enable the policy.</span></span>

<span data-ttu-id="2d40f-325">Non è possibile disabilitare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="2d40f-325">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2d40f-326">Impostare la priorità dei criteri anti-phishing personalizzati in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2d40f-326">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2d40f-327">Per impostazione predefinita, ai criteri anti-phishing viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="2d40f-327">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="2d40f-328">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="2d40f-328">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="2d40f-329">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="2d40f-329">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="2d40f-330">Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="2d40f-330">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="2d40f-331">I criteri anti-phishing personalizzati vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="2d40f-331">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="2d40f-332">Il criterio anti-phishing predefinito denominato Office365 AntiPhish Default ha il valore di priorità personalizzato **Lowest** e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-332">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="2d40f-333">**Nota:** nel Centro sicurezza & conformità, è possibile modificare la priorità del criterio anti-phishing solo dopo aver creato il criterio.</span><span class="sxs-lookup"><span data-stu-id="2d40f-333">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="2d40f-334">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phish (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="2d40f-334">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="2d40f-335">Per modificare la priorità di  un criterio, fare clic su Aumenta priorità o Riduci  priorità nelle proprietà del criterio (non è possibile modificare direttamente il numero di priorità nel Centro sicurezza & conformità). </span><span class="sxs-lookup"><span data-stu-id="2d40f-335">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="2d40f-336">La modifica della priorità di un criterio ha senso solo se si dispone di più criteri.</span><span class="sxs-lookup"><span data-stu-id="2d40f-336">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="2d40f-337">Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-337">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2d40f-338">Selezionare il criterio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="2d40f-338">Select the policy that you want to modify.</span></span> <span data-ttu-id="2d40f-339">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-339">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="2d40f-340">Viene **visualizzato \<name\> il riquadro a comparsa** Modifica il criterio.</span><span class="sxs-lookup"><span data-stu-id="2d40f-340">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="2d40f-341">Il criterio anti-phishing personalizzato con **il valore Priority** **0** ha solo il **pulsante Riduci** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="2d40f-341">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="2d40f-342">Il criterio anti-phishing personalizzato con il valore **priority** più basso (ad esempio, **3**) ha solo il **pulsante Aumenta** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="2d40f-342">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="2d40f-343">Se si dispone di tre o più criteri anti-phishing personalizzati,  i criteri  tra i valori di priorità più alta e più bassa hanno entrambi i pulsanti Aumenta priorità e Riduci priorità disponibili.</span><span class="sxs-lookup"><span data-stu-id="2d40f-343">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="2d40f-344">Fare **clic su Aumenta priorità** o **Diminuisci priorità** per modificare il valore **Priorità.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-344">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="2d40f-345">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-345">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2d40f-346">Usare il Centro sicurezza & conformità per visualizzare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2d40f-346">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="2d40f-347">Nel Centro sicurezza & conformità e passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-347">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2d40f-348">Esegui uno dei seguenti passaggi:</span><span class="sxs-lookup"><span data-stu-id="2d40f-348">Do one of the following steps:</span></span>

   - <span data-ttu-id="2d40f-349">Selezionare un criterio anti-phishing personalizzato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="2d40f-349">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="2d40f-350">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-350">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="2d40f-351">Fare **clic su Criterio** predefinito per visualizzare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="2d40f-351">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="2d40f-352">Viene **visualizzato \<name\> il riquadro a** comparsa Modifica il criterio, in cui è possibile visualizzare le impostazioni e i valori.</span><span class="sxs-lookup"><span data-stu-id="2d40f-352">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2d40f-353">Usare il Centro sicurezza & conformità per rimuovere i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2d40f-353">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="2d40f-354">Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="2d40f-355">Selezionare il criterio che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="2d40f-355">Select the policy that you want to remove.</span></span> <span data-ttu-id="2d40f-356">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-356">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="2d40f-357">Nel riquadro **a \<name\> comparsa Modifica criterio** visualizzato fare clic **su** Elimina criterio e quindi su **Sì** nella finestra di dialogo di avviso visualizzata.</span><span class="sxs-lookup"><span data-stu-id="2d40f-357">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="2d40f-358">Non è possibile rimuovere il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="2d40f-358">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2d40f-359">Usare Exchange Online PowerShell per configurare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="2d40f-359">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2d40f-360">Come descritto in precedenza, un criterio di protezione da posta indesiderata è costituito da un criterio anti-phish e da una regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="2d40f-360">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="2d40f-361">In Exchange Online PowerShell, è evidente la differenza tra i criteri anti-phish e le regole anti-phish.</span><span class="sxs-lookup"><span data-stu-id="2d40f-361">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="2d40f-362">È possibile gestire i criteri anti-phish utilizzando i cmdlet **\* -AntiPhishPolicy** e gestire le regole anti-phish utilizzando i cmdlet **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-362">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="2d40f-363">In PowerShell, si crea prima il criterio anti-phish, quindi si crea la regola anti-phish che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="2d40f-363">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="2d40f-364">In PowerShell, le impostazioni dei criteri anti-phish e della regola anti-phish vengono modificate separatamente.</span><span class="sxs-lookup"><span data-stu-id="2d40f-364">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="2d40f-365">Quando si rimuove un criterio anti-phish da PowerShell, la regola anti-phish corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="2d40f-365">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="2d40f-366">Utilizzare PowerShell per creare criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="2d40f-366">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="2d40f-367">La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="2d40f-367">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="2d40f-368">Creare i criteri anti-phish.</span><span class="sxs-lookup"><span data-stu-id="2d40f-368">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="2d40f-369">Creare la regola anti-phish che specifica il criterio anti-phish a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="2d40f-369">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="2d40f-370">**Note**:</span><span class="sxs-lookup"><span data-stu-id="2d40f-370">**Notes**:</span></span>

- <span data-ttu-id="2d40f-371">È possibile creare una nuova regola anti-phish e assegnarle un criterio anti-phish esistente e non associazione.</span><span class="sxs-lookup"><span data-stu-id="2d40f-371">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="2d40f-372">Una regola anti-phish non può essere associata a più di un criterio anti-phish.</span><span class="sxs-lookup"><span data-stu-id="2d40f-372">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="2d40f-373">È possibile configurare le impostazioni seguenti nei nuovi criteri anti-phish in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:</span><span class="sxs-lookup"><span data-stu-id="2d40f-373">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="2d40f-374">Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="2d40f-374">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="2d40f-375">Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-375">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="2d40f-376">Un nuovo criterio anti-phish creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="2d40f-376">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="2d40f-377">Passaggio 1: Usare PowerShell per creare un criterio anti-phish</span><span class="sxs-lookup"><span data-stu-id="2d40f-377">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="2d40f-378">Per creare un criterio anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2d40f-378">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="2d40f-379">In questo esempio viene creato un criterio anti-phish denominato Research Quarantine con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d40f-379">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="2d40f-380">Il criterio è abilitato (non viene utilizzato il _parametro Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="2d40f-380">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="2d40f-381">La descrizione è: Criteri del reparto di ricerca.</span><span class="sxs-lookup"><span data-stu-id="2d40f-381">The description is: Research department policy.</span></span>
- <span data-ttu-id="2d40f-382">Abilita la protezione dei domini dell'organizzazione per tutti i domini accettati e la protezione dei domini di destinazione per fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="2d40f-382">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="2d40f-383">Specifica Mai Fujito (mfujito@fabrikam.com) come l'utente da proteggere da imitazione.</span><span class="sxs-lookup"><span data-stu-id="2d40f-383">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="2d40f-384">Abilita l'intelligence della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="2d40f-384">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="2d40f-385">Abilita la protezione dell'intelligence delle cassette postali e specifica l'azione di quarantena.</span><span class="sxs-lookup"><span data-stu-id="2d40f-385">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="2d40f-386">Abilita i suggerimenti per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="2d40f-386">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="2d40f-387">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="2d40f-387">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="2d40f-388">Passaggio 2: Usare PowerShell per creare una regola anti-phish</span><span class="sxs-lookup"><span data-stu-id="2d40f-388">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="2d40f-389">Per creare una regola anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2d40f-389">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="2d40f-390">In questo esempio viene creata una regola anti-phish denominata Research Department con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d40f-390">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="2d40f-391">La regola è associata al criterio anti-phish denominato Quarantena ricerche.</span><span class="sxs-lookup"><span data-stu-id="2d40f-391">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="2d40f-392">La regola viene applicata ai membri del gruppo denominato Research Department.</span><span class="sxs-lookup"><span data-stu-id="2d40f-392">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="2d40f-393">Poiché non si utilizza il parametro _Priority,_ viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="2d40f-393">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="2d40f-394">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="2d40f-394">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="2d40f-395">Usare PowerShell per visualizzare i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="2d40f-395">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="2d40f-396">Per visualizzare i criteri anti-phish esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2d40f-396">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="2d40f-397">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri anti-phish insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="2d40f-397">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="2d40f-398">In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio anti-phish denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="2d40f-398">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="2d40f-399">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="2d40f-399">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="2d40f-400">Usare PowerShell per visualizzare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="2d40f-400">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="2d40f-401">Per visualizzare le regole anti-phish esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2d40f-401">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="2d40f-402">In questo esempio viene restituito un elenco riepilogativo di tutte le regole anti-phish insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="2d40f-402">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="2d40f-403">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d40f-403">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="2d40f-404">In questo esempio vengono restituiti tutti i valori delle proprietà per la regola anti-phish denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="2d40f-404">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="2d40f-405">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="2d40f-405">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="2d40f-406">Utilizzare PowerShell per modificare i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="2d40f-406">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="2d40f-407">Oltre agli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio anti-phish in PowerShell come quando si crea il criterio come descritto nella sezione Passaggio 1: utilizzare PowerShell per creare un criterio [anti-phish](#step-1-use-powershell-to-create-an-anti-phish-policy) in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-407">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="2d40f-408">L'opzione _MakeDefault_ che trasforma il criterio specificato nel  criterio predefinito (applicato a tutti, sempre con priorità minima e non è possibile eliminarlo) è disponibile solo quando si modifica un criterio anti-phish in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d40f-408">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="2d40f-409">Non è possibile rinominare un criterio anti-phish (il cmdlet **Set-AntiPhishPolicy** non dispone di _alcun parametro Name)._</span><span class="sxs-lookup"><span data-stu-id="2d40f-409">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="2d40f-410">Quando si rinomina un criterio anti-phishing nel Centro sicurezza & conformità, si rinomina solo la regola _anti-phishing._</span><span class="sxs-lookup"><span data-stu-id="2d40f-410">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="2d40f-411">Per modificare un criterio anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2d40f-411">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="2d40f-412">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="2d40f-412">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="2d40f-413">Utilizzare PowerShell per modificare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="2d40f-413">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="2d40f-414">L'unica impostazione non disponibile quando si modifica una regola anti-phish in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="2d40f-414">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="2d40f-415">Per abilitare o disabilitare le regole anti-phish esistenti, vedi la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="2d40f-415">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="2d40f-416">In caso contrario, non sono disponibili impostazioni aggiuntive quando si modifica una regola anti-phish in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d40f-416">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="2d40f-417">Le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione Passaggio 2: Utilizzare PowerShell per creare una regola [anti-phish](#step-2-use-powershell-to-create-an-anti-phish-rule) in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="2d40f-417">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="2d40f-418">Per modificare una regola anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2d40f-418">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="2d40f-419">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="2d40f-419">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="2d40f-420">Usare PowerShell per abilitare o disabilitare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="2d40f-420">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="2d40f-421">L'abilitazione o la disabilitazione di una regola anti-phishing in PowerShell abilita o disabilita l'intero criterio anti-phishing (la regola anti-phishing e il criterio anti-phishing assegnato).</span><span class="sxs-lookup"><span data-stu-id="2d40f-421">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="2d40f-422">Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="2d40f-422">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="2d40f-423">Per abilitare o disabilitare una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2d40f-423">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="2d40f-424">In questo esempio viene disabilitata la regola anti-phish denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="2d40f-424">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="2d40f-425">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="2d40f-425">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="2d40f-426">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="2d40f-426">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="2d40f-427">Usare PowerShell per impostare la priorità delle regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="2d40f-427">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="2d40f-428">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="2d40f-428">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="2d40f-429">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="2d40f-429">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="2d40f-430">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="2d40f-430">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="2d40f-431">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="2d40f-431">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="2d40f-432">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="2d40f-432">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="2d40f-433">Per impostare la priorità di una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2d40f-433">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="2d40f-p148">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="2d40f-p148">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="2d40f-436">**Note**:</span><span class="sxs-lookup"><span data-stu-id="2d40f-436">**Notes**:</span></span>

- <span data-ttu-id="2d40f-437">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare invece il parametro _Priority_ nel cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-437">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="2d40f-438">Il criterio anti-phish predefinito non dispone di una regola anti-phish corrispondente e ha sempre il valore di priorità non modificabile **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="2d40f-438">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="2d40f-439">Usare PowerShell per rimuovere i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="2d40f-439">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="2d40f-440">Quando si utilizza PowerShell per rimuovere un criterio anti-phish, la regola anti-phish corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="2d40f-440">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="2d40f-441">Per rimuovere un criterio anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2d40f-441">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="2d40f-442">In questo esempio viene rimosso il criterio anti-phish denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="2d40f-442">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="2d40f-443">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="2d40f-443">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="2d40f-444">Usare PowerShell per rimuovere le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="2d40f-444">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="2d40f-445">Quando si utilizza PowerShell per rimuovere una regola anti-phish, il criterio anti-phish corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="2d40f-445">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="2d40f-446">Per rimuovere una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="2d40f-446">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="2d40f-447">In questo esempio viene rimossa la regola anti-phish denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="2d40f-447">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="2d40f-448">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="2d40f-448">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="2d40f-449">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="2d40f-449">How do you know these procedures worked?</span></span>

<span data-ttu-id="2d40f-450">Per verificare di aver configurato correttamente i criteri anti-phishing in Microsoft Defender per Office 365, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d40f-450">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="2d40f-451">Nel Centro sicurezza & conformità passare a **Gestione** delle minacce \> **Criteri** \> **Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-451">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span> <span data-ttu-id="2d40f-452">Verificare l'elenco dei criteri, i **relativi valori status** e i relativi valori **Priority.**</span><span class="sxs-lookup"><span data-stu-id="2d40f-452">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="2d40f-453">Per visualizzare ulteriori dettagli, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d40f-453">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="2d40f-454">Selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="2d40f-454">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="2d40f-455">Fare **clic su** Criterio predefinito e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="2d40f-455">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="2d40f-456">In Exchange Online PowerShell, sostituire con il nome del criterio o della regola ed eseguire il \<Name\> comando seguente e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="2d40f-456">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```