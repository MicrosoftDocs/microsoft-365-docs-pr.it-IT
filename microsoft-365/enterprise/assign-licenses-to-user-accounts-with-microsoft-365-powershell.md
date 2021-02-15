---
title: Assegnare licenze di Microsoft 365 agli account utente con PowerShell
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
description: In questo articolo viene illustrato come usare PowerShell per assegnare una licenza di Microsoft 365 agli utenti senza licenza.
ms.openlocfilehash: 8c3165b99477afa14e6d2b0da927b5f64c416ef1
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580941"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="ac6a8-103">Assegnare licenze di Microsoft 365 agli account utente con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac6a8-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="ac6a8-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ac6a8-105">Gli utenti non possono usare alcun servizio di Microsoft 365 finché all'account non viene assegnata una licenza da un piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="ac6a8-106">È possibile utilizzare PowerShell per assegnare rapidamente le licenze agli account senza licenza.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="ac6a8-107">Agli account utente deve prima essere assegnata una posizione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="ac6a8-108">La specifica di una posizione è una parte obbligatoria della creazione di un nuovo account utente nell'interfaccia di amministrazione di [Microsoft 365.](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="ac6a8-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="ac6a8-109">Per impostazione predefinita, per gli account sincronizzati da Servizi di dominio Active Directory locale non è specificato un percorso.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="ac6a8-110">È possibile configurare una posizione per questi account da:</span><span class="sxs-lookup"><span data-stu-id="ac6a8-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="ac6a8-111">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac6a8-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="ac6a8-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac6a8-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="ac6a8-113">Il [portale di Azure](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) ( Utenti di Active **Directory**  >  **>** account utente > **Profilo**  >  **Info contatto** Paese o area  >  **geografica).**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-113">The [Azure portal](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="ac6a8-114">[Informazioni su come assegnare licenze agli account utente con](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-114">[Learn how to assign licenses to user accounts](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="ac6a8-115">Per un elenco delle risorse aggiuntive, vedere [Gestire utenti e gruppi.](https://docs.microsoft.com/microsoft-365/admin/add-users/)</span><span class="sxs-lookup"><span data-stu-id="ac6a8-115">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ac6a8-116">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="ac6a8-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="ac6a8-117">Prima di [tutto, connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ac6a8-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="ac6a8-118">Successivamente, elencare i piani di licenza per il tenant con questo comando.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="ac6a8-119">Successivamente, ottenere il nome di accesso dell'account a cui si desidera aggiungere una licenza, noto anche come nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="ac6a8-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="ac6a8-120">Assicurarsi quindi che all'account utente sia assegnata una posizione di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="ac6a8-121">Se non è stata assegnata alcuna posizione di utilizzo, è possibile assegnare una posizione con questi comandi:</span><span class="sxs-lookup"><span data-stu-id="ac6a8-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="ac6a8-122">Infine, specificare il nome di accesso utente e il nome del piano di licenza ed eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ac6a8-123">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac6a8-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ac6a8-124">Prima di [tutto, connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="ac6a8-124">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="ac6a8-125">Eseguire il `Get-MsolAccountSku` comando per visualizzare i piani di licenza disponibili e il numero di licenze disponibili in ogni piano dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-125">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="ac6a8-126">Il numero di licenze disponibili in ogni piano è **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits.**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-126">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="ac6a8-127">Per ulteriori informazioni sui piani di licenza, le licenze e i servizi, vedere [Visualizzare licenze e servizi con PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="ac6a8-127">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="ac6a8-128">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="ac6a8-129">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="ac6a8-130">Per trovare gli account senza licenza nell'organizzazione, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-130">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="ac6a8-131">È possibile assegnare licenze solo agli account utente la cui proprietà **UsageLocation** è impostata su un codice paese ISO 3166-1 alpha-2 valido.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-131">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="ac6a8-132">Ad esempio, US per gli Stati Uniti e FR per la Francia.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-132">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="ac6a8-133">Alcuni servizi di Microsoft 365 non sono disponibili in alcuni paesi.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-133">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="ac6a8-134">Per ulteriori informazioni, vedere [Informazioni sulle restrizioni di licenza.](https://go.microsoft.com/fwlink/p/?LinkId=691730)</span><span class="sxs-lookup"><span data-stu-id="ac6a8-134">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="ac6a8-135">Per trovare gli account che non hanno un **valore UsageLocation,** eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-135">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="ac6a8-136">Per impostare il **valore UsageLocation** in un account, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-136">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="ac6a8-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ac6a8-137">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="ac6a8-138">Se si usa il cmdlet **Get-MsolUser** senza utilizzare il parametro **-All**, vengono restituiti solo i primi 500 account.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-138">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="ac6a8-139">Assegnazione di licenze agli account utente</span><span class="sxs-lookup"><span data-stu-id="ac6a8-139">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="ac6a8-140">Per assegnare una licenza a un utente, utilizzare il comando seguente in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-140">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="ac6a8-141">In questo esempio viene assegnata una licenza dal piano di licenza **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) all'utente senza **licenza belindan \@ litwareinc.com:**</span><span class="sxs-lookup"><span data-stu-id="ac6a8-141">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="ac6a8-142">Per assegnare una licenza a tutti gli utenti senza licenza, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-142">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="ac6a8-143">Non è possibile assegnare più licenze a un utente dallo stesso piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-143">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="ac6a8-144">Se non si dispone di una quantità sufficiente di licenze disponibili, le licenze vengono assegnate agli utenti nell'ordine in cui vengono restituiti dal cmdlet **Get-MsolUser** finché non vengono esaurite le licenze disponibili.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-144">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="ac6a8-145">In questo esempio vengono assegnate le licenze del piano di gestione delle licenze **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) a tutti gli utenti senza licenza:</span><span class="sxs-lookup"><span data-stu-id="ac6a8-145">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="ac6a8-146">In questo esempio vengono assegnate le stesse licenze agli utenti senza licenza nel reparto Vendite negli Stati Uniti:</span><span class="sxs-lookup"><span data-stu-id="ac6a8-146">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ac6a8-147">Spostare un utente in un altro abbonamento (piano di licenza) con il modulo Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="ac6a8-147">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="ac6a8-148">Prima di [tutto, connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="ac6a8-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="ac6a8-149">Successivamente, ottenere il nome di accesso dell'account utente per il quale si desidera cambiare sottoscrizione, noto anche come nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="ac6a8-149">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="ac6a8-150">Successivamente, elencare le sottoscrizioni (piani di licenza) per il tenant con questo comando.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-150">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="ac6a8-151">Elenca quindi le sottoscrizioni attualmente disponibili nell'account utente con questi comandi.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-151">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="ac6a8-152">Identificare la sottoscrizione attualmente disponibile per l'utente (la sottoscrizione FROM) e la sottoscrizione a cui l'utente si sta spostando (la sottoscrizione TO).</span><span class="sxs-lookup"><span data-stu-id="ac6a8-152">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="ac6a8-153">Infine, specificare i nomi delle sottoscrizioni TO e FROM (numeri di parte SKU) ed eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-153">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="ac6a8-154">È possibile verificare la modifica della sottoscrizione per l'account utente con questi comandi.</span><span class="sxs-lookup"><span data-stu-id="ac6a8-154">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="ac6a8-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac6a8-155">See also</span></span>

[<span data-ttu-id="ac6a8-156">Gestire gli account utente, le licenze e i gruppi con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac6a8-156">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ac6a8-157">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac6a8-157">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ac6a8-158">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac6a8-158">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
