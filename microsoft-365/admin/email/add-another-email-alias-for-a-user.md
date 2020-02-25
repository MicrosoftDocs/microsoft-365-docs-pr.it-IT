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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: "Informazioni su come è possibile disporre di più indirizzi di posta elettronica, denominati alias di posta elettronica, associati all'account di Office 365 for business. "
ms.openlocfilehash: 10f219f380d30a5ee8e9822e7a35ee533d165c33
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42253099"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="042a8-103">Aggiungere un altro alias di posta elettronica per un utente</span><span class="sxs-lookup"><span data-stu-id="042a8-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="042a8-104">Questo articolo è per gli amministratori di Office 365 che dispongono di sottoscrizioni di business.</span><span class="sxs-lookup"><span data-stu-id="042a8-104">This article is for Office 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="042a8-105">Non è destinato agli utenti privati.</span><span class="sxs-lookup"><span data-stu-id="042a8-105">It's not for home users.</span></span>
  
<span data-ttu-id="042a8-106">Un indirizzo di posta elettronica principale in Office 365 è in genere l'indirizzo di posta elettronica a cui è stato assegnato un utente quando è stato creato l'account.</span><span class="sxs-lookup"><span data-stu-id="042a8-106">A primary email address in Office 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="042a8-107">Quando si invia un messaggio di posta elettronica a un altro utente, l'indirizzo di posta elettronica principale corrisponde in genere al contenuto del campo  *Da*  nelle app di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="042a8-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="042a8-108">Si possono associare più indirizzi di posta elettronica al proprio account di Office 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="042a8-108">They can also have more than one email address associated with their Office 365 for business account.</span></span> <span data-ttu-id="042a8-109">Questi indirizzi aggiuntivi sono detti alias.</span><span class="sxs-lookup"><span data-stu-id="042a8-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="042a8-110">Ad esempio, si supponga che Jenna abbia l'indirizzo di posta elettronica jenna@contosoco.com, ma desidera anche ricevere messaggi di posta elettronica in jen@contosoco.com perché alcune persone si riferiscono a lei con quel nome.</span><span class="sxs-lookup"><span data-stu-id="042a8-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="042a8-111">È possibile creare alias per lei in modo che entrambi gli indirizzi di posta elettronica vadano alla posta in arrivo di Jenna.</span><span class="sxs-lookup"><span data-stu-id="042a8-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="042a8-112">È possibile creare fino a 400 alias per utente.</span><span class="sxs-lookup"><span data-stu-id="042a8-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="042a8-113">Non sono previsti ulteriori costi o licenze.</span><span class="sxs-lookup"><span data-stu-id="042a8-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="042a8-114">Se si desidera che più persone gestiscano la posta elettronica inviata a un singolo indirizzo di posta elettronica, come info@NodPublishers.com o sales@NodPublishers.com, creare una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="042a8-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="042a8-115">Per ulteriori informazioni, vedere [creare una cassetta postale condivisa](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="042a8-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="042a8-116">Aggiungere alias di posta elettronica a un utente</span><span class="sxs-lookup"><span data-stu-id="042a8-116">Add email aliases to a user</span></span>
<span data-ttu-id="042a8-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="042a8-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="042a8-118">Per eseguire questa operazione, è necessario disporre [delle autorizzazioni di amministratore](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="042a8-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="042a8-119">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="042a8-119">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="042a8-120">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="042a8-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="042a8-121">Nella pagina **utenti attivi** selezionare l'utente > gestire gli **alias di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="042a8-121">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="042a8-122">Questa opzione non viene visualizzata se alla persona non è stata assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="042a8-122">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="042a8-123">Selezionare **+ Aggiungi un alias** e immettere un nuovo alias per l'utente.</span><span class="sxs-lookup"><span data-stu-id="042a8-123">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="042a8-124">Se viene visualizzato il messaggio di errore "**non è possibile trovare un parametro che corrisponda al nome del parametro" EmailAddresses**", significa che richiede un po' di tempo per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto di recente uno.</span><span class="sxs-lookup"><span data-stu-id="042a8-124">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="042a8-125">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="042a8-125">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="042a8-126">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="042a8-126">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="042a8-127">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="042a8-127">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="042a8-128">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="042a8-128">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="042a8-129">L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="042a8-129">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="042a8-130">Per aggiungere un altro nome di dominio all'elenco, vedere [aggiungere un dominio a Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span><span class="sxs-lookup"><span data-stu-id="042a8-130">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 
  
     
5. <span data-ttu-id="042a8-131">Al termine, scegliere **Save Changes**.</span><span class="sxs-lookup"><span data-stu-id="042a8-131">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="042a8-132">Attendere 24 ore per il popolamento dei nuovi alias in Office 365.</span><span class="sxs-lookup"><span data-stu-id="042a8-132">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span>
    
    <span data-ttu-id="042a8-133">L'utente avrà ora un indirizzo primario e un alias.</span><span class="sxs-lookup"><span data-stu-id="042a8-133">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="042a8-134">Ad esempio, tutti i messaggi inviati all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, andranno alla posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="042a8-134">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="042a8-135">**Quando l'utente risponde, l'indirizzo mittente sarà l'alias *di* posta elettronica principale.**</span><span class="sxs-lookup"><span data-stu-id="042a8-135">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="042a8-136">Si supponga, ad esempio, che venga inviato un messaggio a Sales@NodPublishers.com, che arriva nella posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="042a8-136">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="042a8-137">Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="042a8-137">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="042a8-138">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="042a8-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="042a8-139">Nella pagina **Utenti attivi** selezionare il nome della persona da modificare.</span><span class="sxs-lookup"><span data-stu-id="042a8-139">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="042a8-140">Accanto a **nome utente/alias di posta elettronica**, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="042a8-140">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="042a8-141">Se viene visualizzato il messaggio di errore "**non è possibile trovare un parametro che corrisponda al nome del parametro" EmailAddresses**", significa che richiede un po' di tempo per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto di recente uno.</span><span class="sxs-lookup"><span data-stu-id="042a8-141">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="042a8-142">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="042a8-142">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="042a8-143">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="042a8-143">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="042a8-144">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="042a8-144">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="042a8-145">Nella casella di testo in **alias**Digitare la prima parte del nuovo alias di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="042a8-145">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="042a8-146">Se si è aggiunto il proprio dominio a Office 365, è possibile specificarlo per il nuovo alias usando l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="042a8-146">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="042a8-147">Quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="042a8-147">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="042a8-148">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="042a8-148">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="042a8-149">L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="042a8-149">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="042a8-150">Per aggiungere un altro nome di dominio all'elenco, vedere [aggiungere un dominio a Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span><span class="sxs-lookup"><span data-stu-id="042a8-150">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 

5. <span data-ttu-id="042a8-151">Al termine, seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="042a8-151">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="042a8-152">Attendere 24 ore per il popolamento dei nuovi alias in Office 365.</span><span class="sxs-lookup"><span data-stu-id="042a8-152">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="042a8-153">L'utente avrà ora un indirizzo primario e un alias.</span><span class="sxs-lookup"><span data-stu-id="042a8-153">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="042a8-154">Ad esempio, tutti i messaggi inviati all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, andranno alla posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="042a8-154">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="042a8-155">**Quando l'utente risponde, l'indirizzo mittente sarà l'alias *di* posta elettronica principale.**</span><span class="sxs-lookup"><span data-stu-id="042a8-155">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="042a8-156">Si supponga, ad esempio, che venga inviato un messaggio a Sales@NodPublishers.com, che arriva nella posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="042a8-156">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="042a8-157">Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="042a8-157">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="042a8-158">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="042a8-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="042a8-159">Nella pagina **Utenti attivi** selezionare il nome della persona da modificare.</span><span class="sxs-lookup"><span data-stu-id="042a8-159">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="042a8-160">Accanto a **nome utente/alias di posta elettronica**, selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="042a8-160">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="042a8-161">Se viene visualizzato il messaggio di errore "**non è possibile trovare un parametro che corrisponda al nome del parametro" EmailAddresses**", significa che richiede un po' di tempo per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto di recente uno.</span><span class="sxs-lookup"><span data-stu-id="042a8-161">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="042a8-162">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="042a8-162">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="042a8-163">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="042a8-163">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="042a8-164">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="042a8-164">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="042a8-165">Nella casella di testo in **alias**Digitare la prima parte del nuovo alias di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="042a8-165">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="042a8-166">Se si è aggiunto il proprio dominio a Office 365, è possibile specificarlo per il nuovo alias usando l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="042a8-166">If you added your own domain to Office 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="042a8-167">Quindi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="042a8-167">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="042a8-168">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="042a8-168">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="042a8-169">L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="042a8-169">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="042a8-170">Per aggiungere un altro nome di dominio all'elenco, vedere [aggiungere un dominio a Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span><span class="sxs-lookup"><span data-stu-id="042a8-170">To add another domain name to the list, see [Add a domain to Office 365](https://support.office.com/article/2d2fa996-b760-411d-a5cc-190d63f13207.aspx).</span></span> 

5. <span data-ttu-id="042a8-171">Al termine, seleziona **Salva**.</span><span class="sxs-lookup"><span data-stu-id="042a8-171">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="042a8-172">Attendere 24 ore per il popolamento dei nuovi alias in Office 365.</span><span class="sxs-lookup"><span data-stu-id="042a8-172">Wait 24 hours for the new aliases to populate throughout Office 365.</span></span> 
    
    <span data-ttu-id="042a8-173">L'utente avrà ora un indirizzo primario e un alias.</span><span class="sxs-lookup"><span data-stu-id="042a8-173">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="042a8-174">Ad esempio, tutti i messaggi inviati all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, andranno alla posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="042a8-174">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="042a8-175">**Quando l'utente risponde, l'indirizzo mittente sarà l'alias *di* posta elettronica principale.**</span><span class="sxs-lookup"><span data-stu-id="042a8-175">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="042a8-176">Si supponga, ad esempio, che venga inviato un messaggio a Sales@NodPublishers.com, che arriva nella posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="042a8-176">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="042a8-177">Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="042a8-177">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="042a8-178">È stato visualizzato "non è possibile trovare un parametro che corrisponda al nome del parametro EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="042a8-178">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="042a8-179">Se viene visualizzato il messaggio di errore "**non è possibile trovare un parametro che corrisponda al nome del parametro EmailAddresses**" significa che è necessario un po' di tempo per completare la configurazione del tenant o del dominio personalizzato, se ne è stato aggiunto di recente uno.</span><span class="sxs-lookup"><span data-stu-id="042a8-179">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="042a8-180">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="042a8-180">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="042a8-181">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="042a8-181">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="042a8-182">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="042a8-182">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="042a8-183">L'abbonamento è stato acquistato presso GoDaddy o un altro partner?</span><span class="sxs-lookup"><span data-stu-id="042a8-183">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="042a8-184">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="042a8-184">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="042a8-185">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="042a8-185">Related articles</span></span>

[<span data-ttu-id="042a8-186">Inviare un messaggio di posta elettronica da un indirizzo diverso</span><span class="sxs-lookup"><span data-stu-id="042a8-186">Send email from a different address</span></span>](https://support.office.com/article/ccba89cb-141c-4a36-8c56-6d16a8556d2e.aspx)

[<span data-ttu-id="042a8-187">Cambiare un nome utente e un indirizzo di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="042a8-187">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

