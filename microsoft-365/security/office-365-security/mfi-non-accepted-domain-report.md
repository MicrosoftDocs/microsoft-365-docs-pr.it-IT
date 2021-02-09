---
title: Rapporto dominio non accettato nel dashboard del flusso di posta
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
description: Gli amministratori possono imparare a usare il report dominio non accettato nel dashboard del flusso di posta nel Centro sicurezza & conformità per monitorare i messaggi dall'organizzazione locale in cui il dominio del mittente non è configurato in Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 573fb0ba2bf7981b6eb7df4eec7c8c4e5d596cac
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150821"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="dc308-103">Report dominio non accettato nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="dc308-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dc308-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="dc308-104">**Applies to**</span></span>
- [<span data-ttu-id="dc308-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dc308-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="dc308-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="dc308-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="dc308-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc308-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="dc308-108">Il **report** Dominio non accettato nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità visualizza informazioni sui messaggi provenienti dall'organizzazione di posta elettronica locale in cui il dominio del mittente non è configurato come dominio accettato nell'organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc308-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="dc308-109">Microsoft 365 potrebbe limitazione di questi messaggi se si dispone di dati per dimostrare che l'intento di questi messaggi è dannoso.</span><span class="sxs-lookup"><span data-stu-id="dc308-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="dc308-110">Pertanto, è importante comprendere cosa sta succedendo e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="dc308-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Widget Dominio non accettato nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="dc308-112">Visualizzazione report per il rapporto dominio non accettato</span><span class="sxs-lookup"><span data-stu-id="dc308-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="dc308-113">Se si fa clic sul grafico **nel** widget Dominio non accettato, verrà visualizzato il report **Dominio non** accettato.</span><span class="sxs-lookup"><span data-stu-id="dc308-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="dc308-114">Per impostazione predefinita, viene visualizzata l'attività per tutti i connettori interessati.</span><span class="sxs-lookup"><span data-stu-id="dc308-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="dc308-115">Se si fa **clic su Mostra dati per**, è possibile selezionare un connettore specifico nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="dc308-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="dc308-116">Se si passa il mouse su un punto dati (giorno) nel grafico, viene visualizzato il numero totale di messaggi per il connettore.</span><span class="sxs-lookup"><span data-stu-id="dc308-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Visualizzazione report nel rapporto dominio non accettato](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="dc308-118">Visualizzazione della tabella dei dettagli per il report dominio non accettato</span><span class="sxs-lookup"><span data-stu-id="dc308-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="dc308-119">Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc308-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="dc308-120">**Data**</span><span class="sxs-lookup"><span data-stu-id="dc308-120">**Date**</span></span>
- <span data-ttu-id="dc308-121">**Nome connettore in ingresso**</span><span class="sxs-lookup"><span data-stu-id="dc308-121">**Inbound connector name**</span></span>
- <span data-ttu-id="dc308-122">**Dominio del mittente**</span><span class="sxs-lookup"><span data-stu-id="dc308-122">**Sender domain**</span></span>
- <span data-ttu-id="dc308-123">**Numero messaggi**</span><span class="sxs-lookup"><span data-stu-id="dc308-123">**Message count**</span></span>
- <span data-ttu-id="dc308-124">**Messaggi di esempio**: ID messaggio di un campione di messaggi interessati.</span><span class="sxs-lookup"><span data-stu-id="dc308-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="dc308-125">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="dc308-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="dc308-126">Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic **su Richiedi download.**</span><span class="sxs-lookup"><span data-stu-id="dc308-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="dc308-127">Quando si seleziona una riga nella tabella, viene visualizzato un riquadro a comparsa con le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dc308-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="dc308-128">**Data**</span><span class="sxs-lookup"><span data-stu-id="dc308-128">**Date**</span></span>
- <span data-ttu-id="dc308-129">**Nome connettore in ingresso**</span><span class="sxs-lookup"><span data-stu-id="dc308-129">**Inbound connector name**</span></span>
- <span data-ttu-id="dc308-130">**Dominio del mittente**</span><span class="sxs-lookup"><span data-stu-id="dc308-130">**Sender domain**</span></span>
- <span data-ttu-id="dc308-131">**Numero messaggi**</span><span class="sxs-lookup"><span data-stu-id="dc308-131">**Message count**</span></span>
- <span data-ttu-id="dc308-132">**Messaggi di esempio:** è possibile fare clic **su Visualizza** messaggi di esempio per visualizzare i risultati [della](message-trace-scc.md) traccia dei messaggi per un campione dei messaggi interessati.</span><span class="sxs-lookup"><span data-stu-id="dc308-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Riquadro a comparsa Dettagli dopo aver selezionato una riga nella visualizzazione Tabella dettagli nel report Dominio non accettato](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="dc308-134">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="dc308-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dc308-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="dc308-135">Related topics</span></span>

<span data-ttu-id="dc308-136">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="dc308-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
