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
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="8269f-103">Script di esempio per l'applicazione delle impostazioni di Exchange Online Protection a più tenant</span><span class="sxs-lookup"><span data-stu-id="8269f-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8269f-104">Il seguente script di esempio consente agli amministratori di Microsoft Exchange Online Protection (EOP) che gestiscono più tenant (aziende) di utilizzare Windows PowerShell per applicare le impostazioni di configurazione ai tenant.</span><span class="sxs-lookup"><span data-stu-id="8269f-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Windows PowerShell to apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="8269f-105">Eseguire uno script o un cmdlet su più tenant</span><span class="sxs-lookup"><span data-stu-id="8269f-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="8269f-106">Usando un'applicazione quale Excel, creare un file .csv (ad esempio, c:\scripts\inputfile.csv):</span><span class="sxs-lookup"><span data-stu-id="8269f-106">Using an application such as Excel, create a .csv file (for example, c:\scripts\inputfile.csv):</span></span>

2. <span data-ttu-id="8269f-107">Nel file .csv, specificare due nomi di colonna: UserName e Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8269f-107">In the .csv file, specify two column names: UserName and Cmdlet.</span></span>

3. <span data-ttu-id="8269f-p101">Per ogni riga del file .csv, aggiungere il nome dell'amministratore del tenant nella colonna NomeUtente e il cmdlet da eseguire per quel tenant nella colonna denominata Cmdlet. Ad esempio, utilizzare admin@contoso.com e Get-AcceptedDomain.</span><span class="sxs-lookup"><span data-stu-id="8269f-p101">For each row in the .csv file, add the tenant's admin name in the UserName column and the cmdlet to run for that tenant in the Cmdlet column. For example, use admin@contoso.com and Get-AcceptedDomain.</span></span>

4. <span data-ttu-id="8269f-110">Copiare lo script [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) in blocco note e quindi salvare il file in un percorso facile da trovare (ad esempio, c:\Scripts).</span><span class="sxs-lookup"><span data-stu-id="8269f-110">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find  (for example, c:\scripts).</span></span>

5. <span data-ttu-id="8269f-111">Eseguire lo script utilizzando la seguente sintassi:</span><span class="sxs-lookup"><span data-stu-id="8269f-111">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="8269f-112">Di seguito viene riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="8269f-112">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="8269f-113">Ogni tenant verrà connesso e lo script verrà eseguito.</span><span class="sxs-lookup"><span data-stu-id="8269f-113">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="8269f-114">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="8269f-114">RunCmdletOnMultipleTenants.ps1</span></span>

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
