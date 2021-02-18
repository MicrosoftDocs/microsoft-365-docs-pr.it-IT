---
title: Rapporto di mancato recapito nel dashboard del flusso di posta
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
description: Gli amministratori possono imparare a usare il report dettagli di mancato recapito nel dashboard del flusso di posta nel Centro sicurezza & conformità per monitorare i codici di errore riscontrati più di frequente nei rapporti di mancato recapito (noti anche come rapporti di mancato recapito o notifiche di mancato recapito) dai mittenti dell'organizzazione.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0e31e7dfcbd3c0cacaa6020464ed315f466a849b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287890"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="6fdb3-103">Rapporto di mancato recapito nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="6fdb3-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6fdb3-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="6fdb3-104">**Applies to**</span></span>
- [<span data-ttu-id="6fdb3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6fdb3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6fdb3-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="6fdb3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="6fdb3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6fdb3-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="6fdb3-108">Il **rapporto** di mancato recapito nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza [&](https://protection.office.com) conformità mostra i codici di errore più rilevati nei rapporti di mancato recapito (noti anche come rapporti di mancato recapito o notifiche di mancato recapito) per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6fdb3-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="6fdb3-109">Questo report mostra i dettagli dei rapporti di mancato recapito in modo da poter risolvere i problemi di recapito della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6fdb3-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget report di mancato recapito nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="6fdb3-111">Visualizzazione report per il rapporto di mancato recapito</span><span class="sxs-lookup"><span data-stu-id="6fdb3-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="6fdb3-112">Se si fa clic sul widget **Rapporto di** mancato recapito, verrà visualizzato il rapporto di mancato **recapito.**</span><span class="sxs-lookup"><span data-stu-id="6fdb3-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="6fdb3-113">Per impostazione predefinita, viene visualizzata l'attività per tutti i codici di errore.</span><span class="sxs-lookup"><span data-stu-id="6fdb3-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="6fdb3-114">Se fai clic **su Mostra dati per**, puoi selezionare un codice di errore specifico nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="6fdb3-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="6fdb3-115">Se si passa il mouse su un colore specifico (codice di errore) in un giorno specifico del grafico, verrà visualizzato il numero totale di messaggi per l'errore.</span><span class="sxs-lookup"><span data-stu-id="6fdb3-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Visualizzazione report nel rapporto dominio non accettato](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="6fdb3-117">Visualizzazione tabella dettagli per il rapporto di mancato recapito</span><span class="sxs-lookup"><span data-stu-id="6fdb3-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="6fdb3-118">Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fdb3-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="6fdb3-119">**Data**</span><span class="sxs-lookup"><span data-stu-id="6fdb3-119">**Date**</span></span>
- <span data-ttu-id="6fdb3-120">**Codice rapporto di mancato recapito**</span><span class="sxs-lookup"><span data-stu-id="6fdb3-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="6fdb3-121">**Numero**</span><span class="sxs-lookup"><span data-stu-id="6fdb3-121">**Count**</span></span>
- <span data-ttu-id="6fdb3-122">**Messaggi di esempio**: ID messaggio di un campione di messaggi interessati.</span><span class="sxs-lookup"><span data-stu-id="6fdb3-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="6fdb3-123">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="6fdb3-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6fdb3-124">Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic **su Richiedi download.**</span><span class="sxs-lookup"><span data-stu-id="6fdb3-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="6fdb3-125">Quando si seleziona una riga nella tabella, viene visualizzato un riquadro a comparsa con le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6fdb3-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="6fdb3-126">**Data**</span><span class="sxs-lookup"><span data-stu-id="6fdb3-126">**Date**</span></span>
- <span data-ttu-id="6fdb3-127">**Codice del rapporto di mancato** recapito: è possibile fare clic sul collegamento per trovare ulteriori informazioni sulle cause e le soluzioni per il codice di errore specifico.</span><span class="sxs-lookup"><span data-stu-id="6fdb3-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="6fdb3-128">**Numero**</span><span class="sxs-lookup"><span data-stu-id="6fdb3-128">**Count**</span></span>
- <span data-ttu-id="6fdb3-129">**Messaggi di esempio:** è possibile fare clic **su Visualizza** messaggi di esempio per visualizzare i risultati [della](message-trace-scc.md) traccia dei messaggi per un campione dei messaggi interessati.</span><span class="sxs-lookup"><span data-stu-id="6fdb3-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Riquadro a comparsa Dettagli dopo aver selezionato una riga nella visualizzazione Tabella dettagli nel rapporto di mancato recapito](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="6fdb3-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6fdb3-131">Related topics</span></span>

<span data-ttu-id="6fdb3-132">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="6fdb3-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
