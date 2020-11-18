---
title: Gestire i gruppi di sicurezza con PowerShell
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
description: Informazioni su come utilizzare PowerShell per gestire i gruppi di sicurezza.
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073232"
---
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="d181f-103">Gestire i gruppi di sicurezza con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d181f-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="d181f-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d181f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d181f-105">È possibile utilizzare PowerShell per Microsoft 365 come alternativa all'interfaccia di amministrazione di Microsoft 365 per gestire i gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d181f-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="d181f-106">In questo articolo viene descritto l'elenco, la creazione, la modifica delle impostazioni e la rimozione di gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d181f-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="d181f-107">Se per un blocco di comandi di questo articolo è necessario specificare i valori delle variabili, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="d181f-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="d181f-108">Copiare il blocco di comandi negli Appunti e incollarlo nel blocco note o in PowerShell Integrated script Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="d181f-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="d181f-109">Inserire i valori delle variabili e rimuovere i caratteri "<" e ">".</span><span class="sxs-lookup"><span data-stu-id="d181f-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="d181f-110">Eseguire i comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="d181f-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="d181f-111">Vedere [mantenere l'appartenenza al gruppo di sicurezza](maintain-group-membership-with-microsoft-365-powershell.md) per gestire l'appartenenza ai gruppi con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d181f-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="d181f-112">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="d181f-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="d181f-113">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="d181f-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="d181f-114">Elencare i gruppi</span><span class="sxs-lookup"><span data-stu-id="d181f-114">List your groups</span></span>

<span data-ttu-id="d181f-115">Utilizzare questo comando per elencare tutti i gruppi.</span><span class="sxs-lookup"><span data-stu-id="d181f-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="d181f-116">Utilizzare questi comandi per visualizzare le impostazioni di un gruppo specifico in base al relativo nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="d181f-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="d181f-117">Creare un nuovo gruppo</span><span class="sxs-lookup"><span data-stu-id="d181f-117">Create a new group</span></span>

<span data-ttu-id="d181f-118">Utilizzare questo comando per creare un nuovo gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d181f-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="d181f-119">Modificare le impostazioni di un gruppo</span><span class="sxs-lookup"><span data-stu-id="d181f-119">Change the settings on a group</span></span>

<span data-ttu-id="d181f-120">Visualizzare le impostazioni del gruppo con questi comandi.</span><span class="sxs-lookup"><span data-stu-id="d181f-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="d181f-121">Utilizzare quindi l'articolo [set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) per determinare la modalità di modifica di un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="d181f-121">Then, use the [Set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="d181f-122">Rimuovere un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d181f-122">Remove a security group</span></span>

<span data-ttu-id="d181f-123">Utilizzare questi comandi per rimuovere un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d181f-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="d181f-124">Gestire i proprietari di un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d181f-124">Manage the owners of a security group</span></span>

<span data-ttu-id="d181f-125">Utilizzare questi comandi per visualizzare i proprietari correnti di un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d181f-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="d181f-126">Utilizzare questi comandi per aggiungere un account utente in base al **nome dell'entità utente (UPN)** ai proprietari correnti di un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d181f-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="d181f-127">Utilizzare questi comandi per aggiungere un account utente in base al relativo **nome visualizzato** ai proprietari correnti di un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d181f-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="d181f-128">Utilizzare questi comandi per rimuovere un account utente dal relativo **UPN** ai proprietari correnti di un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d181f-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="d181f-129">Utilizzare questi comandi per rimuovere un account utente dal relativo **nome visualizzato** ai proprietari correnti di un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d181f-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="d181f-130">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d181f-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="d181f-131">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d181f-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="d181f-132">Elencare i gruppi</span><span class="sxs-lookup"><span data-stu-id="d181f-132">List your groups</span></span>

<span data-ttu-id="d181f-133">Utilizzare questo comando per elencare tutti i gruppi.</span><span class="sxs-lookup"><span data-stu-id="d181f-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="d181f-134">Utilizzare questi comandi per visualizzare le impostazioni di un gruppo specifico in base al relativo nome visualizzato.</span><span class="sxs-lookup"><span data-stu-id="d181f-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="d181f-135">Creare un nuovo gruppo</span><span class="sxs-lookup"><span data-stu-id="d181f-135">Create a new group</span></span>

<span data-ttu-id="d181f-136">Utilizzare questo comando per creare un nuovo gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d181f-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="d181f-137">Modificare le impostazioni di un gruppo</span><span class="sxs-lookup"><span data-stu-id="d181f-137">Change the settings on a group</span></span>

<span data-ttu-id="d181f-138">Visualizzare le impostazioni del gruppo con questi comandi.</span><span class="sxs-lookup"><span data-stu-id="d181f-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="d181f-139">Utilizzare quindi l'articolo [set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) per determinare la modalità di modifica di un'impostazione.</span><span class="sxs-lookup"><span data-stu-id="d181f-139">Then, use the [Set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="d181f-140">Rimuovere un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="d181f-140">Remove a security group</span></span>

<span data-ttu-id="d181f-141">Utilizzare questi comandi per rimuovere un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d181f-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="d181f-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d181f-142">See also</span></span>

[<span data-ttu-id="d181f-143">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d181f-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d181f-144">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d181f-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d181f-145">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d181f-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
