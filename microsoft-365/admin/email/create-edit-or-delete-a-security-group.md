---
title: Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Informazioni su come creare, modificare o eliminare un gruppo di sicurezza.
ms.openlocfilehash: 03e391727f9a61b1fc8e819e92d5a119017c38e0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579339"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="4ac67-103">Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4ac67-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="4ac67-104">Nella pagina Gruppi di  Microsoft 365 è possibile creare gruppi di account utente che è possibile utilizzare per assegnare le stesse autorizzazioni in SharePoint Online e CRM Online.</span><span class="sxs-lookup"><span data-stu-id="4ac67-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="4ac67-105">Ad esempio, un amministratore può creare un gruppo di sicurezza per concedere a un determinato gruppo di utenti l'accesso a un sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4ac67-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="4ac67-106">Solo gli amministratori globali e di gestione degli utenti dispongono delle autorizzazioni per creare, modificare o eliminare gruppi di sicurezza. per ulteriori informazioni sui ruoli di amministratore, vedere [Assigning admin roles](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="4ac67-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="4ac67-107">Sono inoltre disponibili [Gruppi in Exchange Online e SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) che è possibile usare per inviare messaggi di posta elettronica o assegnare autorizzazioni a un gruppo di utenti e [Gruppi in Exchange Online e SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) che consentono di concedere agli utenti i diritti e l'accesso a siti e raccolte siti.</span><span class="sxs-lookup"><span data-stu-id="4ac67-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="4ac67-108">Pianificazione dell'utilizzo delle cassette postali del sito</span><span class="sxs-lookup"><span data-stu-id="4ac67-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="4ac67-109">Tutti gli utenti aggiunti a un sito di SharePoint tramite un gruppo di sicurezza anziché essere aggiunti singolarmente possono utilizzare solo la cassetta postale del sito da SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4ac67-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="4ac67-110">Questi utenti non saranno in grado di accedere alla cassetta postale del sito da Outlook.</span><span class="sxs-lookup"><span data-stu-id="4ac67-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="4ac67-111">Per ulteriori informazioni, vedere [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span><span class="sxs-lookup"><span data-stu-id="4ac67-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="4ac67-112">Gestire i gruppi di sicurezza nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="4ac67-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="4ac67-113">Aggiungere un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="4ac67-113">Add a security group</span></span>

1. <span data-ttu-id="4ac67-114">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi di</a> gruppi.</span><span class="sxs-lookup"><span data-stu-id="4ac67-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="4ac67-115">Nella pagina **Gruppi** selezionare **Aggiungi un gruppo.**</span><span class="sxs-lookup"><span data-stu-id="4ac67-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="4ac67-116">Nella pagina **Scegliere un tipo di gruppo** scegliere **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="4ac67-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="4ac67-117">Seguire i passaggi per completare la creazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4ac67-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="4ac67-118">Aggiungere membri a un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="4ac67-118">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="4ac67-119">Selezionare il nome del gruppo di sicurezza **nella** pagina Gruppi e nella **scheda** Membri selezionare Visualizza tutti e **gestisci membri**.</span><span class="sxs-lookup"><span data-stu-id="4ac67-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="4ac67-120">Nel riquadro del  gruppo selezionare Aggiungi membri e scegliere la persona dall'elenco o digitare il nome della persona che si desidera aggiungere nella casella Di **ricerca** e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="4ac67-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="4ac67-121">Per rimuovere i membri, selezionare la X accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="4ac67-121">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4ac67-122">Selezionare il nome del gruppo di sicurezza nella **pagina** Gruppi e quindi selezionare **Modifica** accanto a **Membri**.</span><span class="sxs-lookup"><span data-stu-id="4ac67-122">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="4ac67-123">Nel riquadro del  gruppo selezionare Aggiungi membri e scegliere la persona dall'elenco o digitare il nome della persona che si desidera aggiungere nella casella Di **ricerca** e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="4ac67-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="4ac67-124">Per rimuovere i membri, selezionare la X accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="4ac67-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="4ac67-125">Selezionare il nome del gruppo di sicurezza nella **pagina** Gruppi e quindi selezionare **Modifica** accanto a **Membri**.</span><span class="sxs-lookup"><span data-stu-id="4ac67-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="4ac67-126">Nel riquadro del  gruppo selezionare Aggiungi membri e scegliere la persona dall'elenco o digitare il nome della persona che si desidera aggiungere nella casella Di **ricerca** e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="4ac67-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="4ac67-127">Per rimuovere i membri, selezionare la X accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="4ac67-127">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="4ac67-128">Modificare un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="4ac67-128">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4ac67-129">Nell'interfaccia di amministrazione passare alla **pagina** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi di</a> gruppi.</span><span class="sxs-lookup"><span data-stu-id="4ac67-129">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="4ac67-130">Nella pagina **Gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4ac67-130">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="4ac67-131">Nel riquadro delle impostazioni selezionare la **scheda Generale** o **Membri** per modificare i dettagli del gruppo o i membri.</span><span class="sxs-lookup"><span data-stu-id="4ac67-131">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4ac67-132"><a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Gruppi** \> **di** gruppi.</span><span class="sxs-lookup"><span data-stu-id="4ac67-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="4ac67-133">Nella pagina **Gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4ac67-133">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="4ac67-134">Nel riquadro del gruppo di sicurezza selezionare **Modifica** accanto alla scheda **Nome** o **Membri** per modificare i dettagli o i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4ac67-134">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="4ac67-135">Dopo aver apportato le modifiche, selezionare **Salva** \> **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="4ac67-135">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4ac67-136"><a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Nell'interfaccia di amministrazione</a>passare alla pagina **Gruppi** \> **di** gruppi.</span><span class="sxs-lookup"><span data-stu-id="4ac67-136">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="4ac67-137">Nella pagina **Gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4ac67-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="4ac67-138">Nel riquadro del gruppo di sicurezza selezionare **Modifica** accanto alla scheda **Nome** o **Membri** per modificare i dettagli o i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4ac67-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="4ac67-139">Dopo aver apportato le modifiche, selezionare **Salva** > **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="4ac67-139">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="4ac67-140">Eliminare un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="4ac67-140">Delete a security group</span></span>

1. <span data-ttu-id="4ac67-141">Nell'interfaccia di amministrazione passare alla **pagina**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi di</a> gruppi.</span><span class="sxs-lookup"><span data-stu-id="4ac67-141">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="4ac67-142">Nella pagina **Gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4ac67-142">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="4ac67-143">Selezionare **Elimina gruppo** (icona wasetbin), quindi confermare selezionando **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="4ac67-143">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="4ac67-144">Selezionare **Chiudi** dopo l'eliminazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4ac67-144">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="4ac67-145">Gruppi in Exchange Online e SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4ac67-145">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="4ac67-146">Se si desidera creare gruppi di utenti in modo da poter inviare messaggi di posta elettronica a tutti contemporaneamente, è possibile farlo nell'interfaccia di amministrazione di Exchange andando a **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="4ac67-146">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="4ac67-147">Quindi, selezionare **Nuovo** ![ aggiungi e selezionare il tipo di gruppo che si ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) desidera creare:</span><span class="sxs-lookup"><span data-stu-id="4ac67-147">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="4ac67-148">**Gruppo di distribuzione**: viene usato per distribuire messaggi a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="4ac67-148">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="4ac67-149">È anche denominato gruppo di distribuzione abilitato *alla* posta o lista *di distribuzione.*</span><span class="sxs-lookup"><span data-stu-id="4ac67-149">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="4ac67-150">Per ulteriori informazioni, vedere [Gestione dei gruppi di distribuzione](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="4ac67-150">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="4ac67-151">**Gruppo di sicurezza**: può essere usato per distribuire messaggi a un gruppo di utenti oppure per concedere autorizzazioni di accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="4ac67-151">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="4ac67-152">Questo gruppo è anche denominato gruppo *di sicurezza abilitato alla posta .*</span><span class="sxs-lookup"><span data-stu-id="4ac67-152">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="4ac67-153">Per ulteriori informazioni, vedere [Gestire gruppi di sicurezza abilitati alla posta elettronica](/Exchange/recipients/mail-enabled-security-groups).</span><span class="sxs-lookup"><span data-stu-id="4ac67-153">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="4ac67-154">**Gruppo di distribuzione dinamico**: un tipo di gruppo di distribuzione la cui lista di destinatari viene ricalcolata ogni volta che si invia un messaggio in base alle condizioni e ai filtri definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4ac67-154">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="4ac67-155">Per ulteriori informazioni, vedere [Gestione dei gruppi di distribuzione dinamici](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="4ac67-155">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="4ac67-156">Dopo aver creato i gruppi di distribuzione e i gruppi di sicurezza abilitati alla posta elettronica nell'interfaccia di amministrazione di Exchange, i relativi nomi e gli elenchi di utenti vengono visualizzati nella **pagina Gruppi di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4ac67-156">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="4ac67-157">È possibile eliminare tali gruppi in entrambe le posizioni, ma è possibile modificarli solo nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="4ac67-157">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="4ac67-158">I gruppi di distribuzione dinamici non vengono visualizzati nella **pagina Gruppi di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="4ac67-158">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="4ac67-159">I gruppi di SharePoint vengono creati are automaticamente quando si crea una raccolta sito.</span><span class="sxs-lookup"><span data-stu-id="4ac67-159">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="4ac67-160">I gruppi predefiniti usano i livelli di autorizzazione predefiniti di SharePoint, a volte indicati come ruoli di SharePoint, per concedere agli utenti i diritti e l'accesso.</span><span class="sxs-lookup"><span data-stu-id="4ac67-160">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="4ac67-161">Per ulteriori informazioni, vedere [Gruppi di SharePoint predefiniti in SharePoint Online.](/sharepoint/default-sharepoint-groups)</span><span class="sxs-lookup"><span data-stu-id="4ac67-161">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="4ac67-162">In che modo un gruppo di sicurezza è diverso dai gruppi di sicurezza creati in SharePoint?</span><span class="sxs-lookup"><span data-stu-id="4ac67-162">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="4ac67-163">I gruppi di sicurezza possono essere usati con SharePoint, Exchange, MDM, Windows e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="4ac67-163">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="4ac67-164">I gruppi di sicurezza creati in SharePoint vengono riconosciuti solo dalla raccolta siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4ac67-164">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="4ac67-165">È necessario utilizzare i gruppi di sicurezza per garantire la protezione dell'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="4ac67-165">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="4ac67-p110">No. È solo un altro modo di gestire la sicurezza dell'organizzazione. È sempre possibile concedere le autorizzazioni e l'accesso ai siti ai singoli utenti, ma con i gruppi di sicurezza si possono gestire più facilmente gruppi di utenti di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="4ac67-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="4ac67-170">È possibile inviare messaggi di posta elettronica a un gruppo di sicurezza?</span><span class="sxs-lookup"><span data-stu-id="4ac67-170">Can I send email to a security group?</span></span>

<span data-ttu-id="4ac67-171">Sì.</span><span class="sxs-lookup"><span data-stu-id="4ac67-171">Yes.</span></span> <span data-ttu-id="4ac67-172">Tuttavia, se si desidera utilizzare i gruppi per la posta elettronica e la collaborazione, è consigliabile creare un gruppo [di Microsoft 365.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4ac67-172">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
