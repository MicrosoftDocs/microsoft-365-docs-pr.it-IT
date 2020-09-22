---
title: Gestire i gruppi di ruoli in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Gli amministratori possono imparare a assegnare o rimuovere le autorizzazioni nell'interfaccia di amministrazione di Exchange (EAC) in Exchange Online Protection.
ms.openlocfilehash: fb1e0979b77c38d852f35817e01135af888eac68
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201902"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="586c6-103">Gestire i gruppi di ruoli in Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="586c6-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="586c6-104">Nelle organizzazioni standalone di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) per aggiungere utenti ai gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="586c6-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="586c6-105">L'aggiunta di un utente a un gruppo di ruoli consente alle autorizzazioni degli utenti di eseguire attività amministrative specifiche.</span><span class="sxs-lookup"><span data-stu-id="586c6-105">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="586c6-106">È inoltre possibile rimuovere gli utenti dai gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="586c6-106">You can also remove users from role groups.</span></span>

<span data-ttu-id="586c6-107">Per ulteriori informazioni sui ruoli e sui gruppi di ruolo, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="586c6-107">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="586c6-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="586c6-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="586c6-109">Per aprire l'interfaccia di amministrazione di Exchange (EAC), vedere interfaccia [di amministrazione di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="586c6-109">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="586c6-110">Per aprire PowerShell EOP autonomo, vedere [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="586c6-110">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="586c6-111">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="586c6-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="586c6-112">In particolare, è necessario il ruolo di gestione dei ruoli, assegnato al gruppo di ruoli OrganizationManagement (Global Admins) per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="586c6-112">Specifically, you need the Role Management role, which is assigned to the OrganizationManagement (global admins) role group by default.</span></span> <span data-ttu-id="586c6-113">Per ulteriori informazioni, vedere [autorizzazioni in EOP autonomo](feature-permissions-in-eop.md) e [utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="586c6-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="586c6-114">Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="586c6-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="586c6-115">Problemi?</span><span class="sxs-lookup"><span data-stu-id="586c6-115">Having problems?</span></span> <span data-ttu-id="586c6-116">Chiedere assistenza nel forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="586c6-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="586c6-117">Utilizzo dell'interfaccia di amministrazione di Exchange per gestire gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="586c6-117">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="586c6-118">Utilizzo dell'interfaccia di amministrazione di Exchange per visualizzare gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="586c6-118">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="586c6-119">Nell'interfaccia di amministrazione di Exchange, accedere ai ruoli di amministratore **delle autorizzazioni** \> **Admin roles**.</span><span class="sxs-lookup"><span data-stu-id="586c6-119">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="586c6-120">Qui sono elencati tutti i gruppi di ruoli nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="586c6-120">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="586c6-121">Selezionare un gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="586c6-121">Select a role group.</span></span> <span data-ttu-id="586c6-122">Nel riquadro dei dettagli vengono visualizzati il **nome**, la **Descrizione**, i **ruoli assegnati**e **gestiti dal** gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="586c6-122">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="586c6-123">È inoltre possibile visualizzare queste informazioni facendo clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="586c6-123">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="586c6-124">Utilizzo dell'interfaccia di amministrazione di Exchange per creare gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="586c6-124">Use the EAC to create role groups</span></span>

<span data-ttu-id="586c6-125">Quando si crea un nuovo gruppo di ruoli, è possibile configurare tutte le impostazioni (durante la creazione del gruppo o dopo).</span><span class="sxs-lookup"><span data-stu-id="586c6-125">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="586c6-126">In alternativa, è possibile copiare un gruppo di ruoli esistente e modificarlo.</span><span class="sxs-lookup"><span data-stu-id="586c6-126">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="586c6-127">Nell'interfaccia di amministrazione di Exchange, accedere ai ruoli di amministratore **delle autorizzazioni** \> **Admin roles**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="586c6-127">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="586c6-128">**Creare manualmente un nuovo gruppo di ruoli**: fare clic su **Aggiungi** ![ icona Aggiungi ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="586c6-128">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="586c6-129">**Copia di un gruppo di ruoli esistente**: selezionare il gruppo di ruoli che si desidera copiare e quindi fare clic su **copia** copia ![ icona ](../../media/ITPro-EAC-CopyIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="586c6-129">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="586c6-130">Nella finestra **nuovo gruppo di ruoli** che viene visualizzata, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="586c6-130">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="586c6-131">**Nome**: immettere un nome univoco per il gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="586c6-131">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="586c6-132">**Descrizione**: immettere una descrizione facoltativa per il gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="586c6-132">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="586c6-133">**Ruoli**: fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) o **rimuovere** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) per selezionare o modificare i ruoli assegnati al gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="586c6-133">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="586c6-134">**Membri**: fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) o **rimuovere** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) per modificare l'appartenenza a un gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="586c6-134">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![ITPro-EAC-RemoveIcon.gif](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="586c6-135">Al termine, fare clic su **Salva** per creare il gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="586c6-135">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="586c6-136">Utilizzo dell'interfaccia di amministrazione di Exchange per modificare gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="586c6-136">Use the EAC to modify role groups</span></span>

<span data-ttu-id="586c6-137">Nell'interfaccia di amministrazione di Exchange, andare a ruoli di amministratore **delle autorizzazioni** \> **Admin roles**, selezionare il gruppo di ruoli che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="586c6-137">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="586c6-138">Le stesse opzioni sono disponibili quando si modificano i gruppi di ruoli come quando si creano gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="586c6-138">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="586c6-139">È possibile:</span><span class="sxs-lookup"><span data-stu-id="586c6-139">You can:</span></span>

- <span data-ttu-id="586c6-140">Modificare il nome e la descrizione.</span><span class="sxs-lookup"><span data-stu-id="586c6-140">Change the name and description.</span></span>

- <span data-ttu-id="586c6-141">Aggiungere e rimuovere i ruoli di gestione (creare o rimuovere le assegnazioni di ruolo).</span><span class="sxs-lookup"><span data-stu-id="586c6-141">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="586c6-142">Aggiungere e rimuovere membri.</span><span class="sxs-lookup"><span data-stu-id="586c6-142">Add and remove members.</span></span>

<span data-ttu-id="586c6-143">**Nota**: alcuni gruppi di ruoli, ad esempio Gestione organizzazione, limitano i ruoli che è possibile rimuovere dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="586c6-143">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="586c6-144">Utilizzo dell'interfaccia di amministrazione di Exchange modificare l'elenco dei membri nei gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="586c6-144">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="586c6-145">Nell'interfaccia di amministrazione di Exchange, andare a ruoli di amministratore **delle autorizzazioni** \> **Admin roles**, selezionare il gruppo di ruoli che si desidera modificare, quindi fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="586c6-145">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="586c6-146">Nella pagina delle proprietà del gruppo di ruoli che si apre, nella sezione **membri** , eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="586c6-146">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="586c6-147">Fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="586c6-147">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="586c6-148">Nella pagina che viene visualizzata, individuare l'utente che Wou desidera aggiungere, quindi fare clic su **Add->**.</span><span class="sxs-lookup"><span data-stu-id="586c6-148">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="586c6-149">Selezionare utenti e fare clic su **Add->** molte volte, se necessario.</span><span class="sxs-lookup"><span data-stu-id="586c6-149">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="586c6-150">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="586c6-150">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="586c6-151">Selezionare gli utenti che si desidera rimuovere, quindi fare clic su **Rimuovi** ![ icona Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="586c6-151">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="586c6-152">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="586c6-152">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="586c6-153">Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="586c6-153">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="586c6-154">Utilizzo dell'interfaccia di amministrazione di Exchange per rimuovere gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="586c6-154">Use the EAC to remove role groups</span></span>

<span data-ttu-id="586c6-155">Non è possibile rimuovere i gruppi di ruoli incorporati, ma possono essere rimossi i gruppi di ruoli personalizzati che sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="586c6-155">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="586c6-156">Nell'interfaccia di amministrazione di Exchange, accedere ai ruoli di amministratore **delle autorizzazioni** \> **Admin roles**.</span><span class="sxs-lookup"><span data-stu-id="586c6-156">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="586c6-157">Selezionare il gruppo di ruoli che si desidera rimuovere, quindi fare clic su **Elimina** ![ icona di eliminazione ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="586c6-157">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="586c6-158">Fare clic su **Sì** nella finestra di conferma che viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="586c6-158">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="586c6-159">Utilizzo di PowerShell per gestire i gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="586c6-159">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="586c6-160">Utilizzo di PowerShell EOP autonomo per visualizzare i gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="586c6-160">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="586c6-161">Per visualizzare un gruppo di ruoli, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="586c6-161">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="586c6-162">In questo esempio viene restituito un elenco riepilogativo di tutti i gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="586c6-162">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="586c6-163">In questo esempio vengono restituite informazioni dettagliate per il gruppo di ruoli denominato Recipient Administrators.</span><span class="sxs-lookup"><span data-stu-id="586c6-163">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="586c6-164">In questo esempio vengono restituiti tutti i gruppi di ruoli in cui l'utente Julia è membro.</span><span class="sxs-lookup"><span data-stu-id="586c6-164">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="586c6-165">È necessario utilizzare il valore distinto (DN) per Julia, che può essere trovato eseguendo il comando: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="586c6-165">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="586c6-166">Per ulteriori informazioni sulla sintassi e sui parametri, vedere [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="586c6-166">For detailed syntax and parameter information, see [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="586c6-167">Utilizzo di PowerShell EOP autonomo per creare gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="586c6-167">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="586c6-168">Quando si crea un nuovo gruppo di ruoli, è possibile configurare tutte le impostazioni manualmente (durante la creazione del gruppo o dopo).</span><span class="sxs-lookup"><span data-stu-id="586c6-168">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="586c6-169">In alternativa, è possibile copiare un gruppo di ruoli esistente e modificarlo.</span><span class="sxs-lookup"><span data-stu-id="586c6-169">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="586c6-170">Per creare manualmente un nuovo gruppo di ruoli, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="586c6-170">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="586c6-171">Il parametro _roles_ consente di specificare i ruoli di gestione da assegnare al gruppo di ruoli utilizzando la sintassi seguente `"Role1","Role1",..."RoleN"` .</span><span class="sxs-lookup"><span data-stu-id="586c6-171">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="586c6-172">È possibile visualizzare i ruoli disponibili utilizzando il cmdlet **Get-ManagementRole** .</span><span class="sxs-lookup"><span data-stu-id="586c6-172">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="586c6-173">Il parametro _Members_ consente di specificare i membri del gruppo di ruoli utilizzando la sintassi seguente: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="586c6-173">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="586c6-174">È possibile specificare gli utenti, i gruppi di protezione universale abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).</span><span class="sxs-lookup"><span data-stu-id="586c6-174">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="586c6-175">In questo esempio viene creato un nuovo gruppo di ruoli denominato "Limited Recipient Management" con le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="586c6-175">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="586c6-176">Il ruolo Destinatari di posta viene assegnato al gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="586c6-176">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="586c6-177">Gli utenti Kim e Martin vengono aggiunti come membri.</span><span class="sxs-lookup"><span data-stu-id="586c6-177">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="586c6-178">Per copiare un gruppo di ruoli esistente, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="586c6-178">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="586c6-179">Archiviare il gruppo di ruoli che si desidera copiare in una variabile utilizzando la seguente sintassi:</span><span class="sxs-lookup"><span data-stu-id="586c6-179">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="586c6-180">Creare il nuovo gruppo di ruoli utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="586c6-180">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="586c6-181">Il parametro _Members_ consente di specificare i membri del gruppo di ruoli utilizzando la sintassi seguente: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="586c6-181">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="586c6-182">È possibile specificare gli utenti, i gruppi di protezione universale abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).</span><span class="sxs-lookup"><span data-stu-id="586c6-182">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="586c6-183">In questo esempio il gruppo di ruoli Gestione organizzazione viene copiato nel nuovo gruppo di ruoli denominato "Gestione organizzazione limitata".</span><span class="sxs-lookup"><span data-stu-id="586c6-183">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="586c6-184">I membri del gruppo di ruoli sono Isabelle, Carter e Lukas.</span><span class="sxs-lookup"><span data-stu-id="586c6-184">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="586c6-185">Per informazioni dettagliate sulla sintassi e sui parametri, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="586c6-185">For detailed syntax and parameter information, [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="586c6-186">Utilizzo di EOP autonomo PowerShell modificare l'elenco dei membri nei gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="586c6-186">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="586c6-187">I cmdlet **Add-RoleGroupMember** e **Remove-RoleGroupMember** aggiungono o rimuovono singoli membri uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="586c6-187">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="586c6-188">Il cmdlet **Update-RoleGroupMember** è in grado di sostituire o modificare l'elenco dei membri esistente.</span><span class="sxs-lookup"><span data-stu-id="586c6-188">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="586c6-189">I membri di un gruppo di ruoli possono essere utenti, gruppi di protezione universali abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).</span><span class="sxs-lookup"><span data-stu-id="586c6-189">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="586c6-190">Per modificare i membri di un gruppo di ruoli, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="586c6-190">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="586c6-191">Per _sostituire_ l'elenco esistente di membri con i valori specificati, utilizzare la sintassi seguente: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="586c6-191">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="586c6-192">Per _modificare in modo selettivo_ l'elenco di membri esistente, utilizzare la sintassi seguente: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="586c6-192">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="586c6-193">In questo esempio vengono sostituiti tutti i membri correnti del gruppo di ruolo Help Desk con gli utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="586c6-193">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="586c6-194">Questo esempio aggiunge Daigoro Akai e rimuove Valeria Barrio dall'elenco dei membri del gruppo di ruolo Help desk.</span><span class="sxs-lookup"><span data-stu-id="586c6-194">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="586c6-195">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="586c6-195">For detailed syntax and parameter information, see [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="586c6-196">Utilizzo di PowerShell EOP autonomo per rimuovere i gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="586c6-196">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="586c6-197">Non è possibile rimuovere i gruppi di ruoli incorporati, ma possono essere rimossi i gruppi di ruoli personalizzati che sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="586c6-197">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="586c6-198">Per rimuovere un gruppo di ruoli personalizzato, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="586c6-198">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="586c6-199">Questo esempio rimuove il gruppo di ruolo Formazione degli amministratori.</span><span class="sxs-lookup"><span data-stu-id="586c6-199">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="586c6-200">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="586c6-200">For detailed syntax and parameter information, see [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="586c6-201">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="586c6-201">How do you know these procedures worked?</span></span>

<span data-ttu-id="586c6-202">Per verificare la corretta copia di un gruppo di ruoli, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="586c6-202">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="586c6-203">Nell'interfaccia di amministrazione di Exchange, accedere ai ruoli di amministratore **delle autorizzazioni** \> **Admin roles**e verificare che il gruppo di ruoli sia elencato (o non elencato).</span><span class="sxs-lookup"><span data-stu-id="586c6-203">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="586c6-204">Selezionare il gruppo di ruoli e verificare le impostazioni nel riquadro dei dettagli oppure fare clic su **modifica** ![ icona modifica ](../../media/ITPro-EAC-EditIcon.png) per verificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="586c6-204">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="586c6-205">In Exchange Online PowerShell, sostituire \<Role Group Name\> con il nome del gruppo di ruolo ed eseguire il comando riportato di seguito per verificare che il gruppo di ruoli esista (o non esista) e verificare le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="586c6-205">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
