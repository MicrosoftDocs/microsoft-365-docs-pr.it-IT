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
description: Gli amministratori possono scoprire in che modo la formazione sulla simulazione di attacchi nel portale di Microsoft 365 Defender influisce sui dipendenti e può ottenere informazioni dettagliate dai risultati della simulazione e della formazione.
ms.technology: mdo
ms.openlocfilehash: e189864a42d025bb5ce720a6edb6c1c2c8c84623
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878377"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Acquisire informazioni approfondite attraverso la formazione del Simulatore di attacchi

**Si applica a** [Microsoft Defender per Office 365 piano 2](defender-for-office-365.md)

Nell'ambito della formazione sulla simulazione di attacchi, Microsoft fornisce informazioni dettagliate basate sui risultati delle simulazioni e dei corsi di formazione che i dipendenti hanno seguito. Queste informazioni dettagliate consentono di tenere informati sull'avanzamento della preparazione alle minacce dei dipendenti, nonché di consigliare i passaggi successivi per preparare meglio i dipendenti e l'ambiente per gli attacchi.

Stiamo continuamente lavorando per espandere le informazioni dettagliate disponibili. L'impatto sul comportamento e le azioni consigliate sono attualmente disponibili. Per iniziare, vai al training di simulazione degli [attacchi nel portale Microsoft 365 Defender.](https://security.microsoft.com/attacksimulator?viewid=overview)

## <a name="behavior-impact-on-compromise-rate"></a>Impatto del comportamento sulla frequenza di compromissione

Nella scheda **Panoramica del** training di simulazione degli attacchi, è possibile trovare l'impatto sul comportamento sulla scheda tasso **di compromissione.** Questa scheda mostra come i dipendenti hanno gestito le simulazioni che hai eseguito in contrasto con il **tasso di compromissione previsto.** È possibile usare queste informazioni dettagliate per tenere traccia dello stato di avanzamento della preparazione alle minacce dei dipendenti eseguendo più simulazioni con gli stessi gruppi di dipendenti.

Nel grafico è possibile visualizzare:

- **Tasso di compromissione previsto** che riflette la percentuale media di compromissione per le simulazioni che usano lo stesso tipo di payload in altri tenant di Microsoft 365 che usano la formazione di simulazione di attacco.
- **Il tasso di compromissione** effettivo riflette la percentuale di dipendenti che sono diminuiti per la simulazione.

Riflette inoltre la differenza tra il numero effettivo di dipendenti compromessi dall'attacco e il `<number> less susceptible to phishing` tasso di compromissione previsto. Questo numero di dipendenti è meno probabile che venga compromesso da attacchi simili in futuro, mentre indica come i dipendenti hanno fatto complessivamente in contrasto con il tasso di compromissione `<percent%> better than predicted rate` previsto.

> [!div class="mx-imgBorder"]
> ![Panoramica del training della scheda impatto sul comportamento nella simulazione di attacco](../../media/attack-sim-preview-behavior-impact-card.png)

Per visualizzare un report più dettagliato, fare clic su Visualizza simulazioni **e report sull'efficacia della formazione.** Questo report fornisce le stesse informazioni con un contesto aggiuntivo dalla simulazione stessa (ad esempio, la tecnica di simulazione e il totale degli utenti mirati).

## <a name="recommended-actions"></a>Azioni consigliate

Nella scheda [ **Simulazioni** selezionare](https://security.microsoft.com/attacksimulator?viewid=simulations)una simulazione per visualizzare i dettagli della simulazione, dove è presente la **sezione Azioni consigliate.**

Nella sezione azioni consigliate vengono fornite informazioni dettagliate sui suggerimenti disponibili in [Microsoft Secure Score.](../defender/microsoft-secure-score.md) Questi suggerimenti si basano sul payload usato nella simulazione e consentono di proteggere i dipendenti e l'ambiente. Facendo clic su ogni azione di miglioramento, verranno fornite informazioni dettagliate.

> [!div class="mx-imgBorder"]
> ![Sezione Azioni consigliate sul training di simulazione degli attacchi](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Collegamenti correlati

[Introduzione alla formazione sull’uso di Simulatore di attacchi](attack-simulation-training-get-started.md)

[Creare una simulazione di attacco di phishing](attack-simulation-training.md)

[creare un payload per la formazione delle persone](attack-simulation-training-payloads.md)
