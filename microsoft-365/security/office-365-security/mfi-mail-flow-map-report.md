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
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="fd689-103">Mappa del flusso di posta nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="fd689-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fd689-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="fd689-104">**Applies to**</span></span>
- [<span data-ttu-id="fd689-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fd689-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fd689-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="fd689-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="fd689-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd689-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="fd689-108">La **mappa del flusso di posta** nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità fornisce informazioni dettagliate sul flusso di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fd689-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="fd689-109">È possibile utilizzare queste informazioni per apprendere modelli, identificare anomalie e risolvere i problemi man quando si verificano.</span><span class="sxs-lookup"><span data-stu-id="fd689-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget mappa del flusso di posta nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="fd689-111">Per impostazione predefinita, il widget mostra il modello del flusso di posta del giorno precedente in un grafico noto come *diagramma Sankey.*</span><span class="sxs-lookup"><span data-stu-id="fd689-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="fd689-112">È possibile utilizzare la freccia sinistra freccia sinistra e la freccia ![ destra freccia destra per visualizzare informazioni di giorni ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) diversi.</span><span class="sxs-lookup"><span data-stu-id="fd689-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="fd689-113">Ogni colore diverso rappresenta il flusso di posta su un connettore in ingresso o in uscita diverso (o senza utilizzare connettori).</span><span class="sxs-lookup"><span data-stu-id="fd689-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="fd689-114">Se si passa il mouse su un colore specifico, viene visualizzato il numero di messaggi per quel tipo di connettore.</span><span class="sxs-lookup"><span data-stu-id="fd689-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="fd689-115">Visualizzazione report per la mappa del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="fd689-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="fd689-116">Facendo clic sul widget **Mappa flusso di** posta, si visualizza il report Mappa flusso **di** posta.</span><span class="sxs-lookup"><span data-stu-id="fd689-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="fd689-117">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd689-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="fd689-118">**Mostra dati per: Panoramica**: si tratta fondamentalmente di una visualizzazione più ampia del widget.</span><span class="sxs-lookup"><span data-stu-id="fd689-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="fd689-119">Se si passa il mouse su un colore specifico, viene visualizzato il numero di messaggi per quel tipo di connettore.</span><span class="sxs-lookup"><span data-stu-id="fd689-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Visualizzazione panoramica nel report Mappa flusso di posta](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="fd689-121">**Mostra dati per: Dettagli**: questa visualizzazione mostra i dettagli sui connettori e sui domini di destinazione.</span><span class="sxs-lookup"><span data-stu-id="fd689-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="fd689-122">I domini del mittente e del destinatario principali sono elencati e gli altri sono inseriti in **Altri**.</span><span class="sxs-lookup"><span data-stu-id="fd689-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="fd689-123">Se si passa il mouse su un colore e una sezione specifici, viene visualizzato il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="fd689-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Visualizzazione dettagli nel report Mappa flusso di posta](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="fd689-125">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="fd689-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fd689-126">Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic **su Richiedi download.**</span><span class="sxs-lookup"><span data-stu-id="fd689-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="fd689-127">Le informazioni dettagliate correlate vengono visualizzate sotto la mappa del flusso di posta, se disponibili(ad esempio, la correzione delle possibili informazioni dettagliate [sul ciclo di posta).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="fd689-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="fd689-128">Visualizzazione tabella dettagli per la mappa del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="fd689-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="fd689-129">Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd689-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="fd689-130">**Data**</span><span class="sxs-lookup"><span data-stu-id="fd689-130">**Date**</span></span>
- <span data-ttu-id="fd689-131">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="fd689-131">**Category**</span></span>
- <span data-ttu-id="fd689-132">**Connettore/provider di servizi di terze parti**</span><span class="sxs-lookup"><span data-stu-id="fd689-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="fd689-133">**Dominio mittente/destinatario**</span><span class="sxs-lookup"><span data-stu-id="fd689-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="fd689-134">**Conteggio messaggi**</span><span class="sxs-lookup"><span data-stu-id="fd689-134">**Message count**</span></span>

<span data-ttu-id="fd689-135">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="fd689-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fd689-136">Se si seleziona una riga, dettagli simili vengono visualizzati in un riquadro a comparsa:</span><span class="sxs-lookup"><span data-stu-id="fd689-136">If you select a row, similar details are shown in a flyout:</span></span>

![Riquadro a comparsa Dettagli dalla tabella dei dettagli nella mappa del flusso di posta](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="fd689-138">Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic **su Richiedi download.**</span><span class="sxs-lookup"><span data-stu-id="fd689-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="fd689-139">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="fd689-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd689-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd689-140">See also</span></span>

<span data-ttu-id="fd689-141">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="fd689-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
