---
title: Ripristinare un utente in Office 365
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
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Informazioni su come ripristinare gli account utente di Office 365 eliminati e tutti i dati associati.
ms.openlocfilehash: 385f7938f5e0ce1f3a580d40830124f77454f64d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241573"
---
# <a name="restore-a-user-in-office-365"></a><span data-ttu-id="846c5-103">Ripristinare un utente in Office 365</span><span class="sxs-lookup"><span data-stu-id="846c5-103">Restore a user in Office 365</span></span>
   
<span data-ttu-id="846c5-p101">Se si ripristina un account utente entro 30 giorni dalla sua eliminazione, vengono ripristinati l'account stesso e tutti i dati associati. L'utente può accedere con lo stesso account aziendale o dell'istituto di istruzione. La cassetta postale dell'utente verrà completamente ripristinata. Per scoprire quanto tempo rimane prima che non sia più possibile ripristinare un account utente specifico, [contattare il supporto tecnico](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="846c5-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../contact-support-for-business-products.md).</span></span>
  
<span data-ttu-id="846c5-108">Ecco un paio di suggerimenti:</span><span class="sxs-lookup"><span data-stu-id="846c5-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="846c5-109">Assicurarsi che siano disponibili licenze di Office 365 da assegnare all'account.</span><span class="sxs-lookup"><span data-stu-id="846c5-109">Make sure there are Office 365 licenses available that you can assign to the account.</span></span>
    
- <span data-ttu-id="846c5-110">Se l'azienda usa Active Directory, vedere [Risoluzione dei problemi relativi agli account utente eliminati in Office 365](https://support.microsoft.com/kb/2619308) per istruzioni sul ripristino di un account utente.</span><span class="sxs-lookup"><span data-stu-id="846c5-110">If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](https://support.microsoft.com/kb/2619308) for instructions on restoring a user account.</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="846c5-111">Ripristinare uno o più account utente</span><span class="sxs-lookup"><span data-stu-id="846c5-111">Restore one or more user accounts</span></span>

<span data-ttu-id="846c5-112">Per eseguire questa procedura è necessario essere un amministratore globale o un amministratore di gestione utenti in Office 365.</span><span class="sxs-lookup"><span data-stu-id="846c5-112">You must be a global admin or user management admin in Office 365 to do these steps.</span></span> 
  
 
::: moniker range="o365-worldwide"

1. <span data-ttu-id="846c5-113">Nell'interfaccia di amministrazione passare alla \*\*\*\* \> pagina utenti <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminati</a> utenti.</span><span class="sxs-lookup"><span data-stu-id="846c5-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="846c5-114">Passare all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=848041), quindi selezionare **utenti** \> **eliminati**.</span><span class="sxs-lookup"><span data-stu-id="846c5-114">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="846c5-115">Passare all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=850627), quindi selezionare **utenti** \> **eliminati**.</span><span class="sxs-lookup"><span data-stu-id="846c5-115">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="846c5-116">Nella pagina **utenti eliminati** selezionare i nomi degli utenti che si desidera ripristinare e quindi fare clic su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="846c5-116">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
 
3. <span data-ttu-id="846c5-117">Seguire le istruzioni visualizzate per impostare la password, quindi selezionare **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="846c5-117">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="846c5-118">Se l'utente è stato ripristinato correttamente, selezionare **Invia messaggio di posta elettronica e Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="846c5-118">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="846c5-119">Se si riscontra un conflitto tra nomi o indirizzi proxy, vedere le istruzioni di seguito per ripristinare questi account.</span><span class="sxs-lookup"><span data-stu-id="846c5-119">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="846c5-120">Dopo aver ripristinato un utente, verificare di aver informato che la password è stata modificata e che è stato eseguito il follow-up.</span><span class="sxs-lookup"><span data-stu-id="846c5-120">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="846c5-121">Ripristinare un utente con conflitto relativo al nome utente</span><span class="sxs-lookup"><span data-stu-id="846c5-121">Restore a user that has a user name conflict</span></span>
<span data-ttu-id="846c5-122"><a name="RestoreUserNameConflict"> </a></span><span class="sxs-lookup"><span data-stu-id="846c5-122"><a name="RestoreUserNameConflict"> </a></span></span>

<span data-ttu-id="846c5-123">I conflitti relativi al nome utente si verificano quando l'amministratore elimina un account utente, ne crea uno nuovo con lo stesso nome utente (per lo stesso utente o per un altro utente con nome simile) e successivamente cerca di ripristinare l'account eliminato.</span><span class="sxs-lookup"><span data-stu-id="846c5-123">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="846c5-p103">Per risolvere i conflitti di questo tipo, sostituire l'account utente attivo con quello da ripristinare oppure assegnare un altro nome utente a quest'ultimo account, in modo da evitare che esistano due account con lo stesso nome utente. Ecco come fare.</span><span class="sxs-lookup"><span data-stu-id="846c5-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="846c5-127">Nell'interfaccia di amministrazione passare alla \*\*\*\* \> pagina utenti <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminati</a> utenti.</span><span class="sxs-lookup"><span data-stu-id="846c5-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="846c5-128">Passare all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=848041), quindi selezionare **utenti** \> **eliminati**.</span><span class="sxs-lookup"><span data-stu-id="846c5-128">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="846c5-129">Passare all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=850627), quindi selezionare **utenti** \> **eliminati**.</span><span class="sxs-lookup"><span data-stu-id="846c5-129">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

  
2. <span data-ttu-id="846c5-130">Nella pagina **utenti eliminati** selezionare i nomi degli utenti che si desidera ripristinare e quindi fare clic su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="846c5-130">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="846c5-p104">Se non si riesce a ripristinare due o più utenti, verrà visualizzato un messaggio di errore che comunica che l'operazione di ripristino non è riuscita per alcuni utenti. Per sapere quali utenti non sono stati ripristinati, visualizzare il log. Gli account che non è stato possibile ripristinare dovranno essere ripristinati uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="846c5-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="846c5-133">Seguire le istruzioni visualizzate per impostare la password e selezionare **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="846c5-133">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="846c5-p105">Un messaggio popup informa che si è verificato un problema durante il ripristino dell'account. Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="846c5-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="846c5-p106">Annullare il ripristino e rinominare l'utente attivo corrente. Provare quindi a eseguire di nuovo il ripristino.</span><span class="sxs-lookup"><span data-stu-id="846c5-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="846c5-138">In alternativa, digitare un nuovo indirizzo di posta elettronica principale per l'utente e selezionare **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="846c5-138">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="846c5-139">Esaminare i risultati e quindi scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="846c5-139">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="846c5-140">Ripristinare un utente che ha un conflitto tra indirizzi proxy</span><span class="sxs-lookup"><span data-stu-id="846c5-140">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="846c5-p107">I conflitti relativi all'indirizzo proxy si verificano quando l'amministratore elimina un account utente contenente un indirizzo proxy, assegna lo stesso indirizzo proxy a un altro account, quindi cerca di ripristinare l'account eliminato. Eseguire la procedura seguente per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="846c5-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="846c5-143">Per eseguire questa procedura, è necessario avere autorizzazioni di [amministratore](about-admin-roles.md) in Office 365.</span><span class="sxs-lookup"><span data-stu-id="846c5-143">You must have [admin permissions](about-admin-roles.md) in Office 365 to do this.</span></span> 
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="846c5-144">Nell'interfaccia di amministrazione passare alla \*\*\*\* \> pagina utenti <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">eliminati</a> utenti.</span><span class="sxs-lookup"><span data-stu-id="846c5-144">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="846c5-145">Passare all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=848041), quindi selezionare **utenti** \> **eliminati**.</span><span class="sxs-lookup"><span data-stu-id="846c5-145">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="846c5-146">Passare all'interfaccia di [Amministrazione](https://go.microsoft.com/fwlink/p/?linkid=850627), quindi selezionare **utenti** \> **eliminati**.</span><span class="sxs-lookup"><span data-stu-id="846c5-146">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="846c5-147">Nella pagina **Utenti eliminati** selezionare l'utente da ripristinare e quindi scegliere **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="846c5-147">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="846c5-148">Nella pagina **Ripristina** , seguire le istruzioni per impostare la password e selezionare **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="846c5-148">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="846c5-149">Gli eventuali indirizzi proxy in conflitto vengono rimossi automaticamente dall'utente che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="846c5-149">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="846c5-150">Esaminare i risultati e quindi scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="846c5-150">Review the results, and then select **Close**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="846c5-151">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="846c5-151">Related articles</span></span>

[<span data-ttu-id="846c5-152">Eliminare un utente</span><span class="sxs-lookup"><span data-stu-id="846c5-152">Delete a user</span></span>](delete-a-user.md)
  

