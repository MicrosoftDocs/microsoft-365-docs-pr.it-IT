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
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Gli amministratori possono imparare ad assegnare o rimuovere autorizzazioni nell'interfaccia di amministrazione di Exchange (EAC) in Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e712c47d49508934ec7dd2438beff00eb6e1a20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926881"
---
# <a name="manage-role-groups-in-standalone-eop"></a><span data-ttu-id="9aa7f-103">Gestire i gruppi di ruoli in Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="9aa7f-103">Manage role groups in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9aa7f-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="9aa7f-104">**Applies to**</span></span>
-  [<span data-ttu-id="9aa7f-105">Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="9aa7f-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="9aa7f-106">Nelle organizzazioni autonome di Exchange Online Protection (EOP) senza cassette postali di Exchange Online, è possibile utilizzare l'interfaccia di amministrazione di Exchange (EAC) per aggiungere utenti ai gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) to add users to role groups.</span></span> <span data-ttu-id="9aa7f-107">L'aggiunta di un utente a un gruppo di ruoli concede all'utente le autorizzazioni per eseguire attività di amministrazione specifiche.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-107">Adding a users to a role group gives the user permissions to do specific admin tasks.</span></span> <span data-ttu-id="9aa7f-108">È inoltre possibile rimuovere utenti dai gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-108">You can also remove users from role groups.</span></span>

<span data-ttu-id="9aa7f-109">Per ulteriori informazioni sui ruoli e sui gruppi di ruoli, vedere [Autorizzazioni in EOP autonomo.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="9aa7f-109">For more information about roles and role groups, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9aa7f-110">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="9aa7f-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9aa7f-111">Per aprire l'interfaccia di amministrazione di Exchange ( EAC), vedere Interfaccia di amministrazione [di Exchange in EOP autonomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-111">To open the Exchange admin center (EAC), see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="9aa7f-112">Per aprire PowerShell EOP autonomo, vedere [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-112">To open standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9aa7f-113">Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-113">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="9aa7f-114">In particolare, è necessario **il ruolo Gestione** ruoli, assegnato al gruppo di ruoli **Gestione** organizzazione per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-114">Specifically, you need the **Role Management** role, which is assigned to the **Organization Management** role group by default.</span></span> <span data-ttu-id="9aa7f-115">Per ulteriori informazioni, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md) e [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-115">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="9aa7f-116">Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo articolo, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di [Exchange in Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="9aa7f-116">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="9aa7f-117">Problemi?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-117">Having problems?</span></span> <span data-ttu-id="9aa7f-118">Chiedere assistenza nel forum [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-118">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-manage-role-groups"></a><span data-ttu-id="9aa7f-119">Utilizzo dell'interfaccia di amministrazione di Exchange per gestire i gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="9aa7f-119">Use the EAC to manage role groups</span></span>

### <a name="use-the-eac-to-view-role-groups"></a><span data-ttu-id="9aa7f-120">Utilizzo dell'interfaccia di amministrazione di Exchange per visualizzare i gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="9aa7f-120">Use the EAC to view role groups</span></span>

1. <span data-ttu-id="9aa7f-121">Nell'interfaccia di amministrazione di Exchange, accedere a **Autorizzazioni** \> **Ruoli di amministratore**.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-121">In the EAC, go to **Permissions** \> **Admin roles**.</span></span> <span data-ttu-id="9aa7f-122">Qui sono elencati tutti i gruppi di ruoli nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-122">All of the role groups in your organization are listed here.</span></span>

2. <span data-ttu-id="9aa7f-123">Selezionare un gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-123">Select a role group.</span></span> <span data-ttu-id="9aa7f-124">Nel riquadro Dettagli vengono visualizzati **i campi Nome,** **Descrizione,** **Ruoli assegnati** e **Gestito dal** gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-124">The Details pane shows the **Name**, **Description**, **Assigned roles**, and **Managed by** of the role group.</span></span> <span data-ttu-id="9aa7f-125">È inoltre possibile visualizzare queste informazioni facendo clic su **Modifica** ![ icona ](../../media/ITPro-EAC-EditIcon.png) Modifica.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-125">You can also see this information by clicking **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

### <a name="use-the-eac-to-create-role-groups"></a><span data-ttu-id="9aa7f-126">Utilizzo dell'interfaccia di amministrazione di Exchange per creare gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="9aa7f-126">Use the EAC to create role groups</span></span>

<span data-ttu-id="9aa7f-127">Quando si crea un nuovo gruppo di ruoli, è possibile configurare tutte le impostazioni manualmente (durante la creazione del gruppo o dopo).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-127">When you create a new role group, you can configure all of the settings yourself (during the creation of the group or after).</span></span> <span data-ttu-id="9aa7f-128">In caso contrario, è possibile copiare un gruppo di ruoli esistente e modificarlo.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-128">Or, you can copy an existing role group and modify it.</span></span>

1. <span data-ttu-id="9aa7f-129">Nell'interfaccia di amministrazione di Exchange, accedere **a Autorizzazioni** Ruoli \> **di amministratore** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-129">In the EAC, go to **Permissions** \> **Admin roles**, and then do one of the following steps:</span></span>

   - <span data-ttu-id="9aa7f-130">**Creare manualmente un nuovo gruppo di ruoli**: fare clic su **Aggiungi** Icona ![ Aggiungi ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9aa7f-130">**Manually create a new role group**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

   - <span data-ttu-id="9aa7f-131">**Copiare un gruppo di ruoli esistente**: selezionare il gruppo di ruoli che si desidera copiare e quindi fare clic su **Copia** ![ icona ](../../media/ITPro-EAC-CopyIcon.png) Copia.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-131">**Copy an existing role group**: Select the role group that you want to copy and then click **Copy** ![Copy icon](../../media/ITPro-EAC-CopyIcon.png).</span></span>

2. <span data-ttu-id="9aa7f-132">Nella finestra **Nuovo gruppo di** ruoli visualizzata configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-132">In the **New role group** window that appears, configure the following settings:</span></span>

    - <span data-ttu-id="9aa7f-133">**Nome**: immettere un nome univoco per il gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-133">**Name**: Enter a unique name for the role group.</span></span>

    - <span data-ttu-id="9aa7f-134">**Descrizione:** immettere una descrizione facoltativa per il gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-134">**Description**: Enter an optional description for the role group.</span></span>

    - <span data-ttu-id="9aa7f-135">**Ruoli**: **fare clic su** Aggiungi icona Aggiungi o Rimuovi rimuovi per selezionare o modificare i ruoli assegnati al gruppo di ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) ruoli.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-135">**Roles**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to select or modify the roles that are assigned to the role group.</span></span>

    - <span data-ttu-id="9aa7f-136">**Membri**: fare clic **su Aggiungi** icona Aggiungi ![ o ](../../media/ITPro-EAC-AddIcon.png) **Rimuovi** icona Rimuovi per ![ modificare ](../../media/ITPro-EAC-RemoveIcon.gif) l'appartenenza al gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-136">**Members**: Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) to modify the role group membership.</span></span>

3. <span data-ttu-id="9aa7f-137">Al termine, fare clic su **Salva** per creare il gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-137">When you're finished, click **Save** to create the role group.</span></span>

### <a name="use-the-eac-to-modify-role-groups"></a><span data-ttu-id="9aa7f-138">Modifica dei gruppi di ruoli tramite EAC</span><span class="sxs-lookup"><span data-stu-id="9aa7f-138">Use the EAC to modify role groups</span></span>

<span data-ttu-id="9aa7f-139">Nell'interfaccia di amministrazione di Exchange, accedere a **Autorizzazioni** \> **Ruoli di amministratore,** selezionare il gruppo di ruoli che si desidera modificare e quindi fare clic su **Modifica** Icona ![ Modifica ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9aa7f-139">In the EAC, go to **Permissions** \> **Admin roles**, select the role group you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

<span data-ttu-id="9aa7f-140">Le stesse opzioni sono disponibili quando si modificano i gruppi di ruoli come quando si creano gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-140">The same options are available when you modify role groups as when you create role groups.</span></span> <span data-ttu-id="9aa7f-141">È possibile:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-141">You can:</span></span>

- <span data-ttu-id="9aa7f-142">Modificare il nome e la descrizione.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-142">Change the name and description.</span></span>

- <span data-ttu-id="9aa7f-143">Aggiungere e rimuovere ruoli di gestione (creare o rimuovere assegnazioni di ruolo).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-143">Add and remove management roles (create or remove role assignments).</span></span>

- <span data-ttu-id="9aa7f-144">Aggiungere e rimuovere membri.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-144">Add and remove members.</span></span>

<span data-ttu-id="9aa7f-145">**Nota:** alcuni gruppi di ruoli ,ad esempio Gestione organizzazione, limitano i ruoli che è possibile rimuovere dal gruppo.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-145">**Note**: Some role groups (for example, Organization Management) restrict the roles that you can remove from group.</span></span>

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="9aa7f-146">Utilizzo dell'interfaccia di amministrazione di Exchange per modificare l'elenco dei membri nei gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="9aa7f-146">Use the EAC modify the list of members in role groups</span></span>

1. <span data-ttu-id="9aa7f-147">Nell'interfaccia di amministrazione di Exchange, accedere a **Autorizzazioni** Ruoli di amministratore, selezionare il gruppo di ruoli che si desidera modificare e quindi fare \> clic su **Modifica** ![ Icona ](../../media/ITPro-EAC-EditIcon.png) Modifica.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-147">In the EAC, go to **Permissions** \> **Admin roles**, select the role group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="9aa7f-148">Nella pagina delle proprietà del gruppo di ruoli visualizzata, nella **sezione Membri,** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-148">In the role group properties page that opens, in the **Members** section, do either of the following steps:</span></span>

   - <span data-ttu-id="9aa7f-149">Fare **clic su** Aggiungi Icona Aggiungi ![ ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="9aa7f-149">Click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="9aa7f-150">Nella pagina visualizzata individuare l'utente che si desidera aggiungere e quindi fare clic **su aggiungi ->**.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-150">In the page that appears, find the user that wou want to add, and then click **add ->**.</span></span> <span data-ttu-id="9aa7f-151">Selezionare gli utenti e **fare clic su aggiungi ->** più volte in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-151">Select users and click **add ->** many times as necessary.</span></span> <span data-ttu-id="9aa7f-152">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-152">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="9aa7f-153">Selezionare gli utenti che si desidera rimuovere e quindi fare clic su **Rimuovi Icona** ![ Rimuovi ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="9aa7f-153">Select the users that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="9aa7f-154">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-154">When you're finished, click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9aa7f-155">Dopo aver aggiunto o rimosso membri dal gruppo di ruoli, è possibile che gli utenti debbano disconnettersi e, successivamente, accedere nuovamente per visualizzare la modifica nei diritti amministrativi.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-155">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>

### <a name="use-the-eac-to-remove-role-groups"></a><span data-ttu-id="9aa7f-156">Rimozione dei gruppi di ruoli tramite EAC</span><span class="sxs-lookup"><span data-stu-id="9aa7f-156">Use the EAC to remove role groups</span></span>

<span data-ttu-id="9aa7f-157">Non è possibile rimuovere i gruppi di ruoli predefiniti, ma è possibile rimuovere i gruppi di ruoli personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-157">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

1. <span data-ttu-id="9aa7f-158">Nell'interfaccia di amministrazione di Exchange, accedere a **Autorizzazioni** \> **Ruoli di amministratore**.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-158">In the EAC, go to **Permissions** \> **Admin roles**.</span></span>

2. <span data-ttu-id="9aa7f-159">Selezionare il gruppo di ruoli che si desidera rimuovere e quindi fare clic su **Elimina Icona** ![ ](../../media/ITPro-EAC-DeleteIcon.png) Elimina.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-159">Select the role group you want to remove and then click **Delete** ![Delete icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

3. <span data-ttu-id="9aa7f-160">Fare **clic su** Sì nella finestra di conferma visualizzata.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-160">Click **Yes** in the confirmation window that appears.</span></span>

## <a name="use-powershell-to-manage-role-groups"></a><span data-ttu-id="9aa7f-161">Utilizzare PowerShell per gestire i gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="9aa7f-161">Use PowerShell to manage role groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a><span data-ttu-id="9aa7f-162">Usare PowerShell EOP autonomo per visualizzare i gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="9aa7f-162">Use standalone EOP PowerShell to view role groups</span></span>

<span data-ttu-id="9aa7f-163">Per visualizzare un gruppo di ruoli, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-163">To view a role group, use the following syntax:</span></span>

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

<span data-ttu-id="9aa7f-164">In questo esempio viene restituito un elenco riepilogativo di tutti i gruppi di ruoli.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-164">This example returns a summary list of all role groups.</span></span>

```PowerShell
Get-RoleGroup
```

<span data-ttu-id="9aa7f-165">In questo esempio vengono restituite informazioni dettagliate per il gruppo di ruoli denominato Recipient Administrators.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-165">This example returns detailed information for the role group named Recipient Administrators.</span></span>

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

<span data-ttu-id="9aa7f-166">In questo esempio vengono restituiti tutti i gruppi di ruoli in cui l'utente Julia è membro.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-166">This example returns all role groups where the user Julia is a member.</span></span> <span data-ttu-id="9aa7f-167">È necessario utilizzare il valore DistinguishedName (DN) per Julia, che è possibile trovare eseguendo il comando: `Get-User -Identity Julia | Format-List DistinguishedName` .</span><span class="sxs-lookup"><span data-stu-id="9aa7f-167">You need to use the DistinguishedName (DN) value for Julia, which you can find by running the command: `Get-User -Identity Julia | Format-List DistinguishedName`.</span></span>

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

<span data-ttu-id="9aa7f-168">Per ulteriori informazioni sulla sintassi e sui parametri, vedere [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-168">For detailed syntax and parameter information, see [Get-RoleGroup](/powershell/module/exchange/Get-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a><span data-ttu-id="9aa7f-169">Usare PowerShell EOP autonomo per creare gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="9aa7f-169">Use standalone EOP PowerShell to create role groups</span></span>

<span data-ttu-id="9aa7f-170">Quando si crea un nuovo gruppo di ruoli, è possibile configurare tutte le impostazioni manualmente (durante la creazione del gruppo o dopo).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-170">When you create a new role group, you can configure all of the settings manually (during the creation of the group or after).</span></span> <span data-ttu-id="9aa7f-171">In caso contrario, è possibile copiare un gruppo di ruoli esistente e modificarlo.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-171">Or, you can copy an existing role group and modify it.</span></span>

- <span data-ttu-id="9aa7f-172">Per creare manualmente un nuovo gruppo di ruoli, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-172">To manually create a new role group, use the following syntax:</span></span>

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - <span data-ttu-id="9aa7f-173">Il _parametro Roles_ consente di specificare i ruoli di gestione da assegnare al gruppo di ruoli utilizzando la sintassi `"Role1","Role1",..."RoleN"` seguente.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-173">The _Roles_ parameter specifies the management roles to assign to the role group by using the following syntax `"Role1","Role1",..."RoleN"`.</span></span> <span data-ttu-id="9aa7f-174">È possibile visualizzare i ruoli disponibili utilizzando il cmdlet **Get-ManagementRole.**</span><span class="sxs-lookup"><span data-stu-id="9aa7f-174">You can see the available roles by using the **Get-ManagementRole** cmdlet.</span></span>

  - <span data-ttu-id="9aa7f-175">Il _parametro Members_ consente di specificare i membri del gruppo di ruoli utilizzando la sintassi seguente: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="9aa7f-175">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="9aa7f-176">È possibile specificare utenti, gruppi di protezione universale abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-176">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

  <span data-ttu-id="9aa7f-177">In questo esempio viene creato un nuovo gruppo di ruoli denominato "Limited Recipient Management" con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-177">This example creates a new role group named "Limited Recipient Management" with the following settings:</span></span>

  - <span data-ttu-id="9aa7f-178">Il ruolo Destinatari di posta viene assegnato al gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-178">The Mail Recipients role is assigned to the role group.</span></span>

  - <span data-ttu-id="9aa7f-179">Gli utenti Kim e Martin vengono aggiunti come membri.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-179">The users Kim and Martin are added as members.</span></span>

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- <span data-ttu-id="9aa7f-180">Per copiare un gruppo di ruoli esistente, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-180">To copy an existing role group, do the following steps:</span></span>

  1. <span data-ttu-id="9aa7f-181">Archiviare il gruppo di ruoli che si desidera copiare in una variabile utilizzando la seguente sintassi:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-181">Store the role group that you want to copy in a variable using the following syntax:</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. <span data-ttu-id="9aa7f-182">Creare il nuovo gruppo di ruoli utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-182">Create the new role group using the following syntax:</span></span>

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     <span data-ttu-id="9aa7f-183">Il _parametro Members_ consente di specificare i membri del gruppo di ruoli utilizzando la sintassi seguente: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="9aa7f-183">The _Members_ parameter specifies the members of the role group by using the following syntax: `"Member1","Member2",..."MemberN"`.</span></span> <span data-ttu-id="9aa7f-184">È possibile specificare utenti, gruppi di protezione universale abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-184">You can specify users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

     <span data-ttu-id="9aa7f-185">In questo esempio il gruppo di ruoli Gestione organizzazione viene copiato nel nuovo gruppo di ruoli denominato "Limited Organization Management".</span><span class="sxs-lookup"><span data-stu-id="9aa7f-185">This example copies the Organization Management role group to the new role group named "Limited Organization Management".</span></span> <span data-ttu-id="9aa7f-186">I membri del gruppo di ruolo sono Isabelle, Carter e Lukas.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-186">The role group members are Isabelle, Carter, and Lukas.</span></span>

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

<span data-ttu-id="9aa7f-187">Per informazioni dettagliate sulla sintassi e sui parametri, [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-187">For detailed syntax and parameter information, [New-RoleGroup](/powershell/module/exchange/New-RoleGroup).</span></span>

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a><span data-ttu-id="9aa7f-188">Utilizzare PowerShell EOP autonomo per modificare l'elenco dei membri nei gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="9aa7f-188">Use standalone EOP PowerShell modify the list of members in role groups</span></span>

- <span data-ttu-id="9aa7f-189">I cmdlet **Add-RoleGroupMember** e **Remove-RoleGroupMember** aggiungono o rimuovono singoli membri uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-189">The **Add-RoleGroupMember** and **Remove-RoleGroupMember** cmdlets add or remove individual members one at a time.</span></span> <span data-ttu-id="9aa7f-190">Il cmdlet **Update-RoleGroupMember** può sostituire o modificare l'elenco di membri esistente.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-190">The **Update-RoleGroupMember** cmdlet can replace or modify the existing list of members.</span></span>

- <span data-ttu-id="9aa7f-191">I membri di un gruppo di ruoli possono essere utenti, gruppi di protezione universale abilitati alla posta elettronica o altri gruppi di ruoli (entità di sicurezza).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-191">The members of a role group can be users, mail-enabled universal security groups (USGs), or other role groups (security principals).</span></span>

<span data-ttu-id="9aa7f-192">Per modificare i membri di un gruppo di ruoli, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-192">To modify the members of a role group, use the following syntax:</span></span>

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- <span data-ttu-id="9aa7f-193">Per _sostituire_ l'elenco esistente di membri con i valori specificati, utilizzare la sintassi seguente: `"Member1","Member2",..."MemberN"` .</span><span class="sxs-lookup"><span data-stu-id="9aa7f-193">To _replace_ the existing list of members with the values you specify, use the following syntax: `"Member1","Member2",..."MemberN"`.</span></span>

- <span data-ttu-id="9aa7f-194">Per _modificare in modo selettivo_ l'elenco esistente di membri, utilizzare la sintassi seguente: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .</span><span class="sxs-lookup"><span data-stu-id="9aa7f-194">To _selectively modify_ the existing list of members, use the following syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}`.</span></span>

<span data-ttu-id="9aa7f-195">In questo esempio tutti i membri correnti del gruppo di ruoli Help Desk vengono sostituiti con gli utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-195">This example replaces all current members of the Help Desk role group with the specified users.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

<span data-ttu-id="9aa7f-196">In questo esempio Viene aggiunto Daigoro Akai e viene rimossa Valeria Barrio dall'elenco dei membri del gruppo di ruoli Help Desk.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-196">This example adds Daigoro Akai and removes Valeria Barrio from the list of members on the Help Desk role group.</span></span>

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

<span data-ttu-id="9aa7f-197">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Update-RoleGroupMember](/powershell/module/exchange/Update-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-197">For detailed syntax and parameter information, see [Update-RoleGroupMember](/powershell/module/exchange/Update-RoleGroupMember).</span></span>

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a><span data-ttu-id="9aa7f-198">Usare PowerShell EOP autonomo per rimuovere gruppi di ruoli</span><span class="sxs-lookup"><span data-stu-id="9aa7f-198">Use standalone EOP PowerShell to remove role groups</span></span>

<span data-ttu-id="9aa7f-199">Non è possibile rimuovere i gruppi di ruoli predefiniti, ma è possibile rimuovere i gruppi di ruoli personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-199">You can't remove built-in role groups, but you can remove custom role groups that you've created.</span></span>

<span data-ttu-id="9aa7f-200">Per rimuovere un gruppo di ruoli personalizzato, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-200">To remove a custom role group, use the following syntax:</span></span>

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

<span data-ttu-id="9aa7f-201">Questo esempio rimuove il gruppo di ruolo Formazione degli amministratori.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-201">This example removes the Training Administrators role group.</span></span>

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

<span data-ttu-id="9aa7f-202">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-202">For detailed syntax and parameter information, see [Remove-RoleGroup](/powershell/module/exchange/Remove-RoleGroup).</span></span>

### <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="9aa7f-203">Come verificare se queste procedure hanno avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="9aa7f-203">How do you know these procedures worked?</span></span>

<span data-ttu-id="9aa7f-204">Per verificare la corretta copia di un gruppo di ruoli, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-204">To verify that you've successfully copied a role group, do either of the following steps:</span></span>

- <span data-ttu-id="9aa7f-205">Nell'interfaccia di amministrazione di Exchange, accedere **a Autorizzazioni** Ruoli di amministratore e verificare che il gruppo di ruoli sia \> elencato (o non elencato).</span><span class="sxs-lookup"><span data-stu-id="9aa7f-205">In the EAC, go to **Permissions** \> **Admin roles**, and verify the role group is listed (or not listed).</span></span> <span data-ttu-id="9aa7f-206">Selezionare il gruppo di ruoli e verificare le impostazioni nel riquadro Dettagli oppure fare clic **su Modifica** icona Modifica per verificare ![ le ](../../media/ITPro-EAC-EditIcon.png) impostazioni.</span><span class="sxs-lookup"><span data-stu-id="9aa7f-206">Select the role group, and verify the settings in the Details pane or click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="9aa7f-207">In PowerShell di Exchange Online, sostituire con il nome del gruppo di ruoli ed eseguire il comando seguente per verificare che il gruppo di ruoli esista (o non esista) e verificare \<Role Group Name\> le impostazioni:</span><span class="sxs-lookup"><span data-stu-id="9aa7f-207">In Exchange Online PowerShell, replace \<Role Group Name\> with the name of the role group, and run the following command to verify the role group exists (or doesn't exist) and verify the settings:</span></span>

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```