---
title: Rilevare regole per la riduzione della superficie di attacco
description: Scopri come la riduzione della superficie di attacco potrebbe bloccare e impedire gli attacchi con lo strumento demo personalizzato.
keywords: Riduzione della superficie di attacco, fianchi, sistema di prevenzione delle intrusioni host, regole di protezione, anti-exploit, antiexploit, exploit, prevenzione delle infezioni, valutare, testare, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 07573fd92643ce5fdf3e9140031bf5f15ae8f7aa
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570340"
---
# <a name="evaluate-attack-surface-reduction-rules"></a>Rilevare regole per la riduzione della superficie di attacco

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Le regole di riduzione della superficie di attacco consentono di impedire le azioni in genere utilizzate dal malware per compromettere dispositivi o reti. Imposta le regole di riduzione della superficie di attacco per i dispositivi che eseguono una delle seguenti edizioni e versioni di Windows:

- Windows 10 Pro, [versione 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o successiva
- Windows 10 Enterprise, [versione 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o successiva
- Windows Server, [versione 1803 (Canale semestraale)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) o versione successiva
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Scopri come valutare le regole di riduzione della superficie di attacco abilitando la modalità di controllo per testare la funzionalità direttamente nell'organizzazione.

> [!TIP]
> Puoi anche visitare il sito Web dello scenario demo di Microsoft Defender per Endpoint [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che la funzionalità funzioni e vedere come funziona.

## <a name="use-audit-mode-to-measure-impact"></a>Usare la modalità di controllo per misurare l'impatto

Abilita le regole di riduzione della superficie di attacco in modalità di controllo per visualizzare un record di app che sarebbero state bloccate se la funzionalità fosse stata completamente abilitata. Testare il funzionamento della funzionalità nell'organizzazione per assicurarsi che non influisca sulle app line-of-business. È inoltre possibile avere un'idea della frequenza di esecuzione delle regole durante il normale utilizzo.

Per abilitare una regola di riduzione della superficie di attacco in modalità di controllo, utilizzare il cmdlet PowerShell seguente:

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

Dove è un valore GUID della regola di riduzione della superficie `<rule ID>` [di attacco.](attack-surface-reduction.md#attack-surface-reduction-rules)

Per abilitare tutte le regole di riduzione della superficie di attacco aggiunte in modalità di controllo, utilizzare il cmdlet PowerShell seguente:

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> Se si desidera controllare completamente il funzionamento delle regole di riduzione della superficie di attacco nell'organizzazione, è necessario utilizzare uno strumento di gestione per distribuire questa impostazione nei dispositivi della rete.

Puoi anche usare Criteri di gruppo, Intune o provider di servizi di configurazione (CSP) per la gestione dei dispositivi mobili (MDM) per configurare e distribuire l'impostazione. Per ulteriori informazioni, vedere [l'articolo principale Sulle regole di riduzione della superficie di](attack-surface-reduction.md) attacco.

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Esaminare gli eventi di riduzione della superficie di attacco nel Visualizzatore eventi di Windows

Per esaminare le app che sarebbero state bloccate, aprire il Visualizzatore eventi e filtrare l'ID evento 1121 nel registro microsoft-Windows-Windows Defender/operativo. Nella tabella seguente sono elencati tutti gli eventi di protezione di rete.

ID evento | Descrizione
-|-
 5007 | Evento quando vengono modificate le impostazioni
 1121 | Evento quando viene attivata una regola di riduzione della superficie di attacco in modalità blocco
 1122 | Evento quando una regola di riduzione della superficie di attacco viene attivata in modalità di controllo

## <a name="customize-attack-surface-reduction-rules"></a>Personalizzare regole per la riduzione della superficie di attacco

Durante la valutazione, è possibile configurare ogni regola singolarmente o escludere determinati file e processi dalla valutazione da parte della funzionalità.

Vedi [Personalizzare le regole di riduzione della superficie](customize-attack-surface-reduction.md) di attacco per informazioni sulla configurazione della funzionalità con strumenti di gestione, inclusi Criteri di gruppo e criteri CSP MDM.

## <a name="see-also"></a>Vedere anche

* [Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco](attack-surface-reduction.md)
* [Usare la modalità di controllo per valutare Windows Defender](audit-windows-defender.md)
* [FAQ per la riduzione della superficie d'attacco](attack-surface-reduction.md)
