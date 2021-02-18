---
title: Mappa del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare la mappa del flusso di posta nel dashboard del flusso di posta nel Centro sicurezza & conformità per visualizzare e tenere traccia del flusso di posta da e verso l'organizzazione sui connettori e senza utilizzare i connettori.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2f507f7f01999492d17e168a2a56da906bfcb52d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290586"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Mappa del flusso di posta nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

La **mappa del flusso di posta** nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità fornisce informazioni dettagliate sul flusso di posta nell'organizzazione. Puoi usare queste informazioni per imparare modelli, identificare anomalie e risolvere i problemi non appena si verificano.

![Widget Mappa flusso di posta nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-mail-flow-map-widget.png)

Per impostazione predefinita, il widget mostra il modello del flusso di posta del giorno precedente in un grafico noto come *diagramma Sankey.* È possibile utilizzare la freccia sinistra e la freccia destra per visualizzare ![ le informazioni di giorni ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) diversi. Ogni colore diverso rappresenta il flusso di posta su un connettore in ingresso o in uscita diverso (o senza utilizzare connettori). Se si passa il mouse su un colore specifico, viene visualizzato il numero di messaggi per quel tipo di connettore.

## <a name="report-view-for-the-mail-flow-map"></a>Visualizzazione report per la mappa del flusso di posta

Facendo clic sul widget **Mappa flusso di** posta si visualizza il report Mappa flusso **di** posta.

Nella visualizzazione report sono disponibili i grafici seguenti:

- **Mostra dati per: Panoramica:** si tratta fondamentalmente di una visualizzazione più ampia del widget. Se si passa il mouse su un colore specifico, viene visualizzato il numero di messaggi per quel tipo di connettore.

  ![Visualizzazione Panoramica nel report Mappa flusso di posta](../../media/mfi-mail-flow-map-report-overview.png)

- **Show data for: Detail**: This view shows details about the connectors and destination domains. I domini del mittente e del destinatario principali sono elencati e gli altri sono inseriti in **Altri.** Se si passa il mouse su un colore e una sezione specifici, viene visualizzato il numero di messaggi.

  ![Visualizzazione Dettagli nel report Mappa flusso di posta](../../media/mfi-mail-flow-map-report-detail.png)

Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**

Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic **su Richiedi download.**

Le informazioni dettagliate correlate vengono visualizzate sotto la mappa del flusso di posta, se disponibili (ad esempio, le informazioni dettagliate sui possibili [cicli di posta).](mfi-mail-loop-insight.md)

## <a name="details-table-view-for-the-mail-flow-map"></a>Visualizzazione della tabella dei dettagli per la mappa del flusso di posta

Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:

- **Data**
- **Categoria**
- **Connettore/provider di servizi di terze parti**
- **Dominio mittente/destinatario**
- **Numero messaggi**

Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**

Se si seleziona una riga, dettagli simili vengono visualizzati in un riquadro a comparsa:

![Riquadro a comparsa Dettagli dalla tabella dei dettagli nella mappa del flusso di posta](../../media/mfi-mail-flow-map-view-details-table-details.png)

Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic **su Richiedi download.**

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="see-also"></a>Vedere anche

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)
