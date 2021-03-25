---
title: Verificare il funzionamento delle funzionalità di Microsoft Defender for Endpoint in modalità di controllo
description: La modalità di controllo ti aiuta a vedere in che modo Microsoft Defender for Endpoint proteggerebbe i dispositivi se fosse abilitato.
keywords: exploit guard, controllo, controllo, modalità, abilitato, disabilitato, test, demo, valutare, lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: dda0e58e587add2693f8448dd0833ce17706786c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067354"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a>Verificare il funzionamento delle funzionalità di Microsoft Defender for Endpoint in modalità di controllo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Puoi abilitare le regole di riduzione della superficie di attacco, la protezione degli exploit, la protezione di rete e l'accesso controllato alle cartelle in modalità di controllo. La modalità di controllo consente di visualizzare un record di ciò *che* sarebbe successo se fosse stata abilitata la funzionalità.

È possibile abilitare la modalità di controllo durante il test del funzionamento delle funzionalità nell'organizzazione. In questo modo puoi assicurarti che le app line-of-business non siano interessate. Puoi anche avere un'idea del numero di tentativi sospetti di modifica dei file in un determinato periodo di tempo.

Le funzionalità non bloccano o impediscono la modifica di app, script o file. Tuttavia, il registro eventi di Windows registrerà gli eventi come se le funzionalità fossero completamente abilitate. Con la modalità di controllo, è possibile esaminare il registro eventi per verificare l'impatto che la funzionalità avrebbe avuto se fosse stata abilitata.

Per trovare le voci controllate, passare a **Applicazioni e** servizi  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.

Puoi usare Defender for Endpoint per ottenere maggiori dettagli per ogni evento, in particolare per analizzare le regole di riduzione della superficie di attacco. L'uso della console defender per endpoint consente di analizzare i problemi nell'ambito della sequenza temporale degli avvisi e [degli scenari di indagine.](investigate-alerts.md)

È possibile usare Criteri di gruppo, PowerShell e provider di servizi di configurazione (CSP) per abilitare la modalità di controllo.

> [!TIP]
> Puoi anche visitare il sito Web Windows Defender Testground all'indirizzo [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) verificare che le funzionalità funzionino e vedere come funzionano.

 **Opzioni di controllo** | **Come abilitare la modalità di controllo** | **Come visualizzare gli eventi**
|---------|---------|---------|
| Il controllo si applica a tutti gli eventi | [Abilitare l'accesso controllato alle cartelle](enable-controlled-folders.md) | [Eventi di accesso controllato alle cartelle](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| Il controllo si applica a singole regole | [Abilitare le regole di riduzione della superficie di attacco](enable-attack-surface-reduction.md) | [Eventi delle regole di riduzione della superficie di attacco](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| Il controllo si applica a tutti gli eventi | [Abilitare la protezione di rete](enable-network-protection.md) | [Eventi di protezione di rete](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| Il controllo si applica alle singole mitigazioni | [Abilitare la protezione da exploit](enable-exploit-protection.md) | [Eventi di protezione da exploit](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a>Argomenti correlati

* [Proteggere i dispositivi dagli exploit](exploit-protection.md)
* [Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco](attack-surface-reduction.md)
* [Proteggere la rete](network-protection.md)
* [Proteggere le cartelle importanti](controlled-folders.md)
