---
title: Mappa del flusso di posta
f1.keywords:
- NOCSH
ms.author: siosulli
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
ms.openlocfilehash: fc03f05db77c40dbf726692e6fb6069d587a5ffc
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877766"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="07d17-103">Mappa del flusso di posta elettronica nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="07d17-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="07d17-104">La **mappa del flusso** di posta nel [Dashboard del flusso di posta](mail-flow-insights-v2.md) elettronica nel [Centro sicurezza & conformità](https://protection.office.com) fornisce informazioni su come scorre la posta attraverso la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="07d17-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="07d17-105">È possibile utilizzare queste informazioni per apprendere modelli, identificare anomalie e correggere i problemi che si verificano.</span><span class="sxs-lookup"><span data-stu-id="07d17-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget mappa del flusso di posta elettronica nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="07d17-107">Per impostazione predefinita, il widget Visualizza il modello del flusso di posta del giorno precedente in un grafico conosciuto come diagramma di *Sankey* .</span><span class="sxs-lookup"><span data-stu-id="07d17-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="07d17-108">È possibile utilizzare il freccia sinistra freccia sinistra e freccia destra ![ ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) per visualizzare le informazioni di giorni diversi.</span><span class="sxs-lookup"><span data-stu-id="07d17-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="07d17-109">Ogni colore diverso rappresenta il flusso di posta su un connettore in ingresso o in uscita diverso (o senza l'utilizzo di connettori).</span><span class="sxs-lookup"><span data-stu-id="07d17-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="07d17-110">Se si posiziona il puntatore del mouse su un colore specifico, il numero di messaggi viene visualizzato per il tipo di connettore.</span><span class="sxs-lookup"><span data-stu-id="07d17-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="07d17-111">Visualizzazione report per la mappa del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="07d17-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="07d17-112">Se si fa clic sul widget **mappa del flusso di posta elettronica** , verrà eseguito il rapporto **mappa del flusso di posta** .</span><span class="sxs-lookup"><span data-stu-id="07d17-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="07d17-113">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="07d17-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="07d17-114">Mostra **dati per: Panoramica** : è fondamentalmente una visualizzazione ingrandita del widget.</span><span class="sxs-lookup"><span data-stu-id="07d17-114">**Show data for: Overview** : This is basically a larger view of the widget.</span></span> <span data-ttu-id="07d17-115">Se si posiziona il puntatore del mouse su un colore specifico, il numero di messaggi viene visualizzato per il tipo di connettore.</span><span class="sxs-lookup"><span data-stu-id="07d17-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Visualizzazione panoramica nel rapporto Mappa del flusso di posta](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="07d17-117">Mostra **dati per: dettaglio** : questa visualizzazione contiene informazioni dettagliate sui connettori e sui domini di destinazione.</span><span class="sxs-lookup"><span data-stu-id="07d17-117">**Show data for: Detail** : This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="07d17-118">I domini principale del mittente e del destinatario sono elencati e gli altri vengono inseriti in **altri**.</span><span class="sxs-lookup"><span data-stu-id="07d17-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="07d17-119">Se si posiziona il puntatore del mouse su un colore e una sezione specifici, viene visualizzato il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="07d17-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Visualizzazione dettagli nel rapporto Mappa flusso di posta](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="07d17-121">Se si fa clic su **filtri** in una visualizzazione report, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="07d17-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="07d17-122">Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic su **Richiedi download**.</span><span class="sxs-lookup"><span data-stu-id="07d17-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="07d17-123">Le informazioni correlate vengono visualizzate sotto la mappa del flusso di posta, se disponibili, ad esempio l' [Insight del ciclo di posta possibile](mfi-mail-loop-insight.md).</span><span class="sxs-lookup"><span data-stu-id="07d17-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="07d17-124">Visualizzazione della tabella dei dettagli per la mappa del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="07d17-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="07d17-125">Se si fa clic su **Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07d17-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="07d17-126">**Data**</span><span class="sxs-lookup"><span data-stu-id="07d17-126">**Date**</span></span>
- <span data-ttu-id="07d17-127">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="07d17-127">**Category**</span></span>
- <span data-ttu-id="07d17-128">**Connettore/provider di servizi di terze parti**</span><span class="sxs-lookup"><span data-stu-id="07d17-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="07d17-129">**Dominio mittente/destinatario**</span><span class="sxs-lookup"><span data-stu-id="07d17-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="07d17-130">**Numero di messaggi**</span><span class="sxs-lookup"><span data-stu-id="07d17-130">**Message count**</span></span>

<span data-ttu-id="07d17-131">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="07d17-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="07d17-132">Se si seleziona una riga, i dettagli simili vengono visualizzati in un riquadro a comparsa:</span><span class="sxs-lookup"><span data-stu-id="07d17-132">If you select a row, similar details are shown in a flyout:</span></span>

![Riquadro a comparsa dettagli dalla tabella Details della mappa del flusso di posta](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="07d17-134">Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic su **Richiedi download**.</span><span class="sxs-lookup"><span data-stu-id="07d17-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="07d17-135">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="07d17-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="07d17-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07d17-136">See also</span></span>

<span data-ttu-id="07d17-137">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="07d17-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
