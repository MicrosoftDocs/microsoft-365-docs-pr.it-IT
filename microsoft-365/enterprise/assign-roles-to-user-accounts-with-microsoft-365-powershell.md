---
title: Assegnare ruoli agli account utente di Microsoft 365 con PowerShell
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
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: In questo articolo viene illustrato come usare PowerShell per Microsoft 365 in modo rapido e semplice per assegnare ruoli di amministratore agli account utente.
ms.openlocfilehash: 84e785052c970ca15487540c3904eacdd0e9ca28
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905381"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>Assegnare ruoli di amministratore agli account utente di Microsoft 365 con PowerShell

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

È possibile assegnare facilmente ruoli agli account utente tramite PowerShell per Microsoft 365.

>[!Note]
>Informazioni su come  [assegnare ruoli di amministratore](../admin/add-users/assign-admin-roles.md) agli account utente con l'interfaccia di amministrazione di Microsoft 365.
>
>Per un elenco delle risorse aggiuntive, vedere [Manage users and groups](../admin/add-users/index.yml).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Innanzitutto, utilizzare un account amministratore globale [per connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Identificare quindi il nome di accesso dell'account utente che si desidera aggiungere a un ruolo (ad esempio: fredsm \@ contoso.com). Questo nome è noto anche come nome dell'entità utente (UPN).

Successivamente, determinare il nome del ruolo. Vedere [autorizzazioni del ruolo di amministratore in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

>[!Note]
>Prestare attenzione alle note in questo articolo. Alcuni nomi di ruolo sono diversi per Azure Active Directory (Azure AD) PowerShell. Ad esempio, il ruolo *di amministratore di SharePoint* nell'interfaccia di amministrazione di Microsoft 365 è Amministratore del servizio *SharePoint* in Azure AD PowerShell.
>

Quindi, inserire i nomi di accesso e di ruolo ed eseguire questi comandi:
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Ecco un esempio di un set di comandi completato che assegna il ruolo di amministratore del servizio SharePoint all'account *di contoso.com \@ belindan:*
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

Per visualizzare l'elenco dei nomi utente per uno specifico ruolo di amministratore, utilizzare questi comandi.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Innanzitutto, utilizzare un account amministratore globale [per connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
### <a name="for-a-single-role-change"></a>Per una singola modifica del ruolo

I modi più comuni per specificare l'account utente sono il nome visualizzato o il nome di posta elettronica, noto anche come nome di accesso o nome dell'entità utente (UPN).

#### <a name="display-names-of-user-accounts"></a>Nomi visualizzati degli account utente

Se si è utilizzati per utilizzare i nomi visualizzati degli account utente, determinare le informazioni seguenti:
  
- L'account utente che si desidera configurare
    
    Per specificare l'account utente, è necessario determinare il nome visualizzato. Per ottenere un elenco completo degli account, utilizzare questo comando:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Questo comando elenca il nome visualizzato degli account utente, ordinati per nome visualizzato, una schermata alla volta. È possibile filtrare l'elenco in un set più piccolo utilizzando il cmdlet **Where**. Vedere l'esempio seguente.

   >[!Note]
   >PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome. Eseguire questi cmdlet da Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Questo comando elenca solo gli account utente per cui il nome visualizzato inizia con "John".
    
- Ruolo che si desidera assegnare
    
    Per visualizzare l'elenco dei ruoli di amministratore disponibili che è possibile assegnare agli account utente, utilizzare questo comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Dopo aver determinato il nome visualizzato dell'account e il nome del ruolo, utilizzare questi comandi per assegnare il ruolo all'account:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Incollare i comandi nel Blocco note. Per le *variabili $dispName* *e $roleName,* sostituire il testo della descrizione con i relativi valori. Rimuovere i \< and > caratteri ma mantenere le virgolette. Incollare le righe modificate nel modulo di Microsoft Azure Active Directory per Windows PowerShell finestra per eseguirle. È anche possibile utilizzare Windows PowerShell Integrated Scripting Environment (ISE).
  
Ecco un esempio di un set di comandi completato:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Nomi di accesso degli account utente

Se si è abituati a utilizzare i nomi di accesso o gli UPN degli account utente, determinare le informazioni seguenti:
  
- UPN dell'account utente
    
    Se non si conosce l'UPN, utilizzare questo comando:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Questo comando elenca l'UPN degli account utente, ordinati per UPN, una schermata alla volta. È possibile utilizzare il cmdlet **Where** per filtrare l'elenco. Di seguito viene riportato un esempio:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Questo comando elenca solo gli account utente per cui il nome visualizzato inizia con "John".
    
- Ruolo che si desidera assegnare
    
    Per visualizzare l'elenco dei ruoli disponibili che è possibile assegnare agli account utente, usare questo comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Dopo aver impostato l'UPN dell'account e il nome del ruolo, utilizzare questi comandi per assegnare il ruolo all'account:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Copiare i comandi e incollarli nel blocco note. Per le **$upnName** e **$roleName** variabili. Sostituire il testo della descrizione con i relativi valori. Rimuovere i \< and > caratteri ma mantenere le virgolette. Incollare le righe modificate nel modulo di Microsoft Azure Active Directory per Windows PowerShell finestra per eseguirle. In alternativa, è possibile utilizzare il Windows PowerShell ISE.
  
Ecco un esempio di un set di comandi completato:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Modifiche a più ruoli

Per le modifiche a più ruoli, determinare le informazioni seguenti:
  
- Quali account utente si desidera configurare. È possibile utilizzare i metodi descritti nella sezione precedente per raccogliere il set di nomi visualizzati o UPN.
    
- Ruoli che si desidera assegnare a ogni account utente. Per visualizzare l'elenco dei ruoli disponibili che è possibile assegnare agli account utente, usare questo comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Creare quindi un file di testo con valori delimitati da virgole (CSV) con il nome visualizzato o l'UPN e i campi del nome del ruolo. È possibile eseguire questa operazione facilmente in Microsoft Excel.

Ecco un esempio per i nomi visualizzati:
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

Immettere infine il percorso del file CSV ed eseguire i comandi risultanti al prompt dei comandi di PowerShell.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

Ecco un esempio di UPN:
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

Immettere infine il percorso del file CSV ed eseguire i comandi risultanti al prompt dei comandi di PowerShell.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>Vedere anche

- [Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)