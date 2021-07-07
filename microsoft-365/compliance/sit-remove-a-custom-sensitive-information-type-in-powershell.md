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
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="9ca59-103">Rimuovere un tipo di informazioni riservate personalizzato tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ca59-103">Remove a custom sensitive information type using PowerShell</span></span>



<span data-ttu-id="9ca59-104">PowerShell nel Centro conformità offre due metodi per rimuovere i tipi di informazioni sensibili personalizzati:</span><span class="sxs-lookup"><span data-stu-id="9ca59-104">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="9ca59-105">**Rimuovere singoli tipi di informazioni riservate personalizzate**: utilizzare il metodo documentato in Modificare un tipo di informazioni riservate personalizzato tramite [PowerShell.](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="9ca59-105">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type using PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell).</span></span> <span data-ttu-id="9ca59-106">È possibile esportare il pacchetto di regole personalizzate contenente il tipo di informazioni riservate personalizzato, rimuovere il tipo di informazioni riservate dal file XML e importare di nuovo il file XML aggiornato nel pacchetto di regole personalizzate esistente.</span><span class="sxs-lookup"><span data-stu-id="9ca59-106">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="9ca59-107">**Rimuovere un pacchetto di regole personalizzato e tutti i tipi di informazioni riservate personalizzati che questo contiene**: questo metodo è descritto in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="9ca59-107">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

> [!NOTE]
> <span data-ttu-id="9ca59-108">Prima di eliminare un tipo di informazioni sensibili personalizzato, verificare che nessun criterio DLP o regola del flusso di posta di Exchange (nota anche come regola di trasporto) faccia ancora riferimento al tipo di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="9ca59-108">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. [<span data-ttu-id="9ca59-109">Connettersi a PowerShell nel Centro conformità</span><span class="sxs-lookup"><span data-stu-id="9ca59-109">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

2. <span data-ttu-id="9ca59-110">Per rimuovere un pacchetto di regole personalizzato, usare il cmdlet [Remove -DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):</span><span class="sxs-lookup"><span data-stu-id="9ca59-110">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="9ca59-111">È possibile utilizzare il valore Nome (per qualsiasi lingua) o il valore `RulePack id` (GUID) per identificare il pacchetto di regole.</span><span class="sxs-lookup"><span data-stu-id="9ca59-111">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="9ca59-112">In questo esempio viene rimosso il pacchetto di regole denominato "Pacchetto di regole personalizzate ID dipendente".</span><span class="sxs-lookup"><span data-stu-id="9ca59-112">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="9ca59-113">Per informazioni dettagliate su sintassi e parametri, vedere [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="9ca59-113">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="9ca59-114">Per verificare che sia stato rimosso correttamente un tipo di informazioni riservate personalizzato, eseguire uno dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ca59-114">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="9ca59-115">Eseguire il cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) per verificare che il nuovo pacchetto di regole non sia più elencato:</span><span class="sxs-lookup"><span data-stu-id="9ca59-115">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="9ca59-116">Eseguire il cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) per verificare che i tipi di informazioni riservate nel pacchetto di regole rimosse non siano più elencati:</span><span class="sxs-lookup"><span data-stu-id="9ca59-116">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="9ca59-117">Per i tipi di informazioni riservate personalizzati, il valore proprietà Publisher sarà diverso da Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="9ca59-117">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="9ca59-118">Sostituire \<Name\> con il valore nome del tipo di informazioni riservate (ad esempio, l'ID del dipendente) ed eseguire il cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) per verificare che il tipo di informazioni riservate non sia più elencato:</span><span class="sxs-lookup"><span data-stu-id="9ca59-118">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a><span data-ttu-id="9ca59-119">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9ca59-119">More information</span></span>

- [<span data-ttu-id="9ca59-120">Informazioni sulla prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="9ca59-120">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="9ca59-121">Definizioni delle entità tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="9ca59-121">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="9ca59-122">Cosa individuano le funzioni di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="9ca59-122">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
