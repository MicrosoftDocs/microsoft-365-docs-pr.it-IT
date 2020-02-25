---
title: Aggiungere gli utenti singolarmente o in blocco a Office 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: Informazioni su come aggiungere utenti a Office 365, uno alla volta o più utenti contemporaneamente da un file CSV.
ms.openlocfilehash: 708bce2cb5a2c1b6a621bffc3ce56a2744bb518d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241687"
---
# <a name="add-users-individually-or-in-bulk-to-office-365"></a><span data-ttu-id="4fb84-103">Aggiungere gli utenti singolarmente o in blocco a Office 365</span><span class="sxs-lookup"><span data-stu-id="4fb84-103">Add users individually or in bulk to Office 365</span></span>

<span data-ttu-id="4fb84-104">Per poter accedere a [Office 365 per le aziende](https://go.microsoft.com/fwlink/?LinkID=519395), è necessario che ogni persona del team abbia un account utente.</span><span class="sxs-lookup"><span data-stu-id="4fb84-104">The people on your team each need a user account before they can sign in and access [Office 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="4fb84-105">Il modo più semplice per aggiungere account utente consiste nell'aggiungerli uno alla volta nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fb84-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4fb84-106">Dopo aver eseguito questo passaggio, gli utenti avranno licenze di Office 365, credenziali di accesso e cassette postali di Office 365.</span><span class="sxs-lookup"><span data-stu-id="4fb84-106">After you do this step, your users will have Office 365 licenses, sign in credentials, and Office 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="4fb84-107">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="4fb84-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="4fb84-108">Passare all’interfaccia di amministrazione su <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="4fb84-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="4fb84-109">Passare a \*\*\*\* > utenti **attivi**e selezionare **Aggiungi un utente**.</span><span class="sxs-lookup"><span data-stu-id="4fb84-109">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="4fb84-110">Nel riquadro **Configura le nozioni di base** , immettere le informazioni seguenti e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="4fb84-110">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="4fb84-111">**Nome** Compilare primo, ultimo, nome visualizzato e nome utente.</span><span class="sxs-lookup"><span data-stu-id="4fb84-111">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="4fb84-112">**Dominio** Se ad esempio il nome utente è Pio e il suo dominio è contoso.com, questo utente eseguirà l'accesso a Office 365 digitando pio@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4fb84-112">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="4fb84-113">**Impostazioni della password** Scegliere di utilizzare la password generata automaticamente o creare una password complessa per l'utente.</span><span class="sxs-lookup"><span data-stu-id="4fb84-113">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="4fb84-114">L'utente dovrà cambiare la password dopo 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="4fb84-114">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="4fb84-115">In alternativa, è possibile **richiedere all'utente di modificare la propria password al primo accesso**.</span><span class="sxs-lookup"><span data-stu-id="4fb84-115">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="4fb84-116">Scegliere se si desidera inviare la password tramite posta elettronica quando l'utente è stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="4fb84-116">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="4fb84-117">Nel riquadro **assegna licenze di prodotto** selezionare il percorso e la licenza appropriata per l'utente.</span><span class="sxs-lookup"><span data-stu-id="4fb84-117">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="4fb84-118">Se non ci sono licenze disponibili, è sempre possibile aggiungere un utente e acquistare licenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4fb84-118">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="4fb84-119"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="4fb84-119">Select **Next**.</span></span>

5. <span data-ttu-id="4fb84-120">Nella pagina **impostazioni facoltative** espandere **ruoli** se si desidera che l'utente sia un amministratore e quindi espandere informazioni sul **profilo** se si desidera aggiungere ulteriori informazioni sull'utente.</span><span class="sxs-lookup"><span data-stu-id="4fb84-120">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="4fb84-121">Selezionare **Avanti**, esaminare le impostazioni del nuovo utente, apportare le modifiche desiderate e quindi selezionare **termina aggiunta**.</span><span class="sxs-lookup"><span data-stu-id="4fb84-121">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="4fb84-122">Passare all’interfaccia di amministrazione su <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="4fb84-122">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="4fb84-123">Passare a \*\*\*\* > utenti **attivi**e selezionare **Aggiungi un utente**.</span><span class="sxs-lookup"><span data-stu-id="4fb84-123">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="4fb84-124">Nel riquadro **nuovo utente** , immettere le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4fb84-124">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="4fb84-125">Selezionare **Aggiungi** al termine.</span><span class="sxs-lookup"><span data-stu-id="4fb84-125">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="4fb84-126">**Nome** Inserire il nome, il cognome, il nome visualizzato e il nome utente.</span><span class="sxs-lookup"><span data-stu-id="4fb84-126">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="4fb84-127">**Dominio** Se ad esempio il nome utente è Pio e il suo dominio è contoso.com, questo utente eseguirà l'accesso a Office 365 digitando pio@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4fb84-127">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="4fb84-128">**Informazioni di contatto** Espandere per inserire il numero di telefono cellulare, l'indirizzo e così via.</span><span class="sxs-lookup"><span data-stu-id="4fb84-128">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="4fb84-129">**Password** Usare la password generata automaticamente o espandere per specificare una password complessa per l'utente.</span><span class="sxs-lookup"><span data-stu-id="4fb84-129">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="4fb84-p105">L'utente dovrà cambiare la password dopo 90 giorni. Oppure si può selezionare **Chiedi all'utente di cambiare la password al primo accesso**.</span><span class="sxs-lookup"><span data-stu-id="4fb84-p105">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="4fb84-132">**Ruoli** Espandere se si vuole impostare l'utente come amministratore.</span><span class="sxs-lookup"><span data-stu-id="4fb84-132">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="4fb84-p106">**Licenze di prodotto** Espandere questa sezione e selezionare la licenza appropriata. Se non ci sono licenze disponibili, è sempre possibile aggiungere un utente e acquistare licenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4fb84-p106">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4fb84-135">Passare all’interfaccia di amministrazione su <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="4fb84-135">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="4fb84-136">Passare a \*\*\*\* > utenti **attivi**e selezionare **Aggiungi un utente**.</span><span class="sxs-lookup"><span data-stu-id="4fb84-136">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="4fb84-137">Nel riquadro **nuovo utente** , immettere le informazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="4fb84-137">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="4fb84-138">Selezionare **Aggiungi** al termine.</span><span class="sxs-lookup"><span data-stu-id="4fb84-138">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="4fb84-139">**Nome** Inserire il nome, il cognome, il nome visualizzato e il nome utente.</span><span class="sxs-lookup"><span data-stu-id="4fb84-139">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="4fb84-140">**Dominio** Se ad esempio il nome utente è Pio e il suo dominio è contoso.com, questo utente eseguirà l'accesso a Office 365 digitando pio@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4fb84-140">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="4fb84-141">**Informazioni di contatto** Espandere per inserire il numero di telefono cellulare, l'indirizzo e così via.</span><span class="sxs-lookup"><span data-stu-id="4fb84-141">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="4fb84-142">**Password** Usare la password generata automaticamente o espandere per specificare una password complessa per l'utente.</span><span class="sxs-lookup"><span data-stu-id="4fb84-142">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="4fb84-p108">L'utente dovrà cambiare la password dopo 90 giorni. Oppure si può selezionare **Chiedi all'utente di cambiare la password al primo accesso**.</span><span class="sxs-lookup"><span data-stu-id="4fb84-p108">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="4fb84-145">**Ruoli** Espandere se si vuole impostare l'utente come amministratore.</span><span class="sxs-lookup"><span data-stu-id="4fb84-145">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="4fb84-p109">**Licenze di prodotto** Espandere questa sezione e selezionare la licenza appropriata. Se non ci sono licenze disponibili, è sempre possibile aggiungere un utente e acquistare licenze aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4fb84-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="4fb84-148">Dopo aver aggiunto un utente, si otterrà una notifica tramite posta elettronica dal team dei Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="4fb84-148">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="4fb84-149">Il messaggio di posta elettronica conterrà l'ID utente e la password di Office 365 in modo che possano accedere a Office 365.</span><span class="sxs-lookup"><span data-stu-id="4fb84-149">The email will contain the person's Office 365 user ID and password so they can sign in to Office 365.</span></span> <span data-ttu-id="4fb84-150">È necessario informare il nuovo utente sulle proprie informazioni di accesso a Office 365.</span><span class="sxs-lookup"><span data-stu-id="4fb84-150">You need to tell your new user about their Office 365 sign in information.</span></span> <span data-ttu-id="4fb84-151">Usare il consueto processo per la comunicazione di nuove password.</span><span class="sxs-lookup"><span data-stu-id="4fb84-151">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="4fb84-152">Se si creano utenti eseguendo la migrazione di cassette postali, sarà necessario attivare gli account utente di Office 365 assegnando le licenze.</span><span class="sxs-lookup"><span data-stu-id="4fb84-152">If you create users by migrating mail boxes, you will need to activate Office 365 user accounts by assigning licenses.</span></span> <span data-ttu-id="4fb84-153">Se non si assegna una licenza a un utente, la propria cassetta postale verrà disabilitata dopo un periodo di prova di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="4fb84-153">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="4fb84-154">Vedere come [assegnare le licenze agli utenti](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) utilizzando l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4fb84-154">See how to [assign licenses to users](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="4fb84-155">Video: aggiungere e gestire gli utenti nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="4fb84-155">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="4fb84-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4fb84-156">Next steps</span></span>

<span data-ttu-id="4fb84-157">Condividere la [guida introduttiva per i dipendenti](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) con i nuovi utenti per facilitare la configurazione dei vari elementi, come [Office in un PC o un Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) e le [app per dispositivi mobili di Office](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span><span class="sxs-lookup"><span data-stu-id="4fb84-157">Share the [Employee quick start guide](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) with your new users to set things up, like [Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) and [Office mobile apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="4fb84-158">Serve assistenza?</span><span class="sxs-lookup"><span data-stu-id="4fb84-158">Need help?</span></span>

<span data-ttu-id="4fb84-159">[Contattare il supporto di Office 365 for business](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="4fb84-159">[Contact Office 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="4fb84-160">Se è necessario aggiungere centinaia o migliaia di utenti contemporaneamente,</span><span class="sxs-lookup"><span data-stu-id="4fb84-160">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="4fb84-161">vedere le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4fb84-161">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="4fb84-162">**Usare un foglio di calcolo per aggiungere persone in blocco.**</span><span class="sxs-lookup"><span data-stu-id="4fb84-162">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="4fb84-163">Per ulteriori informazioni, vedere [aggiungere più utenti contemporaneamente](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span><span class="sxs-lookup"><span data-stu-id="4fb84-163">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="4fb84-164">**Automatizzare il processo di aggiunta di account e assegnazione delle licenze.**</span><span class="sxs-lookup"><span data-stu-id="4fb84-164">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="4fb84-165">Vedere [creare account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="4fb84-165">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="4fb84-166">Questo metodo è adeguato se si ha già familiarità con i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4fb84-166">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="4fb84-167">**Utilizzo di ActiveDirectory**</span><span class="sxs-lookup"><span data-stu-id="4fb84-167">**Using ActiveDirectory?**</span></span> <span data-ttu-id="4fb84-168">[Configurare la sincronizzazione della directory per Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="4fb84-168">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="4fb84-169">Usare Azure AD Connect per replicare gli account utente di Active Directory (e altri oggetti Active Directory) in Office 365.</span><span class="sxs-lookup"><span data-stu-id="4fb84-169">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="4fb84-170">Con la sincronizzazione vengono aggiunti solo gli account utente.</span><span class="sxs-lookup"><span data-stu-id="4fb84-170">The sync only adds the user accounts.</span></span> <span data-ttu-id="4fb84-171">Sarà necessario assegnare le licenze agli utenti sincronizzati perché possano usare la posta elettronica e altre app di Office.</span><span class="sxs-lookup"><span data-stu-id="4fb84-171">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="4fb84-172">**Migrazione da Exchange**</span><span class="sxs-lookup"><span data-stu-id="4fb84-172">**Migrating from Exchange?**</span></span> <span data-ttu-id="4fb84-173">[Modalità di migrazione di più account di posta elettronica a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="4fb84-173">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="4fb84-174">Quando si esegue la migrazione di più cassette postali a Office 365 usando il metodo di migrazione completa, a fasi o ibrida di Exchange, gli utenti vengono aggiunti automaticamente nell'ambito della migrazione.</span><span class="sxs-lookup"><span data-stu-id="4fb84-174">When you migrate multiple mailboxes to Office 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="4fb84-175">Con la migrazione vengono aggiunti solo gli account utente.</span><span class="sxs-lookup"><span data-stu-id="4fb84-175">The migration only adds the user accounts.</span></span> <span data-ttu-id="4fb84-176">Sarà necessario assegnare le licenze agli utenti perché possano usare la posta elettronica e altre app di Office.</span><span class="sxs-lookup"><span data-stu-id="4fb84-176">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4fb84-177">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="4fb84-177">Related articles</span></span>

[<span data-ttu-id="4fb84-178">Aggiungere un nuovo dipendente a Office 365</span><span class="sxs-lookup"><span data-stu-id="4fb84-178">Add a new employee to Office 365</span></span>](add-new-employee.md)

[<span data-ttu-id="4fb84-179">Eliminare un utente dall'organizzazione</span><span class="sxs-lookup"><span data-stu-id="4fb84-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="4fb84-180">Ripristinare un utente in Office 365</span><span class="sxs-lookup"><span data-stu-id="4fb84-180">Restore a user in Office 365</span></span>](restore-user.md)

[<span data-ttu-id="4fb84-181">Aggiungere più utenti contemporaneamente a Office 365</span><span class="sxs-lookup"><span data-stu-id="4fb84-181">Add several users at the same time to Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)


