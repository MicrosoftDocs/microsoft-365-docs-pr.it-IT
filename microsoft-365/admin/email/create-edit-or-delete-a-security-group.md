---
title: Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Informazioni su come creare, modificare o eliminare un gruppo di sicurezza.
ms.openlocfilehash: 283f1eca7500bfb1d8172657639bbc7cff76906f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400089"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1da5a-103">Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1da5a-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1da5a-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="1da5a-104">The admin center is changing.</span></span> <span data-ttu-id="1da5a-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="1da5a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="1da5a-106">Nella pagina Microsoft 365 **Groups** è possibile creare gruppi di account utente che è possibile utilizzare per assegnare le stesse autorizzazioni in SharePoint Online e CRM online.</span><span class="sxs-lookup"><span data-stu-id="1da5a-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="1da5a-107">Ad esempio, un amministratore può creare un gruppo di sicurezza per consentire a un determinato gruppo di utenti di accedere a un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1da5a-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="1da5a-108">Solo gli amministratori di gestione globale e degli utenti dispongono delle autorizzazioni per creare, modificare o eliminare gruppi di sicurezza. Per ulteriori informazioni sui ruoli di amministratore, vedere [assegnazione di ruoli](../add-users/assign-admin-roles.md)di amministratore.</span><span class="sxs-lookup"><span data-stu-id="1da5a-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="1da5a-109">Sono inoltre disponibili [Gruppi in Exchange Online e SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) che è possibile usare per inviare messaggi di posta elettronica o assegnare autorizzazioni a un gruppo di utenti e [Gruppi in Exchange Online e SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) che consentono di concedere agli utenti i diritti e l'accesso a siti e raccolte siti.</span><span class="sxs-lookup"><span data-stu-id="1da5a-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="1da5a-110">Pianificazione dell'utilizzo delle cassette postali del sito?</span><span class="sxs-lookup"><span data-stu-id="1da5a-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="1da5a-111">Tutti gli utenti aggiunti a un sito di SharePoint tramite un gruppo di sicurezza anziché essere aggiunti singolarmente possono utilizzare solo la cassetta postale del sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1da5a-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="1da5a-112">Questi utenti non saranno in grado di accedere alla cassetta postale del sito da Outlook.</span><span class="sxs-lookup"><span data-stu-id="1da5a-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="1da5a-113">Per ulteriori informazioni, vedere [utilizzare i gruppi di Microsoft 365 anziché le cassette postali del sito](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span><span class="sxs-lookup"><span data-stu-id="1da5a-113">For more information, see [Use Microsoft 365 groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="1da5a-114">Gestire i gruppi di sicurezza nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="1da5a-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="1da5a-115">Aggiungere un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="1da5a-115">Add a security group</span></span>

1. <span data-ttu-id="1da5a-116">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **gruppi**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="1da5a-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="1da5a-117">Nella pagina **gruppi** selezionare **Aggiungi un gruppo**.</span><span class="sxs-lookup"><span data-stu-id="1da5a-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="1da5a-118">Nella pagina **scegliere il tipo di gruppo** scegliere **sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="1da5a-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="1da5a-119">Seguire la procedura per completare la creazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="1da5a-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="1da5a-120">Aggiungere membri a un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="1da5a-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="1da5a-121">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="1da5a-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="1da5a-122">Selezionare il nome del gruppo di sicurezza nella pagina **gruppi** , quindi selezionare **Visualizza tutti e Gestisci membri**nella scheda **membri** .</span><span class="sxs-lookup"><span data-stu-id="1da5a-122">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="1da5a-123">Nel riquadro gruppo, selezionare **Aggiungi membri** e scegliere la persona nell'elenco oppure digitare il nome della persona che si desidera aggiungere nella casella di **ricerca** e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1da5a-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="1da5a-124">Per rimuovere i membri, selezionare la X accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="1da5a-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1da5a-125">Selezionare il nome del gruppo di sicurezza nella pagina **gruppi** e quindi fare clic su **modifica** accanto a **membri**.</span><span class="sxs-lookup"><span data-stu-id="1da5a-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="1da5a-126">Nel riquadro gruppo, selezionare **Aggiungi membri** e scegliere la persona nell'elenco oppure digitare il nome della persona che si desidera aggiungere nella casella di **ricerca** e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1da5a-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="1da5a-127">Per rimuovere i membri, selezionare la X accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="1da5a-127">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="1da5a-128">Selezionare il nome del gruppo di sicurezza nella pagina **gruppi** e quindi fare clic su **modifica** accanto a **membri**.</span><span class="sxs-lookup"><span data-stu-id="1da5a-128">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="1da5a-129">Nel riquadro gruppo, selezionare **Aggiungi membri** e scegliere la persona nell'elenco oppure digitare il nome della persona che si desidera aggiungere nella casella di **ricerca** e quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1da5a-129">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="1da5a-130">Per rimuovere i membri, selezionare la X accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="1da5a-130">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="1da5a-131">Modificare un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="1da5a-131">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="1da5a-132">Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.</span><span class="sxs-lookup"><span data-stu-id="1da5a-132">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="1da5a-133">Nell'interfaccia di amministrazione, andare alla pagina **gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="1da5a-133">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="1da5a-134">Nella pagina **gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="1da5a-134">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="1da5a-135">Nel riquadro Impostazioni, selezionare la scheda **generale** o la scheda **membri** per modificare i dettagli o i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="1da5a-135">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1da5a-136">Nell'interfaccia di amministrazione, andare alla pagina **gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="1da5a-136">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="1da5a-137">Nella pagina **gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="1da5a-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="1da5a-138">Nel riquadro gruppo di sicurezza selezionare **modifica** accanto a **nome** o scheda **membri** per modificare i dettagli o i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="1da5a-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="1da5a-139">Dopo aver apportato le modifiche, selezionare **Salva** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="1da5a-139">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1da5a-140">Nell'interfaccia di amministrazione, andare alla pagina **gruppi** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="1da5a-140">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="1da5a-141">Nella pagina **gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="1da5a-141">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="1da5a-142">Nel riquadro gruppo di sicurezza selezionare **modifica** accanto a **nome** o scheda **membri** per modificare i dettagli o i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="1da5a-142">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="1da5a-143">Dopo aver apportato le modifiche, selezionare **Salva** > **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="1da5a-143">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="1da5a-144">Eliminare un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="1da5a-144">Delete a security group</span></span>

1. <span data-ttu-id="1da5a-145">Nell'interfaccia di amministrazione, andare alla pagina **gruppi**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .</span><span class="sxs-lookup"><span data-stu-id="1da5a-145">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="1da5a-146">Nella pagina **gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="1da5a-146">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="1da5a-147">Selezionare **Elimina gruppo** (icona di wasetbin), quindi confermare selezionando **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="1da5a-147">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="1da5a-148">Selezionare **Chiudi** dopo che il gruppo è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="1da5a-148">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="1da5a-149">Gruppi in Exchange Online e SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1da5a-149">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="1da5a-150">Se si desidera creare gruppi di utenti in modo che sia possibile inviare messaggi di posta elettronica a tutti contemporaneamente, è possibile farlo nell'interfaccia di amministrazione di Exchange accedendo ai **Admin** \> **Exchange** \> gruppi di **destinatari** di Exchange per l'amministratore \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="1da5a-150">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="1da5a-151">Fare quindi clic su **nuovo** ![ Aggiungi ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) e selezionare il tipo di gruppo che si desidera creare:</span><span class="sxs-lookup"><span data-stu-id="1da5a-151">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="1da5a-152">**Gruppo di distribuzione**: viene usato per distribuire messaggi a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="1da5a-152">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="1da5a-153">Viene anche definito un *gruppo di distribuzione abilitato alla posta elettronica*o una *lista di distribuzione*.</span><span class="sxs-lookup"><span data-stu-id="1da5a-153">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="1da5a-154">Per ulteriori informazioni, vedere [Gestione dei gruppi di distribuzione](https://technet.microsoft.com/library/bb124513.aspx).</span><span class="sxs-lookup"><span data-stu-id="1da5a-154">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="1da5a-155">**Gruppo di sicurezza**: può essere usato per distribuire messaggi a un gruppo di utenti oppure per concedere autorizzazioni di accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="1da5a-155">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="1da5a-156">Questo gruppo è anche denominato *gruppo di sicurezza abilitato alla posta elettronica*.</span><span class="sxs-lookup"><span data-stu-id="1da5a-156">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="1da5a-157">Per ulteriori informazioni, vedere [Gestire gruppi di sicurezza abilitati alla posta elettronica](https://technet.microsoft.com/library/bb123521.aspx).</span><span class="sxs-lookup"><span data-stu-id="1da5a-157">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="1da5a-158">**Gruppo di distribuzione dinamico**: un tipo di gruppo di distribuzione la cui lista di destinatari viene ricalcolata ogni volta che si invia un messaggio in base alle condizioni e ai filtri definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1da5a-158">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="1da5a-159">Per ulteriori informazioni, vedere [Gestione dei gruppi di distribuzione dinamici](https://technet.microsoft.com/library/bb123722.aspx).</span><span class="sxs-lookup"><span data-stu-id="1da5a-159">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="1da5a-160">Dopo aver creato i gruppi di distribuzione e i gruppi di sicurezza abilitati alla posta elettronica nell'interfaccia di amministrazione di Exchange, i nomi e gli elenchi di utenti vengono visualizzati nella pagina **gruppi di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="1da5a-160">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="1da5a-161">È possibile eliminare tali gruppi in entrambe le posizioni, ma è possibile modificarli solo nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="1da5a-161">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="1da5a-162">I gruppi di distribuzione dinamici non vengono visualizzati nella pagina **gruppi di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="1da5a-162">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="1da5a-163">I gruppi di SharePoint vengono creati are automaticamente quando si crea una raccolta sito.</span><span class="sxs-lookup"><span data-stu-id="1da5a-163">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="1da5a-164">I gruppi predefiniti usano i livelli di autorizzazione predefiniti di SharePoint, a volte indicati come ruoli di SharePoint, per concedere agli utenti i diritti e l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1da5a-164">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="1da5a-165">Per ulteriori informazioni, vedere [gruppi di SharePoint predefiniti in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="1da5a-165">For more information, see [Default SharePoint groups in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="1da5a-166">In che modo un gruppo di sicurezza è diverso dai gruppi di sicurezza creati in SharePoint?</span><span class="sxs-lookup"><span data-stu-id="1da5a-166">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="1da5a-167">I gruppi di sicurezza possono essere utilizzati con SharePoint, Exchange, MDM, Windows e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="1da5a-167">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="1da5a-168">I gruppi di sicurezza creati in SharePoint vengono riconosciuti solo dalla raccolta siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1da5a-168">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="1da5a-169">È necessario utilizzare I gruppi di sicurezza per garantire la protezione dell'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="1da5a-169">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="1da5a-p111">No. È solo un altro modo di gestire la sicurezza dell'organizzazione. È sempre possibile concedere le autorizzazioni e l'accesso ai siti ai singoli utenti, ma con i gruppi di sicurezza si possono gestire più facilmente gruppi di utenti di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="1da5a-p111">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="1da5a-174">È possibile inviare messaggi di posta elettronica a un gruppo di sicurezza?</span><span class="sxs-lookup"><span data-stu-id="1da5a-174">Can I send email to a security group?</span></span>

<span data-ttu-id="1da5a-175">Sì.</span><span class="sxs-lookup"><span data-stu-id="1da5a-175">Yes.</span></span> <span data-ttu-id="1da5a-176">Tuttavia, se si desidera utilizzare i gruppi per la posta elettronica e la collaborazione, è consigliabile [creare un gruppo di Microsoft 365](../create-groups/create-groups.md) .</span><span class="sxs-lookup"><span data-stu-id="1da5a-176">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
