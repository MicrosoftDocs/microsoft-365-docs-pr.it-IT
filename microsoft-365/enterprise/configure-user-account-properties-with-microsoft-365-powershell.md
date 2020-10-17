---
title: Configurare le proprietà degli account utente di Microsoft 365 con PowerShell
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
description: 'Riepilogo: utilizzare PowerShell per Microsoft 365 per configurare le proprietà di singoli o più account utente nel tenant di Microsoft 365.'
ms.openlocfilehash: ae797d67b47c637dc95176b92fad8090f8a7ab37
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580929"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Configurare le proprietà degli account utente di Microsoft 365 con PowerShell

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Anche se è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per configurare le proprietà per gli account utente del tenant di Microsoft 365, è anche possibile utilizzare PowerShell e fare alcuni elementi che possono essere configurati dal centro di amministrazione di Microsoft 365.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Per configurare le proprietà degli account utente con il modulo Azure Active Directory PowerShell per Graph, utilizzare il cmdlet [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) e specificare le proprietà da impostare o modificare. 

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
   
### <a name="change-properties-for-a-specific-user-account"></a>Modificare le proprietà per un account utente specifico

Identificare l'account con il parametro **-ObjectID** e impostare o modificare proprietà specifiche con ulteriori parametri. Ecco un elenco dei parametri più comuni.
  
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
    
Per ulteriori parametri, vedere [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser).

>[!Note]
>Prima di poter assegnare licenze a un account utente, è necessario assegnare una posizione di utilizzo.
>

Per visualizzare il nome principale degli utenti per gli account utente, eseguire il comando seguente.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Questo comando indica a PowerShell di:
  
- Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).
    
- Ordinare l'elenco dei nomi delle entità utente in ordine alfabetico (**Sort userPrincipalName**) e inviarlo al comando successivo ( **|** ).
    
- Visualizzare solo la proprietà del nome dell'entità utente per ogni account (**selezionare userPrincipalName**).

- Visualizzare gli elementi in una schermata alla volta (**More**).
    
Con questo comando vengono elencati tutti gli account. Se si desidera visualizzare il nome dell'entità utente per un account in base al nome visualizzato (nome e cognome), inserire la variabile **$username** in basso (rimozione dei \< and > caratteri), quindi eseguire i comandi seguenti:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Questo esempio permette di visualizzare il nome dell’entità utente per l’account utente con nome visualizzato Caleb Sillis.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Utilizzando una variabile **$upn**, è possibile apportare modifiche ai singoli account in base al nome visualizzato. Ecco un esempio di impostazione della posizione di utilizzo di Belinda Newman in Francia, specificando il nome visualizzato anziché il nome principale dell'utente:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Modificare le proprietà per tutti gli account utente

Per modificare le proprietà per tutti gli utenti, è possibile utilizzare la combinazione di cmdlet **Get-AzureADUser** e **Set-AzureADUser**. Nell'esempio seguente viene modificata la posizione di utilizzo per tutti gli utenti in Francia:
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Questo comando indica a PowerShell di:
  
- Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).
    
- Impostare la posizione dell'utente in Francia (**set-AzureADUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Modificare le proprietà per un set specifico di account utente

Per modificare le proprietà per un set specifico di account utente, è possibile utilizzare la combinazione di cmdlet **Get-AzureADUser**, **Where** e **Set-AzureADUser**. Nell'esempio seguente viene modificata la posizione di utilizzo per tutti gli utenti del reparto Contabilità in Francia:
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Questo comando indica a PowerShell di:
  
- Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).
    
- Individuare tutti gli account utente con la proprietà Department impostata su "Accounting" (**dove {$ _. Department-EQ "Accounting"}**) e inviare le informazioni risultanti al comando successivo ( **|** ).
    
- Impostare la posizione dell'utente in Francia (**set-AzureADUser-UsageLocation "fr"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Per configurare le proprietà degli account utente con il modulo di Microsoft Azure Active Directory per Windows PowerShell, utilizzare il cmdlet **set-MsolUser** e specificare le proprietà da impostare o modificare. 

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Modificare le proprietà per un account utente specifico

Per configurare le proprietà per un account utente specifico, utilizzare il cmdlet [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) e specificare le proprietà da impostare o modificare. 

Identificare l'account con il parametro **-UserPrincipalName** e impostare o modificare proprietà specifiche con ulteriori parametri. Ecco un elenco dei parametri più comuni.
  
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
    
Per ulteriori parametri, vedere [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).

Per visualizzare i nomi principali di tutti gli utenti, eseguire il comando seguente.
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Questo comando indica a PowerShell di:
  
- Ottenere tutte le informazioni sugli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).
    
- Ordinare l'elenco dei nomi delle entità utente in ordine alfabetico (**Sort userPrincipalName**) e inviarlo al comando successivo ( **|** ).
    
- Visualizzare solo la proprietà del nome dell'entità utente per ogni account (**selezionare userPrincipalName**).
    
- Visualizzare gli elementi in una schermata alla volta (**More**).
    
Con questo comando vengono elencati tutti gli account. Se si desidera visualizzare il nome dell'entità utente per un account in base al nome visualizzato (nome e cognome), inserire la variabile **$username** in basso (rimozione dei \< and > caratteri), quindi eseguire i comandi seguenti:
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Questo esempio permette di visualizzare il nome principale dell'utente denominato Caleb Sillis.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Utilizzando una variabile **$upn**, è possibile apportare modifiche ai singoli account in base al nome visualizzato. Ecco un esempio di impostazione della posizione di utilizzo di Belinda Newman in Francia, specificando il nome visualizzato anziché il nome principale dell'utente:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Modificare le proprietà per tutti gli account utente

Per modificare le proprietà per tutti gli utenti, è possibile utilizzare la combinazione di cmdlet **Get-MsolUser** e **Set-MsolUser**. Nell'esempio seguente viene modificata la posizione di utilizzo per tutti gli utenti in Francia:
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Questo comando indica a PowerShell di:
  
- Ottenere tutte le informazioni sugli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).
    
- Impostare la posizione dell'utente in Francia (**set-MsolUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Modificare le proprietà per un set specifico di account utente

Per modificare le proprietà di un determinato set di account utente, è possibile utilizzare la combinazione dei cmdlet **Get-MsolUser**, **where**e **set-MsolUser** . Nell'esempio seguente viene modificata la posizione di utilizzo per tutti gli utenti del reparto Contabilità in Francia:
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Questo comando indica a PowerShell di:
  
- Ottenere tutte le informazioni sugli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).
    
- Individuare tutti gli account utente con la proprietà Department impostata su "Accounting" (**dove {$ _. Department-EQ "Accounting"}**) e inviare le informazioni risultanti al comando successivo ( **|** ).
    
- Impostare la posizione dell'utente in Francia (**set-MsolUser-UsageLocation "fr"**).


## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
