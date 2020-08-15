---
title: Disabilitare l'accesso ai servizi di Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: In questo articolo vengono fornite informazioni su come utilizzare PowerShell per disabilitare l'accesso ai servizi di Microsoft 365 per gli utenti.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691176"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a><span data-ttu-id="5a9bc-103">Disabilitare l'accesso ai servizi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a9bc-103">Disable access to Microsoft 365 services with PowerShell</span></span>

<span data-ttu-id="5a9bc-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5a9bc-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5a9bc-105">Quando a un account Microsoft 365 viene assegnata una licenza da un piano di gestione delle licenze, i servizi Microsoft 365 vengono resi disponibili all'utente dalla licenza.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-105">When a Microsoft 365 account is assigned a license from a licensing plan, Microsoft 365 services are made available to the user from that license.</span></span> <span data-ttu-id="5a9bc-106">Tuttavia, è possibile controllare i servizi Microsoft 365 che l'utente può accedere.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-106">However, you can control the Microsoft 365 services that the user can access.</span></span> <span data-ttu-id="5a9bc-107">Ad esempio, anche se la licenza consente l'accesso al servizio SharePoint Online, è possibile disabilitarne l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-107">For example, even though the license allows access to the SharePoint Online service, you can disable access to it.</span></span> <span data-ttu-id="5a9bc-108">È possibile utilizzare PowerShell per disabilitare l'accesso a qualsiasi numero di servizi per uno specifico piano di gestione delle licenze per:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-108">You can use PowerShell to disable access to any number of services for a specific licensing plan for:</span></span>

- <span data-ttu-id="5a9bc-109">Un singolo account.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-109">An individual account.</span></span>
- <span data-ttu-id="5a9bc-110">Un gruppo di account.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-110">A group of accounts.</span></span>
- <span data-ttu-id="5a9bc-111">Tutti gli account nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-111">All accounts in your organization.</span></span>

>[!Note]
><span data-ttu-id="5a9bc-112">Esistono dipendenze del servizio Microsoft 365 che possono impedire la disabilitazione di un servizio specificato quando altri servizi dipendono da esso.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-112">There are Microsoft 365 service dependencies that can prevent you from disabling a specified service when other services depend on it.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="5a9bc-113">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a9bc-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="5a9bc-114">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5a9bc-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="5a9bc-115">Successivamente, utilizzare questo comando per visualizzare i piani di licenza disponibili, noti anche come AccountSkuIds:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-115">Next, use this command to view your available licensing plans, also known as AccountSkuIds:</span></span>

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
><span data-ttu-id="5a9bc-116">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-116">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="5a9bc-117">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-117">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="5a9bc-118">Per ulteriori informazioni, vedere [visualizzare le licenze e i servizi con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5a9bc-118">For more information, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="5a9bc-119">Per visualizzare i risultati precedenti e successivi delle procedure descritte in questo argomento, vedere [View account License and Service details with PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5a9bc-119">To see the before and after results of the procedures in this topic, see [View account license and service details with PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="5a9bc-120">Uno script PowerShell è disponibile per rendere automatiche le procedure descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-120">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="5a9bc-121">Nello specifico, lo script consente di visualizzare e disabilitare i servizi nell'organizzazione Microsoft 365, tra cui Sway.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-121">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="5a9bc-122">Per ulteriori informazioni, vedere [disabilitare l'accesso a Sway con PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5a9bc-122">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a><span data-ttu-id="5a9bc-123">Disabilitare servizi Microsoft 365 specifici per utenti specifici per uno specifico piano di gestione delle licenze</span><span class="sxs-lookup"><span data-stu-id="5a9bc-123">Disable specific Microsoft 365 services for specific users for a specific licensing plan</span></span>
  
<span data-ttu-id="5a9bc-124">Per disabilitare un set specifico di servizi Microsoft 365 per gli utenti per uno specifico piano di gestione delle licenze, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-124">To disable a specific set of Microsoft 365 services for users for a specific licensing plan, perform the following steps:</span></span>
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a><span data-ttu-id="5a9bc-125">Passaggio 1: identificare i servizi indesiderati nel piano di gestione delle licenze utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-125">Step 1: Identify the undesirable services in the licensing plan by using the following syntax:</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

<span data-ttu-id="5a9bc-126">Nell'esempio seguente viene creato un oggetto **LicenseOptions** che Disabilita i servizi Office e SharePoint Online nel piano di gestione delle licenze denominato `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="5a9bc-126">The following example creates a **LicenseOptions** object that disables the Office and SharePoint Online services in the licensing plan named `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a><span data-ttu-id="5a9bc-127">Passaggio 2: utilizzare l'oggetto **LicenseOptions** del passaggio 1 su uno o più utenti.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-127">Step 2: Use the **LicenseOptions** object from Step 1 on one or more users.</span></span>
    
<span data-ttu-id="5a9bc-128">Per creare un nuovo account con i servizi disabilitati, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-128">To create a new account that has the services disabled, use the following syntax:</span></span>
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

<span data-ttu-id="5a9bc-129">Nell'esempio seguente viene creato un nuovo account per Allie Bellew che assegna la licenza e Disabilita i servizi descritti nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-129">The following example creates a new account for Allie Bellew that assigns the license and disables the services described in Step 1.</span></span>
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

<span data-ttu-id="5a9bc-130">Per ulteriori informazioni sulla creazione di account utente in PowerShell per Microsoft 365, vedere [creare account utente con PowerShell](create-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5a9bc-130">For more information about creating user accounts in PowerShell for Microsoft 365, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="5a9bc-131">Per disabilitare i servizi per un utente dotato di una licenza esistente, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-131">To disable the services for an existing licensed user, use the following syntax:</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

<span data-ttu-id="5a9bc-132">In questo esempio vengono disabilitati i servizi per l'utente BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-132">This example disables the services for the user BelindaN@litwareinc.com.</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

<span data-ttu-id="5a9bc-133">Per disabilitare i servizi descritti nel passaggio 1 per tutti gli utenti con licenza esistenti, specificare il nome del piano Microsoft 365 dalla visualizzazione del cmdlet **Get-MsolAccountSku** (ad esempio **litwareinc: ENTERPRISEPACK**) e quindi eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-133">To disable the services described in Step 1 for all existing licensed users, specify the name of your Microsoft 365 plan from the display of the **Get-MsolAccountSku** cmdlet (such as **litwareinc:ENTERPRISEPACK**), and then run the following commands:</span></span>
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 <span data-ttu-id="5a9bc-134">Se si utilizza il cmdlet **Get-MsolUser** senza utilizzare il parametro _All_ , vengono restituiti solo i primi account utente 500.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-134">If you use the **Get-MsolUser** cmdlet without using the _All_ parameter, only the first 500 user accounts are returned.</span></span>

<span data-ttu-id="5a9bc-135">Per disabilitare i servizi per un gruppo di utenti esistenti, utilizzare uno dei metodi seguenti per identificare gli utenti:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-135">To disable the services for a group of existing users, use either of the following methods to identify the users:</span></span>
    
<span data-ttu-id="5a9bc-136">**Metodo 1. Filtrare gli account in base a un attributo account esistente**</span><span class="sxs-lookup"><span data-stu-id="5a9bc-136">**Method 1. Filter the accounts based on an existing account attribute**</span></span> 

<span data-ttu-id="5a9bc-137">A tal fine, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-137">To do this, use the following syntax:</span></span>
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="5a9bc-138">Nell'esempio seguente vengono disabilitati i servizi per gli utenti nel reparto vendite degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-138">The following example disables the services for users in the Sales department in the United States.</span></span>
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="5a9bc-139">**Metodo 2: utilizzare un elenco di account specifici**</span><span class="sxs-lookup"><span data-stu-id="5a9bc-139">**Method 2: Use a list of specific accounts**</span></span> 

<span data-ttu-id="5a9bc-140">A tal fine, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-140">To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="5a9bc-141">Creare un file di testo contenente un account su ogni riga come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-141">Create a text file that contains one account on each line like this:</span></span>
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   <span data-ttu-id="5a9bc-142">In questo esempio, il file di testo è C: \\ My documents \\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-142">In this example, the text file is C:\\My Documents\\Accounts.txt.</span></span>
    
2. <span data-ttu-id="5a9bc-143">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-143">Run the following command:</span></span>
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

<span data-ttu-id="5a9bc-144">Se si desidera disabilitare l'accesso ai servizi per più piani di gestione delle licenze, ripetere le istruzioni sopra riportate per ogni piano di gestione delle licenze, garantendo che:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-144">If you want to disable access to services for multiple licensing plans, repeat the above instructions for each licensing plan, ensuring that:</span></span>

- <span data-ttu-id="5a9bc-145">Agli account utente è stato assegnato il piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-145">The user accounts have been assigned the licensing plan.</span></span>
- <span data-ttu-id="5a9bc-146">I servizi da disabilitare sono disponibili nel piano di gestione delle licenze.</span><span class="sxs-lookup"><span data-stu-id="5a9bc-146">The services to disable are available in the licensing plan.</span></span>

<span data-ttu-id="5a9bc-147">Per disabilitare i servizi Microsoft 365 per gli utenti mentre si assegnano a un piano di gestione delle licenze, vedere [disabilitare l'accesso ai servizi durante l'assegnazione di licenze utente](disable-access-to-services-while-assigning-user-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="5a9bc-147">To disable Microsoft 365 services for users while you are assigning them to a licensing plan, see [Disable access to services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</span></span>

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a><span data-ttu-id="5a9bc-148">Assegnare tutti i servizi in un piano di gestione delle licenze a un account utente</span><span class="sxs-lookup"><span data-stu-id="5a9bc-148">Assign all services in a licensing plan to a user account</span></span>

<span data-ttu-id="5a9bc-149">Per gli account utente che dispongono di servizi disattivati, è possibile abilitare tutti i servizi per uno specifico piano di gestione delle licenze con questi comandi:</span><span class="sxs-lookup"><span data-stu-id="5a9bc-149">For user accounts that have had services disabled, you can enable all services for a specific licensing plan with these commands:</span></span>

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a><span data-ttu-id="5a9bc-150">Argomento correlato</span><span class="sxs-lookup"><span data-stu-id="5a9bc-150">Related topic</span></span>

[<span data-ttu-id="5a9bc-151">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a9bc-151">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5a9bc-152">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a9bc-152">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5a9bc-153">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5a9bc-153">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
