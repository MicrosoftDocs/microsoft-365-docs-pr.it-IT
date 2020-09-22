---
title: Script di esempio per le impostazioni di EOP-più tenant
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni su come utilizzare PowerShell per applicare le impostazioni di configurazione ai tenant in Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 6e33ceb6a9daa88bfefd4ec08ac9f2a9f34a942f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198680"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Script di esempio per l'applicazione delle impostazioni di Exchange Online Protection a più tenant

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Il seguente script di esempio consente agli amministratori di Microsoft Exchange Online Protection (EOP) che gestiscono più tenant (aziende) di utilizzare Windows PowerShell per applicare le impostazioni di configurazione ai tenant.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Eseguire uno script o un cmdlet su più tenant

1. Usando un'applicazione quale Excel, creare un file .csv (ad esempio, c:\scripts\inputfile.csv):

2. Nel file .csv, specificare due nomi di colonna: UserName e Cmdlet.

3. Per ogni riga del file .csv, aggiungere il nome dell'amministratore del tenant nella colonna NomeUtente e il cmdlet da eseguire per quel tenant nella colonna denominata Cmdlet. Ad esempio, utilizzare admin@contoso.com e Get-AcceptedDomain.

4. Copiare lo script [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) in blocco note e quindi salvare il file in un percorso facile da trovare (ad esempio, c:\Scripts).

5. Eseguire lo script utilizzando la seguente sintassi:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Di seguito viene riportato un esempio:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. Ogni tenant verrà connesso e lo script verrà eseguito.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```
