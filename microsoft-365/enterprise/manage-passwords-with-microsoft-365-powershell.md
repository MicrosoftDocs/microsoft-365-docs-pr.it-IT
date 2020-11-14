---
title: Gestire le password con PowerShell
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
description: Informazioni su come utilizzare PowerShell per gestire le password.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073213"
---
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="fc6fa-103">Gestire le password con PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc6fa-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="fc6fa-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="fc6fa-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fc6fa-105">È possibile utilizzare PowerShell per Microsoft 365 come alternativa all'interfaccia di amministrazione di Microsoft 365 per gestire le password in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="fc6fa-106">Se per un blocco di comandi di questo articolo è necessario specificare i valori delle variabili, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="fc6fa-107">Copiare il blocco di comandi negli Appunti e incollarlo nel blocco note o in PowerShell Integrated script Environment (ISE).</span><span class="sxs-lookup"><span data-stu-id="fc6fa-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="fc6fa-108">Inserire i valori delle variabili e rimuovere i caratteri "<" e ">".</span><span class="sxs-lookup"><span data-stu-id="fc6fa-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="fc6fa-109">Eseguire i comandi nella finestra di PowerShell o in PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="fc6fa-110">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="fc6fa-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="fc6fa-111">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="fc6fa-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="fc6fa-112">Impostare una password</span><span class="sxs-lookup"><span data-stu-id="fc6fa-112">Set a password</span></span>

<span data-ttu-id="fc6fa-113">Utilizzare questi comandi per specificare una password per un account utente.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="fc6fa-114">Forzare la modifica della password di un utente</span><span class="sxs-lookup"><span data-stu-id="fc6fa-114">Force a user to change their password</span></span>

<span data-ttu-id="fc6fa-115">Utilizzare questi comandi per impostare una password e forzare la modifica della nuova password da un utente.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="fc6fa-116">Utilizzare questi comandi per impostare una password e imporre a un utente di modificare la nuova password al successivo accesso.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="fc6fa-117">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc6fa-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="fc6fa-118">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="fc6fa-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="fc6fa-119">Impostare una password</span><span class="sxs-lookup"><span data-stu-id="fc6fa-119">Set a password</span></span>

<span data-ttu-id="fc6fa-120">Utilizzare questi comandi per specificare una password per un account utente.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="fc6fa-121">Forzare la modifica della password di un utente</span><span class="sxs-lookup"><span data-stu-id="fc6fa-121">Force a user to change their password</span></span>

<span data-ttu-id="fc6fa-122">Utilizzare questi comandi per forzare la modifica della password da un utente.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="fc6fa-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc6fa-123">See also</span></span>

[<span data-ttu-id="fc6fa-124">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc6fa-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fc6fa-125">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc6fa-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fc6fa-126">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc6fa-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

