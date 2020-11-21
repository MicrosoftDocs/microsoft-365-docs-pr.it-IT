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
ms.openlocfilehash: dbb4135c89ac8d351c40bd7d9ce5301500a9b81b
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376568"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Script di esempio per l'applicazione delle impostazioni di Exchange Online Protection a più tenant

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Lo script di esempio seguente consente agli amministratori di Microsoft Exchange Online Protection (EOP) che gestiscono più tenant (aziende) di utilizzare PowerShell di Exchange Online per visualizzare e/o applicare le impostazioni di configurazione ai tenant.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Eseguire uno script o un cmdlet su più tenant

1. Se non è già stato [installato il modulo Exchange Online V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

2. Utilizzando un'app foglio di calcolo (ad esempio, Excel), creare un file con estensione CSV con i seguenti dettagli:

   - Colonna nomeutente: l'account che verrà utilizzato per la connessione (ad esempio, `admin@contoso.onmicrosoft.com` ).
   - Colonna cmdlet: il cmdlet o il comando da eseguire (ad esempio, `Get-AcceptedDomain` o `Get-AcceptedDomain | FT Name` ).

   Il file avrà un aspetto analogo al seguente:

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. Salvare il file. csv in una posizione facile da trovare, ad esempio c:\scripts\inputfile.csv.

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

> [!NOTE]
> Potrebbe essere necessario modificare la `Connect-IPPSSession` riga nello script in modo che corrisponda all'ambiente in uso. Ad esempio, Office 365 Germany richiede un valore _ConnectionURI_ diverso rispetto al valore corrente in uno script. Per ulteriori informazioni, vedere Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
#
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
#
# UserName,Cmdlet
# admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
# admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name

# Get the .csv file name as an argument to this script.
$FilePath = $args[0]

# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath

# Load the EXO V2 module
Import-Module ExchangeOnlineManagement

# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
  
# Get the current entry's UserName.
$UserName = $Company.UserName

# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet

# Connect to EOP PowerShell by using the current entry's UserName. Prompt for the password.
Connect-IPPSSession -UserPrincipalName $UserName -ConnectionUri https://ps.protection.outlook.com/powershell-liveid/

# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet

# End the current PowerShell session.
Disconnect-ExchangeOnline -Confirm:$false
}
```
