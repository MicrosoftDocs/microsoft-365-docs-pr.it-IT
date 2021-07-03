---
title: Bloccare Microsoft 365 account utente con PowerShell
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
description: Come usare PowerShell per bloccare e sbloccare l'accesso Microsoft 365 account.
ms.openlocfilehash: 90d712cdb6eb34d0588fc262e3a02673accfbd9e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287222"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="7e1d4-103">Bloccare Microsoft 365 account utente con PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e1d4-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="7e1d4-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="7e1d4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7e1d4-105">Quando si blocca l'accesso a un account Microsoft 365, si impedisce a chiunque di usare l'account per accedere ai servizi e ai dati nell'organizzazione Microsoft 365 aziendale.</span><span class="sxs-lookup"><span data-stu-id="7e1d4-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="7e1d4-106">È possibile utilizzare PowerShell per bloccare l'accesso a singoli o più account utente.</span><span class="sxs-lookup"><span data-stu-id="7e1d4-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="7e1d4-107">Usare il modulo di Azure Active Directory PowerShell per Graph</span><span class="sxs-lookup"><span data-stu-id="7e1d4-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="7e1d4-108">Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="7e1d4-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="7e1d4-109">Bloccare l'accesso a singoli account utente</span><span class="sxs-lookup"><span data-stu-id="7e1d4-109">Block access to individual user accounts</span></span>

<span data-ttu-id="7e1d4-110">Utilizzare la sintassi seguente per bloccare un singolo account utente:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-110">Use the following syntax to block an individual user account:</span></span>

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="7e1d4-111">Il *parametro -ObjectID* nel cmdlet **Set-AzureAD** accetta il nome di accesso dell'account, noto anche come nome dell'entità utente, o l'ID oggetto dell'account.</span><span class="sxs-lookup"><span data-stu-id="7e1d4-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>

<span data-ttu-id="7e1d4-112">In questo esempio viene limitato l'accesso all'account *utente fabricec@litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="7e1d4-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="7e1d4-113">Per sbloccare questo account utente, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-113">To unblock this user account, run the following command:</span></span>

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="7e1d4-114">Per visualizzare l'UPN dell'account utente in base al nome visualizzato dell'utente, utilizzare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>

```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="7e1d4-115">In questo esempio viene visualizzato l'UPN dell'account utente *Caleb Sills.*</span><span class="sxs-lookup"><span data-stu-id="7e1d4-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>

```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="7e1d4-116">Per bloccare un account in base al nome visualizzato dell'utente, utilizzare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-116">To block an account based on the user's display name, use the following commands:</span></span>

```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="7e1d4-117">Per verificare lo stato bloccato di un account utente, utilizzare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-117">To check the blocked status of a user account use the following command:</span></span>

```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="7e1d4-118">Bloccare più account utente</span><span class="sxs-lookup"><span data-stu-id="7e1d4-118">Block multiple user accounts</span></span>

<span data-ttu-id="7e1d4-119">Per bloccare l'accesso a più account utente, creare un file di testo contenente un nome di accesso per l'account in ogni riga in questo modo:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="7e1d4-120">Nei comandi seguenti, il file di testo di esempio *è C:\My Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="7e1d4-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="7e1d4-121">Sostituire questo nome di file con il percorso e il nome del file di testo.</span><span class="sxs-lookup"><span data-stu-id="7e1d4-121">Replace this file name with the path and file name of your text file.</span></span>

<span data-ttu-id="7e1d4-122">Per bloccare l'accesso agli account elencati nel file di testo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-122">To block access to the accounts listed in the text file, run the following command:</span></span>

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

<span data-ttu-id="7e1d4-123">Per sbloccare gli account elencati nel file di testo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="7e1d4-124">Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e1d4-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="7e1d4-125">Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="7e1d4-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="block-individual-user-accounts"></a><span data-ttu-id="7e1d4-126">Bloccare singoli account utente</span><span class="sxs-lookup"><span data-stu-id="7e1d4-126">Block individual user accounts</span></span>

<span data-ttu-id="7e1d4-127">Utilizzare la sintassi seguente per bloccare l'accesso a un singolo account utente:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-127">Use the following syntax to block access for an individual user account:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="7e1d4-128">PowerShell Core non supporta il modulo Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* nel nome.</span><span class="sxs-lookup"><span data-stu-id="7e1d4-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="7e1d4-129">È necessario eseguire questi cmdlet da Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7e1d4-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="7e1d4-130">In questo esempio viene limitato l'accesso all'account *utente fabricec \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="7e1d4-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>

```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="7e1d4-131">Per sbloccare l'account utente, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-131">To unblock the user account, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="7e1d4-132">Per verificare lo stato bloccato di un account utente, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-132">To check the blocked status of a user account run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="7e1d4-133">Bloccare l'accesso per più account utente</span><span class="sxs-lookup"><span data-stu-id="7e1d4-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="7e1d4-134">Prima di tutto, crea un file di testo contenente un account in ogni riga come questo:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-134">First, create a text file that contains one account on each line like this:</span></span>

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="7e1d4-135">Nei comandi seguenti, il file di testo di esempio *è C:\My Documents\Accounts.txt*.</span><span class="sxs-lookup"><span data-stu-id="7e1d4-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="7e1d4-136">Sostituire questo nome di file con il percorso e il nome del file di testo.</span><span class="sxs-lookup"><span data-stu-id="7e1d4-136">Replace this file name with the path and file name of your text file.</span></span>

<span data-ttu-id="7e1d4-137">Per bloccare l'accesso per gli account elencati nel file di testo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="7e1d4-138">Per sbloccare gli account elencati nel file di testo, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="7e1d4-138">To unblock the accounts listed in the text file, run the following command:</span></span>

  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="7e1d4-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e1d4-139">See also</span></span>

[<span data-ttu-id="7e1d4-140">Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e1d4-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[<span data-ttu-id="7e1d4-141">Gestire Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="7e1d4-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="7e1d4-142">Guida introduttiva a PowerShell per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7e1d4-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
