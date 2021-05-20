---
title: Assegnare Microsoft 365 licenze agli account utente con PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: In questo articolo imparerai a usare PowerShell per assegnare una Microsoft 365 licenza a utenti senza licenza.
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572622"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Assegnare Microsoft 365 licenze agli account utente con PowerShell

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Gli utenti non possono utilizzare alcun servizio Microsoft 365 a cui al proprio account non è stata assegnata una licenza da un piano di licenza. È possibile utilizzare PowerShell per assegnare rapidamente licenze ad account senza licenza. 

Agli account utente deve prima essere assegnata una posizione. La specifica di un percorso è una parte necessaria della creazione di un nuovo account utente [nell'Microsoft 365 di amministrazione](../admin/add-users/add-users.md). 

Per impostazione predefinita, gli account sincronizzati da Servizi di dominio Active Directory locali non hanno un percorso specificato. È possibile configurare un percorso per questi account da:

- L'interfaccia di amministrazione di Microsoft 365
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - Il [portale di Azure](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) ( Utenti di Active **Directory**> account utente > informazioni  >   di **contatto**  >  **profilo** Paese o  >  **area geografica**).

>[!Note]
>[Informazioni su come assegnare licenze agli account utente con l'interfaccia](../admin/manage/assign-licenses-to-users.md) Microsoft 365 amministrazione. Per un elenco delle risorse aggiuntive, vedere [Gestire utenti e gruppi](../admin/add-users/index.yml).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Innanzitutto, [connettersi al tenant Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  

Elencare quindi i piani di licenza per il tenant con questo comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Ottenere quindi il nome di accesso dell'account a cui si desidera aggiungere una licenza, noto anche come nome dell'entità utente (UPN).

Assicurarsi quindi che all'account utente sia assegnata una posizione di utilizzo.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Se non è stata assegnata alcuna posizione di utilizzo, è possibile assegnarla con questi comandi:

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Infine, specificare il nome di accesso utente e il nome del piano di licenza ed eseguire questi comandi.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Si noti che inizieremo a deprecare questo modulo quando la funzionalità di questo modulo è disponibile nel più [Azure Active Directory PowerShell per Graph](/powershell/azuread/v2/azureactivedirectory) modulo. Consigliamo ai clienti che stanno creando nuovi script di PowerShell di utilizzare il modulo più nuovo anziché questo modulo.

Innanzitutto, [connettersi al tenant Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Eseguire il `Get-MsolAccountSku` comando per visualizzare i piani di licenza disponibili e il numero di licenze disponibili in ogni piano dell'organizzazione. Il numero di licenze disponibili in ogni piano è **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**. Per ulteriori informazioni su piani di licenza, licenze e servizi, vedere [Visualizzare licenze e servizi con PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.
>

Per trovare gli account senza licenza nell'organizzazione, eseguire questo comando.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

È possibile assegnare licenze solo agli account utente la cui **proprietà UsageLocation** è impostata su un codice paese ISO 3166-1 alpha-2 valido. Ad esempio, US per gli Stati Uniti e FR per la Francia. Alcuni Microsoft 365 servizi non sono disponibili in alcuni paesi. Per ulteriori informazioni, vedere [Informazioni sulle restrizioni di licenza](https://go.microsoft.com/fwlink/p/?LinkId=691730).
    
Per trovare gli account che non hanno un valore **UsageLocation,** eseguire questo comando.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Per impostare il **valore UsageLocation** in un account, eseguire questo comando.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Ad esempio:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Se si usa il cmdlet **Get-MsolUser** senza utilizzare il parametro **-All**, vengono restituiti solo i primi 500 account.

### <a name="assigning-licenses-to-user-accounts"></a>Assegnazione di licenze agli account utente
    
Per assegnare una licenza a un utente, utilizzare il comando seguente in PowerShell.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

In questo esempio viene assegnata una licenza **dal piano di licenze litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) all'utente senza licenza **belindan \@ litwareinc.com**:
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Per assegnare una licenza a tutti gli utenti senza licenza, eseguire questo comando.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>Non è possibile assegnare più licenze a un utente dallo stesso piano di gestione delle licenze. Se non si dispone di una quantità sufficiente di licenze disponibili, le licenze vengono assegnate agli utenti nell'ordine in cui vengono restituiti dal cmdlet **Get-MsolUser** finché non vengono esaurite le licenze disponibili.
>

In questo esempio le licenze del **piano di licenza litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) vengono assegnate a tutti gli utenti senza licenza:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

In questo esempio vengono assegnate le stesse licenze agli utenti senza licenza nel reparto vendite negli Stati Uniti:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Spostare un utente in un abbonamento diverso (piano di licenza) con il modulo Azure Active Directory PowerShell per Graph utente

Innanzitutto, [connettersi al tenant Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Ottenere quindi il nome di accesso dell'account utente per il quale si desidera cambiare sottoscrizioni, noto anche come nome dell'entità utente (UPN).

Elencare quindi le sottoscrizioni (piani di licenza) per il tenant con questo comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Elencare quindi le sottoscrizioni attualmente disponibili nell'account utente con questi comandi.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Identificare la sottoscrizione attualmente in corso (la sottoscrizione FROM) e la sottoscrizione a cui l'utente si sta spostando (la sottoscrizione TO).

Infine, specificare i nomi delle sottotitoi TO e FROM (numeri di parte SKU) ed eseguire questi comandi.

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

È possibile verificare la modifica della sottoscrizione per l'account utente con questi comandi.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
