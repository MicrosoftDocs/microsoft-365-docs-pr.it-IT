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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Informazioni su come rimuovere un vecchio dominio da Microsoft 365 e spostare gli utenti e i gruppi in un altro dominio.
ms.openlocfilehash: ef0209d6ccb7534745172585fe599f627e386cb4
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140406"
---
# <a name="remove-a-domain"></a><span data-ttu-id="56ef6-103">Rimuovere un dominio</span><span class="sxs-lookup"><span data-stu-id="56ef6-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="56ef6-104">L'interfaccia di amministrazione cambia.</span><span class="sxs-lookup"><span data-stu-id="56ef6-104">The admin center is changing.</span></span> <span data-ttu-id="56ef6-105">Se l'esperienza non corrisponde ai dettagli presentati, vedere [About The New Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="56ef6-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="56ef6-106">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="56ef6-107">Si sta rimuovendo il dominio perché si desidera aggiungerlo a un piano di sottoscrizione di Microsoft 365 diverso?</span><span class="sxs-lookup"><span data-stu-id="56ef6-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="56ef6-108">Oppure si desidera semplicemente annullare l'abbonamento?</span><span class="sxs-lookup"><span data-stu-id="56ef6-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="56ef6-109">È possibile [modificare il piano o la sottoscrizione](../../commerce/subscriptions/switch-to-a-different-plan.md) oppure [annullare l'abbonamento](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="56ef6-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="56ef6-110">Passaggio 1: spostare gli utenti in un altro dominio</span><span class="sxs-lookup"><span data-stu-id="56ef6-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="56ef6-111">Spostare gli utenti</span><span class="sxs-lookup"><span data-stu-id="56ef6-111">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="56ef6-112">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="56ef6-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="56ef6-113">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Amministrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="56ef6-113">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="56ef6-114">> Selezionare **utenti** **attivi**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-114">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="56ef6-115">Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="56ef6-115">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="56ef6-116">Selezionare **altre opzioni** (**...**), nella parte superiore della pagina e quindi scegliere **Cambia domini**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-116">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="56ef6-117">Nel riquadro **Cambia domini** , selezionare un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="56ef6-117">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="56ef6-p103">È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.</span><span class="sxs-lookup"><span data-stu-id="56ef6-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="56ef6-120">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="56ef6-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="56ef6-121">> Selezionare **utenti** **attivi**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-121">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="56ef6-122">Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="56ef6-122">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="56ef6-123">Nella parte superiore della pagina, scegliere **altri** > **domini di modifica**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-123">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="56ef6-124">Nel riquadro **modifica domini** selezionare un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="56ef6-124">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="56ef6-p104">È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.</span><span class="sxs-lookup"><span data-stu-id="56ef6-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="56ef6-127">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="56ef6-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="56ef6-128">> Selezionare **utenti** **attivi**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-128">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="56ef6-129">Selezionare le caselle accanto ai nomi di tutti gli utenti che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="56ef6-129">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="56ef6-130">Nella parte superiore della pagina, scegliere **altri** > **domini di modifica**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-130">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="56ef6-131">Nel riquadro **modifica domini** selezionare un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="56ef6-131">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="56ef6-p105">È necessario eseguire questa operazione anche per se stessi se si usa il dominio che si intende rimuovere. Quando si modifica il dominio per il proprio account, per proseguire è necessario disconnettersi e accedere di nuovo con il nuovo dominio scelto.</span><span class="sxs-lookup"><span data-stu-id="56ef6-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="56ef6-134">Sposta te stesso</span><span class="sxs-lookup"><span data-stu-id="56ef6-134">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="56ef6-135">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="56ef6-135">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="56ef6-136">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>.</span><span class="sxs-lookup"><span data-stu-id="56ef6-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="56ef6-137">Passare a **Users** \> utenti **attivi**e selezionare l'account dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="56ef6-137">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="56ef6-138">Nella scheda **account** selezionare **Gestisci nome utente**e quindi scegliere un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="56ef6-138">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="56ef6-139">Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Esci**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-139">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="56ef6-140">Accedere con il nuovo dominio e la stessa password.</span><span class="sxs-lookup"><span data-stu-id="56ef6-140">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="56ef6-141">È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="56ef6-141">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="56ef6-142">Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="56ef6-142">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="56ef6-143">Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="56ef6-143">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="56ef6-144">Vai a **Users** \> utenti **attivi**e seleziona il tuo nome nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="56ef6-144">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="56ef6-145">Nella sezione **nome utente/indirizzo di posta elettronica** selezionare **modifica**e quindi scegliere un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="56ef6-145">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="56ef6-146">Selezionare **Imposta come Primary** > **Save** > **Close**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-146">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="56ef6-147">Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Esci**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-147">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="56ef6-148">Accedere con il nuovo dominio e la stessa password.</span><span class="sxs-lookup"><span data-stu-id="56ef6-148">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="56ef6-149">È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="56ef6-149">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="56ef6-150">Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="56ef6-150">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="56ef6-151">Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="56ef6-151">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="56ef6-152">Vai a **Users** \> utenti **attivi**e seleziona il tuo nome nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="56ef6-152">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="56ef6-153">Nella sezione **nome utente/indirizzo di posta elettronica** selezionare **modifica**e quindi scegliere un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="56ef6-153">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="56ef6-154">Selezionare **Imposta come Primary** > **Save** > **Close**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-154">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="56ef6-155">Nella parte superiore, seleziona il nome dell'account, quindi seleziona **Esci**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-155">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="56ef6-156">Accedere con il nuovo dominio e la stessa password.</span><span class="sxs-lookup"><span data-stu-id="56ef6-156">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="56ef6-157">È anche possibile usare PowerShell per trasferire gli utenti in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="56ef6-157">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="56ef6-158">Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="56ef6-158">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="56ef6-159">Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="56ef6-159">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="56ef6-160">Passaggio 2: spostare i gruppi in un altro dominio</span><span class="sxs-lookup"><span data-stu-id="56ef6-160">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="56ef6-161">Nell'interfaccia di amministrazione, andare alla <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> \> pagina **gruppi.**</span><span class="sxs-lookup"><span data-stu-id="56ef6-161">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="56ef6-162">Selezionare il nome del gruppo, quindi nella scheda **generale** sotto **indirizzo di posta elettronica, primario**, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-162">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="56ef6-163">Utilizzare l'elenco a discesa per scegliere un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="56ef6-163">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="56ef6-164">Selezionare **Salva**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-164">Select **Save**, then **Close**.</span></span> <span data-ttu-id="56ef6-165">Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="56ef6-165">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="56ef6-166">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>, andare alla **Groups** > pagina **gruppi.**</span><span class="sxs-lookup"><span data-stu-id="56ef6-166">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="56ef6-167">Selezionare il nome del gruppo e quindi fare clic su **modifica** accanto a **nome**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-167">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="56ef6-168">Utilizzare l'elenco a discesa per scegliere un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="56ef6-168">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="56ef6-169">Selezionare **Salva**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-169">Select **Save**, then **Close**.</span></span> <span data-ttu-id="56ef6-170">Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="56ef6-170">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="56ef6-171">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>, andare alla **Groups** > pagina **gruppi.**</span><span class="sxs-lookup"><span data-stu-id="56ef6-171">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="56ef6-172">Selezionare il nome del gruppo e quindi fare clic su **modifica** accanto a **nome**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-172">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="56ef6-173">Utilizzare l'elenco a discesa per scegliere un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="56ef6-173">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="56ef6-174">Selezionare **Salva**, quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-174">Select **Save**, then **Close**.</span></span> <span data-ttu-id="56ef6-175">Ripetere l'operazione per tutti i gruppi o le liste di distribuzione associate al dominio che si vuole rimuovere.</span><span class="sxs-lookup"><span data-stu-id="56ef6-175">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="56ef6-176">Passaggio 3: rimuovere il dominio precedente</span><span class="sxs-lookup"><span data-stu-id="56ef6-176">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="56ef6-177">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="56ef6-177">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="56ef6-178">Nell'interfaccia di amministrazione, andare alla pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domini</a> di **installazione** \> .</span><span class="sxs-lookup"><span data-stu-id="56ef6-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="56ef6-179">Nell'interfaccia di amministrazione, andare alla pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domini</a> di **installazione** \> .</span><span class="sxs-lookup"><span data-stu-id="56ef6-179">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="56ef6-180">Nella pagina **Domains** selezionare il dominio che si desidera rimuovere.</span><span class="sxs-lookup"><span data-stu-id="56ef6-180">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="56ef6-181">Nel riquadro a destra, selezionare **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-181">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="56ef6-182">Seguire le istruzioni aggiuntive e quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="56ef6-182">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="56ef6-183">Quanto ci vuole per rimuovere un dominio?</span><span class="sxs-lookup"><span data-stu-id="56ef6-183">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="56ef6-184">La rimozione di un dominio in molti luoghi come gruppi di sicurezza, liste di distribuzione, utenti e gruppi di Microsoft 365 può richiedere meno di 5 minuti a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56ef6-184">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="56ef6-185">Se sono presenti molti riferimenti che usano il dominio, la rimozione può richiedere diverse ore (un giorno).</span><span class="sxs-lookup"><span data-stu-id="56ef6-185">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="56ef6-p113">Se ci sono centinaia o migliaia di utenti, usare PowerShell per eseguire query per tutti gli utenti e spostarli in un altro dominio. In caso contrario, alcuni utenti potrebbero risultare mancanti nell'interfaccia utente e quindi, quando si rimuove il dominio, non sarà possibile spostarli e non si riuscirà a individuare la causa del problema. Per altre informazioni, vedere [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Per impostare il dominio predefinito, usare [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="56ef6-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="56ef6-190">Serve ulteriore assistenza?</span><span class="sxs-lookup"><span data-stu-id="56ef6-190">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="56ef6-191">Non si riesce a rimuovere il dominio [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) dall'account.</span><span class="sxs-lookup"><span data-stu-id="56ef6-191">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="56ef6-p114">Il problema persiste? Potrebbe essere necessario rimuovere manualmente il dominio. [Contattare il supporto](../contact-support-for-business-products.md) per ottenere assistenza.</span><span class="sxs-lookup"><span data-stu-id="56ef6-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="56ef6-195">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="56ef6-195">Related articles</span></span>

[<span data-ttu-id="56ef6-196">Domande frequenti sui domini</span><span class="sxs-lookup"><span data-stu-id="56ef6-196">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="56ef6-197">Ottenere assistenza per i domini di Office 365</span><span class="sxs-lookup"><span data-stu-id="56ef6-197">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="56ef6-198">Passare a un piano di Microsoft 365 per le aziende diverso</span><span class="sxs-lookup"><span data-stu-id="56ef6-198">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="56ef6-199">Annullare l'abbonamento</span><span class="sxs-lookup"><span data-stu-id="56ef6-199">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
