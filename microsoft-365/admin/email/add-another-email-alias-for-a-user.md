---
title: Aggiungere un altro alias di posta elettronica per un utente
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
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: "Informazioni su come è possibile disporre di più indirizzi di posta elettronica, denominati alias di posta elettronica, associati all'account Microsoft 365 for business. "
ms.openlocfilehash: bab4ace6d497bac8892a29c76b6f2d05c4fa018f
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432326"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="30684-103">Aggiungere un altro alias di posta elettronica per un utente</span><span class="sxs-lookup"><span data-stu-id="30684-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="30684-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="30684-104">The admin center is changing.</span></span> <span data-ttu-id="30684-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="30684-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="30684-106">Questo articolo è per gli amministratori di Microsoft 365 che dispongono di sottoscrizioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="30684-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="30684-107">Non è destinato agli utenti privati.</span><span class="sxs-lookup"><span data-stu-id="30684-107">It's not for home users.</span></span>
  
<span data-ttu-id="30684-108">Un indirizzo di posta elettronica principale in Microsoft 365 è in genere l'indirizzo di posta elettronica a cui è stato assegnato un utente quando è stato creato l'account.</span><span class="sxs-lookup"><span data-stu-id="30684-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="30684-109">Quando si invia un messaggio di posta elettronica a un altro utente, l'indirizzo di posta elettronica principale corrisponde in genere al contenuto del campo  *Da*  nelle app di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="30684-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="30684-110">Possono anche avere più di un indirizzo di posta elettronica associato al proprio account Microsoft 365 for business.</span><span class="sxs-lookup"><span data-stu-id="30684-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="30684-111">Questi indirizzi aggiuntivi sono detti alias.</span><span class="sxs-lookup"><span data-stu-id="30684-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="30684-112">Ad esempio, si supponga che Jenna abbia l'indirizzo di posta elettronica jenna@contosoco.com, ma desidera anche ricevere messaggi di posta elettronica in jen@contosoco.com perché alcune persone si riferiscono a lei con quel nome.</span><span class="sxs-lookup"><span data-stu-id="30684-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="30684-113">È possibile creare alias per lei in modo che entrambi gli indirizzi di posta elettronica vadano alla posta in arrivo di Jenna.</span><span class="sxs-lookup"><span data-stu-id="30684-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="30684-114">È possibile creare fino a 400 alias per utente.</span><span class="sxs-lookup"><span data-stu-id="30684-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="30684-115">Non sono previsti ulteriori costi o licenze.</span><span class="sxs-lookup"><span data-stu-id="30684-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="30684-116">Se si desidera che più persone gestiscano la posta elettronica inviata a un singolo indirizzo di posta elettronica, come info@NodPublishers.com o sales@NodPublishers.com, creare una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="30684-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="30684-117">Per ulteriori informazioni, vedere [creare una cassetta postale condivisa](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="30684-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="30684-118">Aggiungere alias di posta elettronica a un utente</span><span class="sxs-lookup"><span data-stu-id="30684-118">Add email aliases to a user</span></span>
<span data-ttu-id="30684-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="30684-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="30684-120">Per eseguire questa operazione, è necessario disporre [delle autorizzazioni di amministratore](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="30684-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="30684-121">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="30684-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="30684-122">Nella pagina **utenti attivi** selezionare l'utente > gestire gli **alias di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="30684-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="30684-123">Questa opzione non viene visualizzata se alla persona non è stata assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="30684-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="30684-124">Selezionare **+ Aggiungi un alias** e immettere un nuovo alias per l'utente.</span><span class="sxs-lookup"><span data-stu-id="30684-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="30684-125">Se viene visualizzato il messaggio di errore "**non è possibile trovare un parametro che corrisponda al nome del parametro" EmailAddresses**", significa che richiede un po' di tempo per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto di recente uno.</span><span class="sxs-lookup"><span data-stu-id="30684-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="30684-126">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="30684-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="30684-127">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="30684-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="30684-128">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="30684-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="30684-129">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="30684-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="30684-130">L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="30684-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="30684-131">Per aggiungere un altro nome di dominio all'elenco, vedere [aggiungere un dominio a Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="30684-131">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="30684-132">Al termine, scegliere **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="30684-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="30684-133">Attendere 24 ore per il popolamento dei nuovi alias in Office 365.</span><span class="sxs-lookup"><span data-stu-id="30684-133">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="30684-134">L'utente avrà ora un indirizzo primario e un alias.</span><span class="sxs-lookup"><span data-stu-id="30684-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="30684-135">Ad esempio, tutti i messaggi inviati all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, andranno alla posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="30684-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="30684-136">**Quando l'utente risponde, l'indirizzo mittente sarà l'alias *di* posta elettronica principale.**</span><span class="sxs-lookup"><span data-stu-id="30684-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="30684-137">Si supponga, ad esempio, che venga inviato un messaggio a Sales@NodPublishers.com, che arriva nella posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="30684-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="30684-138">Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="30684-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="30684-139">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="30684-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="30684-140">Nella pagina **Utenti attivi** selezionare il nome della persona da modificare.</span><span class="sxs-lookup"><span data-stu-id="30684-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="30684-141">Accanto a **nome utente/alias di posta elettronica**, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="30684-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="30684-142">Se viene visualizzato il messaggio di errore "**non è possibile trovare un parametro che corrisponda al nome del parametro" EmailAddresses**", significa che richiede un po' di tempo per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto di recente uno.</span><span class="sxs-lookup"><span data-stu-id="30684-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="30684-143">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="30684-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="30684-144">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="30684-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="30684-145">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="30684-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="30684-146">Nella casella di testo in **alias**Digitare la prima parte del nuovo alias di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="30684-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="30684-147">Se si è aggiunto il proprio dominio a Office 365, è possibile specificarlo per il nuovo alias usando l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="30684-147">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="30684-148">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="30684-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="30684-149">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="30684-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="30684-150">L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="30684-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="30684-151">Per aggiungere un altro nome di dominio all'elenco, vedere [aggiungere un dominio a Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="30684-151">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="30684-152">Al termine, seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="30684-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="30684-153">Attendere 24 ore per il popolamento dei nuovi alias in Office 365.</span><span class="sxs-lookup"><span data-stu-id="30684-153">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="30684-154">L'utente avrà ora un indirizzo primario e un alias.</span><span class="sxs-lookup"><span data-stu-id="30684-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="30684-155">Ad esempio, tutti i messaggi inviati all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, andranno alla posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="30684-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="30684-156">**Quando l'utente risponde, l'indirizzo mittente sarà l'alias *di* posta elettronica principale.**</span><span class="sxs-lookup"><span data-stu-id="30684-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="30684-157">Si supponga, ad esempio, che venga inviato un messaggio a Sales@NodPublishers.com, che arriva nella posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="30684-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="30684-158">Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="30684-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="30684-159">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="30684-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="30684-160">Nella pagina **Utenti attivi** selezionare il nome della persona da modificare.</span><span class="sxs-lookup"><span data-stu-id="30684-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="30684-161">Accanto a **nome utente/alias di posta elettronica**, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="30684-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="30684-162">Se viene visualizzato il messaggio di errore "**non è possibile trovare un parametro che corrisponda al nome del parametro" EmailAddresses**", significa che richiede un po' di tempo per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto di recente uno.</span><span class="sxs-lookup"><span data-stu-id="30684-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="30684-163">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="30684-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="30684-164">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="30684-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="30684-165">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="30684-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="30684-166">Nella casella di testo in **alias**Digitare la prima parte del nuovo alias di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="30684-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="30684-167">Se si è aggiunto il proprio dominio a Office 365, è possibile specificarlo per il nuovo alias usando l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="30684-167">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="30684-168">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="30684-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="30684-169">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="30684-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="30684-170">L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="30684-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="30684-171">Per aggiungere un altro nome di dominio all'elenco, vedere [aggiungere un dominio a Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span><span class="sxs-lookup"><span data-stu-id="30684-171">To add another domain name to the list, see [Add a domain to Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="30684-172">Al termine, seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="30684-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="30684-173">Attendere 24 ore per il popolamento dei nuovi alias in Office 365.</span><span class="sxs-lookup"><span data-stu-id="30684-173">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="30684-174">L'utente avrà ora un indirizzo primario e un alias.</span><span class="sxs-lookup"><span data-stu-id="30684-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="30684-175">Ad esempio, tutti i messaggi inviati all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, andranno alla posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="30684-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="30684-176">**Quando l'utente risponde, l'indirizzo mittente sarà l'alias *di* posta elettronica principale.**</span><span class="sxs-lookup"><span data-stu-id="30684-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="30684-177">Si supponga, ad esempio, che venga inviato un messaggio a Sales@NodPublishers.com, che arriva nella posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="30684-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="30684-178">Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="30684-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="30684-179">È stato visualizzato "non è possibile trovare un parametro che corrisponda al nome del parametro EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="30684-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="30684-180">Se viene visualizzato il messaggio di errore "**non è possibile trovare un parametro che corrisponda al nome del parametro EmailAddresses**" significa che è necessario un po' di tempo per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto di recente uno.</span><span class="sxs-lookup"><span data-stu-id="30684-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="30684-181">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="30684-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="30684-182">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="30684-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="30684-183">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="30684-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="30684-184">L'abbonamento è stato acquistato presso GoDaddy o un altro partner?</span><span class="sxs-lookup"><span data-stu-id="30684-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="30684-185">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="30684-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="30684-186">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="30684-186">Related articles</span></span>

[<span data-ttu-id="30684-187">Inviare un messaggio di posta elettronica da un indirizzo diverso</span><span class="sxs-lookup"><span data-stu-id="30684-187">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="30684-188">Cambiare un nome utente e un indirizzo di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="30684-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

