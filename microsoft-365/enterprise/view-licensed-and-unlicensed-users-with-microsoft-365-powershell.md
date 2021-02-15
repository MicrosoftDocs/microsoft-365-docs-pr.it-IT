---
title: Visualizzare gli utenti di Microsoft 365 con licenza e senza licenza con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: Questo articolo spiega come usare PowerShell per visualizzare gli account utente di Microsoft 365 con e senza licenza.
ms.openlocfilehash: b38ee7674abaea6b63d0661ba79a9814f8c54229
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651385"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a><span data-ttu-id="de603-103">Visualizzare gli utenti di Microsoft 365 con licenza e senza licenza con PowerShell</span><span class="sxs-lookup"><span data-stu-id="de603-103">View licensed and unlicensed Microsoft 365 users with PowerShell</span></span>

<span data-ttu-id="de603-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="de603-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="de603-105">Gli account utente nell'organizzazione di Microsoft 365 potrebbero avere alcune, tutte o nessuna delle licenze disponibili assegnate dai piani di gestione delle licenze disponibili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="de603-105">User accounts in your Microsoft 365 organization may have some, all, or none of the available licenses assigned to them from the licensing plans that are available in your organization.</span></span> <span data-ttu-id="de603-106">È possibile usare PowerShell per Microsoft 365 per trovare rapidamente gli utenti con licenza e senza licenza nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="de603-106">You can use PowerShell for Microsoft 365 to quickly find the licensed and unlicensed users in your organization.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="de603-107">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="de603-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="de603-108">Prima di [tutto, connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="de603-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
<span data-ttu-id="de603-109">Per visualizzare l'elenco di tutti gli account utente dell'organizzazione a cui NON è stato assegnato alcun piano di licenza (utenti senza licenza), eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="de603-109">To view the list of all user accounts in your organization that have NOT been assigned any of your licensing plans (unlicensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

<span data-ttu-id="de603-110">Per visualizzare l'elenco di tutti gli account utente dell'organizzazione a cui è stato assegnato uno dei piani di licenza (utenti con licenza), eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="de603-110">To view the list of all user accounts in your organization that have been assigned any of your licensing plans (licensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$True ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
><span data-ttu-id="de603-111">Per elencare tutti gli utenti dell'abbonamento, utilizzare il `Get-AzureAdUser -All $true` comando.</span><span class="sxs-lookup"><span data-stu-id="de603-111">To list all of the users in your subscription, use the `Get-AzureAdUser -All $true` command.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="de603-112">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="de603-112">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="de603-113">Prima di [tutto, connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="de603-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="de603-114">Per visualizzare l'elenco di tutti gli account utente e il relativo stato di licenza nell'organizzazione, eseguire il comando seguente in PowerShell:</span><span class="sxs-lookup"><span data-stu-id="de603-114">To view the list of all user accounts and their licensing status in your organization, run the following command in PowerShell:</span></span>
  
```powershell
Get-MsolUser -All
```

>[!Note]
><span data-ttu-id="de603-115">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="de603-115">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="de603-116">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de603-116">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="de603-117">Per visualizzare l'elenco di tutti gli account utente senza licenza nell'organizzazione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="de603-117">To view the list of all unlicensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="de603-118">Per visualizzare l'elenco di tutti gli account utente con licenza nell'organizzazione, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="de603-118">To view the list of all licensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a><span data-ttu-id="de603-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de603-119">See also</span></span>

[<span data-ttu-id="de603-120">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="de603-120">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="de603-121">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="de603-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="de603-122">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="de603-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
