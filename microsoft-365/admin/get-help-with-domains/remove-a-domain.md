---
title: Rimuovere un dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Informazioni su come rimuovere un vecchio dominio da Microsoft 365 e spostare gli utenti e i gruppi in un altro dominio.
ms.openlocfilehash: 6f5e36a897316c8cdc057a725957c54e7eb53edc
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079762"
---
# <a name="remove-a-domain"></a><span data-ttu-id="726e5-103">Rimuovere un dominio</span><span class="sxs-lookup"><span data-stu-id="726e5-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="726e5-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="726e5-104">The admin center is changing.</span></span> <span data-ttu-id="726e5-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="726e5-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="726e5-106">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="726e5-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="726e5-107">Si sta rimuovendo il dominio perché si desidera aggiungerlo a un piano di sottoscrizione di Microsoft 365 diverso?</span><span class="sxs-lookup"><span data-stu-id="726e5-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="726e5-108">Oppure si desidera semplicemente annullare l'abbonamento?</span><span class="sxs-lookup"><span data-stu-id="726e5-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="726e5-109">È possibile [modificare il piano o la sottoscrizione](../../commerce/subscriptions/switch-to-a-different-plan.md) oppure [annullare l'abbonamento](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="726e5-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="726e5-110">Passaggio 1: spostare gli utenti in un altro dominio</span><span class="sxs-lookup"><span data-stu-id="726e5-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="726e5-111">Spostare gli utenti</span><span class="sxs-lookup"><span data-stu-id="726e5-111">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="726e5-112">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Amministrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="726e5-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="726e5-113">Selezionare **utenti** > **attivi**.</span><span class="sxs-lookup"><span data-stu-id="726e5-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="726e5-114">Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="726e5-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="726e5-115">Selezionare **altre opzioni** (**...**), nella parte superiore della pagina e quindi scegliere **Cambia domini**.</span><span class="sxs-lookup"><span data-stu-id="726e5-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="726e5-116">Nel riquadro **Cambia domini** , selezionare un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="726e5-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="726e5-p103">È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.</span><span class="sxs-lookup"><span data-stu-id="726e5-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="726e5-119">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="726e5-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="726e5-120">Selezionare **utenti** > **attivi**.</span><span class="sxs-lookup"><span data-stu-id="726e5-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="726e5-121">Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="726e5-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="726e5-122">Nella parte superiore della pagina, scegliere **altri** > **domini di modifica**.</span><span class="sxs-lookup"><span data-stu-id="726e5-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="726e5-123">Nel riquadro **modifica domini** selezionare un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="726e5-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="726e5-p104">È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.</span><span class="sxs-lookup"><span data-stu-id="726e5-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="726e5-126">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="726e5-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="726e5-127">Selezionare **utenti** > **attivi**.</span><span class="sxs-lookup"><span data-stu-id="726e5-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="726e5-128">Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="726e5-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="726e5-129">Nella parte superiore della pagina, scegliere **altri** > **domini di modifica**.</span><span class="sxs-lookup"><span data-stu-id="726e5-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="726e5-130">Nel riquadro **modifica domini** selezionare un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="726e5-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="726e5-p105">È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.</span><span class="sxs-lookup"><span data-stu-id="726e5-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="726e5-133">Sposta te stesso</span><span class="sxs-lookup"><span data-stu-id="726e5-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="726e5-134">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="726e5-134">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="726e5-135">Passare a **utenti** \> **attivi**e selezionare l'account dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="726e5-135">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="726e5-136">Nella scheda **account** selezionare **Gestisci nome utente**e quindi scegliere un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="726e5-136">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="726e5-137">Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Esci**.</span><span class="sxs-lookup"><span data-stu-id="726e5-137">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="726e5-138">Accedere con il nuovo dominio e la stessa password.</span><span class="sxs-lookup"><span data-stu-id="726e5-138">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="726e5-139">È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="726e5-139">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="726e5-140">Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="726e5-140">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="726e5-141">Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="726e5-141">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="726e5-142">Vai a **utenti** \> **attivi**e seleziona il tuo nome nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="726e5-142">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="726e5-143">Nella sezione **nome utente/indirizzo di posta elettronica** selezionare **modifica**e quindi scegliere un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="726e5-143">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="726e5-144">Selezionare **Imposta come Primary** > **Save** > **Close**.</span><span class="sxs-lookup"><span data-stu-id="726e5-144">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="726e5-145">Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Esci**.</span><span class="sxs-lookup"><span data-stu-id="726e5-145">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="726e5-146">Accedere con il nuovo dominio e la stessa password.</span><span class="sxs-lookup"><span data-stu-id="726e5-146">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="726e5-147">È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="726e5-147">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="726e5-148">Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="726e5-148">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="726e5-149">Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="726e5-149">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="726e5-150">Vai a **utenti** \> **attivi**e seleziona il tuo nome nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="726e5-150">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="726e5-151">Nella sezione **nome utente/indirizzo di posta elettronica** selezionare **modifica**e quindi scegliere un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="726e5-151">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="726e5-152">Selezionare **Imposta come Primary** > **Save** > **Close**.</span><span class="sxs-lookup"><span data-stu-id="726e5-152">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="726e5-153">Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Esci**.</span><span class="sxs-lookup"><span data-stu-id="726e5-153">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="726e5-154">Accedere con il nuovo dominio e la stessa password.</span><span class="sxs-lookup"><span data-stu-id="726e5-154">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="726e5-155">È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="726e5-155">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="726e5-156">Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="726e5-156">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="726e5-157">Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="726e5-157">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="726e5-158">Passaggio 2: spostare i gruppi in un altro dominio</span><span class="sxs-lookup"><span data-stu-id="726e5-158">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="726e5-159">Nell'interfaccia di amministrazione, andare alla pagina **gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="726e5-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="726e5-160">Selezionare il nome del gruppo, quindi nella scheda **generale** sotto **indirizzo di posta elettronica, primario**, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="726e5-160">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="726e5-161">Utilizzare l'elenco a discesa per scegliere un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="726e5-161">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="726e5-162">Selezionare **Salva**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="726e5-162">Select **Save**, then **Close**.</span></span> <span data-ttu-id="726e5-163">Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="726e5-163">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="726e5-164">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>, andare alla pagina **gruppi** > **Groups** .</span><span class="sxs-lookup"><span data-stu-id="726e5-164">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="726e5-165">Selezionare il nome del gruppo e quindi fare clic su **modifica** accanto a **nome**.</span><span class="sxs-lookup"><span data-stu-id="726e5-165">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="726e5-166">Utilizzare l'elenco a discesa per scegliere un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="726e5-166">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="726e5-167">Selezionare **Salva**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="726e5-167">Select **Save**, then **Close**.</span></span> <span data-ttu-id="726e5-168">Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="726e5-168">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="726e5-169">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>, andare alla pagina **gruppi** > **Groups** .</span><span class="sxs-lookup"><span data-stu-id="726e5-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="726e5-170">Selezionare il nome del gruppo e quindi fare clic su **modifica** accanto a **nome**.</span><span class="sxs-lookup"><span data-stu-id="726e5-170">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="726e5-171">Utilizzare l'elenco a discesa per scegliere un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="726e5-171">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="726e5-172">Selezionare **Salva**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="726e5-172">Select **Save**, then **Close**.</span></span> <span data-ttu-id="726e5-173">Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="726e5-173">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="726e5-174">Passaggio 3: rimuovere il dominio precedente</span><span class="sxs-lookup"><span data-stu-id="726e5-174">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="726e5-175">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="726e5-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="726e5-176">Nell'interfaccia di amministrazione, andare alla pagina dei domini di **installazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> .</span><span class="sxs-lookup"><span data-stu-id="726e5-176">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="726e5-177">Nell'interfaccia di amministrazione, andare alla pagina dei domini di **installazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> .</span><span class="sxs-lookup"><span data-stu-id="726e5-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="726e5-178">Nella pagina **Domains** selezionare il dominio che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="726e5-178">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="726e5-179">Nel riquadro a destra, selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="726e5-179">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="726e5-180">Seguire le istruzioni aggiuntive e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="726e5-180">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="726e5-181">Quanto ci vuole per rimuovere un dominio?</span><span class="sxs-lookup"><span data-stu-id="726e5-181">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="726e5-182">La rimozione di un dominio in molti luoghi come gruppi di sicurezza, liste di distribuzione, utenti e gruppi di Microsoft 365 può richiedere meno di 5 minuti a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="726e5-182">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="726e5-183">Se sono presenti molti riferimenti che usano il dominio, la rimozione può richiedere diverse ore (un giorno).</span><span class="sxs-lookup"><span data-stu-id="726e5-183">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="726e5-p113">Se ci sono centinaia o migliaia di utenti, usare PowerShell per eseguire query per tutti gli utenti e spostarli in un altro dominio. In caso contrario, alcuni utenti potrebbero risultare mancanti nell'interfaccia utente e quindi, quando si rimuove il dominio, non sarà possibile spostarli e non si riuscirà a individuare la causa del problema. Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="726e5-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="726e5-188">Ulteriore assistenza</span><span class="sxs-lookup"><span data-stu-id="726e5-188">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="726e5-189">Non si riesce a rimuovere il dominio [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) dall'account.</span><span class="sxs-lookup"><span data-stu-id="726e5-189">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="726e5-p114">Il problema persiste? Potrebbe essere necessario rimuovere manualmente il dominio. [Contattare il supporto](../contact-support-for-business-products.md) per ottenere assistenza.</span><span class="sxs-lookup"><span data-stu-id="726e5-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="726e5-193">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="726e5-193">Related articles</span></span>

[<span data-ttu-id="726e5-194">Domande frequenti sui domini</span><span class="sxs-lookup"><span data-stu-id="726e5-194">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="726e5-195">Ottenere assistenza per i domini di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="726e5-195">Get help with Microsoft 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="726e5-196">Passare a un piano di Microsoft 365 per le aziende diverso</span><span class="sxs-lookup"><span data-stu-id="726e5-196">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="726e5-197">Annullare l'abbonamento</span><span class="sxs-lookup"><span data-stu-id="726e5-197">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
