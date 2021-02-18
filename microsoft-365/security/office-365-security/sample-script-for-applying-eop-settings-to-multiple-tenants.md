---
title: Script di esempio per le impostazioni di EOP - più tenant
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: In questo articolo viene illustrato come utilizzare PowerShell per applicare le impostazioni di configurazione ai tenant in Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4823ed09cd8a9d72aef21df3d51213cb4512b4f9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288538"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="1f150-103">Script di esempio per l'applicazione delle impostazioni di Exchange Online Protection a più tenant</span><span class="sxs-lookup"><span data-stu-id="1f150-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1f150-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="1f150-104">**Applies to**</span></span>
-  [<span data-ttu-id="1f150-105">Exchange Online Protection autonomo</span><span class="sxs-lookup"><span data-stu-id="1f150-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="1f150-106">Il seguente script di esempio consente agli amministratori di Microsoft Exchange Online Protection (EOP) che gestiscono più tenant (società) di utilizzare PowerShell di Exchange Online per visualizzare e/o applicare le impostazioni di configurazione ai tenant.</span><span class="sxs-lookup"><span data-stu-id="1f150-106">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="1f150-107">Eseguire uno script o un cmdlet su più tenant</span><span class="sxs-lookup"><span data-stu-id="1f150-107">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="1f150-108">Se non è già stato fatto, [installare il modulo V2 di Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)</span><span class="sxs-lookup"><span data-stu-id="1f150-108">If you haven't already, [install the Exchange Online V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="1f150-109">Usando un'app per fogli di calcolo (ad esempio, Excel), crea un file CSV con i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="1f150-109">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="1f150-110">Colonna UserName: l'account che verrà utilizzato per la connessione (ad esempio, `admin@contoso.onmicrosoft.com` ).</span><span class="sxs-lookup"><span data-stu-id="1f150-110">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="1f150-111">Colonna cmdlet: il cmdlet o il comando da eseguire (ad esempio, `Get-AcceptedDomain` o `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="1f150-111">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="1f150-112">Il file sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1f150-112">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="1f150-113">Salvare il file CSV in un percorso facile da trovare, ad esempio c:\scripts\inputfile.csv.</span><span class="sxs-lookup"><span data-stu-id="1f150-113">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="1f150-114">Copiare [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script nel Blocco note e quindi salvare il file in un percorso facile da trovare, ad esempio c:\scripts.</span><span class="sxs-lookup"><span data-stu-id="1f150-114">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="1f150-115">Eseguire lo script utilizzando la seguente sintassi:</span><span class="sxs-lookup"><span data-stu-id="1f150-115">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="1f150-116">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="1f150-116">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="1f150-117">A ogni tenant verrà eseguito l'accesso e lo script verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="1f150-117">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="1f150-118">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="1f150-118">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="1f150-119">Potrebbe essere necessario modificare la `Connect-IPPSSession` riga nello script in modo che corrisponda al proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="1f150-119">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="1f150-120">Ad esempio, Office 365 Germany richiede un _valore ConnectionUri_ diverso da quello corrente in uno script.</span><span class="sxs-lookup"><span data-stu-id="1f150-120">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="1f150-121">Per informazioni dettagliate, vedere Connettersi [a PowerShell di Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="1f150-121">For details, see Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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
