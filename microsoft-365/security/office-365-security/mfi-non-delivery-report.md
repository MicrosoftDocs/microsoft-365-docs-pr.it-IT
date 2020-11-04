---
title: Rapporto di mancato recapito nel dashboard del flusso di posta
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
description: Gli amministratori possono imparare a usare il rapporto Dettagli di mancato recapito nel dashboard del flusso di posta elettronica nel centro sicurezza & conformità per monitorare i codici di errore più frequentemente riscontrati nei rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo) dai mittenti dell'organizzazione.
ms.openlocfilehash: 4967b3b5c294566e46bbc715dd6702c23d618105
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877682"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="36671-103">Rapporto di mancato recapito nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="36671-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="36671-104">Il **rapporto di mancato recapito** nel [Dashboard del flusso di posta](mail-flow-insights-v2.md) nel [Centro sicurezza & conformità](https://protection.office.com) Visualizza i codici di errore più rilevati nei rapporti di mancato recapito (noti anche come NDR o messaggi di rimbalzo) per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="36671-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="36671-105">Questo rapporto Visualizza i dettagli dei rapporti di mancato recapito in modo da poter risolvere i problemi relativi al parto.</span><span class="sxs-lookup"><span data-stu-id="36671-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget del rapporto di mancato recapito nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="36671-107">Visualizzazione report per il rapporto di mancato recapito</span><span class="sxs-lookup"><span data-stu-id="36671-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="36671-108">Se si fa clic sul widget del **rapporto di mancato recapito** , verrà eseguito il **rapporto di mancato recapito**.</span><span class="sxs-lookup"><span data-stu-id="36671-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="36671-109">Per impostazione predefinita, viene visualizzata l'attività per tutti i codici di errore.</span><span class="sxs-lookup"><span data-stu-id="36671-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="36671-110">Se si fa clic su **Mostra dati per** , è possibile selezionare un codice di errore specifico dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="36671-110">If you click **Show data for** , you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="36671-111">Se si posiziona il puntatore del mouse su un colore specifico (codice di errore) in un giorno specifico del grafico, verrà visualizzato il numero totale di messaggi per l'errore.</span><span class="sxs-lookup"><span data-stu-id="36671-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Visualizzazione report nel rapporto dominio non accettato](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="36671-113">Visualizzazione della tabella dei dettagli per il rapporto di mancato recapito</span><span class="sxs-lookup"><span data-stu-id="36671-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="36671-114">Se si fa clic su **Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="36671-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="36671-115">**Data**</span><span class="sxs-lookup"><span data-stu-id="36671-115">**Date**</span></span>
- <span data-ttu-id="36671-116">**Codice del rapporto di mancato recapito**</span><span class="sxs-lookup"><span data-stu-id="36671-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="36671-117">**Numero**</span><span class="sxs-lookup"><span data-stu-id="36671-117">**Count**</span></span>
- <span data-ttu-id="36671-118">**Messaggi di esempio** : ID del messaggio di un esempio di messaggi coinvolti.</span><span class="sxs-lookup"><span data-stu-id="36671-118">**Sample messages** : The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="36671-119">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="36671-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="36671-120">Per inviare tramite posta elettronica il report per un intervallo di date specifico a uno o più destinatari, fare clic su **Richiedi download**.</span><span class="sxs-lookup"><span data-stu-id="36671-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="36671-121">Quando si seleziona una riga nella tabella, viene visualizzato un riquadro a comparsa con le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="36671-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="36671-122">**Data**</span><span class="sxs-lookup"><span data-stu-id="36671-122">**Date**</span></span>
- <span data-ttu-id="36671-123">**Codice del rapporto di mancato recapito** : è possibile fare clic sul collegamento per ottenere ulteriori informazioni sulle cause e sulle soluzioni per il codice di errore specifico.</span><span class="sxs-lookup"><span data-stu-id="36671-123">**Non-delivery report code** : You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="36671-124">**Numero**</span><span class="sxs-lookup"><span data-stu-id="36671-124">**Count**</span></span>
- <span data-ttu-id="36671-125">**Messaggi di esempio** : è possibile fare clic su **Visualizza messaggi di esempio** per visualizzare i risultati della [traccia](message-trace-scc.md) dei messaggi per un esempio di messaggi coinvolti.</span><span class="sxs-lookup"><span data-stu-id="36671-125">**Sample messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Riquadro a comparsa dettagli dopo aver selezionato una riga nella visualizzazione tabella dettagli nel rapporto di mancato recapito](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="36671-127">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="36671-127">Related topics</span></span>

<span data-ttu-id="36671-128">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="36671-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
