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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Informazioni su come creare, modificare o eliminare un gruppo di sicurezza.
ms.openlocfilehash: 525acc45b293563f58bb9aa12c40bec1438cb055
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393956"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="0e9e5-103">Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e9e5-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="0e9e5-104">Nella pagina Microsoft 365 **gruppi** è possibile creare gruppi di account utente che è possibile utilizzare per assegnare le stesse autorizzazioni in SharePoint Online e CRM Online.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="0e9e5-105">Ad esempio, un amministratore può creare un gruppo di sicurezza per concedere a un determinato gruppo di utenti l'accesso a un SharePoint sito.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="0e9e5-106">Solo gli amministratori globali e di gestione degli utenti dispongono delle autorizzazioni per creare, modificare o eliminare gruppi di sicurezza. per ulteriori informazioni sui ruoli di amministratore, vedere [Assigning admin roles](../add-users/assign-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="0e9e5-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="0e9e5-107">Sono inoltre disponibili [Gruppi in Exchange Online e SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) che è possibile usare per inviare messaggi di posta elettronica o assegnare autorizzazioni a un gruppo di utenti e [Gruppi in Exchange Online e SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) che consentono di concedere agli utenti i diritti e l'accesso a siti e raccolte siti.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="0e9e5-108">Pianificazione dell'utilizzo delle cassette postali del sito</span><span class="sxs-lookup"><span data-stu-id="0e9e5-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="0e9e5-109">Tutti gli utenti aggiunti a un sito SharePoint tramite un gruppo di sicurezza anziché essere aggiunti singolarmente possono utilizzare solo la cassetta postale del sito da SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="0e9e5-110">Questi utenti non saranno in grado di accedere alla cassetta postale del sito da Outlook.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="0e9e5-111">Per ulteriori informazioni, vedere [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span><span class="sxs-lookup"><span data-stu-id="0e9e5-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="0e9e5-112">Gestire i gruppi di sicurezza nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="0e9e5-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="0e9e5-113">Aggiungere un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0e9e5-113">Add a security group</span></span>

1. <span data-ttu-id="0e9e5-114">Nella pagina interfaccia di amministrazione di Microsoft 365 gruppi passare alla **pagina**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi.</a></span><span class="sxs-lookup"><span data-stu-id="0e9e5-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="0e9e5-115">Nella pagina **Gruppi** selezionare **Aggiungi un gruppo.**</span><span class="sxs-lookup"><span data-stu-id="0e9e5-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="0e9e5-116">Nella pagina **Scegliere un tipo di gruppo** scegliere **Sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="0e9e5-117">Seguire i passaggi per completare la creazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="0e9e5-118">Aggiungere membri a un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0e9e5-118">Add members to a security group</span></span>
    
1. <span data-ttu-id="0e9e5-119">Selezionare il nome del gruppo di sicurezza **nella** pagina Gruppi e nella **scheda** Membri selezionare Visualizza tutti e **gestisci membri**.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="0e9e5-120">Nel riquadro del  gruppo selezionare Aggiungi membri e scegliere la persona dall'elenco o digitare il nome della persona che si desidera aggiungere nella casella Di **ricerca** e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="0e9e5-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="0e9e5-121">Per rimuovere i membri, selezionare la X accanto al nome.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-121">To remove members, select the X next to their name.</span></span> 
  
### <a name="edit-a-security-group"></a><span data-ttu-id="0e9e5-122">Modificare un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0e9e5-122">Edit a security group</span></span>

1. <span data-ttu-id="0e9e5-123">Nell'interfaccia di amministrazione passare alla **pagina** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi di</a> gruppi.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="0e9e5-124">Nella pagina **Gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-124">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0e9e5-125">Nel riquadro delle impostazioni selezionare la **scheda Generale** o **Membri** per modificare i dettagli del gruppo o i membri.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-125">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

### <a name="delete-a-security-group"></a><span data-ttu-id="0e9e5-126">Eliminare un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="0e9e5-126">Delete a security group</span></span>

1. <span data-ttu-id="0e9e5-127">Nell'interfaccia di amministrazione passare alla **pagina**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppi di</a> gruppi.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-127">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="0e9e5-128">Nella pagina **Gruppi** selezionare il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-128">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="0e9e5-129">Selezionare **Elimina gruppo** (icona wasetbin), quindi confermare selezionando **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-129">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="0e9e5-130">Selezionare **Chiudi** dopo l'eliminazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-130">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="0e9e5-131">Gruppi in Exchange Online e SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0e9e5-131">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="0e9e5-132">Se si desidera creare gruppi di utenti in modo da poter inviare messaggi di posta elettronica contemporaneamente, è possibile farlo nell'interfaccia di amministrazione di Exchange andando a **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-132">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="0e9e5-133">Quindi, selezionare **Nuovo** ![ aggiungi e selezionare il tipo di gruppo che si ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) desidera creare:</span><span class="sxs-lookup"><span data-stu-id="0e9e5-133">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="0e9e5-134">**Gruppo di distribuzione**: viene usato per distribuire messaggi a un gruppo di utenti.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-134">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="0e9e5-135">È anche denominato gruppo di distribuzione abilitato *alla* posta o lista *di distribuzione.*</span><span class="sxs-lookup"><span data-stu-id="0e9e5-135">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="0e9e5-136">Per ulteriori informazioni, vedere [Gestione dei gruppi di distribuzione](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="0e9e5-136">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="0e9e5-137">**Gruppo di sicurezza**: può essere usato per distribuire messaggi a un gruppo di utenti oppure per concedere autorizzazioni di accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-137">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="0e9e5-138">Questo gruppo è anche denominato gruppo *di sicurezza abilitato alla posta .*</span><span class="sxs-lookup"><span data-stu-id="0e9e5-138">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="0e9e5-139">Per ulteriori informazioni, vedere [Gestire gruppi di sicurezza abilitati alla posta elettronica](/Exchange/recipients/mail-enabled-security-groups).</span><span class="sxs-lookup"><span data-stu-id="0e9e5-139">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="0e9e5-140">**Gruppo di distribuzione dinamico**: un tipo di gruppo di distribuzione la cui lista di destinatari viene ricalcolata ogni volta che si invia un messaggio in base alle condizioni e ai filtri definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-140">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="0e9e5-141">Per ulteriori informazioni, vedere [Gestione dei gruppi di distribuzione dinamici](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span><span class="sxs-lookup"><span data-stu-id="0e9e5-141">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="0e9e5-142">Dopo aver creato i gruppi di distribuzione e i gruppi di sicurezza abilitati alla posta elettronica nell'interfaccia di amministrazione di Exchange, i relativi nomi e gli elenchi di utenti vengono visualizzati nella **pagina Gruppi di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-142">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="0e9e5-143">È possibile eliminare tali gruppi in entrambe le posizioni, ma è possibile modificarli solo nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-143">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="0e9e5-144">I gruppi di distribuzione dinamici non vengono visualizzati nella **pagina Gruppi di** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-144">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="0e9e5-145">I gruppi di SharePoint vengono creati are automaticamente quando si crea una raccolta sito.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-145">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="0e9e5-146">I gruppi predefiniti usano i livelli di autorizzazione predefiniti di SharePoint, a volte indicati come ruoli di SharePoint, per concedere agli utenti i diritti e l'accesso.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-146">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="0e9e5-147">Per ulteriori informazioni, vedere [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="0e9e5-147">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="0e9e5-148">In che modo un gruppo di sicurezza è diverso dai gruppi di sicurezza creati in SharePoint?</span><span class="sxs-lookup"><span data-stu-id="0e9e5-148">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="0e9e5-149">I gruppi di sicurezza possono essere usati con SharePoint, Exchange, MDM, Windows e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-149">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="0e9e5-150">I gruppi di sicurezza creati in SharePoint vengono riconosciuti solo dalla raccolta siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-150">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="0e9e5-151">È necessario utilizzare i gruppi di sicurezza per garantire la protezione dell'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="0e9e5-151">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="0e9e5-p110">No. È solo un altro modo di gestire la sicurezza dell'organizzazione. È sempre possibile concedere le autorizzazioni e l'accesso ai siti ai singoli utenti, ma con i gruppi di sicurezza si possono gestire più facilmente gruppi di utenti di dimensioni maggiori.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="0e9e5-156">È possibile inviare messaggi di posta elettronica a un gruppo di sicurezza?</span><span class="sxs-lookup"><span data-stu-id="0e9e5-156">Can I send email to a security group?</span></span>

<span data-ttu-id="0e9e5-157">Sì.</span><span class="sxs-lookup"><span data-stu-id="0e9e5-157">Yes.</span></span> <span data-ttu-id="0e9e5-158">Tuttavia, se si desidera utilizzare i gruppi per la posta elettronica e la collaborazione, è consigliabile creare un Microsoft 365 [gruppo.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="0e9e5-158">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 

## <a name="related-content"></a><span data-ttu-id="0e9e5-159">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="0e9e5-159">Related content</span></span>

<span data-ttu-id="0e9e5-160">[Creare un gruppo nel interfaccia di amministrazione di Microsoft 365](../create-groups/create-groups.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="0e9e5-160">[Create a group in the Microsoft 365 admin center](../create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="0e9e5-161">[Spiegazione di Microsoft 365 gruppi agli utenti](../create-groups/explain-groups-knowledge-worker.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="0e9e5-161">[Explaining Microsoft 365 Groups to your users](../create-groups/explain-groups-knowledge-worker.md) (article)</span></span>\
<span data-ttu-id="0e9e5-162">[Gestire un gruppo nell'interfaccia di amministrazione di Microsoft 365](../create-groups/manage-groups.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="0e9e5-162">[Manage a group in the Microsoft 365 admin center](../create-groups/manage-groups.md) (article)</span></span>