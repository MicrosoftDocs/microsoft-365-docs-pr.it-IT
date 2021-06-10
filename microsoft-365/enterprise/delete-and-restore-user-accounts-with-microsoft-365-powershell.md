---
title: Eliminare Microsoft 365 account utente con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Informazioni su come usare moduli diversi in PowerShell per eliminare Microsoft 365 account utente.
ms.openlocfilehash: 32081d1ce0cbc7aac89b337cf8b5d08bc8e43dfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919141"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Eliminare Microsoft 365 account utente con PowerShell

È possibile utilizzare PowerShell per Microsoft 365 per eliminare e ripristinare gli account utente.

>[!Note]
>Informazioni su come [ripristinare un account utente](../admin/add-users/restore-user.md) tramite l'Microsoft 365 di amministrazione.
>
>Per un elenco delle risorse aggiuntive, vedere [Manage users and groups](../admin/add-users/index.yml).
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

Dopo la connessione, utilizzare la sintassi seguente per rimuovere un singolo account utente:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

In questo esempio viene rimosso l'account *utente fabricec \@ litwareinc.com*.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> Il *parametro -ObjectID* nel cmdlet **Remove-AzureADUser** accetta il nome di accesso dell'account, noto anche come Nome entità utente o ID oggetto dell'account.
  
Per visualizzare il nome dell'account in base al nome dell'utente, usare i comandi seguenti:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In questo esempio viene visualizzato il nome dell'account per *l'utente Caleb Sills.*
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Per rimuovere un account in base al nome visualizzato dell'utente, utilizzare i comandi seguenti:
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il modulo di Microsoft Azure Active Directory per Windows PowerShell

Quando si elimina un account utente tramite il modulo Microsoft Azure Active Directory per Windows PowerShell, l'account non viene eliminato definitivamente. Infatti, si hanno a disposizione 30 giorni di tempo per ripristinare l'account utente eliminato.

Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Per eliminare un account utente, utilizzare la sintassi riportata di seguito:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome. Eseguire questi cmdlet da Windows PowerShell.
>

In questo esempio viene eliminato l'account *utente BelindaN@litwareinc.com*.
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Per ripristinare un account utente eliminato entro la fine del periodo di tolleranza di 30 giorni, utilizzare la sintassi seguente:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

In questo esempio viene ripristinato l'account *eliminato BelindaN \@ litwareinc.com*.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> Per visualizzare un elenco di utenti eliminati che possono essere ripristinati, eseguire il comando seguente:
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> Se il nome dell'entità utente originale di un account viene usato da un altro account, fare ricorso al parametro _NewUserPrincipalName_ invece che a quello _UserPrincipalName_ per specificare un differente nome principale dell'utente, quando si ripristina l'account utente.


## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)