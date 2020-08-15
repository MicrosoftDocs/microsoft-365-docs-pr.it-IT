---
title: Creare gli account utente di Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: In questo articolo vengono fornite informazioni su come utilizzare PowerShell per creare account utente o più account utente di Microsoft 365.
ms.openlocfilehash: 53077352862b6d0df6bb569300e2d8bc2475df91
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691327"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="e2e8f-103">Creare gli account utente di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2e8f-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="e2e8f-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e2e8f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e2e8f-105">È possibile utilizzare PowerShell per Microsoft 365 per creare efficacemente gli account utente, in particolare più account utente.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, especially multiple user accounts.</span></span> <span data-ttu-id="e2e8f-106">Quando si creano account utente in PowerShell, vengono sempre richieste determinate proprietà dell'account.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="e2e8f-107">Altre proprietà non sono necessarie per creare l'account, ma sono comunque importanti.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-107">Other properties aren't required to create the account, but are otherwise important.</span></span> <span data-ttu-id="e2e8f-108">Tali proprietà sono descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-108">These properties are described in the following table:</span></span>
  
|<span data-ttu-id="e2e8f-109">**Nome della proprietà**</span><span class="sxs-lookup"><span data-stu-id="e2e8f-109">**Property name**</span></span>|<span data-ttu-id="e2e8f-110">**Obbligatorio?**</span><span class="sxs-lookup"><span data-stu-id="e2e8f-110">**Required?**</span></span>|<span data-ttu-id="e2e8f-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e2e8f-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e2e8f-112">**DisplayName**</span><span class="sxs-lookup"><span data-stu-id="e2e8f-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="e2e8f-113">Sì</span><span class="sxs-lookup"><span data-stu-id="e2e8f-113">Yes</span></span>  <br/> |<span data-ttu-id="e2e8f-114">Si tratta del nome visualizzato utilizzato nei servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="e2e8f-115">Ad esempio, Caleb Sills.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-115">For example, Caleb Sills.</span></span>  <br/> |
|<span data-ttu-id="e2e8f-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="e2e8f-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="e2e8f-117">Sì</span><span class="sxs-lookup"><span data-stu-id="e2e8f-117">Yes</span></span>  <br/> |<span data-ttu-id="e2e8f-118">Si tratta del nome dell'account utilizzato per accedere ai servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="e2e8f-119">Ad esempio, CalebS@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-119">For example, CalebS@contoso.onmicrosoft.com.</span></span>  <br/> |
|<span data-ttu-id="e2e8f-120">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="e2e8f-120">**FirstName**</span></span> <br/> |<span data-ttu-id="e2e8f-121">No</span><span class="sxs-lookup"><span data-stu-id="e2e8f-121">No</span></span>  <br/> ||
|<span data-ttu-id="e2e8f-122">**LastName**</span><span class="sxs-lookup"><span data-stu-id="e2e8f-122">**LastName**</span></span> <br/> |<span data-ttu-id="e2e8f-123">No</span><span class="sxs-lookup"><span data-stu-id="e2e8f-123">No</span></span>  <br/> ||
|<span data-ttu-id="e2e8f-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="e2e8f-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="e2e8f-125">No</span><span class="sxs-lookup"><span data-stu-id="e2e8f-125">No</span></span>  <br/> |<span data-ttu-id="e2e8f-126">Si tratta del piano di gestione delle licenze (noto anche come piano di licenza o SKU) da cui viene assegnata una licenza disponibile per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="e2e8f-127">La licenza definisce i servizi Microsoft 365 che sono disponibili per l'account.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-127">The license defines the Microsoft 365 services that are available to account.</span></span> <span data-ttu-id="e2e8f-128">Non è necessario assegnare una licenza a un utente quando si crea l'account, ma l'account richiede una licenza per accedere ai servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-128">You don't have to assign a license to a user when you create the account, but the account requires a license to access Microsoft 365 services.</span></span> <span data-ttu-id="e2e8f-129">Dopo aver creato l'account utente, sono presenti 30 giorni per la licenza.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="e2e8f-130">**Password**</span><span class="sxs-lookup"><span data-stu-id="e2e8f-130">**Password**</span></span> <br/> |<span data-ttu-id="e2e8f-131">No</span><span class="sxs-lookup"><span data-stu-id="e2e8f-131">No</span></span>  <br/> | <span data-ttu-id="e2e8f-p105">Se non si specifica una password, all'account utente ne viene assegnata una casuale, visibile nei risultati del comando. Se si specifica una password, è necessario che contenga da 8 a 16 caratteri di testo ASCII di uno dei tre tipi seguenti: lettere minuscole, lettere maiuscole, numeri e simboli.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-p105">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command. If you specify a password, it needs to be 8 to 16 ASCII text characters from any three of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span> <br/> |
|<span data-ttu-id="e2e8f-134">**UsageLocation**</span><span class="sxs-lookup"><span data-stu-id="e2e8f-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="e2e8f-135">No</span><span class="sxs-lookup"><span data-stu-id="e2e8f-135">No</span></span>  <br/> |<span data-ttu-id="e2e8f-136">Questo è un codice paese valido ISO 3166-1 Alpha-2.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="e2e8f-137">Ad esempio, US per gli Stati Uniti e FR per la Francia.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-137">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="e2e8f-138">È importante fornire questo valore perché alcuni servizi Microsoft 365 non sono disponibili in alcuni paesi, pertanto non è possibile assegnare una licenza a un account utente, a meno che l'account non abbia configurato questo valore.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries, so you can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="e2e8f-139">Per ulteriori informazioni, vedere [informazioni sulle restrizioni di licenza](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="e2e8f-139">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>  <br/> |
   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e2e8f-140">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="e2e8f-140">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e2e8f-141">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="e2e8f-141">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="e2e8f-142">Una volta stabilita la connessione, utilizzare la sintassi seguente per creare un singolo account:</span><span class="sxs-lookup"><span data-stu-id="e2e8f-142">After you have connected, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="e2e8f-143">In questo esempio viene creato un account per l'utente degli Stati Uniti chiamato Caleb Sills:</span><span class="sxs-lookup"><span data-stu-id="e2e8f-143">This example creates an account for the United States user named Caleb Sills:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e2e8f-144">Usare il modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2e8f-144">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e2e8f-145">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="e2e8f-145">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="e2e8f-146">Creare un account utente singolo</span><span class="sxs-lookup"><span data-stu-id="e2e8f-146">Create an individual user account</span></span>

<span data-ttu-id="e2e8f-147">Per creare un singolo account, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e2e8f-147">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="e2e8f-148">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-148">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="e2e8f-149">Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-149">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="e2e8f-150">Per elencare i nomi dei piani di gestione delle licenze disponibili, usare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="e2e8f-150">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="e2e8f-151">In questo esempio viene creato un account per l'utente degli Stati Uniti chiamato Caleb Sills, a cui viene assegnata una licenza dal piano `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="e2e8f-151">This example creates an account for the United States user named Caleb Sills, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="e2e8f-152">Creare più account utente</span><span class="sxs-lookup"><span data-stu-id="e2e8f-152">Create multiple user accounts</span></span>

1. <span data-ttu-id="e2e8f-p108">Creare un file CSV che includa le necessarie informazioni sull'account utente. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e2e8f-p108">Create a comma-separated value (CSV) file that contains the required user account information. For example:</span></span>
    
  ```powershell
  UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
  ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
  LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
  ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
  ```

 > [!NOTE]
><span data-ttu-id="e2e8f-155">I nomi delle colonne e il relativo ordine nella prima riga del file CSV sono arbitrari, ma assicurano che i dati del resto del file corrispondano all'ordine dei nomi delle colonne e utilizzino i nomi delle colonne per i valori del parametro nel comando PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-155">The column names and their order in the first row of the CSV file are arbitrary, but make sure the data in the rest of the file matches the order of the column names, and use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="e2e8f-156">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e2e8f-156">Use the following syntax:</span></span>
    
  ```powershell
  Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
  ```

<span data-ttu-id="e2e8f-157">In questo esempio, vengono creati gli account utente dal file denominato C:\My Documents\NewAccounts.csv, quindi vengono registrati i risultati nel file C:\My Documents\NewAccountResults.csv</span><span class="sxs-lookup"><span data-stu-id="e2e8f-157">This example creates the user accounts from the file named C:\My Documents\NewAccounts.csv, and logs the results in the file named C:\My Documents\NewAccountResults.csv</span></span>
    
  ```powershell
  Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
  ```

3. <span data-ttu-id="e2e8f-158">Esaminare il file di output per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-158">Review the output file to see the results.</span></span> <span data-ttu-id="e2e8f-159">Non sono state specificate le password, pertanto le password casuali generate da Microsoft 365 sono visibili nel file di output.</span><span class="sxs-lookup"><span data-stu-id="e2e8f-159">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e2e8f-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2e8f-160">See also</span></span>

[<span data-ttu-id="e2e8f-161">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2e8f-161">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e2e8f-162">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2e8f-162">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e2e8f-163">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e2e8f-163">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
