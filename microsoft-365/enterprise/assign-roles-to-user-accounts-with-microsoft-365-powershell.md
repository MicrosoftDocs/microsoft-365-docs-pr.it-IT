---
title: Assegnare i ruoli agli account utente di Microsoft 365 con PowerShell
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
description: In questo articolo vengono fornite informazioni su come utilizzare PowerShell per Microsoft 365 in modo rapido e semplice per assegnare ruoli di amministratore agli account utente.
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754199"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>Assegnare i ruoli di amministratore agli account utente di Microsoft 365 con PowerShell

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

È possibile assegnare facilmente i ruoli agli account utente tramite PowerShell per Microsoft 365.

>[!Note]
>Informazioni su come  [assegnare i ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) agli account utente con l'interfaccia di amministrazione di Microsoft 365.
>
>Per un elenco di risorse aggiuntive, vedere [Manage Users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Per prima cosa, utilizzare un account di amministratore globale per [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Successivamente, identificare il nome di accesso dell'account utente che si desidera aggiungere a un ruolo (ad esempio: fredsm \@ contoso.com). Questo è conosciuto anche come nome dell'entità utente (UPN, User Principal Name).

Successivamente, determinare il nome del ruolo. Vedere [autorizzazioni per i ruoli di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

>[!Note]
>Prestare attenzione alle note in questo articolo. Alcuni nomi di ruolo sono diversi per PowerShell di Azure Active Directory (Azure AD). Ad esempio, il ruolo di *amministratore di SharePoint* nell'interfaccia di amministrazione di Microsoft 365 è amministratore del *servizio di SharePoint* in Azure ad PowerShell.
>

Successivamente, immettere i nomi di accesso e di ruolo ed eseguire i comandi seguenti:
  
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

Di seguito è riportato un esempio di un set di comandi completato che assegna il ruolo di amministratore del servizio di SharePoint all'account * \@ contoso.com di dilindan* :
  
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

Per prima cosa, utilizzare un account di amministratore globale per [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
### <a name="for-a-single-role-change"></a>Per una singola modifica del ruolo

La modalità più comune per specificare l'account utente consiste nell'utilizzare il relativo nome visualizzato o il relativo nome di posta elettronica, noto anche come nome di accesso o nome dell'entità utente (UPN, User Principal Name).

#### <a name="display-names-of-user-accounts"></a>Visualizzazione dei nomi degli account utente

Se si è abituati a utilizzare i nomi visualizzati degli account utente, determinare le seguenti informazioni:
  
- L'account utente che si desidera configurare
    
    Per specificare l'account utente, è necessario determinare il nome visualizzato. Per ottenere un elenco completo degli account, utilizzare questo comando:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Questo comando elenca il nome visualizzato degli account utente, ordinati per nome visualizzato, una schermata alla volta. È possibile filtrare l'elenco in un set più piccolo utilizzando il cmdlet **Where**. Vedere l'esempio seguente.

   >[!Note]
   >PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per il modulo di Windows PowerShell e i cmdlet con *MSOL* nel proprio nome. Eseguire questi cmdlet da Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Questo comando elenca solo gli account utente per cui il nome visualizzato inizia con "John".
    
- Il ruolo che si desidera assegnare
    
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

Incollare i comandi nel blocco note. Per le variabili *$dispName* e *$roleName* , sostituire il testo della descrizione con i relativi valori. Rimuovere i \< and > caratteri ma mantenere le virgolette. Incollare le righe modificate nella finestra di Microsoft Azure Active Directory Module per Windows PowerShell per eseguirle. È anche possibile utilizzare Windows PowerShell Integrated Scripting Environment (ISE).
  
Di seguito è riportato un esempio di un set di comandi completato:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Nomi di accesso degli account utente

Se si è abituati a utilizzare i nomi di accesso o gli account utente di UPN, determinare le informazioni seguenti:
  
- UPN dell'account utente
    
    Se non si conosce l'UPN, utilizzare il seguente comando:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Questo comando elenca l'UPN degli account utente, ordinati in base all'UPN, una schermata alla volta. È possibile utilizzare il cmdlet **where** per filtrare l'elenco. Di seguito viene riportato un esempio:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Questo comando elenca solo gli account utente per cui il nome visualizzato inizia con "John".
    
- Il ruolo che si desidera assegnare
    
    Per visualizzare l'elenco dei ruoli disponibili che è possibile assegnare agli account utente, usare questo comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Dopo aver utilizzato l'UPN dell'account e il nome del ruolo, utilizzare questi comandi per assegnare il ruolo all'account:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Copiare i comandi e incollarli nel blocco note. Per le variabili **$upnName** e **$roleName** . Sostituire il testo della descrizione con i relativi valori. Rimuovere i \< and > caratteri ma mantenere le virgolette. Incollare le righe modificate nella finestra di Microsoft Azure Active Directory Module per Windows PowerShell per eseguirle. In alternativa, è possibile utilizzare Windows PowerShell ISE.
  
Di seguito è riportato un esempio di un set di comandi completato:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Modifiche a più ruoli

Per le modifiche a più ruoli, determinare le seguenti informazioni:
  
- Gli account utente che si desidera configurare. È possibile utilizzare i metodi descritti nella sezione precedente per raccogliere il set di nomi visualizzati o UPN.
    
- Ruoli che si desidera assegnare a ogni account utente. Per visualizzare l'elenco dei ruoli disponibili che è possibile assegnare agli account utente, usare questo comando:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Successivamente, creare un file di testo con valori delimitati da virgole (CSV) con il nome visualizzato o i campi UPN e nome ruolo. È possibile eseguire questa operazione facilmente in Microsoft Excel.

Di seguito è riportato un esempio per i nomi visualizzati:
  
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

Di seguito è riportato un esempio di UPN:
  
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
