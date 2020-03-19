---
title: Rimuovere un dominio da Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Informazioni su come rimuovere un vecchio dominio da Office 365 e spostare gli utenti e i gruppi in un altro dominio.
ms.openlocfilehash: efbd49daa28b5d15989e1531929cb2d9355aeb8f
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857428"
---
# <a name="remove-a-domain-from-office-365"></a><span data-ttu-id="145be-103">Rimuovere un dominio da Office 365</span><span class="sxs-lookup"><span data-stu-id="145be-103">Remove a domain from Office 365</span></span>

<span data-ttu-id="145be-104">Collaboratori: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span><span class="sxs-lookup"><span data-stu-id="145be-104">Contributors: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span></span>
  
 <span data-ttu-id="145be-105">**Se non si trovano le informazioni desiderate, vedere le [domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="145be-105">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="145be-p101">Se si rimuove il dominio perché lo si vuole aggiungere a un piano di abbonamento a Office 365 diverso o se si vuole annullare semplicemente l'abbonamento, è possibile [cambiare piano o abbonamento](../../commerce/subscriptions/switch-to-a-different-plan.md) oppure [annullare l'abbonamento](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="145be-p101">Are you removing your domain because you want to add it to a different Office 365 subscription plan? Or do you just want to cancel your subscription? You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="145be-109">Passaggio 1: spostare gli utenti in un altro dominio</span><span class="sxs-lookup"><span data-stu-id="145be-109">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="145be-110">Spostare gli utenti</span><span class="sxs-lookup"><span data-stu-id="145be-110">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="145be-111">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="145be-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="145be-112">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Amministrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="145be-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="145be-113">> Selezionare **utenti** **attivi**.</span><span class="sxs-lookup"><span data-stu-id="145be-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="145be-114">Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="145be-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="145be-115">Selezionare **altre opzioni** (**...**), nella parte superiore della pagina e quindi scegliere **Cambia domini**.</span><span class="sxs-lookup"><span data-stu-id="145be-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="145be-116">Nel riquadro **Cambia domini** , selezionare un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="145be-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="145be-p102">È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.</span><span class="sxs-lookup"><span data-stu-id="145be-p102">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="145be-119">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="145be-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="145be-120">> Selezionare **utenti** **attivi**.</span><span class="sxs-lookup"><span data-stu-id="145be-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="145be-121">Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="145be-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="145be-122">Nella parte superiore della pagina, scegliere **altri** > **domini di modifica**.</span><span class="sxs-lookup"><span data-stu-id="145be-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="145be-123">Nel riquadro **modifica domini** selezionare un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="145be-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="145be-p103">È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.</span><span class="sxs-lookup"><span data-stu-id="145be-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="145be-126">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="145be-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="145be-127">> Selezionare **utenti** **attivi**.</span><span class="sxs-lookup"><span data-stu-id="145be-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="145be-128">Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="145be-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="145be-129">Nella parte superiore della pagina, scegliere **altri** > **domini di modifica**.</span><span class="sxs-lookup"><span data-stu-id="145be-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="145be-130">Nel riquadro **modifica domini** selezionare un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="145be-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="145be-p104">È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.</span><span class="sxs-lookup"><span data-stu-id="145be-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="145be-133">Sposta te stesso</span><span class="sxs-lookup"><span data-stu-id="145be-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="145be-134">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="145be-134">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="145be-135">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="145be-135">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="145be-136">Passare a **Users** \> utenti **attivi**e selezionare l'account dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="145be-136">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="145be-137">Nella scheda **account** selezionare **Gestisci nome utente**e quindi scegliere un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="145be-137">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="145be-138">Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Esci**.</span><span class="sxs-lookup"><span data-stu-id="145be-138">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="145be-139">Accedere con il nuovo dominio e la stessa password.</span><span class="sxs-lookup"><span data-stu-id="145be-139">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="145be-140">È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="145be-140">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="145be-141">Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="145be-141">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="145be-142">Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="145be-142">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="145be-143">Vai a **Users** \> utenti **attivi**e seleziona il tuo nome nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="145be-143">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="145be-144">Nella sezione **nome utente/indirizzo di posta elettronica** selezionare **modifica**e quindi scegliere un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="145be-144">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="145be-145">Selezionare **Imposta come Primary** > **Save** > **Close**.</span><span class="sxs-lookup"><span data-stu-id="145be-145">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="145be-146">Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Esci**.</span><span class="sxs-lookup"><span data-stu-id="145be-146">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="145be-147">Accedere con il nuovo dominio e la stessa password.</span><span class="sxs-lookup"><span data-stu-id="145be-147">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="145be-148">È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="145be-148">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="145be-149">Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="145be-149">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="145be-150">Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="145be-150">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="145be-151">Vai a **Users** \> utenti **attivi**e seleziona il tuo nome nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="145be-151">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="145be-152">Nella sezione **nome utente/indirizzo di posta elettronica** selezionare **modifica**e quindi scegliere un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="145be-152">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="145be-153">Selezionare **Imposta come Primary** > **Save** > **Close**.</span><span class="sxs-lookup"><span data-stu-id="145be-153">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="145be-154">Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Esci**.</span><span class="sxs-lookup"><span data-stu-id="145be-154">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="145be-155">Accedere con il nuovo dominio e la stessa password.</span><span class="sxs-lookup"><span data-stu-id="145be-155">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="145be-156">È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="145be-156">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="145be-157">Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="145be-157">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="145be-158">Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="145be-158">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="145be-159">Passaggio 2: spostare i gruppi in un altro dominio</span><span class="sxs-lookup"><span data-stu-id="145be-159">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="145be-160">Nell'interfaccia di amministrazione, andare alla <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> \> pagina **gruppi.**</span><span class="sxs-lookup"><span data-stu-id="145be-160">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="145be-161">Selezionare il nome del gruppo, quindi nella scheda **generale** sotto **indirizzo di posta elettronica, primario**, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="145be-161">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="145be-162">Utilizzare l'elenco a discesa per scegliere un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="145be-162">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="145be-163">Selezionare **Salva**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="145be-163">Select **Save**, then **Close**.</span></span> <span data-ttu-id="145be-164">Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="145be-164">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="145be-165">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>, andare alla **Groups** > pagina **gruppi.**</span><span class="sxs-lookup"><span data-stu-id="145be-165">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="145be-166">Selezionare il nome del gruppo e quindi fare clic su **modifica** accanto a **nome**.</span><span class="sxs-lookup"><span data-stu-id="145be-166">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="145be-167">Utilizzare l'elenco a discesa per scegliere un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="145be-167">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="145be-168">Selezionare **Salva**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="145be-168">Select **Save**, then **Close**.</span></span> <span data-ttu-id="145be-169">Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="145be-169">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="145be-170">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>, andare alla **Groups** > pagina **gruppi.**</span><span class="sxs-lookup"><span data-stu-id="145be-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="145be-171">Selezionare il nome del gruppo e quindi fare clic su **modifica** accanto a **nome**.</span><span class="sxs-lookup"><span data-stu-id="145be-171">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="145be-172">Utilizzare l'elenco a discesa per scegliere un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="145be-172">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="145be-173">Selezionare **Salva**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="145be-173">Select **Save**, then **Close**.</span></span> <span data-ttu-id="145be-174">Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="145be-174">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="145be-175">Passaggio 3: rimuovere il dominio precedente</span><span class="sxs-lookup"><span data-stu-id="145be-175">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="145be-176">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="145be-176">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="145be-177">Nell'interfaccia di amministrazione, andare alla pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domini</a> di **installazione** \> .</span><span class="sxs-lookup"><span data-stu-id="145be-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="145be-178">Nell'interfaccia di amministrazione, andare alla pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domini</a> di **installazione** \> .</span><span class="sxs-lookup"><span data-stu-id="145be-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="145be-179">Nella pagina **Domains** selezionare il dominio che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="145be-179">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="145be-180">Nel riquadro a destra, selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="145be-180">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="145be-181">Seguire le istruzioni aggiuntive e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="145be-181">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="145be-182">Quanto ci vuole per rimuovere un dominio?</span><span class="sxs-lookup"><span data-stu-id="145be-182">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="145be-183">La rimozione di un dominio in molti luoghi, ad esempio 365 i gruppi di sicurezza, le liste di distribuzione, gli utenti e i gruppi di Office 365, può richiedere meno di 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="145be-183">It can take as little as 5 minutes for Office 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Office 365 groups.</span></span> <span data-ttu-id="145be-184">Se sono presenti molti riferimenti che usano il dominio, la rimozione può richiedere diverse ore (un giorno).</span><span class="sxs-lookup"><span data-stu-id="145be-184">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="145be-p112">Se ci sono centinaia o migliaia di utenti, usare PowerShell per eseguire query per tutti gli utenti e spostarli in un altro dominio. In caso contrario, alcuni utenti potrebbero risultare mancanti nell'interfaccia utente e quindi, quando si rimuove il dominio, non sarà possibile spostarli e non si riuscirà a individuare la causa del problema. Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="145be-p112">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="145be-189">Serve ulteriore assistenza?</span><span class="sxs-lookup"><span data-stu-id="145be-189">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="145be-190">Non si riesce a rimuovere il dominio [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) dall'account.</span><span class="sxs-lookup"><span data-stu-id="145be-190">You can't remove the [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) domain from your account.</span></span>
  
<span data-ttu-id="145be-p113">Il problema persiste? Potrebbe essere necessario rimuovere manualmente il dominio. [Contattare il supporto](../contact-support-for-business-products.md) per ottenere assistenza.</span><span class="sxs-lookup"><span data-stu-id="145be-p113">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="145be-194">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="145be-194">Related articles</span></span>

[<span data-ttu-id="145be-195">Domande frequenti sui domini</span><span class="sxs-lookup"><span data-stu-id="145be-195">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="145be-196">Ottenere assistenza per i domini di Office 365</span><span class="sxs-lookup"><span data-stu-id="145be-196">Get help with Office 365 domains</span></span>](get-help-with-domains.yml)

[<span data-ttu-id="145be-197">Passare a un piano di Office 365 per le aziende diverso</span><span class="sxs-lookup"><span data-stu-id="145be-197">Switch to a different Office 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="145be-198">Annullare l'abbonamento</span><span class="sxs-lookup"><span data-stu-id="145be-198">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
