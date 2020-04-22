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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: "Informazioni su come assegnare a un utente il diritto di accedere alla cassetta postale di un altro utente. In questo modo l'utente potrà leggere i messaggi di posta elettronica e inviare messaggi dalla cassetta postale dell'altro utente. "
ms.openlocfilehash: 5a0677844e8503253561c57f926c9c4fadadd76d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43617171"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="84e13-104">Assegnare le autorizzazioni della cassetta postale a un altro utente - Guida per l'amministratore</span><span class="sxs-lookup"><span data-stu-id="84e13-104">Give mailbox permissions to another user - Admin Help</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="84e13-105">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="84e13-105">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="84e13-106">In base ai requisiti aziendali, l'amministratore può consentire ad alcuni utenti di accedere alla cassetta postale di un altro utente.</span><span class="sxs-lookup"><span data-stu-id="84e13-106">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="84e13-107">Ad esempio, è possibile consentire a un assistente di inviare o leggere posta elettronica dalla cassetta postale del suo manager oppure permettere a un utente di inviare messaggi per conto di un altro utente.</span><span class="sxs-lookup"><span data-stu-id="84e13-107">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="84e13-108">Questo argomento illustra le procedure da eseguire.</span><span class="sxs-lookup"><span data-stu-id="84e13-108">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="84e13-109">Se si cercano informazioni su come creare e gestire cassette postali condivise, vedere [Creare una cassetta postale condivisa](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="84e13-109">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="84e13-110">Configurare le autorizzazioni per le cassette postali</span><span class="sxs-lookup"><span data-stu-id="84e13-110">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="84e13-p103">Le autorizzazioni per le cassette postali consentono di concedere a un altro utente l'accesso in lettura/scrittura a una cassetta postale. Gli articoli elencati di seguito potrebbero fornire l'aiuto necessario per configurare e usare questa funzionalità:</span><span class="sxs-lookup"><span data-stu-id="84e13-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="84e13-113">**Configurazione delle autorizzazioni:**</span><span class="sxs-lookup"><span data-stu-id="84e13-113">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="84e13-p104">Il primo passaggio del processo di configurazione delle autorizzazioni consiste nel decidere quali azioni potranno essere eseguite dall'altro utente nella cassetta postale specifica. È possibile consentire a un utente di leggere i messaggi di posta elettronica contenuti nella cassetta postale, inviare messaggi per conto di un altro utente oppure inviarli con la cassetta postale come mittente. Per informazioni su come configurare ogni tipo di autorizzazione, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="84e13-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="84e13-117">Leggere messaggi di posta elettronica dalla cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="84e13-117">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="84e13-118">Inviare messaggi di posta elettronica dalla cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="84e13-118">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="84e13-119">Inviare e-mail per conto di un altro utente</span><span class="sxs-lookup"><span data-stu-id="84e13-119">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="84e13-120">**Propagazione delle modifiche:**</span><span class="sxs-lookup"><span data-stu-id="84e13-120">**Changing propagation:**</span></span>
  
<span data-ttu-id="84e13-121">Dopo la configurazione delle autorizzazioni, la loro propagazione e applicazione nell'intero sistema può richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="84e13-121">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="84e13-122">**Come usare la funzionalità dopo la configurazione delle autorizzazioni:**</span><span class="sxs-lookup"><span data-stu-id="84e13-122">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="84e13-p105">Dopo la concessione dell'accesso, è possibile accedere a una cassetta postale in alcuni modi diversi. Per altre informazioni, vedere l'articolo [Accedere alla cassetta postale di un'altra persona](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx).</span><span class="sxs-lookup"><span data-stu-id="84e13-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.office.com/article/Access-another-person-s-mailbox-A909AD30-E413-40B5-A487-0EA70B763081.aspx)</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="84e13-125">Inviare messaggi di posta elettronica dalla cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="84e13-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="84e13-126">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="84e13-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="84e13-127">Selezionare il nome dell'utente da cui si vuole concedere l'autorizzazione di invio per aprire il riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="84e13-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="84e13-128">Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="84e13-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="84e13-129">Accanto a **Invia come** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="84e13-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="84e13-130">Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio.</span><span class="sxs-lookup"><span data-stu-id="84e13-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="84e13-131">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e13-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="84e13-132">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="84e13-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="84e13-133">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="84e13-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="84e13-134">Accanto a **Invia come** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="84e13-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="84e13-135">Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio.</span><span class="sxs-lookup"><span data-stu-id="84e13-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="84e13-136">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e13-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="84e13-137">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="84e13-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="84e13-138">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="84e13-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="84e13-139">Accanto a **Invia come** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="84e13-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="84e13-140">Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio.</span><span class="sxs-lookup"><span data-stu-id="84e13-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="84e13-141">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e13-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="84e13-142">Leggere messaggi di posta elettronica nella cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="84e13-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="84e13-143">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="84e13-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="84e13-144">Selezionare il nome dell'utente (di cui si vuole consentire la lettura della cassetta postale) per aprire il riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="84e13-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="84e13-145">Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="84e13-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="84e13-146">Accanto a **Lettura e gestione**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="84e13-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="84e13-147">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="84e13-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="84e13-148">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e13-148">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="84e13-149">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="84e13-149">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="84e13-150">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="84e13-150">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="84e13-151">Accanto a **Lettura e gestione**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="84e13-151">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="84e13-152">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="84e13-152">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="84e13-153">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e13-153">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="84e13-154">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="84e13-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="84e13-155">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="84e13-155">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="84e13-156">Accanto a **Lettura e gestione**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="84e13-156">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="84e13-157">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="84e13-157">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="84e13-158">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e13-158">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="84e13-159">Inviare messaggi di posta elettronica per conto di un altro utente</span><span class="sxs-lookup"><span data-stu-id="84e13-159">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="84e13-160">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="84e13-160">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="84e13-161">Selezionare il nome dell'utente da cui si vuole concedere l'autorizzazione **Invia per conto di** per aprire il riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="84e13-161">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="84e13-162">Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="84e13-162">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="84e13-163">Accanto a **Invia per conto di** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="84e13-163">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="84e13-164">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="84e13-164">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="84e13-165">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e13-165">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="84e13-166">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="84e13-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="84e13-167">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="84e13-167">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="84e13-168">Accanto a **Invia per conto di** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="84e13-168">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="84e13-169">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="84e13-169">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="84e13-170">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e13-170">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="84e13-171">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="84e13-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="84e13-172">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="84e13-172">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="84e13-173">Accanto a **Invia per conto di** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="84e13-173">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="84e13-174">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="84e13-174">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="84e13-175">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84e13-175">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="84e13-176">Inviare e leggere messaggi da Outlook e Outlook sul Web per le aziende</span><span class="sxs-lookup"><span data-stu-id="84e13-176">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="84e13-p106">Per informazioni su come inviare messaggi di posta elettronica dalla cassetta postale di un altro utente, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="84e13-p106">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="84e13-179">Gestire gli elementi di posta e di calendario di un altro utente</span><span class="sxs-lookup"><span data-stu-id="84e13-179">Manage another person's mail and calendar items</span></span>](https://support.office.com/article/afb79d6b-2967-43b9-a944-a6b953190af5.aspx)
    
- [<span data-ttu-id="84e13-180">Inviare un messaggio di posta elettronica da un altro utente o gruppo</span><span class="sxs-lookup"><span data-stu-id="84e13-180">Send email from another person or group</span></span>](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx)
