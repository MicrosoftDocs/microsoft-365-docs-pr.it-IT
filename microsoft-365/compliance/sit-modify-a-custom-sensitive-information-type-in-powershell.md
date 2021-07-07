---
title: Modificare un tipo di informazioni riservate personalizzato tramite PowerShell
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come modificare informazioni riservate personalizzate tramite PowerShell.
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322695"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="e47e9-103">Modificare un tipo di informazioni riservate personalizzato tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="e47e9-103">Modify a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="e47e9-104">In PowerShell nel Centro conformità, la modifica di un tipo di informazioni riservate personalizzato richiede di:</span><span class="sxs-lookup"><span data-stu-id="e47e9-104">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="e47e9-105">Esportare il pacchetto di regole esistente contenente il tipo di informazioni riservate personalizzato in un file XML (oppure utilizzare il file XML esistente, se disponibile).</span><span class="sxs-lookup"><span data-stu-id="e47e9-105">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="e47e9-106">Modificare il tipo di informazioni riservate personalizzato nel file XML esportato.</span><span class="sxs-lookup"><span data-stu-id="e47e9-106">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="e47e9-107">Importare nuovamente il file XML aggiornato nel pacchetto di regole esistente.</span><span class="sxs-lookup"><span data-stu-id="e47e9-107">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="e47e9-108">Per connettersi a PowerShell nel Centro conformità, vedere [Connettersi a PowerShell nel Centro conformità](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e47e9-108">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="e47e9-109">Passaggio 1: esportare il pacchetto di regole esistente in un file XML</span><span class="sxs-lookup"><span data-stu-id="e47e9-109">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="e47e9-110">Se si possiede una copia del file XML (ad esempio, se lo si è appena creato e importato), è possibile andare al passaggio successivo per modificare il file XML.</span><span class="sxs-lookup"><span data-stu-id="e47e9-110">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="e47e9-111">Se non lo si conosce già, eseguire il cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) per trovare il nome del pacchetto di regole personalizzato:</span><span class="sxs-lookup"><span data-stu-id="e47e9-111">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="e47e9-p101">Nota: il pacchetto di regole predefinite che contiene i tipi di informazioni sensibili predefinito è denominato Pacchetto di regole di Microsoft. Il pacchetto di regole che contiene i tipi di informazioni sensibili personalizzato creato nell'interfaccia utente del Centro conformità è denominato Microsoft.SCCManaged.CustomRulePack.</span><span class="sxs-lookup"><span data-stu-id="e47e9-p101">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package. The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="e47e9-114">Usare il cmdlet [Get- DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) per archiviare il pacchetto di regole personalizzato in una variabile:</span><span class="sxs-lookup"><span data-stu-id="e47e9-114">Use the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="e47e9-115">Ad esempio, se il nome del pacchetto di regole è "Pacchetto di regole personalizzate ID dipendente", eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="e47e9-115">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="e47e9-116">Usare il cmdlet [Set-Content](/powershell/module/microsoft.powershell.management/set-content) per esportare il pacchetto di regole personalizzato in un file XML:</span><span class="sxs-lookup"><span data-stu-id="e47e9-116">Use the [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="e47e9-117">In questo esempio, il pacchetto di regole viene esportato in un file denominato ExportedRulePackage.xml nella cartella C:\Documenti.</span><span class="sxs-lookup"><span data-stu-id="e47e9-117">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="e47e9-118">Passaggio 2: modificare il tipo di informazioni riservate nel file XML esportato</span><span class="sxs-lookup"><span data-stu-id="e47e9-118">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="e47e9-119">I tipi di informazioni riservate nel file XML e altri elementi nel file sono descritti precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e47e9-119">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="e47e9-120">Passaggio 3: importare nuovamente il file XML aggiornato nel pacchetto di regole esistente</span><span class="sxs-lookup"><span data-stu-id="e47e9-120">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="e47e9-121">Per importare nuovamente il file XML aggiornato nel pacchetto di regole esistente, usare il cmdlet [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage):</span><span class="sxs-lookup"><span data-stu-id="e47e9-121">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="e47e9-122">Per informazioni dettagliate su sintassi e parametri, vedere [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="e47e9-122">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>


## <a name="more-information"></a><span data-ttu-id="e47e9-123">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="e47e9-123">More information</span></span>

- [<span data-ttu-id="e47e9-124">Informazioni sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="e47e9-124">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="e47e9-125">Definizioni delle entità tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="e47e9-125">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="e47e9-126">Cosa individuano le funzioni di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="e47e9-126">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
