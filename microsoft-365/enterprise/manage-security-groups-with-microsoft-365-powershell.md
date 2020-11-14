---
title: Gestire i gruppi di sicurezza con PowerShell
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
description: Informazioni su come utilizzare PowerShell per gestire i gruppi di sicurezza.
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073232"
---
# <a name="manage-security-groups-with-powershell"></a>Gestire i gruppi di sicurezza con PowerShell

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

È possibile utilizzare PowerShell per Microsoft 365 come alternativa all'interfaccia di amministrazione di Microsoft 365 per gestire i gruppi di sicurezza. 

In questo articolo viene descritto l'elenco, la creazione, la modifica delle impostazioni e la rimozione di gruppi di sicurezza. 

Se per un blocco di comandi di questo articolo è necessario specificare i valori delle variabili, attenersi alla seguente procedura.

1. Copiare il blocco di comandi negli Appunti e incollarlo nel blocco note o in PowerShell Integrated script Environment (ISE).
2. Inserire i valori delle variabili e rimuovere i caratteri "<" e ">".
3. Eseguire i comandi nella finestra di PowerShell o in PowerShell ISE.

Vedere [mantenere l'appartenenza al gruppo di sicurezza](maintain-group-membership-with-microsoft-365-powershell.md) per gestire l'appartenenza ai gruppi con PowerShell.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Usare il modulo di Azure Active Directory PowerShell per Graph

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="list-your-groups"></a>Elencare i gruppi

Utilizzare questo comando per elencare tutti i gruppi.

```powershell
Get-AzureADGroup
```
Utilizzare questi comandi per visualizzare le impostazioni di un gruppo specifico in base al relativo nome visualizzato.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Creare un nuovo gruppo

Utilizzare questo comando per creare un nuovo gruppo di sicurezza.

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>Modificare le impostazioni di un gruppo

Visualizzare le impostazioni del gruppo con questi comandi.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Utilizzare quindi l'articolo [set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) per determinare la modalità di modifica di un'impostazione.

### <a name="remove-a-security-group"></a>Rimuovere un gruppo di sicurezza

Utilizzare questi comandi per rimuovere un gruppo di sicurezza.

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>Gestire i proprietari di un gruppo di sicurezza

Utilizzare questi comandi per visualizzare i proprietari correnti di un gruppo di sicurezza.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
Utilizzare questi comandi per aggiungere un account utente in base al **nome dell'entità utente (UPN)** ai proprietari correnti di un gruppo di sicurezza.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
Utilizzare questi comandi per aggiungere un account utente in base al relativo **nome visualizzato** ai proprietari correnti di un gruppo di sicurezza.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
Utilizzare questi comandi per rimuovere un account utente dal relativo **UPN** ai proprietari correnti di un gruppo di sicurezza.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

Utilizzare questi comandi per rimuovere un account utente dal relativo **nome visualizzato** ai proprietari correnti di un gruppo di sicurezza.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Usare il Modulo di Microsoft Azure Active Directory per Windows PowerShell

Per prima cosa, [connettersi al tenant Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="list-your-groups"></a>Elencare i gruppi

Utilizzare questo comando per elencare tutti i gruppi.

```powershell
Get-MsolGroup
```
Utilizzare questi comandi per visualizzare le impostazioni di un gruppo specifico in base al relativo nome visualizzato.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Creare un nuovo gruppo

Utilizzare questo comando per creare un nuovo gruppo di sicurezza.

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>Modificare le impostazioni di un gruppo

Visualizzare le impostazioni del gruppo con questi comandi.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Utilizzare quindi l'articolo [set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) per determinare la modalità di modifica di un'impostazione.

### <a name="remove-a-security-group"></a>Rimuovere un gruppo di sicurezza

Utilizzare questi comandi per rimuovere un gruppo di sicurezza.

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>Vedere anche

[Gestire gli account utente, le licenze e i gruppi di Microsoft 365 con PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Gestire Microsoft 365 con PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Guida introduttiva a PowerShell per Microsoft 365](getting-started-with-microsoft-365-powershell.md)

