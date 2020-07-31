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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Informazioni su come convertire una cassetta postale privata in una cassetta postale condivisa a cui è possibile accedere da più utenti. '
ms.openlocfilehash: a4b2e9ce53051feb07ea035adc0c959bbb1a0948
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521030"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="e2ed0-103">Convertire una cassetta postale utente in una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="e2ed0-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="e2ed0-104">Quando si converte la cassetta postale di un utente in cassetta condivisa, vengono mantenuti tutti gli elementi di posta elettronica e del calendario esistenti.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="e2ed0-105">L'unica differenza è che ora si trovano in una cassetta postale condivisa, cui potranno accedere diversi utenti invece di uno solo.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="e2ed0-106">In un secondo momento, è possibile convertire una cassetta postale condivisa di nuovo in una cassetta postale utente (privata).</span><span class="sxs-lookup"><span data-stu-id="e2ed0-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="e2ed0-107">**Di seguito sono riportate alcune informazioni importanti che è necessario conoscere:**</span><span class="sxs-lookup"><span data-stu-id="e2ed0-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="e2ed0-108">La cassetta postale utente che si sta convertendo richiede una licenza assegnata prima di convertirla in una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="e2ed0-109">In caso contrario, l'opzione per convertire la cassetta postale non sarà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="e2ed0-110">Se la licenza è stata rimossa, aggiungerla di nuovo in modo da poter convertire la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="e2ed0-111">Dopo aver convertito la cassetta postale in una condivisa, è possibile rimuovere la licenza dall'account dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="e2ed0-112">Le cassette postali condivise possono avere fino a 50 GB di dati senza una licenza assegnata.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="e2ed0-113">Perché possano contenere ancora più dati, è necessario assegnarvi una licenza.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="e2ed0-114">Potrebbe essere necessario eliminare diversi messaggi di posta elettronica di grandi dimensioni, ad esempio quelli con allegati, dalla cassetta postale condivisa per ridurne le dimensioni e rimuovere la licenza.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="e2ed0-p104">Non eliminare il vecchio account utente. Sarà necessario per l'ancoraggio della cassetta postale condivisa. Se l'account utente è già stato eliminato, vedere [Convertire la cassetta postale di un utente eliminato](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="e2ed0-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="e2ed0-118">Le regole sono intatte dopo la conversione della cassetta postale in una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="e2ed0-119">Utilizzare l'interfaccia di amministrazione di Exchange per convertire una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="e2ed0-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="e2ed0-120">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="e2ed0-121">Selezionare **Recipients** le \> **cassette postali**destinatari.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="e2ed0-122">Selezionare la cassetta postale utente.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-122">Select the user mailbox.</span></span> <span data-ttu-id="e2ed0-123">In **Converti in cassetta postale condivisa**, selezionare **Converti**.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="e2ed0-124">Se la cassetta postale è inferiore a 50 GB, è possibile rimuovere la [licenza dall'utente](../manage/remove-licenses-from-users.md)e smettere di pagarla.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="e2ed0-125">Non eliminare l'account dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-125">Don't delete the user's account.</span></span> <span data-ttu-id="e2ed0-126">Sarà necessaria come ancoraggio per la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="e2ed0-127">Se si converte la cassetta postale di un dipendente che lascia l'organizzazione, è necessario eseguire ulteriori passaggi per verificare che non siano più in grado di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="e2ed0-128">Per ulteriori informazioni, vedere [rimuovere un ex dipendente da Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="e2ed0-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
5. <span data-ttu-id="e2ed0-129">Per tutti gli altri elementi necessari per conoscere le cassette postali condivise, vedere [informazioni sulle cassette postali condivise](about-shared-mailboxes.md) e [creare una cassetta postale condivisa](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="e2ed0-129">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="e2ed0-130">Utilizzare l'interfaccia di amministrazione di Microsoft 365 per convertire una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="e2ed0-130">Use the Microsoft 365 admin center to convert a mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e2ed0-131">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="e2ed0-132">Selezionare il nome dell'utente di cui si desidera convertire la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-132">Select the name of the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="e2ed0-133">Reimpostare la password dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-133">Reset the user's password.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e2ed0-134">Non è necessario reimpostare la password dell'utente durante la conversione delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-134">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="e2ed0-135">Tuttavia, se la password non viene reimpostata, **il nome utente e la password originali continuano a funzionare** dopo che la conversione della cassetta postale è terminata.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-135">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

4. <span data-ttu-id="e2ed0-136">Nella scheda **posta** , in **altre azioni**, selezionare **Converti in cassetta postale condivisa**.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-136">On the **Mail** tab, under **More actions**, select **Convert to shared mailbox**.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e2ed0-137">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="e2ed0-138">Selezionare l'utente di cui si desidera convertire la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-138">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="e2ed0-139">Nel riquadro destro espandere Impostazioni di **posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-139">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="e2ed0-140">Accanto a **altre impostazioni**, selezionare **Converti in cassetta postale condivisa**.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-140">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e2ed0-141">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="e2ed0-142">Selezionare l'utente di cui si desidera convertire la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-142">Select the user whose mailbox you want to convert.</span></span>

3. <span data-ttu-id="e2ed0-143">Nel riquadro destro espandere Impostazioni di **posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-143">In the right pane, expand **Mail Settings**.</span></span> <span data-ttu-id="e2ed0-144">Accanto a **altre impostazioni**, selezionare **Converti in cassetta postale condivisa**.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-144">Next to **More settings**, select **Convert to shared mailbox**.</span></span>

::: moniker-end


<span data-ttu-id="e2ed0-145">Se la cassetta postale è inferiore a 50 GB, è possibile [rimuovere la licenza dall'utente](../manage/remove-licenses-from-users.md)e smettere di pagarla.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-145">If the mailbox is smaller than 50 GB, you can [remove the license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="e2ed0-146">Non eliminare la vecchia cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-146">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="e2ed0-147">Sarà necessaria come ancoraggio per la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-147">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="e2ed0-148">Se si converte la cassetta postale di un dipendente che lascia l'organizzazione, è necessario eseguire ulteriori passaggi per verificare che non siano più in grado di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-148">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="e2ed0-149">Vedere [rimuovere un ex dipendente da Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="e2ed0-149">See [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
<span data-ttu-id="e2ed0-150">Per tutti gli altri elementi necessari per conoscere le cassette postali condivise, vedere [informazioni sulle cassette postali condivise](about-shared-mailboxes.md) e [creare una cassetta postale condivisa](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="e2ed0-150">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e2ed0-151">Le cassette postali condivise non richiedono una licenza separata.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-151">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="e2ed0-152">Tuttavia, se si desidera attivare un'archiviazione sul posto oppure sottoporre una cassetta postale a blocco sul posto o blocco per controversia legale, è necessario assegnare alla cassetta postale una licenza di Exchange Online, piano 1 con Archiviazione Exchange Online o Exchange Online, piano 2.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-152">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="e2ed0-153">Convertire la cassetta postale di un utente eliminato</span><span class="sxs-lookup"><span data-stu-id="e2ed0-153">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="e2ed0-p112">Si supponga di aver eliminato un account utente e di volerne convertire la vecchia cassetta postale in cassetta postale condivisa. Ecco cosa fare:</span><span class="sxs-lookup"><span data-stu-id="e2ed0-p112">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="e2ed0-156">[Ripristinare l'account dell'utente](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="e2ed0-156">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="e2ed0-157">Assicurarsi che sia assegnata una licenza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-157">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="e2ed0-158">Reimpostare la password dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-158">Reset the user's password.</span></span>
    
4. <span data-ttu-id="e2ed0-159">Attendere 20-30 minuti perché la cassetta postale venga ricreata.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-159">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="e2ed0-160">Seguire ora le istruzioni in questa pagina per convertire la cassetta postale dell'account utente in cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-160">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="e2ed0-161">Al termine, è possibile rimuovere la licenza dalla cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-161">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="e2ed0-162">Non eliminare la vecchia cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-162">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="e2ed0-163">Sarà necessaria come ancoraggio per la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-163">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="e2ed0-164">Aggiungere membri alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-164">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="e2ed0-165">Convertire di nuovo una cassetta postale condivisa in una cassetta postale (privata) dell'utente</span><span class="sxs-lookup"><span data-stu-id="e2ed0-165">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="e2ed0-166">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-166">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="e2ed0-167">Selezionare i **destinatari** \> **condivisi**.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-167">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="e2ed0-168">Selezionare la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-168">Select the shared mailbox.</span></span> <span data-ttu-id="e2ed0-169">In **Converti in cassetta postale normale**selezionare **Converti**.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-169">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="e2ed0-170">Tornare all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-170">Go back to the admin center.</span></span> <span data-ttu-id="e2ed0-171">In **Utenti** scegliere l'account utente associato alla vecchia cassetta postale utente.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-171">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="e2ed0-172">Assegnare una licenza all'account e reimpostare la password.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-172">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="e2ed0-p116">Saranno necessari alcuni minuti prima che la cassetta postale venga configurata, ma al termine, l'utente che usa l'account sarà pronto per iniziare. All'accesso, l'utente visualizzerà gli elementi di posta elettronica e del calendario che erano presenti nella cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-p116">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="e2ed0-175">Convertire la cassetta postale di un utente in un ambiente ibrido</span><span class="sxs-lookup"><span data-stu-id="e2ed0-175">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="e2ed0-176">Se questa cassetta postale condivisa si trova in un ambiente ibrido, è **consigliabile** (è quasi necessario) riportare la cassetta postale dell'utente in locale, convertire la cassetta postale utente in una cassetta postale condivisa e quindi riportare la cassetta postale condivisa nel cloud.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-176">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="e2ed0-177">Ecco perché: se si converte la cassetta postale nel cloud, è possibile convertirla, ma la cassetta postale è ancora in uso, in quanto la nuova realtà non viene sincronizzata di nuovo in locale.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-177">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="e2ed0-178">In genere, non si tratta di un problema, ma ci sono alcuni scenari in cui gli attributi locali (che pensano che la cassetta postale è la cassetta postale dell'utente) possono sovrascrivere le nuove versioni cloud di tali attributi e, di conseguenza, la cassetta postale potrebbe riconvertirsi.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-178">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="e2ed0-179">Questo è un problema perché le cassette postali degli utenti richiedono licenze **o sono eliminate temporaneamente dopo 30 giorni**.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-179">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="e2ed0-180">Sono state affrontate la maggior parte dei motivi per cui questo accade ma può comunque verificarsi, anche se raramente.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-180">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="e2ed0-181">È consigliabile essere sicuri e riportare la cassetta postale in locale, convertirla e quindi spostare di nuovo la cassetta postale condivisa nel cloud.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-181">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="e2ed0-182">La soluzione consigliata non è in violazione del contratto di licenza per gli ambienti ibridi perché l'esistenza della cassetta postale dell'utente locale è solo temporanea.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-182">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="e2ed0-183">Si potrebbe essere in violazione della licenza se si è mantenuto la cassetta postale dell'utente o la cassetta postale condivisa nell'organizzazione locale e non è stata spostata di nuovo nel cloud.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-183">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="e2ed0-184">Se si è membri del gruppo di ruoli Gestione organizzazione o Gestione destinatari, è possibile utilizzare Exchange Management Shell per modificare una cassetta postale utente in una cassetta postale condivisa locale.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-184">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="e2ed0-185">Ad esempio, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="e2ed0-185">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="e2ed0-186">Per le istanze in cui le [cassette postali condivise sono inaspettatamente convertite nelle cassette postali degli utenti](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di), vedere la soluzione di supporto</span><span class="sxs-lookup"><span data-stu-id="e2ed0-186">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="e2ed0-187">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="e2ed0-187">Related articles</span></span>

[<span data-ttu-id="e2ed0-188">Informazioni sulle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="e2ed0-188">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="e2ed0-189">Creare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="e2ed0-189">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="e2ed0-190">Configurare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="e2ed0-190">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="e2ed0-191">Rimuovere una licenza da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="e2ed0-191">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="e2ed0-192">Risolvere i problemi relativi alle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="e2ed0-192">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
