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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: Assegnare a un utente i diritti di accesso alla cassetta postale di un altro utente, per poter leggere e inviare e-mail dalla cassetta postale di quest'ultimo.
ms.openlocfilehash: 0e5f7b154fa37ae9775e7208574b2a5395e7c239
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634281"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="58dcc-103">Assegnare le autorizzazioni della cassetta postale a un altro utente - Guida per l'amministratore</span><span class="sxs-lookup"><span data-stu-id="58dcc-103">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="58dcc-p101">In base ai requisiti aziendali, l'amministratore può consentire ad alcuni utenti di accedere alla cassetta postale di un altro utente. Ad esempio, è possibile consentire a un assistente di inviare o leggere posta elettronica dalla cassetta postale del suo manager oppure permettere a un utente di inviare messaggi per conto di un altro utente. Questo argomento illustra le procedure da eseguire.</span><span class="sxs-lookup"><span data-stu-id="58dcc-p101">As the admin, you may have company requirements to allow some users access to another user's mailbox. For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user. This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="58dcc-107">Se si cercano informazioni su come creare e gestire cassette postali condivise, vedere [Creare una cassetta postale condivisa](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="58dcc-107">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="58dcc-108">Configurare le autorizzazioni per le cassette postali</span><span class="sxs-lookup"><span data-stu-id="58dcc-108">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="58dcc-p102">Le autorizzazioni per le cassette postali consentono di concedere a un altro utente l'accesso in lettura/scrittura a una cassetta postale. Gli articoli elencati di seguito potrebbero fornire l'aiuto necessario per configurare e usare questa funzionalità:</span><span class="sxs-lookup"><span data-stu-id="58dcc-p102">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="58dcc-111">**Configurazione delle autorizzazioni:**</span><span class="sxs-lookup"><span data-stu-id="58dcc-111">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="58dcc-p103">Il primo passaggio del processo di configurazione delle autorizzazioni consiste nel decidere quali azioni potranno essere eseguite dall'altro utente nella cassetta postale specifica. È possibile consentire a un utente di leggere i messaggi di posta elettronica contenuti nella cassetta postale, inviare messaggi per conto di un altro utente oppure inviarli con la cassetta postale come mittente. Per informazioni su come configurare ogni tipo di autorizzazione, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="58dcc-p103">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="58dcc-115">Leggere messaggi di posta elettronica dalla cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58dcc-115">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="58dcc-116">Inviare messaggi di posta elettronica dalla cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58dcc-116">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="58dcc-117">Inviare e-mail per conto di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58dcc-117">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="58dcc-118">**Propagazione delle modifiche:**</span><span class="sxs-lookup"><span data-stu-id="58dcc-118">**Changing propagation:**</span></span>
  
<span data-ttu-id="58dcc-119">Dopo la configurazione delle autorizzazioni, la loro propagazione e applicazione nell'intero sistema può richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="58dcc-119">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="58dcc-120">**Come usare la funzionalità dopo la configurazione delle autorizzazioni:**</span><span class="sxs-lookup"><span data-stu-id="58dcc-120">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="58dcc-p104">Dopo la concessione dell'accesso, è possibile accedere a una cassetta postale in alcuni modi diversi. Per altre informazioni, vedere l'articolo [Accedere alla cassetta postale di un'altra persona](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span><span class="sxs-lookup"><span data-stu-id="58dcc-p104">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="58dcc-123">Le autorizzazioni possono essere configurate solo all'interno del tenant corrente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58dcc-123">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="58dcc-124">Non è possibile configurare le autorizzazioni delle cassette postali con utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="58dcc-124">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="58dcc-125">Inviare messaggi di posta elettronica dalla cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58dcc-125">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="58dcc-126">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58dcc-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="58dcc-127">Selezionare il nome dell'utente da cui si vuole concedere l'autorizzazione di invio per aprire il riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="58dcc-127">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="58dcc-128">Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-128">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="58dcc-129">Accanto a **Invia come** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-129">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="58dcc-130">Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio.</span><span class="sxs-lookup"><span data-stu-id="58dcc-130">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="58dcc-131">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-131">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="58dcc-132">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58dcc-132">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="58dcc-133">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-133">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="58dcc-134">Accanto a **Invia come** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-134">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="58dcc-135">Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio.</span><span class="sxs-lookup"><span data-stu-id="58dcc-135">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="58dcc-136">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-136">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="58dcc-137">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58dcc-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="58dcc-138">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-138">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="58dcc-139">Accanto a **Invia come** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-139">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="58dcc-140">Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio.</span><span class="sxs-lookup"><span data-stu-id="58dcc-140">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="58dcc-141">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-141">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="58dcc-142">Leggere messaggi di posta elettronica nella cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58dcc-142">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="58dcc-143">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58dcc-143">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="58dcc-144">Selezionare il nome dell'utente (di cui si vuole consentire la lettura della cassetta postale) per aprire il riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="58dcc-144">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="58dcc-145">Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-145">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="58dcc-146">Accanto a **Lettura e gestione**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-146">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="58dcc-147">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58dcc-147">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="58dcc-148">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-148">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="58dcc-149">Le autorizzazioni di **Lettura** e **Gestione** sono chiamate autorizzazioni di **Accesso completo** quando concesse nell'Interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="58dcc-149">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="58dcc-150">Le autorizzazioni di Accesso completo non comportano anche le autorizzazioni **Invia come** o **Invia per conto di**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-150">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="58dcc-151">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58dcc-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="58dcc-152">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-152">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="58dcc-153">Accanto a **Lettura e gestione**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-153">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="58dcc-154">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58dcc-154">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="58dcc-155">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-155">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="58dcc-156">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58dcc-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="58dcc-157">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-157">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="58dcc-158">Accanto a **Lettura e gestione**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-158">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="58dcc-159">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58dcc-159">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="58dcc-160">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-160">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="58dcc-161">Inviare messaggi di posta elettronica per conto di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58dcc-161">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="58dcc-162">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58dcc-162">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="58dcc-163">Selezionare il nome dell'utente da cui si vuole concedere l'autorizzazione **Invia per conto di** per aprire il riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="58dcc-163">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="58dcc-164">Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-164">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="58dcc-165">Accanto a **Invia per conto di** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-165">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="58dcc-166">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58dcc-166">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="58dcc-167">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-167">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="58dcc-168">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58dcc-168">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="58dcc-169">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-169">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="58dcc-170">Accanto a **Invia per conto di** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-170">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="58dcc-171">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58dcc-171">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="58dcc-172">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-172">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="58dcc-173">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58dcc-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="58dcc-174">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-174">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="58dcc-175">Accanto a **Invia per conto di** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-175">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="58dcc-176">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58dcc-176">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="58dcc-177">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58dcc-177">Select **Save**.</span></span>

::: moniker-end


## <a name="related-content"></a><span data-ttu-id="58dcc-178">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="58dcc-178">Related content</span></span>
  
<span data-ttu-id="58dcc-179">[Gestire gli elementi di posta e di calendario di un altro utente](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (articolo)</span><span class="sxs-lookup"><span data-stu-id="58dcc-179">[Manage another person's mail and calendar items](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5) (article)</span></span>\   
<span data-ttu-id="58dcc-180">[Inviare un messaggio di posta elettronica da un altro utente o gruppo](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (articolo)</span><span class="sxs-lookup"><span data-stu-id="58dcc-180">[Send email from another person or group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) (article)</span></span>\
<span data-ttu-id="58dcc-181">[Cambiare un nome utente e un indirizzo e-mail](../add-users/change-a-user-name-and-email-address.md) (video) </span><span class="sxs-lookup"><span data-stu-id="58dcc-181">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (video)</span></span>

