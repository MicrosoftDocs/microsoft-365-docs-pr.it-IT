---
title: Mantenere l'appartenenza ai gruppi di sicurezza con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Informazioni su come usare PowerShell per mantenere l'appartenenza Microsoft 365 gruppi.
ms.openlocfilehash: 9696c9093ae6f24a2edaf544e80794bde45d18d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909575"
---
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="95773-103">Mantenere l'appartenenza ai gruppi di sicurezza con PowerShell</span><span class="sxs-lookup"><span data-stu-id="95773-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="95773-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="95773-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="95773-105">È possibile usare PowerShell per Microsoft 365 come alternativa all'interfaccia di amministrazione di Microsoft 365 per mantenere l'appartenenza al gruppo di sicurezza in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95773-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="95773-106">[Informazioni su come mantenere l'Microsoft 365 di gruppo](../admin/create-groups/add-or-remove-members-from-groups.md) con l'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="95773-106">[Learn how to maintain Microsoft 365 group membership](../admin/create-groups/add-or-remove-members-from-groups.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="95773-107">Per un elenco delle risorse aggiuntive, vedere [Manage users and groups](../admin/add-users/index.yml).</span><span class="sxs-lookup"><span data-stu-id="95773-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="95773-108">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="95773-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="95773-109">Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="95773-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="95773-110">Aggiungere o rimuovere account utente come membri di un gruppo</span><span class="sxs-lookup"><span data-stu-id="95773-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="95773-111">Per aggiungere un account utente tramite il relativo **UPN,** inserire il nome dell'entità utente (UPN) dell'account utente (ad esempio: belindan@contoso.com) e il nome visualizzato del gruppo di sicurezza, rimuovendo i caratteri "<" e ">" ed eseguire questi comandi nella finestra di PowerShell o nell'ambiente di script integrato (ISE) di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95773-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="95773-112">Per aggiungere un **account** utente con il relativo nome visualizzato, immettere il nome visualizzato dell'account utente (ad esempio: Belinda Newman) e il nome visualizzato del gruppo ed eseguire questi comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="95773-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="95773-113">Per rimuovere un account utente dal relativo **UPN,** immettere l'UPN dell'account utente (ad esempio: belindan@contoso.com) e il nome visualizzato del gruppo ed eseguire questi comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="95773-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="95773-114">Per rimuovere un **account** utente con il relativo nome visualizzato, immettere il nome visualizzato dell'account utente (ad esempio: Belinda Newman) e il nome visualizzato del gruppo ed eseguire questi comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="95773-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="95773-115">Aggiungere o rimuovere gruppi come membri di un gruppo</span><span class="sxs-lookup"><span data-stu-id="95773-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="95773-116">I gruppi di sicurezza possono contenere altri gruppi come membri.</span><span class="sxs-lookup"><span data-stu-id="95773-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="95773-117">Microsoft 365 gruppi, tuttavia, non possono.</span><span class="sxs-lookup"><span data-stu-id="95773-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="95773-118">Questa sezione contiene i comandi di PowerShell per aggiungere o rimuovere gruppi solo per un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="95773-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="95773-119">Per aggiungere un gruppo in base al relativo nome **visualizzato,** immettere il nome visualizzato del gruppo che si desidera aggiungere e il nome visualizzato del gruppo che conterrà il gruppo di membri ed eseguire questi comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="95773-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="95773-120">Per rimuovere un gruppo in base al relativo nome **visualizzato,** immettere il nome visualizzato del gruppo che si desidera rimuovere e il nome visualizzato del gruppo che conterrà il gruppo di membri ed eseguire questi comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="95773-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="95773-121">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95773-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="95773-122">Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="95773-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="95773-123">Aggiungere o rimuovere account utente come membri di un gruppo</span><span class="sxs-lookup"><span data-stu-id="95773-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="95773-124">Per aggiungere un account utente tramite il relativo **UPN,** immettere il nome dell'entità utente (UPN) dell'account utente (ad esempio: belindan@contoso.com) e il nome visualizzato del gruppo, rimuovendo i caratteri "<" e ">" ed eseguire questi comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="95773-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="95773-125">Per aggiungere un **account** utente con il relativo nome visualizzato, immettere il nome visualizzato dell'account utente (ad esempio: Belinda Newman) e il nome visualizzato del gruppo ed eseguire questi comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="95773-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="95773-126">Per rimuovere un account utente dal relativo **UPN,** immettere l'UPN dell'account utente (ad esempio: belindan@contoso.com) e il nome visualizzato del gruppo ed eseguire questi comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="95773-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="95773-127">Per rimuovere un **account** utente con il relativo nome visualizzato, immettere il nome visualizzato dell'account utente (ad esempio: Belinda Newman) e il nome visualizzato del gruppo ed eseguire questi comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="95773-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="95773-128">Aggiungere o rimuovere gruppi come membri di un gruppo</span><span class="sxs-lookup"><span data-stu-id="95773-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="95773-129">I gruppi di sicurezza possono contenere altri gruppi come membri.</span><span class="sxs-lookup"><span data-stu-id="95773-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="95773-130">Microsoft 365 gruppi, tuttavia, non possono.</span><span class="sxs-lookup"><span data-stu-id="95773-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="95773-131">Questa sezione contiene i comandi di PowerShell per aggiungere o rimuovere gruppi solo per un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="95773-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="95773-132">Per aggiungere un gruppo in base al relativo nome **visualizzato,** immettere il nome visualizzato del gruppo che si desidera aggiungere e il nome visualizzato del gruppo che conterrà il gruppo di membri ed eseguire questi comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="95773-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="95773-133">Per rimuovere un gruppo in base al relativo nome **visualizzato,** immettere il nome visualizzato del gruppo che si desidera rimuovere e il nome visualizzato del gruppo che conterrà il gruppo di membri ed eseguire questi comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="95773-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="95773-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95773-134">See also</span></span>

[<span data-ttu-id="95773-135">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="95773-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="95773-136">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="95773-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="95773-137">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="95773-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)