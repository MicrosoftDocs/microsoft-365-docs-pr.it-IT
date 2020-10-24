---
title: Creare gli account utente di Microsoft 365 con PowerShell
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
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Come utilizzare PowerShell per creare singoli o più account utente di Microsoft 365.
ms.openlocfilehash: d96de72ca3e7c4a439665c3ebf751a8fe25ce572
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754211"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="3564e-103">Creare gli account utente di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3564e-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="3564e-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3564e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3564e-105">È possibile utilizzare PowerShell per Microsoft 365 per creare efficacemente gli account utente, inclusi più account.</span><span class="sxs-lookup"><span data-stu-id="3564e-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, including multiple accounts.</span></span>

<span data-ttu-id="3564e-106">Quando si creano account utente in PowerShell, vengono sempre richieste determinate proprietà dell'account.</span><span class="sxs-lookup"><span data-stu-id="3564e-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="3564e-107">Altre proprietà non sono necessarie, ma sono importanti.</span><span class="sxs-lookup"><span data-stu-id="3564e-107">Other properties aren't required but are important.</span></span> <span data-ttu-id="3564e-108">Vedere la tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3564e-108">See the following table.</span></span>
  
|<span data-ttu-id="3564e-109">**Nome della proprietà**</span><span class="sxs-lookup"><span data-stu-id="3564e-109">**Property name**</span></span>|<span data-ttu-id="3564e-110">**Obbligatorio?**</span><span class="sxs-lookup"><span data-stu-id="3564e-110">**Required?**</span></span>|<span data-ttu-id="3564e-111">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="3564e-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3564e-112">**DisplayName**</span><span class="sxs-lookup"><span data-stu-id="3564e-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="3564e-113">Sì</span><span class="sxs-lookup"><span data-stu-id="3564e-113">Yes</span></span>  <br/> |<span data-ttu-id="3564e-114">Si tratta del nome visualizzato utilizzato nei servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3564e-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="3564e-115">Ad esempio, *Caleb davanzali*.</span><span class="sxs-lookup"><span data-stu-id="3564e-115">For example, *Caleb Sills*.</span></span> <br/> |
|<span data-ttu-id="3564e-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="3564e-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="3564e-117">Sì</span><span class="sxs-lookup"><span data-stu-id="3564e-117">Yes</span></span>  <br/> |<span data-ttu-id="3564e-118">Si tratta del nome dell'account utilizzato per accedere ai servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3564e-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="3564e-119">Ad esempio, *calebs \@ contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="3564e-119">For example, *CalebS\@contoso.onmicrosoft.com*.</span></span>  <br/> |
|<span data-ttu-id="3564e-120">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="3564e-120">**FirstName**</span></span> <br/> |<span data-ttu-id="3564e-121">No</span><span class="sxs-lookup"><span data-stu-id="3564e-121">No</span></span>  <br/> ||
|<span data-ttu-id="3564e-122">**LastName**</span><span class="sxs-lookup"><span data-stu-id="3564e-122">**LastName**</span></span> <br/> |<span data-ttu-id="3564e-123">No</span><span class="sxs-lookup"><span data-stu-id="3564e-123">No</span></span>  <br/> ||
|<span data-ttu-id="3564e-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="3564e-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="3564e-125">No</span><span class="sxs-lookup"><span data-stu-id="3564e-125">No</span></span>  <br/> |<span data-ttu-id="3564e-126">Si tratta del piano di gestione delle licenze (noto anche come piano di licenza o SKU) da cui viene assegnata una licenza disponibile per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="3564e-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="3564e-127">La licenza definisce i servizi Microsoft 365 che sono disponibili per l'account.</span><span class="sxs-lookup"><span data-stu-id="3564e-127">The license defines the Microsoft 365 services that are available to the account.</span></span> <span data-ttu-id="3564e-128">Non è necessario assegnare una licenza a un utente quando si crea l'account, ma l'account deve disporre di una licenza per accedere ai servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3564e-128">You don't have to assign a license to a user when you create the account, but the account must have a license to access Microsoft 365 services.</span></span> <span data-ttu-id="3564e-129">Dopo aver creato l'account utente, sono presenti 30 giorni per la licenza.</span><span class="sxs-lookup"><span data-stu-id="3564e-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="3564e-130">**Password**</span><span class="sxs-lookup"><span data-stu-id="3564e-130">**Password**</span></span> <br/> |<span data-ttu-id="3564e-131">No</span><span class="sxs-lookup"><span data-stu-id="3564e-131">No</span></span>  <br/> | <span data-ttu-id="3564e-132">Se non si specifica una password, all'account utente ne viene assegnata una casuale, visibile nei risultati del comando.</span><span class="sxs-lookup"><span data-stu-id="3564e-132">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command.</span></span> <span data-ttu-id="3564e-133">Se si specifica una password, è necessario che siano presenti da 8 a 16 caratteri di testo ASCII dei tipi seguenti: lettere minuscole, lettere maiuscole, numeri e simboli.</span><span class="sxs-lookup"><span data-stu-id="3564e-133">If you specify a password, it needs to be 8 to 16 ASCII text characters of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span><br/> |
|<span data-ttu-id="3564e-134">**UsageLocation**</span><span class="sxs-lookup"><span data-stu-id="3564e-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="3564e-135">No</span><span class="sxs-lookup"><span data-stu-id="3564e-135">No</span></span>  <br/> |<span data-ttu-id="3564e-136">Questo è un codice paese valido ISO 3166-1 Alpha-2.</span><span class="sxs-lookup"><span data-stu-id="3564e-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="3564e-137">Ad esempio, *US* per gli Stati Uniti e *fr* per la Francia.</span><span class="sxs-lookup"><span data-stu-id="3564e-137">For example, *US* for the United States, and *FR* for France.</span></span> <span data-ttu-id="3564e-138">È importante fornire questo valore, perché alcuni servizi Microsoft 365 non sono disponibili in alcuni paesi.</span><span class="sxs-lookup"><span data-stu-id="3564e-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="3564e-139">Non è possibile assegnare una licenza a un account utente, a meno che il valore dell'account non sia configurato.</span><span class="sxs-lookup"><span data-stu-id="3564e-139">You can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="3564e-140">Per ulteriori informazioni, vedere [informazioni sulle restrizioni di licenza](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="3564e-140">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span><br/> |

>[!Note]
><span data-ttu-id="3564e-141">[Informazioni su come creare account utente](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) utilizzando l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3564e-141">[Learn how to create user accounts](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) by using the Microsoft 365 admin center.</span></span>
> 
> <span data-ttu-id="3564e-142">Per un elenco di risorse aggiuntive, vedere [Manage Users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="3564e-142">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="3564e-143">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="3564e-143">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="3564e-144">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="3564e-144">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="3564e-145">Dopo aver eseguito la connessione, utilizzare la sintassi seguente per creare un singolo account:</span><span class="sxs-lookup"><span data-stu-id="3564e-145">After you connect, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="3564e-146">In questo esempio viene creato un account per l'utente statunitense *Caleb davanzali*:</span><span class="sxs-lookup"><span data-stu-id="3564e-146">This example creates an account for the US user *Caleb Sills*:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="3564e-147">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3564e-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="3564e-148">Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="3564e-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="3564e-149">Creare un account utente singolo</span><span class="sxs-lookup"><span data-stu-id="3564e-149">Create an individual user account</span></span>

<span data-ttu-id="3564e-150">Per creare un singolo account, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3564e-150">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="3564e-151">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per il modulo di Windows PowerShell e i cmdlet che dispongono di *MSOL* nel proprio nome.</span><span class="sxs-lookup"><span data-stu-id="3564e-151">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="3564e-152">Eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3564e-152">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="3564e-153">Per elencare i nomi dei piani di gestione delle licenze disponibili, usare il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="3564e-153">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="3564e-154">In questo esempio viene creato un account per l'utente statunitense *Caleb davanzali*e viene assegnata una licenza dal `contoso:ENTERPRISEPACK` piano di gestione delle licenze (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="3564e-154">This example creates an account for the US user *Caleb Sills*, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="3564e-155">Creare più account utente</span><span class="sxs-lookup"><span data-stu-id="3564e-155">Create multiple user accounts</span></span>

1. <span data-ttu-id="3564e-p108">Creare un file CSV che includa le necessarie informazioni sull'account utente. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3564e-p108">Create a comma-separated value (CSV) file that contains the required user account information. For example:</span></span>

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   ><span data-ttu-id="3564e-158">I nomi delle colonne e il relativo ordine nella prima riga del file CSV sono arbitrari.</span><span class="sxs-lookup"><span data-stu-id="3564e-158">The column names and their order in the first row of the CSV file are arbitrary.</span></span> <span data-ttu-id="3564e-159">Tuttavia, verificare che l'ordine dei dati nel resto del file corrisponda all'ordine dei nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="3564e-159">But make sure the order of the data in the rest of the file matches the order of the column names.</span></span> <span data-ttu-id="3564e-160">E utilizzare i nomi di colonna per i valori dei parametri nel comando PowerShell per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3564e-160">And use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="3564e-161">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="3564e-161">Use the following syntax:</span></span>
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   <span data-ttu-id="3564e-162">In questo esempio vengono creati gli account utente dal file *C:\My Documents\NewAccounts.csv* e i risultati vengono registrati in un file denominato *C:\My Documents\NewAccountResults.csv*.</span><span class="sxs-lookup"><span data-stu-id="3564e-162">This example creates user accounts from the file *C:\My Documents\NewAccounts.csv* and logs the results in a file named *C:\My Documents\NewAccountResults.csv*.</span></span>
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. <span data-ttu-id="3564e-163">Esaminare il file di output per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="3564e-163">Review the output file to see the results.</span></span> <span data-ttu-id="3564e-164">Non sono state specificate le password, pertanto le password casuali generate da Microsoft 365 sono visibili nel file di output.</span><span class="sxs-lookup"><span data-stu-id="3564e-164">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3564e-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3564e-165">See also</span></span>

[<span data-ttu-id="3564e-166">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3564e-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3564e-167">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="3564e-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="3564e-168">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3564e-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
