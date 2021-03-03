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
ms.openlocfilehash: d75455df972e9db0ef1cf4bbeba9f3b78b11002b
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406199"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0269a-103">Configurare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="0269a-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0269a-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="0269a-104">**Applies to**</span></span>
- [<span data-ttu-id="0269a-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="0269a-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="0269a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0269a-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="0269a-107">I criteri anti-phishing in [Microsoft Defender per Office 365](office-365-atp.md) consentono di proteggere l'organizzazione da attacchi di phishing dannosi basati sulla rappresentazione e altri tipi di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="0269a-107">Anti-phishing policies in [Microsoft Defender for Office 365](office-365-atp.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="0269a-108">Per ulteriori informazioni sulle differenze tra i criteri anti-phishing in Exchange Online Protection (EOP) e i criteri anti-phishing in Microsoft Defender per Office 365, vedere [Protezione anti-phishing.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="0269a-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="0269a-109">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="0269a-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="0269a-110">Per una maggiore granularità, è inoltre possibile creare criteri anti-phishing personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0269a-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="0269a-111">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).</span><span class="sxs-lookup"><span data-stu-id="0269a-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="0269a-112">È possibile configurare i criteri anti-phishing nel Centro sicurezza & conformità o in PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0269a-112">You can configure anti-phishing policies in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="0269a-113">Per informazioni sulla configurazione dei criteri di anti-phishing più limitati disponibili nelle organizzazioni di Exchange Online Protection (ovvero le organizzazioni senza Microsoft Defender per Office 365), vedere Configurare i criteri [anti-phishing in EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="0269a-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection organizations (that is, organizations without Microsoft Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="0269a-114">Gli elementi di base di un criterio anti-phishing sono:</span><span class="sxs-lookup"><span data-stu-id="0269a-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="0269a-115">**Il criterio anti-phishing**: specifica le protezioni anti-phishing da abilitare o disabilitare e le azioni da applicare.</span><span class="sxs-lookup"><span data-stu-id="0269a-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="0269a-116">**La regola anti-phish**: specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phish.</span><span class="sxs-lookup"><span data-stu-id="0269a-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="0269a-117">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri anti-phishing nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="0269a-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Security & Compliance Center:</span></span>

- <span data-ttu-id="0269a-118">Quando crei un criterio, stai creando contemporaneamente una regola anti-phish e il criterio anti-phish associato usando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="0269a-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="0269a-119">Quando si modifica un criterio, le impostazioni relative al nome, alla priorità, all'attivazione o alla disabilitazione e i filtri destinatari modificano la regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="0269a-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="0269a-120">Tutte le altre impostazioni modificano il criterio anti-phish associato.</span><span class="sxs-lookup"><span data-stu-id="0269a-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="0269a-121">Quando si rimuove un criterio, vengono rimossi la regola anti-phish e il criterio anti-phish associato.</span><span class="sxs-lookup"><span data-stu-id="0269a-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="0269a-122">In PowerShell di Exchange Online, il criterio e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="0269a-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="0269a-123">Per ulteriori informazioni, vedere la sezione Utilizzare PowerShell di Exchange Online per configurare i criteri [anti-phishing in Microsoft Defender per Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0269a-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) section later in this article.</span></span>

<span data-ttu-id="0269a-124">Ogni organizzazione di Microsoft Defender per Office 365 dispone di un criterio anti-phishing predefinito denominato Office365 AntiPhish Default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="0269a-124">Every Microsoft Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="0269a-125">Il criterio viene applicato a tutti i destinatari nell'organizzazione, anche se al criterio non è associata alcuna regola anti-phish (filtri destinatari).</span><span class="sxs-lookup"><span data-stu-id="0269a-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="0269a-126">Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="0269a-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="0269a-127">Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="0269a-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="0269a-128">Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="0269a-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="0269a-129">Per aumentare l'efficacia della protezione anti-phishing in Microsoft Defender per Office 365, è possibile creare criteri anti-phishing personalizzati con impostazioni più rigide applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="0269a-129">To increase the effectiveness of anti-phishing protection in Microsoft Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0269a-130">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="0269a-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0269a-131">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0269a-131">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0269a-132">Per passare direttamente alla pagina **anti-phishing di ATP,** utilizzare <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="0269a-132">To go directly to the **ATP anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="0269a-133">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0269a-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="0269a-134">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in **Exchange Online:**</span><span class="sxs-lookup"><span data-stu-id="0269a-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="0269a-135">Per aggiungere, modificare ed eliminare criteri anti-phishing, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="0269a-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="0269a-136">Per l'accesso in sola lettura ai criteri anti-phishing, è  necessario essere membri dei gruppi di ruoli **Lettore** globale o Lettore di <sup>\*</sup> sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0269a-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="0269a-137">Per ulteriori informazioni, vedere [Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="0269a-137">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="0269a-138">**Note**:</span><span class="sxs-lookup"><span data-stu-id="0269a-138">**Notes**:</span></span>

  - <span data-ttu-id="0269a-139">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 offre agli utenti le autorizzazioni e le autorizzazioni necessarie per altre funzionalità di Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="0269a-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0269a-140">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0269a-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="0269a-141">Il **gruppo di ruoli Gestione organizzazione** di sola visualizzazione in Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) consente inoltre l'accesso in sola lettura alla <sup>\*</sup> funzionalità.</span><span class="sxs-lookup"><span data-stu-id="0269a-141">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>
  - <span data-ttu-id="0269a-142"><sup>\*</sup> Nel Centro sicurezza & conformità, l'accesso in sola lettura consente agli utenti di visualizzare le impostazioni dei criteri anti-phishing personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0269a-142"><sup>\*</sup> In the Security & Compliance Center, read-only access allows users to view the settings of custom anti-phishing policies.</span></span> <span data-ttu-id="0269a-143">Gli utenti di sola lettura non possono visualizzare le impostazioni nel criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="0269a-143">Read-only users can't see the settings in the default anti-phishing policy.</span></span>

- <span data-ttu-id="0269a-144">Per le impostazioni consigliate per i criteri anti-phishing in Microsoft Defender per Office 365, vedere Criteri anti-phishing in Defender per le impostazioni [di Office 365.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="0269a-144">For our recommended settings for anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="0269a-145">Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.</span><span class="sxs-lookup"><span data-stu-id="0269a-145">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="0269a-146">Per informazioni su dove vengono applicati i criteri anti-phishing nella pipeline di filtro, vedere [Ordine e precedenza della protezione della posta elettronica.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="0269a-146">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0269a-147">Usare il Centro sicurezza & conformità per creare criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="0269a-147">Use the Security & Compliance Center to create anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0269a-148">La creazione di un criterio anti-phishing personalizzato nel Centro sicurezza & conformità crea contemporaneamente la regola anti-phishing e il criterio anti-phishing associato usando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="0269a-148">Creating a custom anti-phishing policy in the Security & Compliance Center creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

<span data-ttu-id="0269a-149">Quando si crea un criterio anti-phishing, è possibile specificare solo il nome, la descrizione e il filtro destinatario che identifica a chi si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="0269a-149">When you create an anti-phishing policy, you can only specify the policy name, description, and the recipient filter that identifies who the policy applies to.</span></span> <span data-ttu-id="0269a-150">Dopo aver creato il criterio, è possibile modificare il criterio per modificare o rivedere le impostazioni di anti-phishing predefinite.</span><span class="sxs-lookup"><span data-stu-id="0269a-150">After you create the policy, you can modify the policy to change or review the default anti-phishing settings.</span></span>

1. <span data-ttu-id="0269a-151">Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="0269a-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0269a-152">Nella pagina **Anti-phishing** fare clic su **Crea.**</span><span class="sxs-lookup"><span data-stu-id="0269a-152">On the **Anti-phishing** page, click **Create**.</span></span>

3. <span data-ttu-id="0269a-153">Verrà visualizzata la procedura guidata Crea un nuovo **criterio anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="0269a-153">The **Create a new anti-phishing policy** wizard opens.</span></span> <span data-ttu-id="0269a-154">Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0269a-154">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="0269a-155">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="0269a-155">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="0269a-156">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="0269a-156">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="0269a-157">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0269a-157">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0269a-158">Nella pagina **Applicato a** visualizzata, identificare i destinatari interni a cui si applica il criterio.</span><span class="sxs-lookup"><span data-stu-id="0269a-158">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="0269a-159">È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="0269a-159">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="0269a-160">Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="0269a-160">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="0269a-161">Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="0269a-161">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="0269a-162">Fare **clic su Aggiungi condizione.**</span><span class="sxs-lookup"><span data-stu-id="0269a-162">Click **Add a condition**.</span></span> <span data-ttu-id="0269a-163">Nell'elenco a discesa visualizzato selezionare una condizione in **Applicato se:**</span><span class="sxs-lookup"><span data-stu-id="0269a-163">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="0269a-164">**Il destinatario è**: specifica una o più cassette postali, utenti di posta o contatti di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0269a-164">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="0269a-165">**Il destinatario è membro di**: Specifica uno o più gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0269a-165">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="0269a-166">**Il dominio del destinatario** è : specifica i destinatari in uno o più domini accettati configurati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0269a-166">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in the organization.</span></span>

   <span data-ttu-id="0269a-167">Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con **una qualsiasi di queste** caselle.</span><span class="sxs-lookup"><span data-stu-id="0269a-167">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="0269a-168">Fare clic nella casella e scorrere l'elenco dei valori da selezionare.</span><span class="sxs-lookup"><span data-stu-id="0269a-168">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="0269a-169">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="0269a-169">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="0269a-170">Per aggiungere ulteriori valori, fare clic in un'area vuota della casella.</span><span class="sxs-lookup"><span data-stu-id="0269a-170">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="0269a-171">Per rimuovere singole voci, fare **clic sull'icona** ![ Rimuovi sul ](../../media/scc-remove-icon.png) valore.</span><span class="sxs-lookup"><span data-stu-id="0269a-171">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="0269a-172">Per rimuovere l'intera condizione, fare **clic sull'icona** ![ Rimuovi nella ](../../media/scc-remove-icon.png) condizione.</span><span class="sxs-lookup"><span data-stu-id="0269a-172">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="0269a-173">Per aggiungere una condizione aggiuntiva, fare clic **su Aggiungi una condizione** e selezionare un valore rimanente in Applicato **se.**</span><span class="sxs-lookup"><span data-stu-id="0269a-173">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="0269a-174">Per aggiungere eccezioni, fare clic **su Aggiungi una condizione** e selezionare un'eccezione in Tranne **se**.</span><span class="sxs-lookup"><span data-stu-id="0269a-174">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="0269a-175">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="0269a-175">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="0269a-176">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0269a-176">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0269a-177">Nella pagina **Controlla le impostazioni** visualizzata, rivedere le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="0269a-177">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="0269a-178">È possibile fare **clic su** Modifica per ogni impostazione per modificarla.</span><span class="sxs-lookup"><span data-stu-id="0269a-178">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="0269a-179">Al termine, fare clic **su Crea questo criterio.**</span><span class="sxs-lookup"><span data-stu-id="0269a-179">When you're finished, click **Create this policy**.</span></span>

6. <span data-ttu-id="0269a-180">Fare **clic su OK** nella finestra di dialogo di conferma visualizzata.</span><span class="sxs-lookup"><span data-stu-id="0269a-180">Click **OK** in the confirmation dialog that appears.</span></span>

<span data-ttu-id="0269a-181">Dopo aver creato il criterio anti-phishing con queste impostazioni generali, seguire le istruzioni nella sezione successiva per configurare le impostazioni di protezione nel criterio.</span><span class="sxs-lookup"><span data-stu-id="0269a-181">After you create the anti-phishing policy with these general settings, use the instructions in the next section to configure the protection settings in the policy.</span></span>

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0269a-182">Usare il Centro sicurezza & conformità per modificare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="0269a-182">Use the Security & Compliance Center to modify anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0269a-183">Utilizzare le procedure seguenti per modificare i criteri anti-phishing: un nuovo criterio creato dall'utente o criteri esistenti già personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0269a-183">Use the following procedures to modify anti-phishing policies: a new policy that you created, or existing policies that you've already customized.</span></span>

1. <span data-ttu-id="0269a-184">Se non si è già presenti, aprire il Centro sicurezza  & conformità e passare a Criteri di gestione delle minacce \>  \> **anti-phishing ATP.**</span><span class="sxs-lookup"><span data-stu-id="0269a-184">If you're not already there, open the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0269a-185">Selezionare il criterio anti-phishing personalizzato che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="0269a-185">Select the custom anti-phishing policy that you want to modify.</span></span> <span data-ttu-id="0269a-186">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="0269a-186">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0269a-187">Verrà **visualizzato \<name\> il riquadro a comparsa** Modifica criterio.</span><span class="sxs-lookup"><span data-stu-id="0269a-187">The **Edit your policy \<name\>** flyout appears.</span></span> <span data-ttu-id="0269a-188">Facendo **clic su** Modifica in qualsiasi sezione è possibile accedere alle impostazioni di tale sezione.</span><span class="sxs-lookup"><span data-stu-id="0269a-188">Clicking **Edit** in any section gives you access to the settings in that section.</span></span>

   - <span data-ttu-id="0269a-189">I passaggi seguenti vengono presentati nell'ordine in cui vengono visualizzate le sezioni, ma non sono sequenziali (è possibile selezionare e modificare le sezioni in qualsiasi ordine).</span><span class="sxs-lookup"><span data-stu-id="0269a-189">The following steps are presented in the order that the sections appear, but they aren't sequential (you can select and modify the sections in any order).</span></span>

   - <span data-ttu-id="0269a-190">Dopo aver fatto clic su Modifica **in** una sezione, le impostazioni disponibili vengono presentate in un  formato di procedura guidata,  ma è possibile passare all'interno delle pagine in qualsiasi ordine e fare clic su Salva in qualsiasi pagina (o  ![ ](../../media/scc-remove-icon.png) **\<name\>** sull'icona Annulla o Chiudi chiudi per tornare alla pagina Modifica i criteri (non è necessario visitare l'ultima pagina della procedura guidata per salvare o uscire).</span><span class="sxs-lookup"><span data-stu-id="0269a-190">After you click **Edit** in a section, the available settings are presented in a wizard format, but you can jump within the pages in any order, and you can click **Save** on any page (or **Cancel** or **Close** ![Close icon](../../media/scc-remove-icon.png) to return to the **Edit your policy \<name\>** page (you aren't required to visit the last page of the wizard to save or leave).</span></span>

4. <span data-ttu-id="0269a-191">**Impostazione dei criteri:** **fare** clic su Modifica per modificare le stesse impostazioni disponibili quando [è](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) stato creato il criterio nella sezione precedente:</span><span class="sxs-lookup"><span data-stu-id="0269a-191">**Policy setting**: Click **Edit** to modify the same settings that were available when you [created the policy](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) in the previous section:</span></span>

   - <span data-ttu-id="0269a-192">**Nome**</span><span class="sxs-lookup"><span data-stu-id="0269a-192">**Name**</span></span>
   - <span data-ttu-id="0269a-193">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0269a-193">**Description**</span></span>
   - <span data-ttu-id="0269a-194">**Applicato a**</span><span class="sxs-lookup"><span data-stu-id="0269a-194">**Applied to**</span></span>
   - <span data-ttu-id="0269a-195">**Rivedere le impostazioni**</span><span class="sxs-lookup"><span data-stu-id="0269a-195">**Review your settings**</span></span>

   <span data-ttu-id="0269a-196">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="0269a-196">When you're finished, click **Save** on any page.</span></span>

5. <span data-ttu-id="0269a-197">**Rappresentazione:** fare **clic su Modifica** per modificare i mittenti protetti e i domini protetti nel criterio.</span><span class="sxs-lookup"><span data-stu-id="0269a-197">**Impersonation**: Click **Edit** to modify the protected senders and protected domains in the policy.</span></span> <span data-ttu-id="0269a-198">Queste impostazioni sono una condizione per il criterio che identifica i mittenti falsificati da cercare (singolarmente o per dominio) nell'indirizzo del mittente dei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="0269a-198">These settings are a condition for the policy that identifies spoofed senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="0269a-199">Per ulteriori informazioni, vedere [Impostazioni di rappresentazione nei criteri anti-phishing in Microsoft Defender per Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="0269a-199">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="0269a-200">**Aggiungere utenti da proteggere:** il valore predefinito è **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-200">**Add users to protect**: The default value is **Off**.</span></span> <span data-ttu-id="0269a-201">Per attivarlo, far scorrere l'interruttore su **Attivato** e quindi fare **clic** sul pulsante Aggiungi utente visualizzato.</span><span class="sxs-lookup"><span data-stu-id="0269a-201">To turn it on, slide the toggle to **On**, and then click the **Add user** button that appears.</span></span>

     <span data-ttu-id="0269a-202">Nel riquadro **a comparsa** Aggiungi utente visualizzato configurare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="0269a-202">In the **Add user** flyout that appears, configure the following values:</span></span>

     - <span data-ttu-id="0269a-203">**Indirizzo di posta elettronica**:</span><span class="sxs-lookup"><span data-stu-id="0269a-203">**Email address**:</span></span>

       - <span data-ttu-id="0269a-204">Fare clic nella casella e scorrere l'elenco degli utenti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="0269a-204">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="0269a-205">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="0269a-205">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="0269a-206">Per rimuovere una voce, fare **clic sull'icona** ![ Rimuovi ](../../media/scc-remove-icon.png) nell'utente.</span><span class="sxs-lookup"><span data-stu-id="0269a-206">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="0269a-207">**Nome:** questo valore viene popolato in base all'indirizzo di posta elettronica selezionato, ma è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="0269a-207">**Name**: This value is populated based on the email address you selected, but you can change it.</span></span>

     <span data-ttu-id="0269a-208">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="0269a-208">When you're finished, click **Save** on any page.</span></span>

     <span data-ttu-id="0269a-209">Per modificare una voce esistente, selezionare l'utente protetto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0269a-209">To edit an existing entry, select the protected user in the list.</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="0269a-210">In ogni criterio anti-phishing è possibile specificare un massimo di 60 utenti protetti (indirizzi di posta elettronica del mittente).</span><span class="sxs-lookup"><span data-stu-id="0269a-210">In each anti-phishing policy, you can specify a maximum of 60 protected users (sender email addresses).</span></span> <span data-ttu-id="0269a-211">Non è possibile specificare lo stesso utente protetto in più criteri.</span><span class="sxs-lookup"><span data-stu-id="0269a-211">You can't specify the same protected user in multiple policies.</span></span>
     >
     > - <span data-ttu-id="0269a-212">La protezione della rappresentazione dell'utente non funziona se il mittente e il destinatario hanno già comunicato tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0269a-212">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="0269a-213">Se il mittente e il destinatario non hanno mai comunicato tramite posta elettronica, il messaggio verrà identificato come tentativo di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="0269a-213">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

   - <span data-ttu-id="0269a-214">**Aggiungere domini da proteggere:** configurare una o entrambe le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0269a-214">**Add domains to protect**: Configure one or both of the following settings:</span></span>

     - <span data-ttu-id="0269a-215">**Includi automaticamente i domini di cui sono proprietario:** il valore predefinito è **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-215">**Automatically include the domains I own**: The default value is **Off**.</span></span> <span data-ttu-id="0269a-216">Per attivarlo, far scorrere l'interruttore su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-216">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0269a-217">**Includi domini personalizzati**: il valore predefinito è **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-217">**Include custom domains**: The default value is **Off**.</span></span> <span data-ttu-id="0269a-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press INVIO, and repeat as necessary.</span><span class="sxs-lookup"><span data-stu-id="0269a-218">To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

     > [!NOTE]
     > <span data-ttu-id="0269a-219">È possibile disporre di un massimo di 50 domini in tutti i criteri anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="0269a-219">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

   - <span data-ttu-id="0269a-220">**Azioni**: fare clic su **Modifica**</span><span class="sxs-lookup"><span data-stu-id="0269a-220">**Actions**: Click **Edit**</span></span>

     - <span data-ttu-id="0269a-221">**Se la posta elettronica** viene inviata da un utente rappresentato: configurare una delle azioni seguenti per i messaggi in cui il mittente falsificato è uno degli utenti protetti specificati in Aggiungi utenti **da proteggere:**</span><span class="sxs-lookup"><span data-stu-id="0269a-221">**If email is sent by an impersonated user**: Configure one of the following actions for messages where the spoofed sender is one of the protected users you specified in **Add users to protect**:</span></span>

       - <span data-ttu-id="0269a-222">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="0269a-222">**Don't apply any action**</span></span>
       - <span data-ttu-id="0269a-223">**Reindirizzare il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="0269a-223">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0269a-224">**Sposta messaggio nella cartella Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="0269a-224">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0269a-225">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="0269a-225">**Quarantine the message**</span></span>
       - <span data-ttu-id="0269a-226">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="0269a-226">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0269a-227">**Eliminare il messaggio prima che venga recapitato**</span><span class="sxs-lookup"><span data-stu-id="0269a-227">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="0269a-228">**Se la posta elettronica** viene inviata da un dominio rappresentato: configurare una delle azioni seguenti per i messaggi in cui il mittente falsificato si trova in uno dei domini protetti specificati in Aggiungi domini **da proteggere:**</span><span class="sxs-lookup"><span data-stu-id="0269a-228">**If email is sent by an impersonated domain**: Configure one of the following actions for messages where the spoofed sender is in one of the protected domains you specified in **Add domains to protect**:</span></span>

       - <span data-ttu-id="0269a-229">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="0269a-229">**Don't apply any action**</span></span>
       - <span data-ttu-id="0269a-230">**Reindirizzare il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="0269a-230">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0269a-231">**Sposta messaggio nella cartella Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="0269a-231">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0269a-232">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="0269a-232">**Quarantine the message**</span></span>
       - <span data-ttu-id="0269a-233">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="0269a-233">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0269a-234">**Eliminare il messaggio prima che venga recapitato**</span><span class="sxs-lookup"><span data-stu-id="0269a-234">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="0269a-235">Fare **clic su Attiva suggerimenti per la sicurezza della** rappresentazione e configurare una delle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0269a-235">Click **turn on impersonation safety tips** and configure any of the following settings:</span></span>

     - <span data-ttu-id="0269a-236">**Mostra suggerimento per gli utenti rappresentati:** il valore predefinito è **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-236">**Show tip for impersonated users**: The default value is **Off**.</span></span> <span data-ttu-id="0269a-237">Per attivarlo, far scorrere l'interruttore su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-237">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0269a-238">**Mostra suggerimento per i domini rappresentati:** il valore predefinito è **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-238">**Show tip for impersonated domains**: The default value is **Off**.</span></span> <span data-ttu-id="0269a-239">Per attivarlo, far scorrere l'interruttore su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-239">To turn it on, slide the toggle to **On**.</span></span>
     - <span data-ttu-id="0269a-240">**Mostra suggerimento per caratteri insoliti**: il valore predefinito è **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-240">**Show tip for unusual characters**: The default value is **Off**.</span></span> <span data-ttu-id="0269a-241">Per attivarlo, far scorrere l'interruttore su **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-241">To turn it on, slide the toggle to **On**.</span></span>

     <span data-ttu-id="0269a-242">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0269a-242">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="0269a-243">**Intelligence per le cassette postali:**</span><span class="sxs-lookup"><span data-stu-id="0269a-243">**Mailbox intelligence**:</span></span>

     - <span data-ttu-id="0269a-244">**Abilitare l'intelligence per le** cassette postali? : il valore predefinito è **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-244">**Enable mailbox intelligence?**: The default value is **On**.</span></span> <span data-ttu-id="0269a-245">Per disattivarlo, far scorrere l'interruttore su **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-245">To turn it off, slide the toggle to **Off**.</span></span>

     - <span data-ttu-id="0269a-246">**Abilitare la protezione della rappresentazione basata sull'intelligence** delle cassette postali? : Questa impostazione è disponibile solo se Abilita intelligence cassetta **postale?** **è attivata.**</span><span class="sxs-lookup"><span data-stu-id="0269a-246">**Enable mailbox intelligence based impersonation protection?**: This setting is only available if **Enable mailbox intelligence?** is **On**.</span></span>

       <span data-ttu-id="0269a-247">In **Se** la posta elettronica viene inviata da un utente rappresentato, è possibile specificare una delle seguenti azioni da eseguire sui messaggi che non riescono a usare l'intelligence per le cassette postali (le stesse azioni disponibili per gli utenti protetti e i domini protetti):</span><span class="sxs-lookup"><span data-stu-id="0269a-247">In **If email is sent by an impersonated user**, you can specify one of the following actions to take on messages that fail mailbox intelligence (the same actions that are available for protected users and protected domains):</span></span>

       - <span data-ttu-id="0269a-248">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="0269a-248">**Don't apply any action**</span></span>
       - <span data-ttu-id="0269a-249">**Reindirizzare il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="0269a-249">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="0269a-250">**Sposta messaggio nella cartella Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="0269a-250">**Move message to Junk Email folder**</span></span>
       - <span data-ttu-id="0269a-251">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="0269a-251">**Quarantine the message**</span></span>
       - <span data-ttu-id="0269a-252">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="0269a-252">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="0269a-253">**Eliminare il messaggio prima che venga recapitato**</span><span class="sxs-lookup"><span data-stu-id="0269a-253">**Delete the message before it's delivered**</span></span>

   - <span data-ttu-id="0269a-254">**Aggiungere domini e mittenti attendibili:** specificare le eccezioni per il criterio:</span><span class="sxs-lookup"><span data-stu-id="0269a-254">**Add trusted senders and domains**: Specify exceptions for the policy:</span></span>

     - <span data-ttu-id="0269a-255">**Mittenti attendibili:**</span><span class="sxs-lookup"><span data-stu-id="0269a-255">**Trusted senders**:</span></span>

       - <span data-ttu-id="0269a-256">Fare clic nella casella e scorrere l'elenco degli utenti da selezionare.</span><span class="sxs-lookup"><span data-stu-id="0269a-256">Click in the box and scroll through the list of users to select.</span></span>
       - <span data-ttu-id="0269a-257">Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="0269a-257">Click in the box and start typing to filter the list and select a user.</span></span>
       - <span data-ttu-id="0269a-258">Per rimuovere una voce, fare **clic sull'icona** ![ Rimuovi ](../../media/scc-remove-icon.png) nell'utente.</span><span class="sxs-lookup"><span data-stu-id="0269a-258">To remove an entry, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the user.</span></span>

     - <span data-ttu-id="0269a-259">**Domini attendibili:** immettere il nome di dominio (ad esempio, contoso.com), premere INVIO e ripetere in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="0269a-259">**Trusted domains**: Enter the domain name (for example, contoso.com), press ENTER, and repeat as necessary.</span></span>

   - <span data-ttu-id="0269a-260">**Rivedere le impostazioni:** invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="0269a-260">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0269a-261">È possibile fare **clic su Modifica** in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="0269a-261">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0269a-262">È possibile attivare o **disattivare** le **impostazioni** seguenti direttamente in questa pagina:</span><span class="sxs-lookup"><span data-stu-id="0269a-262">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="0269a-263">**Utenti protetti**</span><span class="sxs-lookup"><span data-stu-id="0269a-263">**Protected users**</span></span>
       - <span data-ttu-id="0269a-264">**Domini protetti** \> **Includere i domini di cui sono proprietario**</span><span class="sxs-lookup"><span data-stu-id="0269a-264">**Protected domains** \> **Include domains I own**</span></span>
       - <span data-ttu-id="0269a-265">**Domini protetti** \> **Domini protetti** (domini personalizzati)</span><span class="sxs-lookup"><span data-stu-id="0269a-265">**Protected domains** \> **Protected domains** (custom domains)</span></span>
       - <span data-ttu-id="0269a-266">**Intelligence della cassetta postale**</span><span class="sxs-lookup"><span data-stu-id="0269a-266">**Mailbox intelligence**</span></span>

   <span data-ttu-id="0269a-267">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="0269a-267">When you're finished, click **Save** on any page.</span></span>

6. <span data-ttu-id="0269a-268">**Spoof**:  fare clic su Modifica per attivare o disattivare spoof intelligence, attivare o disattivare l'identificazione del mittente non autenticato in Outlook e configurare l'azione da applicare ai messaggi provenienti da mittenti falsificati bloccati.</span><span class="sxs-lookup"><span data-stu-id="0269a-268">**Spoof**: Click **Edit** to turn spoof intelligence on or off, turn unauthenticated sender identification in Outlook on or off, and configure the action to apply to messages from blocked spoofed senders.</span></span> <span data-ttu-id="0269a-269">Per ulteriori informazioni, vedere [Impostazioni di spoofing nei criteri anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="0269a-269">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   <span data-ttu-id="0269a-270">Si noti che queste stesse impostazioni sono disponibili anche nei criteri anti-phishing in EOP.</span><span class="sxs-lookup"><span data-stu-id="0269a-270">Note that these same settings are also available in anti-phishing policies in EOP.</span></span>

   - <span data-ttu-id="0269a-271">**Impostazioni del filtro per lo spoofing**: il valore predefinito è **On** e si consiglia di lasciarlo.</span><span class="sxs-lookup"><span data-stu-id="0269a-271">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="0269a-272">Per disattivarlo, far scorrere l'interruttore su **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-272">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="0269a-273">Per ulteriori informazioni, vedere [Configurare spoof intelligence in EOP.](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="0269a-273">For more information, see [Configure spoof intelligence in EOP](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="0269a-274">Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Microsoft 365; si abilita invece il filtro avanzato per i connettori.</span><span class="sxs-lookup"><span data-stu-id="0269a-274">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="0269a-275">Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)</span><span class="sxs-lookup"><span data-stu-id="0269a-275">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="0269a-276">**Abilita la funzionalità mittente non autenticato:** il valore predefinito è **Attivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-276">**Enable Unauthenticated Sender feature**: The default value is **On**.</span></span> <span data-ttu-id="0269a-277">Per disattivarlo, far scorrere l'interruttore su **Disattivato.**</span><span class="sxs-lookup"><span data-stu-id="0269a-277">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="0269a-278">**Azioni**: specificare l'azione da eseguire sui messaggi che non riescono a spoof intelligence:</span><span class="sxs-lookup"><span data-stu-id="0269a-278">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="0269a-279">Se la posta elettronica viene inviata da un utente a cui non è consentito **effettuare lo spoofing del dominio:**</span><span class="sxs-lookup"><span data-stu-id="0269a-279">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="0269a-280">**Spostare il messaggio nelle cartelle Posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="0269a-280">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="0269a-281">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="0269a-281">**Quarantine the message**</span></span>

   - <span data-ttu-id="0269a-282">**Rivedere le impostazioni:** invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.</span><span class="sxs-lookup"><span data-stu-id="0269a-282">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="0269a-283">È possibile fare **clic su Modifica** in ogni sezione per tornare alla pagina pertinente.</span><span class="sxs-lookup"><span data-stu-id="0269a-283">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="0269a-284">È possibile attivare o **disattivare** le **impostazioni** seguenti direttamente in questa pagina:</span><span class="sxs-lookup"><span data-stu-id="0269a-284">You can toggle the following settings **On** or **Off** directly on this page:</span></span>
       - <span data-ttu-id="0269a-285">**Abilitare la protezione antispoofing**</span><span class="sxs-lookup"><span data-stu-id="0269a-285">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="0269a-286">**Abilitare la funzionalità Mittente non autenticato**</span><span class="sxs-lookup"><span data-stu-id="0269a-286">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="0269a-287">Al termine, fare clic su **Salva** in qualsiasi pagina.</span><span class="sxs-lookup"><span data-stu-id="0269a-287">When you're finished, click **Save** on any page.</span></span>

7. <span data-ttu-id="0269a-288">**Impostazioni avanzate:** fare clic **su Modifica** per configurare le soglie di phishing avanzate.</span><span class="sxs-lookup"><span data-stu-id="0269a-288">**Advanced settings**: Click **Edit** to configure the advanced phishing thresholds.</span></span> <span data-ttu-id="0269a-289">Per ulteriori informazioni, vedere [Soglie di phishing avanzate nei criteri anti-phishing in Microsoft Defender per Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="0269a-289">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="0269a-290">**Soglie di phishing avanzate:** selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="0269a-290">**Advanced phishing thresholds**: Select one of the following values:</span></span>

   - <span data-ttu-id="0269a-291">**1 - Standard** (questo è il valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="0269a-291">**1 - Standard** (This is the default value.)</span></span>
   - <span data-ttu-id="0269a-292">**2 - Aggressivo**</span><span class="sxs-lookup"><span data-stu-id="0269a-292">**2 - Aggressive**</span></span>
   - <span data-ttu-id="0269a-293">**3 - Più aggressivo**</span><span class="sxs-lookup"><span data-stu-id="0269a-293">**3 - More aggressive**</span></span>
   - <span data-ttu-id="0269a-294">**4 - Più aggressivo**</span><span class="sxs-lookup"><span data-stu-id="0269a-294">**4 - Most aggressive**</span></span>

   - <span data-ttu-id="0269a-295">**Rivedere le impostazioni:** fare clic **su Modifica** per tornare alla **pagina Soglie di phishing** avanzate.</span><span class="sxs-lookup"><span data-stu-id="0269a-295">**Review your settings**: Click **Edit** to jump back to the **Advanced phishing thresholds** page.</span></span>

   <span data-ttu-id="0269a-296">Al termine, fare clic su **Salva** in entrambe le pagine.</span><span class="sxs-lookup"><span data-stu-id="0269a-296">When you're finished, click **Save** on either page.</span></span>

8. <span data-ttu-id="0269a-297">Tornare alla pagina **Modifica i \<Name\> criteri,** rivedere le impostazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="0269a-297">Back on the **Edit your policy \<Name\>** page, review your settings and then click **Close**.</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0269a-298">Usare il Centro sicurezza & conformità per modificare il criterio anti-phishing predefinito in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="0269a-298">Use the Security & Compliance Center to modify the default anti-phishing policy in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0269a-299">Il criterio anti-phishing predefinito in Microsoft Defender per Office 365 è denominato Office365 AntiPhish Default e non viene visualizzato nell'elenco dei criteri.</span><span class="sxs-lookup"><span data-stu-id="0269a-299">The default anti-phishing policy in Microsoft Defender for Office 365 is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="0269a-300">Per modificare il criterio anti-phishing predefinito, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="0269a-300">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="0269a-301">Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="0269a-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0269a-302">Nella pagina **Anti-phishing** fare clic su **Criterio predefinito.**</span><span class="sxs-lookup"><span data-stu-id="0269a-302">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="0269a-303">Verrà **visualizzata la pagina Modifica i criteri predefiniti di Office365 AntiPhish.**</span><span class="sxs-lookup"><span data-stu-id="0269a-303">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="0269a-304">Sono disponibili le sezioni seguenti, che contengono le stesse impostazioni per la modifica [di un criterio personalizzato:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="0269a-304">The following sections are available, which contain identical settings for when you [modify a custom policy](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365):</span></span>

   - <span data-ttu-id="0269a-305">**Rappresentazione**</span><span class="sxs-lookup"><span data-stu-id="0269a-305">**Impersonation**</span></span>
   - <span data-ttu-id="0269a-306">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="0269a-306">**Spoof**</span></span>
   - <span data-ttu-id="0269a-307">**Impostazioni avanzate**</span><span class="sxs-lookup"><span data-stu-id="0269a-307">**Advanced settings**</span></span>

   <span data-ttu-id="0269a-308">Le impostazioni seguenti non sono disponibili quando si modifica il criterio predefinito:</span><span class="sxs-lookup"><span data-stu-id="0269a-308">The following settings aren't available when you modify the default policy:</span></span>

   - <span data-ttu-id="0269a-309">È possibile  visualizzare la sezione e i valori  dell'impostazione dei criteri, ma non è disponibile alcun collegamento Modifica, quindi non è possibile modificare le impostazioni (nome del criterio, descrizione e a chi si applica il criterio (si applica a tutti i destinatari)).</span><span class="sxs-lookup"><span data-stu-id="0269a-309">You can see the **Policy setting** section and values, but there's no **Edit** link, so you can't modify the settings (policy name, description, and who the policy applies to (it applies to all recipients)).</span></span>
   - <span data-ttu-id="0269a-310">Non è possibile eliminare il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="0269a-310">You can't delete the default policy.</span></span>
   - <span data-ttu-id="0269a-311">Non è possibile modificare la priorità del criterio predefinito (viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="0269a-311">You can't change the priority of the default policy (it's always applied last).</span></span>

4. <span data-ttu-id="0269a-312">Nella pagina **Modifica i criteri predefiniti di Office365,** rivedere le impostazioni e quindi fare clic su **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="0269a-312">On the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0269a-313">Abilitare o disabilitare i criteri anti-phishing personalizzati in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="0269a-313">Enable or disable custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="0269a-314">Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="0269a-314">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0269a-315">Si noti il valore nella **colonna** Stato:</span><span class="sxs-lookup"><span data-stu-id="0269a-315">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="0269a-316">Fai scorrere **l'interruttore su Off** per disabilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="0269a-316">Slide the toggle to **Off** to disable the policy.</span></span>

   - <span data-ttu-id="0269a-317">Fai scorrere **l'interruttore su On** per abilitare il criterio.</span><span class="sxs-lookup"><span data-stu-id="0269a-317">Slide the toggle to **On** to enable the policy.</span></span>

<span data-ttu-id="0269a-318">Non è possibile disabilitare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="0269a-318">You can't disable the default anti-phishing policy.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0269a-319">Impostare la priorità dei criteri anti-phishing personalizzati in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="0269a-319">Set the priority of custom anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0269a-320">Per impostazione predefinita, ai criteri anti-phishing viene data una priorità che si basa sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità inferiore rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="0269a-320">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="0269a-321">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="0269a-321">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="0269a-322">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="0269a-322">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="0269a-323">Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).</span><span class="sxs-lookup"><span data-stu-id="0269a-323">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="0269a-324">I criteri anti-phishing personalizzati vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore Di** priorità 0).</span><span class="sxs-lookup"><span data-stu-id="0269a-324">Custom anti-phishing policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="0269a-325">Il criterio anti-phishing predefinito denominato Office365 AntiPhish Default ha il valore di priorità personalizzato **Lowest** e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="0269a-325">The default anti-phishing policy named Office365 AntiPhish Default has the custom priority value **Lowest**, and you can't change it.</span></span>

 <span data-ttu-id="0269a-326">**Nota:** nel Centro sicurezza & conformità, è possibile modificare la priorità del criterio anti-phishing solo dopo aver creato il criterio.</span><span class="sxs-lookup"><span data-stu-id="0269a-326">**Note**: In the Security & Compliance Center, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="0269a-327">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phish (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="0269a-327">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="0269a-328">Per modificare la priorità di  un criterio, fare clic su Aumenta priorità o Diminuisci  priorità nelle proprietà del criterio (non è possibile modificare direttamente il numero di priorità nel Centro sicurezza & conformità). </span><span class="sxs-lookup"><span data-stu-id="0269a-328">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span> <span data-ttu-id="0269a-329">La modifica della priorità di un criterio è utile solo se si dispone di più criteri.</span><span class="sxs-lookup"><span data-stu-id="0269a-329">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

1. <span data-ttu-id="0269a-330">Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="0269a-330">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0269a-331">Selezionare il criterio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="0269a-331">Select the policy that you want to modify.</span></span> <span data-ttu-id="0269a-332">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="0269a-332">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0269a-333">Verrà **visualizzato \<name\> il riquadro a comparsa** Modifica criterio.</span><span class="sxs-lookup"><span data-stu-id="0269a-333">The **Edit your policy \<name\>** flyout appears.</span></span>

   - <span data-ttu-id="0269a-334">Il criterio anti-phishing personalizzato con **il valore Priority** **0** ha solo il **pulsante Diminuisci** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="0269a-334">The custom anti-phishing policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="0269a-335">Il criterio anti-phishing personalizzato con il valore **Di** priorità più basso (ad esempio, **3)** ha solo il pulsante **Aumenta** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="0269a-335">The custom anti-phishing policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="0269a-336">Se si dispone di tre o più criteri anti-phishing personalizzati,  i criteri tra i valori di priorità più alta e più bassa hanno entrambi i pulsanti Aumenta priorità e **Diminuisci** priorità disponibili.</span><span class="sxs-lookup"><span data-stu-id="0269a-336">If you have three or more custom anti-phishing policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="0269a-337">Fare **clic su Aumenta priorità** o **Diminuisci priorità** per modificare il valore **di** Priorità.</span><span class="sxs-lookup"><span data-stu-id="0269a-337">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="0269a-338">Al termine, fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="0269a-338">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0269a-339">Usare il Centro sicurezza & conformità per visualizzare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="0269a-339">Use the Security & Compliance Center to view anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="0269a-340">Nel Centro sicurezza & conformità e passare a Criteri di **gestione** delle minacce \>  \> **ANTI-phishing ATP.**</span><span class="sxs-lookup"><span data-stu-id="0269a-340">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0269a-341">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0269a-341">Do one of the following steps:</span></span>

   - <span data-ttu-id="0269a-342">Selezionare un criterio anti-phishing personalizzato che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="0269a-342">Select a custom anti-phishing policy that you want to view.</span></span> <span data-ttu-id="0269a-343">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="0269a-343">If it's already selected, deselect it and select it again.</span></span>

   - <span data-ttu-id="0269a-344">Fare **clic su Criterio predefinito** per visualizzare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="0269a-344">Click **Default policy** to view the default anti-phishing policy.</span></span>

3. <span data-ttu-id="0269a-345">Viene **visualizzato \<name\> il riquadro a comparsa** Modifica il criterio, in cui è possibile visualizzare le impostazioni e i valori.</span><span class="sxs-lookup"><span data-stu-id="0269a-345">The **Edit your policy \<name\>** flyout appears, where you can view the settings and values.</span></span>

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0269a-346">Usare il Centro sicurezza & conformità per rimuovere i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="0269a-346">Use the Security & Compliance Center to remove anti-phishing policies in Microsoft Defender for Office 365</span></span>

1. <span data-ttu-id="0269a-347">Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="0269a-347">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="0269a-348">Selezionare il criterio che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="0269a-348">Select the policy that you want to remove.</span></span> <span data-ttu-id="0269a-349">Se è già selezionato, deselezionalo e selezionalo di nuovo.</span><span class="sxs-lookup"><span data-stu-id="0269a-349">If it's already selected, deselect it and select it again.</span></span>

3. <span data-ttu-id="0269a-350">Nel riquadro **a \<name\> comparsa Modifica** criterio visualizzato fare clic su Elimina criterio **e** quindi su **Sì** nella finestra di dialogo di avviso visualizzata.</span><span class="sxs-lookup"><span data-stu-id="0269a-350">In the **Edit your policy \<name\>** flyout that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

<span data-ttu-id="0269a-351">Non è possibile rimuovere il criterio predefinito.</span><span class="sxs-lookup"><span data-stu-id="0269a-351">You can't remove the default policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0269a-352">Utilizzare PowerShell di Exchange Online per configurare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="0269a-352">Use Exchange Online PowerShell to configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="0269a-353">Come descritto in precedenza, un criterio di protezione da posta indesiderata è costituito da un criterio anti-phish e da una regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="0269a-353">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="0269a-354">In PowerShell di Exchange Online, la differenza tra i criteri anti-phish e le regole anti-phish è evidente.</span><span class="sxs-lookup"><span data-stu-id="0269a-354">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="0269a-355">È possibile gestire i criteri anti-phish utilizzando i cmdlet **\* -AntiPhishPolicy** e gestire le regole anti-phish utilizzando i cmdlet **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="0269a-355">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="0269a-356">In PowerShell, si crea prima il criterio anti-phish, quindi si crea la regola anti-phish che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="0269a-356">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="0269a-357">In PowerShell, le impostazioni dei criteri anti-phish e della regola anti-phish vengono modificate separatamente.</span><span class="sxs-lookup"><span data-stu-id="0269a-357">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="0269a-358">Quando si rimuove un criterio anti-phish da PowerShell, la regola anti-phish corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="0269a-358">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="0269a-359">Utilizzare PowerShell per creare criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="0269a-359">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="0269a-360">La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="0269a-360">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="0269a-361">Creare il criterio anti-phish.</span><span class="sxs-lookup"><span data-stu-id="0269a-361">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="0269a-362">Creare la regola anti-phish che specifica il criterio anti-phish a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="0269a-362">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="0269a-363">**Note**:</span><span class="sxs-lookup"><span data-stu-id="0269a-363">**Notes**:</span></span>

- <span data-ttu-id="0269a-364">È possibile creare una nuova regola anti-phish e assegnarle un criterio anti-phish esistente e non associazione.</span><span class="sxs-lookup"><span data-stu-id="0269a-364">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="0269a-365">Una regola anti-phish non può essere associata a più criteri anti-phish.</span><span class="sxs-lookup"><span data-stu-id="0269a-365">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="0269a-366">È possibile configurare le impostazioni seguenti nei nuovi criteri anti-phish in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:</span><span class="sxs-lookup"><span data-stu-id="0269a-366">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>

  - <span data-ttu-id="0269a-367">Creare il nuovo criterio come disabilitato (_abilitato_ `$false` nel cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="0269a-367">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="0269a-368">Impostare la priorità del criterio durante la creazione (_Priority_ ) nel _\<Number\>_ cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="0269a-368">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="0269a-369">Un nuovo criterio anti-phish creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="0269a-369">A new anti-phish policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="0269a-370">Passaggio 1: Utilizzare PowerShell per creare un criterio anti-phish</span><span class="sxs-lookup"><span data-stu-id="0269a-370">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="0269a-371">Per creare un criterio anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0269a-371">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="0269a-372">In questo esempio viene creato un criterio anti-phish denominato Research Quarantine con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0269a-372">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="0269a-373">Il criterio è abilitato (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="0269a-373">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="0269a-374">La descrizione è: Criteri del reparto ricerche.</span><span class="sxs-lookup"><span data-stu-id="0269a-374">The description is: Research department policy.</span></span>
- <span data-ttu-id="0269a-375">Abilita la protezione dei domini dell'organizzazione per tutti i domini accettati e la protezione dei domini di destinazione per fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="0269a-375">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="0269a-376">Specifica Mai Fujito (mfujito@fabrikam.com) come l'utente da proteggere da imitazione.</span><span class="sxs-lookup"><span data-stu-id="0269a-376">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="0269a-377">Abilita l'intelligence della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="0269a-377">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="0269a-378">Abilita la protezione intelligence delle cassette postali e specifica l'azione di quarantena.</span><span class="sxs-lookup"><span data-stu-id="0269a-378">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="0269a-379">Abilita i suggerimenti per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0269a-379">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="0269a-380">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="0269a-380">For detailed syntax and parameter information, see [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="0269a-381">Passaggio 2: Utilizzare PowerShell per creare una regola anti-phish</span><span class="sxs-lookup"><span data-stu-id="0269a-381">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="0269a-382">Per creare una regola anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0269a-382">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="0269a-383">In questo esempio viene creata una regola anti-phish denominata Research Department con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0269a-383">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="0269a-384">La regola è associata al criterio anti-phish denominato Quarantena ricerche.</span><span class="sxs-lookup"><span data-stu-id="0269a-384">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="0269a-385">La regola viene applicata ai membri del gruppo denominato Research Department.</span><span class="sxs-lookup"><span data-stu-id="0269a-385">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="0269a-386">Poiché non viene utilizzato il parametro _Priority,_ viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="0269a-386">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="0269a-387">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="0269a-387">For detailed syntax and parameter information, see [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="0269a-388">Usare PowerShell per visualizzare i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="0269a-388">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="0269a-389">Per visualizzare i criteri anti-phish esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0269a-389">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0269a-390">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri anti-phish insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="0269a-390">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="0269a-391">In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio anti-phish denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="0269a-391">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="0269a-392">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="0269a-392">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="0269a-393">Utilizzare PowerShell per visualizzare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="0269a-393">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="0269a-394">Per visualizzare le regole anti-phish esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0269a-394">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="0269a-395">In questo esempio viene restituito un elenco riepilogativo di tutte le regole anti-phish insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="0269a-395">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="0269a-396">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0269a-396">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="0269a-397">In questo esempio vengono restituiti tutti i valori delle proprietà per la regola anti-phish denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="0269a-397">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="0269a-398">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)</span><span class="sxs-lookup"><span data-stu-id="0269a-398">For detailed syntax and parameter information, see [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="0269a-399">Utilizzare PowerShell per modificare i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="0269a-399">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="0269a-400">Oltre agli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio anti-phish in PowerShell come quando si crea il criterio come descritto nel passaggio 1: Utilizzare PowerShell per creare una sezione dei criteri [anti-phish](#step-1-use-powershell-to-create-an-anti-phish-policy) più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0269a-400">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="0269a-401">L'opzione _MakeDefault_ che trasforma il criterio specificato nel  criterio predefinito (applicato a tutti, sempre con priorità bassa e non è possibile eliminarlo) è disponibile solo quando si modifica un criterio anti-phish in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0269a-401">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="0269a-402">Non è possibile rinominare un criterio anti-phish (il cmdlet **Set-AntiPhishPolicy** non dispone di alcun _parametro_ Name).</span><span class="sxs-lookup"><span data-stu-id="0269a-402">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="0269a-403">Quando si rinomina un criterio anti-phishing nel Centro sicurezza & conformità, si rinomina solo la regola anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="0269a-403">When you rename an anti-phishing policy in the Security & Compliance Center, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="0269a-404">Per modificare un criterio anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0269a-404">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="0269a-405">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="0269a-405">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="0269a-406">Utilizzare PowerShell per modificare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="0269a-406">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="0269a-407">L'unica impostazione non disponibile quando si modifica una regola anti-phish in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="0269a-407">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="0269a-408">Per abilitare o disabilitare le regole anti-phish esistenti, vedere la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="0269a-408">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="0269a-409">In caso contrario, non sono disponibili impostazioni aggiuntive quando si modifica una regola anti-phish in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0269a-409">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="0269a-410">Le stesse impostazioni sono disponibili quando si crea una regola come descritto nel passaggio 2: Utilizzare PowerShell per creare una regola [anti-phish](#step-2-use-powershell-to-create-an-anti-phish-rule) descritta in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="0269a-410">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="0269a-411">Per modificare una regola anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0269a-411">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="0269a-412">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="0269a-412">For detailed syntax and parameter information, see [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="0269a-413">Utilizzare PowerShell per abilitare o disabilitare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="0269a-413">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="0269a-414">L'abilitazione o disabilitazione di una regola anti-phishing in PowerShell abilita o disabilita l'intero criterio anti-phishing (la regola anti-phishing e il criterio anti-phishing assegnato).</span><span class="sxs-lookup"><span data-stu-id="0269a-414">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="0269a-415">Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="0269a-415">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="0269a-416">Per abilitare o disabilitare una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0269a-416">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="0269a-417">In questo esempio viene disabilitata la regola anti-phish denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="0269a-417">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0269a-418">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="0269a-418">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0269a-419">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="0269a-419">For detailed syntax and parameter information, see [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="0269a-420">Usare PowerShell per impostare la priorità delle regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="0269a-420">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="0269a-421">Il valore di priorità più alto che è possibile impostare in una regola è 0.</span><span class="sxs-lookup"><span data-stu-id="0269a-421">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="0269a-422">Il valore più basso che è possibile impostare dipende dal numero di regole.</span><span class="sxs-lookup"><span data-stu-id="0269a-422">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="0269a-423">Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4.</span><span class="sxs-lookup"><span data-stu-id="0269a-423">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="0269a-424">Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole.</span><span class="sxs-lookup"><span data-stu-id="0269a-424">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="0269a-425">Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="0269a-425">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="0269a-426">Per impostare la priorità di una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0269a-426">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="0269a-p148">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="0269a-p148">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="0269a-429">**Note**:</span><span class="sxs-lookup"><span data-stu-id="0269a-429">**Notes**:</span></span>

- <span data-ttu-id="0269a-430">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="0269a-430">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="0269a-431">Il criterio anti-phish predefinito non dispone di una regola anti-phish corrispondente e ha sempre il valore di priorità non modificabile **Lowest.**</span><span class="sxs-lookup"><span data-stu-id="0269a-431">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="0269a-432">Utilizzare PowerShell per rimuovere i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="0269a-432">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="0269a-433">Quando si utilizza PowerShell per rimuovere un criterio anti-phish, la regola anti-phish corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="0269a-433">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="0269a-434">Per rimuovere un criterio anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0269a-434">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="0269a-435">In questo esempio viene rimosso il criterio anti-phish denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="0269a-435">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="0269a-436">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="0269a-436">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="0269a-437">Utilizzare PowerShell per rimuovere le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="0269a-437">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="0269a-438">Quando si utilizza PowerShell per rimuovere una regola anti-phish, il criterio anti-phish corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="0269a-438">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="0269a-439">Per rimuovere una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0269a-439">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="0269a-440">In questo esempio viene rimossa la regola anti-phish denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="0269a-440">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="0269a-441">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="0269a-441">For detailed syntax and parameter information, see [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0269a-442">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="0269a-442">How do you know these procedures worked?</span></span>

<span data-ttu-id="0269a-443">Per verificare la corretta configurazione dei criteri anti-phishing in Microsoft Defender per Office 365, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0269a-443">To verify that you've successfully configured anti-phishing policies in Microsoft Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="0269a-444">Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.**</span><span class="sxs-lookup"><span data-stu-id="0269a-444">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span> <span data-ttu-id="0269a-445">Verificare l'elenco dei criteri, i relativi **valori di** stato e i relativi **valori di** priorità.</span><span class="sxs-lookup"><span data-stu-id="0269a-445">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="0269a-446">Per visualizzare ulteriori dettagli, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0269a-446">To view more details do either of the following steps:</span></span>

  - <span data-ttu-id="0269a-447">Selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="0269a-447">Select the policy from the list, and view the details in the flyout.</span></span>
  - <span data-ttu-id="0269a-448">Fare **clic su Criterio** predefinito e visualizzare i dettagli nel riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="0269a-448">Click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="0269a-449">In PowerShell di Exchange Online, sostituire con il nome del criterio o della regola ed eseguire il \<Name\> comando seguente e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="0269a-449">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
