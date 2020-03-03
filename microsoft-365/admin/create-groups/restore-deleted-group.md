---
title: Ripristinare un gruppo di Office 365 eliminato
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: "Informazioni su come ripristinare un gruppo di Office 365 eliminato utilizzando l'interfaccia di amministrazione di Exchange. "
ms.openlocfilehash: c88f10df27e5f3a0af79c93c7d0e347c5646abc9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352437"
---
# <a name="restore-a-deleted-office-365-group"></a><span data-ttu-id="0c16d-103">Ripristinare un gruppo di Office 365 eliminato</span><span class="sxs-lookup"><span data-stu-id="0c16d-103">Restore a deleted Office 365 Group</span></span>

<span data-ttu-id="0c16d-104">Se si è il proprietario di un gruppo di Office 365, è possibile ripristinare il gruppo manualmente attenendosi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="0c16d-104">If you are the owner of an Office 365 group, you can restore the group yourself by following these steps.</span></span>

1. <span data-ttu-id="0c16d-105">Nella [pagina Gruppi eliminati](https://outlook.office.com/people/group/deleted)selezionare l'opzione **Gestisci gruppi** nel nodo **gruppi** e quindi scegliere **eliminata**.</span><span class="sxs-lookup"><span data-stu-id="0c16d-105">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>
2. <span data-ttu-id="0c16d-106">Fare clic sulla scheda **Ripristina** accanto al gruppo che si desidera ripristinare.</span><span class="sxs-lookup"><span data-stu-id="0c16d-106">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="0c16d-107">Se il gruppo eliminato non viene visualizzato, contattare un amministratore.</span><span class="sxs-lookup"><span data-stu-id="0c16d-107">If the deleted group doesn't appear here, contact an administrator.</span></span>
  
<span data-ttu-id="0c16d-108">Se sei un utente che vuole ripristinare un gruppo di Office 365, Chiedi a un amministratore di eseguire questi passaggi per te o contattare l'help desk.</span><span class="sxs-lookup"><span data-stu-id="0c16d-108">If you're a user who wants to restore an Office 365 group, ask an administrator to do these steps for you or contact your help desk.</span></span>  
   
<span data-ttu-id="0c16d-109">Se si è eliminato un gruppo, questo verrà mantenuto per 30 giorni per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0c16d-109">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="0c16d-110">Questo periodo di 30 giorni è considerato "soft-delete" perché è ancora possibile ripristinare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="0c16d-110">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="0c16d-111">Dopo 30 giorni, il gruppo e il relativo contenuto associato vengono eliminati definitivamente e non possono essere ripristinati.</span><span class="sxs-lookup"><span data-stu-id="0c16d-111">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>
  
<span data-ttu-id="0c16d-112">Durante il periodo di "eliminazione temporanea", se un utente tenta di accedere al sito riceverà un messaggio 404 _Forbidden_ .</span><span class="sxs-lookup"><span data-stu-id="0c16d-112">During the "soft-delete" period, if a user tries to access the site they will get a 404 _forbidden_ message.</span></span> <span data-ttu-id="0c16d-113">Dopo questo periodo, se un utente tenta di accedere al sito, riceverà un messaggio di 404 _non trovato_ .</span><span class="sxs-lookup"><span data-stu-id="0c16d-113">After this period, if a user tries to access the site, they will get a 404 _not found_ message.</span></span>
  
<span data-ttu-id="0c16d-114">Quando si ripristina un gruppo, vengono ripristinati anche i contenuti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0c16d-114">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="0c16d-115">Gli oggetti, le proprietà e i membri di Azure Active Directory (AD) Office 365 gruppi.</span><span class="sxs-lookup"><span data-stu-id="0c16d-115">Azure Active Directory (AD) Office 365 groups object, properties, and members.</span></span>
    
- <span data-ttu-id="0c16d-116">Indirizzi di posta elettronica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0c16d-116">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="0c16d-117">Posta in arrivo condivisa e calendario di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0c16d-117">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="0c16d-118">Sito e file del team di SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0c16d-118">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="0c16d-119">Blocco appunti di OneNote</span><span class="sxs-lookup"><span data-stu-id="0c16d-119">OneNote notebook</span></span>
    
- <span data-ttu-id="0c16d-120">Planner</span><span class="sxs-lookup"><span data-stu-id="0c16d-120">Planner</span></span>
    
- <span data-ttu-id="0c16d-121">Teams</span><span class="sxs-lookup"><span data-stu-id="0c16d-121">Teams</span></span>

- <span data-ttu-id="0c16d-122">Gruppo di Yammer e contenuto del gruppo (se il gruppo di Office 365 è stato creato da Yammer)</span><span class="sxs-lookup"><span data-stu-id="0c16d-122">Yammer group and group content (If the Office 365 group was created from Yammer)</span></span>
    
<span data-ttu-id="0c16d-123">Si può anche [Eliminare definitivamente un gruppo di Office 365](#permanently-delete-an-office-365-group) se non si può aspettare che scadano i 30 giorni del periodo di conservazione e che il contenuto venga quindi eliminato definitivamente.</span><span class="sxs-lookup"><span data-stu-id="0c16d-123">You can also [Permanently delete an Office 365 group](#permanently-delete-an-office-365-group) if you can't wait the 30 days for the retention period to expire for the content to be permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="0c16d-124">Anche il proprietario del gruppo di Office 365 eliminato è in grado di ripristinare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="0c16d-124">The owner of the deleted Office 365 group is also able to restore the group.</span></span> <span data-ttu-id="0c16d-125">Per ripristinare un gruppo di Office 365 utilizzando l'autorizzazione proprietario senza autorizzazione di amministratore, vedere [ripristino di un gruppo di office 365 tramite PowerShell](#restore-an-office-365-group-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="0c16d-125">To restore an office 365 group using owner permission without administrator permission, see [Restore an Office 365 Group using PowerShell](#restore-an-office-365-group-using-powershell).</span></span>

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a><span data-ttu-id="0c16d-126">Ripristinare un gruppo di Office 365 tramite l'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="0c16d-126">Restore an Office 365 Group using the Exchange admin center</span></span>

<span data-ttu-id="0c16d-127">È necessario disporre delle autorizzazioni di amministratore globale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c16d-127">You must have Office 365 global administrator permissions.</span></span>

1. <span data-ttu-id="0c16d-128">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="0c16d-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="0c16d-129">Nell'interfaccia di amministrazione di Exchange selezionare **destinatari** e quindi scegliere **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="0c16d-129">In the Exchange admin center, select **recipients**, and then choose **groups**.</span></span> <span data-ttu-id="0c16d-130">È possibile visualizzare se il gruppo è attivo o è stato eliminato temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0c16d-130">You can view whether the group is Active or soft-deleted.</span></span> <span data-ttu-id="0c16d-131">Se il gruppo è stato eliminato definitivamente, non sarà incluso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0c16d-131">If the group has been permanently deleted, it won't be listed at all.</span></span>
  
3. <span data-ttu-id="0c16d-132">Per visualizzare l'ora esatta in cui il gruppo è stato eliminato temporaneamente, selezionare il gruppo e visualizzare le informazioni nel riquadro destro.</span><span class="sxs-lookup"><span data-stu-id="0c16d-132">To view the exact time when the group was soft-deleted, select the group and view the info in the right pane.</span></span>
      
4. <span data-ttu-id="0c16d-133">Selezionare il gruppo che si desidera ripristinare, quindi selezionare l'icona Ripristina.</span><span class="sxs-lookup"><span data-stu-id="0c16d-133">Select the group you want to restore, and then select the restore icon.</span></span>
    
    ![Scegliere il gruppo che si desidera ripristinare, quindi selezionare l'icona Ripristina.](../../media/restore-group.png)
  
5. <span data-ttu-id="0c16d-135">Selezionare Aggiorna</span><span class="sxs-lookup"><span data-stu-id="0c16d-135">Select refresh</span></span> ![Icona Aggiorna](../../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) <span data-ttu-id="0c16d-137">per aggiornare le informazioni della pagina.</span><span class="sxs-lookup"><span data-stu-id="0c16d-137">to update the information on the page.</span></span> <span data-ttu-id="0c16d-138">Lo stato del gruppo sarà ora attivo.</span><span class="sxs-lookup"><span data-stu-id="0c16d-138">Your group will show as Active.</span></span> <span data-ttu-id="0c16d-139">Verranno ripristinate anche le forme e i dati del modulo associati al gruppo.</span><span class="sxs-lookup"><span data-stu-id="0c16d-139">Any forms and form data associated with your group will also be restored.</span></span>
    
## <a name="restore-an-office-365-group-using-powershell"></a><span data-ttu-id="0c16d-140">Ripristinare un gruppo di Office 365 tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c16d-140">Restore an Office 365 Group using PowerShell</span></span>

<span data-ttu-id="0c16d-141">È necessario disporre delle autorizzazioni di amministratore globale di Office 365 o essere un ex proprietario del gruppo di Office 365 eliminato.</span><span class="sxs-lookup"><span data-stu-id="0c16d-141">You must have Office 365 global administrator permissions, or be a former owner of the deleted Office 365 group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c16d-142">Se si utilizza il file Remove-MsolGroup in PowerShell per eliminare un gruppo, questo eliminerà definitivamente il gruppo.</span><span class="sxs-lookup"><span data-stu-id="0c16d-142">If you use Remove-MsolGroup in PowerShell to delete a group, this will delete the group permanently.</span></span> <span data-ttu-id="0c16d-143">Quando si usa PowerShell per l'eliminazione di gruppi, è buona pratica usare **Remove-AzureADMSGroup** per eliminare il gruppo di Office 365 temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0c16d-143">When using PowerShell to delete groups, it's best practice to use **Remove-AzureADMSGroup** to soft-delete the Office 365 group.</span></span> <span data-ttu-id="0c16d-144">In questo modo sarà possibile ripristinarlo, se necessario.</span><span class="sxs-lookup"><span data-stu-id="0c16d-144">That way you can restore it if needed.</span></span> 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="0c16d-145">Installare la versione in anteprima di Azure Active Directory PowerShell for Graph</span><span class="sxs-lookup"><span data-stu-id="0c16d-145">Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c16d-146">Non è possibile installare contemporaneamente entrambe le versioni di anteprima e di GA nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="0c16d-146">You cannot install both the preview and GA versions on the same computer at the same time.</span></span>
  
<span data-ttu-id="0c16d-147">Come procedura consigliata, è consigliabile rimanere *sempre* aggiornati, ovvero disinstallare la versione Old AzureADPreview o Old AzureAD e ottenere quella più recente.</span><span class="sxs-lookup"><span data-stu-id="0c16d-147">As a best practice, we recommend *always* staying current, i.e. uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
 
1. <span data-ttu-id="0c16d-148">Nella barra di ricerca digitare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c16d-148">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="0c16d-149">Fare clic con il pulsante destro del mouse su **Windows PowerShell** e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="0c16d-149">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
  
2. <span data-ttu-id="0c16d-150">Esaminare i moduli installati:</span><span class="sxs-lookup"><span data-stu-id="0c16d-150">Review your installed modules:</span></span>
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. <span data-ttu-id="0c16d-151">Per disinstallare una versione precedente di AzureADPreview o AzureAD, eseguire questo comando:</span><span class="sxs-lookup"><span data-stu-id="0c16d-151">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
```
   Uninstall-Module AzureADPreview
```

<span data-ttu-id="0c16d-152">oppure</span><span class="sxs-lookup"><span data-stu-id="0c16d-152">or</span></span>
  
```
   Uninstall-Module AzureAD
```

4. <span data-ttu-id="0c16d-153">To install the latest version of AzureADPreview, run this command:</span><span class="sxs-lookup"><span data-stu-id="0c16d-153">To install the latest version of AzureADPreview, run this command:</span></span>
  
```
   Install-Module AzureADPreview
```



<span data-ttu-id="0c16d-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. </span><span class="sxs-lookup"><span data-stu-id="0c16d-154">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>
  
### <a name="restore-the-deleted-group"></a><span data-ttu-id="0c16d-155">Ripristinare il gruppo eliminato</span><span class="sxs-lookup"><span data-stu-id="0c16d-155">Restore the deleted group</span></span>
  
1. <span data-ttu-id="0c16d-156">È stato installato il modulo **AzureADPreview** , come indicato nella sezione previoius "installare la versione di anteprima del modulo di Azure Active Directory per Windows PowerShell"?</span><span class="sxs-lookup"><span data-stu-id="0c16d-156">Did you install the **AzureADPreview** module, as instructed in the previoius section "Install the preview version of the Azure Active Directory Module for Windows PowerShell"?</span></span>  <span data-ttu-id="0c16d-157">La causa principale del mancato funzionamento di questa procedura è l'assenza della versione **in anteprima** più recente.</span><span class="sxs-lookup"><span data-stu-id="0c16d-157">Not having the most current **preview** version is the #1 reason these steps don't work for people.</span></span> 
    
2. <span data-ttu-id="0c16d-158">Se non è già aperta, aprire una finestra Windows PowerShell nel computer. Non importa se è una finestra Windows PowerShell normale o una aperta selezionando **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="0c16d-158">If you haven't already, open a Windows PowerShell window on your computer (it doesn't matter if it's a normal Windows PowerShell window, or one you opened by selecting **Run as administrator**).</span></span>
    
3. <span data-ttu-id="0c16d-159">Per eseguire i comandi seguenti, premere **invio** dopo ognuno:</span><span class="sxs-lookup"><span data-stu-id="0c16d-159">Run the following commands by pressing **Enter** after each one:</span></span> 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  <span data-ttu-id="0c16d-160">Nella schermata **accedi al tuo account** che si apre, immettere il nome utente e la password dell'account amministrativo per connettersi al servizio Azure ad e selezionare **Accedi**.</span><span class="sxs-lookup"><span data-stu-id="0c16d-160">On the **Sign in to your Account** screen that opens, enter your administrative account user name and password to connect you to your Azure AD service, and select **Sign in**.</span></span>
  
4. <span data-ttu-id="0c16d-161">Eseguire questo comando per visualizzare tutti i gruppi di Office 365 con eliminazione temporanea nell'organizzazione che sono ancora entro il periodo di cancellazione di 30 giorni:</span><span class="sxs-lookup"><span data-stu-id="0c16d-161">Run this command to display all soft-deleted Office 365 groups in your organization that are still within the 30 day soft-deletion period:</span></span>
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. <span data-ttu-id="0c16d-162">Annotare l'ID oggetto del gruppo o dei gruppi da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="0c16d-162">Take note of the object ID of the group, or groups, you want to restore.</span></span> <span data-ttu-id="0c16d-163">Se non si Visualizza il gruppo che si sta cercando in questo elenco, è probabile che sia già stato eliminato definitivamente.</span><span class="sxs-lookup"><span data-stu-id="0c16d-163">If you don't see the group you're looking for on this list then it has likely been permanently purged already.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="0c16d-164">Se è stato creato un nuovo gruppo con lo stesso indirizzo SMTP del gruppo eliminato, occorre eliminare il nuovo gruppo per poter ripristinare quello eliminato.</span><span class="sxs-lookup"><span data-stu-id="0c16d-164">If a new group has been created with the same alias or SMTP address as your deleted group, you will have to delete that new group before you'll be able to restore your deleted group.</span></span> 
  
6. <span data-ttu-id="0c16d-165">Per ripristinare il gruppo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0c16d-165">To restore that group, run this command:</span></span>
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. <span data-ttu-id="0c16d-166">Questo processo in genere richiede solo pochi minuti, ma in alcuni casi rari può richiedere fino a 24 ore per essere completamente ripristinato.</span><span class="sxs-lookup"><span data-stu-id="0c16d-166">This process usually takes just a few minutes but in a few rare cases it can take as long as 24 hours to be completely restored.</span></span> <span data-ttu-id="0c16d-167">Per verificare che il gruppo sia stato ripristinato correttamente, eseguire questo comando in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0c16d-167">To verify that the group has been successfully restored, run this command in PowerShell:</span></span>
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

<span data-ttu-id="0c16d-p110">Una volta completato il ripristino, il gruppo dovrebbe ricomparire nel riquadro di spostamento in Outlook e in Outlook sul Web. Tutti i contenuti ripristinati, tra cui quelli di SharePoint e Planner, dovrebbero essere di nuovo disponibili per i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0c16d-p110">Once the restore has successfully completed, the group should reappear on the navigation pane in Outlook and Outlook on the web. All restored content, including SharePoint and Planner, should be available to the group members again.</span></span>
  
## <a name="permanently-delete-an-office-365-group"></a><span data-ttu-id="0c16d-170">Eliminare definitivamente un gruppo di Office 365</span><span class="sxs-lookup"><span data-stu-id="0c16d-170">Permanently delete an Office 365 group</span></span>

<span data-ttu-id="0c16d-171">A volte è possibile che si desideri eliminare definitivamente un gruppo senza attendere la scadenza del periodo di cancellazione di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="0c16d-171">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="0c16d-172">A tale scopo, avviare PowerShell ed eseguire questo comando per ottenere l'ID oggetto del gruppo:</span><span class="sxs-lookup"><span data-stu-id="0c16d-172">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="0c16d-173">Prendere nota dell'ID oggetto del gruppo o dei gruppi che si desidera eliminare definitivamente.</span><span class="sxs-lookup"><span data-stu-id="0c16d-173">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="0c16d-174">Il gruppo e i dati che contiene vengono eliminati in modo definitivo.</span><span class="sxs-lookup"><span data-stu-id="0c16d-174">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="0c16d-175">Per eliminare il gruppo, eseguire questo comando in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0c16d-175">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="0c16d-p112">Per verificare che il gruppo sia stato eliminato correttamente, eseguire di nuovo il cmdlet  *Get-AzureADMSDeletedGroup*  per controllare che il gruppo non compaia più nell'elenco dei gruppi eliminati temporaneamente. In alcuni casi l'eliminazione definitiva del gruppo e di tutti i suoi dati può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="0c16d-p112">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-office-365-groups"></a><span data-ttu-id="0c16d-178">Domande su Gruppi di Office 365?</span><span class="sxs-lookup"><span data-stu-id="0c16d-178">Got questions about Office 365 Groups?</span></span>

<span data-ttu-id="0c16d-179">Visitare la [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) per inviare domande e partecipare a conversazioni sui gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c16d-179">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Office 365 Groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="0c16d-180">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="0c16d-180">Related articles</span></span>

[<span data-ttu-id="0c16d-181">Gestire Gruppi di Office 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="0c16d-181">Manage Office 365 Groups with PowerShell</span></span>](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[<span data-ttu-id="0c16d-182">Eliminare gruppi usando il cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="0c16d-182">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="0c16d-183">Gestire le impostazioni del sito del team connesso al gruppo</span><span class="sxs-lookup"><span data-stu-id="0c16d-183">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="0c16d-184">Eliminare un gruppo in Outlook</span><span class="sxs-lookup"><span data-stu-id="0c16d-184">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
