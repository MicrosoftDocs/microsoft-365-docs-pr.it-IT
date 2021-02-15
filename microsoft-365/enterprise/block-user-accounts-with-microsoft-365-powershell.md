---
title: Bloccare gli account utente di Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: Come usare PowerShell per bloccare e sbloccare l'accesso agli account di Microsoft 365.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754681"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="d4286-103">Bloccare gli account utente di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4286-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="d4286-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="d4286-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d4286-105">Quando si blocca l'accesso a un account di Microsoft 365, si impedisce a chiunque di usare l'account per accedere ai servizi e ai dati nell'organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4286-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="d4286-106">È possibile utilizzare PowerShell per bloccare l'accesso a uno o più account utente.</span><span class="sxs-lookup"><span data-stu-id="d4286-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="d4286-107">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="d4286-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="d4286-108">Prima di [tutto, connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="d4286-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="d4286-109">Bloccare l'accesso a singoli account utente</span><span class="sxs-lookup"><span data-stu-id="d4286-109">Block access to individual user accounts</span></span>

<span data-ttu-id="d4286-110">Utilizzare la sintassi seguente per bloccare un singolo account utente:</span><span class="sxs-lookup"><span data-stu-id="d4286-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="d4286-111">Il *parametro -ObjectID* nel cmdlet **Set-AzureAD** accetta il nome di accesso dell'account, noto anche come nome dell'entità utente, o l'ID oggetto dell'account.</span><span class="sxs-lookup"><span data-stu-id="d4286-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="d4286-112">In questo esempio viene limitato l'accesso all'account *utente fabricec@litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="d4286-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="d4286-113">Per sbloccare questo account utente, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d4286-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="d4286-114">Per visualizzare l'UPN dell'account utente in base al nome visualizzato dell'utente, utilizzare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4286-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="d4286-115">In questo esempio viene visualizzato l'UPN dell'account utente *Caleb Sills.*</span><span class="sxs-lookup"><span data-stu-id="d4286-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="d4286-116">Per bloccare un account in base al nome visualizzato dell'utente, utilizzare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4286-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="d4286-117">Per controllare lo stato bloccato di un account utente, utilizzare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d4286-117">To check the blocked status of a user account use the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="d4286-118">Bloccare più account utente</span><span class="sxs-lookup"><span data-stu-id="d4286-118">Block multiple user accounts</span></span>

<span data-ttu-id="d4286-119">Per bloccare l'accesso per più account utente, creare un file di testo contenente un nome di accesso per l'account in ogni riga simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d4286-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="d4286-120">Nei comandi seguenti il file di testo di esempio è *C:\My Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="d4286-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="d4286-121">Sostituire questo nome file con il percorso e il nome del file di testo.</span><span class="sxs-lookup"><span data-stu-id="d4286-121">Replace this file name with the path and file name of your text file.</span></span>
  
<span data-ttu-id="d4286-122">Per bloccare l'accesso agli account elencati nel file di testo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d4286-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="d4286-123">Per sbloccare gli account elencati nel file di testo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d4286-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="d4286-124">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4286-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="d4286-125">Prima di [tutto, connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="d4286-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-individual-user-accounts"></a><span data-ttu-id="d4286-126">Bloccare singoli account utente</span><span class="sxs-lookup"><span data-stu-id="d4286-126">Block individual user accounts</span></span>

<span data-ttu-id="d4286-127">Utilizzare la sintassi seguente per bloccare l'accesso per un singolo account utente:</span><span class="sxs-lookup"><span data-stu-id="d4286-127">Use the following syntax to block access for an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="d4286-128">PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* nel nome.</span><span class="sxs-lookup"><span data-stu-id="d4286-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="d4286-129">È necessario eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4286-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="d4286-130">In questo esempio viene limitato l'accesso all'account *utente fabricec \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="d4286-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="d4286-131">Per sbloccare l'account utente, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d4286-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="d4286-132">Per verificare lo stato bloccato di un account utente, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d4286-132">To check the blocked status of a user account run the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="d4286-133">Bloccare l'accesso per più account utente</span><span class="sxs-lookup"><span data-stu-id="d4286-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="d4286-134">Prima di tutto, crea un file di testo che contiene un account in ogni riga, come nel seguente:</span><span class="sxs-lookup"><span data-stu-id="d4286-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="d4286-135">Nei comandi seguenti il file di testo di esempio è *C:\My Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="d4286-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="d4286-136">Sostituire questo nome file con il percorso e il nome del file di testo.</span><span class="sxs-lookup"><span data-stu-id="d4286-136">Replace this file name with the path and file name of your text file.</span></span>
    
<span data-ttu-id="d4286-137">Per bloccare l'accesso per gli account elencati nel file di testo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d4286-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="d4286-138">Per sbloccare gli account elencati nel file di testo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d4286-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="d4286-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4286-139">See also</span></span>

[<span data-ttu-id="d4286-140">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4286-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d4286-141">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4286-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d4286-142">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d4286-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
