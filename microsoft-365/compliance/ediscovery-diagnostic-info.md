---
title: Raccolta delle informazioni di diagnostica di eDiscovery
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
description: Informazioni su come raccogliere dati di diagnostica di eDiscovery per un caso di supporto Microsoft.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944393"
---
# <a name="collect-ediscovery-diagnostic-information"></a>Raccolta delle informazioni di diagnostica di eDiscovery

Occasionalmente gli ingegneri del supporto tecnico Microsoft richiedono informazioni specifiche sul problema quando si apre un caso di supporto relativo a eDiscovery di base o Advanced eDiscovery. In questo articolo vengono fornite indicazioni su come raccogliere informazioni di diagnostica per aiutare gli ingegneri del supporto a analizzare e risolvere i problemi. In genere, non è necessario raccogliere queste informazioni fino a quando non viene richiesto da un tecnico del supporto Microsoft.

> [!IMPORTANT]
> L'output dei cmdlet e delle informazioni di diagnostica descritti in questo articolo può includere informazioni riservate relative a controversie legali o indagini interne nell'organizzazione. Prima di inviare le informazioni di diagnostica non elaborate al supporto tecnico Microsoft, è consigliabile esaminare le informazioni e redigere eventuali informazioni riservate (ad esempio, nomi o altre informazioni sulle parti di una controversia legale o indagini) sostituendo con `XXXXXXX` . L'utilizzo di questo metodo indicherà anche all'ingegnere del supporto tecnico Microsoft che sono state redatte informazioni.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Raccogliere informazioni di diagnostica per eDiscovery di base

La raccolta di informazioni di diagnostica per eDiscovery di base è basata su cmdlet, pertanto è necessario utilizzare PowerShell per la sicurezza & Compliance Center. Negli esempi di PowerShell seguenti vengono eseguiti i cmdlet e quindi viene salvato l'output in un file di testo specificato. Nella maggior parte dei casi di supporto, è necessario eseguire solo uno di questi comandi.

Per eseguire i cmdlet seguenti, [connettersi a PowerShell </span> per centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell). Dopo aver eseguito la connessione, eseguire uno o più dei comandi seguenti e assicurarsi di sostituire i segnaposto con i nomi degli oggetti effettivi.

Dopo aver esaminato il file di testo generato e relazioni le informazioni riservate, inviarlo al supporto tecnico Microsoft per il caso.

> [!NOTE]
> È inoltre possibile eseguire i comandi in questa sezione per raccogliere informazioni di diagnostica per le ricerche e le esportazioni elencate nella pagina **Ricerca contenuto** nel centro conformità di Microsoft 365.

### <a name="collect-information-about-searches"></a>Raccogliere informazioni sulle ricerche

Il seguente comando raccoglie informazioni utili quando si esaminano i problemi relativi a una ricerca di contenuto o a una ricerca associata a un caso di eDiscovery di base.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>Raccogliere informazioni sulle azioni di ricerca

Il comando seguente consente di raccogliere informazioni per esaminare i problemi relativi alla visualizzazione in anteprima, all'esportazione o all'eliminazione dei risultati di una ricerca di contenuto o di una ricerca associata a un caso di eDiscovery di base. È possibile identificare il nome dell'azione di ricerca facendo clic su un'esportazione elencata nella scheda **esportazioni** . Per identificare i nomi delle azioni di anteprima e di eliminazione, è possibile eseguire il cmdlet **Get-ComplianceSearchAction** per visualizzare un elenco di tutte le azioni. Il formato del nome dell'azione di ricerca è costruito aggiungendo `_Preview` , `_Export` o `_Purge` al nome della ricerca corrispondente.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>Raccogliere informazioni sulle stive di eDiscovery

Quando una conservazione di eDiscovery associata a un caso di eDiscovery Core non funziona come previsto, eseguire il comando seguente per raccogliere informazioni sui criteri di conservazione dei casi e la regola di blocco del caso associata per il blocco eDiscovery. Il *nome del criterio di blocco del caso* nel comando seguente è lo stesso del nome dell'esenzione di eDiscovery. È possibile identificare questo nome nelle schede **esenzioni** nel caso di eDiscovery di base.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>Raccogliere tutte le informazioni sul caso

A volte, non è evidente quali informazioni devono essere richieste dal supporto tecnico Microsoft per esaminare il problema. In questa situazione, è possibile raccogliere tutte le informazioni di diagnostica per un caso di eDiscovery di base. Il *nome del case di eDiscovery di base* nel comando seguente è lo stesso del nome di un caso visualizzato nella pagina **Core eDiscovery** nel centro conformità di Microsoft 365.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Raccogliere informazioni di diagnostica per Advanced eDiscovery

La scheda **Impostazioni** in un caso avanzato di eDiscovery consente di copiare rapidamente le informazioni di diagnostica per il caso. Le informazioni di diagnostica vengono salvate negli Appunti in modo che sia possibile incollarle in un file di testo e inviarle al supporto tecnico Microsoft.

1. Andare a [https://compliance.microsoft.com](https://compliance.microsoft.com/) e quindi fare clic su **mostra tutti > eDiscovery > Advanced**.

2. Selezionare un caso e quindi fare clic sulla scheda **Impostazioni** .

3. In **informazioni sul caso** , fare clic su **Seleziona**.

4. Nella pagina riquadro a comparsa, fare clic su **copia informazioni di diagnostica** per copiare le informazioni negli Appunti.

5. Aprire un file di testo (in blocco note) e quindi incollare le informazioni nel file di testo.

6. Salvare il file di testo e denominarlo come `AeD Diagnostic Info YYYY.MM.DD` (ad esempio, `AeD Diagnostic Info 2020.11.03` ).

Dopo aver esaminato il file e relazioni le informazioni riservate, inviarlo al supporto tecnico Microsoft per il caso.
