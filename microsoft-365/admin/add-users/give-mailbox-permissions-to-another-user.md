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
description: "Informazioni su come assegnare a un utente il diritto di accedere alla cassetta postale di un altro utente. In questo modo l'utente potrà leggere i messaggi di posta elettronica e inviare messaggi dalla cassetta postale dell'altro utente. "
ms.openlocfilehash: e6b94d4e24b0ff1d5dc397ccbcfba98929a303f2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925543"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a><span data-ttu-id="58154-104">Assegnare le autorizzazioni della cassetta postale a un altro utente - Guida per l'amministratore</span><span class="sxs-lookup"><span data-stu-id="58154-104">Give mailbox permissions to another user - Admin Help</span></span>

<span data-ttu-id="58154-105">In base ai requisiti aziendali, l'amministratore può consentire ad alcuni utenti di accedere alla cassetta postale di un altro utente.</span><span class="sxs-lookup"><span data-stu-id="58154-105">As the admin, you may have company requirements to allow some users access to another user's mailbox.</span></span> <span data-ttu-id="58154-106">Ad esempio, è possibile consentire a un assistente di inviare o leggere posta elettronica dalla cassetta postale del suo manager oppure permettere a un utente di inviare messaggi per conto di un altro utente.</span><span class="sxs-lookup"><span data-stu-id="58154-106">For example, you may want to enable an assistant to send or read email from their manager's mailbox, or one of your user's the ability to send email on behalf of another user.</span></span> <span data-ttu-id="58154-107">Questo argomento illustra le procedure da eseguire.</span><span class="sxs-lookup"><span data-stu-id="58154-107">This topic shows you how to accomplish this.</span></span>
  
<span data-ttu-id="58154-108">Se si cercano informazioni su come creare e gestire cassette postali condivise, vedere [Creare una cassetta postale condivisa](../email/create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="58154-108">If you're looking for information about creating and managing shared mailboxes, check out [Create a shared mailbox](../email/create-a-shared-mailbox.md).</span></span>
    
## <a name="looking-to-set-up-mailbox-permissions"></a><span data-ttu-id="58154-109">Configurare le autorizzazioni per le cassette postali</span><span class="sxs-lookup"><span data-stu-id="58154-109">Looking to set up mailbox permissions?</span></span>

<span data-ttu-id="58154-p103">Le autorizzazioni per le cassette postali consentono di concedere a un altro utente l'accesso in lettura/scrittura a una cassetta postale. Gli articoli elencati di seguito potrebbero fornire l'aiuto necessario per configurare e usare questa funzionalità:</span><span class="sxs-lookup"><span data-stu-id="58154-p103">Mailbox permissions allow you to give read/write access to a mailbox to another user. The articles below might give you the help you need to set up and use this feature:</span></span>
  
 <span data-ttu-id="58154-112">**Configurazione delle autorizzazioni:**</span><span class="sxs-lookup"><span data-stu-id="58154-112">**Setting up the permissions:**</span></span>
  
<span data-ttu-id="58154-p104">Il primo passaggio del processo di configurazione delle autorizzazioni consiste nel decidere quali azioni potranno essere eseguite dall'altro utente nella cassetta postale specifica. È possibile consentire a un utente di leggere i messaggi di posta elettronica contenuti nella cassetta postale, inviare messaggi per conto di un altro utente oppure inviarli con la cassetta postale come mittente. Per informazioni su come configurare ogni tipo di autorizzazione, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="58154-p104">The first step to setting up permissions is deciding which actions you want to allow the other user to take in the given mailbox. You can allow a user to read emails from the mailbox, send emails on behalf of another user, and send emails as if they were sent from that mailbox. Refer to the following articles on how to set up each type of permissions:</span></span>
  
- [<span data-ttu-id="58154-116">Leggere messaggi di posta elettronica dalla cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58154-116">Read email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [<span data-ttu-id="58154-117">Inviare messaggi di posta elettronica dalla cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58154-117">Send email from another user's mailbox</span></span>](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [<span data-ttu-id="58154-118">Inviare e-mail per conto di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58154-118">Send email on behalf of another user</span></span>](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 <span data-ttu-id="58154-119">**Propagazione delle modifiche:**</span><span class="sxs-lookup"><span data-stu-id="58154-119">**Changing propagation:**</span></span>
  
<span data-ttu-id="58154-120">Dopo la configurazione delle autorizzazioni, la loro propagazione e applicazione nell'intero sistema può richiedere fino a 60 minuti.</span><span class="sxs-lookup"><span data-stu-id="58154-120">Once you've set up the permissions, it can take up to 60 minutes for the changes to propagate through the system and be in effect.</span></span>
  
 <span data-ttu-id="58154-121">**Come usare la funzionalità dopo la configurazione delle autorizzazioni:**</span><span class="sxs-lookup"><span data-stu-id="58154-121">**How to use it once permissions are set up:**</span></span>
  
<span data-ttu-id="58154-p105">Dopo la concessione dell'accesso, è possibile accedere a una cassetta postale in alcuni modi diversi. Per altre informazioni, vedere l'articolo [Accedere alla cassetta postale di un'altra persona](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span><span class="sxs-lookup"><span data-stu-id="58154-p105">There are a few different ways you can access a mailbox once you've been given access. For help on this, refer to this article: [Access another person's mailbox](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).</span></span>

> [!NOTE]
> <span data-ttu-id="58154-124">Le autorizzazioni possono essere configurate solo all'interno del tenant corrente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58154-124">The permissions can be set up only within the current organization tenant.</span></span> <span data-ttu-id="58154-125">Non è possibile configurare le autorizzazioni delle cassette postali con utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="58154-125">It is not possible to set up mailbox permissions with out of tenant users.</span></span>
  
## <a name="send-email-from-another-users-mailbox"></a><span data-ttu-id="58154-126">Inviare messaggi di posta elettronica dalla cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58154-126">Send email from another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="58154-127">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58154-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="58154-128">Selezionare il nome dell'utente da cui si vuole concedere l'autorizzazione di invio per aprire il riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="58154-128">Select the name of the user (from whom you plan to give a sending permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="58154-129">Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58154-129">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>

4. <span data-ttu-id="58154-130">Accanto a **Invia come** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58154-130">Next to **Send as**, select **Edit**.</span></span> 

5. <span data-ttu-id="58154-131">Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio.</span><span class="sxs-lookup"><span data-stu-id="58154-131">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
6. <span data-ttu-id="58154-132">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58154-132">Select **Save**.</span></span>
 
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="58154-133">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58154-133">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="58154-134">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58154-134">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="58154-135">Accanto a **Invia come** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58154-135">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="58154-136">Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio.</span><span class="sxs-lookup"><span data-stu-id="58154-136">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="58154-137">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58154-137">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="58154-138">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58154-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="58154-139">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58154-139">Select the user you want, expand **Mail Settings**, and then Select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="58154-140">Accanto a **Invia come** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58154-140">Next to **Send as**, select **Edit**.</span></span> 

4. <span data-ttu-id="58154-141">Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio.</span><span class="sxs-lookup"><span data-stu-id="58154-141">Select **Add permissions**, then choose the name of the person who you want this user to be able to send as.</span></span> 
    
5. <span data-ttu-id="58154-142">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58154-142">Select **Save**.</span></span>

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a><span data-ttu-id="58154-143">Leggere messaggi di posta elettronica nella cassetta postale di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58154-143">Read email in another user's mailbox</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="58154-144">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58154-144">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="58154-145">Selezionare il nome dell'utente (di cui si vuole consentire la lettura della cassetta postale) per aprire il riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="58154-145">Select the name of the user (whose mailbox you want to allow to be read) to open their properties pane.</span></span>
    
3. <span data-ttu-id="58154-146">Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58154-146">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="58154-147">Accanto a **Lettura e gestione**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58154-147">Next to **Read and manage**, select **Edit**.</span></span> 
    
5. <span data-ttu-id="58154-148">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58154-148">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

6. <span data-ttu-id="58154-149">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58154-149">Select **Save**.</span></span>


> [!NOTE]
> <span data-ttu-id="58154-150">Le autorizzazioni di **Lettura** e **Gestione** sono chiamate autorizzazioni di **Accesso completo** quando concesse nell'Interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="58154-150">**Read** and **Manage** permissions are called **Full Access** permission when granted in the Exchange admin center.</span></span> <span data-ttu-id="58154-151">Le autorizzazioni di Accesso completo non comportano anche le autorizzazioni **Invia come** o **Invia per conto di**.</span><span class="sxs-lookup"><span data-stu-id="58154-151">Full Access permission does not grant **Send as** or **Send on Behalf**  permissions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="58154-152">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58154-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  
  
2. <span data-ttu-id="58154-153">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58154-153">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="58154-154">Accanto a **Lettura e gestione**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58154-154">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="58154-155">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58154-155">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="58154-156">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58154-156">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="58154-157">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58154-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
  
2. <span data-ttu-id="58154-158">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58154-158">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>
    
3. <span data-ttu-id="58154-159">Accanto a **Lettura e gestione**, selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58154-159">Next to **Read and manage**, select **Edit**.</span></span> 
    
4. <span data-ttu-id="58154-160">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58154-160">Select **Add permissions**, then choose the name of the user or users that you want to allow to read email from this mailbox.</span></span>

5. <span data-ttu-id="58154-161">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58154-161">Select **Save**.</span></span>

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a><span data-ttu-id="58154-162">Inviare messaggi di posta elettronica per conto di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58154-162">Send email on behalf of another user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="58154-163">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58154-163">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="58154-164">Selezionare il nome dell'utente da cui si vuole concedere l'autorizzazione **Invia per conto di** per aprire il riquadro delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="58154-164">Select the name of the user (from whom you plan to give a **Send on behalf** permission) to open their properties pane.</span></span>
    
3. <span data-ttu-id="58154-165">Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58154-165">On the **Mail** tab, select **Manage mailbox permissions**.</span></span>
    
4. <span data-ttu-id="58154-166">Accanto a **Invia per conto di** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58154-166">Next to **Send on behalf**, select **Edit**.</span></span>

5. <span data-ttu-id="58154-167">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58154-167">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

6. <span data-ttu-id="58154-168">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58154-168">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="58154-169">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58154-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="58154-170">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58154-170">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="58154-171">Accanto a **Invia per conto di** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58154-171">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="58154-172">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58154-172">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="58154-173">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58154-173">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="58154-174">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="58154-174">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="58154-175">Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="58154-175">Select the user you want, expand **Mail Settings**, and then select **Edit** next to **Mailbox permissions**.</span></span>

3. <span data-ttu-id="58154-176">Accanto a **Invia per conto di** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="58154-176">Next to **Send on behalf**, select **Edit**.</span></span>
    
4. <span data-ttu-id="58154-177">Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="58154-177">Select **Add permissions**, then choose the name of the user or users that you want to allow to send email on behalf of this mailbox.</span></span>

5. <span data-ttu-id="58154-178">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="58154-178">Select **Save**.</span></span>

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a><span data-ttu-id="58154-179">Inviare e leggere messaggi da Outlook e Outlook sul Web per le aziende</span><span class="sxs-lookup"><span data-stu-id="58154-179">Send and read from Outlook and Outlook on the web for business</span></span>


<span data-ttu-id="58154-p108">Per informazioni su come inviare messaggi di posta elettronica dalla cassetta postale di un altro utente, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="58154-p108">Want to know how to send email from another user's mailbox? Check out the following topics:</span></span>
  
- [<span data-ttu-id="58154-182">Gestire gli elementi di posta e di calendario di un altro utente</span><span class="sxs-lookup"><span data-stu-id="58154-182">Manage another person's mail and calendar items</span></span>](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [<span data-ttu-id="58154-183">Inviare un messaggio di posta elettronica da un altro utente o gruppo</span><span class="sxs-lookup"><span data-stu-id="58154-183">Send email from another person or group</span></span>](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
