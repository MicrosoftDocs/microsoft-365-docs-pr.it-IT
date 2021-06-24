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
description: Gli amministratori possono imparare a creare, modificare ed eliminare i criteri anti-phishing disponibili nelle organizzazioni di Exchange Online Protection (EOP) con o senza Exchange Online cassette postali.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e56e1b5d91b74d2ffcf9cccc897962b915c6e83c
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108068"
---
# <a name="configure-anti-phishing-policies-in-eop"></a><span data-ttu-id="3ae04-103">Configurare i criteri anti-phishing in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3ae04-103">Configure anti-phishing policies in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3ae04-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="3ae04-104">**Applies to**</span></span>
- [<span data-ttu-id="3ae04-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3ae04-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="3ae04-106">Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, esiste un criterio anti-phishing predefinito che contiene un numero limitato di funzionalità anti-spoofing abilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3ae04-106">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there's a default anti-phishing policy that contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="3ae04-107">Per altre informazioni, vedere [Impostazioni di spoofing nei criteri anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="3ae04-107">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="3ae04-108">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="3ae04-108">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="3ae04-109">Per una maggiore granularità, è inoltre possibile creare criteri anti-phishing personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3ae04-109">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="3ae04-110">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).</span><span class="sxs-lookup"><span data-stu-id="3ae04-110">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="3ae04-111">Le organizzazioni con Exchange Online cassette postali possono configurare i criteri anti-phishing nel portale di Microsoft 365 Defender o in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ae04-111">Organizations with Exchange Online mailboxes can configure anti-phishing policies in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span> <span data-ttu-id="3ae04-112">Le organizzazioni EOP autonome possono utilizzare solo il Microsoft 365 Defender portale.</span><span class="sxs-lookup"><span data-stu-id="3ae04-112">Standalone EOP organizations can only use the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="3ae04-113">Per informazioni sulla creazione e la modifica dei criteri anti-phishing più avanzati disponibili in Microsoft Defender per Office 365, vedere [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3ae04-113">For information about creating and modifying the more advanced anti-phishing policies that are available in Microsoft Defender for Office 365, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

<span data-ttu-id="3ae04-114">Gli elementi di base di un criterio anti-phishing sono:</span><span class="sxs-lookup"><span data-stu-id="3ae04-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="3ae04-115">**Il criterio anti-phishing**: Specifica le protezioni anti-phishing da abilitare o disabilitare e le azioni da applicare.</span><span class="sxs-lookup"><span data-stu-id="3ae04-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="3ae04-116">**La regola anti-phish**: Specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phish.</span><span class="sxs-lookup"><span data-stu-id="3ae04-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="3ae04-117">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri anti-phishing nel portale Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="3ae04-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="3ae04-118">Quando crei un criterio anti-phishing, stai creando una regola anti-phishing e il criterio anti-phishing associato contemporaneamente usando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="3ae04-118">When you create an anti-phishing policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="3ae04-119">Quando si modifica un criterio anti-phishing, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="3ae04-119">When you modify an anti-phishing policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="3ae04-120">Tutte le altre impostazioni modificano il criterio anti-phish associato.</span><span class="sxs-lookup"><span data-stu-id="3ae04-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="3ae04-121">Quando si rimuove un criterio anti-phishing, la regola anti-phishing e il criterio anti-phishing associato vengono rimossi.</span><span class="sxs-lookup"><span data-stu-id="3ae04-121">When you remove an anti-phishing policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="3ae04-122">In Exchange Online PowerShell, il criterio e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="3ae04-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="3ae04-123">Per ulteriori informazioni, vedere la sezione [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3ae04-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="3ae04-124">Ogni organizzazione dispone di un criterio anti-phishing predefinito denominato Office365 AntiPhish Default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="3ae04-124">Every organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="3ae04-125">Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se al criterio non è associata alcuna regola anti-phish (filtri destinatari).</span><span class="sxs-lookup"><span data-stu-id="3ae04-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="3ae04-126">Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="3ae04-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="3ae04-127">Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="3ae04-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="3ae04-128">Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="3ae04-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="3ae04-129">Per aumentare l'efficacia della protezione anti-phishing, è possibile creare criteri anti-phishing personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="3ae04-129">To increase the effectiveness of anti-phishing protection, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3ae04-130">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="3ae04-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3ae04-131">Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="3ae04-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="3ae04-132">Per passare direttamente alla pagina **Anti-phishing,** utilizzare <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="3ae04-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="3ae04-133">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3ae04-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

  <span data-ttu-id="3ae04-134">Non è possibile gestire i criteri anti-phishing in PowerShell EOP autonomo.</span><span class="sxs-lookup"><span data-stu-id="3ae04-134">You can't manage anti-phishing policies in standalone EOP PowerShell.</span></span>

- <span data-ttu-id="3ae04-135">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="3ae04-135">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="3ae04-136">Per aggiungere, modificare ed eliminare criteri anti-phishing, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-136">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="3ae04-137">Per l'accesso in sola lettura ai criteri anti-phishing, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="3ae04-137">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="3ae04-138">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="3ae04-138">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="3ae04-139">**Note**:</span><span class="sxs-lookup"><span data-stu-id="3ae04-139">**Notes**:</span></span>

  - <span data-ttu-id="3ae04-140">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ae04-140">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="3ae04-141">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3ae04-141">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="3ae04-142">Il **gruppo di ruoli Gestione organizzazione** di sola visualizzazione in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) consente inoltre l'accesso in sola lettura alla funzionalità <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="3ae04-142">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature<sup>\*</sup>.</span></span>

- <span data-ttu-id="3ae04-143">Per le impostazioni consigliate per i criteri anti-phishing, vedere [Impostazioni dei criteri anti-phishing EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="3ae04-143">For our recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="3ae04-144">Consentire fino a 30 minuti per l'applicazione del criterio aggiornato.</span><span class="sxs-lookup"><span data-stu-id="3ae04-144">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="3ae04-145">Per informazioni su dove vengono applicati i criteri anti-phishing nella pipeline di filtro, vedere [Order and precedence of email protection.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="3ae04-145">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="3ae04-146">Utilizzare il portale Microsoft 365 Defender per creare criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="3ae04-146">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="3ae04-147">La creazione di un criterio anti-phishing personalizzato nel portale di Microsoft 365 Defender crea la regola anti-phishing e il criterio anti-phishing associato contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="3ae04-147">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="3ae04-148">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-148">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3ae04-149">Nella pagina **Anti-phishing** fare clic su ![ Crea icona ](../../media/m365-cc-sc-create-icon.png) **Crea**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-149">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="3ae04-150">Viene aperta la creazione guidata criteri.</span><span class="sxs-lookup"><span data-stu-id="3ae04-150">The policy wizard opens.</span></span> <span data-ttu-id="3ae04-151">Nella pagina **Nome criterio** configurare queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="3ae04-151">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="3ae04-152">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="3ae04-152">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="3ae04-153">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="3ae04-153">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="3ae04-154">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-154">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="3ae04-155">Nella pagina **Utenti, gruppi e domini** visualizzata identificare i destinatari interni a cui si applicano i criteri (condizioni del destinatario):</span><span class="sxs-lookup"><span data-stu-id="3ae04-155">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="3ae04-156">**Utenti**: la cassette postali specificate, utenti di posta o contatti di posta specificati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3ae04-156">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="3ae04-157">**Gruppi**: i gruppi di distribuzione specificati, gruppi di sicurezza abilitati alla posta elettronica o gruppi di Microsoft 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3ae04-157">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="3ae04-158">**Domini**: tutti i destinatari nei domini specificati [accettati](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3ae04-158">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="3ae04-159">Fare clic nella casella appropriata, iniziare a digitare un valore e selezionare il valore desiderato nei risultati.</span><span class="sxs-lookup"><span data-stu-id="3ae04-159">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="3ae04-160">Ripetere questa procedura tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="3ae04-160">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="3ae04-161">Per rimuovere un valore esistente, fare clic su Rimuovi</span><span class="sxs-lookup"><span data-stu-id="3ae04-161">To remove an existing value, click remove</span></span> ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="3ae04-163">accanto al valore.</span><span class="sxs-lookup"><span data-stu-id="3ae04-163">next to the value.</span></span>

   <span data-ttu-id="3ae04-164">Per utenti o gruppi è possibile usare la maggior parte degli identificatori, ad esempio nome, nome visualizzato, alias, indirizzo di posta elettronica, nome dell'account e così via, ma il nome visualizzato corrispondente viene visualizzato nei risultati.</span><span class="sxs-lookup"><span data-stu-id="3ae04-164">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="3ae04-165">Per gli utenti, immettere un asterisco (\*) da solo per visualizzare tutti i valori disponibili.</span><span class="sxs-lookup"><span data-stu-id="3ae04-165">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="3ae04-166">Più valori della stessa condizione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="3ae04-166">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="3ae04-167">Condizioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="3ae04-167">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="3ae04-168">**Escludere questi utenti, gruppi e domini**: per aggiungere eccezioni per i destinatari interni a cui si applicano i criteri (eccezione destinatari), selezionare questa opzione e configurare le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="3ae04-168">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="3ae04-169">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="3ae04-169">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="3ae04-170">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-170">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="3ae04-171">Nella pagina **Soglia di &** phishing visualizzata, utilizzare la casella di controllo Abilita spoof **intelligence** per attivare o disattivare l'intelligence di spoofing.</span><span class="sxs-lookup"><span data-stu-id="3ae04-171">On the **Phishing threshold & protection** page that appears, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="3ae04-172">Il valore predefinito è on (selezionato) e ti consigliamo di lasciarlo.</span><span class="sxs-lookup"><span data-stu-id="3ae04-172">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="3ae04-173">È possibile configurare l'azione da eseguire sui messaggi falsificati bloccati nella pagina successiva.</span><span class="sxs-lookup"><span data-stu-id="3ae04-173">You configure the action to take on blocked spoofed messages on the next page.</span></span>

   <span data-ttu-id="3ae04-174">Per disattivare lo spoof intelligence, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="3ae04-174">To turn off spoof intelligence, clear the check box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3ae04-175">Non è necessario disattivare la protezione anti-spoofing se il record MX non punta a Microsoft 365; si abilita invece il filtro avanzato per i connettori.</span><span class="sxs-lookup"><span data-stu-id="3ae04-175">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="3ae04-176">Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="3ae04-176">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="3ae04-177">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-177">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="3ae04-178">Nella pagina **Azioni** visualizzata configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ae04-178">On the **Actions** page that appears, configure the following settings:</span></span>
   - <span data-ttu-id="3ae04-179">**Se il messaggio viene rilevato come spoof:** questa impostazione è disponibile solo se è stato selezionato **Abilita spoof intelligence** nella pagina precedente.</span><span class="sxs-lookup"><span data-stu-id="3ae04-179">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="3ae04-180">Selezionare una delle azioni seguenti nell'elenco a discesa per i messaggi provenienti da mittenti falsificati bloccati:</span><span class="sxs-lookup"><span data-stu-id="3ae04-180">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
     - <span data-ttu-id="3ae04-181">**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="3ae04-181">**Move message to the recipients' Junk Email folders**</span></span>
     - <span data-ttu-id="3ae04-182">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="3ae04-182">**Quarantine the message**</span></span>

   - <span data-ttu-id="3ae04-183">**Suggerimenti per la sicurezza & indicatori**:</span><span class="sxs-lookup"><span data-stu-id="3ae04-183">**Safety tips & indicators**:</span></span>
     - <span data-ttu-id="3ae04-184">**Show first contact suggerimento per la sicurezza**: Per ulteriori informazioni, vedere [First contact suggerimento per la sicurezza](set-up-anti-phishing-policies.md#first-contact-safety-tip).</span><span class="sxs-lookup"><span data-stu-id="3ae04-184">**Show first contact safety tip**: For more information, see [First contact safety tip](set-up-anti-phishing-policies.md#first-contact-safety-tip).</span></span>
     - <span data-ttu-id="3ae04-185">**Show (?) for unauthenticated senders for spoof**: Aggiunge un punto interrogativo alla foto del mittente nella casella Da di Outlook se il messaggio non supera i controlli SPF o DKIM e il messaggio non passa DMARC o <sup>\*</sup> l'autenticazione [composita.](email-validation-and-authentication.md#composite-authentication) </span><span class="sxs-lookup"><span data-stu-id="3ae04-185">**Show (?) for unauthenticated senders for spoof**<sup>\*</sup>: Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="3ae04-186">**Show "via" tag**: Aggiunge un tag via (chris@contoso.com tramite fabrikam.com) all'indirizzo From se è diverso dal dominio nella firma <sup>\*</sup> DKIM o nell'indirizzo **MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-186">**Show "via" tag**<sup>\*</sup>: Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span>

     <span data-ttu-id="3ae04-187">Per attivare un'impostazione, selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="3ae04-187">To turn on a setting, select the check box.</span></span> <span data-ttu-id="3ae04-188">Per disattivarla, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="3ae04-188">To turn it off, clear the check box.</span></span>

     <span data-ttu-id="3ae04-189"><sup>\*</sup> Questa impostazione è disponibile solo se è stata selezionata **l'opzione Abilita spoof intelligence** nella pagina precedente.</span><span class="sxs-lookup"><span data-stu-id="3ae04-189"><sup>\*</sup> This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="3ae04-190">Per ulteriori informazioni, vedere [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).</span><span class="sxs-lookup"><span data-stu-id="3ae04-190">For more information, see [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).</span></span>

   <span data-ttu-id="3ae04-191">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-191">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="3ae04-192">Nella pagina **Controllo** visualizzata controllare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="3ae04-192">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="3ae04-193">È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="3ae04-193">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="3ae04-194">Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="3ae04-194">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="3ae04-195">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-195">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="3ae04-196">Nel messaggio di conferma visualizzato fare clic su **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-196">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="3ae04-197">Utilizzare il portale Microsoft 365 Defender per visualizzare i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="3ae04-197">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="3ae04-198">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-198">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3ae04-199">Nella pagina **Anti-phishing** vengono visualizzate le proprietà seguenti nell'elenco dei criteri:</span><span class="sxs-lookup"><span data-stu-id="3ae04-199">On the **Anti-phishing** page, the following properties are displayed in the list of policies:</span></span>

   - <span data-ttu-id="3ae04-200">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3ae04-200">**Name**</span></span>
   - <span data-ttu-id="3ae04-201">**Stato**</span><span class="sxs-lookup"><span data-stu-id="3ae04-201">**Status**</span></span>
   - <span data-ttu-id="3ae04-202">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="3ae04-202">**Priority**</span></span>
   - <span data-ttu-id="3ae04-203">**Data ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="3ae04-203">**Last modified**</span></span>

3. <span data-ttu-id="3ae04-204">Quando si seleziona un criterio facendo clic sul nome, le impostazioni dei criteri vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="3ae04-204">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="3ae04-205">Utilizzare il portale Microsoft 365 Defender per modificare i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="3ae04-205">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="3ae04-206">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-206">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3ae04-207">Nella pagina **Anti-phishing** selezionare un criterio dall'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="3ae04-207">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="3ae04-208">Nel riquadro a comparsa dei dettagli sui criteri visualizzato selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="3ae04-208">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="3ae04-209">Per ulteriori informazioni sulle impostazioni, vedere la sezione Usare il portale di Microsoft 365 Defender per creare criteri [anti-phishing](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3ae04-209">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="3ae04-210">Per il criterio anti-phishing predefinito, la sezione **Utenti,** gruppi e domini non è disponibile (il criterio si applica a tutti) e non è possibile rinominare il criterio.</span><span class="sxs-lookup"><span data-stu-id="3ae04-210">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="3ae04-211">Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="3ae04-211">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="3ae04-212">Abilitare o disabilitare i criteri anti-phishing personalizzati</span><span class="sxs-lookup"><span data-stu-id="3ae04-212">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="3ae04-213">Non è possibile disabilitare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="3ae04-213">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="3ae04-214">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-214">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3ae04-215">Nella pagina **Anti-phishing** selezionare un criterio personalizzato nell'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="3ae04-215">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="3ae04-216">Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato è presente uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ae04-216">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="3ae04-217">**Criterio disattivato**: per attivare il criterio, fare clic su ![Attiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Attiva** .</span><span class="sxs-lookup"><span data-stu-id="3ae04-217">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="3ae04-218">**Criterio attivato**: per disattivare il criterio, fare clic su ![Disattiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-218">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="3ae04-219">Nella finestra di dialogo di conferma visualizzata fare clic su **Attiva** o **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-219">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="3ae04-220">Fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.</span><span class="sxs-lookup"><span data-stu-id="3ae04-220">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="3ae04-221">Tornare alla pagina dei criteri principale, il valore **Stato** del criterio sarà **Attivato** o **Disattivato**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-221">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="3ae04-222">Impostare la priorità dei criteri anti-phishing personalizzati</span><span class="sxs-lookup"><span data-stu-id="3ae04-222">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="3ae04-223">Per impostazione predefinita, ai criteri anti-phishing viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="3ae04-223">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="3ae04-224">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="3ae04-224">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="3ae04-225">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="3ae04-225">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="3ae04-226">Per modificare la priorità di un criterio, fare clic su **Aumenta priorità** o **Riduci priorità** nelle proprietà del criterio. Non è possibile modificare direttamente il valore **Priorità** nel portale di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3ae04-226">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="3ae04-227">La modifica di priorità di un criterio è utile solo se si hanno più criteri.</span><span class="sxs-lookup"><span data-stu-id="3ae04-227">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="3ae04-228">**Note**:</span><span class="sxs-lookup"><span data-stu-id="3ae04-228">**Notes**:</span></span>

- <span data-ttu-id="3ae04-229">Nel portale Microsoft 365 Defender, è possibile modificare la priorità del criterio anti-phishing solo dopo aver creato il criterio.</span><span class="sxs-lookup"><span data-stu-id="3ae04-229">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="3ae04-230">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phish (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="3ae04-230">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="3ae04-231">I criteri anti-phishing vengono elaborati nell'ordine in cui vengono visualizzati (il primo criterio ha il **valore Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="3ae04-231">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="3ae04-232">Il criterio anti-phishing predefinito ha il valore di priorità **Lowest** e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="3ae04-232">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="3ae04-233">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-233">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3ae04-234">Nella pagina **Anti-phishing** selezionare un criterio personalizzato nell'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="3ae04-234">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="3ae04-235">Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato viene visualizzato **Aumenta priorità** o **Riduci priorità** in base al valore di priorità corrente e al numero di criteri personalizzati:</span><span class="sxs-lookup"><span data-stu-id="3ae04-235">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="3ae04-236">Per il criterio con **valore Priority** **0 è** disponibile solo **l'opzione Riduci** priorità.</span><span class="sxs-lookup"><span data-stu-id="3ae04-236">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="3ae04-237">Il criterio con il valore **Di priorità** più basso (ad esempio, **3)** ha solo l'opzione **Aumenta** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="3ae04-237">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="3ae04-238">Se si dispone di tre o più criteri, per i  criteri tra i valori di priorità più alta e più bassa sono disponibili le opzioni Aumenta priorità e **Riduci** priorità.</span><span class="sxs-lookup"><span data-stu-id="3ae04-238">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="3ae04-239">Fare clic![ sull’icona Aumenta priorità](../../media/m365-cc-sc-increase-icon.png) **Aumenta priorità** o ![sull’icona Riduci priorità](../../media/m365-cc-sc-decrease-icon.png) **Riduci priorità** per modificare il valore **Priorità**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-239">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="3ae04-240">Al termine, fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.</span><span class="sxs-lookup"><span data-stu-id="3ae04-240">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="3ae04-241">Utilizzare il portale Microsoft 365 Defender per rimuovere criteri anti-phishing personalizzati</span><span class="sxs-lookup"><span data-stu-id="3ae04-241">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="3ae04-242">Quando si utilizza il portale Microsoft 365 Defender per rimuovere un criterio anti-phishing personalizzato, la regola anti-phishing e il criterio anti-phishing corrispondente vengono eliminati entrambi.</span><span class="sxs-lookup"><span data-stu-id="3ae04-242">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="3ae04-243">Non è possibile rimuovere il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="3ae04-243">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="3ae04-244">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-244">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="3ae04-245">Nella pagina **Anti-phishing** selezionare un criterio personalizzato nell'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="3ae04-245">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="3ae04-246">Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato fare clic![ sull'icona Altre azioni](../../media/m365-cc-sc-more-actions-icon.png) **Altre azioni** \> ![Icona Elimina criterio](../../media/m365-cc-sc-delete-icon.png) **Elimina criterio**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-246">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="3ae04-247">Nella finestra di dialogo di conferma che viene visualizzata fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-247">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="3ae04-248">Utilizzare Exchange Online PowerShell per configurare i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="3ae04-248">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="3ae04-249">Come descritto in precedenza, un criterio anti-phishing è costituito da un criterio anti-phishing e da una regola anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="3ae04-249">As previously described, an anti-phishing policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="3ae04-250">In Exchange Online PowerShell, è evidente la differenza tra i criteri anti-phish e le regole anti-phish.</span><span class="sxs-lookup"><span data-stu-id="3ae04-250">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="3ae04-251">È possibile gestire i criteri anti-phish utilizzando i cmdlet **\* -AntiPhishPolicy** e gestire le regole anti-phish utilizzando i cmdlet **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-251">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="3ae04-252">In PowerShell, si crea prima il criterio anti-phish, quindi si crea la regola anti-phish che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="3ae04-252">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="3ae04-253">In PowerShell, le impostazioni dei criteri anti-phish e della regola anti-phish vengono modificate separatamente.</span><span class="sxs-lookup"><span data-stu-id="3ae04-253">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="3ae04-254">Quando si rimuove un criterio anti-phish da PowerShell, la regola anti-phish corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="3ae04-254">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

> [!NOTE]
> <span data-ttu-id="3ae04-255">Le procedure di PowerShell seguenti non sono disponibili nelle organizzazioni EOP autonome che usano Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ae04-255">The following PowerShell procedures aren't available in standalone EOP organizations using Exchange Online Protection PowerShell.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="3ae04-256">Utilizzare PowerShell per creare criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="3ae04-256">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="3ae04-257">La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="3ae04-257">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="3ae04-258">Creare i criteri anti-phish.</span><span class="sxs-lookup"><span data-stu-id="3ae04-258">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="3ae04-259">Creare la regola anti-phish che specifica il criterio anti-phish a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="3ae04-259">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="3ae04-260">**Note**:</span><span class="sxs-lookup"><span data-stu-id="3ae04-260">**Notes**:</span></span>

- <span data-ttu-id="3ae04-261">È possibile creare una nuova regola anti-phish e assegnarle un criterio anti-phish esistente e non associazione.</span><span class="sxs-lookup"><span data-stu-id="3ae04-261">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="3ae04-262">Una regola anti-phish non può essere associata a più di un criterio anti-phish.</span><span class="sxs-lookup"><span data-stu-id="3ae04-262">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>

- <span data-ttu-id="3ae04-263">È possibile configurare le impostazioni seguenti nei nuovi criteri anti-phish in PowerShell che non sono disponibili nel portale di Microsoft 365 Defender fino a quando non si crea il criterio:</span><span class="sxs-lookup"><span data-stu-id="3ae04-263">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>

  - <span data-ttu-id="3ae04-264">Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="3ae04-264">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="3ae04-265">Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-265">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>

- <span data-ttu-id="3ae04-266">Un nuovo criterio anti-phish creato in PowerShell non è visibile nel portale di Microsoft 365 Defender finché non si assegna il criterio a una regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="3ae04-266">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="3ae04-267">Passaggio 1: Usare PowerShell per creare un criterio anti-phish</span><span class="sxs-lookup"><span data-stu-id="3ae04-267">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="3ae04-268">Per creare un criterio anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3ae04-268">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>] [-EnableViaTag <$true | $false>]
```

<span data-ttu-id="3ae04-269">In questo esempio viene creato un criterio anti-phish denominato Research Quarantine con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ae04-269">This example creates an anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="3ae04-270">La descrizione è: Criteri del reparto di ricerca.</span><span class="sxs-lookup"><span data-stu-id="3ae04-270">The description is: Research department policy.</span></span>
- <span data-ttu-id="3ae04-271">Modifica l'azione predefinita per lo spoofing in Quarantena.</span><span class="sxs-lookup"><span data-stu-id="3ae04-271">Changes the default action for spoofing to Quarantine.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="3ae04-272">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="3ae04-272">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="3ae04-273">Passaggio 2: Usare PowerShell per creare una regola anti-phish</span><span class="sxs-lookup"><span data-stu-id="3ae04-273">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="3ae04-274">Per creare una regola anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3ae04-274">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="3ae04-275">In questo esempio viene creata una regola anti-phish denominata Research Department con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ae04-275">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="3ae04-276">La regola è associata al criterio anti-phish denominato Quarantena ricerche.</span><span class="sxs-lookup"><span data-stu-id="3ae04-276">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="3ae04-277">La regola viene applicata ai membri del gruppo denominato Research Department.</span><span class="sxs-lookup"><span data-stu-id="3ae04-277">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="3ae04-278">Poiché non si utilizza il parametro _Priority,_ viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="3ae04-278">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="3ae04-279">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="3ae04-279">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="3ae04-280">Usare PowerShell per visualizzare i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="3ae04-280">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="3ae04-281">Per visualizzare i criteri anti-phish esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3ae04-281">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3ae04-282">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri anti-phish insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="3ae04-282">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="3ae04-283">In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio anti-phish denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="3ae04-283">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="3ae04-284">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="3ae04-284">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="3ae04-285">Usare PowerShell per visualizzare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="3ae04-285">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="3ae04-286">Per visualizzare le regole anti-phish esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3ae04-286">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="3ae04-287">In questo esempio viene restituito un elenco riepilogativo di tutte le regole anti-phish insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="3ae04-287">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="3ae04-288">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ae04-288">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="3ae04-289">In questo esempio vengono restituiti tutti i valori delle proprietà per la regola anti-phish denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="3ae04-289">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="3ae04-290">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="3ae04-290">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="3ae04-291">Utilizzare PowerShell per modificare i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="3ae04-291">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="3ae04-292">Oltre agli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio anti-phish in PowerShell come quando si crea un criterio come descritto in [Passaggio 1: Utilizzare PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) per creare un criterio anti-phish più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3ae04-292">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create a policy as described in [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) earlier in this article.</span></span>

- <span data-ttu-id="3ae04-293">L'opzione _MakeDefault_ che trasforma il criterio specificato nel  criterio predefinito (applicato a tutti, sempre con priorità minima e non è possibile eliminarlo) è disponibile solo quando si modifica un criterio anti-phish in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ae04-293">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>
- <span data-ttu-id="3ae04-294">Non è possibile rinominare un criterio anti-phish (il cmdlet **Set-AntiPhishPolicy** non dispone di _alcun parametro Name)._</span><span class="sxs-lookup"><span data-stu-id="3ae04-294">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="3ae04-295">Quando si rinomina un criterio anti-phishing nel portale Microsoft 365 Defender, si rinomina solo la regola _anti-phishing._</span><span class="sxs-lookup"><span data-stu-id="3ae04-295">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="3ae04-296">Per modificare un criterio anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3ae04-296">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="3ae04-297">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="3ae04-297">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="3ae04-298">Utilizzare PowerShell per modificare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="3ae04-298">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="3ae04-299">L'unica impostazione non disponibile quando si modifica una regola anti-phish in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="3ae04-299">The only setting that's not available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="3ae04-300">Per abilitare o disabilitare le regole anti-phish esistenti, vedi la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="3ae04-300">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="3ae04-301">In caso contrario, le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione Passaggio 2: utilizzare PowerShell per creare una regola [anti-phish](#step-2-use-powershell-to-create-an-anti-phish-rule) in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="3ae04-301">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="3ae04-302">Per modificare una regola anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3ae04-302">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="3ae04-303">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="3ae04-303">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="3ae04-304">Usare PowerShell per abilitare o disabilitare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="3ae04-304">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="3ae04-305">L'abilitazione o la disabilitazione di una regola anti-phishing in PowerShell abilita o disabilita l'intero criterio anti-phishing (la regola anti-phishing e il criterio anti-phishing assegnato).</span><span class="sxs-lookup"><span data-stu-id="3ae04-305">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="3ae04-306">Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="3ae04-306">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="3ae04-307">Per abilitare o disabilitare una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3ae04-307">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="3ae04-308">In questo esempio viene disabilitata la regola anti-phish denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="3ae04-308">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3ae04-309">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="3ae04-309">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3ae04-310">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="3ae04-310">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="3ae04-311">Usare PowerShell per impostare la priorità delle regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="3ae04-311">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="3ae04-p131">Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole predefinite, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole (priorità da 0 a 4) e si modifica la priorità di una regola a 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="3ae04-p131">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="3ae04-317">Per impostare la priorità di una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3ae04-317">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="3ae04-p132">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="3ae04-p132">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="3ae04-320">**Note**:</span><span class="sxs-lookup"><span data-stu-id="3ae04-320">**Notes**:</span></span>

- <span data-ttu-id="3ae04-321">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare invece il parametro _Priority_ nel cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-321">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>
- <span data-ttu-id="3ae04-322">Il criterio anti-phish predefinito non dispone di una regola anti-phish corrispondente e ha sempre il valore di priorità non modificabile **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="3ae04-322">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="3ae04-323">Usare PowerShell per rimuovere i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="3ae04-323">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="3ae04-324">Quando si utilizza PowerShell per rimuovere un criterio anti-phish, la regola anti-phish corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="3ae04-324">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="3ae04-325">Per rimuovere un criterio anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3ae04-325">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="3ae04-326">In questo esempio viene rimosso il criterio anti-phish denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="3ae04-326">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="3ae04-327">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="3ae04-327">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="3ae04-328">Usare PowerShell per rimuovere le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="3ae04-328">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="3ae04-329">Quando si utilizza PowerShell per rimuovere una regola anti-phish, il criterio anti-phish corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="3ae04-329">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="3ae04-330">Per rimuovere una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3ae04-330">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="3ae04-331">In questo esempio viene rimossa la regola anti-phish denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="3ae04-331">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="3ae04-332">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="3ae04-332">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="3ae04-333">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="3ae04-333">How do you know these procedures worked?</span></span>

<span data-ttu-id="3ae04-334">Per verificare la corretta configurazione dei criteri anti-phishing in EOP, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3ae04-334">To verify that you've successfully configured anti-phishing policies in EOP, do any of the following steps:</span></span>

- <span data-ttu-id="3ae04-335">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-335">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="3ae04-336">Verificare l'elenco dei criteri, i **relativi valori status** e i relativi valori **Priority.**</span><span class="sxs-lookup"><span data-stu-id="3ae04-336">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="3ae04-337">Per visualizzare altri dettagli, selezionare il criterio dall'elenco facendo clic sul nome e visualizzando i dettagli nel riquadro a comparsa visualizzato.</span><span class="sxs-lookup"><span data-stu-id="3ae04-337">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="3ae04-338">In Exchange Online PowerShell, sostituire con il nome del criterio o della regola, eseguire il \<Name\> comando seguente e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="3ae04-338">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
