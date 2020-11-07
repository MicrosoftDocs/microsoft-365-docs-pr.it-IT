---
title: Acquisire informazioni dettagliate tramite la formazione sulla simulazione di attacco
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Informazioni su come l'addestramento all'attacco di simulazione in Microsoft 365 Security Center ha effetto sui dipendenti e sul guadagno dei risultati di simulazione e formazione.
ms.openlocfilehash: 180ddc773b5a299692e40ddc558d3b3a89f4093b
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944469"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Acquisire informazioni dettagliate tramite la formazione sulla simulazione di attacco

All'interno della formazione sulla simulazione degli attacchi, Microsoft fornisce informazioni basate sui risultati di simulazioni e i dipendenti della formazione hanno attraversato. Queste informazioni consentiranno di informarti sul progresso che i dipendenti stanno facendo sulla preparazione delle minacce, nonché di consigliare i passaggi successivi per preparare meglio i dipendenti e l'ambiente per gli attacchi.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Stiamo lavorando continuamente su come espandere approfondimenti disponibili, con un impatto comportamentale e le azioni consigliate attualmente disponibili.
Per iniziare, passare a [Attack Simulation Training on the Microsoft 365 Security Center](https://security.microsoft.com/attacksimulator?viewid=overview).

## <a name="behavior-impact-on-compromise-rate"></a>Impatto del comportamento sulla velocità di compromesso

Nella scheda **Panoramica** sulla formazione di attacchi di simulazione, è possibile trovare l' **impatto sul comportamento sulla scheda velocità di compromesso** . Questa scheda illustra come i dipendenti hanno affrontato la simulazione che è stata eseguita in contrasto con il **tasso di compromesso previsto**. È possibile utilizzare queste informazioni per monitorare lo stato di avanzamento della preparazione delle minacce dei dipendenti eseguendo più simulazioni sugli stessi gruppi di dipendenti.

Nel grafico è possibile vedere:

- **Tasso di compromesso previsto** che riflette il tasso medio di compromesso per le simulazioni usando lo stesso tipo di payload tra i tenant usando la formazione sulla simulazione degli attacchi.
- Il **tasso di compromesso effettivo** riflette la percentuale di dipendenti che sono caduti per la simulazione.

Inoltre, `<number> less susceptible to phishing` riflette la differenza tra il numero effettivo di dipendenti compromessi dall'attacco e il tasso di compromesso previsto. Questo numero di dipendenti ha meno probabilità di essere compromesso da attacchi simili in futuro, mentre `<percent%> better than predicted rate` indica la modalità complessiva dei dipendenti in contrasto con il tasso di compromesso previsto.

![Scheda impatto sulla simulazione dell'addestramento di attacco](../../media/attack-sim-preview-behavior-impact-card.png)

Per visualizzare un report più dettagliato, fare clic su **Visualizza simulazioni e report sull'efficacia della formazione** che fornisce le stesse informazioni con un contesto aggiuntivo dalla simulazione stessa, come la tecnica di simulazione e gli utenti totali mirati.

## <a name="recommended-actions"></a>Azioni consigliate

Nella scheda [ **simulazioni**](https://security.microsoft.com/attacksimulator?viewid=simulations) , selezionando una qualsiasi delle simulazioni, verranno illustrati i dettagli della simulazione. Qui è disponibile la sezione **azioni consigliate** .

La sezione azioni consigliate descrive in dettaglio i suggerimenti disponibili in [Microsoft Secure Score](../mtp/microsoft-secure-score.md). Questi suggerimenti si basano sul payload utilizzato nella simulazione e consentono di proteggere i dipendenti e il proprio ambiente. Facendo clic su ogni azione di miglioramento, vengono illustrati i dettagli.

![Sezione azioni consigliate sulla formazione sulla simulazione di attacco](../../media/attack-sim-preview-recommended-actions.png)