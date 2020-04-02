---
title: Accedere ai dati di un ex utente ed eseguirne il backup
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
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
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Informazioni su come conservare i file e i messaggi di posta elettronica di un dipendente quando la persona lascia l'organizzazione.
ms.openlocfilehash: 2b608b51060e746d0b69fd887882b51735578496
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "43105760"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="36c09-103">Accedere ai dati di un ex utente ed eseguirne il backup</span><span class="sxs-lookup"><span data-stu-id="36c09-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="36c09-104">Quando un dipendente lascia l'organizzazione, è probabile che si desideri accedere ai propri dati (documenti e messaggi di posta elettronica) e rivederla, eseguirne il backup o darla a un nuovo dipendente.</span><span class="sxs-lookup"><span data-stu-id="36c09-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="36c09-105">Accedere ai documenti di OneDrive di un utente precedente</span><span class="sxs-lookup"><span data-stu-id="36c09-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="36c09-106">Se si rimuove la licenza di un utente, ma non si elimina l'account, è possibile accedere al contenuto del OneDrive dell'utente.</span><span class="sxs-lookup"><span data-stu-id="36c09-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="36c09-107">Se si elimina l'account dell'utente, per impostazione predefinita sono presenti 30 giorni per accedere ai dati di OneDrive dell'utente precedente.</span><span class="sxs-lookup"><span data-stu-id="36c09-107">If you delete the user's account, you have 30 days by default to access the former user’s OneDrive data.</span></span> <span data-ttu-id="36c09-108">[Informazioni su come impostare la conservazione di OneDrive per gli utenti eliminati](/onedrive/set-retention).</span><span class="sxs-lookup"><span data-stu-id="36c09-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="36c09-109">Se non si [Ripristina un account utente](/office365/admin/add-users/restore-user) entro questo intervallo di tempo, viene eliminato il contenuto di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="36c09-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="36c09-110">Per conservare i file di OneDrive di un utente precedente, è necessario accedere al proprio OneDrive e quindi spostare i file che si desidera mantenere.</span><span class="sxs-lookup"><span data-stu-id="36c09-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="36c09-111">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="36c09-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="36c09-112">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="36c09-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="36c09-113">Selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="36c09-113">Select a user.</span></span>

3. <span data-ttu-id="36c09-114">Nel riquadro a destra, selezionare **OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="36c09-114">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="36c09-115">In **Accedi ai file**, selezionare **Crea collegamento ai file**.</span><span class="sxs-lookup"><span data-stu-id="36c09-115">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="36c09-116">Selezionare il collegamento per aprire il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="36c09-116">Select the link to open the file location.</span></span> <span data-ttu-id="36c09-117">Scaricare i file nel computer in uso oppure selezionare **Sposta in** o **copia** in per spostarli o copiarli nel proprio OneDrive o in una raccolta condivisa.</span><span class="sxs-lookup"><span data-stu-id="36c09-117">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="36c09-118">È possibile spostare o copiare fino a 500 MB di file e cartelle alla volta.</span><span class="sxs-lookup"><span data-stu-id="36c09-118">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="36c09-119">Quando si spostano o si copiano documenti con cronologia delle versioni, viene spostata solo la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="36c09-119">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="36c09-120">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="36c09-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="36c09-121">Selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="36c09-121">Select a user.</span></span>

3. <span data-ttu-id="36c09-122">Nel riquadro destro espandere Impostazioni di **OneDrive**e quindi fare **clic su Access** **file**.</span><span class="sxs-lookup"><span data-stu-id="36c09-122">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="36c09-123">Selezionare il collegamento per aprire il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="36c09-123">Select the link to open the file location.</span></span> <span data-ttu-id="36c09-124">Scaricare i file nel computer in uso oppure selezionare **Sposta in** o **copia** in per spostarli o copiarli nel proprio OneDrive o in una raccolta condivisa.</span><span class="sxs-lookup"><span data-stu-id="36c09-124">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="36c09-125">È possibile spostare o copiare fino a 500 MB di file e cartelle alla volta.</span><span class="sxs-lookup"><span data-stu-id="36c09-125">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="36c09-126">Quando si spostano o si copiano documenti con cronologia delle versioni, viene spostata solo la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="36c09-126">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="36c09-127">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="36c09-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="36c09-128">Selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="36c09-128">Select a user.</span></span>

3. <span data-ttu-id="36c09-129">Nel riquadro destro espandere Impostazioni di **OneDrive**e quindi fare **clic su Access** **file**.</span><span class="sxs-lookup"><span data-stu-id="36c09-129">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="36c09-130">Selezionare il collegamento per aprire il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="36c09-130">Select the link to open the file location.</span></span> <span data-ttu-id="36c09-131">Scaricare i file nel computer in uso oppure selezionare **Sposta in** o **copia** in per spostarli o copiarli nel proprio OneDrive o in una raccolta condivisa.</span><span class="sxs-lookup"><span data-stu-id="36c09-131">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="36c09-132">È possibile spostare o copiare fino a 500 MB di file e cartelle alla volta.</span><span class="sxs-lookup"><span data-stu-id="36c09-132">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="36c09-133">Quando si spostano o si copiano documenti con cronologia delle versioni, viene spostata solo la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="36c09-133">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="36c09-134">Revocare l'accesso dell'amministratore all'OneDrive di un utente</span><span class="sxs-lookup"><span data-stu-id="36c09-134">Revoke admin access to a user’s OneDrive</span></span>

<span data-ttu-id="36c09-135">In qualità di amministratore globale, è possibile accedere al contenuto del OneDrive di un utente, ma potrebbe essere opportuno rimuovere l'accesso quando non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="36c09-135">As global admin, you can give yourself access to the content in a user’s OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="36c09-136">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Amministrazione</a> come amministratore globale o amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="36c09-136">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="36c09-137">Se viene visualizzato un messaggio che non dispone dell'autorizzazione necessaria per accedere all'interfaccia di amministrazione, non si dispone delle autorizzazioni di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36c09-137">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="36c09-138">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a> come amministratore globale o amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="36c09-138">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="36c09-139">Se viene visualizzato un messaggio che non dispone dell'autorizzazione necessaria per accedere all'interfaccia di amministrazione, non si dispone delle autorizzazioni di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36c09-139">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="36c09-140">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a> come amministratore globale o amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="36c09-140">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="36c09-141">Se viene visualizzato un messaggio che non dispone dell'autorizzazione necessaria per accedere all'interfaccia di amministrazione, non si dispone delle autorizzazioni di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36c09-141">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="36c09-142">Nel riquadro sinistro, selezionare interfaccia di **Amministrazione** \> di **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="36c09-142">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="36c09-143">Potrebbe essere necessario selezionare **Mostra tutto** per vedere l'elenco di interfacce di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="36c09-143">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="36c09-144">Se viene visualizzata l'interfaccia di amministrazione di SharePoint classica, selezionare **Apri ora** nella parte superiore della pagina per aprire la nuova interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="36c09-144">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

4. <span data-ttu-id="36c09-145">Nel riquadro sinistro, selezionare **altre caratteristiche**.</span><span class="sxs-lookup"><span data-stu-id="36c09-145">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="36c09-146">In **profili utente**selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="36c09-146">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="36c09-147">In **utenti**selezionare **Gestisci profili utente**.</span><span class="sxs-lookup"><span data-stu-id="36c09-147">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="36c09-148">Immettere il nome dell'utente e selezionare **trova**.</span><span class="sxs-lookup"><span data-stu-id="36c09-148">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="36c09-149">Fare clic con il pulsante destro del mouse sull'utente, quindi scegliere **Gestisci proprietari raccolta siti**.</span><span class="sxs-lookup"><span data-stu-id="36c09-149">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="36c09-150">Rimuovere la persona che non ha più bisogno di accedere ai dati dell'utente e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="36c09-150">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="36c09-151">Accedere ai dati di Outlook di un utente precedente</span><span class="sxs-lookup"><span data-stu-id="36c09-151">Access the Outlook data of a former user</span></span>

<span data-ttu-id="36c09-152">Per salvare i messaggi di posta elettronica, il calendario, le attività e i contatti dell'ex dipendente, è possibile esportare le informazioni in un file di dati di Outlook (con estensione pst).</span><span class="sxs-lookup"><span data-stu-id="36c09-152">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="36c09-153">[Aggiungere il messaggio di posta elettronica dell'ex dipendente](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) al proprio Outlook (se si [Reimposta la password dell'utente](reset-passwords.md), è possibile impostarla su una cosa che si conosce solo).</span><span class="sxs-lookup"><span data-stu-id="36c09-153">[Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="36c09-154">In Outlook selezionare **file**.</span><span class="sxs-lookup"><span data-stu-id="36c09-154">In Outlook, select **File**.</span></span>
    
    ![Questo è l'aspetto della barra multifunzione in Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="36c09-156">Selezionare **Open &amp; Export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="36c09-156">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Comando Importa/esporta nella visualizzazione Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="36c09-158">Selezionare **Esporta in un file**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="36c09-158">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Opzione Esporta in un file nell'Importazione/Esportazione guidata](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="36c09-160">Selezionare **file di dati di Outlook (con estensione pst)** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="36c09-160">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="36c09-161">Selezionare l'account che si desidera esportare selezionando il nome o l'indirizzo di posta elettronica, ad esempio Mailbox-Anne Weiler o anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="36c09-161">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="36c09-162">Se si vuole esportare tutto il contenuto dell'account, inclusi i messaggi di posta elettronica, il calendario, i contatti, le attività e le note, verificare che sia selezionata la casella di controllo **Includi sottocartelle**.</span><span class="sxs-lookup"><span data-stu-id="36c09-162">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="36c09-p108">È possibile esportare un solo account alla volta. Se si desidera esportare più account, ripetere questi passaggi per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="36c09-p108">You can export one account at a time. If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Finestra di dialogo Esporta file di dati di Outlook con la cartella principale e l'opzione Includi sottocartelle selezionate](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="36c09-166">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="36c09-166">Select **Next**.</span></span>
    
8. <span data-ttu-id="36c09-167">Selezionare **Sfoglia** per selezionare il percorso in cui salvare il file di dati di Outlook (con estensione pst).</span><span class="sxs-lookup"><span data-stu-id="36c09-167">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="36c09-168">Digitare un *nome di file*e quindi fare clic su **OK** per continuare.</span><span class="sxs-lookup"><span data-stu-id="36c09-168">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="36c09-169">Se l'esportazione è già stata usata, verranno visualizzati il nome del file e il percorso della cartella precedenti.</span><span class="sxs-lookup"><span data-stu-id="36c09-169">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="36c09-170">Digitare un *nome di file diverso* prima di selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="36c09-170">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="36c09-171">Se si esegue l'esportazione in un File di dati di Outlook (.pst) esistente, in **Opzioni** specificare come procedere per l'esportazione di elementi già esistenti nel file.</span><span class="sxs-lookup"><span data-stu-id="36c09-171">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="36c09-172">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="36c09-172">Select **Finish**.</span></span>
    
<span data-ttu-id="36c09-173">Outlook avvia immediatamente l'esportazione, a meno che non venga creato un nuovo File di dati di Outlook (pst) o non venga usato un file protetto da password.</span><span class="sxs-lookup"><span data-stu-id="36c09-173">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="36c09-174">Se si crea un nuovo File di dati di Outlook (pst), è possibile impostare una password facoltativa per proteggerlo.</span><span class="sxs-lookup"><span data-stu-id="36c09-174">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="36c09-175">Quando viene visualizzata la finestra di dialogo **Crea file di dati di Outlook** , digitare *la password nelle* caselle **password** e **Verifica password** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="36c09-175">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="36c09-176">Nella finestra di dialogo **password file di dati di Outlook** Digitare la *password*e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="36c09-176">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="36c09-177">Se si esporta in un file di dati di Outlook (con estensione pst) esistente protetto da password, nella finestra di dialogo **password file di dati di Outlook** Digitare la *password*e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="36c09-177">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="36c09-178">Vedere come [esportare o eseguire il backup di posta elettronica, contatti e calendario in un file PST](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) di Outlook in Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="36c09-178">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="36c09-179">Per impostazione predefinita, il messaggio di posta elettronica è disponibile offline per un periodo di 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="36c09-179">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="36c09-180">Se necessario, vedere How to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span><span class="sxs-lookup"><span data-stu-id="36c09-180">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="36c09-181">Concedere a un altro utente l'accesso alla posta elettronica di un utente precedente</span><span class="sxs-lookup"><span data-stu-id="36c09-181">Give another user access to a former user's email</span></span> 

<span data-ttu-id="36c09-182">Per concedere l'accesso ai messaggi di posta elettronica, al calendario, alle attività e ai contatti dell'ex dipendente a un altro dipendente, importare le informazioni nella cartella posta in arrivo di Outlook di un altro dipendente.</span><span class="sxs-lookup"><span data-stu-id="36c09-182">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="36c09-183">È inoltre possibile [convertire la cassetta postale dell'utente precedente in una cassetta postale condivisa](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) o [inoltrare la posta elettronica di un ex dipendente a un altro dipendente](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="36c09-183">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="36c09-184">In Outlook, passare a **file** \> **Open &amp; Export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="36c09-184">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="36c09-185">Viene avviata l'Importazione/Esportazione guidata.</span><span class="sxs-lookup"><span data-stu-id="36c09-185">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="36c09-186">Selezionare **Importa da un altro programma o file**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="36c09-186">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Importazione/Esportazione guidata](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="36c09-188">Selezionare **file di dati di Outlook (con estensione pst)** e quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="36c09-188">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="36c09-189">Passare al file PST che si vuole importare.</span><span class="sxs-lookup"><span data-stu-id="36c09-189">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="36c09-190">In **Opzioni** scegliere come si vuole gestire i duplicati.</span><span class="sxs-lookup"><span data-stu-id="36c09-190">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="36c09-191">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="36c09-191">Select **Next**.</span></span>
    
7. <span data-ttu-id="36c09-192">Se al file di dati di Outlook (con estensione pst) è stata assegnata una password, immettere la password e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="36c09-192">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="36c09-193">Impostare le opzioni per l'importazione degli elementi.</span><span class="sxs-lookup"><span data-stu-id="36c09-193">Set the options for importing items.</span></span> <span data-ttu-id="36c09-194">Solitamente, non è necessario modificare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="36c09-194">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="36c09-195">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="36c09-195">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="36c09-196">La procedura resta invariata per l'accesso ai dati di posta elettronica e di OneDrive di un utente esistente.</span><span class="sxs-lookup"><span data-stu-id="36c09-196">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="36c09-197">Se si desidera importare o ripristinare solo alcuni elementi da un file di dati di Outlook (con estensione pst), è possibile aprire il file di dati di Outlook.</span><span class="sxs-lookup"><span data-stu-id="36c09-197">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="36c09-198">Nel riquadro di spostamento, quindi, trascinare gli elementi dalle cartelle dei file di dati di Outlook alle cartelle di Outlook esistenti.</span><span class="sxs-lookup"><span data-stu-id="36c09-198">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="36c09-199">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="36c09-199">Related articles</span></span>
[<span data-ttu-id="36c09-200">Rimuovere un ex dipendente da Office 365</span><span class="sxs-lookup"><span data-stu-id="36c09-200">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="36c09-201">Aggiungere e rimuovere gli amministratori in un account di OneDrive</span><span class="sxs-lookup"><span data-stu-id="36c09-201">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="36c09-202">Ripristinare un OneDrive eliminato</span><span class="sxs-lookup"><span data-stu-id="36c09-202">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="36c09-203">Conservazione ed eliminazione di OneDrive</span><span class="sxs-lookup"><span data-stu-id="36c09-203">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
