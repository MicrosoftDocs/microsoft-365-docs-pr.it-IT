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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: "Informazioni su come è possibile associare più indirizzi di posta elettronica, denominati alias di posta elettronica, all'account di Microsoft 365 per le aziende. "
ms.openlocfilehash: 3c97640f4bb16876ec028a1af2b361a21a0decab
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126406"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="296cd-103">Aggiungere un altro alias di posta elettronica per un utente</span><span class="sxs-lookup"><span data-stu-id="296cd-103">Add another email alias for a user</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="296cd-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="296cd-104">The admin center is changing.</span></span> <span data-ttu-id="296cd-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="296cd-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end
  
<span data-ttu-id="296cd-106">Questo articolo è per gli amministratori di Microsoft 365 che hanno abbonamenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="296cd-106">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="296cd-107">Non è destinato agli utenti privati.</span><span class="sxs-lookup"><span data-stu-id="296cd-107">It's not for home users.</span></span>
  
<span data-ttu-id="296cd-108">Un indirizzo di posta elettronica principale in Microsoft 365 è in genere l'indirizzo di posta elettronica assegnato a un utente al momento della creazione dell'account.</span><span class="sxs-lookup"><span data-stu-id="296cd-108">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="296cd-109">Quando si invia un messaggio di posta elettronica a un altro utente, l'indirizzo di posta elettronica principale corrisponde in genere al contenuto del campo  *Da*  nelle app di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="296cd-109">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="296cd-110">Possono inoltre avere più di un indirizzo di posta elettronica associato al proprio account Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="296cd-110">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="296cd-111">Questi indirizzi aggiuntivi sono detti alias.</span><span class="sxs-lookup"><span data-stu-id="296cd-111">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="296cd-112">Si supponga, ad esempio, che Jenna abbia l'indirizzo di posta elettronica jenna@contosoco.com, ma che voglia anche ricevere posta elettronica a jen@contosoco.com perché alcune persone le fanno riferimento con quel nome.</span><span class="sxs-lookup"><span data-stu-id="296cd-112">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="296cd-113">È possibile creare alias per lei in modo che entrambi gli indirizzi di posta elettronica vadano nella posta in arrivo di Jenna.</span><span class="sxs-lookup"><span data-stu-id="296cd-113">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="296cd-114">È possibile creare fino a 400 alias per utente.</span><span class="sxs-lookup"><span data-stu-id="296cd-114">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="296cd-115">Non sono previsti ulteriori costi o licenze.</span><span class="sxs-lookup"><span data-stu-id="296cd-115">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="296cd-116">Se si desidera che più persone gestino la posta elettronica inviata a un singolo indirizzo di posta elettronica come info@NodPublishers.com o sales@NodPublishers.com, creare una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="296cd-116">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="296cd-117">Per ulteriori informazioni, vedere [Creare una cassetta postale condivisa.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="296cd-117">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="296cd-118">Aggiungere alias di posta elettronica a un utente</span><span class="sxs-lookup"><span data-stu-id="296cd-118">Add email aliases to a user</span></span>
<span data-ttu-id="296cd-119"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="296cd-119"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="296cd-120">A tale [scopo, è necessario](../add-users/about-admin-roles.md) disporre delle autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="296cd-120">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="296cd-121">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="296cd-121">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="296cd-122">Nella pagina **Utenti attivi selezionare** l'utente che > gli alias di posta **elettronica.**</span><span class="sxs-lookup"><span data-stu-id="296cd-122">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="296cd-123">Questa opzione non verrà visualizzata se all'utente non è assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="296cd-123">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="296cd-124">Selezionare **+ Aggiungi un alias** e immettere un nuovo alias per l'utente.</span><span class="sxs-lookup"><span data-stu-id="296cd-124">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="296cd-125">Se viene visualizzato il messaggio di errore "Impossibile trovare un parametro che corrisponde al nome del parametro **"EmailAddresses",** significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente.</span><span class="sxs-lookup"><span data-stu-id="296cd-125">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="296cd-126">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="296cd-126">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="296cd-127">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="296cd-127">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="296cd-128">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="296cd-128">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="296cd-129">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="296cd-129">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="296cd-130">L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="296cd-130">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="296cd-131">Per aggiungere un altro nome di dominio all'elenco, vedere [Aggiungere un dominio a Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="296cd-131">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 
  
     
5. <span data-ttu-id="296cd-132">Al termine, scegliere **Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="296cd-132">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="296cd-133">Attendere 24 ore che i nuovi alias si popolino in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="296cd-133">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="296cd-134">L'utente avrà ora un indirizzo principale e un alias.</span><span class="sxs-lookup"><span data-stu-id="296cd-134">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="296cd-135">Ad esempio, tutta la posta inviata all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com e il suo alias, Sales@NodPublishers.com, verranno indirizzati alla cartella Posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="296cd-135">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="296cd-136">**Quando l'utente risponde, l'indirizzo *mittente*  sarà il suo alias di posta elettronica principale.**</span><span class="sxs-lookup"><span data-stu-id="296cd-136">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="296cd-137">Ad esempio, si supponga che un messaggio sia inviato a Sales@NodPublishers.com e che arrivi nella posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="296cd-137">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="296cd-138">Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non come Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="296cd-138">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="296cd-139">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="296cd-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="296cd-140">Nella pagina **Utenti attivi** selezionare il nome della persona da modificare.</span><span class="sxs-lookup"><span data-stu-id="296cd-140">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="296cd-141">Accanto a **Nome utente/Alias di posta elettronica** selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="296cd-141">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="296cd-142">Se viene visualizzato il messaggio di errore "Impossibile trovare un parametro che corrisponde al nome del parametro **"EmailAddresses",** significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente.</span><span class="sxs-lookup"><span data-stu-id="296cd-142">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="296cd-143">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="296cd-143">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="296cd-144">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="296cd-144">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="296cd-145">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="296cd-145">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="296cd-146">Nella casella di testo sotto **Alias** digitare la prima parte del nuovo alias di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="296cd-146">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="296cd-147">Se si è aggiunto il proprio dominio a Microsoft 365, è possibile specificarlo per il nuovo alias usando l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="296cd-147">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="296cd-148">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="296cd-148">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="296cd-149">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="296cd-149">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="296cd-150">L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="296cd-150">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="296cd-151">Per aggiungere un altro nome di dominio all'elenco, vedere [Aggiungere un dominio a Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="296cd-151">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="296cd-152">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="296cd-152">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="296cd-153">Attendere 24 ore che i nuovi alias si popolino in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="296cd-153">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="296cd-154">L'utente avrà ora un indirizzo principale e un alias.</span><span class="sxs-lookup"><span data-stu-id="296cd-154">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="296cd-155">Ad esempio, tutta la posta inviata all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com e il suo alias, Sales@NodPublishers.com, verranno indirizzati alla cartella Posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="296cd-155">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="296cd-156">**Quando l'utente risponde, l'indirizzo *mittente*  sarà il suo alias di posta elettronica principale.**</span><span class="sxs-lookup"><span data-stu-id="296cd-156">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="296cd-157">Ad esempio, si supponga che un messaggio sia inviato a Sales@NodPublishers.com e che arrivi nella posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="296cd-157">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="296cd-158">Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non come Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="296cd-158">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="296cd-159">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="296cd-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="296cd-160">Nella pagina **Utenti attivi** selezionare il nome della persona da modificare.</span><span class="sxs-lookup"><span data-stu-id="296cd-160">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="296cd-161">Accanto a **Nome utente/Alias di posta elettronica** selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="296cd-161">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="296cd-162">Se viene visualizzato il messaggio di errore "Impossibile trovare un parametro che corrisponde al nome del parametro **"EmailAddresses",** significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente.</span><span class="sxs-lookup"><span data-stu-id="296cd-162">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="296cd-163">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="296cd-163">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="296cd-164">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="296cd-164">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="296cd-165">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="296cd-165">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="296cd-166">Nella casella di testo sotto **Alias** digitare la prima parte del nuovo alias di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="296cd-166">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="296cd-167">Se si è aggiunto il proprio dominio a Microsoft 365, è possibile specificarlo per il nuovo alias usando l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="296cd-167">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="296cd-168">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="296cd-168">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="296cd-169">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="296cd-169">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="296cd-170">L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="296cd-170">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="296cd-171">Per aggiungere un altro nome di dominio all'elenco, vedere [Aggiungere un dominio a Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="296cd-171">To add another domain name to the list, see [Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain).</span></span> 

5. <span data-ttu-id="296cd-172">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="296cd-172">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="296cd-173">Attendere 24 ore che i nuovi alias si popolino in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="296cd-173">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="296cd-174">L'utente avrà ora un indirizzo principale e un alias.</span><span class="sxs-lookup"><span data-stu-id="296cd-174">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="296cd-175">Ad esempio, tutta la posta inviata all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com e il suo alias, Sales@NodPublishers.com, verranno indirizzati alla cartella Posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="296cd-175">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="296cd-176">**Quando l'utente risponde, l'indirizzo *mittente*  sarà il suo alias di posta elettronica principale.**</span><span class="sxs-lookup"><span data-stu-id="296cd-176">**When the user replies, the *From*  address will be her primary email alias.**</span></span> <span data-ttu-id="296cd-177">Ad esempio, si supponga che un messaggio sia inviato a Sales@NodPublishers.com e che arrivi nella posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="296cd-177">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="296cd-178">Quando Eliza risponde al messaggio, il suo indirizzo di posta elettronica principale verrà visualizzato come mittente, non come Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="296cd-178">When Eliza replies to the message, her primary email address will appear as the sender, not Sales@NodPublishers.com.</span></span> 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="296cd-179">È stato visualizzato il messaggio "Impossibile trovare un parametro che corrisponde al nome del parametro EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="296cd-179">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="296cd-180">Se viene visualizzato il messaggio di errore "Impossibile trovare un parametro corrispondente al nome del parametro **EmailAddresses",** significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente.</span><span class="sxs-lookup"><span data-stu-id="296cd-180">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="296cd-181">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="296cd-181">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="296cd-182">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="296cd-182">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="296cd-183">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="296cd-183">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="296cd-184">L'abbonamento è stato acquistato presso GoDaddy o un altro partner?</span><span class="sxs-lookup"><span data-stu-id="296cd-184">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="296cd-185">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="296cd-185">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="296cd-186">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="296cd-186">Related articles</span></span>

[<span data-ttu-id="296cd-187">Inviare un messaggio di posta elettronica da un indirizzo diverso</span><span class="sxs-lookup"><span data-stu-id="296cd-187">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="296cd-188">Cambiare un nome utente e un indirizzo di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="296cd-188">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
  

