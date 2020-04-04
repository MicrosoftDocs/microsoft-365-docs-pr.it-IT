---
title: Configurare l'inoltro della posta elettronica in Office 365
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
ms.openlocfilehash: 963256aedb52ae0adf31790a74fbdb77ad2bb27e
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142528"
---
# <a name="configure-email-forwarding-in-office-365"></a><span data-ttu-id="b326b-103">Configurare l'inoltro della posta elettronica in Office 365</span><span class="sxs-lookup"><span data-stu-id="b326b-103">Configure email forwarding in Office 365</span></span>
  
<span data-ttu-id="b326b-p101">L'amministratore di un'organizzazione di Office 365 può avere dei requisiti da rispettare per la configurazione dell'inoltro della posta elettronica della cassetta postale di un utente. L'inoltro della posta elettronica consente di inoltrare i messaggi inviati alla cassetta postale di un utente a quella di un altro utente all'interno o all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b326b-p101">As the admin of an Office 365 organization, you might have company requirements to set up email forwarding for a user's mailbox. Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="b326b-106">Configurare l'inoltro della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b326b-106">Configure email forwarding</span></span>

 <span data-ttu-id="b326b-107">Prima di configurare l'inoltro della posta elettronica, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b326b-107">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="b326b-108">Dopo aver configurato l'inoltro della posta elettronica, verranno inoltrati solo i **nuovi** messaggi di posta elettronica inviati alla cassetta postale *da* .</span><span class="sxs-lookup"><span data-stu-id="b326b-108">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span> 
    
- <span data-ttu-id="b326b-109">L'inoltro della posta elettronica richiede che l'account *da* disponga di una licenza.</span><span class="sxs-lookup"><span data-stu-id="b326b-109">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="b326b-110">Se si sta configurando l'inoltro della posta elettronica perché l'utente ha lasciato la propria organizzazione, un'altra opzione consiste nel [convertire la cassetta postale in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="b326b-110">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="b326b-111">In questo modo diverse persone possono accedervi.</span><span class="sxs-lookup"><span data-stu-id="b326b-111">This way several people can access it.</span></span> <span data-ttu-id="b326b-112">Tuttavia, una cassetta postale condivisa non può essere superiore a 50 GB.</span><span class="sxs-lookup"><span data-stu-id="b326b-112">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="b326b-113">Per eseguire questa procedura è necessario essere un amministratore di Exchange o un amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b326b-113">You must be an Exchange administrator or Global administrator in Office 365 to do these steps.</span></span> <span data-ttu-id="b326b-114">Per ulteriori informazioni, vedere l'argomento [relativo ai ruoli di amministratore](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b326b-114">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="b326b-115">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="b326b-115">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="b326b-116">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="b326b-116">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="b326b-117">Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="b326b-117">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="b326b-118">Nella scheda **posta** , selezionare **Gestisci inoltro della posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="b326b-118">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="b326b-119">Nella pagina inoltro della posta elettronica, selezionare **inoltra tutti i messaggi di posta elettronica inviati a questa cassetta postale**, immettere l'indirizzo di inoltro e scegliere se si desidera mantenere una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="b326b-119">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="b326b-120">Se non si vede questa opzione, assicurarsi che sia assegnata una licenza all'account utente.</span><span class="sxs-lookup"><span data-stu-id="b326b-120">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="b326b-121">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="b326b-121">Select **Save changes**.</span></span>
    
    <span data-ttu-id="b326b-122">*Per inoltrare a più indirizzi di posta elettronica*, è possibile chiedere all'utente di impostare una regola in Outlook per inoltrare agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="b326b-122">*To forward to multiple email addresses*, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="b326b-123">Per ulteriori informazioni, vedere [utilizzare le regole per inoltrare automaticamente i messaggi](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="b326b-123">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="b326b-124">In alternativa, nell'interfaccia di amministrazione, [creare un gruppo di distribuzione](../setup/create-distribution-lists.md), [aggiungere gli indirizzi](add-user-or-contact-to-distribution-list.md)e quindi impostare l'inoltro in modo che punti al DL seguendo le istruzioni riportate in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b326b-124">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="b326b-125">Non eliminare l'account dell'utente che si sta inoltrando o rimuovere la propria licenza.</span><span class="sxs-lookup"><span data-stu-id="b326b-125">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="b326b-126">In caso contrario, l'inoltro della posta elettronica si arresterà.</span><span class="sxs-lookup"><span data-stu-id="b326b-126">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="b326b-127">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="b326b-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="b326b-128">Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="b326b-128">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="b326b-129">Espandere **impostazioni di posta elettronica**e quindi nella sezione **inoltro della posta elettronica** Selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="b326b-129">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="b326b-130">Nella pagina inoltro di posta elettronica, impostare l'interruttore **su**attivato, immettere l'indirizzo di inoltro e scegliere se si desidera mantenere una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="b326b-130">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="b326b-131">Se non si vede questa opzione, assicurarsi che sia assegnata una licenza all'account utente.</span><span class="sxs-lookup"><span data-stu-id="b326b-131">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="b326b-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b326b-132">Select **Save**.</span></span>
    
    <span data-ttu-id="b326b-133">**Per inoltrare a più indirizzi di posta elettronica**, è possibile chiedere all'utente di impostare una regola in Outlook per inoltrare agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="b326b-133">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="b326b-134">Per ulteriori informazioni, vedere [utilizzare le regole per inoltrare automaticamente i messaggi](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="b326b-134">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="b326b-135">In alternativa, nell'interfaccia di amministrazione, [creare un gruppo di distribuzione](../setup/create-distribution-lists.md), [aggiungere gli indirizzi](add-user-or-contact-to-distribution-list.md)e quindi impostare l'inoltro in modo che punti al DL seguendo le istruzioni riportate in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b326b-135">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="b326b-136">Non eliminare l'account dell'utente che si sta inoltrando o rimuovere la propria licenza.</span><span class="sxs-lookup"><span data-stu-id="b326b-136">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="b326b-137">In caso contrario, l'inoltro della posta elettronica si arresterà.</span><span class="sxs-lookup"><span data-stu-id="b326b-137">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="b326b-138">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="b326b-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="b326b-139">Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="b326b-139">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="b326b-140">Espandere **impostazioni di posta elettronica**e quindi nella sezione **inoltro della posta elettronica** Selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="b326b-140">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="b326b-141">Nella pagina inoltro di posta elettronica, impostare l'interruttore **su**attivato, immettere l'indirizzo di inoltro e scegliere se si desidera mantenere una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="b326b-141">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="b326b-142">Se non si vede questa opzione, assicurarsi che sia assegnata una licenza all'account utente.</span><span class="sxs-lookup"><span data-stu-id="b326b-142">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="b326b-143">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b326b-143">Select **Save**.</span></span>
    
    <span data-ttu-id="b326b-144">**Per inoltrare a più indirizzi di posta elettronica**, è possibile chiedere all'utente di impostare una regola in Outlook per inoltrare agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="b326b-144">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="b326b-145">Per ulteriori informazioni, vedere [utilizzare le regole per inoltrare automaticamente i messaggi](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="b326b-145">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="b326b-146">In alternativa, nell'interfaccia di amministrazione, [creare un gruppo di distribuzione](../setup/create-distribution-lists.md), [aggiungere gli indirizzi](add-user-or-contact-to-distribution-list.md)e quindi impostare l'inoltro in modo che punti al DL seguendo le istruzioni riportate in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="b326b-146">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="b326b-147">Non eliminare l'account dell'utente che si sta inoltrando o rimuovere la propria licenza.</span><span class="sxs-lookup"><span data-stu-id="b326b-147">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="b326b-148">In caso contrario, l'inoltro della posta elettronica si arresterà.</span><span class="sxs-lookup"><span data-stu-id="b326b-148">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
