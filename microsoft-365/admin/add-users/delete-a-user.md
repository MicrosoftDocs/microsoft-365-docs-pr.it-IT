---
title: Eliminare un utente dall'organizzazione
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
- SPO_Content
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Informazioni su come eliminare un account utente. Decidere cosa fare con l'indirizzo di posta elettronica dell'utente, il contenuto di OneDrive e se mantenere la licenza del prodotto o smettere di pagarla.
ms.openlocfilehash: 2c87f04675ec92e964acb6fc9aef7171b6d7d510
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353137"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="4d586-104">Eliminare un utente dall'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4d586-104">Delete a user from your organization</span></span>
  
||
|:-----|
|<span data-ttu-id="4d586-105">**Per informazioni su come *eliminare l'account* utente di Office 365 utilizzato al lavoro o all'Istituto di istruzione? Rivolgersi al supporto tecnico del proprio lavoro o dell'Università per eseguire queste operazioni.**</span><span class="sxs-lookup"><span data-stu-id="4d586-105">**Looking for how to delete your *own* Office 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>|
   
## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="4d586-106">Informazioni necessarie relative all'eliminazione degli utenti</span><span class="sxs-lookup"><span data-stu-id="4d586-106">What you need to know about deleting users</span></span>

- <span data-ttu-id="4d586-107">Solo le persone con autorizzazioni di [amministratore globale di Office 365](about-admin-roles.md) o di gestione degli utenti per l'azienda o l'istituto di istruzione possono eliminare gli account utente.</span><span class="sxs-lookup"><span data-stu-id="4d586-107">Only people who have [Office 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span> 
    
- <span data-ttu-id="4d586-108">Si hanno a disposizione 30 giorni per [ripristinare](restore-user.md) l'account prima che i dati dell'utente vengano eliminati definitivamente.</span><span class="sxs-lookup"><span data-stu-id="4d586-108">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span> 
    
- <span data-ttu-id="4d586-p102">Se si vogliono mantenere i dati di OneDrive dell'utente, spostarli in una posizione diversa. È possibile eseguire questa operazione fino a 30 giorni dopo l'eliminazione dell'account. Vedere [Accedere ai dati di un ex utente ed eseguirne il backup](get-access-to-and-back-up-a-former-user-s-data.md). Non è necessario spostare i file di SharePoint dell'utente, perché saranno ancora accessibili.</span><span class="sxs-lookup"><span data-stu-id="4d586-p102">If you want to keep the user's OneDrive data, move it to a different location. You can even do this up to 30 days after deleting the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md). You don't need to move their SharePoint files; you'll still have access to them.</span></span>
    
- <span data-ttu-id="4d586-p103">Se si vuole mantenere la posta elettronica dell'utente, **PRIMA** di eliminare l'account spostarla in una posizione diversa. Se l'account è già stato eliminato, è possibile ripristinarlo entro 30 giorni, spostare i dati della posta elettronica e quindi eliminare l'account. Vedere [Accedere ai dati di un ex utente ed eseguirne il backup](get-access-to-and-back-up-a-former-user-s-data.md).</span><span class="sxs-lookup"><span data-stu-id="4d586-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
    
- <span data-ttu-id="4d586-116">Se si dispone di un abbonamento Enterprise come Office 365 Enterprise E3, è possibile conservare i dati delle cassette postali di un account utente di Office 365 eliminato trasformandola in una *cassetta postale inattiva*.</span><span class="sxs-lookup"><span data-stu-id="4d586-116">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted Office 365 user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="4d586-117">Per saperne di più, vedere [Gestire le cassette postali inattive in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="4d586-117">To learn more, see [Manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span>


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="4d586-118">Amministratore globale: eliminare un utente, smettere di pagare la propria licenza e scegliere cosa fare con i propri messaggi di posta elettronica e contenuti di OneDrive</span><span class="sxs-lookup"><span data-stu-id="4d586-118">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="4d586-119">Se si è un amministratore globale, quando si elimina un utente, è anche possibile concedere a un altro utente l'accesso al proprio indirizzo di posta elettronica e scegliere cosa fare con il contenuto di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4d586-119">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span> 

  
### <a name="things-to-consider"></a><span data-ttu-id="4d586-120">Aspetti da considerare</span><span class="sxs-lookup"><span data-stu-id="4d586-120">Things to consider...</span></span>

<span data-ttu-id="4d586-121">Prima di iniziare, considerare cosa si vuole fare con la posta elettronica e il contenuto di OneDrive dell'utente e se si desidera mantenere la licenza o smettere di pagarla.</span><span class="sxs-lookup"><span data-stu-id="4d586-121">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4d586-122">Licenze per i prodotti</span><span class="sxs-lookup"><span data-stu-id="4d586-122">Product licenses</span></span>  <br/> |<span data-ttu-id="4d586-123">È possibile rimuovere la licenza dall'utente e rimuoverla dagli abbonamenti per interrompere il pagamento per la licenza.</span><span class="sxs-lookup"><span data-stu-id="4d586-123">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="4d586-124">Se si seleziona questa opzione, la licenza verrà rimossa automaticamente dagli abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="4d586-124">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="4d586-125">**Non è possibile rimuovere la licenza** se è stata acquistata tramite un partner o un contratto multilicenza.</span><span class="sxs-lookup"><span data-stu-id="4d586-125">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="4d586-126">Se si paga un piano annuale o si è nel mezzo di un ciclo di fatturazione, non sarà possibile rimuovere la licenza dall'abbonamento fino a quando non viene completato l'impegno.</span><span class="sxs-lookup"><span data-stu-id="4d586-126">If you are paying for an annual plan or if you are in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="4d586-127">Contenuto di OneDrive</span><span class="sxs-lookup"><span data-stu-id="4d586-127">OneDrive content</span></span>  <br/> |<span data-ttu-id="4d586-128">Se l'utente ha salvato i propri file in OneDrive, è possibile concedere a un altro utente l'accesso a questi file.</span><span class="sxs-lookup"><span data-stu-id="4d586-128">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="4d586-129">Sarà necessario spostare i file che si desidera conservare entro il periodo di conservazione impostato per i file di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4d586-129">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="4d586-130">**Per impostazione predefinita, il periodo di conservazione è di 30 giorni.**</span><span class="sxs-lookup"><span data-stu-id="4d586-130">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="4d586-131">Se non si spostano i file entro il periodo di conservazione dopo l'eliminazione dell'utente, il contenuto di OneDrive verrà eliminato definitivamente.</span><span class="sxs-lookup"><span data-stu-id="4d586-131">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="4d586-132">Per aumentare il numero di giorni di conservazione dei file di OneDrive per gli account eliminati, vedere [set the OneDrive retention for deleted Users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).</span><span class="sxs-lookup"><span data-stu-id="4d586-132">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).</span></span>  <br/><br/> <span data-ttu-id="4d586-133">**Importante!**</span><span class="sxs-lookup"><span data-stu-id="4d586-133">**Important!**</span></span> <span data-ttu-id="4d586-134">Se l'utente eliminato ha utilizzato un computer personale per scaricare i file da SharePoint e OneDrive, non è possibile cancellare i file archiviati nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="4d586-134">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="4d586-135">Continueranno ad avere accesso a tutti i file che sono stati sincronizzati da OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4d586-135">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="4d586-136">Posta elettronica</span><span class="sxs-lookup"><span data-stu-id="4d586-136">Email</span></span>  <br/> | <span data-ttu-id="4d586-137">Se si concede a un altro utente l'accesso alla posta elettronica dell'utente eliminato, la cassetta postale dell'utente eliminato verrà convertita in una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="4d586-137">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="4d586-138">Il nuovo proprietario della cassetta postale può quindi accedere alla cassetta postale e monitorare il nuovo messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4d586-138">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="4d586-139">Sono inoltre disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d586-139">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="4d586-140">Modificare il nome visualizzato: si consiglia di modificare il nome visualizzato in modo che sia possibile identificare facilmente la cassetta postale condivisa nell'elenco utenti attivi.</span><span class="sxs-lookup"><span data-stu-id="4d586-140">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the Active users list.</span></span>  <br/>  <span data-ttu-id="4d586-141">Attiva risposte automatiche-abbiamo già scritto una cortese risposta automatica per te.</span><span class="sxs-lookup"><span data-stu-id="4d586-141">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="4d586-142">È possibile inviare una risposta automatica diversa alle persone all'interno dell'organizzazione e persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d586-142">You can send a different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="4d586-143">Pulizia degli alias-gli alias sono indirizzi di posta elettronica aggiuntivi per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4d586-143">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="4d586-144">Alcune organizzazioni non le utilizzano, quindi se non si dispone di alcuna operazione non è necessario eseguire altre operazione.</span><span class="sxs-lookup"><span data-stu-id="4d586-144">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="4d586-145">Se l'utente dispone di alias, è consigliabile rimuoverli in modo che sia possibile riutilizzare tali indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4d586-145">If the user does have aliases, we recommend removing them so that you can re-use those email addresses.</span></span> <span data-ttu-id="4d586-146">In caso contrario, non è possibile riutilizzare tali indirizzi di posta elettronica fino al termine del periodo di conservazione per le cassette postali eliminate.</span><span class="sxs-lookup"><span data-stu-id="4d586-146">Otherwise, you can’t re-use those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="4d586-147">Per impostazione predefinita, una cassetta postale eliminata è ripristinabile per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="4d586-147">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="4d586-148">Per ulteriori informazioni, vedere [eliminare o ripristinare le cassette postali degli utenti in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span><span class="sxs-lookup"><span data-stu-id="4d586-148">For more information, see  [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="4d586-149">Active Directory</span><span class="sxs-lookup"><span data-stu-id="4d586-149">Active Directory</span></span>  <br/> |<span data-ttu-id="4d586-150">Se l'organizzazione usa **Active Directory** che si sincronizza con Azure AD, è necessario eliminare l'account utente da Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4d586-150">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="4d586-151">Non è possibile farlo da Office 365.</span><span class="sxs-lookup"><span data-stu-id="4d586-151">You can't do it through Office 365.</span></span> <span data-ttu-id="4d586-152">Per istruzioni, vedere [eliminare un account utente](https://go.microsoft.com/fwlink/p/?linkid=841808).</span><span class="sxs-lookup"><span data-stu-id="4d586-152">For instructions, see [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808).</span></span>  <br/> |
   
### <a name="get-started"></a><span data-ttu-id="4d586-153">Per iniziare</span><span class="sxs-lookup"><span data-stu-id="4d586-153">Get started</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="4d586-154">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="4d586-154">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="4d586-155">Poiché l'esperienza guidata illustra i passaggi necessari per eliminare un utente, ecco come iniziare.</span><span class="sxs-lookup"><span data-stu-id="4d586-155">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4d586-156">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="4d586-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4d586-157">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="4d586-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4d586-158">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="4d586-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="4d586-159">Selezionare l'utente che si desidera eliminare, quindi selezionare **Elimina utente**.</span><span class="sxs-lookup"><span data-stu-id="4d586-159">Select the user you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="4d586-160">Amministratore Gestione utenti: eliminare uno o più utenti da Office 365</span><span class="sxs-lookup"><span data-stu-id="4d586-160">User management admin: Delete one or more users from Office 365</span></span>


 <span data-ttu-id="4d586-p113">**IMPORTANTE**: Non eliminare l'account di un utente se è stato [convertito in una cassetta postale condivisa](../email/convert-user-mailbox-to-shared-mailbox.md) o se è stato configurato l'inoltro della posta elettronica. Per queste funzioni è necessario mantenere l'account. Se è stato convertito in una cassetta postale condivisa, è possibile [Interrompere il pagamento per la licenza](#stop-paying-for-the-license) dall'account in modo da interrompere il pagamento. Se si imposta l'inoltro della posta elettronica, non è possibile rimuovere la licenza. La rimozione, infatti, interrompe l'inoltro della posta elettronica e disattiva la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="4d586-p113">**IMPORTANT**: Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account. Those functions need the account there. If you've converted it to a shared mailbox, you can [Stop paying for the license](#stop-paying-for-the-license) from it so you aren't paying for it. If you set up email forwarding, you cannot remove the license. Doing so will stop the email forwarding and inactivate the mailbox.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="4d586-166">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="4d586-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="4d586-167">Selezionare i nomi degli utenti che si desidera eliminare, selezionare **altre opzioni** (..**.**) e quindi scegliere **Elimina utente**.</span><span class="sxs-lookup"><span data-stu-id="4d586-167">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="4d586-168">Anche se è stato eliminato l'account dell'utente, **si sta ancora pagando la licenza**.</span><span class="sxs-lookup"><span data-stu-id="4d586-168">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="4d586-169">Vedere la procedura successiva per interrompere il pagamento per la licenza.</span><span class="sxs-lookup"><span data-stu-id="4d586-169">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="4d586-170">In alternativa, è possibile assegnare la licenza a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="4d586-170">Or, you can assign the license to another user.</span></span> <span data-ttu-id="4d586-171">Non verrà assegnato automaticamente a un utente.</span><span class="sxs-lookup"><span data-stu-id="4d586-171">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4d586-172">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="4d586-172">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="4d586-173">Selezionare i nomi degli utenti che si desidera eliminare e, nel riquadro azioni in **blocco** , scegliere **Elimina utenti**.</span><span class="sxs-lookup"><span data-stu-id="4d586-173">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="4d586-174">Anche se è stato eliminato l'account dell'utente, **si sta ancora pagando la licenza**.</span><span class="sxs-lookup"><span data-stu-id="4d586-174">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="4d586-175">Vedere la procedura successiva per interrompere il pagamento per la licenza.</span><span class="sxs-lookup"><span data-stu-id="4d586-175">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="4d586-176">In alternativa, è possibile assegnare la licenza a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="4d586-176">Or, you can assign the license to another user.</span></span> <span data-ttu-id="4d586-177">Non verrà assegnato automaticamente a un utente.</span><span class="sxs-lookup"><span data-stu-id="4d586-177">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4d586-178">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="4d586-178">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="4d586-179">Selezionare i nomi degli utenti che si desidera eliminare e, nel riquadro azioni in **blocco** , scegliere **Elimina utenti**.</span><span class="sxs-lookup"><span data-stu-id="4d586-179">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="4d586-180">Anche se è stato eliminato l'account dell'utente, **si sta ancora pagando la licenza**.</span><span class="sxs-lookup"><span data-stu-id="4d586-180">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="4d586-181">Vedere la procedura successiva per interrompere il pagamento per la licenza.</span><span class="sxs-lookup"><span data-stu-id="4d586-181">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="4d586-182">In alternativa, è possibile assegnare la licenza a un altro utente.</span><span class="sxs-lookup"><span data-stu-id="4d586-182">Or, you can assign the license to another user.</span></span> <span data-ttu-id="4d586-183">Non verrà assegnato automaticamente a un utente.</span><span class="sxs-lookup"><span data-stu-id="4d586-183">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="4d586-184">Interrompere il pagamento per la licenza</span><span class="sxs-lookup"><span data-stu-id="4d586-184">Stop paying for the license</span></span>

<span data-ttu-id="4d586-185">La riduzione del numero di licenze è un passaggio separato che può essere eseguito solo dall'amministratore globale o dall'amministratore della fatturazione.</span><span class="sxs-lookup"><span data-stu-id="4d586-185">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="4d586-186">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Prodotti e servizi</a>.</span><span class="sxs-lookup"><span data-stu-id="4d586-186">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span> <span data-ttu-id="4d586-187">Se non si vede questa opzione, non si è un amministratore globale o un amministratore di fatturazione e non è possibile eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="4d586-187">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="4d586-188">Selezionare l'abbonamento (se si dispone di più di un utente) e quindi selezionare **Aggiungi/Rimuovi licenze** per eliminare la licenza in modo da non pagarla fino a quando non si assume un'altra persona.</span><span class="sxs-lookup"><span data-stu-id="4d586-188">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="4d586-189">Successivamente, quando si esegue la procedura per aggiungere un'altra persona all'azienda, viene richiesto di acquistare una licenza nello stesso momento, con un solo passaggio.</span><span class="sxs-lookup"><span data-stu-id="4d586-189">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4d586-190">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">abbonamenti</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="4d586-190">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="4d586-191">Se non si vede questa opzione, non si è un amministratore globale o un amministratore di fatturazione e non è possibile eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="4d586-191">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="4d586-192">Selezionare l'abbonamento (se si dispone di più di un utente) e quindi selezionare **Aggiungi/Rimuovi licenze** per eliminare la licenza in modo da non pagarla fino a quando non si assume un'altra persona.</span><span class="sxs-lookup"><span data-stu-id="4d586-192">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="4d586-193">Successivamente, quando si esegue la procedura per aggiungere un'altra persona all'azienda, viene richiesto di acquistare una licenza nello stesso momento, con un solo passaggio.</span><span class="sxs-lookup"><span data-stu-id="4d586-193">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4d586-194">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">abbonamenti</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="4d586-194">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="4d586-195">Se non si vede questa opzione, non si è un amministratore globale o un amministratore di fatturazione e non è possibile eseguire questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="4d586-195">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="4d586-196">Selezionare l'abbonamento (se si dispone di più di un utente) e quindi selezionare **Aggiungi/Rimuovi licenze** per eliminare la licenza in modo da non pagarla fino a quando non si assume un'altra persona.</span><span class="sxs-lookup"><span data-stu-id="4d586-196">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="4d586-197">Successivamente, quando si esegue la procedura per aggiungere un'altra persona all'azienda, viene richiesto di acquistare una licenza nello stesso momento, con un solo passaggio.</span><span class="sxs-lookup"><span data-stu-id="4d586-197">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="4d586-198">Eliminare contemporaneamente numerosi utenti</span><span class="sxs-lookup"><span data-stu-id="4d586-198">Delete many users at the same time</span></span>

<span data-ttu-id="4d586-199">Vedere il cmdlet [Remove-MsolUser di](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d586-199">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="4d586-200">Risolvere i problemi relativi all'eliminazione di un utente</span><span class="sxs-lookup"><span data-stu-id="4d586-200">Fix issues with deleting a user</span></span>

<span data-ttu-id="4d586-201">Di seguito sono rilevati i problemi più comuni che si verificano durante l'eliminazione di un utente:</span><span class="sxs-lookup"><span data-stu-id="4d586-201">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="4d586-202">**Viene visualizzato un messaggio di errore lungo le righe di "l'utente non può essere eliminato. Provare di nuovo in un secondo momento.**</span><span class="sxs-lookup"><span data-stu-id="4d586-202">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="4d586-203">Controllare se l'account è configurato per l'inoltro della posta elettronica o se è stato convertito in una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="4d586-203">Doublecheck whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="4d586-204">Entrambe queste cause causano tale errore.</span><span class="sxs-lookup"><span data-stu-id="4d586-204">Both of these will cause that error.</span></span> <span data-ttu-id="4d586-205">Non eliminare l'account se ha l'inoltro della posta elettronica o se è stato convertito in una cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="4d586-205">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="4d586-206">**Non si hanno le autorizzazioni appropriate per eliminare un utente**.</span><span class="sxs-lookup"><span data-stu-id="4d586-206">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="4d586-207">Solo gli amministratori [globali di Office 365 o gli amministratori di gestione utenti](about-admin-roles.md) possono eliminare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4d586-207">Only people who are [Office 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="4d586-208">Si tratta in genere del supporto tecnico dell'istituto di istruzione o dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="4d586-208">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="4d586-p122">**L'utente viene eliminato, ma il nome continua a comparire nella Rubrica globale**. Questo accade quando un'azienda usa Active Directory. È necessario eliminare l'account utente da Active Directory. Per istruzioni, vedere l'articolo di TechNet: [Eliminare un account utente.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span><span class="sxs-lookup"><span data-stu-id="4d586-p122">**You delete the user but their name continues appear in your global address book**. This happens when a business is using Active Directory. You have to delete the users account from Active Directory. For instructions, see this TechNet article: [Delete a User Account.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span></span>

||
|:-----|
|<span data-ttu-id="4d586-213">**Eliminare Office 365 dal computer? Passare a [Annullare l'abbonamento](../../commerce/subscriptions/cancel-your-subscription.md).**</span><span class="sxs-lookup"><span data-stu-id="4d586-213">**Do you want to delete Office 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="4d586-214">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="4d586-214">Related articles</span></span>

[<span data-ttu-id="4d586-215">Ripristinare un utente</span><span class="sxs-lookup"><span data-stu-id="4d586-215">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="4d586-216">Eliminare definitivamente una cassetta postale</span><span class="sxs-lookup"><span data-stu-id="4d586-216">Permanently delete a mailbox</span></span>](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[<span data-ttu-id="4d586-217">Rimuovere un ex dipendente da Office 365</span><span class="sxs-lookup"><span data-stu-id="4d586-217">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="4d586-218">Aggiungere un nuovo dipendente a Office 365</span><span class="sxs-lookup"><span data-stu-id="4d586-218">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="4d586-219">[Eliminare un account utente](https://go.microsoft.com/fwlink/p/?linkid=841808): utilizzare queste istruzioni se la propria azienda utilizza **Active Directory** che esegue la sincronizzazione con Azure ad.</span><span class="sxs-lookup"><span data-stu-id="4d586-219">[Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="4d586-220">Non è possibile farlo da Office 365.</span><span class="sxs-lookup"><span data-stu-id="4d586-220">You can't do it through Office 365.</span></span>
