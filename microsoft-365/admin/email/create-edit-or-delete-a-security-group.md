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
ms.openlocfilehash: df3d8fde0c487663237b3858aa0bf049ba4db045
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114046"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="29ffd-103">Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29ffd-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="29ffd-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="29ffd-104">The admin center is changing.</span></span> <span data-ttu-id="29ffd-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="29ffd-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="29ffd-106">Nella pagina Gruppi di  Microsoft 365 è possibile creare gruppi di account utente che è possibile utilizzare per assegnare le stesse autorizzazioni in SharePoint Online e CRM Online.</span><span class="sxs-lookup"><span data-stu-id="29ffd-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="29ffd-107">Un amministratore può ad esempio creare un gruppo di sicurezza per concedere a un determinato gruppo di utenti l'accesso a un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="29ffd-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="29ffd-108">Solo gli amministratori della gestione globale e degli utenti dispongono delle autorizzazioni per creare, modificare o eliminare gruppi di sicurezza. Per ulteriori informazioni sui ruoli di amministratore, vedere [Assegnazione dei ruoli di amministratore.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="29ffd-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="29ffd-109">Sono inoltre disponibili [Gruppi in Exchange Online e SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) che è possibile usare per inviare messaggi di posta elettronica o assegnare autorizzazioni a un gruppo di utenti e [Gruppi in Exchange Online e SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) che consentono di concedere agli utenti i diritti e l'accesso a siti e raccolte siti.</span><span class="sxs-lookup"><span data-stu-id="29ffd-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="29ffd-110">Pianificazione dell'utilizzo delle cassette postali del sito</span><span class="sxs-lookup"><span data-stu-id="29ffd-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="29ffd-111">Tutti gli utenti aggiunti a un sito di SharePoint tramite un gruppo di sicurezza anziché essere aggiunti singolarmente possono utilizzare solo la cassetta postale del sito da SharePoint.</span><span class="sxs-lookup"><span data-stu-id="29ffd-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="29ffd-112">Questi utenti non potranno accedere alla cassetta postale del sito da Outlook.</span><span class="sxs-lookup"><span data-stu-id="29ffd-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="29ffd-113">Per ulteriori informazioni, vedere [Use Microsoft 365 Groups instead of Site Mailboxes.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)</span><span class="sxs-lookup"><span data-stu-id="29ffd-113">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="29ffd-114">Gestire i gruppi di sicurezza nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="29ffd-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="29ffd-115">Aggiungere un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="29ffd-115">Add a security group</span></span>

1. <span data-ttu-id="29ffd-116">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi di</a> gruppi.</span><span class="sxs-lookup"><span data-stu-id="29ffd-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="29ffd-117">Nella pagina **Gruppi** selezionare **Aggiungi un gruppo.**</span><span class="sxs-lookup"><span data-stu-id="29ffd-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="29ffd-118">Nella pagina **Scegliere un tipo di gruppo** scegliere **Sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="29ffd-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="29ffd-119">Seguire i passaggi per completare la creazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="29ffd-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="29ffd-120">Aggiungere membri a un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="29ffd-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="29ffd-121">Selezionare il nome del gruppo di sicurezza nella **pagina** Gruppi e nella **scheda** Membri selezionare Visualizza tutti e **gestisci membri.**</span><span class="sxs-lookup"><span data-stu-id="29ffd-121">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="29ffd-122">Nel riquadro del  gruppo selezionare Aggiungi membri e scegliere la persona nell'elenco oppure  digitare il nome della persona che si desidera aggiungere nella casella di ricerca e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="29ffd-122">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="29ffd-123">Per rimuovere i membri, selezionare la X accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="29ffd-123">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="29ffd-124">Selezionare il nome del gruppo di sicurezza nella **pagina** Gruppi e quindi selezionare **Modifica** accanto a **Membri.**</span><span class="sxs-lookup"><span data-stu-id="29ffd-124">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="29ffd-125">Nel riquadro del  gruppo selezionare Aggiungi membri e scegliere la persona nell'elenco oppure  digitare il nome della persona che si desidera aggiungere nella casella di ricerca e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="29ffd-125">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="29ffd-126">Per rimuovere i membri, selezionare la X accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="29ffd-126">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="29ffd-127">Selezionare il nome del gruppo di sicurezza nella **pagina** Gruppi e quindi selezionare **Modifica** accanto a **Membri.**</span><span class="sxs-lookup"><span data-stu-id="29ffd-127">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="29ffd-128">Nel riquadro del  gruppo selezionare Aggiungi membri e scegliere la persona nell'elenco oppure  digitare il nome della persona che si desidera aggiungere nella casella di ricerca e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="29ffd-128">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="29ffd-129">Per rimuovere i membri, selezionare la X accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="29ffd-129">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="29ffd-130">Modificare un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="29ffd-130">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="29ffd-131">Nell'interfaccia di amministrazione  passare alla pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi di</a> gruppi.</span><span class="sxs-lookup"><span data-stu-id="29ffd-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="29ffd-132">Nella pagina **Gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="29ffd-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="29ffd-133">Nel riquadro delle impostazioni selezionare la **scheda Generale** o **Membri** per modificare i dettagli del gruppo o i membri.</span><span class="sxs-lookup"><span data-stu-id="29ffd-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="29ffd-134"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Gruppi** \> **di** gruppi.</span><span class="sxs-lookup"><span data-stu-id="29ffd-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="29ffd-135">Nella pagina **Gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="29ffd-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="29ffd-136">Nel riquadro del gruppo di sicurezza selezionare **Modifica** accanto alla scheda **Nome** o **Membri** per modificare i dettagli o i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="29ffd-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="29ffd-137">Dopo aver apportato le modifiche, selezionare **Salva** \> **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="29ffd-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="29ffd-138"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Gruppi** \> **di** gruppi.</span><span class="sxs-lookup"><span data-stu-id="29ffd-138">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="29ffd-139">Nella pagina **Gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="29ffd-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="29ffd-140">Nel riquadro del gruppo di sicurezza selezionare **Modifica** accanto alla scheda **Nome** o **Membri** per modificare i dettagli o i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="29ffd-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="29ffd-141">Dopo aver apportato le modifiche, selezionare **Salva** > **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="29ffd-141">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="29ffd-142">Eliminare un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="29ffd-142">Delete a security group</span></span>

1. <span data-ttu-id="29ffd-143">Nell'interfaccia di amministrazione passare alla pagina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi di</a> gruppi.</span><span class="sxs-lookup"><span data-stu-id="29ffd-143">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="29ffd-144">Nella pagina **Gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="29ffd-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="29ffd-145">Selezionare **Elimina gruppo** (icona wasetbin), quindi confermare selezionando **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="29ffd-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="29ffd-146">Selezionare **Chiudi** dopo l'eliminazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="29ffd-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="29ffd-147">Gruppi in Exchange Online e SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="29ffd-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="29ffd-148">Se si desidera creare gruppi di utenti in modo da poter inviare messaggi di posta elettronica a tutti contemporaneamente, è possibile farlo nell'interfaccia di amministrazione di Exchange andando a **Admin** \> **Exchange** \> **Recipients** \> **Groups.**</span><span class="sxs-lookup"><span data-stu-id="29ffd-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="29ffd-149">Successivamente, selezionare **Nuovo** ![ aggiungi e selezionare il tipo di gruppo che si ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) desidera creare:</span><span class="sxs-lookup"><span data-stu-id="29ffd-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="29ffd-150">**Gruppo di distribuzione**: viene usato per distribuire messaggi a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="29ffd-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="29ffd-151">Viene anche chiamato gruppo di distribuzione abilitato *alla* posta o lista *di distribuzione.*</span><span class="sxs-lookup"><span data-stu-id="29ffd-151">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="29ffd-152">Per ulteriori informazioni, vedere [Gestione dei gruppi di distribuzione](https://technet.microsoft.com/library/bb124513.aspx).</span><span class="sxs-lookup"><span data-stu-id="29ffd-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="29ffd-153">**Gruppo di sicurezza**: può essere usato per distribuire messaggi a un gruppo di utenti oppure per concedere autorizzazioni di accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="29ffd-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="29ffd-154">Questo gruppo è anche denominato gruppo *di sicurezza abilitato alla posta elettronica.*</span><span class="sxs-lookup"><span data-stu-id="29ffd-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="29ffd-155">Per ulteriori informazioni, vedere [Gestire gruppi di sicurezza abilitati alla posta elettronica](https://technet.microsoft.com/library/bb123521.aspx).</span><span class="sxs-lookup"><span data-stu-id="29ffd-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="29ffd-156">**Gruppo di distribuzione dinamico**: un tipo di gruppo di distribuzione la cui lista di destinatari viene ricalcolata ogni volta che si invia un messaggio in base alle condizioni e ai filtri definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="29ffd-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="29ffd-157">Per ulteriori informazioni, vedere [Gestione dei gruppi di distribuzione dinamici](https://technet.microsoft.com/library/bb123722.aspx).</span><span class="sxs-lookup"><span data-stu-id="29ffd-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="29ffd-158">Dopo aver creato i gruppi di distribuzione e i gruppi di sicurezza abilitati alla posta elettronica nell'interfaccia di amministrazione di Exchange, i relativi nomi e gli elenchi di utenti vengono visualizzati nella **pagina Gruppi di** protezione.</span><span class="sxs-lookup"><span data-stu-id="29ffd-158">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="29ffd-159">È possibile eliminare tali gruppi in entrambe le posizioni, ma è possibile modificarli solo nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="29ffd-159">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="29ffd-160">I gruppi di distribuzione dinamici non vengono visualizzati nella **pagina Gruppi di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="29ffd-160">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="29ffd-161">I gruppi di SharePoint vengono creati are automaticamente quando si crea una raccolta sito.</span><span class="sxs-lookup"><span data-stu-id="29ffd-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="29ffd-162">I gruppi predefiniti usano i livelli di autorizzazione predefiniti di SharePoint, a volte indicati come ruoli di SharePoint, per concedere agli utenti i diritti e l'accesso.</span><span class="sxs-lookup"><span data-stu-id="29ffd-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="29ffd-163">Per ulteriori informazioni, vedere [Gruppi di SharePoint predefiniti in SharePoint Online.](https://docs.microsoft.com/sharepoint/default-sharepoint-groups)</span><span class="sxs-lookup"><span data-stu-id="29ffd-163">For more information, see [Default SharePoint groups in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="29ffd-164">In che modo un gruppo di sicurezza è diverso dai gruppi di sicurezza creati in SharePoint?</span><span class="sxs-lookup"><span data-stu-id="29ffd-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="29ffd-165">I gruppi di sicurezza possono essere usati con SharePoint, Exchange, MDM, Windows e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="29ffd-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="29ffd-166">I gruppi di sicurezza creati in SharePoint vengono riconosciuti solo dalla raccolta siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="29ffd-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="29ffd-167">È necessario utilizzare i gruppi di sicurezza per garantire la sicurezza dell'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="29ffd-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="29ffd-p111">No. È solo un altro modo di gestire la sicurezza dell'organizzazione. È sempre possibile concedere le autorizzazioni e l'accesso ai siti ai singoli utenti, ma con i gruppi di sicurezza si possono gestire più facilmente gruppi di utenti di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="29ffd-p111">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="29ffd-172">È possibile inviare messaggi di posta elettronica a un gruppo di sicurezza?</span><span class="sxs-lookup"><span data-stu-id="29ffd-172">Can I send email to a security group?</span></span>

<span data-ttu-id="29ffd-173">Sì.</span><span class="sxs-lookup"><span data-stu-id="29ffd-173">Yes.</span></span> <span data-ttu-id="29ffd-174">Tuttavia, se si desidera usare i gruppi per la posta elettronica e la collaborazione, è consigliabile creare invece un gruppo di [Microsoft 365.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="29ffd-174">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
