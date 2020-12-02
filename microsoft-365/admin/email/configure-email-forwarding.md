---
title: Configurare l'inoltro della posta elettronica
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Impostare l'inoltro della posta elettronica su uno o più account di posta elettronica utilizzando Office365.
ms.openlocfilehash: acdca0b19eda70d7da34ce1093a4a1b11052fd79
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551835"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="094d0-103">Configurare l'inoltro della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="094d0-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="094d0-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="094d0-104">The admin center is changing.</span></span> <span data-ttu-id="094d0-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="094d0-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="094d0-106">Come amministratore di un'organizzazione, potrebbe essere necessario disporre dei requisiti aziendali per configurare l'inoltro della posta elettronica per la cassetta postale di un utente.</span><span class="sxs-lookup"><span data-stu-id="094d0-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="094d0-107">L'inoltro della posta elettronica consente di inoltrare i messaggi inviati alla cassetta postale di un utente a quella di un altro utente all'interno o all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="094d0-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="094d0-108">Configurare l'inoltro della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="094d0-108">Configure email forwarding</span></span>

 <span data-ttu-id="094d0-109">Prima di configurare l'inoltro della posta elettronica, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="094d0-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="094d0-110">Dopo aver configurato l'inoltro della posta elettronica, verranno inoltrati solo i **nuovi** messaggi di posta elettronica inviati alla cassetta postale  *da*  .</span><span class="sxs-lookup"><span data-stu-id="094d0-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span> 
    
- <span data-ttu-id="094d0-111">L'inoltro della posta elettronica richiede che l'account  *da*  disponga di una licenza.</span><span class="sxs-lookup"><span data-stu-id="094d0-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="094d0-112">Se si sta configurando l'inoltro della posta elettronica perché l'utente ha lasciato la propria organizzazione, un'altra opzione consiste nel [convertire la cassetta postale in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="094d0-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="094d0-113">In questo modo diverse persone possono accedervi.</span><span class="sxs-lookup"><span data-stu-id="094d0-113">This way several people can access it.</span></span> <span data-ttu-id="094d0-114">Tuttavia, una cassetta postale condivisa non può essere superiore a 50 GB.</span><span class="sxs-lookup"><span data-stu-id="094d0-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="094d0-115">Per eseguire questa procedura, è necessario essere un amministratore di Exchange o un amministratore globale in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="094d0-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="094d0-116">Per ulteriori informazioni, vedere l'argomento [relativo ai ruoli di amministratore](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="094d0-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="094d0-117">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="094d0-117">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="094d0-118">Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="094d0-118">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="094d0-119">Nella scheda **posta** , selezionare **Gestisci inoltro della posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="094d0-119">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="094d0-120">Nella pagina inoltro della posta elettronica, selezionare **inoltra tutti i messaggi di posta elettronica inviati a questa cassetta postale**, immettere l'indirizzo di inoltro e scegliere se si desidera mantenere una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="094d0-120">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="094d0-121">Se non si vede questa opzione, assicurarsi che sia assegnata una licenza all'account utente.</span><span class="sxs-lookup"><span data-stu-id="094d0-121">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="094d0-122">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="094d0-122">Select **Save changes**.</span></span>
    
    <span data-ttu-id="094d0-123">**Per inoltrare a più indirizzi di posta elettronica**, è possibile chiedere all'utente di impostare una regola in Outlook per inoltrare agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="094d0-123">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="094d0-124">Per ulteriori informazioni, vedere [utilizzare le regole per inoltrare automaticamente i messaggi](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="094d0-124">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="094d0-125">In alternativa, nell'interfaccia di amministrazione, [creare un gruppo di distribuzione](../setup/create-distribution-lists.md), [aggiungere gli indirizzi](add-user-or-contact-to-distribution-list.md)e quindi impostare l'inoltro in modo che punti al DL seguendo le istruzioni riportate in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="094d0-125">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="094d0-126">Non eliminare l'account dell'utente che si sta inoltrando o rimuovere la propria licenza.</span><span class="sxs-lookup"><span data-stu-id="094d0-126">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="094d0-127">In caso contrario, l'inoltro della posta elettronica si arresterà.</span><span class="sxs-lookup"><span data-stu-id="094d0-127">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="094d0-128">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="094d0-128">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="094d0-129">Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="094d0-129">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="094d0-130">Espandere **impostazioni di posta elettronica** e quindi nella sezione **inoltro della posta elettronica** Selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="094d0-130">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="094d0-131">Nella pagina inoltro di posta elettronica, impostare l'interruttore **su** attivato, immettere l'indirizzo di inoltro e scegliere se si desidera mantenere una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="094d0-131">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="094d0-132">Se non si vede questa opzione, assicurarsi che sia assegnata una licenza all'account utente.</span><span class="sxs-lookup"><span data-stu-id="094d0-132">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="094d0-133">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="094d0-133">Select **Save**.</span></span>
    
    <span data-ttu-id="094d0-134">**Per inoltrare a più indirizzi di posta elettronica**, è possibile chiedere all'utente di impostare una regola in Outlook per inoltrare agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="094d0-134">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="094d0-135">Per ulteriori informazioni, vedere [utilizzare le regole per inoltrare automaticamente i messaggi](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="094d0-135">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="094d0-136">In alternativa, nell'interfaccia di amministrazione, [creare un gruppo di distribuzione](../setup/create-distribution-lists.md), [aggiungere gli indirizzi](add-user-or-contact-to-distribution-list.md)e quindi impostare l'inoltro in modo che punti al DL seguendo le istruzioni riportate in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="094d0-136">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="094d0-137">Non eliminare l'account dell'utente che si sta inoltrando o rimuovere la propria licenza.</span><span class="sxs-lookup"><span data-stu-id="094d0-137">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="094d0-138">In caso contrario, l'inoltro della posta elettronica si arresterà.</span><span class="sxs-lookup"><span data-stu-id="094d0-138">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="094d0-139">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="094d0-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="094d0-140">Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica per aprire la pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="094d0-140">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="094d0-141">Espandere **impostazioni di posta elettronica** e quindi nella sezione **inoltro della posta elettronica** Selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="094d0-141">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="094d0-142">Nella pagina inoltro di posta elettronica, impostare l'interruttore **su** attivato, immettere l'indirizzo di inoltro e scegliere se si desidera mantenere una copia dei messaggi di posta elettronica inoltrati.</span><span class="sxs-lookup"><span data-stu-id="094d0-142">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="094d0-143">Se non si vede questa opzione, assicurarsi che sia assegnata una licenza all'account utente.</span><span class="sxs-lookup"><span data-stu-id="094d0-143">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="094d0-144">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="094d0-144">Select **Save**.</span></span>
    
    <span data-ttu-id="094d0-145">**Per inoltrare a più indirizzi di posta elettronica**, è possibile chiedere all'utente di impostare una regola in Outlook per inoltrare agli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="094d0-145">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="094d0-146">Per ulteriori informazioni, vedere [utilizzare le regole per inoltrare automaticamente i messaggi](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="094d0-146">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="094d0-147">In alternativa, nell'interfaccia di amministrazione, [creare un gruppo di distribuzione](../setup/create-distribution-lists.md), [aggiungere gli indirizzi](add-user-or-contact-to-distribution-list.md)e quindi impostare l'inoltro in modo che punti al DL seguendo le istruzioni riportate in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="094d0-147">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="094d0-148">Non eliminare l'account dell'utente che si sta inoltrando o rimuovere la propria licenza.</span><span class="sxs-lookup"><span data-stu-id="094d0-148">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="094d0-149">In caso contrario, l'inoltro della posta elettronica si arresterà.</span><span class="sxs-lookup"><span data-stu-id="094d0-149">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
