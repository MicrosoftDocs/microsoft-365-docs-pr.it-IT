---
title: Disabilitare l'accesso Microsoft 365 servizi durante l'assegnazione delle licenze utente
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: Informazioni su come assegnare licenze agli account utente e disabilitare piani di servizio specifici contemporaneamente usando PowerShell per Microsoft 365.
ms.openlocfilehash: ca5becb8709eeab7b5c535747ac93d36fefa0da8
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228904"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a>Disabilitare l'accesso Microsoft 365 servizi durante l'assegnazione delle licenze utente

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Microsoft 365 sono disponibili piani di servizio per singoli servizi. Microsoft 365 gli amministratori devono spesso disabilitare determinati piani quando assegnano licenze agli utenti. Con le istruzioni contenute in questo articolo, è possibile assegnare una licenza di Microsoft 365 disabilitando piani di servizio specifici tramite PowerShell per un singolo account utente o più account utente.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)


Successivamente, elencare i piani di licenza per il tenant con questo comando.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Successivamente, ottenere il nome di accesso dell'account a cui si desidera aggiungere una licenza, noto anche come nome dell'entità utente (UPN).

Successivamente, compilare un elenco di servizi da abilitare. Per un elenco completo dei piani di licenza (noti anche come nomi di prodotto), dei piani di servizio inclusi e dei nomi descrittivi corrispondenti, vedere Nomi dei prodotti e identificatori del piano di servizio [per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Per il blocco di comandi seguente, inserire il nome dell'entità utente dell'account utente, il numero della parte SKU e l'elenco dei piani di servizio per abilitare e rimuovere il testo esplicativo e i \< and > caratteri. Successivamente, eseguire i comandi risultanti nel prompt dei comandi di PowerShell.

```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Prima di [tutto, connettersi al tenant Microsoft 365 .](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Eseguire quindi questo comando per visualizzare le sottoscrizioni correnti:

```powershell
Get-MsolAccountSku
```

>[!Note]
>PowerShell Core non supporta il modulo di Microsoft Azure Active Directory per Windows PowerShell e i cmdlet con **MSOL** all'interno del nome. Per continuare a usare i cmdlet, è necessario eseguirli in Windows PowerShell.
>

Nella visualizzazione del comando  `Get-MsolAccountSku`:

- **AccountSkuId** è un abbonamento per l'organizzazione nel formato \<OrganizationName>:\<Subscription>. Il valore specificato al momento della registrazione a Microsoft 365 \<OrganizationName> ed è univoco per l'organizzazione. Il valore \<Subscription> è per una sottoscrizione specifica. Ad esempio, per litwareinc:ENTERPRISEPACK, il nome dell'organizzazione è litwareinc e il nome della sottoscrizione è ENTERPRISEPACK (Office 365 Enterprise E3).

- **ActiveUnits** è il numero di licenze acquistate per la sottoscrizione.

- **WarningUnits** è il numero di licenze in una sottoscrizione non rinnovata e che scadrà dopo il periodo di prova di 30 giorni.

- **ConsumedUnits** è il numero di licenze assegnate agli utenti per la sottoscrizione.

Nota accountSkuId per la sottoscrizione Microsoft 365 che contiene gli utenti di cui vuoi ottenere la licenza. Inoltre, assicurarsi che siano disponibili licenze sufficienti da assegnare (sottrarre **ConsumedUnits** da **ActiveUnits**).

Eseguire quindi questo comando per visualizzare i dettagli sui piani di Microsoft 365 disponibili in tutte le sottoscrizioni:

```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

Dalla visualizzazione di questo comando, stabilire quali piani di servizio si desidera disattivare quando si assegnano le licenze agli utenti.

Ecco un elenco parziale dei piani di servizio e dei servizi Microsoft 365 corrispondenti.

Nella tabella seguente vengono illustrati i Microsoft 365 e i relativi nomi descrittivi per i servizi più comuni. L'elenco dei piani di servizio degli utenti potrebbe essere diverso.

|**Piano di servizio**|**Descrizione**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Microsoft 365 Apps for enterprise *(precedentemente denominato Office 365 ProPlus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype for Business Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online, piano 2  <br/> |

Per un elenco completo dei piani di licenza (noti anche come nomi di prodotto), dei piani di servizio inclusi e dei nomi descrittivi corrispondenti, vedere Nomi dei prodotti e identificatori del piano di servizio [per le licenze](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).

Dopo aver creato AccountSkuId e i piani di servizio da disabilitare, è possibile assegnare licenze per un singolo utente o per più utenti.

### <a name="for-a-single-user"></a>Per un utente singolo

Per un singolo utente, inserire il nome dell'entità utente dell'account utente, l'AccountSkuId e l'elenco dei piani di servizio per disabilitare e rimuovere il testo esplicativo e i \< and > caratteri. Successivamente, eseguire i comandi risultanti nel prompt dei comandi di PowerShell.

```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

Ecco un blocco di comando di esempio per l'account denominato belindan@contoso.com, per la licenza contoso:ENTERPRISEPACK e i piani di servizio da disabilitare sono RMS_S_ENTERPRISE, SWAY, INTUNE_O365 e YAMMER_ENTERPRISE:

```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a>Per più utenti

Per eseguire questa attività di amministrazione per più utenti, creare un file CSV contenente i campi UserPrincipalName e UsageLocation. Ecco un esempio:

```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

Successivamente, immettere il percorso dei file CSV di input e output, l'ID SKU dell'account e l'elenco dei piani di servizio da disabilitare, quindi eseguire i comandi risultanti nel prompt dei comandi di PowerShell.

```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

Blocco di comando di PowerShell:

- Visualizza il nome dell'entità utente di ogni utente.

- Assegna licenze personalizzate a ogni utente.

- Crea un file CSV con tutti gli utenti che sono stati elaborati e mostra il relativo stato della licenza.

## <a name="see-also"></a>Vedere anche

[Disabilitare l'accesso Microsoft 365 servizi con PowerShell](disable-access-to-services-with-microsoft-365-powershell.md)

[Disabilitare l'accesso a Sway con PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md)

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)