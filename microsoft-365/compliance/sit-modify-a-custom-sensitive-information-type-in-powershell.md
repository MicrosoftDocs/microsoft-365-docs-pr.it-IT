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
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a>Modificare un tipo di informazioni riservate personalizzato tramite PowerShell

In PowerShell nel Centro conformità, la modifica di un tipo di informazioni riservate personalizzato richiede di:

1. Esportare il pacchetto di regole esistente contenente il tipo di informazioni riservate personalizzato in un file XML (oppure utilizzare il file XML esistente, se disponibile).

2. Modificare il tipo di informazioni riservate personalizzato nel file XML esportato.

3. Importare nuovamente il file XML aggiornato nel pacchetto di regole esistente.

Per connettersi a PowerShell nel Centro conformità, vedere [Connettersi a PowerShell nel Centro conformità](/powershell/exchange/exchange-online-powershell).

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>Passaggio 1: esportare il pacchetto di regole esistente in un file XML

> [!NOTE]
> Se si possiede una copia del file XML (ad esempio, se lo si è appena creato e importato), è possibile andare al passaggio successivo per modificare il file XML.

1. Se non lo si conosce già, eseguire il cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) per trovare il nome del pacchetto di regole personalizzato:

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > Nota: il pacchetto di regole predefinite che contiene i tipi di informazioni sensibili predefinito è denominato Pacchetto di regole di Microsoft. Il pacchetto di regole che contiene i tipi di informazioni sensibili personalizzato creato nell'interfaccia utente del Centro conformità è denominato Microsoft.SCCManaged.CustomRulePack.

2. Usare il cmdlet [Get- DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) per archiviare il pacchetto di regole personalizzato in una variabile:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   Ad esempio, se il nome del pacchetto di regole è "Pacchetto di regole personalizzate ID dipendente", eseguire il cmdlet seguente:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. Usare il cmdlet [Set-Content](/powershell/module/microsoft.powershell.management/set-content) per esportare il pacchetto di regole personalizzato in un file XML:

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   In questo esempio, il pacchetto di regole viene esportato in un file denominato ExportedRulePackage.xml nella cartella C:\Documenti.

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>Passaggio 2: modificare il tipo di informazioni riservate nel file XML esportato

I tipi di informazioni riservate nel file XML e altri elementi nel file sono descritti precedenza in questo argomento.

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>Passaggio 3: importare nuovamente il file XML aggiornato nel pacchetto di regole esistente

Per importare nuovamente il file XML aggiornato nel pacchetto di regole esistente, usare il cmdlet [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage):

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

Per informazioni dettagliate su sintassi e parametri, vedere [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).


## <a name="more-information"></a>Ulteriori informazioni

- [Informazioni sulla prevenzione della perdita dei dati](dlp-learn-about-dlp.md)

- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)

- [Cosa individuano le funzioni di prevenzione della perdita dei dati](what-the-dlp-functions-look-for.md)
