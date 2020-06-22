---
title: Assegnare le autorizzazioni della cassetta postale a un altro utente - Guida per l'amministratore
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: "Informazioni su come assegnare a un utente il diritto di accedere alla cassetta postale di un altro utente. In questo modo l'utente potrà leggere i messaggi di posta elettronica e inviare messaggi dalla cassetta postale dell'altro utente. "
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780602"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="ec2ff-104">Assegnare le autorizzazioni della cassetta postale a un altro utente - Guida per l'amministratore</span><span class="sxs-lookup"><span data-stu-id="ec2ff-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="ec2ff-105">In base ai requisiti aziendali, l'amministratore può consentire ad alcuni utenti di accedere alla cassetta postale di un altro utente.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="ec2ff-106">Ad esempio, è possibile consentire a un assistente di inviare o leggere posta elettronica dalla cassetta postale del suo manager oppure permettere a un utente di inviare messaggi per conto di un altro utente.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="ec2ff-107">Questo argomento illustra le procedure da eseguire.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="ec2ff-108">Se si cercano informazioni su come creare e gestire cassette postali condivise, vedere [Creare una cassetta postale condivisa](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="ec2ff-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="ec2ff-109">Configurare le autorizzazioni per le cassette postali</span><span class="sxs-lookup"><span data-stu-id="ec2ff-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="ec2ff-110">Mailbox permissions allow you to give read/write access to a mailbox to another user.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-110">Mailbox permissions allow you to give read/write access to a mailbox to another user.</span></span> <span data-ttu-id="ec2ff-111">The articles below might give you the help you need to set up and use this feature:</span><span class="sxs-lookup"><span data-stu-id="ec2ff-111">The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="ec2ff-112">**Configurazione delle autorizzazioni:**</span><span class="sxs-lookup"><span data-stu-id="ec2ff-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="ec2ff-113">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-113">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox.</span></span> <span data-ttu-id="ec2ff-114">You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-114">You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox.</span></span> <span data-ttu-id="ec2ff-115">Refer to the following articles on how to set up each type of permissions:</span><span class="sxs-lookup"><span data-stu-id="ec2ff-115">Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="ec2ff-116">Leggere messaggi di posta elettronica dalla cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="ec2ff-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="ec2ff-117">Inviare messaggi di posta elettronica dalla cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="ec2ff-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="ec2ff-118">Inviare e-mail per conto di un altro utente</span><span class="sxs-lookup"><span data-stu-id="ec2ff-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="ec2ff-119">**Propagazione delle modifiche:**</span><span class="sxs-lookup"><span data-stu-id="ec2ff-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="ec2ff-120">Dopo la configurazione delle autorizzazioni, la loro propagazione e applicazione nell'intero sistema può richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="ec2ff-121">**Come usare la funzionalità dopo la configurazione delle autorizzazioni:**</span><span class="sxs-lookup"><span data-stu-id="ec2ff-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="ec2ff-122">There are a few different ways you can access a mailbox once you've been given access.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-122">There are a few different ways you can access a mailbox once you've been given access.</span></span> <span data-ttu-id="ec2ff-123">For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span><span class="sxs-lookup"><span data-stu-id="ec2ff-123">For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="ec2ff-124">Inviare messaggi di posta elettronica dalla cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="ec2ff-124">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ec2ff-125">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-125">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="ec2ff-126">Selezionare il nome dell'utente da cui si vuole concedere l'autorizzazione di invio per aprire il riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-126">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="ec2ff-127">Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-127">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="ec2ff-128">Accanto a **Invia come** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-128">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="ec2ff-129">Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-129">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="ec2ff-130">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-130">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ec2ff-131">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-131">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="ec2ff-132">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-132">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="ec2ff-133">Accanto a **Invia come** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-133">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="ec2ff-134">Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-134">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="ec2ff-135">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-135">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ec2ff-136">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="ec2ff-137">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-137">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="ec2ff-138">Accanto a **Invia come** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-138">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="ec2ff-139">Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-139">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="ec2ff-140">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-140">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="ec2ff-141">Leggere messaggi di posta elettronica nella cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="ec2ff-141">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ec2ff-142">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-142">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="ec2ff-143">Selezionare il nome dell'utente (di cui si vuole consentire la lettura della cassetta postale) per aprire il riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-143">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="ec2ff-144">Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-144">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="ec2ff-145">Accanto a **Lettura e gestione**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-145">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="ec2ff-146">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-146">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="ec2ff-147">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-147">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ec2ff-148">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-148">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="ec2ff-149">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-149">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="ec2ff-150">Accanto a **Lettura e gestione**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-150">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="ec2ff-151">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-151">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="ec2ff-152">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-152">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ec2ff-153">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-153">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="ec2ff-154">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-154">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="ec2ff-155">Accanto a **Lettura e gestione**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-155">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="ec2ff-156">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-156">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="ec2ff-157">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-157">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="ec2ff-158">Inviare messaggi di posta elettronica per conto di un altro utente</span><span class="sxs-lookup"><span data-stu-id="ec2ff-158">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ec2ff-159">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="ec2ff-160">Selezionare il nome dell'utente da cui si vuole concedere l'autorizzazione **Invia per conto di** per aprire il riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-160">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="ec2ff-161">Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-161">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="ec2ff-162">Accanto a **Invia per conto di** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-162">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="ec2ff-163">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-163">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="ec2ff-164">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-164">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ec2ff-165">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="ec2ff-166">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-166">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="ec2ff-167">Accanto a **Invia per conto di** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-167">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="ec2ff-168">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-168">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="ec2ff-169">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-169">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ec2ff-170">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="ec2ff-171">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-171">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="ec2ff-172">Accanto a **Invia per conto di** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-172">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="ec2ff-173">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-173">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="ec2ff-174">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ec2ff-174">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="ec2ff-175">Inviare e leggere messaggi da Outlook e Outlook sul Web per le aziende</span><span class="sxs-lookup"><span data-stu-id="ec2ff-175">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="ec2ff-176">Want to know how to send email from another user's mailbox?</span><span class="sxs-lookup"><span data-stu-id="ec2ff-176">Want to know how to send email from another user's mailbox?</span></span> <span data-ttu-id="ec2ff-177">Check out the following topics:</span><span class="sxs-lookup"><span data-stu-id="ec2ff-177">Check out the following topics:</span></span>
  
- [<span data-ttu-id="ec2ff-178">Gestire gli elementi di posta e di calendario di un altro utente</span><span class="sxs-lookup"><span data-stu-id="ec2ff-178">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="ec2ff-179">Inviare un messaggio di posta elettronica da un altro utente o gruppo</span><span class="sxs-lookup"><span data-stu-id="ec2ff-179">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
