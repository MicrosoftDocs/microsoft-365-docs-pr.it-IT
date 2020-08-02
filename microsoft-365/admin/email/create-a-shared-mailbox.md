---
title: Creazione di una cassetta postale condivisa
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Creare una cassetta postale condivisa consente di affidare a più utenti all'interno dell'azienda la responsabilità di leggere e rispondere ai messaggi di posta elettronica inviati a un unico indirizzo.
ms.openlocfilehash: 47690e1295b67c01f86429d97e0fc8d82ad58d6f
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529636"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="cbae4-103">Creare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="cbae4-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="cbae4-104">Se l'organizzazione utilizza un ambiente Exchange ibrido, è necessario ricorrere all'interfaccia di amministrazione di Exchange per creare e gestire cassette postali condivise.</span><span class="sxs-lookup"><span data-stu-id="cbae4-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="cbae4-105">Vedere [Creare cassette postali condivise nell'interfaccia di amministrazione di Exchange](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span><span class="sxs-lookup"><span data-stu-id="cbae4-105">See [Create shared mailboxes in the Exchange admin center](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span></span><br><br>
> <span data-ttu-id="cbae4-106">Se non si è sicuri di dover creare una cassetta postale condivisa o un gruppo di Microsoft 365 per Outlook, vedere [Confrontare i gruppi](../create-groups/compare-groups.md) per indicazioni.</span><span class="sxs-lookup"><span data-stu-id="cbae4-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="cbae4-107">Notare che al momento non è possibile eseguire la migrazione di una cassetta postale condivisa a un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cbae4-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="cbae4-108">Se si vuole ottenere questa possibilità, inviare commenti e suggerimenti [votando qui](https://go.microsoft.com/fwlink/?linkid=871518).</span><span class="sxs-lookup"><span data-stu-id="cbae4-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="cbae4-p103">Le cassette postali condivise consentono a un gruppo di persone di monitorare e inviare posta elettronica da un indirizzo di posta elettronica comune, come info@contoso.com. Quando un utente del gruppo risponde a un messaggio inviato alla cassetta postale condivisa, il messaggio di risposta sembrerà inviato dalla cassetta postale condivisa, non dal singolo utente.</span><span class="sxs-lookup"><span data-stu-id="cbae4-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="cbae4-111">Le cassette postali condivise includono un calendario condiviso.</span><span class="sxs-lookup"><span data-stu-id="cbae4-111">Shared mailboxes include a shared calendar.</span></span> <span data-ttu-id="cbae4-112">Sono molte le piccole aziende che trovano utile usare un calendario condiviso come posizione centralizzata in cui tutti possono inserire i propri appuntamenti.</span><span class="sxs-lookup"><span data-stu-id="cbae4-112">A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments.</span></span> <span data-ttu-id="cbae4-113">Ad esempio, se un'azienda ha 3 persone che effettuano visite presso clienti, tutte e tre possono usare il calendario condiviso per immettere gli appuntamenti.</span><span class="sxs-lookup"><span data-stu-id="cbae4-113">For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments.</span></span> <span data-ttu-id="cbae4-114">È un modo semplice per tenersi informati sulle reciproche posizioni.</span><span class="sxs-lookup"><span data-stu-id="cbae4-114">This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="cbae4-115">Prima di creare una cassetta postale condivisa, leggere [Informazioni sulle cassette postali condivise](about-shared-mailboxes.md) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="cbae4-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="cbae4-116">Creare una cassetta postale condivisa e aggiungervi membri</span><span class="sxs-lookup"><span data-stu-id="cbae4-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="cbae4-117">Effettuare l'accesso con un account amministratore globale o con un account amministratore di Exchange.</span><span class="sxs-lookup"><span data-stu-id="cbae4-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="cbae4-118">Se viene visualizzato il messaggio "**Non si dispone dell'autorizzazione necessaria per accedere a questa pagina o eseguire questa azione**", non si è amministratori.</span><span class="sxs-lookup"><span data-stu-id="cbae4-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="cbae4-119">Nell'interfaccia di amministrazione passare alla pagina **Gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Cassette postali condivise</a>.</span><span class="sxs-lookup"><span data-stu-id="cbae4-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="cbae4-120">Nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=848041) passare alla pagina **Gruppi** \> **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="cbae4-121">Nell'[interfaccia di amministrazione](https://go.microsoft.com/fwlink/p/?linkid=850627) passare alla pagina **Gruppi** \> **Cassette postali condivise**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="cbae4-122">Nella pagina **Cassette postali condivise** selezionare **+ Aggiungi cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="cbae4-123">Immettere un nome per la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="cbae4-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="cbae4-124">La procedura guidata sceglie l'indirizzo di posta elettronica, ma è possibile cambiarlo.</span><span class="sxs-lookup"><span data-stu-id="cbae4-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Assegnare un nome alla cassetta postale condivisa.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="cbae4-126">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-126">Select **Add**.</span></span> <span data-ttu-id="cbae4-127">Potrebbero trascorrere alcuni minuti prima che si possa iniziare ad aggiungere membri.</span><span class="sxs-lookup"><span data-stu-id="cbae4-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="cbae4-128">In **Passaggi successivi** scegliere **Aggiungere membri a questa cassetta postale**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="cbae4-129">I membri sono le persone che potranno visualizzare la posta in entrata in questa cassetta postale condivisa e le risposte in uscita.</span><span class="sxs-lookup"><span data-stu-id="cbae4-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Selezionare Aggiungi membri](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="cbae4-131">Selezionare il pulsante **+ Aggiungi membri**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-131">Select the **+Add members** button.</span></span> <span data-ttu-id="cbae4-132">Inserire un segno di spunta accanto alle persone a cui si vuole consentire di usare la cassetta postale condivisa, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Assegnare membri alla cassetta postale condivisa](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="cbae4-134">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-134">Select **Close**.</span></span>

<span data-ttu-id="cbae4-135">Si dispone di una cassetta postale condivisa che include un calendario condiviso.</span><span class="sxs-lookup"><span data-stu-id="cbae4-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="cbae4-136">Procedere con il passaggio successivo: bloccare l'accesso per l'account della cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="cbae4-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="cbae4-137">Bloccare l'accesso per l'account della cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="cbae4-137">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="cbae4-138">Ogni cassetta postale condivisa ha un account utente corrispondente.</span><span class="sxs-lookup"><span data-stu-id="cbae4-138">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="cbae4-139">Anche se non è stata richiesta una password al momento della creazione della cassetta postale condivisa,</span><span class="sxs-lookup"><span data-stu-id="cbae4-139">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="cbae4-140">l'account dispone di una password, ma è generata dal sistema (sconosciuta).</span><span class="sxs-lookup"><span data-stu-id="cbae4-140">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="cbae4-141">Non è necessario usare l'account per accedere alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="cbae4-141">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="cbae4-142">Ma cosa succede se un amministratore reimposta semplicemente la password dell'account utente della cassetta postale condivisa,</span><span class="sxs-lookup"><span data-stu-id="cbae4-142">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="cbae4-143">o se un utente malintenzionato accede alle credenziali dell'account della cassetta postale condivisa?</span><span class="sxs-lookup"><span data-stu-id="cbae4-143">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="cbae4-144">In questo modo l'account utente potrebbe accedere alla cassetta postale condivisa e inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="cbae4-144">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="cbae4-145">Per evitare questo problema, è necessario bloccare l'accesso per l'account associato alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="cbae4-145">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cbae4-146">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="cbae4-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="cbae4-147">Nell'elenco di account utente individuare l'account della cassetta postale condivisa (ad esempio, impostare il filtro su **Utenti senza licenza**).</span><span class="sxs-lookup"><span data-stu-id="cbae4-147">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="cbae4-148">Selezionare l'utente per aprire il riquadro proprietà e quindi selezionare l'icona **Bloccare l’utente** ![Schermata dell'icona Bloccare l'utente](../../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="cbae4-148">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="cbae4-149">**Nota**: se l'account è già bloccato, verrà visualizzato **Accesso bloccato** nella parte superiore e sull'icona sarà scritto **Sbloccare l’utente**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-149">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="cbae4-150">Nel riquadro **Bloccare l'utente?**, selezionare **Blocca l'accesso dell'utente** e quindi selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-150">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cbae4-151">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="cbae4-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="cbae4-152">Nell'elenco di account utente individuare l'account della cassetta postale condivisa (ad esempio, impostare la visualizzazione su **Utenti senza licenza**) e selezionare l’account.</span><span class="sxs-lookup"><span data-stu-id="cbae4-152">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="cbae4-153">Nel riquadro a comparsa Proprietà, selezionare **Blocca l’accesso**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-153">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="cbae4-154">**Nota:** se l'account fosse già bloccato, il pulsante riporterebbe la scritta **Sblocca l’accesso**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-154">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="cbae4-155">Nel riquadro a comparsa **Modifica stato di accesso**, verificare che l'opzione Blocca l'accesso dell'utente sia selezionata, selezionare **Salva** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-155">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cbae4-156">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="cbae4-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="cbae4-157">Nell'elenco di account utente individuare l'account della cassetta postale condivisa (ad esempio, impostare la visualizzazione su **Utenti senza licenza**) e selezionare l’account.</span><span class="sxs-lookup"><span data-stu-id="cbae4-157">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="cbae4-158">Nel riquadro a comparsa Proprietà, selezionare **Blocca l’accesso**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-158">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="cbae4-159">**Nota:** se l'account fosse già bloccato, il pulsante riporterebbe la scritta **Sblocca l’accesso**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-159">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="cbae4-160">Nel riquadro a comparsa **Modifica stato di accesso**, verificare che l'opzione Blocca l'accesso dell'utente sia selezionata, selezionare **Salva** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="cbae4-160">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="cbae4-161">Per istruzioni su come bloccare l'accesso per gli account con Azure AD PowerShell (anche per molti account contemporaneamente), vedere [Bloccare gli account utente con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="cbae4-161">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="cbae4-162">Aggiungere la cassetta postale condivisa in Outlook</span><span class="sxs-lookup"><span data-stu-id="cbae4-162">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="cbae4-163">Se nell'azienda è abilitata l'impostazione AutoMapping (per impostazione predefinita, è abilitata nella maggior parte dei casi), la cassetta postale condivisa verrà visualizzata nell'app Outlook degli utenti automaticamente dopo la chiusura e il riavvio di Outlook.</span><span class="sxs-lookup"><span data-stu-id="cbae4-163">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="cbae4-164">L'opzione AutoMapping viene impostata sulla cassetta postale dell'utente, non su quella condivisa.  </span><span class="sxs-lookup"><span data-stu-id="cbae4-164">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="cbae4-165">Questo significa che se si cerca di usare un gruppo di sicurezza per gestire le autorizzazioni di accesso alla cassetta postale condivisa, AutoMapping non funziona.</span><span class="sxs-lookup"><span data-stu-id="cbae4-165">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="cbae4-166">Se quindi si vuole usare questa impostazione, occorre assegnare le autorizzazioni in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="cbae4-166">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="cbae4-167">L’opzione AutoMapping è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cbae4-167">Automapping is on by default.</span></span> <span data-ttu-id="cbae4-168">Per informazioni su come disattivarla, vedere [Rimuovere AutoMapping per una cassetta postale condivisa](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="cbae4-168">To learn how to turn it off, see [Remove automapping for a shared mailbox](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="cbae4-169">Per ulteriori informazioni sulle cassette postali condivise in Outlook, vedere:</span><span class="sxs-lookup"><span data-stu-id="cbae4-169">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="cbae4-170"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Aprire e usare cassette postali condivise in Outlook</a></span><span class="sxs-lookup"><span data-stu-id="cbae4-170"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="cbae4-171"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Aggiungere una cassetta postale condivisa in Outlook sul Web</a></span><span class="sxs-lookup"><span data-stu-id="cbae4-171"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="cbae4-172"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Aggiungere una cassetta postale condivisa in Outlook per dispositivi mobili</a></span><span class="sxs-lookup"><span data-stu-id="cbae4-172"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="cbae4-173"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Aprire una cartella o una cassetta postale condivisa in Outlook per Mac</a></span><span class="sxs-lookup"><span data-stu-id="cbae4-173"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="cbae4-174"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Aggiungere regole a una cassetta postale condivisa</a></span><span class="sxs-lookup"><span data-stu-id="cbae4-174"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="cbae4-175">Usare una cassetta postale condivisa in un dispositivo mobile (telefono o tablet)</span><span class="sxs-lookup"><span data-stu-id="cbae4-175">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="cbae4-176">È possibile accedere a una cassetta postale condivisa in un dispositivo mobile in due modi:</span><span class="sxs-lookup"><span data-stu-id="cbae4-176">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="cbae4-177">Aggiungere la cassetta postale condivisa nell'<a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">app Outlook per iOS</a> o nell'<a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">app Outlook per Android per dispositivi mobili</a>.</span><span class="sxs-lookup"><span data-stu-id="cbae4-177">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="cbae4-178">Per le istruzioni, vedere <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Aggiungere una cassetta postale condivisa in Outlook per dispositivi mobili</a>.</span><span class="sxs-lookup"><span data-stu-id="cbae4-178">For instructions, see <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="cbae4-179">Aprire il browser, effettuare l'accesso e quindi passare a Outlook sul web.</span><span class="sxs-lookup"><span data-stu-id="cbae4-179">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="cbae4-180">Da Outlook sul web sarà possibile accedere alla cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="cbae4-180">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="cbae4-181">Per le istruzioni, vedere <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Aggiungere una cassetta postale condivisa in Outlook sul web</a>.</span><span class="sxs-lookup"><span data-stu-id="cbae4-181">For instructions, see <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cbae4-182">La cassetta postale condivisa può essere aggiunta solo all'Outlook per iOS o all'app mobile Outlook per Android</span><span class="sxs-lookup"><span data-stu-id="cbae4-182">Shared mailbox can only be added to Outlook for iOS app or the Outlook for Android mobile app</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="cbae4-183">Usare il calendario condiviso</span><span class="sxs-lookup"><span data-stu-id="cbae4-183">Use the shared calendar</span></span>

<span data-ttu-id="cbae4-184">Dopo aver creato la cassetta postale condivisa, viene creato automaticamente un calendario condiviso.</span><span class="sxs-lookup"><span data-stu-id="cbae4-184">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="cbae4-185">Il calendario della cassetta postale condivisa viene in genere preferito a un calendario di SharePoint per tenere traccia degli appuntamenti e della posizione delle persone.</span><span class="sxs-lookup"><span data-stu-id="cbae4-185">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="cbae4-186">Un calendario condiviso è integrato in Outlook ed è molto più facile da usare rispetto a un calendario di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cbae4-186">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="cbae4-187">Nell'app Outlook passare alla visualizzazione Calendario e selezionare la cassetta postale condivisa.</span><span class="sxs-lookup"><span data-stu-id="cbae4-187">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="cbae4-188">Quando si immette un appuntamento, ogni membro della cassetta postale condivisa potrà vederlo. </span><span class="sxs-lookup"><span data-stu-id="cbae4-188">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="cbae4-189">Qualsiasi membro della cassetta postale condivisa può creare, visualizzare e gestire gli appuntamenti nel calendario, come gli appuntamenti personali.</span><span class="sxs-lookup"><span data-stu-id="cbae4-189">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="cbae4-190">Tutti i membri della cassetta postale condivisa possono vedere le modifiche apportate al calendario condiviso.</span><span class="sxs-lookup"><span data-stu-id="cbae4-190">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cbae4-191">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="cbae4-191">Related articles</span></span>

[<span data-ttu-id="cbae4-192">Informazioni sulle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="cbae4-192">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="cbae4-193">Configurare una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="cbae4-193">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="cbae4-194">Convertire una cassetta postale utente in una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="cbae4-194">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="cbae4-195">Rimuovere una licenza da una cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="cbae4-195">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="cbae4-196">Risolvere i problemi relativi alle cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="cbae4-196">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)





