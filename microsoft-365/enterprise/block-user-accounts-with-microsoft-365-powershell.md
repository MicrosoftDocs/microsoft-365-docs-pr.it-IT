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
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Bloccare gli account utente di Microsoft 365 con PowerShell

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Quando si blocca l'accesso a un account Microsoft 365, si impedisce a tutti gli utenti di utilizzare l'account per accedere ai servizi e ai dati dell'organizzazione Microsoft 365. È possibile utilizzare PowerShell per bloccare l'accesso a singoli o più account utente.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
 
### <a name="block-access-to-individual-user-accounts"></a>Blocca l'accesso a singoli account utente

Per bloccare un singolo account utente, utilizzare la sintassi seguente:
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> Il parametro *-ObjectID* nel cmdlet **set-AzureAD** accetta sia il nome di accesso dell'account, noto anche come nome dell'entità utente, sia l'ID oggetto dell'account.
  
In questo esempio viene bloccato l'accesso all'account utente *fabricec@litwareinc.com*.
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

Per sbloccare questo account utente, eseguire il comando riportato di seguito:
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

Per visualizzare l'UPN dell'account utente in base al nome visualizzato dell'utente, utilizzare i comandi seguenti:
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

In questo esempio viene visualizzato l'UPN dell'account utente per l'utente  *davanzali Caleb*.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Per bloccare un account in base al nome visualizzato dell'utente, utilizzare i comandi seguenti:
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

Per controllare lo stato bloccato di un account utente, utilizzare il seguente comando:
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>Blocca più account utente

Per bloccare l'accesso a più account utente, creare un file di testo contenente un nome di accesso all'account su ogni riga simile alla seguente:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

Nei comandi seguenti, il file di testo di esempio è *C:\My Documents\Accounts.txt*. Sostituire il nome del file con il percorso e il nome del file di testo.
  
Per bloccare l'accesso agli account elencati nel file di testo, eseguire il comando seguente:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

Per sbloccare gli account elencati nel file di testo, eseguire il comando riportato di seguito:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
### <a name="block-individual-user-accounts"></a>Blocca singoli account utente

Utilizzare la seguente sintassi per bloccare l'accesso per un singolo account utente:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per il modulo di Windows PowerShell e i cmdlet che dispongono di *MSOL* nel proprio nome. È necessario eseguire questi cmdlet da Windows PowerShell.

In questo esempio viene bloccato l'accesso all'account utente *fabricec \@ litwareinc.com*.
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

Per sbloccare l'account utente, eseguire il comando riportato di seguito:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

Per controllare lo stato bloccato di un account utente, eseguire il comando riportato di seguito:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>Blocca l'accesso per più account utente

Per prima cosa, creare un file di testo contenente un account su ogni riga come riportato di questo tipo:
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

Nei comandi seguenti, il file di testo di esempio è *C:\My Documents\Accounts.txt*. Sostituire il nome del file con il percorso e il nome del file di testo.
    
Per bloccare l'accesso per gli account elencati nel file di testo, eseguire il comando riportato di seguito:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
Per sbloccare gli account elencati nel file di testo, eseguire il comando seguente:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
