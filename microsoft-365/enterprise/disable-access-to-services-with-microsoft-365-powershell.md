---
title: Disabilitare l'accesso ai servizi di Microsoft 365 con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: In questo articolo viene illustrato come usare PowerShell per disabilitare l'accesso ai servizi di Microsoft 365 per gli utenti.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691176"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>Disabilitare l'accesso ai servizi di Microsoft 365 con PowerShell

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Quando a un account di Microsoft 365 viene assegnata una licenza da un piano di gestione delle licenze, i servizi di Microsoft 365 vengono resi disponibili all'utente da tale licenza. Tuttavia, è possibile controllare i servizi di Microsoft 365 a cui l'utente può accedere. Ad esempio, anche se la licenza consente l'accesso al servizio SharePoint Online, è possibile disabilitare l'accesso al servizio. È possibile utilizzare PowerShell per disabilitare l'accesso a un numero qualsiasi di servizi per uno specifico piano di gestione delle licenze per:

- Un singolo account.
- Un gruppo di account.
- Tutti gli account nell'organizzazione.

>[!Note]
>Esistono dipendenze dei servizi di Microsoft 365 che possono impedire la disabilitazione di un servizio specificato quando altri servizi dipendono da esso.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Prima di [tutto, connettersi al tenant di Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Successivamente, utilizzare questo comando per visualizzare i piani di licenza disponibili, noti anche come AccountSkuIds:

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.
>

Per ulteriori informazioni, vedere [Visualizzare licenze e servizi con PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)
    
Per visualizzare i risultati prima e dopo le procedure descritte in questo argomento, vedere Visualizzare i dettagli relativi alla licenza dell'account e al servizio [con PowerShell.](view-account-license-and-service-details-with-microsoft-365-powershell.md)
    
Uno script PowerShell è disponibile per rendere automatiche le procedure descritte in questo argomento. In particolare, lo script consente di visualizzare e disabilitare i servizi nell'organizzazione di Microsoft 365, incluso Sway. Per ulteriori informazioni, vedere [Disabilitare l'accesso a Sway con PowerShell.](disable-access-to-sway-with-microsoft-365-powershell.md)
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>Disabilitare specifici servizi di Microsoft 365 per utenti specifici per un piano di gestione delle licenze specifico
  
Per disabilitare un set specifico di servizi di Microsoft 365 per gli utenti per un piano di gestione delle licenze specifico, eseguire la procedura seguente:
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a>Passaggio 1: identificare i servizi indesiderati nel piano di gestione delle licenze utilizzando la sintassi seguente:
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

Nell'esempio seguente viene creato un oggetto **LicenseOptions** che disabilita i servizi Office e SharePoint Online nel piano di gestione delle licenze `litwareinc:ENTERPRISEPACK` denominato (Office 365 Enterprise E3).
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>Passaggio 2: Utilizzare **l'oggetto LicenseOptions** del passaggio 1 per uno o più utenti.
    
Per creare un nuovo account con i servizi disabilitati, utilizzare la sintassi seguente:
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

Nell'esempio seguente viene creato un nuovo account per Allie Bellew che assegna la licenza e disabilita i servizi descritti nel passaggio 1.
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

Per ulteriori informazioni sulla creazione di account utente in PowerShell per Microsoft 365, vedere [Creare account utente con PowerShell.](create-user-accounts-with-microsoft-365-powershell.md)
    
Per disabilitare i servizi per un utente dotato di una licenza esistente, utilizzare la sintassi seguente:
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

In questo esempio vengono disabilitati i servizi per l'utente BelindaN@litwareinc.com.
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

Per disabilitare i servizi descritti nel passaggio 1 per tutti gli utenti con licenza esistenti, specificare il nome del piano di Microsoft 365 dalla visualizzazione del cmdlet **Get-MsolAccountSku** (ad esempio **litwareinc:ENTERPRISEPACK),** quindi eseguire i comandi seguenti:
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 Se si utilizza il cmdlet **Get-MsolUser** senza utilizzare il parametro _All,_ vengono restituiti solo i primi 500 account utente.

Per disabilitare i servizi per un gruppo di utenti esistenti, utilizzare uno dei metodi seguenti per identificare gli utenti:
    
**Metodo 1. Filtrare gli account in base a un attributo account esistente** 

A tal fine, utilizzare la sintassi seguente:
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

Nell'esempio seguente vengono disabilitati i servizi per gli utenti del reparto Vendite (Sales) negli Stati Uniti.
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**Metodo 2: Utilizzare un elenco di account specifici** 

A tal fine, procedere come segue:
    
1. Creare un file di testo contenente un account su ogni riga come riportato di seguito:
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   In questo esempio il file di testo è C: \\ Documenti \\Accounts.txt.
    
2. Eseguire il comando riportato di seguito:
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

Se si desidera disabilitare l'accesso ai servizi per più piani di gestione delle licenze, ripetere le istruzioni precedenti per ogni piano di licenza, assicurandosi che:

- Agli account utente è stato assegnato il piano di gestione delle licenze.
- I servizi da disabilitare sono disponibili nel piano di gestione delle licenze.

Per disabilitare i servizi di Microsoft 365 per gli utenti mentre vengono assegnati a un piano di gestione delle licenze, vedere Disabilitare l'accesso ai servizi durante l'assegnazione [delle licenze utente.](disable-access-to-services-while-assigning-user-licenses.md)

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>Assegnare tutti i servizi in un piano di gestione delle licenze a un account utente

Per gli account utente in cui sono stati disabilitati i servizi, è possibile abilitare tutti i servizi per uno specifico piano di gestione delle licenze con questi comandi:

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>Argomento correlato

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
