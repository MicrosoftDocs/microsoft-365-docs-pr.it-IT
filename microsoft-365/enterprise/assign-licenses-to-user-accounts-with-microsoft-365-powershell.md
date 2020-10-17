---
title: Assegnare le licenze Microsoft 365 agli account utente con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: In questo articolo vengono fornite informazioni su come utilizzare PowerShell per assegnare una licenza Microsoft 365 agli utenti senza licenza.
ms.openlocfilehash: 8c3165b99477afa14e6d2b0da927b5f64c416ef1
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580941"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="6d81e-103">Assegnare le licenze Microsoft 365 agli account utente con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d81e-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="6d81e-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="6d81e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6d81e-105">Gli utenti non possono utilizzare i servizi di Microsoft 365 finché all'account non è stata assegnata una licenza da un piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="6d81e-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="6d81e-106">È possibile utilizzare PowerShell per assegnare rapidamente le licenze agli account senza licenza.</span><span class="sxs-lookup"><span data-stu-id="6d81e-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="6d81e-107">Gli account utente devono prima essere assegnati a un percorso.</span><span class="sxs-lookup"><span data-stu-id="6d81e-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="6d81e-108">Se si specifica un percorso, è necessario creare un nuovo account utente nell'interfaccia di [amministrazione di Microsoft 365](../admin/add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="6d81e-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="6d81e-109">Gli account sincronizzati dai servizi di dominio Active Directory locali non dispongono per impostazione predefinita di una posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="6d81e-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="6d81e-110">È possibile configurare una posizione per questi account da:</span><span class="sxs-lookup"><span data-stu-id="6d81e-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="6d81e-111">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d81e-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="6d81e-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d81e-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="6d81e-113">[Portale di Azure](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (gli utenti di**Active Directory**  >  **Users** > account **Profile**utente >  >  **Contact info**  >  **paese o area geografica**dei contatti del profilo).</span><span class="sxs-lookup"><span data-stu-id="6d81e-113">The [Azure portal](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="6d81e-114">[Informazioni su come assegnare le licenze agli account utente](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) con l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d81e-114">[Learn how to assign licenses to user accounts](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="6d81e-115">Per un elenco di risorse aggiuntive, vedere [Manage Users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="6d81e-115">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6d81e-116">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="6d81e-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6d81e-117">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6d81e-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="6d81e-118">Successivamente, elencare i piani di licenza per il tenant con questo comando.</span><span class="sxs-lookup"><span data-stu-id="6d81e-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="6d81e-119">Successivamente, ottenere il nome di accesso dell'account a cui si desidera aggiungere una licenza, noto anche come nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="6d81e-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="6d81e-120">Successivamente, verificare che l'account utente disponga di una posizione di utilizzo assegnata.</span><span class="sxs-lookup"><span data-stu-id="6d81e-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="6d81e-121">Se non è stata assegnata alcuna posizione di utilizzo, è possibile assegnarne una con questi comandi:</span><span class="sxs-lookup"><span data-stu-id="6d81e-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="6d81e-122">Infine, specificare il nome di accesso dell'utente e il nome del piano di licenza ed eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="6d81e-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6d81e-123">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d81e-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6d81e-124">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="6d81e-124">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="6d81e-125">Eseguire il `Get-MsolAccountSku` comando per visualizzare i piani di gestione delle licenze disponibili e il numero di licenze disponibili in ogni piano dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6d81e-125">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="6d81e-126">Il numero di licenze disponibili in ogni piano è **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**.</span><span class="sxs-lookup"><span data-stu-id="6d81e-126">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="6d81e-127">Per ulteriori informazioni sui piani di licenza, le licenze e i servizi, vedere [View licences and Services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6d81e-127">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="6d81e-128">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="6d81e-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="6d81e-129">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d81e-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="6d81e-130">Per trovare gli account senza licenza nell'organizzazione, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="6d81e-130">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="6d81e-131">È possibile assegnare licenze solo agli account utente con la proprietà **UsageLocation** impostata su un codice paese ISO 3166-1 Alpha-2 valido.</span><span class="sxs-lookup"><span data-stu-id="6d81e-131">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="6d81e-132">Ad esempio, US per gli Stati Uniti e FR per la Francia.</span><span class="sxs-lookup"><span data-stu-id="6d81e-132">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="6d81e-133">Alcuni servizi Microsoft 365 non sono disponibili in alcuni paesi.</span><span class="sxs-lookup"><span data-stu-id="6d81e-133">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="6d81e-134">Per ulteriori informazioni, vedere [informazioni sulle restrizioni di licenza](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="6d81e-134">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="6d81e-135">Per trovare account che non dispongono di un valore **UsageLocation** , eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="6d81e-135">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="6d81e-136">Per impostare il valore **UsageLocation** su un account, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="6d81e-136">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="6d81e-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6d81e-137">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="6d81e-138">Se si usa il cmdlet **Get-MsolUser** senza utilizzare il parametro **-All**, vengono restituiti solo i primi 500 account.</span><span class="sxs-lookup"><span data-stu-id="6d81e-138">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="6d81e-139">Assegnazione di licenze agli account utente</span><span class="sxs-lookup"><span data-stu-id="6d81e-139">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="6d81e-140">Per assegnare una licenza a un utente, utilizzare il seguente comando in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d81e-140">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="6d81e-141">In questo esempio viene assegnata una licenza dal piano di gestione delle licenze **litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3) all'utente non autorizzato \*\* \@ litwareinc.com\*\*:</span><span class="sxs-lookup"><span data-stu-id="6d81e-141">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="6d81e-142">Per assegnare una licenza a tutti gli utenti senza licenza, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="6d81e-142">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="6d81e-143">Non è possibile assegnare più licenze a un utente dallo stesso piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="6d81e-143">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="6d81e-144">Se non si dispone di una quantità sufficiente di licenze disponibili, le licenze vengono assegnate agli utenti nell'ordine in cui vengono restituiti dal cmdlet **Get-MsolUser** finché non vengono esaurite le licenze disponibili.</span><span class="sxs-lookup"><span data-stu-id="6d81e-144">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="6d81e-145">In questo esempio vengono assegnate le licenze dal piano di gestione delle licenze **litwareinc: ENTERPRISEPACK** (Office 365 Enterprise E3) a tutti gli utenti senza licenza:</span><span class="sxs-lookup"><span data-stu-id="6d81e-145">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="6d81e-146">In questo esempio vengono assegnate le stesse licenze agli utenti senza licenza del reparto vendite negli Stati Uniti:</span><span class="sxs-lookup"><span data-stu-id="6d81e-146">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6d81e-147">Spostare un utente in una sottoscrizione diversa (piano di licenza) con il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="6d81e-147">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6d81e-148">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6d81e-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="6d81e-149">Successivamente, ottenere il nome di accesso dell'account utente per il quale si desidera cambiare le sottoscrizioni, noto anche come nome dell'entità utente (UPN, User Principal Name).</span><span class="sxs-lookup"><span data-stu-id="6d81e-149">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="6d81e-150">Successivamente, elencare le sottoscrizioni (piani di licenza) per il tenant con questo comando.</span><span class="sxs-lookup"><span data-stu-id="6d81e-150">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="6d81e-151">Successivamente, elencare le sottoscrizioni che l'account utente ha attualmente con questi comandi.</span><span class="sxs-lookup"><span data-stu-id="6d81e-151">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="6d81e-152">Identificare la sottoscrizione che l'utente ha attualmente (la sottoscrizione da) e l'abbonamento a cui l'utente sta spostando (la sottoscrizione a).</span><span class="sxs-lookup"><span data-stu-id="6d81e-152">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="6d81e-153">Infine, specificare i nomi delle sottoscrizioni da e verso (SKU Part Number) ed eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="6d81e-153">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

<span data-ttu-id="6d81e-154">È possibile verificare la modifica della sottoscrizione per l'account utente con questi comandi.</span><span class="sxs-lookup"><span data-stu-id="6d81e-154">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="6d81e-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d81e-155">See also</span></span>

[<span data-ttu-id="6d81e-156">Gestire gli account utente, le licenze e i gruppi con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d81e-156">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6d81e-157">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d81e-157">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6d81e-158">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d81e-158">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
