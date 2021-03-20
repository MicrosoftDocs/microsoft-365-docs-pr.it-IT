---
title: Creare account utente di Microsoft 365 con PowerShell
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Come usare PowerShell per creare singoli o più account utente di Microsoft 365.
ms.openlocfilehash: c3676acdec3bbba328809ee1528206bbc44f94f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907565"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>Creare account utente di Microsoft 365 con PowerShell

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

È possibile utilizzare PowerShell per Microsoft 365 per creare in modo efficiente account utente, inclusi più account.

Quando si creano account utente in PowerShell, alcune proprietà dell'account sono sempre necessarie. Altre proprietà non sono necessarie, ma sono importanti. Vedere la tabella seguente.
  
|**Nome della proprietà**|**Obbligatorio?**|**Descrizione**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |Sì  <br/> |Questo è il nome visualizzato utilizzato nei servizi di Microsoft 365. Ad esempio, *Caleb Sills*. <br/> |
|**UserPrincipalName** <br/> |Sì  <br/> |Questo è il nome dell'account utilizzato per accedere ai servizi di Microsoft 365. Ad esempio, *CalebS \@ contoso.onmicrosoft.com*.  <br/> |
|**FirstName** <br/> |No  <br/> ||
|**LastName** <br/> |No  <br/> ||
|**LicenseAssignment** <br/> |No  <br/> |Si tratta del piano di licenza (noto anche come piano di licenza o SKU) da cui viene assegnata una licenza disponibile all'account utente. La licenza definisce i servizi di Microsoft 365 disponibili per l'account. Non è necessario assegnare una licenza a un utente quando si crea l'account, ma l'account deve disporre di una licenza per accedere ai servizi di Microsoft 365. Dopo aver creato l'account utente, è necessario disporre di 30 giorni per la licenza. |
|**Password** <br/> |No  <br/> | Se non si specifica una password, all'account utente ne viene assegnata una casuale, visibile nei risultati del comando. Se si specifica una password, la password deve contenere da 8 a 16 caratteri di testo ASCII dei seguenti tipi: lettere minuscole, lettere maiuscole, numeri e simboli.<br/> |
|**UsageLocation** <br/> |No  <br/> |Si tratta di un codice paese ISO 3166-1 alfa-2 valido. Ad esempio, *US* per gli Stati Uniti e *FR* per la Francia. È importante fornire questo valore, perché alcuni servizi di Microsoft 365 non sono disponibili in alcuni paesi. Non è possibile assegnare una licenza a un account utente a meno che l'account non abbia configurato questo valore. Per ulteriori informazioni, vedere [Informazioni sulle restrizioni di licenza.](https://go.microsoft.com/fwlink/p/?LinkId=691730)<br/> |

>[!Note]
>[Informazioni su come creare account utente tramite](../admin/add-users/add-users.md) l'interfaccia di amministrazione di Microsoft 365.
> 
> Per un elenco delle risorse aggiuntive, vedere [Manage users and groups](../admin/add-users/index.yml).
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Innanzitutto, [connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

Dopo la connessione, utilizzare la sintassi seguente per creare un singolo account:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

In questo esempio viene creato un account per l'utente *statunitense Caleb Sills:*
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Innanzitutto, [connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="create-an-individual-user-account"></a>Creare un account utente singolo

Per creare un singolo account, utilizzare la sintassi seguente:
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con *Msol* nel nome. Eseguire questi cmdlet da Windows PowerShell.
>

Per elencare i nomi dei piani di gestione delle licenze disponibili, usare il seguente comando:

````powershell
Get-MsolAccountSku
````

In questo esempio viene creato un account per l'utente *statunitense Caleb Sills* e viene assegnata una licenza dal piano di licenza `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3).
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>Creare più account utente

1. Creare un file CSV che includa le necessarie informazioni sull'account utente. Ad esempio:

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   >I nomi delle colonne e il relativo ordine nella prima riga del file CSV sono arbitrari. Verificare tuttavia che l'ordine dei dati nel resto del file corrisponda all'ordine dei nomi delle colonne. E usare i nomi delle colonne per i valori dei parametri nel comando PowerShell per Microsoft 365.
    
2. Usare la sintassi seguente:
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   Questo esempio crea account utente dal file *C:\My Documents\NewAccounts.csv* e registra i risultati in un file *denominato C:\My Documents\NewAccountResults.csv*.
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. Esaminare il file di output per visualizzare i risultati. Non sono state specificate password, quindi le password casuali generate da Microsoft 365 sono visibili nel file di output.
    
## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)