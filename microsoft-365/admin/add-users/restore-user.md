---
title: Ripristinare un utente
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Entro 30 giorni dall'eliminazione di un account utente, è possibile ripristinare l'account e tutti i dati e l'utente può accedere con lo stesso account.
ms.openlocfilehash: e37f913bcc6a54bdcc1e0f52168fe1aab0c8afdd
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394268"
---
# <a name="restore-a-user"></a><span data-ttu-id="8c6aa-103">Ripristinare un utente</span><span class="sxs-lookup"><span data-stu-id="8c6aa-103">Restore a user</span></span>
   
<span data-ttu-id="8c6aa-p101">Se si ripristina un account utente entro 30 giorni dalla sua eliminazione, vengono ripristinati l'account stesso e tutti i dati associati. L'utente può accedere con lo stesso account aziendale o dell'istituto di istruzione. La cassetta postale dell'utente verrà completamente ripristinata. Per scoprire quanto tempo rimane prima che non sia più possibile ripristinare un account utente specifico, [contattare il supporto tecnico](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="8c6aa-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../../business-video/get-help-support.md).</span></span>
  
<span data-ttu-id="8c6aa-108">Ecco un paio di suggerimenti:</span><span class="sxs-lookup"><span data-stu-id="8c6aa-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="8c6aa-109">Assicurati che le licenze siano disponibili per l'assegnazione all'account.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-109">Make sure licenses are available to assign to the account.</span></span>
    
- <span data-ttu-id="8c6aa-110">Se l'azienda utilizza Active Directory, per le instrusioni sul ripristino di un account utente, vedere Come risolvere i problemi relativi agli account utente eliminati [in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="8c6aa-110">If your business uses Active Directory, for instrutcions on restoring a user account, see [How to troubleshoot deleted user accounts in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts).</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="8c6aa-111">Ripristinare uno o più account utente</span><span class="sxs-lookup"><span data-stu-id="8c6aa-111">Restore one or more user accounts</span></span>

<span data-ttu-id="8c6aa-112">Per eseguire questa procedura, Microsoft 365 amministratore globale o amministratore di gestione utenti.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-112">You must be a Microsoft 365 global admin or user management admin to do these steps.</span></span> 

1. <span data-ttu-id="8c6aa-113">Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">utenti eliminati.</a></span><span class="sxs-lookup"><span data-stu-id="8c6aa-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="8c6aa-114">Nella pagina **Utenti eliminati** selezionare i nomi degli utenti che si desidera ripristinare e quindi selezionare **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-114">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
3. <span data-ttu-id="8c6aa-115">Seguire le istruzioni visualizzate per impostare la password e quindi selezionare **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-115">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="8c6aa-116">Se l'utente viene ripristinato correttamente, selezionare **Invia messaggio di posta elettronica e chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-116">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="8c6aa-117">Se si riscontra un conflitto tra nomi o indirizzi proxy, vedere le istruzioni di seguito per ripristinare questi account.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-117">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="8c6aa-118">Dopo aver ripristinato un utente, assicurati di avvisarlo che la password è cambiata e di seguirli.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-118">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="8c6aa-119">Ripristinare un utente con conflitto relativo al nome utente</span><span class="sxs-lookup"><span data-stu-id="8c6aa-119">Restore a user that has a user name conflict</span></span>

<span data-ttu-id="8c6aa-120">I conflitti relativi al nome utente si verificano quando l'amministratore elimina un account utente, ne crea uno nuovo con lo stesso nome utente (per lo stesso utente o per un altro utente con nome simile) e successivamente cerca di ripristinare l'account eliminato.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-120">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="8c6aa-p103">Per risolvere i conflitti di questo tipo, sostituire l'account utente attivo con quello da ripristinare oppure assegnare un altro nome utente a quest'ultimo account, in modo da evitare che esistano due account con lo stesso nome utente. Ecco come fare.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>

1. <span data-ttu-id="8c6aa-124">Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">utenti eliminati.</a></span><span class="sxs-lookup"><span data-stu-id="8c6aa-124">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>
  
2. <span data-ttu-id="8c6aa-125">Nella pagina **Utenti eliminati** selezionare i nomi degli utenti che si desidera ripristinare e quindi selezionare **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-125">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8c6aa-p104">Se non si riesce a ripristinare due o più utenti, verrà visualizzato un messaggio di errore che comunica che l'operazione di ripristino non è riuscita per alcuni utenti. Per sapere quali utenti non sono stati ripristinati, visualizzare il log. Gli account che non è stato possibile ripristinare dovranno essere ripristinati uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="8c6aa-128">Seguire le istruzioni visualizzate per impostare la password e selezionare **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-128">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="8c6aa-p105">Un messaggio popup informa che si è verificato un problema durante il ripristino dell'account. Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c6aa-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="8c6aa-p106">Annullare il ripristino e rinominare l'utente attivo corrente. Provare quindi a eseguire di nuovo il ripristino.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="8c6aa-133">OPPURE, digitare un nuovo indirizzo di posta elettronica principale per l'utente e selezionare **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-133">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="8c6aa-134">Esaminare i risultati e quindi scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-134">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="8c6aa-135">Ripristinare un utente che ha un conflitto tra indirizzi proxy</span><span class="sxs-lookup"><span data-stu-id="8c6aa-135">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="8c6aa-p107">I conflitti relativi all'indirizzo proxy si verificano quando l'amministratore elimina un account utente contenente un indirizzo proxy, assegna lo stesso indirizzo proxy a un altro account, quindi cerca di ripristinare l'account eliminato. Eseguire la procedura seguente per risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="8c6aa-138">A tale [scopo,](about-admin-roles.md) è necessario disporre Microsoft 365 autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-138">You must have [admin permissions](about-admin-roles.md) in Microsoft 365 to do this.</span></span> 

1. <span data-ttu-id="8c6aa-139">Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">utenti eliminati.</a></span><span class="sxs-lookup"><span data-stu-id="8c6aa-139">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

2. <span data-ttu-id="8c6aa-140">Nella pagina **Utenti eliminati** selezionare l'utente da ripristinare e quindi scegliere **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-140">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="8c6aa-141">Nella pagina **Ripristina** seguire le istruzioni per impostare la password e selezionare **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-141">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="8c6aa-142">Gli eventuali indirizzi proxy in conflitto vengono rimossi automaticamente dall'utente che si sta ripristinando.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-142">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="8c6aa-143">Esaminare i risultati e quindi scegliere **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8c6aa-143">Review the results, and then select **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="8c6aa-144">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="8c6aa-144">Related content</span></span>

<span data-ttu-id="8c6aa-145">[Eliminare un utente](delete-a-user.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="8c6aa-145">[Delete a user](delete-a-user.md) (article)</span></span>\
<span data-ttu-id="8c6aa-146">[Assegnare ruoli di amministratore](assign-admin-roles.md) (video)</span><span class="sxs-lookup"><span data-stu-id="8c6aa-146">[Assign admin roles](assign-admin-roles.md) (video)</span></span>\
<span data-ttu-id="8c6aa-147">[Assegnare licenze agli utenti](../manage/assign-licenses-to-users.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="8c6aa-147">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>
