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
ms.openlocfilehash: ea631d12a95ca813ebf9da3286e36d724d51a2f7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696155"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Visualizzare gli account utente di Microsoft 365 con PowerShell

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Anche se è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 per visualizzare gli account per il tenant di Microsoft 365, è anche possibile utilizzare PowerShell per Microsoft 365 e fare alcuni elementi che l'interfaccia di amministrazione non è in grado di eseguire.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
### <a name="view-all-accounts"></a>Visualizzazione di tutti gli account

Per visualizzare l'elenco completo degli account utente, eseguire il comando seguente:
  
```powershell
Get-AzureADUser
```

Dovrebbero essere visualizzate informazioni analoghe alle seguenti:
  
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

### <a name="view-a-specific-account"></a>Visualizzazione di un account specifico

Per visualizzare un account utente specifico, inserire il nome account di accesso dell'account utente, noto anche come nome dell'entità utente (UPN), rimuovere i caratteri "<" e ">" ed eseguire il comando seguente:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Ecco un esempio:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Visualizzare i valori di proprietà aggiuntivi per un account specifico

Per impostazione predefinita, il cmdlet **Get-AzureADUser** consente di visualizzare solo le proprietà ObjectID, DisplayName e userPrincipalName degli account.

Per essere più selettivi sull'elenco delle proprietà da visualizzare, è possibile utilizzare il cmdlet **Select** in combinazione con il cmdlet **Get-AzureADUser** . Per combinare i due cmdlet, viene utilizzato il carattere "pipe" "|", che indica a Azure Active Directory PowerShell per Graph di prendere i risultati di un comando e inviarlo al comando successivo. Di seguito è riportato un comando di esempio che consente di visualizzare il DisplayName, il reparto e UsageLocation per ogni account utente:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Questo comando indica a PowerShell di:
  
- Accedere a tutte le informazioni degli account utente ( **Get-AzureADUser** ) e inviarle al comando successivo ( **|** ).
    
- Visualizzare solo il nome dell'account utente, il reparto e la posizione di utilizzo ( **selezionare DisplayName, Department, UsageLocation** ).
  
Per visualizzare tutte le proprietà degli account utente, utilizzare il cmdlet **Select** e il carattere jolly (*) per visualizzarli tutti per un account utente specifico. Ecco un esempio:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Come un altro esempio, è possibile controllare lo stato abilitato di un account utente specifico con il seguente comando:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-some-accounts-based-on-a-common-property"></a>Visualizzare alcuni account basati su una proprietà comune

Per essere più selettivi sull'elenco degli account da visualizzare, è possibile utilizzare il cmdlet **where** in combinazione con il cmdlet **Get-AzureADUser** . Per combinare i due cmdlet, viene utilizzato il carattere "pipe" "|", che indica a Azure Active Directory PowerShell per Graph di prendere i risultati di un comando e inviarlo al comando successivo. Ecco un comando di esempio che visualizza soltanto gli account utente con un percorso di utilizzo non specificato:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Questo comando indica a Azure Active Directory PowerShell per Graph di eseguire le operazioni seguenti:
  
- Accedere a tutte le informazioni degli account utente ( **Get-AzureADUser** ) e inviarle al comando successivo ( **|** ).
    
- Individuare tutti gli account utente che dispongono di una posizione di utilizzo non specificata ( **dove {$ \_ . UsageLocation-eq $Null}** ). All'interno delle parentesi graffe, il comando indica a PowerShell di trovare solo il set di account in cui la proprietà dell'account utente di UsageLocation ( ** $ \_ . UsageLocation** ) non è specificato ( **-eq $null** ).
    
La proprietà **UsageLocation** è solo una delle tante associate a un account utente. Per visualizzare tutte le proprietà degli account utente, utilizzare il cmdlet **Select** e il carattere jolly (*) per visualizzarli tutti per un account utente specifico. Ecco un esempio:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

In questo elenco, **City** è il nome di una proprietà dell'account utente. Questo significa che è possibile usare il comando seguente per elencare tutti gli account degli utenti che vivono a Londra:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  La sintassi del cmdlet **where** mostrato in questi esempi è **dove {$ \_ .** [nome della proprietà dell'account utente] [operatore di confronto] valore **}**. > [operatore di confronto] è **-EQ** per Equals, **-ne** per non uguale a, **-lt** per meno di, **-gt** per maggiore di e altri.  [valore] è in genere una stringa (una sequenza di lettere, numeri e altri caratteri), un valore numerico o **$null** per> non specificati vedere [dove](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) per ulteriori informazioni.
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="view-all-accounts"></a>Visualizzazione di tutti gli account

Per visualizzare l'elenco completo degli account utente, eseguire il comando seguente:
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.
>

Dovrebbero essere visualizzate informazioni analoghe alle seguenti:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Il cmdlet **Get-MsolUser** dispone inoltre di un set di parametri per filtrare il gruppo di account utente visualizzato. Ad esempio, per l'elenco degli utenti senza licenza (gli utenti che sono stati aggiunti a Microsoft 365 ma non sono stati ancora autorizzati a utilizzare uno qualsiasi dei servizi), eseguire questo comando.
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Dovrebbero essere visualizzate informazioni analoghe alle seguenti:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Per ulteriori informazioni sui parametri aggiuntivi per filtrare la visualizzazione del set di account utente visualizzato, vedere [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Visualizzazione di un account specifico

Per visualizzare un account utente specifico, inserire il nome di accesso dell'account utente dell'account utente, noto anche come nome dell'entità utente (UPN), rimuovere i caratteri "<" e ">" ed eseguire il comando seguente:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a>Visualizzare alcuni account basati su una proprietà comune

Per essere più selettivi sull'elenco degli account da visualizzare, è possibile utilizzare il cmdlet **where** in combinazione con il cmdlet **Get-MsolUser** . Per combinare i due cmdlet, viene utilizzato il carattere "pipe" "|", che indica a PowerShell di prendere i risultati di un comando e inviarlo al comando successivo. Ecco un comando di esempio che visualizza soltanto gli account utente con un percorso di utilizzo non specificato:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Questo comando indica a PowerShell di:
  
- Accedere a tutte le informazioni degli account utente ( **Get-MsolUser** ) e inviarle al comando successivo ( **|** ).
    
- Individuare tutti gli account utente che dispongono di una posizione di utilizzo non specificata ( **dove {$ \_ . UsageLocation-eq $Null}** ). All'interno delle parentesi graffe, il comando indica a PowerShell di trovare solo il set di account in cui la proprietà dell'account utente di UsageLocation ( ** $ \_ . UsageLocation** ) non è specificato ( **-eq $null** ).
    
Dovrebbero essere visualizzate informazioni analoghe alle seguenti:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

La proprietà **UsageLocation** è solo una delle tante associate a un account utente. Per visualizzare tutte le proprietà degli account utente, utilizzare il cmdlet **Select** e il carattere jolly (*) per visualizzarli tutti per un account utente specifico. Ecco un esempio:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

In questo elenco, **City** è il nome di una proprietà dell'account utente. Questo significa che è possibile usare il comando seguente per elencare tutti gli account degli utenti che vivono a Londra:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  La sintassi del cmdlet **where** mostrato in questi esempi è **dove {$ \_ .** [nome della proprietà dell'account utente] [operatore di confronto] valore **}**.  [operatore di confronto] è **-EQ** per Equals, **-ne** per non uguale a, **-lt** per meno di, **-gt** per maggiore di e altri.  [valore] è in genere una stringa, ovvero una sequenza di lettere, numeri e altri caratteri, un valore numerico o **$null** per Unspecified. Vedere [dove](https://technet.microsoft.com/library/hh849715.aspx) per ulteriori informazioni.
  
È possibile controllare lo stato bloccato di un account utente con il seguente comando:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Visualizzare i valori di proprietà aggiuntivi per gli account

Il cmdlet **Get-MsolUser** per impostazione predefinita visualizza tre proprietà degli account utente:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Se sono necessarie ulteriori proprietà, ad esempio il reparto utilizzato dall'utente e il paese/area geografica in cui l'utente utilizza i servizi Microsoft 365, è possibile eseguire **Get-MsolUser** in combinazione con il cmdlet **SELECT** per specificare l'elenco delle proprietà degli account utente. Ecco un esempio:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Questo comando indica a PowerShell di:
  
- Accedere a tutte le informazioni degli account utente ( **Get-MsolUser** ) e inviarle al comando successivo ( **|** ).
    
- Visualizzare solo il nome dell'account utente, il reparto e la posizione di utilizzo ( **selezionare DisplayName, Department, UsageLocation** ).
    
Dovrebbero essere visualizzate informazioni analoghe alle seguenti:
  
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

Il cmdlet **Select** consente di scegliere le proprietà che si desidera visualizzare. Per visualizzare tutte le proprietà degli account utente, utilizzare il carattere jolly (*) per visualizzarle tutte per un account utente specifico. Ecco un esempio:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Per essere più selettivi sull'elenco degli account da visualizzare, è anche possibile utilizzare il cmdlet **where** . Ecco un comando di esempio che visualizza soltanto gli account utente con un percorso di utilizzo non specificato:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Questo comando indica a PowerShell di:
  
- Accedere a tutte le informazioni degli account utente ( **Get-MsolUser** ) e inviarle al comando successivo ( **|** ).
    
- Individuare tutti gli account utente che dispongono di una posizione di utilizzo non specificata ( **dove {$ \_ . UsageLocation-eq $Null}** ) e inviare le informazioni risultanti al comando successivo ( **|** ). All'interno delle parentesi graffe, il comando indica a PowerShell di trovare solo il set di account in cui la proprietà dell'account utente di UsageLocation ( ** $ \_ . UsageLocation** ) non è specificato ( **-eq $null** ).
    
- Visualizzare solo il nome dell'account utente, il reparto e la posizione di utilizzo ( **selezionare DisplayName, Department, UsageLocation** ).
    
Dovrebbero essere visualizzate informazioni analoghe alle seguenti:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Se si utilizza la sincronizzazione della directory per creare e gestire gli utenti di Microsoft 365, è possibile visualizzare l'account locale da cui è stato progettato un utente di Microsoft 365. Di seguito si presuppone che Azure AD Connect sia stato configurato per l'utilizzo dell'ancoraggio di origine predefinito di ObjectGUID (per ulteriori informazioni sulla configurazione di un ancoraggio di origine, vedere [Azure ad Connect: Design Concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) e presuppone che sia stato installato il modulo servizi di dominio Active Directory per PowerShell (vedere [strumenti di amministrazione remota](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)

