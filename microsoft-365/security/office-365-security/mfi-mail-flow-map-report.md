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
description: Gli amministratori possono imparare a usare la mappa del flusso di posta nel dashboard del flusso di posta nel Centro sicurezza e conformità di & per visualizzare e tenere traccia del flusso di posta da e verso l'organizzazione tramite connettori e senza utilizzare connettori.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206962"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a>Mappa del flusso di posta nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

La **mappa del flusso di posta** nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità fornisce informazioni dettagliate sul flusso di posta nell'organizzazione. È possibile utilizzare queste informazioni per apprendere modelli, identificare anomalie e risolvere i problemi man quando si verificano.

![Widget mappa del flusso di posta nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-mail-flow-map-widget.png)

Per impostazione predefinita, il widget mostra il modello del flusso di posta del giorno precedente in un grafico noto come *diagramma Sankey.* È possibile utilizzare la freccia sinistra freccia sinistra e la freccia ![ destra freccia destra per visualizzare informazioni di giorni ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) diversi. Ogni colore diverso rappresenta il flusso di posta su un connettore in ingresso o in uscita diverso (o senza utilizzare connettori). Se si passa il mouse su un colore specifico, viene visualizzato il numero di messaggi per quel tipo di connettore.

## <a name="report-view-for-the-mail-flow-map"></a>Visualizzazione report per la mappa del flusso di posta

Facendo clic sul widget **Mappa flusso di** posta, si visualizza il report Mappa flusso **di** posta.

Nella visualizzazione report sono disponibili i grafici seguenti:

- **Mostra dati per: Panoramica**: si tratta fondamentalmente di una visualizzazione più ampia del widget. Se si passa il mouse su un colore specifico, viene visualizzato il numero di messaggi per quel tipo di connettore.

  ![Visualizzazione panoramica nel report Mappa flusso di posta](../../media/mfi-mail-flow-map-report-overview.png)

- **Mostra dati per: Dettagli**: questa visualizzazione mostra i dettagli sui connettori e sui domini di destinazione. I domini del mittente e del destinatario principali sono elencati e gli altri sono inseriti in **Altri**. Se si passa il mouse su un colore e una sezione specifici, viene visualizzato il numero di messaggi.

  ![Visualizzazione dettagli nel report Mappa flusso di posta](../../media/mfi-mail-flow-map-report-detail.png)

Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**

Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic **su Richiedi download.**

Le informazioni dettagliate correlate vengono visualizzate sotto la mappa del flusso di posta, se disponibili(ad esempio, la correzione delle possibili informazioni dettagliate [sul ciclo di posta).](mfi-mail-loop-insight.md)

## <a name="details-table-view-for-the-mail-flow-map"></a>Visualizzazione tabella dettagli per la mappa del flusso di posta

Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:

- **Data**
- **Categoria**
- **Connettore/provider di servizi di terze parti**
- **Dominio mittente/destinatario**
- **Conteggio messaggi**

Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**

Se si seleziona una riga, dettagli simili vengono visualizzati in un riquadro a comparsa:

![Riquadro a comparsa Dettagli dalla tabella dei dettagli nella mappa del flusso di posta](../../media/mfi-mail-flow-map-view-details-table-details.png)

Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic **su Richiedi download.**

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="see-also"></a>Vedere anche

Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)
