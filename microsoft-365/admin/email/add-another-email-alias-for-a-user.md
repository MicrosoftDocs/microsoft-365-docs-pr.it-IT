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
description: "Informazioni su come è possibile associare più di un indirizzo di posta elettronica, denominato alias di posta elettronica, all'account di Microsoft 365 per le aziende. "
ms.openlocfilehash: 4003dcfca29a722ccdf9b86cca5aa1141fbdb367
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892806"
---
# <a name="add-another-email-alias-for-a-user"></a><span data-ttu-id="bf0e0-103">Aggiungere un altro alias di posta elettronica per un utente</span><span class="sxs-lookup"><span data-stu-id="bf0e0-103">Add another email alias for a user</span></span>
  
<span data-ttu-id="bf0e0-104">Questo articolo è per gli amministratori di Microsoft 365 che hanno abbonamenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-104">This article is for Microsoft 365 administrators who have business subscriptions.</span></span> <span data-ttu-id="bf0e0-105">Non è destinato agli utenti privati.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-105">It's not for home users.</span></span>
  
<span data-ttu-id="bf0e0-106">Un indirizzo di posta elettronica principale in Microsoft 365 è in genere l'indirizzo di posta elettronica assegnato a un utente al momento della creazione dell'account.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-106">A primary email address in Microsoft 365 is usually the email address a user was assigned when their account was created.</span></span> <span data-ttu-id="bf0e0-107">Quando si invia un messaggio di posta elettronica a un altro utente, l'indirizzo di posta elettronica principale corrisponde in genere al contenuto del campo  *Da*  nelle app di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-107">When the user sends email to someone else, their primary email address is what typically appears in the  *From*  field in email apps.</span></span> <span data-ttu-id="bf0e0-108">Possono inoltre avere più di un indirizzo di posta elettronica associato al proprio account Microsoft 365 per le aziende.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-108">They can also have more than one email address associated with their Microsoft 365 for business account.</span></span> <span data-ttu-id="bf0e0-109">Questi indirizzi aggiuntivi sono detti alias.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-109">These additional addresses are called aliases.</span></span> 
  
<span data-ttu-id="bf0e0-110">Ad esempio, si supponga che Jenna abbia l'indirizzo di posta elettronica jenna@contosoco.com, ma che voglia anche ricevere posta elettronica all'indirizzo jen@contosoco.com perché alcune persone fanno riferimento a lei con quel nome.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-110">For example, let's say Jenna has the email address jenna@contosoco.com, but she also wants to receive email at jen@contosoco.com because some people refer to her by that name.</span></span> <span data-ttu-id="bf0e0-111">Puoi creare alias per lei in modo che entrambi gli indirizzi di posta elettronica vadano nella posta in arrivo di Jenna.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-111">You can create aliases for her so that both email addresses go to Jenna's inbox.</span></span>
<br><br>  
  
<span data-ttu-id="bf0e0-112">È possibile creare fino a 400 alias per utente.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-112">You can create up to 400 aliases for a user.</span></span> <span data-ttu-id="bf0e0-113">Non sono previsti ulteriori costi o licenze.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-113">No additional fees or licenses are required.</span></span>
  
> [!Tip]
> <span data-ttu-id="bf0e0-114">Se si desidera che più persone gestino la posta elettronica inviata a un singolo indirizzo di posta elettronica info@NodPublishers.com o sales@NodPublishers.com, creare una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-114">If you want multiple people to manage email sent to a single email address like info@NodPublishers.com or sales@NodPublishers.com, create a shared mailbox.</span></span> <span data-ttu-id="bf0e0-115">Per ulteriori informazioni, vedere [Create a shared mailbox](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="bf0e0-115">To learn more, see [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>
  
## <a name="add-email-aliases-to-a-user"></a><span data-ttu-id="bf0e0-116">Aggiungere alias di posta elettronica a un utente</span><span class="sxs-lookup"><span data-stu-id="bf0e0-116">Add email aliases to a user</span></span>
<span data-ttu-id="bf0e0-117"><a name="AddEmailPreview"> </a></span><span class="sxs-lookup"><span data-stu-id="bf0e0-117"><a name="AddEmailPreview"> </a></span></span>

<span data-ttu-id="bf0e0-118">A tale [scopo, è necessario](../add-users/about-admin-roles.md) disporre delle autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-118">You must have [admin permissions](../add-users/about-admin-roles.md) to do this.</span></span> 

  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="bf0e0-119">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="bf0e0-120">Nella pagina **Utenti attivi** selezionare l'utente > Gestisci alias di **posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-120">On the **Active Users** page, select the user > **Manage email aliases**.</span></span> <span data-ttu-id="bf0e0-121">Questa opzione non verrà visualizzata se alla persona non è assegnata una licenza.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-121">You won't see this option if the person doesn't have a license assigned to them.</span></span> 
    
3. <span data-ttu-id="bf0e0-122">Selezionare **+ Aggiungi un alias** e immettere un nuovo alias per l'utente.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-122">Select **+ Add an alias** and enter a new alias for the user.</span></span>   
    
    > [!Important] 
    > <span data-ttu-id="bf0e0-123">Se viene visualizzato il messaggio di errore " Non è possibile trovare un parametro corrispondente al nome del parametro **"EmailAddresses",** significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-123">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="bf0e0-124">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-124">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="bf0e0-125">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-125">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="bf0e0-126">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-126">If the problem persists, call Support and they will do a full sync for you.</span></span>
    
  
    > [!IMPORTANT]
    > <span data-ttu-id="bf0e0-127">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-127">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="bf0e0-128">L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-128">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="bf0e0-129">Per aggiungere un altro nome di dominio all'elenco, vedere [Aggiungere un dominio a Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="bf0e0-129">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 
  
     
5. <span data-ttu-id="bf0e0-130">Al termine, scegliere **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-130">When you're done, choose **Save changes**.</span></span>
    
6. <span data-ttu-id="bf0e0-131">Attendere 24 ore prima che i nuovi alias si popolino in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-131">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span>
    
    <span data-ttu-id="bf0e0-132">L'utente avrà ora un indirizzo principale e un alias.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-132">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="bf0e0-133">Ad esempio, tutta la posta inviata all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, verranno indirizzati alla posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-133">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="bf0e0-134">**Quando l'utente risponde, *l'indirizzo From* dipende dal client Outlook. Outlook sul Web utilizzerà l'alias con cui è stato ricevuto il messaggio di posta elettronica (verrà chiamato il principio ping-pong). Il desktop di Outlook utilizzerà il suo alias di posta elettronica principale.**</span><span class="sxs-lookup"><span data-stu-id="bf0e0-134">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="bf0e0-135">Si supponga, ad esempio, che un messaggio sia stato inviato a Sales@NodPublishers.com e che arrivi nella posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-135">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="bf0e0-136">Quando Eliza risponde al messaggio utilizzando outlook desktop, il suo indirizzo di posta elettronica principale verrà visualizzato come Eliza@NodPublishers.com, non Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-136">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"
    
1. <span data-ttu-id="bf0e0-137">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-137">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
    
2. <span data-ttu-id="bf0e0-138">Nella pagina **Utenti attivi** selezionare il nome della persona da modificare.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-138">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="bf0e0-139">Accanto a **Nome utente/Alias di posta elettronica** selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="bf0e0-139">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="bf0e0-140">Se viene visualizzato il messaggio di errore " Non è possibile trovare un parametro corrispondente al nome del parametro **"EmailAddresses",** significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-140">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="bf0e0-141">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-141">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="bf0e0-142">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-142">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="bf0e0-143">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-143">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="bf0e0-144">Nella casella di testo in **Alias** digitare la prima parte del nuovo alias di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-144">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="bf0e0-145">Se si è aggiunto il proprio dominio a Microsoft 365, è possibile specificarlo per il nuovo alias usando l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-145">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="bf0e0-146">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-146">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bf0e0-147">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-147">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="bf0e0-148">L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-148">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="bf0e0-149">Per aggiungere un altro nome di dominio all'elenco, vedere [Aggiungere un dominio a Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="bf0e0-149">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="bf0e0-150">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-150">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="bf0e0-151">Attendere 24 ore prima che i nuovi alias si popolino in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-151">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="bf0e0-152">L'utente avrà ora un indirizzo principale e un alias.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-152">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="bf0e0-153">Ad esempio, tutta la posta inviata all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, verranno indirizzati alla posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-153">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="bf0e0-154">**Quando l'utente risponde, *l'indirizzo From* dipende dal client Outlook. Outlook sul Web utilizzerà l'alias con cui è stato ricevuto il messaggio di posta elettronica (verrà chiamato il principio ping-pong). Il desktop di Outlook utilizzerà il suo alias di posta elettronica principale.**</span><span class="sxs-lookup"><span data-stu-id="bf0e0-154">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="bf0e0-155">Si supponga, ad esempio, che un messaggio sia stato inviato a Sales@NodPublishers.com e che arrivi nella posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-155">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="bf0e0-156">Quando Eliza risponde al messaggio utilizzando outlook desktop, il suo indirizzo di posta elettronica principale verrà visualizzato come Eliza@NodPublishers.com, non Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-156">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="bf0e0-157">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

    
2. <span data-ttu-id="bf0e0-158">Nella pagina **Utenti attivi** selezionare il nome della persona da modificare.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-158">On the **Active Users** page, select the name of the person you want to edit.</span></span>

3. <span data-ttu-id="bf0e0-159">Accanto a **Nome utente/Alias di posta elettronica** selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="bf0e0-159">Next to **Username / Email Aliases**, select **Edit**.</span></span>

    > [!Important] 
    > <span data-ttu-id="bf0e0-160">Se viene visualizzato il messaggio di errore " Non è possibile trovare un parametro corrispondente al nome del parametro **"EmailAddresses",** significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-160">If you get the error message "**A parameter cannot be found that matches parameter name 'EmailAddresses**," it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="bf0e0-161">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-161">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="bf0e0-162">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-162">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="bf0e0-163">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-163">If the problem persists, call Support and they will do a full sync for you.</span></span>

4. <span data-ttu-id="bf0e0-164">Nella casella di testo in **Alias** digitare la prima parte del nuovo alias di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-164">In the text box under **Alias**, type the first part of the new email alias.</span></span> <span data-ttu-id="bf0e0-165">Se si è aggiunto il proprio dominio a Microsoft 365, è possibile specificarlo per il nuovo alias usando l'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-165">If you added your own domain to Microsoft 365, you can choose the domain for the new email alias by using the drop-down list.</span></span> <span data-ttu-id="bf0e0-166">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-166">Then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bf0e0-167">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-167">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span> 
  
    > [!TIP]
    > <span data-ttu-id="bf0e0-168">L'alias di posta elettronica deve terminare con un dominio incluso nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-168">The email alias must end with a domain from the drop-down list.</span></span> <span data-ttu-id="bf0e0-169">Per aggiungere un altro nome di dominio all'elenco, vedere [Aggiungere un dominio a Microsoft 365.](../setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="bf0e0-169">To add another domain name to the list, see [Add a domain to Microsoft 365](../setup/add-domain.md).</span></span> 

5. <span data-ttu-id="bf0e0-170">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-170">When you're done, select **Save**.</span></span>

6. <span data-ttu-id="bf0e0-171">Attendere 24 ore prima che i nuovi alias si popolino in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-171">Wait 24 hours for the new aliases to populate throughout Microsoft 365.</span></span> 
    
    <span data-ttu-id="bf0e0-172">L'utente avrà ora un indirizzo principale e un alias.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-172">The user will now have a primary address and an alias.</span></span> <span data-ttu-id="bf0e0-173">Ad esempio, tutta la posta inviata all'indirizzo principale di Eliza Hoffman, Eliza@NodPublishers.com, e il suo alias, Sales@NodPublishers.com, verranno indirizzati alla posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-173">For example, all mail sent to Eliza Hoffman's primary address, Eliza@NodPublishers.com, and her  alias, Sales@NodPublishers.com, will go to Eliza's Inbox.</span></span>
    
  
7. <span data-ttu-id="bf0e0-174">**Quando l'utente risponde, *l'indirizzo From* dipende dal client Outlook. Outlook sul Web utilizzerà l'alias con cui è stato ricevuto il messaggio di posta elettronica (verrà chiamato il principio ping-pong). Il desktop di Outlook utilizzerà il suo alias di posta elettronica principale.**</span><span class="sxs-lookup"><span data-stu-id="bf0e0-174">**When the user replies, the *From* address will depend on her Outlook client. Outlook on the web will use the alias at which the email was received (we'll call this the ping-pong principle). Outlook desktop will use her primary email alias.**</span></span> <span data-ttu-id="bf0e0-175">Si supponga, ad esempio, che un messaggio sia stato inviato a Sales@NodPublishers.com e che arrivi nella posta in arrivo di Eliza.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-175">For example, let's say a message is sent to Sales@NodPublishers.com, and it arrives in Eliza's inbox.</span></span> <span data-ttu-id="bf0e0-176">Quando Eliza risponde al messaggio utilizzando outlook desktop, il suo indirizzo di posta elettronica principale verrà visualizzato come Eliza@NodPublishers.com, non Sales@NodPublishers.com.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-176">When Eliza replies to the message using Outlook desktop, her primary email address will appear as Eliza@NodPublishers.com, not Sales@NodPublishers.com.</span></span>

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a><span data-ttu-id="bf0e0-177">È stato visualizzato "Impossibile trovare un parametro corrispondente al nome del parametro EmailAddresses"?</span><span class="sxs-lookup"><span data-stu-id="bf0e0-177">Did you get "A parameter cannot be found that matches parameter name EmailAddresses"?</span></span>


<span data-ttu-id="bf0e0-178">Se viene visualizzato il messaggio di errore " Impossibile trovare un parametro corrispondente al nome del parametro **EmailAddresses**", significa che la configurazione del tenant o del dominio personalizzato richiede più tempo se ne è stato aggiunto uno di recente.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-178">If you get the error message "**A parameter cannot be found that matches parameter name EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one.</span></span> <span data-ttu-id="bf0e0-179">Per completare la configurazione possono essere necessarie fino a 4 ore.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-179">The setup process can take up to 4 hours to complete.</span></span> <span data-ttu-id="bf0e0-180">Attendere il tempo necessario per il completamento della procedura e quindi riprovare.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-180">Wait a while so the set up process has time to finish, and then try again.</span></span> <span data-ttu-id="bf0e0-181">Se il problema persiste, contattare il supporto, che provvederà a eseguire una sincronizzazione completa.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-181">If the problem persists, call Support and they will do a full sync for you.</span></span>
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a><span data-ttu-id="bf0e0-182">L'abbonamento è stato acquistato presso GoDaddy o un altro partner?</span><span class="sxs-lookup"><span data-stu-id="bf0e0-182">Did you purchase your subscription from GoDaddy or another Partner?</span></span>


<span data-ttu-id="bf0e0-183">Se l'abbonamento è stato acquistato presso GoDaddy o un altro partner, per impostare il nuovo alias come principale è necessario accedere alla console di gestione di GoDaddy o del partner.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-183">If you purchased your subscription from GoDaddy or another Partner, to set the new alias as the primary, you must go to the GoDaddy/partner management console.</span></span>

## <a name="sending-email-from-the-proxy-address-easily"></a><span data-ttu-id="bf0e0-184">Inviare facilmente messaggi di posta elettronica dall'indirizzo proxy</span><span class="sxs-lookup"><span data-stu-id="bf0e0-184">Sending email from the proxy address easily</span></span>

<span data-ttu-id="bf0e0-185">Ad aprile 2021 viene lanciata una nuova funzionalità che consente agli utenti di inviare facilmente dagli alias quando utilizzano Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-185">A new feature is rolling out in April 2021 that allows users to send from their aliases easily when using Outlook on the web.</span></span> <span data-ttu-id="bf0e0-186">Quando la funzionalità viene implementazione in una tenancy in cui l'amministratore tenant utilizza il cmdlet, gli utenti all'interno della tenancy avranno accesso a un elenco di caselle di controllo in cui ogni voce corrisponde a un alias nelle impostazioni di `Set-OrganizationConfig -SendFromAliasEnabled $true` Outlook.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-186">When the feature rolls out to a tenancy where the tenant admin uses the `Set-OrganizationConfig -SendFromAliasEnabled $true` cmdlet, users within the tenancy will get access to a list of checkboxes where each entry corresponds to an alias in their Outlook settings.</span></span> <span data-ttu-id="bf0e0-187">Se si seleziona un alias, l'alias verrà visualizzato nell'elenco a discesa Da del modulo Compose.</span><span class="sxs-lookup"><span data-stu-id="bf0e0-187">Selecting an alias will make it appear in the From dropdown in the Compose form.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="bf0e0-188">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="bf0e0-188">Related articles</span></span>

[<span data-ttu-id="bf0e0-189">Inviare un messaggio di posta elettronica da un indirizzo diverso</span><span class="sxs-lookup"><span data-stu-id="bf0e0-189">Send email from a different address</span></span>](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[<span data-ttu-id="bf0e0-190">Cambiare un nome utente e un indirizzo di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="bf0e0-190">Change a user name and email address</span></span>](../add-users/change-a-user-name-and-email-address.md)
