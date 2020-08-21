---
title: Mappa del flusso di posta
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare la mappa del flusso di posta nel dashboard del flusso di posta elettronica nel centro sicurezza & conformità per visualizzare e monitorare la modalità di flusso di posta da e verso la propria organizzazione su connettori e senza l'utilizzo di connettori.
ms.openlocfilehash: d27513b905a2b6c1a7ae366040e9e29b2d67b258
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827002"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Mappa del flusso di posta elettronica nel centro sicurezza & Compliance

La **mappa del flusso** di posta nel [Dashboard del flusso di posta](mail-flow-insights-v2.md) elettronica nel centro sicurezza & conformità fornisce informazioni su come scorre la posta attraverso la propria organizzazione. È possibile utilizzare queste informazioni per apprendere modelli, identificare anomalie e correggere i problemi che si verificano.

![Widget mappa del flusso di posta elettronica nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../../media/mfi-mail-flow-map-widget.png)

Per impostazione predefinita, il widget Visualizza il modello del flusso di posta del giorno precedente in un grafico conosciuto come diagramma di *Sankey* . È possibile utilizzare il freccia sinistra freccia sinistra e freccia destra ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) per visualizzare le informazioni di giorni diversi. Ogni colore diverso rappresenta il flusso di posta su un connettore in ingresso o in uscita diverso (o senza l'utilizzo di connettori). Se si posiziona il puntatore del mouse su un colore specifico, il numero di messaggi viene visualizzato per il tipo di connettore.

## <a name="report-view-for-the-mail-flow-map"></a>Visualizzazione report per la mappa del flusso di posta

Se si fa clic sul widget **mappa del flusso di posta elettronica** , verrà eseguito il rapporto **mappa del flusso di posta** .

Nella visualizzazione report sono disponibili i grafici seguenti:

- Mostra **dati per: Panoramica**: è fondamentalmente una visualizzazione ingrandita del widget. Se si posiziona il puntatore del mouse su un colore specifico, il numero di messaggi viene visualizzato per il tipo di connettore.

  ![Visualizzazione panoramica nel rapporto Mappa del flusso di posta](../../media/mfi-mail-flow-map-report-overview.png)

- Mostra **dati per: dettaglio**: questa visualizzazione contiene informazioni dettagliate sui connettori e sui domini di destinazione. I domini principale del mittente e del destinatario sono elencati e gli altri vengono inseriti in **altri**. Se si posiziona il puntatore del mouse su un colore e una sezione specifici, viene visualizzato il numero di messaggi.

  ![Visualizzazione dettagli nel rapporto Mappa flusso di posta](../../media/mfi-mail-flow-map-report-detail.png)

Se si fa clic su **filtri** in una visualizzazione report, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.

Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic su **Richiedi download**.

Le informazioni correlate vengono visualizzate sotto la mappa del flusso di posta, se disponibili, ad esempio l' [Insight del ciclo di posta possibile](mfi-mail-loop-insight.md).

## <a name="details-table-view-for-the-mail-flow-map"></a>Visualizzazione della tabella dei dettagli per la mappa del flusso di posta

Se si fa clic su **Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:

- **Data**
- **Categoria**
- **Connettore/provider di servizi di terze parti**
- **Dominio mittente/destinatario**
- **Numero di messaggi**

Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.

Se si seleziona una riga, i dettagli simili vengono visualizzati in un riquadro a comparsa:

![Riquadro a comparsa dettagli dalla tabella Details della mappa del flusso di posta](../../media/mfi-mail-flow-map-view-details-table-details.png)

Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic su **Richiedi download**.

Per tornare alla visualizzazione report, fare clic su **Visualizza report**.

## <a name="see-also"></a>Vedere anche

Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
