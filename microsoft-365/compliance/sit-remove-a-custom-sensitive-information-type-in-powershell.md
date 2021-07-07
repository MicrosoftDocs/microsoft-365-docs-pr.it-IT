---
title: Rimuovere un tipo di informazioni riservate personalizzato tramite PowerShell
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
description: Informazioni su come rimuovere un tipo di informazioni riservate personalizzato tramite PowerShell
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322694"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>Rimuovere un tipo di informazioni riservate personalizzato tramite PowerShell



PowerShell nel Centro conformità offre due metodi per rimuovere i tipi di informazioni sensibili personalizzati:

- **Rimuovere singoli tipi di informazioni riservate personalizzate**: utilizzare il metodo documentato in Modificare un tipo di informazioni riservate personalizzato tramite [PowerShell.](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell) È possibile esportare il pacchetto di regole personalizzate contenente il tipo di informazioni riservate personalizzato, rimuovere il tipo di informazioni riservate dal file XML e importare di nuovo il file XML aggiornato nel pacchetto di regole personalizzate esistente.

- **Rimuovere un pacchetto di regole personalizzato e tutti i tipi di informazioni riservate personalizzati che questo contiene**: questo metodo è descritto in questa sezione.

> [!NOTE]
> Prima di eliminare un tipo di informazioni sensibili personalizzato, verificare che nessun criterio DLP o regola del flusso di posta di Exchange (nota anche come regola di trasporto) faccia ancora riferimento al tipo di informazioni sensibili.

1. [Connettersi a PowerShell nel Centro conformità](/powershell/exchange/exchange-online-powershell)

2. Per rimuovere un pacchetto di regole personalizzato, usare il cmdlet [Remove -DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   È possibile utilizzare il valore Nome (per qualsiasi lingua) o il valore `RulePack id` (GUID) per identificare il pacchetto di regole.

   In questo esempio viene rimosso il pacchetto di regole denominato "Pacchetto di regole personalizzate ID dipendente".

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   Per informazioni dettagliate su sintassi e parametri, vedere [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).

3. Per verificare che sia stato rimosso correttamente un tipo di informazioni riservate personalizzato, eseguire uno dei passaggi seguenti:

   - Eseguire il cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) per verificare che il nuovo pacchetto di regole non sia più elencato:

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - Eseguire il cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) per verificare che i tipi di informazioni riservate nel pacchetto di regole rimosse non siano più elencati:

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     Per i tipi di informazioni riservate personalizzati, il valore proprietà Publisher sarà diverso da Microsoft Corporation.

   - Sostituire \<Name\> con il valore nome del tipo di informazioni riservate (ad esempio, l'ID del dipendente) ed eseguire il cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) per verificare che il tipo di informazioni riservate non sia più elencato:

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a>Ulteriori informazioni

- [Informazioni sulla prevenzione della perdita dei dati](dlp-learn-about-dlp.md)

- [Definizioni delle entità tipo di informazioni sensibili](sensitive-information-type-entity-definitions.md)

- [Cosa individuano le funzioni di prevenzione della perdita dei dati](what-the-dlp-functions-look-for.md)
