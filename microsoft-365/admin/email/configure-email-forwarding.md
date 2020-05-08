---
title: Configurare l'inoltro della posta elettronica
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
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Impostare l'inoltro della posta elettronica su uno o più account di posta elettronica utilizzando Office365.
ms.openlocfilehash: 8cd86bcab4d73719e527f9942cd41a3174966c2d
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140454"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="caa29-103">Configurare l'inoltro della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="caa29-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="caa29-104">L'interfaccia di amministrazione cambia.</span><span class="sxs-lookup"><span data-stu-id="caa29-104">The admin center is changing.</span></span> <span data-ttu-id="caa29-105">Se l'esperienza non corrisponde ai dettagli presentati, vedere [About The New Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="caa29-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="caa29-106">Come amministratore di un'organizzazione, potrebbe essere necessario disporre dei requisiti aziendali per configurare l'inoltro della posta elettronica per la cassetta postale di un utente.</span><span class="sxs-lookup"><span data-stu-id="caa29-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="caa29-107">L'inoltro della posta elettronica consente di inoltrare i messaggi inviati alla cassetta postale di un utente a quella di un altro utente all'interno o all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="caa29-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="caa29-108">Configurare l'inoltro della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="caa29-108">Configure email forwarding</span></span>

 <span data-ttu-id="caa29-109">Prima di configurare l'inoltro della posta elettronica, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="caa29-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="caa29-110">Dopo aver configurato l'inoltro della posta elettronica, solo i **nuovi** messaggi di posta elettronica inviati alla cassetta postale *da* saranno fowarded.</span><span class="sxs-lookup"><span data-stu-id="caa29-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="caa29-111">L'inoltro della posta elettronica richiede che l'account *da* disponga di una licenza.</span><span class="sxs-lookup"><span data-stu-id="caa29-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="caa29-112">Se si sta configurando l'inoltro della posta elettronica perché l'utente ha lasciato la propria organizzazione, un'altra opzione consiste nel [convertire la cassetta postale in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="caa29-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="caa29-113">In questo modo diverse persone possono accedervi.</span><span class="sxs-lookup"><span data-stu-id="caa29-113">This way several people can access it.</span></span> <span data-ttu-id="caa29-114">Tuttavia, una cassetta postale condivisa non può essere superiore a 50 GB.</span><span class="sxs-lookup"><span data-stu-id="caa29-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="caa29-115">Per eseguire questa procedura, è necessario essere un amministratore di Exchange o un amministratore globale in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="caa29-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="caa29-116">Per ulteriori informazioni, vedere l'argomento [relativo ai ruoli di amministratore](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="caa29-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="caa29-117">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="caa29-117">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="caa29-118">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="caa29-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="caa29-119">Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="caa29-119">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="caa29-120">Nella scheda **posta** , selezionare **Gestisci inoltro della posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="caa29-120">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="caa29-121">Nella pagina inoltro della posta elettronica, selezionare **inoltra tutti i messaggi di posta elettronica inviati a questa cassetta postale**, immettere l'indirizzo di inoltro e scegliere se si desidera mantenere una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="caa29-121">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="caa29-122">Se non si vede questa opzione, assicurarsi che sia assegnata una licenza all'account utente.</span><span class="sxs-lookup"><span data-stu-id="caa29-122">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="caa29-123">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="caa29-123">Select **Save changes**.</span></span>
    
    <span data-ttu-id="caa29-124">**Per inoltrare a più indirizzi di posta elettronica**, è possibile chiedere all'utente di impostare una regola in Outlook per inoltrare agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="caa29-124">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="caa29-125">Per ulteriori informazioni, vedere [utilizzare le regole per inoltrare automaticamente i messaggi](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="caa29-125">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="caa29-126">In alternativa, nell'interfaccia di amministrazione, [creare un gruppo di distribuzione](../setup/create-distribution-lists.md), [aggiungere gli indirizzi](add-user-or-contact-to-distribution-list.md)e quindi impostare l'inoltro in modo che punti al DL seguendo le istruzioni riportate in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="caa29-126">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="caa29-127">Non eliminare l'account dell'utente che si sta inoltrando o rimuovere la propria licenza.</span><span class="sxs-lookup"><span data-stu-id="caa29-127">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="caa29-128">In caso contrario, l'inoltro della posta elettronica si arresterà.</span><span class="sxs-lookup"><span data-stu-id="caa29-128">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="caa29-129">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="caa29-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="caa29-130">Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="caa29-130">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="caa29-131">Espandere **impostazioni di posta elettronica**e quindi nella sezione **inoltro della posta elettronica** Selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="caa29-131">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="caa29-132">Nella pagina inoltro di posta elettronica, impostare l'interruttore **su**attivato, immettere l'indirizzo di inoltro e scegliere se si desidera mantenere una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="caa29-132">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="caa29-133">Se non si vede questa opzione, assicurarsi che sia assegnata una licenza all'account utente.</span><span class="sxs-lookup"><span data-stu-id="caa29-133">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="caa29-134">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="caa29-134">Select **Save**.</span></span>
    
    <span data-ttu-id="caa29-135">**Per inoltrare a più indirizzi di posta elettronica**, è possibile chiedere all'utente di impostare una regola in Outlook per inoltrare agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="caa29-135">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="caa29-136">Per ulteriori informazioni, vedere [utilizzare le regole per inoltrare automaticamente i messaggi](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="caa29-136">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="caa29-137">In alternativa, nell'interfaccia di amministrazione, [creare un gruppo di distribuzione](../setup/create-distribution-lists.md), [aggiungere gli indirizzi](add-user-or-contact-to-distribution-list.md)e quindi impostare l'inoltro in modo che punti al DL seguendo le istruzioni riportate in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="caa29-137">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="caa29-138">Non eliminare l'account dell'utente che si sta inoltrando o rimuovere la propria licenza.</span><span class="sxs-lookup"><span data-stu-id="caa29-138">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="caa29-139">In caso contrario, l'inoltro della posta elettronica si arresterà.</span><span class="sxs-lookup"><span data-stu-id="caa29-139">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="caa29-140">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="caa29-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="caa29-141">Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="caa29-141">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="caa29-142">Espandere **impostazioni di posta elettronica**e quindi nella sezione **inoltro della posta elettronica** Selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="caa29-142">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="caa29-143">Nella pagina inoltro di posta elettronica, impostare l'interruttore **su**attivato, immettere l'indirizzo di inoltro e scegliere se si desidera mantenere una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="caa29-143">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="caa29-144">Se non si vede questa opzione, assicurarsi che sia assegnata una licenza all'account utente.</span><span class="sxs-lookup"><span data-stu-id="caa29-144">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="caa29-145">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="caa29-145">Select **Save**.</span></span>
    
    <span data-ttu-id="caa29-146">**Per inoltrare a più indirizzi di posta elettronica**, è possibile chiedere all'utente di impostare una regola in Outlook per inoltrare agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="caa29-146">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="caa29-147">Per ulteriori informazioni, vedere [utilizzare le regole per inoltrare automaticamente i messaggi](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="caa29-147">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="caa29-148">In alternativa, nell'interfaccia di amministrazione, [creare un gruppo di distribuzione](../setup/create-distribution-lists.md), [aggiungere gli indirizzi](add-user-or-contact-to-distribution-list.md)e quindi impostare l'inoltro in modo che punti al DL seguendo le istruzioni riportate in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="caa29-148">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="caa29-149">Non eliminare l'account dell'utente che si sta inoltrando o rimuovere la propria licenza.</span><span class="sxs-lookup"><span data-stu-id="caa29-149">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="caa29-150">In caso contrario, l'inoltro della posta elettronica si arresterà.</span><span class="sxs-lookup"><span data-stu-id="caa29-150">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
