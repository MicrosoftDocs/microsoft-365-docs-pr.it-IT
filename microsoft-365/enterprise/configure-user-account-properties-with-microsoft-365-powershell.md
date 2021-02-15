---
title: Configurare le proprietà dell'account utente di Microsoft 365 con PowerShell
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Usare PowerShell per Microsoft 365 per configurare le proprietà di uno o più account utente nel tenant di Microsoft 365.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754329"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Configurare le proprietà dell'account utente di Microsoft 365 con PowerShell

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per configurare le proprietà per gli account utente del tenant di Microsoft 365. In PowerShell, è anche possibile eseguire questa operazione, oltre ad altre operazioni che non è possibile eseguire nell'interfaccia di amministrazione.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Per configurare le proprietà per gli account utente nel modulo Azure Active Directory PowerShell per Graph, utilizzare il cmdlet [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) e specificare le proprietà da impostare o modificare.

Prima di [tutto, connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   
### <a name="change-properties-for-a-specific-user-account"></a>Modificare le proprietà per un account utente specifico

È possibile identificare l'account con *il parametro -ObjectID* e impostare o modificare proprietà specifiche utilizzando parametri aggiuntivi. Ecco un elenco dei parametri più comuni:
  
- -Department "\<department name>"
    
- -DisplayName "\<full user name>"
    
- -FacsimilieTelephoneNumber "\<fax number>"
    
- -GivenName "\<user first name>"
    
- -Surname "\<user last name>"
    
- -Mobile "\<mobile phone number>"
    
- -JobTitle "\<job title>"
    
- -PreferredLanguage "\<language>"
    
- -StreetAddress "\<street address>"
    
- -City "<nome città>"
    
- -State "\<state name>"
    
- -PostalCode "\<postal code>"
    
- -Country "\<country name>"
    
- -TelephoneNumber "\<office phone number>"
    
- -UsageLocation " \<2-character country or region code> "
    
    Si tratta del codice paese o area geografica a due lettere ISO 3166-1 alpha-2 (A2).
    
Per ulteriori parametri, vedere [Set-AzureADUser.](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0)

>[!Note]
>Prima di poter assegnare licenze a un account utente, è necessario assegnare una posizione di utilizzo.
>

Per visualizzare il nome principale degli utenti per gli account utente, eseguire il comando seguente.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Questo comando indica a PowerShell di:
  
1. Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).
    
1. Ordinare l'elenco dei nomi dell'entità utente in ordine alfabetico (**Sort UserPrincipalName**) e inviarlo al comando successivo ( **|** ).
    
1. Visualizzare solo la proprietà User Principal Name per ogni account (**Select UserPrincipalName**).

1. Visualizzare gli elementi in una schermata alla volta (**More**).
    
Per visualizzare il nome dell'entità utente per un account in base al nome visualizzato (nome e cognome), eseguire i comandi seguenti. Compilare la *$userName* e rimuovere i \< and > caratteri:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In questo esempio viene visualizzato il nome dell'entità utente per l'account utente con nome visualizzato *Caleb Sills.*
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Utilizzando una variabile *$upn*, è possibile apportare modifiche ai singoli account in base al nome visualizzato. Ecco un esempio che imposta la posizione di utilizzo di *Belinda Newman* sulla Francia. Tuttavia, specifica il nome visualizzato anziché il nome dell'entità utente:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Modificare le proprietà per tutti gli account utente

Per modificare le proprietà di tutti gli utenti, è possibile utilizzare una combinazione dei cmdlet **Get-AzureADUser** e **Set-AzureADUser.** Nell'esempio seguente la posizione di utilizzo di tutti gli utenti viene modificata in *Francia:*
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Questo comando indica a PowerShell di:
  
1. Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).
    
1. Impostare la posizione dell'utente su Francia (**Set-AzureADUser -UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Modificare le proprietà per un set specifico di account utente

Per modificare le proprietà di un set specifico di account utente, è possibile utilizzare una combinazione dei cmdlet **Get-AzureADUser**, **Where** e **Set-AzureADUser.** Nell'esempio seguente la posizione di utilizzo di tutti gli utenti del reparto Contabilità viene modificata in *Francia:*
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Questo comando indica a PowerShell di:
  
1. Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).
    
1.  Trovare tutti gli account utente la cui proprietà *Department* è impostata su "Accounting" (**Where {$_. Department -eq "Accounting"}**) e inviare le informazioni risultanti al comando successivo ( **|** ).
    
1. Impostare la posizione dell'utente su Francia (**Set-AzureADUser -UsageLocation "FR"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Per configurare le proprietà per gli account utente con il modulo di Microsoft Azure Active Directory per Windows PowerShell, utilizzare il cmdlet **Set-MsolUser** e specificare le proprietà da impostare o modificare.

Prima di [tutto, connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
>[!Note]
>PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome. Eseguire questi cmdlet da Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Modificare le proprietà per un account utente specifico

Per configurare le proprietà per un account utente specifico, utilizzare il cmdlet [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) e specificare le proprietà da impostare o modificare. 

È possibile identificare l'account con *il parametro -UserPrincipalName* e impostare o modificare proprietà specifiche utilizzando parametri aggiuntivi. Ecco un elenco dei parametri più comuni.
  
- -City "<nome città>"
    
- -Country "\<country name>"
    
- -Department "\<department name>"
    
- -DisplayName "\<full user name>"
    
- -Fax "\<fax number>"
    
- -FirstName "\<user first name>"
    
- -LastName "\<user last name>"
    
- -MobilePhone "\<mobile phone number>"
    
- -Office "\<office location>"
    
- -PhoneNumber "\<office phone number>"
    
- -PostalCode "\<postal code>"
    
- -PreferredLanguage "\<language>"
    
- -State "\<state name>"
    
- -StreetAddress "\<street address>"
    
- -Title "\<title name>"
    
- -UsageLocation " \<2-character country or region code> "
    
    Si tratta del codice paese o area geografica a due lettere ISO 3166-1 alpha-2 (A2).
    
Per ulteriori parametri, vedere [Set-MsolUser.](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))

Per visualizzare i nomi dell'entità utente di tutti gli utenti, eseguire il comando seguente:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Questo comando indica a PowerShell di:
  
1. Ottenere tutte le informazioni per gli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).
    
1. Ordinare l'elenco dei nomi dell'entità utente in ordine alfabetico (**Sort UserPrincipalName**) e inviarlo al comando successivo ( **|** ).
    
1. Visualizzare solo la proprietà User Principal Name per ogni account (**Select UserPrincipalName**).
    
1. Visualizzare gli elementi in una schermata alla volta (**More**).
    
Per visualizzare il nome dell'entità utente per un account in base al nome visualizzato (nome e cognome), eseguire i comandi seguenti. Compilare la *$userName* e rimuovere i \< and > caratteri.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

In questo esempio viene visualizzato il nome dell'entità utente per l'utente Caleb Sills:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Utilizzando una variabile *$upn*, è possibile apportare modifiche ai singoli account in base al nome visualizzato. Ecco un esempio che imposta la posizione di utilizzo di *Belinda Newman* sulla *Francia,* ma specifica il nome visualizzato anziché il nome dell'entità utente:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Modificare le proprietà per tutti gli account utente

Per modificare le proprietà di tutti gli utenti, utilizzare una combinazione dei cmdlet **Get-MsolUser** e **Set-MsolUser.** Nell'esempio seguente la posizione di utilizzo di tutti gli utenti viene modificata in *Francia:*
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Questo comando indica a PowerShell di:
  
1. Ottenere tutte le informazioni per gli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).
    
1. Impostare la posizione dell'utente su Francia (**Set-MsolUser -UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Modificare le proprietà per un set specifico di account utente

Per modificare le proprietà di un set specifico di account utente, è possibile utilizzare una combinazione dei cmdlet **Get-MsolUser**, **Where** e **Set-MsolUser.** Nell'esempio seguente la posizione di utilizzo di tutti gli utenti del reparto Contabilità viene modificata in *Francia:*
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Questo comando indica a PowerShell di:
  
1. Ottenere tutte le informazioni per gli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).
    
1. Trovare tutti gli account utente la cui proprietà *Department* è impostata su "Accounting" (**Where {$_. Department -eq "Accounting"}**) e inviare le informazioni risultanti al comando successivo ( **|** ).
    
1. Impostare la posizione dell'utente su Francia (**Set-MsolUser -UsageLocation "FR"**).

## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
