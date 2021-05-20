---
title: Assegnare Microsoft 365 licenze agli account utente con PowerShell
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
description: In questo articolo imparerai a usare PowerShell per assegnare una Microsoft 365 licenza a utenti senza licenza.
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572622"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="55c39-103">Assegnare Microsoft 365 licenze agli account utente con PowerShell</span><span class="sxs-lookup"><span data-stu-id="55c39-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="55c39-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="55c39-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="55c39-105">Gli utenti non possono utilizzare alcun servizio Microsoft 365 a cui al proprio account non è stata assegnata una licenza da un piano di licenza.</span><span class="sxs-lookup"><span data-stu-id="55c39-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="55c39-106">È possibile utilizzare PowerShell per assegnare rapidamente licenze ad account senza licenza.</span><span class="sxs-lookup"><span data-stu-id="55c39-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="55c39-107">Agli account utente deve prima essere assegnata una posizione.</span><span class="sxs-lookup"><span data-stu-id="55c39-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="55c39-108">La specifica di un percorso è una parte necessaria della creazione di un nuovo account utente [nell'Microsoft 365 di amministrazione](../admin/add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="55c39-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="55c39-109">Per impostazione predefinita, gli account sincronizzati da Servizi di dominio Active Directory locali non hanno un percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="55c39-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="55c39-110">È possibile configurare un percorso per questi account da:</span><span class="sxs-lookup"><span data-stu-id="55c39-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="55c39-111">L'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="55c39-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="55c39-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="55c39-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="55c39-113">Il [portale di Azure](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) ( Utenti di Active **Directory**> account utente > informazioni  >   di **contatto**  >  **profilo** Paese o  >  **area geografica**).</span><span class="sxs-lookup"><span data-stu-id="55c39-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="55c39-114">[Informazioni su come assegnare licenze agli account utente con l'interfaccia](../admin/manage/assign-licenses-to-users.md) Microsoft 365 amministrazione.</span><span class="sxs-lookup"><span data-stu-id="55c39-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="55c39-115">Per un elenco delle risorse aggiuntive, vedere [Gestire utenti e gruppi](../admin/add-users/index.yml).</span><span class="sxs-lookup"><span data-stu-id="55c39-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="55c39-116">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="55c39-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="55c39-117">Innanzitutto, [connettersi al tenant Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="55c39-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="55c39-118">Elencare quindi i piani di licenza per il tenant con questo comando.</span><span class="sxs-lookup"><span data-stu-id="55c39-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="55c39-119">Ottenere quindi il nome di accesso dell'account a cui si desidera aggiungere una licenza, noto anche come nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="55c39-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="55c39-120">Assicurarsi quindi che all'account utente sia assegnata una posizione di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="55c39-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="55c39-121">Se non è stata assegnata alcuna posizione di utilizzo, è possibile assegnarla con questi comandi:</span><span class="sxs-lookup"><span data-stu-id="55c39-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="55c39-122">Infine, specificare il nome di accesso utente e il nome del piano di licenza ed eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="55c39-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="55c39-123">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="55c39-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="55c39-124">Si noti che inizieremo a deprecare questo modulo quando la funzionalità di questo modulo è disponibile nel più [Azure Active Directory PowerShell per Graph](/powershell/azuread/v2/azureactivedirectory) modulo.</span><span class="sxs-lookup"><span data-stu-id="55c39-124">Please note that we will begin to deprecate this module when the functionality of this module is available in the newer [Azure Active Directory PowerShell for Graph](/powershell/azuread/v2/azureactivedirectory) module.</span></span> <span data-ttu-id="55c39-125">Consigliamo ai clienti che stanno creando nuovi script di PowerShell di utilizzare il modulo più nuovo anziché questo modulo.</span><span class="sxs-lookup"><span data-stu-id="55c39-125">We advise customers who are creating new PowerShell scripts to use the newer module instead of this module.</span></span>

<span data-ttu-id="55c39-126">Innanzitutto, [connettersi al tenant Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="55c39-126">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="55c39-127">Eseguire il `Get-MsolAccountSku` comando per visualizzare i piani di licenza disponibili e il numero di licenze disponibili in ogni piano dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="55c39-127">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="55c39-128">Il numero di licenze disponibili in ogni piano è **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**.</span><span class="sxs-lookup"><span data-stu-id="55c39-128">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="55c39-129">Per ulteriori informazioni su piani di licenza, licenze e servizi, vedere [Visualizzare licenze e servizi con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="55c39-129">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="55c39-130">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="55c39-130">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="55c39-131">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55c39-131">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="55c39-132">Per trovare gli account senza licenza nell'organizzazione, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="55c39-132">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="55c39-133">È possibile assegnare licenze solo agli account utente la cui **proprietà UsageLocation** è impostata su un codice paese ISO 3166-1 alpha-2 valido.</span><span class="sxs-lookup"><span data-stu-id="55c39-133">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="55c39-134">Ad esempio, US per gli Stati Uniti e FR per la Francia.</span><span class="sxs-lookup"><span data-stu-id="55c39-134">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="55c39-135">Alcuni Microsoft 365 servizi non sono disponibili in alcuni paesi.</span><span class="sxs-lookup"><span data-stu-id="55c39-135">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="55c39-136">Per ulteriori informazioni, vedere [Informazioni sulle restrizioni di licenza](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="55c39-136">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="55c39-137">Per trovare gli account che non hanno un valore **UsageLocation,** eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="55c39-137">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="55c39-138">Per impostare il **valore UsageLocation** in un account, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="55c39-138">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="55c39-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="55c39-139">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="55c39-140">Se si usa il cmdlet **Get-MsolUser** senza utilizzare il parametro **-All**, vengono restituiti solo i primi 500 account.</span><span class="sxs-lookup"><span data-stu-id="55c39-140">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="55c39-141">Assegnazione di licenze agli account utente</span><span class="sxs-lookup"><span data-stu-id="55c39-141">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="55c39-142">Per assegnare una licenza a un utente, utilizzare il comando seguente in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="55c39-142">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="55c39-143">In questo esempio viene assegnata una licenza **dal piano di licenze litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) all'utente senza licenza **belindan \@ litwareinc.com**:</span><span class="sxs-lookup"><span data-stu-id="55c39-143">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="55c39-144">Per assegnare una licenza a tutti gli utenti senza licenza, eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="55c39-144">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="55c39-145">Non è possibile assegnare più licenze a un utente dallo stesso piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="55c39-145">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="55c39-146">Se non si dispone di una quantità sufficiente di licenze disponibili, le licenze vengono assegnate agli utenti nell'ordine in cui vengono restituiti dal cmdlet **Get-MsolUser** finché non vengono esaurite le licenze disponibili.</span><span class="sxs-lookup"><span data-stu-id="55c39-146">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="55c39-147">In questo esempio le licenze del **piano di licenza litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) vengono assegnate a tutti gli utenti senza licenza:</span><span class="sxs-lookup"><span data-stu-id="55c39-147">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="55c39-148">In questo esempio vengono assegnate le stesse licenze agli utenti senza licenza nel reparto vendite negli Stati Uniti:</span><span class="sxs-lookup"><span data-stu-id="55c39-148">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="55c39-149">Spostare un utente in un abbonamento diverso (piano di licenza) con il modulo Azure Active Directory PowerShell per Graph utente</span><span class="sxs-lookup"><span data-stu-id="55c39-149">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="55c39-150">Innanzitutto, [connettersi al tenant Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="55c39-150">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="55c39-151">Ottenere quindi il nome di accesso dell'account utente per il quale si desidera cambiare sottoscrizioni, noto anche come nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="55c39-151">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="55c39-152">Elencare quindi le sottoscrizioni (piani di licenza) per il tenant con questo comando.</span><span class="sxs-lookup"><span data-stu-id="55c39-152">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="55c39-153">Elencare quindi le sottoscrizioni attualmente disponibili nell'account utente con questi comandi.</span><span class="sxs-lookup"><span data-stu-id="55c39-153">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="55c39-154">Identificare la sottoscrizione attualmente in corso (la sottoscrizione FROM) e la sottoscrizione a cui l'utente si sta spostando (la sottoscrizione TO).</span><span class="sxs-lookup"><span data-stu-id="55c39-154">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="55c39-155">Infine, specificare i nomi delle sottotitoi TO e FROM (numeri di parte SKU) ed eseguire questi comandi.</span><span class="sxs-lookup"><span data-stu-id="55c39-155">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="55c39-156">È possibile verificare la modifica della sottoscrizione per l'account utente con questi comandi.</span><span class="sxs-lookup"><span data-stu-id="55c39-156">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="55c39-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55c39-157">See also</span></span>

[<span data-ttu-id="55c39-158">Gestire gli account utente, le licenze e i gruppi con PowerShell</span><span class="sxs-lookup"><span data-stu-id="55c39-158">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="55c39-159">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="55c39-159">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="55c39-160">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="55c39-160">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
