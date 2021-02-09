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
ms.openlocfilehash: 87a5780bd2485ba6ad3b295c09a30a4d7fc34277
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150561"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="8d8e1-103">Mappa del flusso di posta nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="8d8e1-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8d8e1-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="8d8e1-104">**Applies to**</span></span>
- [<span data-ttu-id="8d8e1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8d8e1-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="8d8e1-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="8d8e1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="8d8e1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d8e1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="8d8e1-108">La **mappa del flusso di posta** nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità fornisce informazioni dettagliate sul flusso di posta nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8d8e1-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="8d8e1-109">Puoi usare queste informazioni per imparare modelli, identificare anomalie e risolvere i problemi non appena si verificano.</span><span class="sxs-lookup"><span data-stu-id="8d8e1-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget Mappa flusso di posta nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="8d8e1-111">Per impostazione predefinita, il widget mostra il modello del flusso di posta del giorno precedente in un grafico noto come *diagramma Sankey.*</span><span class="sxs-lookup"><span data-stu-id="8d8e1-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="8d8e1-112">È possibile utilizzare la freccia sinistra e la freccia destra per visualizzare ![ le informazioni di giorni ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) diversi.</span><span class="sxs-lookup"><span data-stu-id="8d8e1-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="8d8e1-113">Ogni colore diverso rappresenta il flusso di posta su un connettore in ingresso o in uscita diverso (o senza utilizzare connettori).</span><span class="sxs-lookup"><span data-stu-id="8d8e1-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="8d8e1-114">Se si passa il mouse su un colore specifico, viene visualizzato il numero di messaggi per quel tipo di connettore.</span><span class="sxs-lookup"><span data-stu-id="8d8e1-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="8d8e1-115">Visualizzazione report per la mappa del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="8d8e1-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="8d8e1-116">Facendo clic sul widget **Mappa flusso di** posta si visualizza il report Mappa flusso **di** posta.</span><span class="sxs-lookup"><span data-stu-id="8d8e1-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="8d8e1-117">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d8e1-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="8d8e1-118">**Mostra dati per: Panoramica:** si tratta fondamentalmente di una visualizzazione più ampia del widget.</span><span class="sxs-lookup"><span data-stu-id="8d8e1-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="8d8e1-119">Se si passa il mouse su un colore specifico, viene visualizzato il numero di messaggi per quel tipo di connettore.</span><span class="sxs-lookup"><span data-stu-id="8d8e1-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Visualizzazione Panoramica nel report Mappa flusso di posta](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="8d8e1-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span><span class="sxs-lookup"><span data-stu-id="8d8e1-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="8d8e1-122">I domini del mittente e del destinatario principali sono elencati e gli altri sono inseriti in **Altri.**</span><span class="sxs-lookup"><span data-stu-id="8d8e1-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="8d8e1-123">Se si passa il mouse su un colore e una sezione specifici, viene visualizzato il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="8d8e1-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Visualizzazione Dettagli nel report Mappa flusso di posta](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="8d8e1-125">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="8d8e1-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8d8e1-126">Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic **su Richiedi download.**</span><span class="sxs-lookup"><span data-stu-id="8d8e1-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="8d8e1-127">Le informazioni dettagliate correlate vengono visualizzate sotto la mappa del flusso di posta, se disponibili (ad esempio, le informazioni dettagliate sui possibili [cicli di posta).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="8d8e1-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="8d8e1-128">Visualizzazione della tabella dei dettagli per la mappa del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="8d8e1-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="8d8e1-129">Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d8e1-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="8d8e1-130">**Data**</span><span class="sxs-lookup"><span data-stu-id="8d8e1-130">**Date**</span></span>
- <span data-ttu-id="8d8e1-131">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="8d8e1-131">**Category**</span></span>
- <span data-ttu-id="8d8e1-132">**Connettore/provider di servizi di terze parti**</span><span class="sxs-lookup"><span data-stu-id="8d8e1-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="8d8e1-133">**Dominio mittente/destinatario**</span><span class="sxs-lookup"><span data-stu-id="8d8e1-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="8d8e1-134">**Numero messaggi**</span><span class="sxs-lookup"><span data-stu-id="8d8e1-134">**Message count**</span></span>

<span data-ttu-id="8d8e1-135">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="8d8e1-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8d8e1-136">Se si seleziona una riga, dettagli simili vengono visualizzati in un riquadro a comparsa:</span><span class="sxs-lookup"><span data-stu-id="8d8e1-136">If you select a row, similar details are shown in a flyout:</span></span>

![Riquadro a comparsa Dettagli dalla tabella dei dettagli nella mappa del flusso di posta](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="8d8e1-138">Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic **su Richiedi download.**</span><span class="sxs-lookup"><span data-stu-id="8d8e1-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="8d8e1-139">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="8d8e1-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d8e1-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d8e1-140">See also</span></span>

<span data-ttu-id="8d8e1-141">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="8d8e1-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
