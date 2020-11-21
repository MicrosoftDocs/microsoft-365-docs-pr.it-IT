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
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="b3cdf-103">Script di esempio per l'applicazione delle impostazioni di Exchange Online Protection a più tenant</span><span class="sxs-lookup"><span data-stu-id="b3cdf-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b3cdf-104">Lo script di esempio seguente consente agli amministratori di Microsoft Exchange Online Protection (EOP) che gestiscono più tenant (aziende) di utilizzare PowerShell di Exchange Online per visualizzare e/o applicare le impostazioni di configurazione ai tenant.</span><span class="sxs-lookup"><span data-stu-id="b3cdf-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="b3cdf-105">Eseguire uno script o un cmdlet su più tenant</span><span class="sxs-lookup"><span data-stu-id="b3cdf-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="b3cdf-106">Se non è già stato [installato il modulo Exchange Online V2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="b3cdf-106">If you haven't already, [install the Exchange Online V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="b3cdf-107">Utilizzando un'app foglio di calcolo (ad esempio, Excel), creare un file con estensione CSV con i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="b3cdf-107">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="b3cdf-108">Colonna nomeutente: l'account che verrà utilizzato per la connessione (ad esempio, `admin@contoso.onmicrosoft.com` ).</span><span class="sxs-lookup"><span data-stu-id="b3cdf-108">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="b3cdf-109">Colonna cmdlet: il cmdlet o il comando da eseguire (ad esempio, `Get-AcceptedDomain` o `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="b3cdf-109">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="b3cdf-110">Il file avrà un aspetto analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="b3cdf-110">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="b3cdf-111">Salvare il file. csv in una posizione facile da trovare, ad esempio c:\scripts\inputfile.csv.</span><span class="sxs-lookup"><span data-stu-id="b3cdf-111">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="b3cdf-112">Copiare lo script [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) in blocco note e quindi salvare il file in un percorso facile da trovare (ad esempio, c:\Scripts).</span><span class="sxs-lookup"><span data-stu-id="b3cdf-112">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="b3cdf-113">Eseguire lo script utilizzando la seguente sintassi:</span><span class="sxs-lookup"><span data-stu-id="b3cdf-113">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="b3cdf-114">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="b3cdf-114">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="b3cdf-115">Ogni tenant verrà connesso e lo script verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="b3cdf-115">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="b3cdf-116">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="b3cdf-116">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="b3cdf-117">Potrebbe essere necessario modificare la `Connect-IPPSSession` riga nello script in modo che corrisponda all'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="b3cdf-117">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="b3cdf-118">Ad esempio, Office 365 Germany richiede un valore _ConnectionURI_ diverso rispetto al valore corrente in uno script.</span><span class="sxs-lookup"><span data-stu-id="b3cdf-118">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="b3cdf-119">Per ulteriori informazioni, vedere Connect to [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b3cdf-119">For details, see Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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
