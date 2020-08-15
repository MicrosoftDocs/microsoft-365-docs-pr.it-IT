---
title: Visualizzare le informazioni sulle licenze e i servizi di Microsoft 365 account con PowerShell
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
- PowerShell
- Ent_Office_Other
- LIL_Placement
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: Viene illustrato come utilizzare PowerShell per determinare i servizi Microsoft 365 assegnati agli utenti.
ms.openlocfilehash: 163a92ec31f700aa6157e58b49e23a1cec587815
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691545"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a>Visualizzare le informazioni sulle licenze e i servizi di Microsoft 365 account con PowerShell

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

In Microsoft 365, le licenze provenienti da piani di licenza (denominati anche SKU o piani Microsoft 365) offrono agli utenti l'accesso ai servizi Microsoft 365 definiti per tali piani. Tuttavia, un utente potrebbe non avere accesso a tutti i servizi disponibili in una licenza che gli è attualmente assegnata. È possibile utilizzare PowerShell per Microsoft 365 per visualizzare lo stato dei servizi negli account utente. 

Per ulteriori informazioni sui piani di gestione delle licenze, sulla licenza e sui servizi, vedere [View licences and Services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Successivamente, elencare i piani di licenza per il tenant con questo comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Utilizzare questi comandi per elencare i servizi disponibili in ogni piano di gestione delle licenze.

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

Utilizzare questi comandi per elencare le licenze assegnate a un account utente.

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Successivamente, eseguire il comando seguente per elencare i piani di gestione delle licenze disponibili nell'organizzazione. 

```powershell
Get-MsolAccountSku
```
>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.
>

Successivamente, eseguire il comando seguente per elencare i servizi disponibili in ogni piano di licenze e l'ordine in cui sono elencati (il numero di indice).

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
Utilizzare questo comando per elencare le licenze assegnate a un utente e l'ordine in cui sono elencate (il numero di indice).

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a>Per visualizzare i servizi per un account utente

Per visualizzare tutti i servizi Microsoft 365 a cui un utente ha accesso, utilizzare la sintassi seguente:
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

In questo esempio vengono illustrati i servizi ai quali l'utente BelindaN@litwareinc.com ha accesso. Vengono indicati i servizi associati a tutte le licenze assegnate al suo account.
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

Questo esempio mostra i servizi ai quali l'utente BelindaN@litwareinc.com ha accesso dalla prima licenza assegnata al suo account (il numero di indice è 0).
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

Per visualizzare tutti i servizi per un utente a cui sono state assegnate *più licenze*, utilizzare la sintassi seguente:

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```
 
## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)
