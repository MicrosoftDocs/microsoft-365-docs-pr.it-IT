---
title: Visualizzare gli account utente di Microsoft 365 con PowerShell
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: Informazioni su come visualizzare, elencare o visualizzare gli account utente di Microsoft 365 in modi diversi con PowerShell.
ms.openlocfilehash: de91195afeb8480bf231d9536e4b3a94502a6da1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924649"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Visualizzare gli account utente di Microsoft 365 con PowerShell

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

È possibile usare l'interfaccia di amministrazione di Microsoft 365 per visualizzare gli account per il tenant di Microsoft 365. PowerShell per Microsoft 365 abilita questa funzionalità, ma offre anche funzionalità aggiuntive.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Innanzitutto, [connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
### <a name="view-all-accounts"></a>Visualizzare tutti gli account

Per visualizzare l'elenco completo degli account utente, eseguire questo comando:
  
```powershell
Get-AzureADUser
```

È consigliabile ottenere informazioni simili alle seguenti:
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a>Visualizzare un account specifico

Per visualizzare un account utente specifico, eseguire il comando seguente. Immettere il nome dell'account di accesso dell'account utente, noto anche come nome dell'entità utente (UPN). Rimuovere i caratteri "<" e ">".
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Di seguito viene riportato un esempio:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Visualizzare valori di proprietà aggiuntivi per un account specifico

Per impostazione predefinita, il cmdlet **Get-AzureADUser** visualizza solo le *proprietà ObjectID,* *DisplayName* e *UserPrincipalName* degli account.

Per essere più selettivi sulle proprietà da visualizzare, utilizzare il cmdlet **Select** in combinazione con il cmdlet **Get-AzureADUser.** Per combinare i due cmdlet, utilizzare il carattere "pipe" ("|"), che indica ad Azure Active Directory PowerShell per Graph di ottenere i risultati di un comando e inviarlo al comando successivo. Ecco un comando di esempio che visualizza *DisplayName,* *Department* e *UsageLocation* per ogni account utente:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Questo comando indica a PowerShell di:
  
1. Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).
    
1.  Visualizzare solo il nome dell'account utente, il reparto e la posizione di utilizzo (**Selezionare DisplayName, Department, UsageLocation**).
  
Per visualizzare tutte le proprietà di un account utente specifico, utilizzare il cmdlet **Select** e il carattere jolly (*). Di seguito viene riportato un esempio:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Come altro esempio, eseguire il comando seguente per controllare lo stato abilitato di un account utente specifico:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Visualizzare lo stato di sincronizzazione degli account

Gli account utente hanno due origini: 

- Windows Server Active Directory (AD), ovvero account sincronizzati da Active Directory locale al cloud.

- Account Di Azure Active Directory (Azure AD), creati direttamente nel cloud.


Il comando seguente indica a PowerShell di ottenere tutti gli utenti con l'attributo *DirSyncEnabled* impostato su *True.* Puoi usarlo per trovare gli account che si sincronizzano da Active Directory locale.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

Il comando seguente indica a PowerShell di ottenere tutti gli utenti con l'attributo *DirSyncEnabled* impostato su *False.* Puoi usarlo per trovare account solo cloud.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Visualizzare gli account in base a una proprietà comune

Per essere più selettivi sull'elenco di account da visualizzare, è possibile utilizzare il cmdlet **Where** in combinazione con il cmdlet **Get-AzureADUser.** Per combinare i due cmdlet, utilizzare il carattere "pipe" ("|"), che indica ad Azure Active Directory PowerShell per Graph di ottenere i risultati di un comando e inviarlo al comando successivo. Ecco un comando di esempio che visualizza solo gli account utente con un percorso di utilizzo non specificato:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Questo comando indica ad Azure Active Directory PowerShell per Graph di:
  
1. Ottenere tutte le informazioni sugli account utente (**Get-AzureADUser**) e inviarle al comando successivo ( **|** ).
    
1. Trovare tutti gli account utente con un percorso di utilizzo non specificato (**Where {$ \_ . UsageLocation -eq $Null}**). All'interno delle parentesi graffe, il comando indica a PowerShell di trovare solo il set di account per cui la proprietà dell'account utente UsageLocation (**$ \_ . UsageLocation**) non è specificato (**-eq $Null**).
    
La proprietà **UsageLocation** è solo una delle tante associate a un account utente. Per visualizzare tutte le proprietà di un account utente specifico, utilizzare il cmdlet **Select** e il carattere jolly (*). Di seguito viene riportato un esempio:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

**City** è il nome di una proprietà dell'account utente. È possibile utilizzare il comando seguente per elencare tutti gli account degli utenti che vivono a Londra:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  La sintassi del cmdlet **Where** in questi esempi è **Where {$ \_ .** [nome proprietà account utente] [operatore di confronto] [valore] **}**.> [operatore di confronto] è **-eq** per uguale a, **-ne** per diverso da, **-lt** per minore di, **-gt** per maggiore di e altri.  [valore] è in genere una stringa (una sequenza di lettere, numeri e altri caratteri), un valore numerico **o** $Null per non specificato. Per ulteriori informazioni, vedere [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Innanzitutto, [connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="view-all-accounts"></a>Visualizzare tutti gli account

Per visualizzare l'elenco completo degli account utente, eseguire questo comando:
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core non supporta il Modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* all'interno del nome. Eseguire questi cmdlet da Windows PowerShell.
>

È consigliabile ottenere informazioni simili alle seguenti:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Il cmdlet **Get-MsolUser** dispone inoltre di un set di parametri per filtrare il gruppo di account utente visualizzato. Ad esempio, per l'elenco degli utenti senza licenza (utenti aggiunti a Microsoft 365 ma non ancora concessi in licenza per l'utilizzo di uno dei servizi), eseguire questo comando:
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

È consigliabile ottenere informazioni simili alle seguenti:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Per informazioni sui parametri aggiuntivi per filtrare il set di account utente visualizzati, vedere [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Visualizzare un account specifico

Per visualizzare un account utente specifico, eseguire il comando seguente. Compilare il nome di accesso dell'account utente, noto anche come nome dell'entità utente (UPN). Rimuovere i caratteri "<" e ">".
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Visualizzare gli account in base a una proprietà comune

Per essere più selettivi sull'elenco di account da visualizzare, è possibile utilizzare il cmdlet **Where** in combinazione con il cmdlet **Get-MsolUser.** Per combinare i due cmdlet, utilizzare il carattere "pipe" ("|"), che indica a PowerShell di ottenere i risultati di un comando e inviarlo al comando successivo. Ecco un esempio in cui vengono visualizzati solo gli account utente con un percorso di utilizzo non specificato:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Questo comando indica a PowerShell di:
  
1. Ottenere tutte le informazioni sugli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).
    
1. Trovare tutti gli account utente con un percorso di utilizzo non specificato (**Where {$ \_ . UsageLocation -eq $Null}**). All'interno delle parentesi graffe, il comando indica a PowerShell di trovare solo il set di account per cui la proprietà dell'account utente UsageLocation (**$ \_ . UsageLocation**) non è specificato (**-eq $Null**).
    
È consigliabile ottenere informazioni simili alle seguenti:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

La proprietà *UsageLocation* è solo una delle tante associate a un account utente. Per visualizzare tutte le proprietà per gli account utente, utilizzare il cmdlet **Select** e il carattere jolly (*) per visualizzarle tutte per un account utente specifico. Di seguito viene riportato un esempio:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

*City* è il nome di una proprietà dell'account utente. È possibile utilizzare il comando seguente per elencare tutti gli account utente per gli utenti che vivono a Londra:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  La sintassi del cmdlet **Where** in questi esempi è **Where {$ \_ .** [nome proprietà account utente] [operatore di confronto] [valore] **}**.  [operatore di confronto] è **-eq** per uguale a, **-ne** per diverso da, **-lt** per minore di, **-gt** per maggiore di e altri.  [valore] è in genere una stringa (una sequenza di lettere, numeri e altri caratteri), un valore numerico **o** $Null per non specificato. Per ulteriori informazioni, vedere [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  
Per verificare lo stato bloccato di un account utente, utilizzare il comando seguente:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Visualizzare valori di proprietà aggiuntivi per gli account

Per impostazione predefinita, il cmdlet **Get-MsolUser** visualizza queste tre proprietà degli account utente:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Se sono necessarie proprietà aggiuntive, ad esempio il reparto in cui lavora l'utente e il paese/area geografica in cui utilizzano i servizi di Microsoft 365, è possibile eseguire **Get-MsolUser** in combinazione con il cmdlet **Select** per specificare l'elenco delle proprietà dell'account utente. Di seguito viene riportato un esempio:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Questo comando indica a PowerShell di:
  
1. Ottenere tutte le informazioni sugli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).
    
1. Visualizzare solo il nome dell'account utente, il reparto e la posizione di utilizzo (**Selezionare DisplayName, Department, UsageLocation**).
    
È consigliabile ottenere informazioni simili alle seguenti:
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

Il cmdlet **Select** consente di scegliere le proprietà da visualizzare. Per visualizzare tutte le proprietà di un account utente specifico, utilizzare il carattere jolly (*). Di seguito viene riportato un esempio:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Per essere più selettivi sull'elenco di account da visualizzare, è inoltre possibile utilizzare il cmdlet **Where.** Ecco un comando di esempio che visualizza solo gli account utente con un percorso di utilizzo non specificato:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Questo comando indica a PowerShell di:
  
1. Ottenere tutte le informazioni sugli account utente (**Get-MsolUser**) e inviarle al comando successivo ( **|** ).
    
1. Trovare tutti gli account utente con un percorso di utilizzo non specificato (**Where {$ \_ . UsageLocation -eq $Null}**) e inviare le informazioni risultanti al comando successivo ( **|** ). All'interno delle parentesi graffe, il comando indica a PowerShell di trovare solo il set di account per cui la proprietà dell'account utente UsageLocation (**$ \_ . UsageLocation**) non è specificato (**-eq $Null**).
    
1. Visualizzare solo il nome dell'account utente, il reparto e la posizione di utilizzo (**Selezionare DisplayName, Department, UsageLocation**).
    
È consigliabile ottenere informazioni simili alle seguenti:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Se si utilizza la sincronizzazione della directory per creare e gestire gli utenti di Microsoft 365, è possibile visualizzare l'account locale da cui è stato proiettato un utente di Microsoft 365. Nell'esempio seguente si presuppone che:

- Azure AD Connect è configurato per usare l'ancoraggio di origine predefinito di ObjectGUID. Per ulteriori informazioni sulla configurazione di un ancoraggio di origine, vedere [Azure AD Connect: Concetti di progettazione.](/azure/active-directory/hybrid/plan-connect-design-concepts)
- Il modulo Servizi di dominio Active Directory per PowerShell è stato installato (vedere [Strumenti RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)