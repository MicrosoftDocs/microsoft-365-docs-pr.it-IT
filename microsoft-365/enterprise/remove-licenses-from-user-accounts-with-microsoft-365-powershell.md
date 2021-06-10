---
title: Rimuovere Microsoft 365 licenze dagli account utente con PowerShell
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
- LIL_Placement
- O365ITProTrain
ms.assetid: e7e4dc5e-e299-482c-9414-c265e145134f
description: Spiega come usare PowerShell per rimuovere Microsoft 365 licenze assegnate in precedenza agli utenti.
ms.openlocfilehash: 9944d1ab056d109b6bf71a44fe01acef78ce1f14
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920669"
---
# <a name="remove-microsoft-365-licenses-from-user-accounts-with-powershell"></a><span data-ttu-id="41dcc-103">Rimuovere Microsoft 365 licenze dagli account utente con PowerShell</span><span class="sxs-lookup"><span data-stu-id="41dcc-103">Remove Microsoft 365 licenses from user accounts with PowerShell</span></span>

<span data-ttu-id="41dcc-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="41dcc-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

>[!Note]
><span data-ttu-id="41dcc-105">[Informazioni su come rimuovere licenze dagli account utente con](../admin/manage/remove-licenses-from-users.md) l'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="41dcc-105">[Learn how to remove licenses from user accounts](../admin/manage/remove-licenses-from-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="41dcc-106">Per un elenco delle risorse aggiuntive, vedere [Manage users and groups](../admin/add-users/index.yml).</span><span class="sxs-lookup"><span data-stu-id="41dcc-106">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="41dcc-107">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="41dcc-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="41dcc-108">Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="41dcc-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="41dcc-109">Successivamente, elencare i piani di licenza per il tenant con questo comando.</span><span class="sxs-lookup"><span data-stu-id="41dcc-109">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="41dcc-110">Successivamente, ottenere il nome di accesso dell'account per cui si desidera rimuovere una licenza, noto anche come nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="41dcc-110">Next, get the sign-in name of the account for which you want remove a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="41dcc-111">Infine, specificare i nomi dei piani di accesso e di licenza dell'utente, rimuovere i caratteri "<" e ">" ed eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="41dcc-111">Finally, specify the user sign-in and license plan names, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$License.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $license
```

<span data-ttu-id="41dcc-112">Per rimuovere tutte le licenze per un account utente specifico, specificare il nome di accesso utente, rimuovere i caratteri "<" e ">" ed eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="41dcc-112">To remove all of the licenses for a specific user account, specify the user sign-in name, remove the "<" and ">" characters, and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userList = Get-AzureADUser -ObjectID $userUPN
$Skus = $userList | Select -ExpandProperty AssignedLicenses | Select SkuID
if($userList.Count -ne 0) {
    if($Skus -is [array])
    {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        for ($i=0; $i -lt $Skus.Count; $i++) {
            $Licenses.RemoveLicenses +=  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus[$i].SkuId -EQ).SkuID   
        }
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    } else {
        $licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
        $Licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuID -Value $Skus.SkuId -EQ).SkuID
        Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
    }
}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="41dcc-113">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="41dcc-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="41dcc-114">Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="41dcc-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
   
<span data-ttu-id="41dcc-115">Per visualizzare le informazioni relative ai piani di gestione delle licenze (**AccountSkuID**) nell'organizzazione, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="41dcc-115">To view the licensing plan (**AccountSkuID**) information in your organization, see the following topics:</span></span>
    
  - [<span data-ttu-id="41dcc-116">Visualizzare licenze e servizi con PowerShell</span><span class="sxs-lookup"><span data-stu-id="41dcc-116">View licenses and services with PowerShell</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
    
  - [<span data-ttu-id="41dcc-117">Visualizzare i dettagli della licenza dell'account e del servizio con PowerShell</span><span class="sxs-lookup"><span data-stu-id="41dcc-117">View account license and service details with PowerShell</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
<span data-ttu-id="41dcc-118">Se si usa il cmdlet **Get-MsolUser** senza utilizzare il parametro _-All_, vengono restituiti solo i primi 500 account.</span><span class="sxs-lookup"><span data-stu-id="41dcc-118">If you use the **Get-MsolUser** cmdlet without using the _-All_ parameter, only the first 500 accounts are returned.</span></span>
    
### <a name="removing-licenses-from-user-accounts"></a><span data-ttu-id="41dcc-119">Rimozione delle licenze dagli account utente</span><span class="sxs-lookup"><span data-stu-id="41dcc-119">Removing licenses from user accounts</span></span>

<span data-ttu-id="41dcc-120">Per rimuovere le licenze da un account utente esistente, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="41dcc-120">To remove licenses from an existing user account, use the following syntax:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -RemoveLicenses "<AccountSkuId1>", "<AccountSkuId2>"...
```

>[!Note]
><span data-ttu-id="41dcc-121">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="41dcc-121">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="41dcc-122">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41dcc-122">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="41dcc-123">In questo esempio viene rimossa la licenza **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) dall'account utente BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="41dcc-123">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"
```

>[!Note]
><span data-ttu-id="41dcc-124">Non è possibile utilizzare `Set-MsolUserLicense` il cmdlet per annullare l'assegnazione degli utenti dalle licenze *annullate.*</span><span class="sxs-lookup"><span data-stu-id="41dcc-124">You cannot use the `Set-MsolUserLicense` cmdlet to unassign users from *canceled* licenses.</span></span> <span data-ttu-id="41dcc-125">È necessario eseguire questa operazione singolarmente per ogni account utente nell'Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="41dcc-125">You must do this individually for each user account in the Microsoft 365 admin center.</span></span>
>

<span data-ttu-id="41dcc-126">Per rimuovere tutte le licenze da un gruppo di utenti con licenza esistenti, utilizzare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="41dcc-126">To remove all licenses from a group of existing licensed users, use either of the following methods:</span></span>
  
- <span data-ttu-id="41dcc-127">**Filtrare gli account in base a un attributo account esistente** A tale scopo, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="41dcc-127">**Filter the accounts based on an existing account attribute** To do this, use the following syntax:</span></span>
    
```powershell
$userArray = Get-MsolUser -All <FilterableAttributes> | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="41dcc-128">In questo esempio vengono rimosse tutte le licenze da tutti gli account utente del reparto Vendite negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="41dcc-128">This example removes all licenses from all user accounts in the Sales department in the United States.</span></span>
    
```powershell
$userArray = Get-MsolUser -All -Department "Sales" -UsageLocation "US" | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

- <span data-ttu-id="41dcc-129">**Usare un elenco di account specifici per una licenza specifica** A tale scopo, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="41dcc-129">**Use a list of specific accounts for a specific license** To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="41dcc-130">Creare e salvare un file di testo contenente un account su ogni riga come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="41dcc-130">Create and save a text file that contains one account on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

2. <span data-ttu-id="41dcc-131">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="41dcc-131">Use the following syntax:</span></span>
    
  ```powershell
  $x=Get-Content "<FileNameAndPath>"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "<AccountSkuId1>","<AccountSkuId2>"...
  }
  ```
<span data-ttu-id="41dcc-132">In questo esempio viene rimossa la licenza **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) dagli account utente definiti nel file di testo C:\My Documents\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="41dcc-132">This example removes the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) license from the user accounts defined in the text file C:\My Documents\Accounts.txt.</span></span>
    
  ```powershell
  $x=Get-Content "C:\My Documents\Accounts.txt"
  for ($i=0; $i -lt $x.Count; $i++)
  {
  Set-MsolUserLicense -UserPrincipalName $x[$i] -RemoveLicenses "litwareinc:ENTERPRISEPACK"
  }
  ```

<span data-ttu-id="41dcc-133">Per rimuovere tutte le licenze da tutti gli account utente esistenti, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="41dcc-133">To remove all licenses from all existing user accounts, use the following syntax:</span></span>
  
```powershell
$userArray = Get-MsolUser -All | where {$_.isLicensed -eq $true}
for ($i=0; $i -lt $userArray.Count; $i++)
{
Set-MsolUserLicense -UserPrincipalName $userArray[$i].UserPrincipalName -RemoveLicenses $userArray[$i].licenses.accountskuid
}
```

<span data-ttu-id="41dcc-134">Un altro modo per liberare una licenza consiste nell'eliminazione dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="41dcc-134">Another way to free up a license is by deleting the user account.</span></span> <span data-ttu-id="41dcc-135">Per ulteriori informazioni, vedere [Eliminare e ripristinare gli account utente con PowerShell.](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="41dcc-135">For more information, see [Delete and restore user accounts with PowerShell](delete-and-restore-user-accounts-with-microsoft-365-powershell.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41dcc-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41dcc-136">See also</span></span>

[<span data-ttu-id="41dcc-137">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="41dcc-137">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="41dcc-138">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="41dcc-138">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="41dcc-139">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="41dcc-139">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)