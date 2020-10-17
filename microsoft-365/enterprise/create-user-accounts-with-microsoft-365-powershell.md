---
title: Creare gli account utente di Microsoft 365 con PowerShell
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
description: In questo articolo vengono fornite informazioni su come utilizzare PowerShell per creare account utente o più account utente di Microsoft 365.
ms.openlocfilehash: aedcc4adba6171a63a5ddaeb87b20150e72b2a76
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580953"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>Creare gli account utente di Microsoft 365 con PowerShell

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

È possibile utilizzare PowerShell per Microsoft 365 per creare efficacemente gli account utente, in particolare più account utente. Quando si creano account utente in PowerShell, vengono sempre richieste determinate proprietà dell'account. Altre proprietà non sono necessarie per creare l'account, ma sono comunque importanti. Tali proprietà sono descritte nella tabella seguente.
  
|**Nome della proprietà**|**Obbligatorio?**|**Descrizione**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |Sì  <br/> |Si tratta del nome visualizzato utilizzato nei servizi Microsoft 365. Ad esempio, Caleb Sills.  <br/> |
|**UserPrincipalName** <br/> |Sì  <br/> |Si tratta del nome dell'account utilizzato per accedere ai servizi di Microsoft 365. Ad esempio, CalebS@contoso.onmicrosoft.com.  <br/> |
|**FirstName** <br/> |No  <br/> ||
|**LastName** <br/> |No  <br/> ||
|**LicenseAssignment** <br/> |No  <br/> |Si tratta del piano di gestione delle licenze (noto anche come piano di licenza o SKU) da cui viene assegnata una licenza disponibile per l'account utente. La licenza definisce i servizi Microsoft 365 che sono disponibili per l'account. Non è necessario assegnare una licenza a un utente quando si crea l'account, ma l'account richiede una licenza per accedere ai servizi Microsoft 365. Dopo aver creato l'account utente, sono presenti 30 giorni per la licenza. |
|**Password** <br/> |No  <br/> | Se non si specifica una password, all'account utente ne viene assegnata una casuale, visibile nei risultati del comando. Se si specifica una password, è necessario che contenga da 8 a 16 caratteri di testo ASCII di uno dei tre tipi seguenti: lettere minuscole, lettere maiuscole, numeri e simboli. <br/> |
|**UsageLocation** <br/> |No  <br/> |Questo è un codice paese valido ISO 3166-1 Alpha-2. Ad esempio, US per gli Stati Uniti e FR per la Francia. **Poiché alcuni servizi Microsoft 365 non sono disponibili in alcuni paesi, non è possibile assegnare una licenza a un account utente, a meno che questo valore non sia configurato per l'account.** Per ulteriori informazioni, vedere [informazioni sulle restrizioni di licenza](https://go.microsoft.com/fwlink/p/?LinkId=691730).  <br/> |

>[!Note]
>[Informazioni su come creare account utente](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) con l'interfaccia di amministrazione di Microsoft 365. Per un elenco di risorse aggiuntive, vedere [Manage Users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

Una volta stabilita la connessione, utilizzare la sintassi seguente per creare un singolo account:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

In questo esempio viene creato un account per l'utente degli Stati Uniti chiamato Caleb Sills:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il modulo di Microsoft Azure Active Directory per Windows PowerShell

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="create-an-individual-user-account"></a>Creare un account utente singolo

Per creare un singolo account, utilizzare la sintassi seguente:
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.
>

Per elencare i nomi dei piani di gestione delle licenze disponibili, usare il seguente comando:

````powershell
Get-MsolAccountSku
````

In questo esempio viene creato un account per l'utente degli Stati Uniti chiamato Caleb Sills, a cui viene assegnata una licenza dal piano `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3).
  
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

 > [!NOTE]
>I nomi delle colonne e il relativo ordine nella prima riga del file CSV sono arbitrari, ma assicurano che i dati del resto del file corrispondano all'ordine dei nomi delle colonne e utilizzino i nomi delle colonne per i valori del parametro nel comando PowerShell per Microsoft 365.
    
2. Utilizzare la sintassi seguente:
    
  ```powershell
  Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
  ```

In questo esempio, vengono creati gli account utente dal file denominato C:\My Documents\NewAccounts.csv, quindi vengono registrati i risultati nel file C:\My Documents\NewAccountResults.csv
    
  ```powershell
  Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
  ```

3. Esaminare il file di output per visualizzare i risultati. Non sono state specificate le password, pertanto le password casuali generate da Microsoft 365 sono visibili nel file di output.
    
## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
