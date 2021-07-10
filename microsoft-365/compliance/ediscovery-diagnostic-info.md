---
title: Raccogliere informazioni di diagnostica di eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come raccogliere informazioni di diagnostica di eDiscovery per un caso di supporto Microsoft.
ms.openlocfilehash: b2441e0b7af8a82e24a8acca9e000e954e1c8964
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362595"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Raccogliere informazioni di diagnostica di eDiscovery

Occasionalmente i tecnici del supporto Tecnico Microsoft richiedono informazioni specifiche sul problema quando si apre un caso di supporto relativo a Core eDiscovery o Advanced eDiscovery. In questo articolo vengono fornite indicazioni su come raccogliere informazioni di diagnostica per aiutare i tecnici del supporto tecnico ad analizzare e risolvere i problemi. In genere, non è necessario raccogliere queste informazioni finché non viene richiesto da un tecnico del supporto Tecnico Microsoft.

> [!IMPORTANT]
> L'output dei cmdlet e le informazioni di diagnostica descritte in questo articolo possono includere informazioni riservate su controversie legali o indagini interne nell'organizzazione. Prima di inviare le informazioni di diagnostica non elaborate al supporto tecnico Microsoft, è consigliabile esaminare le informazioni e redigere eventuali informazioni riservate (ad esempio nomi o altre informazioni sulle parti per controversia legale o indagine) sostituendola con `XXXXXXX` . L'utilizzo di questo metodo indicherà anche al tecnico del supporto Tecnico Microsoft che le informazioni sono stati redatti.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Raccogliere informazioni di diagnostica per Core eDiscovery

La raccolta di informazioni di diagnostica per Core eDiscovery è basata su cmdlet, quindi dovrai usare PowerShell per centro sicurezza & conformità. Gli esempi di PowerShell seguenti eseguono cmdlet e quindi salvano l'output in un file di testo specificato. Nella maggior parte dei casi, è necessario eseguire solo uno di questi comandi.

Per eseguire i cmdlet seguenti, [connettersi a PowerShell </span> & Centro sicurezza](/powershell/exchange/connect-to-scc-powershell)e conformità. Dopo aver eseguito la connessione, eseguire uno o più dei comandi seguenti e assicurarsi di sostituire i segnaposto con i nomi degli oggetti effettivi.

Dopo aver esaminato il file di testo generato e aver redatto le informazioni riservate, inviarle al tecnico del supporto Tecnico Microsoft che sta lavorando al caso.

> [!NOTE]
> È inoltre possibile eseguire i comandi in questa sezione per raccogliere  informazioni di diagnostica per le ricerche e le esportazioni elencate nella pagina Ricerca contenuto del Centro conformità Microsoft 365.

### <a name="collect-information-about-searches"></a>Raccogliere informazioni sulle ricerche

Il comando seguente raccoglie informazioni utili quando si analizzano i problemi relativi a una ricerca contenuto o a una ricerca associata a un caso di eDiscovery di base.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Raccogliere informazioni sulle azioni di ricerca

Il comando seguente raccoglie informazioni per analizzare i problemi relativi all'anteprima, all'esportazione o all'eliminazione dei risultati di una ricerca contenuto o di una ricerca associata a un caso di eDiscovery di base. È possibile identificare il nome dell'azione di ricerca facendo clic su un'esportazione elencata nella **scheda** Esportazioni. Per identificare i nomi delle azioni di anteprima ed eliminazione, è possibile eseguire il cmdlet **Get-ComplianceSearchAction** per visualizzare un elenco di tutte le azioni. Il formato per il nome dell'azione di ricerca viene creato aggiungendo `_Preview` , o al nome della ricerca `_Export` `_Purge` corrispondente.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Raccogliere informazioni sui blocchi di eDiscovery

Quando un blocco di eDiscovery associato a un caso di eDiscovery di base non funziona come previsto, eseguire il comando seguente per raccogliere informazioni sui criteri di blocco del caso e sulla regola di blocco del caso associata per il blocco di eDiscovery. Il *nome del criterio di conservazione delle* maiuscole e minuscole nel comando seguente corrisponde al nome del blocco eDiscovery. È possibile identificare questo nome nelle schede **Esenzioni** nel caso core eDiscovery.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Raccogliere tutte le informazioni sul caso

A volte, non è evidente quali informazioni sono necessarie al supporto tecnico Microsoft per analizzare il problema. In questo caso, è possibile raccogliere tutte le informazioni di diagnostica per un caso di eDiscovery di base. Il nome del caso core di *eDiscovery* nel comando seguente corrisponde al nome di un caso visualizzato nella pagina **Core eDiscovery** nel Centro conformità Microsoft 365.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{$_|fl;"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Raccogliere informazioni di diagnostica per Advanced eDiscovery

La **Impostazioni** in un caso Advanced eDiscovery consente di copiare rapidamente le informazioni di diagnostica per il caso. Le informazioni di diagnostica vengono salvate negli Appunti in modo da poter essere incollate in un file di testo e inviate al supporto tecnico Microsoft.

1. Passare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su Mostra > **eDiscovery > Avanzate**.

2. Selezionare un caso e quindi fare clic sulla **Impostazioni.**

3. In **Informazioni caso** fare clic su **Seleziona.**

4. Nella pagina a comparsa fai clic su **Copia informazioni di** diagnostica per copiare le informazioni negli Appunti.

5. Aprire un file di testo (in Blocco note) e quindi incollare le informazioni nel file di testo.

6. Salvare il file di testo e assegnare un nome simile `AeD Diagnostic Info YYYY.MM.DD` (ad esempio, `AeD Diagnostic Info 2020.11.03` ).

Dopo aver esaminato il file e aver redatto le informazioni riservate, inviarlo al tecnico del supporto Tecnico Microsoft che sta lavorando al caso.
