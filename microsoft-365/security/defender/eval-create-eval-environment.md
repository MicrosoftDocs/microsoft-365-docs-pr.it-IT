---
title: Creare l'Microsoft 365 Defender di valutazione. Attivare o abilitare le licenze di valutazione e passare a Microsoft Defender for Identity (MDI).
description: Configurare il laboratorio di Microsoft 365 Defender o l'ambiente pilota attivando le licenze di valutazione. Configura quindi Microsoft Defender for Identity (MDI) e tutte le altre valutazioni M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/19/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 04f7a746788ebcf67525020515cdc7bb20c41bb6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458268"
---
# <a name="create-the-microsoft-365-defender-evaluation-environment"></a>Creare l'Microsoft 365 Defender di valutazione

Esistono due modi comuni per eseguire questo passaggio successivo nella valutazione. Questo documento presuppone che tu abbia già un tenant M365 di produzione e attiverà le licenze di valutazione E5 per valutare M365 Defender *nell'ambiente corrente.* Una valutazione sul posto consente di mantenere tutti i metodi di sicurezza con l'acquisto di licenze dopo il periodo di valutazione.

Il secondo è configurare [l'ambiente Microsoft 365 Defender lab](setup-m365deval.md) di valutazione ai fini della valutazione. Potrebbe non avere molti segnali reali dall'azienda, quindi tenere presente tale avvertenza.

## <a name="to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a>Per attivare le licenze di valutazione di E5 per valutare Microsoft 365 Defender 
1. Accedere al portale di amministrazione tenant M365 esistente.
2. Seleziona *Acquista servizi* dal menu di spostamento.
3. Scorri verso il basso *fino alla Office 365* e seleziona il pulsante "Dettagli" sotto Office 365 E5 licenza.

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="La Office 365 contiene un pulsante Dettagli su cui fare clic.":::

4. Seleziona *Avvia il collegamento per la versione di valutazione* gratuita.

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Fai clic su &quot;Avvia versione di valutazione gratuita&quot; (è disponibile una tariffa di 35$).":::

5. Conferma la richiesta e fai clic *sul pulsante Prova.*

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="C'è un pulsante &quot;Prova ora&quot; nel pannello &quot;Estrai, conferma l'ordine&quot; (per una versione di valutazione di Office 365 E5 di un mese per 25 utenti).":::

## <a name="next-steps"></a>Passaggi successivi
[Abilitare Microsoft 365 per l'identità](eval-defender-identity-overview.md)

Tornare alla panoramica per [valutare e valutare Microsoft 365 Defender](eval-overview.md)