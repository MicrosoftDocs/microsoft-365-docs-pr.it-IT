---
title: Eliminare gli account utente di Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Informazioni su come usare moduli diversi in PowerShell per eliminare gli account utente di Microsoft 365.
ms.openlocfilehash: 32081d1ce0cbc7aac89b337cf8b5d08bc8e43dfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919141"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="a7b5c-103">Eliminare gli account utente di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7b5c-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="a7b5c-104">È possibile utilizzare PowerShell per Microsoft 365 per eliminare e ripristinare gli account utente.</span><span class="sxs-lookup"><span data-stu-id="a7b5c-104">You can use PowerShell for Microsoft 365 to delete and restore user accounts.</span></span>

>[!Note]
><span data-ttu-id="a7b5c-105">Informazioni su come [ripristinare un account utente](../admin/add-users/restore-user.md) tramite l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7b5c-105">Learn how to [restore a user account](../admin/add-users/restore-user.md) by using the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="a7b5c-106">Per un elenco delle risorse aggiuntive, vedere [Manage users and groups](../admin/add-users/index.yml).</span><span class="sxs-lookup"><span data-stu-id="a7b5c-106">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="a7b5c-107">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="a7b5c-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="a7b5c-108">Innanzitutto, [connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="a7b5c-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="a7b5c-109">Dopo la connessione, utilizzare la sintassi seguente per rimuovere un singolo account utente:</span><span class="sxs-lookup"><span data-stu-id="a7b5c-109">After you connect, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="a7b5c-110">In questo esempio viene rimosso l'account *utente fabricec \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="a7b5c-110">This example removes the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="a7b5c-111">Il *parametro -ObjectID* nel cmdlet **Remove-AzureADUser** accetta il nome di accesso dell'account, noto anche come Nome entità utente o ID oggetto dell'account.</span><span class="sxs-lookup"><span data-stu-id="a7b5c-111">The *-ObjectID* parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name or the account's object ID.</span></span>
  
<span data-ttu-id="a7b5c-112">Per visualizzare il nome dell'account in base al nome dell'utente, usare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7b5c-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="a7b5c-113">In questo esempio viene visualizzato il nome dell'account per *l'utente Caleb Sills.*</span><span class="sxs-lookup"><span data-stu-id="a7b5c-113">This example displays the account name for the user *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="a7b5c-114">Per rimuovere un account in base al nome visualizzato dell'utente, utilizzare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7b5c-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="a7b5c-115">Usare il modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7b5c-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="a7b5c-116">Quando si elimina un account utente tramite il modulo di Microsoft Azure Active Directory per Windows PowerShell, l'account non viene eliminato definitivamente.</span><span class="sxs-lookup"><span data-stu-id="a7b5c-116">When you delete a user account through the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="a7b5c-117">Infatti, si hanno a disposizione 30 giorni di tempo per ripristinare l'account utente eliminato.</span><span class="sxs-lookup"><span data-stu-id="a7b5c-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="a7b5c-118">Innanzitutto, [connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="a7b5c-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="a7b5c-119">Per eliminare un account utente, utilizzare la sintassi riportata di seguito:</span><span class="sxs-lookup"><span data-stu-id="a7b5c-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="a7b5c-120">PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="a7b5c-120">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="a7b5c-121">Eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7b5c-121">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="a7b5c-122">In questo esempio viene eliminato l'account *utente BelindaN@litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="a7b5c-122">This example deletes the user account *BelindaN@litwareinc.com*.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="a7b5c-123">Per ripristinare un account utente eliminato entro la fine del periodo di tolleranza di 30 giorni, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="a7b5c-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="a7b5c-124">In questo esempio viene ripristinato l'account *eliminato BelindaN \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="a7b5c-124">This example restores the deleted account *BelindaN\@litwareinc.com*.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> <span data-ttu-id="a7b5c-125">Per visualizzare un elenco di utenti eliminati che possono essere ripristinati, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a7b5c-125">To see the list of deleted users that can be restored, run the following command:</span></span>
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> <span data-ttu-id="a7b5c-126">Se il nome dell'entità utente originale di un account viene usato da un altro account, fare ricorso al parametro _NewUserPrincipalName_ invece che a quello _UserPrincipalName_ per specificare un differente nome principale dell'utente, quando si ripristina l'account utente.</span><span class="sxs-lookup"><span data-stu-id="a7b5c-126">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="a7b5c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7b5c-127">See also</span></span>

[<span data-ttu-id="a7b5c-128">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7b5c-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a7b5c-129">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="a7b5c-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a7b5c-130">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7b5c-130">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)