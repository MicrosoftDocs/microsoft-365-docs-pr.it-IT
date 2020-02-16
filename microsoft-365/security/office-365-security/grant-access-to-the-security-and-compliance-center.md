---
title: Fornire agli utenti l'accesso al Centro sicurezza e conformità di Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gli utenti devono essere autorizzati a utilizzare le autorizzazioni nel centro sicurezza & conformità di Office 365 prima di poter gestire qualsiasi funzionalità di sicurezza o conformità.
ms.openlocfilehash: cccf44a64d20dc1304dbc5145d6ae50441cfacef
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085970"
---
# <a name="give-users-access-to-the-office-365-security--compliance-center"></a><span data-ttu-id="c55a7-103">Fornire agli utenti l'accesso al Centro sicurezza e conformità di Office 365</span><span class="sxs-lookup"><span data-stu-id="c55a7-103">Give users access to the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="c55a7-104">Gli utenti devono essere autorizzati a utilizzare le autorizzazioni nel centro sicurezza & conformità di Office 365 prima di poter gestire qualsiasi funzionalità di sicurezza o conformità.</span><span class="sxs-lookup"><span data-stu-id="c55a7-104">Users need to be assigned permissions in the Office 365 Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="c55a7-105">In qualità di amministratore globale di Office 365 o membro del gruppo di ruoli OrganizationManagement nel centro sicurezza & conformità, è possibile concedere queste autorizzazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c55a7-105">As an Office 365 global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="c55a7-106">Gli utenti potranno solo gestire le funzionalità di sicurezza o conformità per le quali è stato concesso loro l'accesso.</span><span class="sxs-lookup"><span data-stu-id="c55a7-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="c55a7-107">Per ulteriori informazioni sulle diverse autorizzazioni che è possibile assegnare agli utenti nel centro sicurezza & conformità, vedere [autorizzazioni nel centro sicurezza & conformità di Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c55a7-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c55a7-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c55a7-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c55a7-109">Per completare la procedura descritta in questo articolo, è necessario essere un amministratore globale di Office 365 o un membro del gruppo di ruoli OrganizationManagement nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="c55a7-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="c55a7-110">I gruppi di ruoli per il Centro sicurezza & conformità potrebbero avere nomi simili ai gruppi di ruoli in Exchange Online, ma non sono gli stessi.</span><span class="sxs-lookup"><span data-stu-id="c55a7-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="c55a7-111">Le appartenenze ai gruppi di ruoli non sono condivise tra Exchange Online e il Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="c55a7-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="c55a7-112">I partner di autorizzazione accesso delegato (DAP) con amministra per conto di (AOBO) le autorizzazioni non possono accedere al centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="c55a7-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="c55a7-113">Utilizzare l'interfaccia di amministrazione per concedere a un altro utente l'accesso al centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="c55a7-113">Use the admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="c55a7-114">[Accedere a Office 365 e passare all'interfaccia di amministrazione](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="c55a7-114">[Sign in to Office 365 and go to the Admin center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span>

2. <span data-ttu-id="c55a7-115">Nell'interfaccia di amministrazione di Microsoft 365 aprire interfaccia di **Amministrazione** e quindi fare clic su **sicurezza & conformità**.</span><span class="sxs-lookup"><span data-stu-id="c55a7-115">In the Microsoft 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="c55a7-116">Nel centro sicurezza & conformità, accedere a **autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="c55a7-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="c55a7-117">Nell'elenco scegliere il gruppo di ruoli a cui si desidera aggiungere l'utente e fare clic su **modifica** ![icona](../../media/O365-MDM-CreatePolicy-EditIcon.gif)modifica.</span><span class="sxs-lookup"><span data-stu-id="c55a7-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="c55a7-118">Nella pagina delle proprietà del gruppo di ruoli in **membri**fare \*\*\*\*![clic su Aggiungi](../../media/ITPro-EAC-AddIcon.gif) icona e selezionare il nome dell'utente (o degli utenti) che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="c55a7-118">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="c55a7-119">Dopo aver selezionato tutti gli utenti che si desidera aggiungere al gruppo di ruoli, fare clic su \*\*Aggiungi\> \*\* e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c55a7-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="c55a7-120">Fare clic su **Salva** per salvare le modifiche al gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="c55a7-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c55a7-121">Come verificare se l'operazione ha avuto esito positivo?</span><span class="sxs-lookup"><span data-stu-id="c55a7-121">How do you know this worked?</span></span>

1. <span data-ttu-id="c55a7-122">Nel centro sicurezza & conformità, accedere a **autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="c55a7-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="c55a7-123">Nell'elenco, selezionare il gruppo di ruoli per visualizzare i membri.</span><span class="sxs-lookup"><span data-stu-id="c55a7-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="c55a7-124">A destra, nei dettagli del gruppo di ruoli, è possibile visualizzare i membri del gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="c55a7-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="c55a7-125">Utilizzo di PowerShell per consentire a un altro utente di accedere al centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="c55a7-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="c55a7-126">[Connettersi a PowerShell per Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="c55a7-126">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="c55a7-127">Usa il comando **Add-RoleGroupMember** per aggiungere un utente al ruolo Gestione organizzazione, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c55a7-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="c55a7-128">**Parametri**:</span><span class="sxs-lookup"><span data-stu-id="c55a7-128">**Parameters**:</span></span>

   - <span data-ttu-id="c55a7-129">_Identity_ è il gruppo di ruoli a cui aggiungere un membro.</span><span class="sxs-lookup"><span data-stu-id="c55a7-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="c55a7-130">_Member_ è la cassetta postale, il gruppo di protezione universale (USG) o il computer da aggiungere al gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="c55a7-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="c55a7-131">Puoi specificare solo un membro per volta.</span><span class="sxs-lookup"><span data-stu-id="c55a7-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="c55a7-132">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Add-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="c55a7-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Add-RoleGroupMember).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c55a7-133">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="c55a7-133">How do you know this worked?</span></span>

<span data-ttu-id="c55a7-134">Per verificare di aver concesso agli utenti l'accesso al centro sicurezza & conformità, utilizzare il cmdlet **Get-RoleGroupMember** per visualizzare i membri nel gruppo di ruoli Gestione organizzazione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c55a7-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="c55a7-135">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="c55a7-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/role-based-access-control/Get-RoleGroupMember).</span></span>
