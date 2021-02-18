---
title: Acquisire informazioni approfondite attraverso la formazione del Simulatore di attacchi
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gli amministratori possono scoprire in che modo la formazione sulla simulazione degli attacchi nel Centro sicurezza Microsoft 365 influisce sui dipendenti e può ottenere informazioni dettagliate dai risultati della simulazione e della formazione.
ms.technology: mdo
ms.openlocfilehash: 43319089f604d32bf295392dd223cf65af8bd4be
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288658"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Acquisire informazioni approfondite attraverso la formazione del Simulatore di attacchi

Nell'ambito della formazione sulla simulazione degli attacchi, Microsoft fornisce informazioni dettagliate basate sui risultati delle simulazioni e dei corsi di formazione che i dipendenti hanno seguito. Queste informazioni aiutano a tenerti informati sullo stato di preparazione alle minacce dei dipendenti, nonché a consigliare i passaggi successivi per preparare meglio i dipendenti e l'ambiente agli attacchi.

We are continuously working on expanding the insights that are available to you. L'impatto sul comportamento e le azioni consigliate sono attualmente disponibili. Per iniziare, andare alla formazione sulla simulazione degli attacchi nel Centro sicurezza [Microsoft 365.](https://security.microsoft.com/attacksimulator?viewid=overview)

## <a name="behavior-impact-on-compromise-rate"></a>Impatto del comportamento sulla frequenza di compromissione

Nella scheda **Panoramica della** formazione sulla simulazione degli attacchi, è possibile trovare l'impatto sul comportamento sulla scheda **della frequenza di compromissione.** Questa scheda mostra come i dipendenti hanno gestito le simulazioni che hai eseguito in contrasto con il **tasso di compromissione previsto.** È possibile usare queste informazioni dettagliate per tenere traccia dello stato di avanzamento nella preparazione delle minacce dei dipendenti eseguendo più simulazioni per gli stessi gruppi di dipendenti.

Nel grafico è possibile vedere:

- **Tasso di compromissione previsto** che riflette la percentuale media di compromissione per le simulazioni che usano lo stesso tipo di payload in altri tenant di Microsoft 365 che usano la formazione per la simulazione degli attacchi.
- **Il tasso di compromissione** effettivo riflette la percentuale di dipendenti che sono ersi per la simulazione.

Riflette inoltre la differenza tra il numero effettivo di dipendenti compromessi dall'attacco e il `<number> less susceptible to phishing` tasso di compromissione previsto. Questo numero di dipendenti è meno probabile che venga compromesso da attacchi simili in futuro, mentre indica come i dipendenti hanno fatto nel complesso in contrasto con il tasso di `<percent%> better than predicted rate` compromissione previsto.

> [!div class="mx-imgBorder"]
> ![Panoramica della scheda impatto sul comportamento nella formazione sulla simulazione degli attacchi](../../media/attack-sim-preview-behavior-impact-card.png)

Per visualizzare un report più dettagliato, fare clic su Visualizza simulazioni **e training.** Questo report fornisce le stesse informazioni con un contesto aggiuntivo dalla simulazione stessa (ad esempio, la tecnica di simulazione e il numero totale di utenti mirati).

## <a name="recommended-actions"></a>Azioni consigliate

Nella scheda [ **Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations)selezionare una simulazione per visualizzare i dettagli della simulazione, dove è presente la **sezione Azioni consigliate.**

Nella sezione azioni consigliate vengono fornite informazioni dettagliate sui suggerimenti disponibili in [Microsoft Secure Score.](../mtp/microsoft-secure-score.md) Questi consigli si basano sul payload usato nella simulazione e ti aiuteranno a proteggere i dipendenti e il tuo ambiente. Facendo clic su ogni azione di miglioramento, verranno fornite informazioni dettagliate.

> [!div class="mx-imgBorder"]
> ![Sezione Azioni consigliate sul training per la simulazione degli attacchi](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Collegamenti correlati

[Introduzione alla formazione sull’uso di Simulatore di attacchi](attack-simulation-training-get-started.md)

[Creare una simulazione di attacco di phishing](attack-simulation-training.md)

[creare un payload per la formazione delle persone](attack-simulation-training-payloads.md)
