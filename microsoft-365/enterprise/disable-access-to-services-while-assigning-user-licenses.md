---
title: Disabilitare l'accesso Microsoft 365 servizi durante l'assegnazione delle licenze utente
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: Informazioni su come assegnare licenze agli account utente e disabilitare piani di servizio specifici contemporaneamente usando PowerShell per Microsoft 365.
ms.openlocfilehash: ca5becb8709eeab7b5c535747ac93d36fefa0da8
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228904"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a><span data-ttu-id="17f42-103">Disabilitare l'accesso Microsoft 365 servizi durante l'assegnazione delle licenze utente</span><span class="sxs-lookup"><span data-stu-id="17f42-103">Disable access to Microsoft 365 services while assigning user licenses</span></span>

<span data-ttu-id="17f42-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="17f42-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="17f42-105">Microsoft 365 sono disponibili piani di servizio per singoli servizi.</span><span class="sxs-lookup"><span data-stu-id="17f42-105">Microsoft 365 subscriptions come with service plans for individual services.</span></span> <span data-ttu-id="17f42-106">Microsoft 365 gli amministratori devono spesso disabilitare determinati piani quando assegnano licenze agli utenti.</span><span class="sxs-lookup"><span data-stu-id="17f42-106">Microsoft 365 administrators often need to disable certain plans when assigning licenses to users.</span></span> <span data-ttu-id="17f42-107">Con le istruzioni contenute in questo articolo, è possibile assegnare una licenza di Microsoft 365 disabilitando piani di servizio specifici tramite PowerShell per un singolo account utente o più account utente.</span><span class="sxs-lookup"><span data-stu-id="17f42-107">With the instructions in this article, you can assign a Microsoft 365 license while disabling specific service plans using PowerShell for an individual user account or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="17f42-108">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="17f42-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="17f42-109">Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="17f42-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>


<span data-ttu-id="17f42-110">Successivamente, elencare i piani di licenza per il tenant con questo comando.</span><span class="sxs-lookup"><span data-stu-id="17f42-110">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="17f42-111">Successivamente, ottenere il nome di accesso dell'account a cui si desidera aggiungere una licenza, noto anche come nome dell'entità utente (UPN).</span><span class="sxs-lookup"><span data-stu-id="17f42-111">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="17f42-112">Successivamente, compilare un elenco di servizi da abilitare.</span><span class="sxs-lookup"><span data-stu-id="17f42-112">Next, compile a list of services to enable.</span></span> <span data-ttu-id="17f42-113">Per un elenco completo dei piani di licenza (noti anche come nomi di prodotto), dei piani di servizio inclusi e dei nomi descrittivi corrispondenti, vedere Nomi dei prodotti e identificatori del piano di servizio [per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="17f42-113">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="17f42-114">Per il blocco di comandi seguente, inserire il nome dell'entità utente dell'account utente, il numero della parte SKU e l'elenco dei piani di servizio per abilitare e rimuovere il testo esplicativo e i \< and > caratteri.</span><span class="sxs-lookup"><span data-stu-id="17f42-114">For the command block below, fill in the user principal name of the user account, the SKU part number, and the list of service plans to enable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="17f42-115">Successivamente, eseguire i comandi risultanti nel prompt dei comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17f42-115">Then, run the resulting commands at the PowerShell command prompt.</span></span>

```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="17f42-116">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="17f42-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="17f42-117">Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="17f42-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="17f42-118">Eseguire quindi questo comando per visualizzare le sottoscrizioni correnti:</span><span class="sxs-lookup"><span data-stu-id="17f42-118">Next, run this command to see your current subscriptions:</span></span>

```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="17f42-119">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="17f42-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="17f42-120">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17f42-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="17f42-121">Nella visualizzazione del comando  `Get-MsolAccountSku`:</span><span class="sxs-lookup"><span data-stu-id="17f42-121">In the display of the  `Get-MsolAccountSku` command:</span></span>

- <span data-ttu-id="17f42-122">**AccountSkuId** è un abbonamento per l'organizzazione nel formato \<OrganizationName>:\<Subscription>.</span><span class="sxs-lookup"><span data-stu-id="17f42-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span></span> <span data-ttu-id="17f42-123">Il valore specificato al momento della registrazione a Microsoft 365 \<OrganizationName> ed è univoco per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="17f42-123">The \<OrganizationName> is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="17f42-124">Il valore \<Subscription> è per una sottoscrizione specifica.</span><span class="sxs-lookup"><span data-stu-id="17f42-124">The \<Subscription> value is for a specific subscription.</span></span> <span data-ttu-id="17f42-125">Ad esempio, per litwareinc:ENTERPRISEPACK, il nome dell'organizzazione è litwareinc e il nome della sottoscrizione è ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="17f42-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span></span>

- <span data-ttu-id="17f42-126">**ActiveUnits** è il numero di licenze acquistate per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="17f42-126">**ActiveUnits** is the number of licenses that you've purchased for the subscription.</span></span>

- <span data-ttu-id="17f42-127">**WarningUnits** è il numero di licenze in una sottoscrizione non rinnovata e che scadrà dopo il periodo di prova di 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="17f42-127">**WarningUnits** is the number of licenses in a subscription that you haven't renewed, and that will expire after the 30-day grace period.</span></span>

- <span data-ttu-id="17f42-128">**ConsumedUnits** è il numero di licenze assegnate agli utenti per la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="17f42-128">**ConsumedUnits** is the number of licenses that you've assigned to users for the subscription.</span></span>

<span data-ttu-id="17f42-129">Nota accountSkuId per la sottoscrizione Microsoft 365 che contiene gli utenti di cui vuoi ottenere la licenza.</span><span class="sxs-lookup"><span data-stu-id="17f42-129">Note the AccountSkuId for your Microsoft 365 subscription that contains the users you want to license.</span></span> <span data-ttu-id="17f42-130">Inoltre, assicurarsi che siano disponibili licenze sufficienti da assegnare (sottrarre **ConsumedUnits** da **ActiveUnits**).</span><span class="sxs-lookup"><span data-stu-id="17f42-130">Also, ensure that there are enough licenses to assign (subtract **ConsumedUnits** from **ActiveUnits**).</span></span>

<span data-ttu-id="17f42-131">Eseguire quindi questo comando per visualizzare i dettagli sui piani di Microsoft 365 disponibili in tutte le sottoscrizioni:</span><span class="sxs-lookup"><span data-stu-id="17f42-131">Next, run this command to see the details about the Microsoft 365 service plans that are available in all your subscriptions:</span></span>

```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="17f42-132">Dalla visualizzazione di questo comando, stabilire quali piani di servizio si desidera disattivare quando si assegnano le licenze agli utenti.</span><span class="sxs-lookup"><span data-stu-id="17f42-132">From the display of this command, determine which service plans you would like to disable when you assign licenses to users.</span></span>

<span data-ttu-id="17f42-133">Ecco un elenco parziale dei piani di servizio e dei servizi Microsoft 365 corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="17f42-133">Here is a partial list of service plans and their corresponding Microsoft 365 services.</span></span>

<span data-ttu-id="17f42-134">Nella tabella seguente vengono illustrati i Microsoft 365 e i relativi nomi descrittivi per i servizi più comuni.</span><span class="sxs-lookup"><span data-stu-id="17f42-134">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="17f42-135">L'elenco dei piani di servizio degli utenti potrebbe essere diverso.</span><span class="sxs-lookup"><span data-stu-id="17f42-135">Your list of service plans might be different.</span></span>

|<span data-ttu-id="17f42-136">**Piano di servizio**</span><span class="sxs-lookup"><span data-stu-id="17f42-136">**Service plan**</span></span>|<span data-ttu-id="17f42-137">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="17f42-137">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="17f42-138">Sway</span><span class="sxs-lookup"><span data-stu-id="17f42-138">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="17f42-139">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17f42-139">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="17f42-140">Yammer</span><span class="sxs-lookup"><span data-stu-id="17f42-140">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="17f42-141">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="17f42-141">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="17f42-142">Microsoft 365 Apps for enterprise *(precedentemente denominato Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="17f42-142">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="17f42-143">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="17f42-143">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="17f42-144">Office</span><span class="sxs-lookup"><span data-stu-id="17f42-144">Office</span></span>   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="17f42-145">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="17f42-145">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="17f42-146">Exchange Online, piano 2</span><span class="sxs-lookup"><span data-stu-id="17f42-146">Exchange Online Plan 2</span></span>  <br/> |

<span data-ttu-id="17f42-147">Per un elenco completo dei piani di licenza (noti anche come nomi di prodotto), dei piani di servizio inclusi e dei nomi descrittivi corrispondenti, vedere Nomi dei prodotti e identificatori del piano di servizio [per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="17f42-147">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="17f42-148">Dopo aver creato AccountSkuId e i piani di servizio da disabilitare, è possibile assegnare licenze per un singolo utente o per più utenti.</span><span class="sxs-lookup"><span data-stu-id="17f42-148">Now that you have the AccountSkuId and the service plans to disable, you can assign licenses for an individual user or for multiple users.</span></span>

### <a name="for-a-single-user"></a><span data-ttu-id="17f42-149">Per un utente singolo</span><span class="sxs-lookup"><span data-stu-id="17f42-149">For a single user</span></span>

<span data-ttu-id="17f42-150">Per un singolo utente, inserire il nome dell'entità utente dell'account utente, l'AccountSkuId e l'elenco dei piani di servizio per disabilitare e rimuovere il testo esplicativo e i \< and > caratteri.</span><span class="sxs-lookup"><span data-stu-id="17f42-150">For a single user, fill in the user principal name of the user account, the AccountSkuId, and the list of service plans to disable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="17f42-151">Successivamente, eseguire i comandi risultanti nel prompt dei comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17f42-151">Then, run the resulting commands at the PowerShell command prompt.</span></span>

```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

<span data-ttu-id="17f42-152">Ecco un blocco di comando di esempio per l'account denominato belindan@contoso.com, per la licenza contoso:ENTERPRISEPACK e i piani di servizio da disabilitare sono RMS_S_ENTERPRISE, SWAY, INTUNE_O365 e YAMMER_ENTERPRISE:</span><span class="sxs-lookup"><span data-stu-id="17f42-152">Here is an example command block for the account named belindan@contoso.com, for the contoso:ENTERPRISEPACK license, and the service plans to disable are RMS_S_ENTERPRISE, SWAY, INTUNE_O365, and YAMMER_ENTERPRISE:</span></span>

```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a><span data-ttu-id="17f42-153">Per più utenti</span><span class="sxs-lookup"><span data-stu-id="17f42-153">For multiple users</span></span>

<span data-ttu-id="17f42-p109">Per eseguire questa attività di amministrazione per più utenti, creare un file CSV contenente i campi UserPrincipalName e UsageLocation. Ecco un esempio:</span><span class="sxs-lookup"><span data-stu-id="17f42-p109">To perform this administration task for multiple users, create a comma-separated value (CSV) text file that contains the UserPrincipalName and UsageLocation fields. Here is an example:</span></span>

```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

<span data-ttu-id="17f42-156">Successivamente, immettere il percorso dei file CSV di input e output, l'ID SKU dell'account e l'elenco dei piani di servizio da disabilitare, quindi eseguire i comandi risultanti nel prompt dei comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17f42-156">Next, fill in the location of the input and output CSV files, the account SKU ID, and the list of service plans to disable, and then run the resulting commands at the PowerShell command prompt.</span></span>

```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

<span data-ttu-id="17f42-157">Blocco di comando di PowerShell:</span><span class="sxs-lookup"><span data-stu-id="17f42-157">This PowerShell command block:</span></span>

- <span data-ttu-id="17f42-158">Visualizza il nome dell'entità utente di ogni utente.</span><span class="sxs-lookup"><span data-stu-id="17f42-158">Displays the user principal name of each user.</span></span>

- <span data-ttu-id="17f42-159">Assegna licenze personalizzate a ogni utente.</span><span class="sxs-lookup"><span data-stu-id="17f42-159">Assigns customized licenses to each user.</span></span>

- <span data-ttu-id="17f42-160">Crea un file CSV con tutti gli utenti che sono stati elaborati e mostra il relativo stato della licenza.</span><span class="sxs-lookup"><span data-stu-id="17f42-160">Creates a CSV file with all the users that were processed and shows their license status.</span></span>

## <a name="see-also"></a><span data-ttu-id="17f42-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17f42-161">See also</span></span>

[<span data-ttu-id="17f42-162">Disabilitare l'accesso Microsoft 365 servizi con PowerShell</span><span class="sxs-lookup"><span data-stu-id="17f42-162">Disable access to Microsoft 365 services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)

[<span data-ttu-id="17f42-163">Disabilitare l'accesso a Sway con PowerShell</span><span class="sxs-lookup"><span data-stu-id="17f42-163">Disable access to Sway with PowerShell</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)

[<span data-ttu-id="17f42-164">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="17f42-164">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[<span data-ttu-id="17f42-165">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="17f42-165">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)