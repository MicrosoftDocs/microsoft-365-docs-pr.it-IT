---
title: Convertire una cassetta postale utente in una cassetta postale condivisa
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Informazioni su come convertire una cassetta postale privata in una cassetta postale condivisa a cui è possibile accedere da più utenti. '
ms.openlocfilehash: 481707b9d60d37b1d80d822467d17f66750f4f13
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42253052"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="a0298-103">Convertire una cassetta postale utente in una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="a0298-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="a0298-104">Quando si converte la cassetta postale di un utente in cassetta condivisa, vengono mantenuti tutti gli elementi di posta elettronica e del calendario esistenti.</span><span class="sxs-lookup"><span data-stu-id="a0298-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="a0298-105">L'unica differenza è che ora si trovano in una cassetta postale condivisa, cui potranno accedere diversi utenti invece di uno solo.</span><span class="sxs-lookup"><span data-stu-id="a0298-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="a0298-106">In un secondo momento, è possibile convertire una cassetta postale condivisa di nuovo in una cassetta postale utente (privata).</span><span class="sxs-lookup"><span data-stu-id="a0298-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="a0298-107">**Di seguito sono riportate alcune informazioni importanti che è necessario conoscere:**</span><span class="sxs-lookup"><span data-stu-id="a0298-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="a0298-108">La cassetta postale utente che si sta convertendo richiede una licenza assegnata prima di convertirla in una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="a0298-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="a0298-109">In caso contrario, l'opzione per convertire la cassetta postale non sarà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="a0298-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="a0298-110">Se la licenza è stata rimossa, aggiungerla di nuovo in modo da poter convertire la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="a0298-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="a0298-111">Dopo aver convertito la cassetta postale in una condivisa, è possibile rimuovere la licenza dall'account dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a0298-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="a0298-p103">Le cassette postali condivise possono contenere fino a 50 GB di dati senza alcuna licenza assegnata. Perché possano contenere ancora più dati, è necessario assegnarvi una licenza. Potrebbe essere necessario eliminare diversi messaggi di posta elettronica di grandi dimensioni, ad esempio quelli con allegati, dalla cassetta postale condivisa per ridurne le dimensioni e rimuovere la licenza.</span><span class="sxs-lookup"><span data-stu-id="a0298-p103">Shared mailboxes can have up to 50GB of data without a license assigned to them. To hold more data than that, you need a license assigned to it. You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="a0298-p104">Non eliminare il vecchio account utente. Sarà necessario per l'ancoraggio della cassetta postale condivisa. Se l'account utente è già stato eliminato, vedere [Convertire la cassetta postale di un utente eliminato](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="a0298-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="a0298-118">Le regole sono intatte dopo la conversione della cassetta postale in una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="a0298-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="a0298-119">Utilizzare l'interfaccia di amministrazione di Exchange per convertire una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="a0298-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="a0298-120">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="a0298-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="a0298-121">Selezionare le **cassette postali** **destinatari** \> .</span><span class="sxs-lookup"><span data-stu-id="a0298-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="a0298-122">Selezionare la cassetta postale utente.</span><span class="sxs-lookup"><span data-stu-id="a0298-122">Select the user mailbox.</span></span> <span data-ttu-id="a0298-123">In **Converti in cassetta postale condivisa**, selezionare **Converti**.</span><span class="sxs-lookup"><span data-stu-id="a0298-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="a0298-124">Se la cassetta postale è più piccola di 50 GB, è possibile rimuovere la [licenza dall'utente](../manage/remove-licenses-from-users.md) e smettere di pagarne i costi associati.</span><span class="sxs-lookup"><span data-stu-id="a0298-124">If the mailbox is smaller than 50GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="a0298-125">Non eliminare la vecchia cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a0298-125">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="a0298-126">Sarà necessaria come ancoraggio per la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="a0298-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="a0298-127">Se si converte la cassetta postale di un dipendente che lascia l'organizzazione, è necessario eseguire ulteriori passaggi per verificare che non siano più in grado di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a0298-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="a0298-128">Per ulteriori informazioni, vedere [rimuovere un ex dipendente da Office 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="a0298-128">Please see [Remove a former employee from Office 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="a0298-129">Per tutti gli altri elementi necessari per conoscere le cassette postali condivise, vedere [informazioni sulle cassette postali condivise](about-shared-mailboxes.md) e [creare una cassetta postale condivisa](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="a0298-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="a0298-130">Utilizzare l'interfaccia di amministrazione di Microsoft 365 per convertire una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="a0298-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a0298-131">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="a0298-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="a0298-132">Selezionare il nome dell'utente di cui si desidera convertire la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="a0298-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="a0298-133">Reimpostare la password dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a0298-133">Reset the user's password.</span></span>

> [!NOTE]
> <span data-ttu-id="a0298-134">Non è necessario reimpostare la password dell'utente durante la conversione delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="a0298-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="a0298-135">Tuttavia, se la password non viene reimpostata, **il nome utente e la password originali continuano a funzionare** dopo che la conversione della cassetta postale è terminata.</span><span class="sxs-lookup"><span data-stu-id="a0298-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="a0298-136">Nella scheda **posta** , in **altre azioni**, selezionare **Converti in cassetta postale condivisa**.</span><span class="sxs-lookup"><span data-stu-id="a0298-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="a0298-137">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="a0298-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="a0298-138">Selezionare l'utente di cui si desidera convertire la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="a0298-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="a0298-139">Nel riquadro destro espandere Impostazioni di **posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="a0298-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="a0298-140">Accanto a **altre impostazioni**, selezionare **Converti in cassetta postale condivisa**.</span><span class="sxs-lookup"><span data-stu-id="a0298-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a0298-141">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="a0298-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="a0298-142">Selezionare l'utente di cui si desidera convertire la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="a0298-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="a0298-143">Nel riquadro destro espandere Impostazioni di **posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="a0298-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="a0298-144">Accanto a **altre impostazioni**, selezionare **Converti in cassetta postale condivisa**.</span><span class="sxs-lookup"><span data-stu-id="a0298-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="a0298-145">Se la cassetta postale è più piccola di 50 GB, è possibile [rimuovere la licenza dall'utente](../manage/remove-licenses-from-users.md)e smettere di pagarla.</span><span class="sxs-lookup"><span data-stu-id="a0298-145">If the mailbox is smaller than 50GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="a0298-146">Non eliminare la vecchia cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a0298-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="a0298-147">Sarà necessaria come ancoraggio per la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="a0298-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="a0298-148">Se si converte la cassetta postale di un dipendente che lascia l'organizzazione, è necessario eseguire ulteriori passaggi per verificare che non siano più in grado di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a0298-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="a0298-149">Vedere [rimuovere un ex dipendente da Office 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="a0298-149">See [Remove a former employee from Office 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="a0298-150">Per tutti gli altri elementi necessari per conoscere le cassette postali condivise, vedere [informazioni sulle cassette postali condivise](about-shared-mailboxes.md) e [creare una cassetta postale condivisa](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="a0298-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="a0298-151">Convertire la cassetta postale di un utente eliminato</span><span class="sxs-lookup"><span data-stu-id="a0298-151">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="a0298-p111">Si supponga di aver eliminato un account utente e di volerne convertire la vecchia cassetta postale in cassetta postale condivisa. Ecco cosa fare:</span><span class="sxs-lookup"><span data-stu-id="a0298-p111">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="a0298-154">[Ripristinare l'account dell'utente](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="a0298-154">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="a0298-155">Assicurarsi che all'account sia assegnata una licenza di Office 365.</span><span class="sxs-lookup"><span data-stu-id="a0298-155">Make sure an Office 365 license is assigned to it.</span></span>

3. <span data-ttu-id="a0298-156">Reimpostare la password dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a0298-156">Reset the user's password.</span></span>
    
4. <span data-ttu-id="a0298-157">Attendere 20-30 minuti perché la cassetta postale venga ricreata.</span><span class="sxs-lookup"><span data-stu-id="a0298-157">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="a0298-158">Seguire ora le istruzioni in questa pagina per convertire la cassetta postale dell'account utente in cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="a0298-158">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="a0298-159">Al termine, è possibile rimuovere la licenza dalla cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a0298-159">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="a0298-160">Non eliminare la vecchia cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a0298-160">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="a0298-161">Sarà necessaria come ancoraggio per la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="a0298-161">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="a0298-162">Aggiungere membri alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="a0298-162">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="a0298-163">Convertire di nuovo una cassetta postale condivisa in una cassetta postale (privata) dell'utente</span><span class="sxs-lookup"><span data-stu-id="a0298-163">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="a0298-164">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="a0298-164">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="a0298-165">Selezionare i **destinatari** \> **condivisi**.</span><span class="sxs-lookup"><span data-stu-id="a0298-165">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="a0298-166">Selezionare la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="a0298-166">Select the shared mailbox.</span></span> <span data-ttu-id="a0298-167">In **Converti in cassetta postale normale**selezionare **Converti**.</span><span class="sxs-lookup"><span data-stu-id="a0298-167">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="a0298-168">Tornare all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="a0298-168">Go back to the admin center.</span></span> <span data-ttu-id="a0298-169">In **Utenti** scegliere l'account utente associato alla vecchia cassetta postale utente.</span><span class="sxs-lookup"><span data-stu-id="a0298-169">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="a0298-170">Assegnare una licenza all'account e reimpostare la password.</span><span class="sxs-lookup"><span data-stu-id="a0298-170">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="a0298-p115">Saranno necessari alcuni minuti prima che la cassetta postale venga configurata, ma al termine, l'utente che usa l'account sarà pronto per iniziare. All'accesso, l'utente visualizzerà gli elementi di posta elettronica e del calendario che erano presenti nella cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="a0298-p115">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="a0298-173">Convertire la cassetta postale di un utente in un ambiente ibrido</span><span class="sxs-lookup"><span data-stu-id="a0298-173">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="a0298-174">Se questa cassetta postale condivisa si trova in un ambiente ibrido, è **consigliabile** (è quasi necessario) riportare la cassetta postale dell'utente in locale, convertire la cassetta postale utente in una cassetta postale condivisa e quindi riportare la cassetta postale condivisa nel cloud.</span><span class="sxs-lookup"><span data-stu-id="a0298-174">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span>

<span data-ttu-id="a0298-175">Ecco perché: se si converte la cassetta postale nel cloud, è possibile convertirla, ma la cassetta postale è ancora in uso, in quanto la nuova realtà non viene sincronizzata di nuovo in locale.</span><span class="sxs-lookup"><span data-stu-id="a0298-175">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="a0298-176">In genere, non si tratta di un problema, ma ci sono alcuni scenari in cui gli attributi locali (che pensano che la cassetta postale è la cassetta postale dell'utente) possono sovrascrivere le nuove versioni cloud di tali attributi e, di conseguenza, la cassetta postale potrebbe riconvertirsi.</span><span class="sxs-lookup"><span data-stu-id="a0298-176">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="a0298-177">Questo è un problema perché le cassette postali degli utenti richiedono licenze **o sono eliminate temporaneamente dopo 30 giorni**.</span><span class="sxs-lookup"><span data-stu-id="a0298-177">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="a0298-178">Sono state affrontate la maggior parte dei motivi per cui questo accade ma può comunque verificarsi, anche se raramente.</span><span class="sxs-lookup"><span data-stu-id="a0298-178">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="a0298-179">È consigliabile essere sicuri e riportare la cassetta postale in locale.</span><span class="sxs-lookup"><span data-stu-id="a0298-179">It's best to be safe and move the mailbox back to on-premises.</span></span>

> [!NOTE]
> <span data-ttu-id="a0298-180">Se si è parte di gestione organizzazione o Gestione destinatari, è possibile utilizzare Exchange Management Shell per modificare una cassetta postale utente in una cassetta postale condivisa locale.</span><span class="sxs-lookup"><span data-stu-id="a0298-180">If you are a part of Organization Management or Recipient Management, you can use the  Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="a0298-181">Ad esempio, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="a0298-181">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="a0298-182">Per le istanze in cui le [cassette postali condivise sono inaspettatamente convertite nelle cassette postali degli utenti](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di) , vedere la soluzione alternativa</span><span class="sxs-lookup"><span data-stu-id="a0298-182">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="a0298-183">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="a0298-183">Related articles</span></span>

[<span data-ttu-id="a0298-184">Informazioni sulle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="a0298-184">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="a0298-185">Creare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="a0298-185">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="a0298-186">Configurare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="a0298-186">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="a0298-187">Rimuovere una licenza da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="a0298-187">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="a0298-188">Risolvere i problemi relativi alle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="a0298-188">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
