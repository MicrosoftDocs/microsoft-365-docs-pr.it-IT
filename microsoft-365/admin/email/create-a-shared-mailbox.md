---
title: Creazione di una cassetta postale condivisa
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Creare una cassetta postale condivisa consente di affidare a più utenti all'interno dell'azienda la responsabilità di leggere e rispondere ai messaggi di posta elettronica inviati a un unico indirizzo.
ms.openlocfilehash: 35f1de41094c6bf3f806b3e8e01c0a67949c491e
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683248"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="6180a-103">Creare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="6180a-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="6180a-104">Se l'organizzazione utilizza un ambiente Exchange ibrido, è necessario ricorrere all'interfaccia di amministrazione di Exchange per creare e gestire cassette postali condivise.</span><span class="sxs-lookup"><span data-stu-id="6180a-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="6180a-105">Vedere [Creare cassette postali condivise nell'interfaccia di amministrazione di Exchange](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span><span class="sxs-lookup"><span data-stu-id="6180a-105">See [Create shared mailboxes in the Exchange admin center](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)</span></span><br><br>
> <span data-ttu-id="6180a-106">Se non si è sicuri di dover creare una cassetta postale condivisa o un gruppo di Microsoft 365 per Outlook, vedere [Confrontare i gruppi](../create-groups/compare-groups.md) per indicazioni.</span><span class="sxs-lookup"><span data-stu-id="6180a-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="6180a-107">Notare che al momento non è possibile eseguire la migrazione di una cassetta postale condivisa a un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6180a-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="6180a-108">Se si vuole ottenere questa possibilità, inviare commenti e suggerimenti [votando qui](https://go.microsoft.com/fwlink/?linkid=871518).</span><span class="sxs-lookup"><span data-stu-id="6180a-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="6180a-p103">Le cassette postali condivise consentono a un gruppo di persone di monitorare e inviare posta elettronica da un indirizzo di posta elettronica comune, come info@contoso.com. Quando un utente del gruppo risponde a un messaggio inviato alla cassetta postale condivisa, il messaggio di risposta sembrerà inviato dalla cassetta postale condivisa, non dal singolo utente.</span><span class="sxs-lookup"><span data-stu-id="6180a-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="6180a-p104">Le cassette postali condivise includono un calendario condiviso. Sono molte le piccole aziende che trovano utile usare un calendario condiviso come posizione centralizzata in cui tutti possono inserire i propri appuntamenti. Ad esempio, se un'azienda ha 3 persone che effettuano visite presso clienti, tutte e tre possono usare il calendario condiviso per inserire gli appuntamenti. È un modo semplice per tenersi informati sulle reciproche posizioni.</span><span class="sxs-lookup"><span data-stu-id="6180a-p104">Shared mailboxes include a shared calendar. A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments. For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments. This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="6180a-115">Prima di creare una cassetta postale condivisa, leggere [Informazioni sulle cassette postali condivise](about-shared-mailboxes.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="6180a-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="6180a-116">Creare una cassetta postale condivisa e aggiungervi membri</span><span class="sxs-lookup"><span data-stu-id="6180a-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="6180a-117">Effettuare l'accesso con un account amministratore globale o con un account amministratore di Exchange.</span><span class="sxs-lookup"><span data-stu-id="6180a-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="6180a-118">Se viene visualizzato il messaggio "**Non si dispone dell'autorizzazione necessaria per accedere a questa pagina o eseguire questa azione**", non si è amministratori.</span><span class="sxs-lookup"><span data-stu-id="6180a-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="6180a-119">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="6180a-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="6180a-120">Nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=848041) passare alla pagina **Gruppi** \> **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="6180a-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="6180a-121">Nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=850627) passare alla pagina **Gruppi** \> **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="6180a-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="6180a-122">Nella pagina **Cassette postali condivise** selezionare **+ Aggiungi cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="6180a-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="6180a-123">Immettere un nome per la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6180a-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="6180a-124">La procedura guidata sceglie l'indirizzo di posta elettronica, ma è possibile cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="6180a-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Assegnare un nome alla cassetta postale condivisa.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="6180a-126">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6180a-126">Select **Add**.</span></span> <span data-ttu-id="6180a-127">Potrebbero trascorrere alcuni minuti prima che si possa iniziare ad aggiungere membri.</span><span class="sxs-lookup"><span data-stu-id="6180a-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="6180a-128">In **Passaggi successivi** scegliere **Aggiungere membri a questa cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="6180a-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="6180a-129">I membri sono le persone che potranno visualizzare la posta in entrata in questa cassetta postale condivisa e le risposte in uscita.</span><span class="sxs-lookup"><span data-stu-id="6180a-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Selezionare Aggiungi membri](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="6180a-131">Selezionare il pulsante **+ Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="6180a-131">Select the **+Add members** button.</span></span> <span data-ttu-id="6180a-132">Inserire un segno di spunta accanto alle persone a cui si vuole consentire di usare la cassetta postale condivisa, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6180a-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Assegnare membri alla cassetta postale condivisa](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="6180a-134">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="6180a-134">Select **Close**.</span></span>

<span data-ttu-id="6180a-135">Si dispone di una cassetta postale condivisa che include un calendario condiviso.</span><span class="sxs-lookup"><span data-stu-id="6180a-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="6180a-136">Procedere con il passaggio successivo: bloccare l'accesso per l'account della cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6180a-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="which-permissions-should-you-use"></a><span data-ttu-id="6180a-137">Quali autorizzazioni usare?</span><span class="sxs-lookup"><span data-stu-id="6180a-137">Which permissions should you use?</span></span>

<span data-ttu-id="6180a-138">Con una cassetta postale condivisa è possibile usare le autorizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6180a-138">You can use the following permissions with a shared mailbox:</span></span>

- <span data-ttu-id="6180a-139">**Accesso completo**: l'autorizzazione Accesso completo consente all'utente di accedere alla cassetta postale condivisa e agire come proprietario di tale cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="6180a-139">**Full Access**: The Full Access permission lets a user open the shared mailbox and act as the owner of that mailbox.</span></span> <span data-ttu-id="6180a-140">Dopo aver eseguito l'accesso alla cassetta postale condivisa, l'utente può creare voci di calendario, leggere, visualizzare, eliminare e modificare messaggi di posta elettronica e creare attività e contatti.</span><span class="sxs-lookup"><span data-stu-id="6180a-140">After accessing the shared mailbox, a user can create calendar items, read, view, delete, and change email messages, and create tasks and calendar contacts.</span></span> <span data-ttu-id="6180a-141">Un utente con autorizzazione Accesso completo non può tuttavia inviare messaggi di posta elettronica dalla cassetta postale condivisa, a meno che non disponga anche dell'autorizzazione Invia come o Invia per conto di.</span><span class="sxs-lookup"><span data-stu-id="6180a-141">However, a user with Full Access permission can't send email from the shared mailbox unless they also have Send As or Send on Behalf permission.</span></span>

- <span data-ttu-id="6180a-142">**Invia come**: l'autorizzazione Invia come consente a un utente di rappresentare la cassetta postale per l'invio della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6180a-142">**Send As**: The Send As permission lets a user impersonate the shared mailbox when sending mail.</span></span> <span data-ttu-id="6180a-143">Se ad esempio Caterina accede alla cassetta postale condivisa del reparto marketing e invia un messaggio di posta elettronica, questo risulterà inviato dal reparto marketing.</span><span class="sxs-lookup"><span data-stu-id="6180a-143">For example, if Katerina logs into the shared mailbox Marketing Department and sends an email, it will look like the Marketing Department sent the email.</span></span>

- <span data-ttu-id="6180a-144">**Invia per conto di**: l'autorizzazione Invia per conto di consente a un utente di inviare posta elettronica per conto della cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6180a-144">**Send on Behalf**: The Send on Behalf permission lets a user send email on behalf of the shared mailbox.</span></span> <span data-ttu-id="6180a-145">Ad esempio, se Mattia accede alla cassetta postale condivisa Reception 32 e invia un messaggio, questo risulterà inviato da "Mattia per conto di Reception 32".</span><span class="sxs-lookup"><span data-stu-id="6180a-145">For example, if John logs into the shared mailbox Reception Building 32 and sends an email, it will look like the mail was sent by "John on behalf of Reception Building 32".</span></span> <span data-ttu-id="6180a-146">Per concedere l'autorizzazione Invia per conto di, occorre usare il cmdlet **Set-Mailbox** con il parametro _GrantSendonBehalf_.</span><span class="sxs-lookup"><span data-stu-id="6180a-146">You can't use the EAC to grant Send on Behalf permissions, you must use the **Set-Mailbox** cmdlet with the _GrantSendonBehalf_ parameter.</span></span>

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a><span data-ttu-id="6180a-147">Usare l'interfaccia di amministrazione di Exchange per modificare la delega dell'accesso alle cassette postali</span><span class="sxs-lookup"><span data-stu-id="6180a-147">Use the EAC to edit shared mailbox delegation</span></span>

1. <span data-ttu-id="6180a-148">Nell'interfaccia di amministrazione di Exchange accedere a **Destinatari** \> **Condivisi**.</span><span class="sxs-lookup"><span data-stu-id="6180a-148">In the EAC, go to **Recipients** \> **Shared**.</span></span> <span data-ttu-id="6180a-149">Selezionare la cassetta postale condivisa e quindi selezionare **Modifica** ![Icona Modifica](../../media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="6180a-149">Select the shared mailbox, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="6180a-150">Selezionare **Delega cassette postali**.</span><span class="sxs-lookup"><span data-stu-id="6180a-150">Select **Mailbox delegation**.</span></span>

3. <span data-ttu-id="6180a-151">Per concedere o rimuovere le autorizzazioni Accesso completo e Invia come, selezionare **Aggiungi** ![icona Aggiungi](../../media/ITPro-EAC-AddIcon.png) o **Rimuovi** ![icona Rimuovi](../../media/ITPro-EAC-RemoveIcon.gif)e quindi selezionare gli utenti a cui si vogliono concedere o per cui si vogliono rimuovere le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="6180a-151">To grant or remove Full Access and Send As permissions, select **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) and then select the users you want to grant permissions to.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6180a-p115">L'autorizzazione Accesso completo consente a un utente di aprire la cassetta postale, modificare gli elementi in essa contenuti e crearne di nuovi. L'autorizzazione Invia come consente a utenti diversi dal proprietario della cassetta postale di inviare messaggi di posta elettronica dalla cassetta postale condivisa. Entrambe le autorizzazioni sono necessarie per il funzionamento corretto della cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6180a-p115">The Full Access permission allows a user to open the mailbox as well as create and modify items in it. The Send As permission allows anyone other than the mailbox owner to send email from this shared mailbox. Both permissions are required for successful shared mailbox operation.</span></span>

4. <span data-ttu-id="6180a-155">Selezionare **Salva** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6180a-155">Select **Save** to save your changes.</span></span>


## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="6180a-156">Bloccare l'accesso per l'account della cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="6180a-156">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="6180a-157">Ogni cassetta postale condivisa ha un account utente corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6180a-157">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="6180a-158">Anche se non è stata richiesta una password al momento della creazione della cassetta postale condivisa,</span><span class="sxs-lookup"><span data-stu-id="6180a-158">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="6180a-159">l'account dispone di una password, ma è generata dal sistema (sconosciuta).</span><span class="sxs-lookup"><span data-stu-id="6180a-159">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="6180a-160">Non è necessario usare l'account per accedere alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6180a-160">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="6180a-161">Ma cosa succede se un amministratore reimposta semplicemente la password dell'account utente della cassetta postale condivisa,</span><span class="sxs-lookup"><span data-stu-id="6180a-161">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="6180a-162">o se un utente malintenzionato accede alle credenziali dell'account della cassetta postale condivisa?</span><span class="sxs-lookup"><span data-stu-id="6180a-162">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="6180a-163">In questo modo l'account utente potrebbe accedere alla cassetta postale condivisa e inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6180a-163">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="6180a-164">Per evitare questo problema, è necessario bloccare l'accesso per l'account associato alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6180a-164">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6180a-165">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="6180a-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6180a-166">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="6180a-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6180a-167">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="6180a-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
::: moniker-end

1. <span data-ttu-id="6180a-168">Nell'elenco di account utente individuare l'account della cassetta postale condivisa (ad esempio, impostare il filtro su **Utenti senza licenza**).</span><span class="sxs-lookup"><span data-stu-id="6180a-168">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

1. <span data-ttu-id="6180a-169">Selezionare l'utente per aprire il riquadro proprietà e quindi selezionare l'icona **Bloccare l’utente** ![Schermata dell'icona Bloccare l'utente](../../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="6180a-169">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="6180a-170">**Nota**: se l'account è già bloccato, verrà visualizzato **Accesso bloccato** nella parte superiore e sull'icona sarà scritto **Sbloccare l’utente**.</span><span class="sxs-lookup"><span data-stu-id="6180a-170">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

1. <span data-ttu-id="6180a-171">Nel riquadro **Bloccare l'utente?**, selezionare **Blocca l'accesso dell'utente** e quindi selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="6180a-171">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

<span data-ttu-id="6180a-172">Per istruzioni su come bloccare l'accesso per gli account con Azure AD PowerShell (anche per molti account contemporaneamente), vedere [Bloccare gli account utente con Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6180a-172">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="6180a-173">Aggiungere la cassetta postale condivisa in Outlook</span><span class="sxs-lookup"><span data-stu-id="6180a-173">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="6180a-174">Se nell'azienda è abilitata l'impostazione AutoMapping (per impostazione predefinita, è abilitata nella maggior parte dei casi), la cassetta postale condivisa verrà visualizzata nell'app Outlook degli utenti automaticamente dopo la chiusura e il riavvio di Outlook.</span><span class="sxs-lookup"><span data-stu-id="6180a-174">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="6180a-175">L'opzione AutoMapping viene impostata sulla cassetta postale dell'utente, non su quella condivisa.  </span><span class="sxs-lookup"><span data-stu-id="6180a-175">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="6180a-176">Questo significa che se si cerca di usare un gruppo di sicurezza per gestire le autorizzazioni di accesso alla cassetta postale condivisa, AutoMapping non funziona.</span><span class="sxs-lookup"><span data-stu-id="6180a-176">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="6180a-177">Se quindi si vuole usare questa impostazione, occorre assegnare le autorizzazioni in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="6180a-177">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="6180a-178">L’opzione AutoMapping è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6180a-178">Automapping is on by default.</span></span> <span data-ttu-id="6180a-179">Per informazioni su come disattivarla, vedere [Rimuovere AutoMapping per una cassetta postale condivisa](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="6180a-179">To learn how to turn it off, see [Remove automapping for a shared mailbox](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="6180a-180">Per ulteriori informazioni sulle cassette postali condivise in Outlook, vedere:</span><span class="sxs-lookup"><span data-stu-id="6180a-180">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="6180a-181"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Aprire e usare cassette postali condivise in Outlook</a></span><span class="sxs-lookup"><span data-stu-id="6180a-181"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="6180a-182"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Aggiungere una cassetta postale condivisa in Outlook sul Web</a></span><span class="sxs-lookup"><span data-stu-id="6180a-182"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="6180a-183"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Aggiungere una cassetta postale condivisa in Outlook per dispositivi mobili</a></span><span class="sxs-lookup"><span data-stu-id="6180a-183"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="6180a-184"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Aprire una cartella o una cassetta postale condivisa in Outlook per Mac</a></span><span class="sxs-lookup"><span data-stu-id="6180a-184"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="6180a-185"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Aggiungere regole a una cassetta postale condivisa</a></span><span class="sxs-lookup"><span data-stu-id="6180a-185"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Add rules to a shared mailbox</a></span></span>

## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="6180a-186">Usare una cassetta postale condivisa in un dispositivo mobile (telefono o tablet)</span><span class="sxs-lookup"><span data-stu-id="6180a-186">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="6180a-187">È possibile accedere a una cassetta postale condivisa in un dispositivo mobile in due modi:</span><span class="sxs-lookup"><span data-stu-id="6180a-187">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="6180a-188">Aggiungere la cassetta postale condivisa nell'<a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">app Outlook per iOS</a> o nell'<a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">app Outlook per Android per dispositivi mobili</a>.</span><span class="sxs-lookup"><span data-stu-id="6180a-188">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="6180a-189">Per le istruzioni, vedere <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Aggiungere una cassetta postale condivisa in Outlook per dispositivi mobili</a>.</span><span class="sxs-lookup"><span data-stu-id="6180a-189">For instructions, see <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="6180a-190">Aprire il browser, effettuare l'accesso e quindi passare a Outlook sul web.</span><span class="sxs-lookup"><span data-stu-id="6180a-190">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="6180a-191">Da Outlook sul web sarà possibile accedere alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6180a-191">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="6180a-192">Per le istruzioni, vedere <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Aggiungere una cassetta postale condivisa in Outlook sul web</a>.</span><span class="sxs-lookup"><span data-stu-id="6180a-192">For instructions, see <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6180a-193">La cassetta postale condivisa può essere aggiunta solo all'Outlook per iOS o all'app mobile Outlook per Android</span><span class="sxs-lookup"><span data-stu-id="6180a-193">Shared mailbox can only be added to Outlook for iOS app or the Outlook for Android mobile app</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="6180a-194">Usare il calendario condiviso</span><span class="sxs-lookup"><span data-stu-id="6180a-194">Use the shared calendar</span></span>

<span data-ttu-id="6180a-p120">Il calendario della cassetta postale condivisa viene in genere preferito a un calendario di SharePoint per tenere traccia degli appuntamenti e della posizione delle persone. Un calendario condiviso è integrato con Outlook, genera promemoria ed è molto più facile da creare e usare rispetto a un calendario di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6180a-p120">When you created the shared mailbox, you automatically created a shared calendar. We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are. A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="6180a-198">Nell'app Outlook passare alla visualizzazione Calendario e selezionare la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="6180a-198">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="6180a-199">Quando si immette un appuntamento, ogni membro della cassetta postale condivisa potrà vederlo. </span><span class="sxs-lookup"><span data-stu-id="6180a-199">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="6180a-200">Qualsiasi membro della cassetta postale condivisa può creare, visualizzare e gestire gli appuntamenti nel calendario, come gli appuntamenti personali.</span><span class="sxs-lookup"><span data-stu-id="6180a-200">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="6180a-201">Tutti i membri della cassetta postale condivisa possono vedere le modifiche apportate al calendario condiviso.</span><span class="sxs-lookup"><span data-stu-id="6180a-201">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-content"></a><span data-ttu-id="6180a-202">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="6180a-202">Related content</span></span>

<span data-ttu-id="6180a-203">[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="6180a-203">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="6180a-204">[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="6180a-204">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="6180a-205">[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="6180a-205">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="6180a-206">[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="6180a-206">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="6180a-207">[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="6180a-207">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>