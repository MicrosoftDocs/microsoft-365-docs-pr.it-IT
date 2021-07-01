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
ms.openlocfilehash: 71baf947c5834e2eb4b8ef62af69da77ea5bd090
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230044"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="33da3-103">Configurare i criteri anti-phishing in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="33da3-103">Configure anti-phishing policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="33da3-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="33da3-104">**Applies to**</span></span>
- [<span data-ttu-id="33da3-105">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="33da3-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="33da3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33da3-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="33da3-107">I criteri anti-phishing in [Microsoft Defender per Office 365](defender-for-office-365.md) possono aiutare a proteggere l'organizzazione da attacchi di phishing dannosi basati sulla rappresentazione e da altri tipi di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="33da3-107">Anti-phishing policies in [Microsoft Defender for Office 365](defender-for-office-365.md) can help protect your organization from malicious impersonation-based phishing attacks and other types of phishing attacks.</span></span> <span data-ttu-id="33da3-108">Per ulteriori informazioni sulle differenze tra i criteri anti-phishing in Exchange Online Protection (EOP) e i criteri anti-phishing in Microsoft Defender per Office 365, vedere [Protezione anti-phishing.](anti-phishing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="33da3-108">For more information about the differences between anti-phishing policies in Exchange Online Protection (EOP) and anti-phishing policies in Microsoft Defender for Office 365, see [Anti-phishing protection](anti-phishing-protection.md).</span></span>

<span data-ttu-id="33da3-109">Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="33da3-109">Admins can view, edit, and configure (but not delete) the default anti-phishing policy.</span></span> <span data-ttu-id="33da3-110">Per una maggiore granularità, è inoltre possibile creare criteri anti-phishing personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="33da3-110">For greater granularity, you can also create custom anti-phishing policies that apply to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="33da3-111">I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).</span><span class="sxs-lookup"><span data-stu-id="33da3-111">Custom policies always take precedence over the default policy, but you can change the priority (running order) of your custom policies.</span></span>

<span data-ttu-id="33da3-112">È possibile configurare i criteri anti-phishing in Defender per Office 365 nel portale di Microsoft 365 Defender o in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33da3-112">You can configure anti-phishing policies in Defender for Office 365 in the Microsoft 365 Defender portal or in Exchange Online PowerShell.</span></span>

<span data-ttu-id="33da3-113">Per informazioni sulla configurazione dei criteri anti-phishing più limitati disponibili in Exchange Online Protection (ovvero le organizzazioni senza Defender per Office 365), vedere [Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="33da3-113">For information about configuring the more limited in anti-phishing policies that are available in Exchange Online Protection (that is, organizations without Defender for Office 365), see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="33da3-114">Gli elementi di base di un criterio anti-phishing sono:</span><span class="sxs-lookup"><span data-stu-id="33da3-114">The basic elements of an anti-phishing policy are:</span></span>

- <span data-ttu-id="33da3-115">**Il criterio anti-phishing**: Specifica le protezioni anti-phishing da abilitare o disabilitare e le azioni da applicare.</span><span class="sxs-lookup"><span data-stu-id="33da3-115">**The anti-phish policy**: Specifies the phishing protections to enable or disable, and the actions to apply options.</span></span>
- <span data-ttu-id="33da3-116">**La regola anti-phish**: Specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phish.</span><span class="sxs-lookup"><span data-stu-id="33da3-116">**The anti-phish rule**: Specifies the priority and recipient filters (who the policy applies to) for an anti-phish policy.</span></span>

<span data-ttu-id="33da3-117">La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri anti-phishing nel portale Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="33da3-117">The difference between these two elements isn't obvious when you manage anti-phishing policies in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="33da3-118">Quando crei un criterio, stai creando una regola anti-phish e il criterio anti-phish associato contemporaneamente usando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="33da3-118">When you create a policy, you're actually creating an anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="33da3-119">Quando si modifica un criterio, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="33da3-119">When you modify a policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the anti-phish rule.</span></span> <span data-ttu-id="33da3-120">Tutte le altre impostazioni modificano il criterio anti-phish associato.</span><span class="sxs-lookup"><span data-stu-id="33da3-120">All other settings modify the associated anti-phish policy.</span></span>
- <span data-ttu-id="33da3-121">Quando si rimuove un criterio, vengono rimossi la regola anti-phish e il criterio anti-phish associato.</span><span class="sxs-lookup"><span data-stu-id="33da3-121">When you remove a policy, the anti-phish rule and the associated anti-phish policy are removed.</span></span>

<span data-ttu-id="33da3-122">In Exchange Online PowerShell, il criterio e la regola vengono gestiti separatamente.</span><span class="sxs-lookup"><span data-stu-id="33da3-122">In Exchange Online PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="33da3-123">Per ulteriori informazioni, vedere la sezione [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="33da3-123">For more information, see the [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) section later in this article.</span></span>

<span data-ttu-id="33da3-124">Ogni defender per Office 365 ha un criterio anti-phishing predefinito denominato Office365 AntiPhish Default con queste proprietà:</span><span class="sxs-lookup"><span data-stu-id="33da3-124">Every Defender for Office 365 organization has a built-in anti-phishing policy named Office365 AntiPhish Default that has these properties:</span></span>

- <span data-ttu-id="33da3-125">Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se al criterio non è associata alcuna regola anti-phish (filtri destinatari).</span><span class="sxs-lookup"><span data-stu-id="33da3-125">The policy is applied to all recipients in the organization, even though there's no anti-phish rule (recipient filters) associated with the policy.</span></span>
- <span data-ttu-id="33da3-126">Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo).</span><span class="sxs-lookup"><span data-stu-id="33da3-126">The policy has the custom priority value **Lowest** that you can't modify (the policy is always applied last).</span></span> <span data-ttu-id="33da3-127">Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="33da3-127">Any custom policies that you create always have a higher priority.</span></span>
- <span data-ttu-id="33da3-128">Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="33da3-128">The policy is the default policy (the **IsDefault** property has the value `True`), and you can't delete the default policy.</span></span>

<span data-ttu-id="33da3-129">Per aumentare l'efficacia della protezione anti-phishing in Defender per Office 365, è possibile creare criteri anti-phishing personalizzati con impostazioni più rigide applicate a utenti o gruppi di utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="33da3-129">To increase the effectiveness of anti-phishing protection in Defender for Office 365, you can create custom anti-phishing policies with stricter settings that are applied to specific users or groups of users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="33da3-130">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="33da3-130">What do you need to know before you begin?</span></span>

- <span data-ttu-id="33da3-131">Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="33da3-131">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="33da3-132">Per passare direttamente alla pagina **Anti-phishing,** utilizzare <https://security.microsoft.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="33da3-132">To go directly to the **Anti-phishing** page, use <https://security.microsoft.com/antiphishing>.</span></span>

- <span data-ttu-id="33da3-133">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="33da3-133">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="33da3-134">Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="33da3-134">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="33da3-135">Per aggiungere, modificare ed eliminare criteri anti-phishing, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="33da3-135">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="33da3-136">Per l'accesso in sola lettura ai criteri anti-phishing, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="33da3-136">For read-only access to anti-phishing policies, you need to be a member of the **Global Reader** or **Security Reader** role groups<sup>\*</sup>.</span></span>

  <span data-ttu-id="33da3-137">Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="33da3-137">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="33da3-138">**Note**:</span><span class="sxs-lookup"><span data-stu-id="33da3-138">**Notes**:</span></span>

  - <span data-ttu-id="33da3-139">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33da3-139">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="33da3-140">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="33da3-140">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="33da3-141">Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="33da3-141">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="33da3-142">Per le impostazioni consigliate per i criteri anti-phishing in Defender per Office 365, vedi [Criteri anti-phishing in Defender per Office 365 impostazioni](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="33da3-142">For our recommended settings for anti-phishing policies in Defender for Office 365, see [Anti-phishing policy in Defender for Office 365 settings](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

- <span data-ttu-id="33da3-143">Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.</span><span class="sxs-lookup"><span data-stu-id="33da3-143">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="33da3-144">Per informazioni su dove vengono applicati i criteri anti-phishing nella pipeline di filtro, vedere [Order and precedence of email protection.](how-policies-and-protections-are-combined.md)</span><span class="sxs-lookup"><span data-stu-id="33da3-144">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a><span data-ttu-id="33da3-145">Utilizzare il portale Microsoft 365 Defender per creare criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="33da3-145">Use the Microsoft 365 Defender portal to create anti-phishing policies</span></span>

<span data-ttu-id="33da3-146">La creazione di un criterio anti-phishing personalizzato nel portale di Microsoft 365 Defender crea la regola anti-phishing e il criterio anti-phishing associato contemporaneamente utilizzando lo stesso nome per entrambi.</span><span class="sxs-lookup"><span data-stu-id="33da3-146">Creating a custom anti-phishing policy in the Microsoft 365 Defender portal creates the anti-phish rule and the associated anti-phish policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="33da3-147">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="33da3-147">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33da3-148">Nella pagina **Anti-phishing** fare clic su ![ Crea icona ](../../media/m365-cc-sc-create-icon.png) **Crea**.</span><span class="sxs-lookup"><span data-stu-id="33da3-148">On the **Anti-phishing** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png) **Create**.</span></span>

3. <span data-ttu-id="33da3-149">Viene aperta la creazione guidata criteri.</span><span class="sxs-lookup"><span data-stu-id="33da3-149">The policy wizard opens.</span></span> <span data-ttu-id="33da3-150">Nella pagina **Nome criterio** configurare queste impostazioni:</span><span class="sxs-lookup"><span data-stu-id="33da3-150">On the **Policy name** page, configure these settings:</span></span>
   - <span data-ttu-id="33da3-151">**Nome**: immettere un nome univoco descrittivo per il criterio.</span><span class="sxs-lookup"><span data-stu-id="33da3-151">**Name**: Enter a unique, descriptive name for the policy.</span></span>
   - <span data-ttu-id="33da3-152">**Descrizione**: immettere una descrizione opzionale per il criterio.</span><span class="sxs-lookup"><span data-stu-id="33da3-152">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="33da3-153">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="33da3-153">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="33da3-154">Nella pagina **Utenti, gruppi e domini** visualizzata identificare i destinatari interni a cui si applicano i criteri (condizioni del destinatario):</span><span class="sxs-lookup"><span data-stu-id="33da3-154">On the **Users, groups, and domains** page that appears, identify the internal recipients that the policy applies to (recipient conditions):</span></span>
   - <span data-ttu-id="33da3-155">**Utenti**: la cassette postali specificate, utenti di posta o contatti di posta specificati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="33da3-155">**Users**: The specified mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="33da3-156">**Gruppi**: i gruppi di distribuzione specificati, gruppi di sicurezza abilitati alla posta elettronica o gruppi di Microsoft 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="33da3-156">**Groups**: The specified distribution groups, mail-enabled security groups, or Microsoft 365 Groups in your organization.</span></span>
   - <span data-ttu-id="33da3-157">**Domini**: tutti i destinatari nei domini specificati [accettati](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="33da3-157">**Domains**: All recipients in the specified [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in your organization.</span></span>

   <span data-ttu-id="33da3-158">Fare clic nella casella appropriata, iniziare a digitare un valore e selezionare il valore desiderato nei risultati.</span><span class="sxs-lookup"><span data-stu-id="33da3-158">Click in the appropriate box, start typing a value, and select the value that you want from the results.</span></span> <span data-ttu-id="33da3-159">Ripetere questa procedura tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="33da3-159">Repeat this process as many times as necessary.</span></span> <span data-ttu-id="33da3-160">Per rimuovere un valore esistente, fare clic su Rimuovi</span><span class="sxs-lookup"><span data-stu-id="33da3-160">To remove an existing value, click remove</span></span> ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="33da3-162">accanto al valore.</span><span class="sxs-lookup"><span data-stu-id="33da3-162">next to the value.</span></span>

   <span data-ttu-id="33da3-163">Per utenti o gruppi è possibile usare la maggior parte degli identificatori, ad esempio nome, nome visualizzato, alias, indirizzo di posta elettronica, nome dell'account e così via, ma il nome visualizzato corrispondente viene visualizzato nei risultati.</span><span class="sxs-lookup"><span data-stu-id="33da3-163">For users or groups, you can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span> <span data-ttu-id="33da3-164">Per gli utenti, immettere un asterisco (\*) da solo per visualizzare tutti i valori disponibili.</span><span class="sxs-lookup"><span data-stu-id="33da3-164">For users, enter an asterisk (\*) by itself to see all available values.</span></span>

   <span data-ttu-id="33da3-165">Più valori della stessa condizione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_).</span><span class="sxs-lookup"><span data-stu-id="33da3-165">Multiple values in the same condition use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="33da3-166">Condizioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).</span><span class="sxs-lookup"><span data-stu-id="33da3-166">Different conditions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   - <span data-ttu-id="33da3-167">**Escludere questi utenti, gruppi e domini**: per aggiungere eccezioni per i destinatari interni a cui si applicano i criteri (eccezione destinatari), selezionare questa opzione e configurare le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="33da3-167">**Exclude these users, groups, and domains**: To add exceptions for the internal recipients that the policy applies to (recpient exceptions), select this option and configure the exceptions.</span></span> <span data-ttu-id="33da3-168">Impostazioni e comportamento sono equivalenti alle condizioni.</span><span class="sxs-lookup"><span data-stu-id="33da3-168">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="33da3-169">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="33da3-169">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="33da3-170">Nella pagina **Soglia di & phishing** visualizzata configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33da3-170">On the **Phishing threshold & protection** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="33da3-171">**Soglia posta elettronica di phishing**: usa il dispositivo di scorrimento per selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="33da3-171">**Phishing email threshold**: Use the slider to select one of the following values:</span></span>
     - <span data-ttu-id="33da3-172">**1 - Standard** (questo è il valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="33da3-172">**1 - Standard** (This is the default value.)</span></span>
     - <span data-ttu-id="33da3-173">**2 - Aggressivo**</span><span class="sxs-lookup"><span data-stu-id="33da3-173">**2 - Aggressive**</span></span>
     - <span data-ttu-id="33da3-174">**3 - Più aggressivo**</span><span class="sxs-lookup"><span data-stu-id="33da3-174">**3 - More aggressive**</span></span>
     - <span data-ttu-id="33da3-175">**4 - Più aggressivo**</span><span class="sxs-lookup"><span data-stu-id="33da3-175">**4 - Most aggressive**</span></span>

     <span data-ttu-id="33da3-176">Per ulteriori informazioni, vedere [Soglie avanzate di phishing nei criteri anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="33da3-176">For more information, see [Advanced phishing thresholds in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

   - <span data-ttu-id="33da3-177">**Rappresentazione:** queste impostazioni sono una condizione per il criterio che identifica mittenti specifici da cercare (singolarmente o per dominio) nell'indirizzo mittente dei messaggi in ingresso.</span><span class="sxs-lookup"><span data-stu-id="33da3-177">**Impersonation**: These settings are a condition for the policy that identifies specific senders to look for (individually or by domain) in the From address of inbound messages.</span></span> <span data-ttu-id="33da3-178">Per ulteriori informazioni, vedere [Impostazioni di rappresentazione nei criteri anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="33da3-178">For more information, see [Impersonation settings in anti-phishing policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span>

     > [!NOTE]
     >
     > - <span data-ttu-id="33da3-179">In ogni criterio anti-phishing è possibile specificare un massimo di 350 utenti protetti (indirizzi di posta elettronica del mittente).</span><span class="sxs-lookup"><span data-stu-id="33da3-179">In each anti-phishing policy, you can specify a maximum of 350 protected users (sender email addresses).</span></span> <span data-ttu-id="33da3-180">Non è possibile specificare lo stesso utente protetto in più criteri.</span><span class="sxs-lookup"><span data-stu-id="33da3-180">You can't specify the same protected user in multiple policies.</span></span>
     > - <span data-ttu-id="33da3-181">La protezione della rappresentazione dell'utente non funziona se il mittente e il destinatario hanno precedentemente comunicato tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="33da3-181">User impersonation protection does not work if the sender and recipient have previously communicated via email.</span></span> <span data-ttu-id="33da3-182">Se il mittente e il destinatario non hanno mai comunicato tramite posta elettronica, il messaggio verrà identificato come tentativo di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="33da3-182">If the sender and recipient have never communicated via email, the message will be identified as an impersonation attempt.</span></span>

     - <span data-ttu-id="33da3-183">**Consenti agli utenti di proteggere**: il valore predefinito è disattivato (non selezionato).</span><span class="sxs-lookup"><span data-stu-id="33da3-183">**Enable users to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="33da3-184">Per attivarla, selezionare la casella di controllo e quindi fare clic sul collegamento Gestisci **mittenti (nn)** visualizzato.</span><span class="sxs-lookup"><span data-stu-id="33da3-184">To turn it on, select the check box, and then click the **Manage (nn) sender(s)** link that appears.</span></span>

       <span data-ttu-id="33da3-185">Nel riquadro **a comparsa Gestisci mittenti** per la protezione della rappresentazione visualizzato eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="33da3-185">In the **Manage senders for impersonation protection** flyout that appears, do the following steps:</span></span>

       - <span data-ttu-id="33da3-186">**Mittenti interni**: fare clic ![ su Aggiungi icona interna Seleziona ](../../media/m365-cc-sc-add-internal-icon.png) **interno.**</span><span class="sxs-lookup"><span data-stu-id="33da3-186">**Internal senders**: Click ![Add internal icon](../../media/m365-cc-sc-add-internal-icon.png) **Select internal**.</span></span> <span data-ttu-id="33da3-187">Nel riquadro **a comparsa Aggiungi mittenti** interni visualizzato fare clic nella casella e selezionare un utente interno nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="33da3-187">In the **Add internal senders** flyout that appears, click in the box and select an internal user from the list.</span></span> <span data-ttu-id="33da3-188">È possibile filtrare l'elenco digitando l'utente e quindi selezionandolo dai risultati.</span><span class="sxs-lookup"><span data-stu-id="33da3-188">You can filter the list by typing the user, and then selecting the user from the results.</span></span> <span data-ttu-id="33da3-189">È possibile utilizzare la maggior parte degli identificatori (nome, nome visualizzato, alias, indirizzo di posta elettronica, nome account e così via), ma il nome visualizzato corrispondente viene visualizzato nei risultati.</span><span class="sxs-lookup"><span data-stu-id="33da3-189">You can use most identifiers (name, display name, alias, email address, account name, etc.), but the corresponding display name is shown in the results.</span></span>

         <span data-ttu-id="33da3-190">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="33da3-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="33da3-191">Per rimuovere un valore esistente, fare clic su Rimuovi</span><span class="sxs-lookup"><span data-stu-id="33da3-191">To remove an existing value, click remove</span></span> ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="33da3-193">accanto al valore.</span><span class="sxs-lookup"><span data-stu-id="33da3-193">next to the value.</span></span>

         <span data-ttu-id="33da3-194">Al termine, fare clic su **Aggiungi**</span><span class="sxs-lookup"><span data-stu-id="33da3-194">When you're finished, click **Add**</span></span>

       - <span data-ttu-id="33da3-195">**Mittenti esterni**: fare clic ![ su Aggiungi icona esterna Seleziona ](../../media/m365-cc-sc-create-icon.png) **esterno.**</span><span class="sxs-lookup"><span data-stu-id="33da3-195">**External senders**: Click ![Add external icon](../../media/m365-cc-sc-create-icon.png) **Select external**.</span></span> <span data-ttu-id="33da3-196">Nel riquadro a comparsa Add **external senders** that appears, enter a display name in the **Add a name** box and an email address in the Add a **vaild email** box, and then click **Add**.</span><span class="sxs-lookup"><span data-stu-id="33da3-196">In the **Add external senders** flyout that appears, enter a display name in the **Add a name** box and an email address in the **Add a vaild email** box, and then click **Add**.</span></span>

         <span data-ttu-id="33da3-197">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="33da3-197">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="33da3-198">Per rimuovere un valore esistente, fare clic su Rimuovi</span><span class="sxs-lookup"><span data-stu-id="33da3-198">To remove an existing value, click remove</span></span> ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) <span data-ttu-id="33da3-200">accanto al valore.</span><span class="sxs-lookup"><span data-stu-id="33da3-200">next to the value.</span></span>

         <span data-ttu-id="33da3-201">Al termine, fare clic su **Aggiungi**</span><span class="sxs-lookup"><span data-stu-id="33da3-201">When you're finished, click **Add**</span></span>

       <span data-ttu-id="33da3-202">Tornare al **riquadro a** comparsa Gestisci mittenti per la rappresentazione, è possibile rimuovere le voci selezionando una o più voci dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="33da3-202">Back on the **Manage senders for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="33da3-203">È possibile cercare voci utilizzando la casella Di ricerca ![ icona ](../../media/m365-cc-sc-create-icon.png) **di** ricerca.</span><span class="sxs-lookup"><span data-stu-id="33da3-203">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="33da3-204">Dopo aver selezionato almeno una voce, viene visualizzata l'icona Rimuovi utenti selezionati Icona Rimuovi utenti selezionati, che è possibile utilizzare per rimuovere ![ ](../../media/m365-cc-sc-remove-selected-users-icon.png)  le voci selezionate.</span><span class="sxs-lookup"><span data-stu-id="33da3-204">After you select at least one entry, the ![Remove selected users icon](../../media/m365-cc-sc-remove-selected-users-icon.png) **Remove selected users** icon appears, which you can use to remove the selected entries.</span></span>

       <span data-ttu-id="33da3-205">Al termine, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="33da3-205">When you're finished, click **Done**.</span></span>

     - <span data-ttu-id="33da3-206">**Abilita domini da proteggere**: il valore predefinito è disattivato (non selezionato).</span><span class="sxs-lookup"><span data-stu-id="33da3-206">**Enable domains to protect**: The default value is off (not selected).</span></span> <span data-ttu-id="33da3-207">Per attivarla, selezionare la casella di controllo e quindi configurare una o entrambe le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33da3-207">To turn it on, select the check box, and then configure one or both of the following settings that appear:</span></span>
       - <span data-ttu-id="33da3-208">**Includi i domini di cui sono proprietario:** per attivare questa impostazione, selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="33da3-208">**Include the domains I own**: To turn this setting on, select the check box.</span></span> <span data-ttu-id="33da3-209">Per visualizzare i domini di cui si è proprietari, fare **clic su Visualizza domini.**</span><span class="sxs-lookup"><span data-stu-id="33da3-209">To view the domains that you own, click **View my domains**.</span></span>
       - <span data-ttu-id="33da3-210">**Includi domini personalizzati:** per attivare questa impostazione, selezionare la casella di controllo e quindi fare clic sul collegamento Gestisci **(nn)** dominio personalizzato visualizzato.</span><span class="sxs-lookup"><span data-stu-id="33da3-210">**Include custom domains**: To turn this setting on, select the check box, and then click the **Manage (nn) custom domain(s)** link that appears.</span></span> <span data-ttu-id="33da3-211">Nel riquadro **a comparsa Gestisci domini personalizzati per la protezione della** rappresentazione visualizzato fare clic su Aggiungi domini icona Aggiungi ![ ](../../media/m365-cc-sc-create-icon.png) **domini**.</span><span class="sxs-lookup"><span data-stu-id="33da3-211">In the **Manage custom domains for impersonation protection** flyout that appears, click ![Add domains icon](../../media/m365-cc-sc-create-icon.png) **Add domains**.</span></span>

         <span data-ttu-id="33da3-212">Nel riquadro a comparsa **Aggiungi** domini personalizzati visualizzato fare clic nella casella **Dominio,** immettere un valore e quindi premere INVIO o selezionare il valore visualizzato sotto la casella.</span><span class="sxs-lookup"><span data-stu-id="33da3-212">In the **Add custom domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="33da3-213">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="33da3-213">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="33da3-214">Per rimuovere un valore esistente, fare clic su ![Rimuovi icona](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.</span><span class="sxs-lookup"><span data-stu-id="33da3-214">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

         <span data-ttu-id="33da3-215">Al termine, fare clic su **Aggiungi domini**</span><span class="sxs-lookup"><span data-stu-id="33da3-215">When you're finished, click **Add domains**</span></span>

         > [!NOTE]
         > <span data-ttu-id="33da3-216">È possibile avere un massimo di 50 domini in tutti i criteri anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="33da3-216">You can have a maximum of 50 domains in all anti-phishing policies.</span></span>

       <span data-ttu-id="33da3-217">Tornare al **riquadro a** comparsa Gestisci domini personalizzati per la rappresentazione, è possibile rimuovere le voci selezionando una o più voci dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="33da3-217">Back on the **Manage custom domains for impersonation** flyout, you can remove entries by selecting one or more entries from the list.</span></span> <span data-ttu-id="33da3-218">È possibile cercare voci utilizzando la casella Di ricerca ![ icona ](../../media/m365-cc-sc-create-icon.png) **di** ricerca.</span><span class="sxs-lookup"><span data-stu-id="33da3-218">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

       <span data-ttu-id="33da3-219">Dopo aver selezionato almeno una voce, viene visualizzata l'icona Elimina l'icona Elimina domini, che può essere utilizzata per ![ rimuovere le voci ](../../media/m365-cc-sc-delete-icon.png)  selezionate.</span><span class="sxs-lookup"><span data-stu-id="33da3-219">After you select at least one entry, the ![Delete domains icon](../../media/m365-cc-sc-delete-icon.png) **Delete** icon appears, which you can use to remove the selected entries.</span></span>

   - <span data-ttu-id="33da3-220">**Aggiungere mittenti e** domini attendibili : : specificare le eccezioni di protezione della rappresentazione per il criterio facendo clic su Gestisci **(nn)** mittenti attendibili e domini.</span><span class="sxs-lookup"><span data-stu-id="33da3-220">**Add trusted senders and domains**: : Specify impersonation protection exceptions for the policy by clicking on **Manage (nn) trusted sender(s) and domain(s)**.</span></span> <span data-ttu-id="33da3-221">Nel riquadro **a comparsa Gestisci domini personalizzati** per la protezione della rappresentazione visualizzato configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33da3-221">In the **Manage custom domains for impersonation protection** flyout that appears, configure the following settings:</span></span>
      - <span data-ttu-id="33da3-222">**Mittenti:** verificare che la **scheda Mittente** sia selezionata e fare clic ![ su Aggiungi mittenti icona ](../../media/m365-cc-sc-create-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="33da3-222">**Senders**: Verify the **Sender** tab is selected and click ![Add senders icon](../../media/m365-cc-sc-create-icon.png).</span></span> <span data-ttu-id="33da3-223">Nel riquadro **a comparsa Aggiungi mittenti** attendibili visualizzato immettere un indirizzo di posta elettronica nella casella e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="33da3-223">In the **Add trusted senders** flyout that appears, enter an email address in the box and then click **Add**.</span></span> <span data-ttu-id="33da3-224">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="33da3-224">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="33da3-225">Per rimuovere una voce esistente, fare clic ![ sull'icona Elimina ](../../media/m365-cc-sc-close-icon.png) per la voce.</span><span class="sxs-lookup"><span data-stu-id="33da3-225">To remove an existing entry, click ![Delete icon](../../media/m365-cc-sc-close-icon.png) for the entry.</span></span>

        <span data-ttu-id="33da3-226">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="33da3-226">When you're finished, click **Add**.</span></span>

      - <span data-ttu-id="33da3-227">**Domini**: selezionare la **scheda Dominio** e fare clic ![ sull'icona Aggiungi ](../../media/m365-cc-sc-create-icon.png) domini.</span><span class="sxs-lookup"><span data-stu-id="33da3-227">**Domains**: Select the **Domain** tab and click ![Add domains icon](../../media/m365-cc-sc-create-icon.png).</span></span>
  
        <span data-ttu-id="33da3-228">Nel riquadro **a** comparsa Aggiungi domini attendibili  visualizzato fare clic nella casella Dominio, immettere un valore e quindi premere INVIO o selezionare il valore visualizzato sotto la casella.</span><span class="sxs-lookup"><span data-stu-id="33da3-228">In the **Add trusted domains** flyout that appears, click in the **Domain** box, enter a value, and then press Enter or select the value that's displayed below the box.</span></span> <span data-ttu-id="33da3-229">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="33da3-229">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="33da3-230">Per rimuovere un valore esistente, fare clic su ![Rimuovi icona](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.</span><span class="sxs-lookup"><span data-stu-id="33da3-230">To remove an existing value, click remove ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to the value.</span></span>

        <span data-ttu-id="33da3-231">Al termine, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="33da3-231">When you're finished, click **Add**.</span></span>

     <span data-ttu-id="33da3-232">Tornare al **riquadro a** comparsa Gestisci domini personalizzati per la  rappresentazione, è possibile rimuovere le voci dalle schede Mittente e Dominio selezionando una o più voci dall'elenco. </span><span class="sxs-lookup"><span data-stu-id="33da3-232">Back on the **Manage custom domains for impersonation** flyout, you can remove entries from the **Sender** and **Domain** tabs by selecting one or more entries from the list.</span></span> <span data-ttu-id="33da3-233">È possibile cercare voci utilizzando la casella Di ricerca ![ icona ](../../media/m365-cc-sc-create-icon.png) **di** ricerca.</span><span class="sxs-lookup"><span data-stu-id="33da3-233">You can search for entries using the ![Search icon](../../media/m365-cc-sc-create-icon.png) **Search** box.</span></span>

     <span data-ttu-id="33da3-234">Dopo aver selezionato almeno una voce, viene visualizzata **l'icona** Elimina, che può essere utilizzata per rimuovere le voci selezionate.</span><span class="sxs-lookup"><span data-stu-id="33da3-234">After you select at least one entry, the **Delete** icon appears, which you can use to remove the selected entries.</span></span>

     <span data-ttu-id="33da3-235">Al termine, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="33da3-235">When you're finished, click **Done**.</span></span>

   - <span data-ttu-id="33da3-236">**Abilitare l'intelligence delle** cassette postali : il valore predefinito è attivato (selezionato) e si consiglia di lasciarlo attivato.</span><span class="sxs-lookup"><span data-stu-id="33da3-236">**Enable mailbox intelligence**: The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="33da3-237">Per disattivarla, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="33da3-237">To turn it off, clear the check box.</span></span>

     - <span data-ttu-id="33da3-238">**Abilita protezione della rappresentazione basata sull'intelligence**: questa impostazione è disponibile solo se **Abilita intelligence cassetta postale** è attivata (selezionata).</span><span class="sxs-lookup"><span data-stu-id="33da3-238">**Enable intelligence based impersonation protection**: This setting is available only if **Enable mailbox intelligence** is on (selected).</span></span> <span data-ttu-id="33da3-239">Questa impostazione consente all'intelligence delle cassette postali di intervenire sui messaggi identificati come tentativi di rappresentazione.</span><span class="sxs-lookup"><span data-stu-id="33da3-239">This setting allows mailbox intelligence to take action on messages that are identified as impersonation attempts.</span></span> <span data-ttu-id="33da3-240">Specificare l'azione da eseguire **nell'impostazione Se l'intelligence** delle cassette postali rileva un utente rappresentato nella pagina successiva.</span><span class="sxs-lookup"><span data-stu-id="33da3-240">You specify the action to take in the **If mailbox intelligence detects an impersonated user** setting on the next page.</span></span>

       <span data-ttu-id="33da3-241">È consigliabile attivare questa impostazione selezionando la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="33da3-241">We recommend that you turn this setting on by selecting the check box.</span></span> <span data-ttu-id="33da3-242">Per disattivare questa impostazione, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="33da3-242">To turn this setting off, clear the check box.</span></span>

   - <span data-ttu-id="33da3-243">**Spoof**: in questa sezione, utilizzare la casella di controllo **Abilita spoof intelligence** per attivare o disattivare spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="33da3-243">**Spoof**: In this section, use the **Enable spoof intelligence** check box to turn spoof intelligence on or off.</span></span> <span data-ttu-id="33da3-244">Il valore predefinito è on (selezionato) e ti consigliamo di lasciarlo.</span><span class="sxs-lookup"><span data-stu-id="33da3-244">The default value is on (selected), and we recommend that you leave it on.</span></span> <span data-ttu-id="33da3-245">È possibile specificare l'azione da eseguire sui messaggi provenienti da mittenti spoofing bloccati nell'impostazione Se il messaggio viene rilevato come **spoofing** nella pagina successiva.</span><span class="sxs-lookup"><span data-stu-id="33da3-245">You specify the action to take on messages from blocked spoofed senders in the **If message is detected as spoof** setting on the next page.</span></span>

     <span data-ttu-id="33da3-246">Per disattivare lo spoof intelligence, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="33da3-246">To turn off spoof intelligence, clear the check box.</span></span>

     > [!NOTE]
     > <span data-ttu-id="33da3-247">Non è necessario disattivare la protezione anti-spoofing se il record MX non punta a Microsoft 365; si abilita invece il filtro avanzato per i connettori.</span><span class="sxs-lookup"><span data-stu-id="33da3-247">You don't need to turn off anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="33da3-248">Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span><span class="sxs-lookup"><span data-stu-id="33da3-248">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   <span data-ttu-id="33da3-249">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="33da3-249">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="33da3-250">Nella pagina **Azioni** visualizzata configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33da3-250">On the **Actions** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="33da3-251">**Azioni messaggio**: configurare le azioni seguenti in questa sezione:</span><span class="sxs-lookup"><span data-stu-id="33da3-251">**Message actions**: Configure the following actions in this section:</span></span>
     - <span data-ttu-id="33da3-252">**Se il messaggio viene rilevato come utente rappresentato:** questa impostazione è disponibile solo se è stata selezionata l'opzione Consenti agli utenti di **proteggere** nella pagina precedente.</span><span class="sxs-lookup"><span data-stu-id="33da3-252">**If message is detected as an impersonated user**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span> <span data-ttu-id="33da3-253">Selezionare una delle azioni seguenti nell'elenco a discesa per i messaggi in cui il mittente è uno degli utenti protetti specificati nella pagina precedente:</span><span class="sxs-lookup"><span data-stu-id="33da3-253">Select one of the following actions in the drop down list for messages where the sender is one of the protected users that you specified on the previous page:</span></span>
       - <span data-ttu-id="33da3-254">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="33da3-254">**Don't apply any action**</span></span>
       - <span data-ttu-id="33da3-255">**Reindirizzare il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="33da3-255">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="33da3-256">**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="33da3-256">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="33da3-257">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="33da3-257">**Quarantine the message**</span></span>
       - <span data-ttu-id="33da3-258">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="33da3-258">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="33da3-259">**Eliminare il messaggio prima che venga recapitato**</span><span class="sxs-lookup"><span data-stu-id="33da3-259">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="33da3-260">**Se il messaggio viene rilevato come** dominio rappresentato: questa impostazione è disponibile solo se è stata selezionata l'opzione Abilita domini da proteggere nella pagina precedente. </span><span class="sxs-lookup"><span data-stu-id="33da3-260">**If the message is detected as an impersonated domain**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span> <span data-ttu-id="33da3-261">Selezionare una delle azioni seguenti nell'elenco a discesa per i messaggi in cui l'indirizzo di posta elettronica del mittente si trova in uno dei domini protetti specificati nella pagina precedente:</span><span class="sxs-lookup"><span data-stu-id="33da3-261">Select one of the following actions in the drop down list for messages where the sender's email address is in one of the protected domains that you specified on the previous page:</span></span>
       - <span data-ttu-id="33da3-262">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="33da3-262">**Don't apply any action**</span></span>
       - <span data-ttu-id="33da3-263">**Reindirizzare il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="33da3-263">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="33da3-264">**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="33da3-264">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="33da3-265">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="33da3-265">**Quarantine the message**</span></span>
       - <span data-ttu-id="33da3-266">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="33da3-266">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="33da3-267">**Eliminare il messaggio prima che venga recapitato**</span><span class="sxs-lookup"><span data-stu-id="33da3-267">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="33da3-268">**If mailbox intelligence detects an impersonated user**: This setting is available only if you selected **Enable intelligence for impersonation protection** on the previous page.</span><span class="sxs-lookup"><span data-stu-id="33da3-268">**If mailbox intelligence detects an impersonated user**: This setting is available only if you selected **Enable intelligence for impersonation protection** on the previous page.</span></span> <span data-ttu-id="33da3-269">Selezionare una delle azioni seguenti nell'elenco a discesa per i messaggi identificati come tentativi di rappresentazione dall'intelligence delle cassette postali:</span><span class="sxs-lookup"><span data-stu-id="33da3-269">Select one of the following actions in the drop down list for messages that were identified as impersonation attempts by mailbox intelligence:</span></span>
       - <span data-ttu-id="33da3-270">**Non applicare alcuna azione**</span><span class="sxs-lookup"><span data-stu-id="33da3-270">**Don't apply any action**</span></span>
       - <span data-ttu-id="33da3-271">**Reindirizzare il messaggio ad altri indirizzi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="33da3-271">**Redirect message to other email addresses**</span></span>
       - <span data-ttu-id="33da3-272">**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="33da3-272">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="33da3-273">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="33da3-273">**Quarantine the message**</span></span>
       - <span data-ttu-id="33da3-274">**Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**</span><span class="sxs-lookup"><span data-stu-id="33da3-274">**Deliver the message and add other addresses to the Bcc line**</span></span>
       - <span data-ttu-id="33da3-275">**Eliminare il messaggio prima che venga recapitato**</span><span class="sxs-lookup"><span data-stu-id="33da3-275">**Delete the message before it's delivered**</span></span>

     - <span data-ttu-id="33da3-276">**Se il messaggio viene rilevato come spoof:** questa impostazione è disponibile solo se è stato selezionato **Abilita spoof intelligence** nella pagina precedente.</span><span class="sxs-lookup"><span data-stu-id="33da3-276">**If message is detected as spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="33da3-277">Selezionare una delle azioni seguenti nell'elenco a discesa per i messaggi provenienti da mittenti falsificati bloccati:</span><span class="sxs-lookup"><span data-stu-id="33da3-277">Select one of the following actions in the drop down list for messages from blocked spoofed senders:</span></span>
       - <span data-ttu-id="33da3-278">**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**</span><span class="sxs-lookup"><span data-stu-id="33da3-278">**Move message to the recipients' Junk Email folders**</span></span>
       - <span data-ttu-id="33da3-279">**Mettere in quarantena il messaggio**</span><span class="sxs-lookup"><span data-stu-id="33da3-279">**Quarantine the message**</span></span>

   - <span data-ttu-id="33da3-280">**Suggerimenti per la sicurezza & indicatori**: Configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33da3-280">**Safety tips & indicators**: Configure the following settings:</span></span>
     - <span data-ttu-id="33da3-281">**Show first contact suggerimento per la sicurezza**: Per ulteriori informazioni, vedere [First contact suggerimento per la sicurezza](set-up-anti-phishing-policies.md#first-contact-safety-tip).</span><span class="sxs-lookup"><span data-stu-id="33da3-281">**Show first contact safety tip**: For more information, see [First contact safety tip](set-up-anti-phishing-policies.md#first-contact-safety-tip).</span></span>
     - <span data-ttu-id="33da3-282">**Mostra rappresentazione utente suggerimento per la sicurezza**: questa impostazione è disponibile solo se è stata selezionata l'opzione Consenti agli utenti **di proteggere** nella pagina precedente.</span><span class="sxs-lookup"><span data-stu-id="33da3-282">**Show user impersonation safety tip**: This setting is available only if you selected **Enable users to protect** on the previous page.</span></span>
     - <span data-ttu-id="33da3-283">**Show domain impersonation suggerimento per la sicurezza**: Questa impostazione è disponibile solo se è stato selezionato Abilita domini **da proteggere** nella pagina precedente.</span><span class="sxs-lookup"><span data-stu-id="33da3-283">**Show domain impersonation safety tip**: This setting is available only if you selected **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="33da3-284">**Mostra caratteri insoliti di rappresentazione utente suggerimento per la sicurezza** Questa impostazione è disponibile solo se è stata selezionata l'opzione Consenti agli **utenti di proteggere** o Abilitare i domini per la **protezione** nella pagina precedente.</span><span class="sxs-lookup"><span data-stu-id="33da3-284">**Show user impersonation unusual characters safety tip** This setting is available only if you selected **Enable users to protect** or **Enable domains to protect** on the previous page.</span></span>
     - <span data-ttu-id="33da3-285">**Mostra (?) per i mittenti** non autenticati per lo spoofing: questa impostazione è disponibile solo se è stato selezionato **Abilita spoof intelligence** nella pagina precedente.</span><span class="sxs-lookup"><span data-stu-id="33da3-285">**Show (?) for unauthenticated senders for spoof**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="33da3-286">Aggiunge un punto interrogativo alla foto del mittente nella casella Da di Outlook se il  messaggio non supera i controlli SPF o DKIM e il messaggio non supera l'autenticazione DMARC o [composita.](email-validation-and-authentication.md#composite-authentication)</span><span class="sxs-lookup"><span data-stu-id="33da3-286">Adds a question mark to the sender's photo in the From box in Outlook if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>
     - <span data-ttu-id="33da3-287">**Mostra tag "via":** questa impostazione è disponibile solo se è stata selezionata l'opzione **Abilita spoof intelligence** nella pagina precedente.</span><span class="sxs-lookup"><span data-stu-id="33da3-287">**Show "via" tag**: This setting is available only if you selected **Enable spoof intelligence** on the previous page.</span></span> <span data-ttu-id="33da3-288">Aggiunge un tag via (chris@contoso.com tramite fabrikam.com) all'indirizzo From se è diverso dal dominio nella firma DKIM o nell'indirizzo **MAIL FROM.**</span><span class="sxs-lookup"><span data-stu-id="33da3-288">Adds a via tag (chris@contoso.com via fabrikam.com) to the From address if it's different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="33da3-289">Il valore predefinito è on (selezionato).</span><span class="sxs-lookup"><span data-stu-id="33da3-289">The default value is on (selected).</span></span> <span data-ttu-id="33da3-290">Per disattivarla, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="33da3-290">To turn it off, clear the check box.</span></span>

       > [!NOTE]
       > <span data-ttu-id="33da3-291">Se non si dispone dell'impostazione Mostra **tag "via",** il punto interrogativo e il tag via sono entrambi controllati dall'impostazione Mostra **(?)** per i mittenti non autenticati per lo spoofing nell'organizzazione. </span><span class="sxs-lookup"><span data-stu-id="33da3-291">If you don't have the **Show "via" tag** setting, the question mark **and** the via tag are both controlled by the **Show (?) for unauthenticated senders for spoof** setting in your organization.</span></span>

     <span data-ttu-id="33da3-292">Per attivare un'impostazione, selezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="33da3-292">To turn on a setting, select the check box.</span></span> <span data-ttu-id="33da3-293">Per disattivarla, deselezionare la casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="33da3-293">To turn it off, clear the check box.</span></span>

   <span data-ttu-id="33da3-294">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="33da3-294">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="33da3-295">Nella pagina **Controllo** visualizzata controllare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="33da3-295">On the **Review** page that appears, review your settings.</span></span> <span data-ttu-id="33da3-296">È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="33da3-296">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="33da3-297">Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="33da3-297">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="33da3-298">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="33da3-298">When you're finished, click **Submit**.</span></span>

8. <span data-ttu-id="33da3-299">Nel messaggio di conferma visualizzato fare clic su **Fatto**.</span><span class="sxs-lookup"><span data-stu-id="33da3-299">On the confirmation page that appears, click **Done**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a><span data-ttu-id="33da3-300">Utilizzare il portale Microsoft 365 Defender per visualizzare i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="33da3-300">Use the Microsoft 365 Defender portal to view anti-phishing policies</span></span>

1. <span data-ttu-id="33da3-301">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="33da3-301">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33da3-302">Nella pagina **Anti-phishing** vengono visualizzate le proprietà seguenti nell'elenco dei criteri anti-phishing:</span><span class="sxs-lookup"><span data-stu-id="33da3-302">On the **Anti-phishing** page, the following properties are displayed in the list of anti-phishing policies:</span></span>

   - <span data-ttu-id="33da3-303">**Nome**</span><span class="sxs-lookup"><span data-stu-id="33da3-303">**Name**</span></span>
   - <span data-ttu-id="33da3-304">**Stato**</span><span class="sxs-lookup"><span data-stu-id="33da3-304">**Status**</span></span>
   - <span data-ttu-id="33da3-305">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="33da3-305">**Priority**</span></span>
   - <span data-ttu-id="33da3-306">**Data ultima modifica**</span><span class="sxs-lookup"><span data-stu-id="33da3-306">**Last modified**</span></span>

3. <span data-ttu-id="33da3-307">Quando si seleziona un criterio facendo clic sul nome, le impostazioni dei criteri vengono visualizzate in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="33da3-307">When you select a policy by clicking on the name, the policy settings are displayed in a flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a><span data-ttu-id="33da3-308">Utilizzare il portale Microsoft 365 Defender per modificare i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="33da3-308">Use the Microsoft 365 Defender portal to modify anti-phishing policies</span></span>

1. <span data-ttu-id="33da3-309">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="33da3-309">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33da3-310">Nella pagina **Anti-phishing** selezionare un criterio dall'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="33da3-310">On the **Anti-phishing** page, select a policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="33da3-311">Nel riquadro a comparsa dei dettagli sui criteri visualizzato selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione.</span><span class="sxs-lookup"><span data-stu-id="33da3-311">In the policy details flyout that appears, select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="33da3-312">Per ulteriori informazioni sulle impostazioni, vedere la sezione Usare il portale di Microsoft 365 Defender per creare criteri [anti-phishing](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="33da3-312">For more information about the settings, see the [Use the Microsoft 365 Defender portal to create anti-phishing policies](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) section earlier in this article.</span></span>  

   <span data-ttu-id="33da3-313">Per il criterio anti-phishing predefinito, la sezione **Utenti,** gruppi e domini non è disponibile (il criterio si applica a tutti) e non è possibile rinominare il criterio.</span><span class="sxs-lookup"><span data-stu-id="33da3-313">For the default anti-phishing policy, the **Users, groups, and domains** section isn't available (the policy applies to everyone), and you can't rename the policy.</span></span>

<span data-ttu-id="33da3-314">Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="33da3-314">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-custom-anti-phishing-policies"></a><span data-ttu-id="33da3-315">Abilitare o disabilitare i criteri anti-phishing personalizzati</span><span class="sxs-lookup"><span data-stu-id="33da3-315">Enable or disable custom anti-phishing policies</span></span>

<span data-ttu-id="33da3-316">Non è possibile disabilitare il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="33da3-316">You can't disable the default anti-phishing policy.</span></span>

1. <span data-ttu-id="33da3-317">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="33da3-317">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33da3-318">Nella pagina **Anti-phishing** selezionare un criterio personalizzato nell'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="33da3-318">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="33da3-319">Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato è presente uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="33da3-319">At the top of the policy details flyout that appears, you'll see one of the following values:</span></span>
   - <span data-ttu-id="33da3-320">**Criterio disattivato**: per attivare il criterio, fare clic su ![Attiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Attiva** .</span><span class="sxs-lookup"><span data-stu-id="33da3-320">**Policy off**: To turn on the policy, click ![Turn on icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn on** .</span></span>
   - <span data-ttu-id="33da3-321">**Criterio attivato**: per disattivare il criterio, fare clic su ![Disattiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="33da3-321">**Policy on**: To turn off the policy, click ![Turn off icon](../../media/m365-cc-sc-turn-on-off-icon.png) **Turn off**.</span></span>

4. <span data-ttu-id="33da3-322">Nella finestra di dialogo di conferma visualizzata fare clic su **Attiva** o **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="33da3-322">In the confirmation dialog that appears, click **Turn on** or **Turn off**.</span></span>

5. <span data-ttu-id="33da3-323">Fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.</span><span class="sxs-lookup"><span data-stu-id="33da3-323">Click **Close** in the policy details flyout.</span></span>

<span data-ttu-id="33da3-324">Tornare alla pagina dei criteri principale, il valore **Stato** del criterio sarà **Attivato** o **Disattivato**.</span><span class="sxs-lookup"><span data-stu-id="33da3-324">Back on the main policy page, the **Status** value of the policy will be **On** or **Off**.</span></span>

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a><span data-ttu-id="33da3-325">Impostare la priorità dei criteri anti-phishing personalizzati</span><span class="sxs-lookup"><span data-stu-id="33da3-325">Set the priority of custom anti-phishing policies</span></span>

<span data-ttu-id="33da3-326">Per impostazione predefinita, ai criteri anti-phishing viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti).</span><span class="sxs-lookup"><span data-stu-id="33da3-326">By default, anti-phishing policies are given a priority that's based on the order they were created in (newer policies are lower priority than older policies).</span></span> <span data-ttu-id="33da3-327">Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa).</span><span class="sxs-lookup"><span data-stu-id="33da3-327">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="33da3-328">Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.</span><span class="sxs-lookup"><span data-stu-id="33da3-328">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="33da3-329">Per modificare la priorità di un criterio, fare clic su **Aumenta priorità** o **Riduci priorità** nelle proprietà del criterio. Non è possibile modificare direttamente il valore **Priorità** nel portale di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="33da3-329">To change the priority of a policy, you click **Increase priority** or **Decrease priority** in the properties of the policy (you can't directly modify the **Priority** number in the Microsoft 365 Defender portal).</span></span> <span data-ttu-id="33da3-330">La modifica di priorità di un criterio è utile solo se si hanno più criteri.</span><span class="sxs-lookup"><span data-stu-id="33da3-330">Changing the priority of a policy only makes sense if you have multiple policies.</span></span>

 <span data-ttu-id="33da3-331">**Note**:</span><span class="sxs-lookup"><span data-stu-id="33da3-331">**Notes**:</span></span>

- <span data-ttu-id="33da3-332">Nel portale Microsoft 365 Defender, è possibile modificare la priorità del criterio anti-phishing solo dopo aver creato il criterio.</span><span class="sxs-lookup"><span data-stu-id="33da3-332">In the Microsoft 365 Defender portal, you can only change the priority of the anti-phishing policy after you create it.</span></span> <span data-ttu-id="33da3-333">In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phish (che può influire sulla priorità delle regole esistenti).</span><span class="sxs-lookup"><span data-stu-id="33da3-333">In PowerShell, you can override the default priority when you create the anti-phish rule (which can affect the priority of existing rules).</span></span>
- <span data-ttu-id="33da3-334">I criteri anti-phishing vengono elaborati nell'ordine in cui vengono visualizzati (il primo criterio ha il **valore Priority** 0).</span><span class="sxs-lookup"><span data-stu-id="33da3-334">Anti-phishing policies are processed in the order that they're displayed (the first policy has the **Priority** value 0).</span></span> <span data-ttu-id="33da3-335">Il criterio anti-phishing predefinito ha il valore di priorità **Lowest** e non è possibile modificarlo.</span><span class="sxs-lookup"><span data-stu-id="33da3-335">The default anti-phishing policy has the priority value **Lowest**, and you can't change it.</span></span>

1. <span data-ttu-id="33da3-336">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="33da3-336">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33da3-337">Nella pagina **Anti-phishing** selezionare un criterio personalizzato nell'elenco facendo clic sul nome.</span><span class="sxs-lookup"><span data-stu-id="33da3-337">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name.</span></span>

3. <span data-ttu-id="33da3-338">Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato viene visualizzato **Aumenta priorità** o **Riduci priorità** in base al valore di priorità corrente e al numero di criteri personalizzati:</span><span class="sxs-lookup"><span data-stu-id="33da3-338">At the top of the policy details flyout that appears, you'll see **Increase priority** or **Decrease priority** based on the current priority value and the number of custom policies:</span></span>
   - <span data-ttu-id="33da3-339">Per il criterio con **valore Priority** **0 è** disponibile solo **l'opzione Riduci** priorità.</span><span class="sxs-lookup"><span data-stu-id="33da3-339">The policy with the **Priority** value **0** has only the **Decrease priority** option available.</span></span>
   - <span data-ttu-id="33da3-340">Il criterio con il valore **Di priorità** più basso (ad esempio, **3)** ha solo l'opzione **Aumenta** priorità disponibile.</span><span class="sxs-lookup"><span data-stu-id="33da3-340">The policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** option available.</span></span>
   - <span data-ttu-id="33da3-341">Se si dispone di tre o più criteri, per i  criteri tra i valori di priorità più alta e più bassa sono disponibili le opzioni Aumenta priorità e **Riduci** priorità.</span><span class="sxs-lookup"><span data-stu-id="33da3-341">If you have three or more policies, the policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** options available.</span></span>

   <span data-ttu-id="33da3-342">Fare clic![ sull’icona Aumenta priorità](../../media/m365-cc-sc-increase-icon.png) **Aumenta priorità** o ![sull’icona Riduci priorità](../../media/m365-cc-sc-decrease-icon.png) **Riduci priorità** per modificare il valore **Priorità**.</span><span class="sxs-lookup"><span data-stu-id="33da3-342">Click ![Increase priority icon](../../media/m365-cc-sc-increase-icon.png) **Increase priority** or ![Decrease priority icon](../../media/m365-cc-sc-decrease-icon.png) **Decrease priority** to change the **Priority** value.</span></span>

4. <span data-ttu-id="33da3-343">Al termine, fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.</span><span class="sxs-lookup"><span data-stu-id="33da3-343">When you're finished, click **Close** in the policy details flyout.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a><span data-ttu-id="33da3-344">Utilizzare il portale Microsoft 365 Defender per rimuovere criteri anti-phishing personalizzati</span><span class="sxs-lookup"><span data-stu-id="33da3-344">Use the Microsoft 365 Defender portal to remove custom anti-phishing policies</span></span>

<span data-ttu-id="33da3-345">Quando si utilizza il portale Microsoft 365 Defender per rimuovere un criterio anti-phishing personalizzato, la regola anti-phishing e il criterio anti-phishing corrispondente vengono eliminati entrambi.</span><span class="sxs-lookup"><span data-stu-id="33da3-345">When you use the Microsoft 365 Defender portal to remove a custom anti-phishing policy, the anti-phish rule and the corresponding anti-phish policy are both deleted.</span></span> <span data-ttu-id="33da3-346">Non è possibile rimuovere il criterio anti-phishing predefinito.</span><span class="sxs-lookup"><span data-stu-id="33da3-346">You can't remove the default anti-phishing policy.</span></span>

1. <span data-ttu-id="33da3-347">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="33da3-347">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="33da3-348">Nella pagina **Anti-phishing** selezionare un criterio personalizzato nell'elenco facendo clic sul nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="33da3-348">On the **Anti-phishing** page, select a custom policy from the list by clicking on the name of the policy.</span></span>

3. <span data-ttu-id="33da3-349">Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato fare clic![ sull'icona Altre azioni](../../media/m365-cc-sc-more-actions-icon.png) **Altre azioni** \> ![Icona Elimina criterio](../../media/m365-cc-sc-delete-icon.png) **Elimina criterio**.</span><span class="sxs-lookup"><span data-stu-id="33da3-349">At the top of the policy details flyout that appears, click ![More actions icon](../../media/m365-cc-sc-more-actions-icon.png) **More actions** \> ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy**.</span></span>

4. <span data-ttu-id="33da3-350">Nella finestra di dialogo di conferma che viene visualizzata fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="33da3-350">In the confirmation dialog that appears, click **Yes**.</span></span>

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a><span data-ttu-id="33da3-351">Utilizzare Exchange Online PowerShell per configurare i criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="33da3-351">Use Exchange Online PowerShell to configure anti-phishing policies</span></span>

<span data-ttu-id="33da3-352">Come descritto in precedenza, un criterio di protezione da posta indesiderata è costituito da un criterio anti-phish e da una regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="33da3-352">As previously described, an anti-spam policy consists of an anti-phish policy and an anti-phish rule.</span></span>

<span data-ttu-id="33da3-353">In Exchange Online PowerShell, è evidente la differenza tra i criteri anti-phish e le regole anti-phish.</span><span class="sxs-lookup"><span data-stu-id="33da3-353">In Exchange Online PowerShell, the difference between anti-phish policies and anti-phish rules is apparent.</span></span> <span data-ttu-id="33da3-354">È possibile gestire i criteri anti-phish utilizzando i cmdlet **\* -AntiPhishPolicy** e gestire le regole anti-phish utilizzando i cmdlet **\* -AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="33da3-354">You manage anti-phish policies by using the **\*-AntiPhishPolicy** cmdlets, and you manage anti-phish rules by using the **\*-AntiPhishRule** cmdlets.</span></span>

- <span data-ttu-id="33da3-355">In PowerShell, si crea prima il criterio anti-phish, quindi si crea la regola anti-phish che identifica il criterio a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="33da3-355">In PowerShell, you create the anti-phish policy first, then you create the anti-phish rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="33da3-356">In PowerShell, le impostazioni dei criteri anti-phish e della regola anti-phish vengono modificate separatamente.</span><span class="sxs-lookup"><span data-stu-id="33da3-356">In PowerShell, you modify the settings in the anti-phish policy and the anti-phish rule separately.</span></span>
- <span data-ttu-id="33da3-357">Quando si rimuove un criterio anti-phish da PowerShell, la regola anti-phish corrispondente non viene rimossa automaticamente e viceversa.</span><span class="sxs-lookup"><span data-stu-id="33da3-357">When you remove an anti-phish policy from PowerShell, the corresponding anti-phish rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-anti-phishing-policies"></a><span data-ttu-id="33da3-358">Utilizzare PowerShell per creare criteri anti-phishing</span><span class="sxs-lookup"><span data-stu-id="33da3-358">Use PowerShell to create anti-phishing policies</span></span>

<span data-ttu-id="33da3-359">La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:</span><span class="sxs-lookup"><span data-stu-id="33da3-359">Creating an anti-phishing policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="33da3-360">Creare i criteri anti-phish.</span><span class="sxs-lookup"><span data-stu-id="33da3-360">Create the anti-phish policy.</span></span>
2. <span data-ttu-id="33da3-361">Creare la regola anti-phish che specifica il criterio anti-phish a cui si applica la regola.</span><span class="sxs-lookup"><span data-stu-id="33da3-361">Create the anti-phish rule that specifies the anti-phish policy that the rule applies to.</span></span>

 <span data-ttu-id="33da3-362">**Note**:</span><span class="sxs-lookup"><span data-stu-id="33da3-362">**Notes**:</span></span>

- <span data-ttu-id="33da3-363">È possibile creare una nuova regola anti-phish e assegnarle un criterio anti-phish esistente e non associazione.</span><span class="sxs-lookup"><span data-stu-id="33da3-363">You can create a new anti-phish rule and assign an existing, unassociated anti-phish policy to it.</span></span> <span data-ttu-id="33da3-364">Una regola anti-phish non può essere associata a più di un criterio anti-phish.</span><span class="sxs-lookup"><span data-stu-id="33da3-364">An anti-phish rule can't be associated with more than one anti-phish policy.</span></span>
- <span data-ttu-id="33da3-365">È possibile configurare le impostazioni seguenti nei nuovi criteri anti-phish in PowerShell che non sono disponibili nel portale di Microsoft 365 Defender fino a quando non si crea il criterio:</span><span class="sxs-lookup"><span data-stu-id="33da3-365">You can configure the following settings on new anti-phish policies in PowerShell that aren't available in the Microsoft 365 Defender portal until after you create the policy:</span></span>
  - <span data-ttu-id="33da3-366">Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-AntiPhishRule).**</span><span class="sxs-lookup"><span data-stu-id="33da3-366">Create the new policy as disabled (_Enabled_ `$false` on the **New-AntiPhishRule** cmdlet).</span></span>
  - <span data-ttu-id="33da3-367">Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="33da3-367">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet).</span></span>
- <span data-ttu-id="33da3-368">Un nuovo criterio anti-phish creato in PowerShell non è visibile nel portale di Microsoft 365 Defender finché non si assegna il criterio a una regola anti-phish.</span><span class="sxs-lookup"><span data-stu-id="33da3-368">A new anti-phish policy that you create in PowerShell isn't visible in the Microsoft 365 Defender portal until you assign the policy to an anti-phish rule.</span></span>

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a><span data-ttu-id="33da3-369">Passaggio 1: Usare PowerShell per creare un criterio anti-phish</span><span class="sxs-lookup"><span data-stu-id="33da3-369">Step 1: Use PowerShell to create an anti-phish policy</span></span>

<span data-ttu-id="33da3-370">Per creare un criterio anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="33da3-370">To create an anti-phish policy, use this syntax:</span></span>

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

<span data-ttu-id="33da3-371">In questo esempio viene creato un criterio anti-phish denominato Research Quarantine con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33da3-371">This example creates anti-phish policy named Research Quarantine with the following settings:</span></span>

- <span data-ttu-id="33da3-372">Il criterio è abilitato (non viene utilizzato il _parametro Enabled_ e il valore predefinito è `$true` ).</span><span class="sxs-lookup"><span data-stu-id="33da3-372">The policy is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>
- <span data-ttu-id="33da3-373">La descrizione è: Criteri del reparto di ricerca.</span><span class="sxs-lookup"><span data-stu-id="33da3-373">The description is: Research department policy.</span></span>
- <span data-ttu-id="33da3-374">Abilita la protezione dei domini dell'organizzazione per tutti i domini accettati e la protezione dei domini di destinazione per fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="33da3-374">Enables organization domains protection for all accepted domains, and targeted domains protection for fabrikam.com.</span></span>
- <span data-ttu-id="33da3-375">Specifica Mai Fujito (mfujito@fabrikam.com) come l'utente da proteggere da imitazione.</span><span class="sxs-lookup"><span data-stu-id="33da3-375">Specifies Mai Fujito (mfujito@fabrikam.com) as the user to protect from impersonation.</span></span>
- <span data-ttu-id="33da3-376">Abilita l'intelligence della cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="33da3-376">Enables mailbox intelligence.</span></span>
- <span data-ttu-id="33da3-377">Abilita la protezione dell'intelligence delle cassette postali e specifica l'azione di quarantena.</span><span class="sxs-lookup"><span data-stu-id="33da3-377">Enables mailbox intelligence protection, and specifies the quarantine action.</span></span>
- <span data-ttu-id="33da3-378">Abilita i suggerimenti per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="33da3-378">Enables safety tips.</span></span>

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

<span data-ttu-id="33da3-379">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="33da3-379">For detailed syntax and parameter information, see [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a><span data-ttu-id="33da3-380">Passaggio 2: Usare PowerShell per creare una regola anti-phish</span><span class="sxs-lookup"><span data-stu-id="33da3-380">Step 2: Use PowerShell to create an anti-phish rule</span></span>

<span data-ttu-id="33da3-381">Per creare una regola anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="33da3-381">To create an anti-phish rule, use this syntax:</span></span>

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

<span data-ttu-id="33da3-382">In questo esempio viene creata una regola anti-phish denominata Research Department con le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33da3-382">This example creates an anti-phish rule named Research Department with the following conditions:</span></span>

- <span data-ttu-id="33da3-383">La regola è associata al criterio anti-phish denominato Quarantena ricerche.</span><span class="sxs-lookup"><span data-stu-id="33da3-383">The rule is associated with the anti-phish policy named Research Quarantine.</span></span>
- <span data-ttu-id="33da3-384">La regola viene applicata ai membri del gruppo denominato Research Department.</span><span class="sxs-lookup"><span data-stu-id="33da3-384">The rule applies to members of the group named Research Department.</span></span>
- <span data-ttu-id="33da3-385">Poiché non si utilizza il parametro _Priority,_ viene utilizzata la priorità predefinita.</span><span class="sxs-lookup"><span data-stu-id="33da3-385">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

<span data-ttu-id="33da3-386">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span><span class="sxs-lookup"><span data-stu-id="33da3-386">For detailed syntax and parameter information, see [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).</span></span>

### <a name="use-powershell-to-view-anti-phish-policies"></a><span data-ttu-id="33da3-387">Usare PowerShell per visualizzare i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="33da3-387">Use PowerShell to view anti-phish policies</span></span>

<span data-ttu-id="33da3-388">Per visualizzare i criteri anti-phish esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="33da3-388">To view existing anti-phish policies, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="33da3-389">In questo esempio viene restituito un elenco riepilogativo di tutti i criteri anti-phish insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="33da3-389">This example returns a summary list of all anti-phish policies along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

<span data-ttu-id="33da3-390">In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio anti-phish denominato Executives.</span><span class="sxs-lookup"><span data-stu-id="33da3-390">This example returns all the property values for the anti-phish policy named Executives.</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

<span data-ttu-id="33da3-391">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span><span class="sxs-lookup"><span data-stu-id="33da3-391">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-view-anti-phish-rules"></a><span data-ttu-id="33da3-392">Usare PowerShell per visualizzare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="33da3-392">Use PowerShell to view anti-phish rules</span></span>

<span data-ttu-id="33da3-393">Per visualizzare le regole anti-phish esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="33da3-393">To view existing anti-phish rules, use the following syntax:</span></span>

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="33da3-394">In questo esempio viene restituito un elenco riepilogativo di tutte le regole anti-phish insieme alle proprietà specificate.</span><span class="sxs-lookup"><span data-stu-id="33da3-394">This example returns a summary list of all anti-phish rules along with the specified properties.</span></span>

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

<span data-ttu-id="33da3-395">Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="33da3-395">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

<span data-ttu-id="33da3-396">In questo esempio vengono restituiti tutti i valori delle proprietà per la regola anti-phish denominata Contoso Executives.</span><span class="sxs-lookup"><span data-stu-id="33da3-396">This example returns all the property values for the anti-phish rule named Contoso Executives.</span></span>

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

<span data-ttu-id="33da3-397">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span><span class="sxs-lookup"><span data-stu-id="33da3-397">For detailed syntax and parameter information, see [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).</span></span>

### <a name="use-powershell-to-modify-anti-phish-policies"></a><span data-ttu-id="33da3-398">Utilizzare PowerShell per modificare i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="33da3-398">Use PowerShell to modify anti-phish policies</span></span>

<span data-ttu-id="33da3-399">Oltre agli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio anti-phish in PowerShell come quando si crea il criterio come descritto nella sezione Passaggio 1: utilizzare PowerShell per creare un criterio [anti-phish](#step-1-use-powershell-to-create-an-anti-phish-policy) in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="33da3-399">Other than the following items, the same settings are available when you modify an anti-phish policy in PowerShell as when you create the policy as described in the [Step 1: Use PowerShell to create an anti-phish policy](#step-1-use-powershell-to-create-an-anti-phish-policy) section earlier in this article.</span></span>

- <span data-ttu-id="33da3-400">L'opzione _MakeDefault_ che trasforma il criterio specificato nel  criterio predefinito (applicato a tutti, sempre con priorità minima e non è possibile eliminarlo) è disponibile solo quando si modifica un criterio anti-phish in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33da3-400">The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone, always **Lowest** priority, and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.</span></span>

- <span data-ttu-id="33da3-401">Non è possibile rinominare un criterio anti-phish (il cmdlet **Set-AntiPhishPolicy** non dispone di _alcun parametro Name)._</span><span class="sxs-lookup"><span data-stu-id="33da3-401">You can't rename an anti-phish policy (the **Set-AntiPhishPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="33da3-402">Quando si rinomina un criterio anti-phishing nel portale Microsoft 365 Defender, si rinomina solo la regola _anti-phishing._</span><span class="sxs-lookup"><span data-stu-id="33da3-402">When you rename an anti-phishing policy in the Microsoft 365 Defender portal, you're only renaming the anti-phish _rule_.</span></span>

<span data-ttu-id="33da3-403">Per modificare un criterio anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="33da3-403">To modify an anti-phish policy, use this syntax:</span></span>

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="33da3-404">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="33da3-404">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-anti-phish-rules"></a><span data-ttu-id="33da3-405">Utilizzare PowerShell per modificare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="33da3-405">Use PowerShell to modify anti-phish rules</span></span>

<span data-ttu-id="33da3-406">L'unica impostazione non disponibile quando si modifica una regola anti-phish in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata.</span><span class="sxs-lookup"><span data-stu-id="33da3-406">The only setting that isn't available when you modify an anti-phish rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="33da3-407">Per abilitare o disabilitare le regole anti-phish esistenti, vedi la sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="33da3-407">To enable or disable existing anti-phish rules, see the next section.</span></span>

<span data-ttu-id="33da3-408">In caso contrario, non sono disponibili impostazioni aggiuntive quando si modifica una regola anti-phish in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33da3-408">Otherwise, no additional settings are available when you modify an anti-phish rule in PowerShell.</span></span> <span data-ttu-id="33da3-409">Le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione Passaggio 2: Utilizzare PowerShell per creare una regola [anti-phish](#step-2-use-powershell-to-create-an-anti-phish-rule) in precedenza in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="33da3-409">The same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create an anti-phish rule](#step-2-use-powershell-to-create-an-anti-phish-rule) section earlier in this article.</span></span>

<span data-ttu-id="33da3-410">Per modificare una regola anti-phish, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="33da3-410">To modify an anti-phish rule, use this syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="33da3-411">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="33da3-411">For detailed syntax and parameter information, see [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a><span data-ttu-id="33da3-412">Usare PowerShell per abilitare o disabilitare le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="33da3-412">Use PowerShell to enable or disable anti-phish rules</span></span>

<span data-ttu-id="33da3-413">L'abilitazione o la disabilitazione di una regola anti-phishing in PowerShell abilita o disabilita l'intero criterio anti-phishing (la regola anti-phishing e il criterio anti-phishing assegnato).</span><span class="sxs-lookup"><span data-stu-id="33da3-413">Enabling or disabling an anti-phish rule in PowerShell enables or disables the whole anti-phishing policy (the anti-phish rule and the assigned anti-phish policy).</span></span> <span data-ttu-id="33da3-414">Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).</span><span class="sxs-lookup"><span data-stu-id="33da3-414">You can't enable or disable the default anti-phishing policy (it's always applied to all recipients).</span></span>

<span data-ttu-id="33da3-415">Per abilitare o disabilitare una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="33da3-415">To enable or disable an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

<span data-ttu-id="33da3-416">In questo esempio viene disabilitata la regola anti-phish denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="33da3-416">This example disables the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="33da3-417">In questo esempio viene abilitata la stessa regola.</span><span class="sxs-lookup"><span data-stu-id="33da3-417">This example enables same rule.</span></span>

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="33da3-418">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)</span><span class="sxs-lookup"><span data-stu-id="33da3-418">For detailed syntax and parameter information, see [Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) and [Disable-AntiPhishRule](/powershell/module/exchange/disable-antiphishrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a><span data-ttu-id="33da3-419">Usare PowerShell per impostare la priorità delle regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="33da3-419">Use PowerShell to set the priority of anti-phish rules</span></span>

<span data-ttu-id="33da3-p156">Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole predefinite, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole (priorità da 0 a 4) e si modifica la priorità di una regola a 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.</span><span class="sxs-lookup"><span data-stu-id="33da3-p156">The highest priority value you can set on a rule is 0. The lowest value you can set depends on the number of rules. For example, if you have five rules, you can use the priority values 0 through 4. Changing the priority of an existing rule can have a cascading effect on other rules. For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="33da3-425">Per impostare la priorità di una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="33da3-425">To set the priority of an anti-phish rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="33da3-p157">Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).</span><span class="sxs-lookup"><span data-stu-id="33da3-p157">This example sets the priority of the rule named Marketing Department to 2. All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="33da3-428">**Note**:</span><span class="sxs-lookup"><span data-stu-id="33da3-428">**Notes**:</span></span>

- <span data-ttu-id="33da3-429">Per impostare la priorità di una nuova regola al momento della creazione, utilizzare invece il parametro _Priority_ nel cmdlet **New-AntiPhishRule.**</span><span class="sxs-lookup"><span data-stu-id="33da3-429">To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-AntiPhishRule** cmdlet instead.</span></span>

- <span data-ttu-id="33da3-430">Il criterio anti-phish predefinito non dispone di una regola anti-phish corrispondente e ha sempre il valore di priorità non modificabile **Lowest**.</span><span class="sxs-lookup"><span data-stu-id="33da3-430">The default anti-phish policy doesn't have a corresponding anti-phish rule, and it always has the unmodifiable priority value **Lowest**.</span></span>

### <a name="use-powershell-to-remove-anti-phish-policies"></a><span data-ttu-id="33da3-431">Usare PowerShell per rimuovere i criteri anti-phish</span><span class="sxs-lookup"><span data-stu-id="33da3-431">Use PowerShell to remove anti-phish policies</span></span>

<span data-ttu-id="33da3-432">Quando si utilizza PowerShell per rimuovere un criterio anti-phish, la regola anti-phish corrispondente non viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="33da3-432">When you use PowerShell to remove an anti-phish policy, the corresponding anti-phish rule isn't removed.</span></span>

<span data-ttu-id="33da3-433">Per rimuovere un criterio anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="33da3-433">To remove an anti-phish policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="33da3-434">In questo esempio viene rimosso il criterio anti-phish denominato Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="33da3-434">This example removes the anti-phish policy named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

<span data-ttu-id="33da3-435">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)</span><span class="sxs-lookup"><span data-stu-id="33da3-435">For detailed syntax and parameter information, see [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-remove-anti-phish-rules"></a><span data-ttu-id="33da3-436">Usare PowerShell per rimuovere le regole anti-phish</span><span class="sxs-lookup"><span data-stu-id="33da3-436">Use PowerShell to remove anti-phish rules</span></span>

<span data-ttu-id="33da3-437">Quando si utilizza PowerShell per rimuovere una regola anti-phish, il criterio anti-phish corrispondente non viene rimosso.</span><span class="sxs-lookup"><span data-stu-id="33da3-437">When you use PowerShell to remove an anti-phish rule, the corresponding anti-phish policy isn't removed.</span></span>

<span data-ttu-id="33da3-438">Per rimuovere una regola anti-phish in PowerShell, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="33da3-438">To remove an anti-phish rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

<span data-ttu-id="33da3-439">In questo esempio viene rimossa la regola anti-phish denominata Marketing Department.</span><span class="sxs-lookup"><span data-stu-id="33da3-439">This example removes the anti-phish rule named Marketing Department.</span></span>

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

<span data-ttu-id="33da3-440">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)</span><span class="sxs-lookup"><span data-stu-id="33da3-440">For detailed syntax and parameter information, see [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="33da3-441">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="33da3-441">How do you know these procedures worked?</span></span>

<span data-ttu-id="33da3-442">Per verificare di aver configurato correttamente i criteri anti-phishing in Defender per Office 365, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="33da3-442">To verify that you've successfully configured anti-phishing policies in Defender for Office 365, do any of the following steps:</span></span>

- <span data-ttu-id="33da3-443">Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**</span><span class="sxs-lookup"><span data-stu-id="33da3-443">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Anti-phishing**.</span></span> <span data-ttu-id="33da3-444">Verificare l'elenco dei criteri, i **relativi valori status** e i relativi valori **Priority.**</span><span class="sxs-lookup"><span data-stu-id="33da3-444">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="33da3-445">Per visualizzare altri dettagli, selezionare il criterio dall'elenco facendo clic sul nome e visualizzando i dettagli nel riquadro a comparsa visualizzato.</span><span class="sxs-lookup"><span data-stu-id="33da3-445">To view more details, select the policy from the list by clicking on the name and viewing the details in the flyout that appears.</span></span>

- <span data-ttu-id="33da3-446">In Exchange Online PowerShell, sostituire con il nome del criterio o della regola ed eseguire il \<Name\> comando seguente e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="33da3-446">In Exchange Online PowerShell, replace \<Name\> with the name of the policy or rule, and run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
