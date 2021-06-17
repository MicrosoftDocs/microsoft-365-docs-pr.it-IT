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
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985097"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>Testare la riduzione della superficie di attacco in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Come parte del team di sicurezza dell'organizzazione, puoi configurare le funzionalità di riduzione della superficie di attacco per l'esecuzione in modalità di controllo per vedere come funzionano. In modalità di controllo puoi abilitare:

- Regole per la riduzione della superficie di attacco
- Protezione dagli exploit
- Protezione di rete
- E l'accesso controllato alle cartelle in modalità di controllo

La modalità di controllo consente di visualizzare un record di ciò *che* sarebbe successo se fosse stata abilitata la funzionalità.

Puoi abilitare la modalità di controllo durante il test del funzionamento delle funzionalità. In questo modo puoi assicurarti che le app line-of-business non siano interessate. Puoi anche avere un'idea del numero di tentativi sospetti di modifica dei file in un determinato periodo di tempo.

Le funzionalità non bloccano o impediscono la modifica di app, script o file. Tuttavia, il Windows eventi registra gli eventi come se le funzionalità fossero completamente abilitate. Con la modalità di controllo, è possibile esaminare il registro eventi per vedere quali effetti avrebbe avuto la funzionalità se fosse stata abilitata.

Per trovare le voci verificate, passare a **Applicazioni** e servizi  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operativo**.

Usa Defender for Endpoint per ottenere maggiori dettagli per ogni evento, in particolare per analizzare le regole di riduzione della superficie di attacco. L'uso della console defender per endpoint consente di analizzare i problemi nell'ambito della sequenza temporale degli avvisi e [degli scenari di indagine.](investigate-alerts.md)

Puoi abilitare la modalità di controllo usando Criteri di gruppo, PowerShell e provider di servizi di configurazione (CSP).

> [!TIP]
> È inoltre possibile visitare il sito Windows Defender Testground all'indirizzo [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) verificare che le funzionalità funzionino e vedere come funzionano.

| Opzioni di controllo | Come abilitare la modalità di controllo | Come visualizzare gli eventi |
|---------|---------|---------|
| Il controllo si applica a tutti gli eventi | [Abilitare l’accesso controllato alle cartelle](enable-controlled-folders.md) | [Eventi di accesso controllato alle cartelle](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| Il controllo si applica a singole regole | [Abilitare regole per la riduzione della superficie di attacco](enable-attack-surface-reduction.md) | [Eventi delle regole di riduzione della superficie di attacco](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| Il controllo si applica a tutti gli eventi | [Abilitare la protezione di rete](enable-network-protection.md) | [Eventi di protezione di rete](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| Il controllo si applica alle singole mitigazioni | [Abilitare la protezione dagli exploit](enable-exploit-protection.md) | [Eventi di protezione da exploit](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
