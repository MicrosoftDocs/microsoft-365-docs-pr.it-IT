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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Informazioni su come conservare i file e i messaggi di posta elettronica di un dipendente quando la persona lascia l'organizzazione.
ms.openlocfilehash: 38cc44bbe602f3c8c38ca54391d0967fbafbfcf7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906313"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="8a229-103">Accedere ai dati di un ex utente ed eseguirne il backup</span><span class="sxs-lookup"><span data-stu-id="8a229-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="8a229-104">Quando un dipendente lascia l'organizzazione, è probabile che si desideri accedere ai propri dati (documenti e messaggi di posta elettronica) ed esaminarlo, eseguire il backup o assegnarlo a un nuovo dipendente.</span><span class="sxs-lookup"><span data-stu-id="8a229-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="8a229-105">Accedere ai documenti di OneDrive di un ex utente</span><span class="sxs-lookup"><span data-stu-id="8a229-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="8a229-106">Se si rimuove la licenza di un utente ma non si elimina l'account, è possibile concedere l'accesso al contenuto in OneDrive dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8a229-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="8a229-107">Se elimini l'account dell'utente, hai 30 giorni per impostazione predefinita per accedere ai dati di OneDrive dell'ex utente.</span><span class="sxs-lookup"><span data-stu-id="8a229-107">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="8a229-108">[Informazioni su come impostare la conservazione di OneDrive per gli utenti eliminati.](/onedrive/set-retention)</span><span class="sxs-lookup"><span data-stu-id="8a229-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="8a229-109">Se non si ripristina un [account utente entro](/office365/admin/add-users/restore-user) questo periodo di tempo, il relativo contenuto di OneDrive viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="8a229-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="8a229-110">Per conservare i file di OneDrive di un ex utente, concedere innanzitutto l'accesso a OneDrive e quindi spostare i file che si desidera mantenere.</span><span class="sxs-lookup"><span data-stu-id="8a229-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8a229-111">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="8a229-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="8a229-112">Selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="8a229-112">Select a user.</span></span>

3. <span data-ttu-id="8a229-113">Nel riquadro destro selezionare **OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="8a229-113">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="8a229-114">In **Ottieni accesso ai file** seleziona Crea collegamento ai **file**.</span><span class="sxs-lookup"><span data-stu-id="8a229-114">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="8a229-115">Selezionare il collegamento per aprire il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="8a229-115">Select the link to open the file location.</span></span> <span data-ttu-id="8a229-116">Scaricare i file nel computer oppure  selezionare Sposta **in** o Copia in per spostarli o copiarli nel proprio OneDrive o in una raccolta condivisa.</span><span class="sxs-lookup"><span data-stu-id="8a229-116">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="8a229-117">È possibile spostare o copiare fino a 500 MB di file e cartelle alla volta.</span><span class="sxs-lookup"><span data-stu-id="8a229-117">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="8a229-118">Quando si spostano o copiano documenti con cronologia delle versioni, viene spostata solo la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="8a229-118">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8a229-119">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="8a229-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="8a229-120">Selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="8a229-120">Select a user.</span></span>

3. <span data-ttu-id="8a229-121">Nel riquadro destro espandere Impostazioni **di OneDrive** e quindi accanto ad **Access** selezionare **Accedi ai file.**</span><span class="sxs-lookup"><span data-stu-id="8a229-121">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="8a229-122">Selezionare il collegamento per aprire il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="8a229-122">Select the link to open the file location.</span></span> <span data-ttu-id="8a229-123">Scaricare i file nel computer oppure  selezionare Sposta **in** o Copia in per spostarli o copiarli nel proprio OneDrive o in una raccolta condivisa.</span><span class="sxs-lookup"><span data-stu-id="8a229-123">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="8a229-124">È possibile spostare o copiare fino a 500 MB di file e cartelle alla volta.</span><span class="sxs-lookup"><span data-stu-id="8a229-124">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="8a229-125">Quando si spostano o copiano documenti con cronologia delle versioni, viene spostata solo la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="8a229-125">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8a229-126">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="8a229-126">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="8a229-127">Selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="8a229-127">Select a user.</span></span>

3. <span data-ttu-id="8a229-128">Nel riquadro destro espandere Impostazioni **di OneDrive** e quindi accanto ad **Access** selezionare **Accedi ai file.**</span><span class="sxs-lookup"><span data-stu-id="8a229-128">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="8a229-129">Selezionare il collegamento per aprire il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="8a229-129">Select the link to open the file location.</span></span> <span data-ttu-id="8a229-130">Scaricare i file nel computer oppure  selezionare Sposta **in** o Copia in per spostarli o copiarli nel proprio OneDrive o in una raccolta condivisa.</span><span class="sxs-lookup"><span data-stu-id="8a229-130">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="8a229-131">È possibile spostare o copiare fino a 500 MB di file e cartelle alla volta.</span><span class="sxs-lookup"><span data-stu-id="8a229-131">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="8a229-132">Quando si spostano o copiano documenti con cronologia delle versioni, viene spostata solo la versione più recente.</span><span class="sxs-lookup"><span data-stu-id="8a229-132">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="8a229-133">Revocare l'accesso amministratore a OneDrive di un utente</span><span class="sxs-lookup"><span data-stu-id="8a229-133">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="8a229-134">In quanto amministratore globale, puoi concedere l'accesso al contenuto in OneDrive di un utente, ma potresti voler rimuovere l'accesso quando non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="8a229-134">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="8a229-135">Accedere <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">all'interfaccia di amministrazione</a> come amministratore globale o amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8a229-135">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="8a229-136">Se viene visualizzato un messaggio che indica che non si dispone dell'autorizzazione per accedere all'interfaccia di amministrazione, non si dispone delle autorizzazioni di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8a229-136">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="8a229-137">Accedere <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">all'interfaccia di amministrazione</a> come amministratore globale o amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8a229-137">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="8a229-138">Se viene visualizzato un messaggio che indica che non si dispone dell'autorizzazione per accedere all'interfaccia di amministrazione, non si dispone delle autorizzazioni di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8a229-138">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8a229-139">Accedere <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">all'interfaccia di amministrazione</a> come amministratore globale o amministratore di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8a229-139">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="8a229-140">Se viene visualizzato un messaggio che indica che non si dispone dell'autorizzazione per accedere all'interfaccia di amministrazione, non si dispone delle autorizzazioni di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8a229-140">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="8a229-141">Nel riquadro sinistro selezionare **Interfaccia di amministrazione di** \> **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="8a229-141">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="8a229-142">Potrebbe essere necessario selezionare **Mostra tutto** per vedere l'elenco di interfacce di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="8a229-142">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="8a229-143">Se viene visualizzata l'interfaccia di amministrazione di SharePoint classica, selezionare **Apri** ora nella parte superiore della pagina per aprire l'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8a229-143">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the SharePoint admin center.</span></span>

4. <span data-ttu-id="8a229-144">Nel riquadro sinistro selezionare **Altre funzionalità.**</span><span class="sxs-lookup"><span data-stu-id="8a229-144">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="8a229-145">In **Profili utente** selezionare **Apri.**</span><span class="sxs-lookup"><span data-stu-id="8a229-145">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="8a229-146">In **Utenti** selezionare **Gestisci profili utente.**</span><span class="sxs-lookup"><span data-stu-id="8a229-146">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="8a229-147">Immettere il nome dell'utente e selezionare **Trova**.</span><span class="sxs-lookup"><span data-stu-id="8a229-147">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="8a229-148">Fare clic con il pulsante destro del mouse sull'utente e quindi **scegliere Gestisci proprietari raccolta siti**.</span><span class="sxs-lookup"><span data-stu-id="8a229-148">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="8a229-149">Rimuovere la persona che non ha più bisogno di accedere ai dati dell'utente e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="8a229-149">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="8a229-150">Accedere ai dati di Outlook di un ex utente</span><span class="sxs-lookup"><span data-stu-id="8a229-150">Access the Outlook data of a former user</span></span>

<span data-ttu-id="8a229-151">Per salvare i messaggi di posta elettronica, il calendario, le attività e i contatti dell'ex dipendente, è possibile esportare le informazioni in un file di dati di Outlook (con estensione pst).</span><span class="sxs-lookup"><span data-stu-id="8a229-151">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="8a229-152">[Aggiungere il messaggio di posta elettronica dell'ex](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) dipendente a Outlook (se si reimposta la [password dell'utente,](reset-passwords.md)è possibile impostarlo su un elemento che solo si conosce).</span><span class="sxs-lookup"><span data-stu-id="8a229-152">[Add the former employee's email](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="8a229-153">In Outlook, selezionare **File**.</span><span class="sxs-lookup"><span data-stu-id="8a229-153">In Outlook, select **File**.</span></span>
    
    ![Questo è l'aspetto della barra multifunzione in Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="8a229-155">Selezionare **Apri &amp;** \> **Esportazione/Importazione/Esportazione.**</span><span class="sxs-lookup"><span data-stu-id="8a229-155">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Comando Importa/esporta nella visualizzazione Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="8a229-157">Selezionare **Esporta in un file** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="8a229-157">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Opzione Esporta in un file nell'Importazione/Esportazione guidata](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="8a229-159">Selezionare **File di dati di Outlook (.pst)** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="8a229-159">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="8a229-160">Selezionare l'account che si desidera esportare selezionando il nome o l'indirizzo di posta elettronica, ad esempio Cassetta postale - Anne Weiler o anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8a229-160">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="8a229-161">Se si vuole esportare tutto il contenuto dell'account, inclusi i messaggi di posta elettronica, il calendario, i contatti, le attività e le note, verificare che sia selezionata la casella di controllo **Includi sottocartelle**.</span><span class="sxs-lookup"><span data-stu-id="8a229-161">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8a229-p108">È possibile esportare un solo account alla volta. Se si desidera esportare più account, ripetere questi passaggi per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="8a229-p108">You can export one account at a time. If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Finestra di dialogo Esporta file di dati di Outlook con la cartella principale e l'opzione Includi sottocartelle selezionate](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="8a229-165">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8a229-165">Select **Next**.</span></span>
    
8. <span data-ttu-id="8a229-166">Selezionare **Sfoglia** per selezionare la posizione in cui salvare il file di dati di Outlook (.pst).</span><span class="sxs-lookup"><span data-stu-id="8a229-166">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="8a229-167">Digitare un  *nome di file* e quindi scegliere **OK** per continuare.</span><span class="sxs-lookup"><span data-stu-id="8a229-167">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8a229-168">Se l'esportazione è già stata usata, verranno visualizzati il nome del file e il percorso della cartella precedenti.</span><span class="sxs-lookup"><span data-stu-id="8a229-168">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="8a229-169">Digitare un *nome di file diverso* prima di selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="8a229-169">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="8a229-170">Se si esegue l'esportazione in un File di dati di Outlook (.pst) esistente, in **Opzioni** specificare come procedere per l'esportazione di elementi già esistenti nel file.</span><span class="sxs-lookup"><span data-stu-id="8a229-170">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="8a229-171">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="8a229-171">Select **Finish**.</span></span>
    
<span data-ttu-id="8a229-172">Outlook avvia immediatamente l'esportazione, a meno che non venga creato un nuovo File di dati di Outlook (pst) o non venga usato un file protetto da password.</span><span class="sxs-lookup"><span data-stu-id="8a229-172">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="8a229-173">Se si crea un nuovo File di dati di Outlook (pst), è possibile impostare una password facoltativa per proteggerlo.</span><span class="sxs-lookup"><span data-stu-id="8a229-173">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="8a229-174">Quando viene visualizzata la finestra di dialogo Crea file di dati di **Outlook,** digitare la *password* nelle caselle **Password** e Verifica **password** e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="8a229-174">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="8a229-175">Nella finestra **di dialogo Password file** di dati di Outlook digitare la *password* e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="8a229-175">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="8a229-176">Se si sta esportando in un file di dati di Outlook (pst) esistente protetto da password, nella finestra di dialogo **Password file** di dati di Outlook digitare la  *password* e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a229-176">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="8a229-177">Informazioni su come [esportare o eseguire il backup](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) di posta elettronica, contatti e calendario in un file pst di Outlook in Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="8a229-177">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="8a229-178">Per impostazione predefinita, la posta elettronica è disponibile offline per un periodo di 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="8a229-178">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="8a229-179">Se necessario, vedere come aumentare [i dati disponibili offline.](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)</span><span class="sxs-lookup"><span data-stu-id="8a229-179">If required, see how to [increase the data available offline](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="8a229-180">Concedere a un altro utente l'accesso alla posta elettronica di un ex utente</span><span class="sxs-lookup"><span data-stu-id="8a229-180">Give another user access to a former user's email</span></span> 

<span data-ttu-id="8a229-181">Per concedere l'accesso ai messaggi di posta elettronica, al calendario, alle attività e ai contatti dell'ex dipendente a un altro dipendente, importare le informazioni nella posta in arrivo di Outlook di un altro dipendente.</span><span class="sxs-lookup"><span data-stu-id="8a229-181">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="8a229-182">È inoltre possibile [convertire la cassetta postale dell'ex](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) utente in una cassetta postale condivisa o inoltrare la posta elettronica di un ex dipendente a un altro [dipendente.](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="8a229-182">You can also [convert the former user's mailbox to a shared mailbox](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="8a229-183">In Outlook, andare a **File** \> **Apri &amp; Esporta** \> **Importazione/Esportazione**.</span><span class="sxs-lookup"><span data-stu-id="8a229-183">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="8a229-184">Viene avviata l'Importazione/Esportazione guidata.</span><span class="sxs-lookup"><span data-stu-id="8a229-184">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="8a229-185">Selezionare **Importa da un altro programma o file** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="8a229-185">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Importazione/Esportazione guidata](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="8a229-187">Selezionare **File di dati di Outlook (.pst)** e selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="8a229-187">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="8a229-188">Passare al file PST che si vuole importare.</span><span class="sxs-lookup"><span data-stu-id="8a229-188">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="8a229-189">In **Opzioni** scegliere come si vuole gestire i duplicati.</span><span class="sxs-lookup"><span data-stu-id="8a229-189">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="8a229-190">Selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8a229-190">Select **Next**.</span></span>
    
7. <span data-ttu-id="8a229-191">Se al file di dati di Outlook (.pst) è stata assegnata una password, immettere la password e quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="8a229-191">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="8a229-192">Impostare le opzioni per l'importazione degli elementi.</span><span class="sxs-lookup"><span data-stu-id="8a229-192">Set the options for importing items.</span></span> <span data-ttu-id="8a229-193">Solitamente, non è necessario modificare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="8a229-193">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="8a229-194">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="8a229-194">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="8a229-195">I passaggi rimangono gli stessi per accedere a OneDrive e ai dati di posta elettronica di un utente esistente.</span><span class="sxs-lookup"><span data-stu-id="8a229-195">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="8a229-196">Se si desidera importare o ripristinare solo alcuni elementi da un file di dati di Outlook (pst), è possibile aprire il file di dati di Outlook.</span><span class="sxs-lookup"><span data-stu-id="8a229-196">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="8a229-197">Nel riquadro di spostamento trascinare quindi gli elementi dalle cartelle File di dati di Outlook alle cartelle di Outlook esistenti.</span><span class="sxs-lookup"><span data-stu-id="8a229-197">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="8a229-198">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="8a229-198">Related articles</span></span>
[<span data-ttu-id="8a229-199">Rimuovere un ex dipendente da Office 365</span><span class="sxs-lookup"><span data-stu-id="8a229-199">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="8a229-200">Aggiungere e rimuovere amministratori in un account OneDrive</span><span class="sxs-lookup"><span data-stu-id="8a229-200">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="8a229-201">Ripristinare un OneDrive eliminato</span><span class="sxs-lookup"><span data-stu-id="8a229-201">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="8a229-202">Conservazione ed eliminazione di OneDrive</span><span class="sxs-lookup"><span data-stu-id="8a229-202">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
