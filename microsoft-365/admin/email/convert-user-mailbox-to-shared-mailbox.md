---
title: Convertire una cassetta postale utente in una cassetta postale condivisa
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
ms.openlocfilehash: f716bbd16be9f67189b19358ddf16a289f57f8e7
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2020
ms.locfileid: "49737966"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="f3ba9-103">Convertire una cassetta postale utente in una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="f3ba9-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="f3ba9-104">Quando si converte la cassetta postale di un utente in cassetta condivisa, vengono mantenuti tutti gli elementi di posta elettronica e del calendario esistenti.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="f3ba9-105">L'unica differenza è che ora si trovano in una cassetta postale condivisa, cui potranno accedere diversi utenti invece di uno solo.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="f3ba9-106">In un secondo momento, è possibile convertire una cassetta postale condivisa di nuovo in una cassetta postale utente (privata).</span><span class="sxs-lookup"><span data-stu-id="f3ba9-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="f3ba9-107">**Di seguito sono riportate alcune informazioni importanti che è necessario conoscere:**</span><span class="sxs-lookup"><span data-stu-id="f3ba9-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="f3ba9-108">La cassetta postale utente che si sta convertendo richiede una licenza assegnata prima di convertirla in una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="f3ba9-109">In caso contrario, l'opzione per convertire la cassetta postale non sarà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="f3ba9-110">Se la licenza è stata rimossa, aggiungerla di nuovo in modo da poter convertire la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="f3ba9-111">Dopo aver convertito la cassetta postale in una condivisa, è possibile rimuovere la licenza dall'account dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="f3ba9-112">Le cassette postali condivise possono avere fino a 50 GB di dati senza una licenza assegnata.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="f3ba9-113">Perché possano contenere ancora più dati, è necessario assegnarvi una licenza.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="f3ba9-114">Potrebbe essere necessario eliminare diversi messaggi di posta elettronica di grandi dimensioni, ad esempio quelli con allegati, dalla cassetta postale condivisa per ridurne le dimensioni e rimuovere la licenza.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="f3ba9-p104">Non eliminare il vecchio account utente. Sarà necessario per l'ancoraggio della cassetta postale condivisa. Se l'account utente è già stato eliminato, vedere [Convertire la cassetta postale di un utente eliminato](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="f3ba9-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="f3ba9-118">Le regole sono intatte dopo la conversione della cassetta postale in una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="f3ba9-119">Utilizzare l'interfaccia di amministrazione di Exchange per convertire una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="f3ba9-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="f3ba9-120">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="f3ba9-121">Selezionare  le \> **cassette postali** destinatari.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="f3ba9-122">Selezionare la cassetta postale utente.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-122">Select the user mailbox.</span></span> <span data-ttu-id="f3ba9-123">In **Converti in cassetta postale condivisa**, selezionare **Converti**.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="f3ba9-124">Se la cassetta postale è inferiore a 50 GB, è possibile rimuovere la [licenza dall'utente](../manage/remove-licenses-from-users.md)e smettere di pagarla.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="f3ba9-125">Non eliminare l'account dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-125">Don't delete the user's account.</span></span> <span data-ttu-id="f3ba9-126">Sarà necessaria come ancoraggio per la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="f3ba9-127">Se si converte la cassetta postale di un dipendente che lascia l'organizzazione, è necessario eseguire ulteriori passaggi per verificare che non siano più in grado di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="f3ba9-128">Per ulteriori informazioni, vedere [rimuovere un ex dipendente da Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="f3ba9-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="f3ba9-129">Non è necessario reimpostare la password dell'utente durante la conversione delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="f3ba9-130">Tuttavia, se la password non viene reimpostata, **il nome utente e la password originali continuano a funzionare** dopo che la conversione della cassetta postale è terminata.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="f3ba9-131">Per tutti gli altri elementi necessari per conoscere le cassette postali condivise, vedere [informazioni sulle cassette postali condivise](about-shared-mailboxes.md) e [creare una cassetta postale condivisa](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="f3ba9-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f3ba9-132">Le cassette postali condivise non richiedono una licenza separata.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="f3ba9-133">Tuttavia, se si desidera attivare un'archiviazione sul posto oppure sottoporre una cassetta postale a blocco sul posto o blocco per controversia legale, è necessario assegnare alla cassetta postale una licenza di Exchange Online, piano 1 con Archiviazione Exchange Online o Exchange Online, piano 2.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="f3ba9-134">Convertire la cassetta postale di un utente eliminato</span><span class="sxs-lookup"><span data-stu-id="f3ba9-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="f3ba9-p109">Si supponga di aver eliminato un account utente e di volerne convertire la vecchia cassetta postale in cassetta postale condivisa. Ecco cosa fare:</span><span class="sxs-lookup"><span data-stu-id="f3ba9-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="f3ba9-137">[Ripristinare l'account dell'utente](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="f3ba9-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="f3ba9-138">Assicurarsi che sia assegnata una licenza di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="f3ba9-139">Reimpostare la password dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="f3ba9-140">Attendere 20-30 minuti perché la cassetta postale venga ricreata.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="f3ba9-141">Seguire ora le istruzioni in questa pagina per convertire la cassetta postale dell'account utente in cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="f3ba9-142">Al termine, è possibile rimuovere la licenza dalla cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="f3ba9-143">Non eliminare la vecchia cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="f3ba9-144">Sarà necessaria come ancoraggio per la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="f3ba9-145">Aggiungere membri alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="f3ba9-146">Convertire di nuovo una cassetta postale condivisa in una cassetta postale (privata) dell'utente</span><span class="sxs-lookup"><span data-stu-id="f3ba9-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="f3ba9-147">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="f3ba9-148">Selezionare i **destinatari** \> **condivisi**.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="f3ba9-149">Selezionare la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-149">Select the shared mailbox.</span></span> <span data-ttu-id="f3ba9-150">In **Converti in cassetta postale normale** selezionare **Converti**.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="f3ba9-151">Tornare all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-151">Go back to the admin center.</span></span> <span data-ttu-id="f3ba9-152">In **Utenti** scegliere l'account utente associato alla vecchia cassetta postale utente.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="f3ba9-153">Assegnare una licenza all'account e reimpostare la password.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="f3ba9-p113">Saranno necessari alcuni minuti prima che la cassetta postale venga configurata, ma al termine, l'utente che usa l'account sarà pronto per iniziare. All'accesso, l'utente visualizzerà gli elementi di posta elettronica e del calendario che erano presenti nella cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="f3ba9-156">Convertire la cassetta postale di un utente in un ambiente ibrido</span><span class="sxs-lookup"><span data-stu-id="f3ba9-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="f3ba9-157">Per ulteriori informazioni sulla conversione di una cassetta postale utente in una cassetta postale condivisa in un ambiente ibrido di Exchange, vedere:</span><span class="sxs-lookup"><span data-stu-id="f3ba9-157">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="f3ba9-158">Cmdlet per la creazione o la modifica di una cassetta postale condivisa remota in un ambiente Exchange locale</span><span class="sxs-lookup"><span data-stu-id="f3ba9-158">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="f3ba9-159">Le cassette postali condivise sono inaspettatamente convertite nelle cassette postali degli utenti dopo l'esecuzione della sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="f3ba9-159">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](https://docs.microsoft.com/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="f3ba9-160">Se si è membri del gruppo di ruoli Gestione organizzazione o Gestione destinatari, è possibile utilizzare Exchange Management Shell per modificare una cassetta postale utente in una cassetta postale condivisa locale.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-160">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="f3ba9-161">Ad esempio, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="f3ba9-161">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f3ba9-162">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="f3ba9-162">Related articles</span></span>

[<span data-ttu-id="f3ba9-163">Informazioni sulle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="f3ba9-163">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="f3ba9-164">Creare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="f3ba9-164">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="f3ba9-165">Configurare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="f3ba9-165">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="f3ba9-166">Rimuovere una licenza da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="f3ba9-166">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="f3ba9-167">Risolvere i problemi relativi alle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="f3ba9-167">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
