---
title: Insight e report dei client auth SMTP nel dashboard del flusso di posta
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
description: Gli amministratori possono imparare a usare l'Insight e il report SMTP AUTH nel dashboard del flusso di posta elettronica nel centro sicurezza & conformità per monitorare i mittenti di posta elettronica nell'organizzazione che utilizzano SMTP autenticato (AUTH) per inviare messaggi di posta elettronica.
ms.openlocfilehash: 7ca673e5ecc92c28996a976c26a38ae570f16203
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199242"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="bb1cb-103">Insight e report dei client auth SMTP nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="bb1cb-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="bb1cb-104">I **client auth SMTP** Insight nel [Dashboard del flusso di posta](mail-flow-insights-v2.md) e nel [report dei client auth smtp](#smtp-auth-clients-report) associati nel [Centro sicurezza & Compliance](https://protection.office.com) evidenziano l'utilizzo del protocollo di invio client auth SMTP da parte degli utenti o degli account di sistema nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-104">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="bb1cb-105">Questo protocollo legacy (che utilizza l'endpoint smtp.office365.com) offre solo l'autenticazione di base ed è suscettibile di essere utilizzato dagli account compromessi per inviare messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-105">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="bb1cb-106">Insight and report consentono di verificare l'utilizzo di attività inusuali per invii di posta elettronica SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-106">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="bb1cb-107">Vengono inoltre visualizzati i dati di utilizzo di TLS per client o dispositivi che utilizzano l'autenticazione SMTP.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-107">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="bb1cb-108">Il widget indica il numero di utenti o di account di servizio che hanno utilizzato il protocollo di autenticazione SMTP negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-108">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Widget dei client auth SMTP nel dashboard del flusso di posta elettronica nel centro sicurezza & Compliance](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="bb1cb-110">Se si fa clic sul numero di messaggi sul widget, viene visualizzato un riquadro a comparsa dei **client auth SMTP** .</span><span class="sxs-lookup"><span data-stu-id="bb1cb-110">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="bb1cb-111">Il riquadro a comparsa fornisce una visualizzazione aggregata dell'utilizzo e dei volumi TLS per l'ultima settimana.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-111">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Riquadro a comparsa dettagli dopo aver fatto clic sul widget client auth SMTP nel dashboard del flusso di posta](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="bb1cb-113">È possibile fare clic sul collegamento **rapporto client auth SMTP** per accedere al report client auth SMTP come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-113">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="bb1cb-114">Report sui client di autenticazione SMTP</span><span class="sxs-lookup"><span data-stu-id="bb1cb-114">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="bb1cb-115">Visualizzazione report per il rapporto client auth SMTP</span><span class="sxs-lookup"><span data-stu-id="bb1cb-115">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="bb1cb-116">Per impostazione predefinita, il report Visualizza i dati per gli ultimi 7 giorni, ma i dati sono disponibili per gli ultimi 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-116">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="bb1cb-117">La sezione Panoramica contiene i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb1cb-117">The overview section contains the following charts:</span></span>

- <span data-ttu-id="bb1cb-118">**Visualizzazione dei dati per: volume di invio**: per impostazione predefinita, il grafico mostra il numero di messaggi client di autenticazione SMTP inviati da tutti i domini (**Mostra dati per: tutti i domini mittente** è selezionata per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="bb1cb-118">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="bb1cb-119">È possibile filtrare i risultati in uno specifico dominio del mittente facendo clic su **Mostra dati per** e selezionando il dominio del mittente dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-119">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="bb1cb-120">Se si posiziona il puntatore del mouse su un punto dati specifico (giorno), viene visualizzato il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-120">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Invio della visualizzazione volume nel rapporto client auth SMTP nel centro sicurezza & Compliance](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="bb1cb-122">**Visualizzare i dati in base a: utilizzo TLS**: il grafico mostra la percentuale di utilizzo di TLS per tutti i messaggi client auth SMTP durante il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-122">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="bb1cb-123">Questo grafico consente di identificare ed eseguire azioni su utenti e account di sistema che continuano a utilizzare versioni precedenti di TLS.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-123">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Visualizzazione utilizzo TLS nel rapporto client auth SMTP nel centro sicurezza & Compliance](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="bb1cb-125">Se si fa clic su **filtri** in una visualizzazione report, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bb1cb-126">Fare clic su **Richiedi report** per ricevere una versione più dettagliata del report in un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-126">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="bb1cb-127">È possibile specificare l'intervallo di date e i destinatari per la ricezione del report.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-127">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="bb1cb-128">Visualizzazione tabella dettagli per il rapporto client auth SMTP</span><span class="sxs-lookup"><span data-stu-id="bb1cb-128">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="bb1cb-129">Se si fa clic su **Visualizza tabella dettagli**, le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="bb1cb-129">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="bb1cb-130">**Visualizzare i dati in base a: volume di invio**: le informazioni seguenti sono visualizzate in una tabella:</span><span class="sxs-lookup"><span data-stu-id="bb1cb-130">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="bb1cb-131">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-131">**Sender address**</span></span>
  - <span data-ttu-id="bb1cb-132">**Numero di messaggi**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-132">**Message count**</span></span>

  <span data-ttu-id="bb1cb-133">Se si seleziona una riga, gli stessi dettagli vengono visualizzati in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-133">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="bb1cb-134">**Visualizzare i dati in base a: utilizzo di TLS**: le informazioni seguenti sono visualizzate in una tabella:</span><span class="sxs-lookup"><span data-stu-id="bb1cb-134">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="bb1cb-135">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-135">**Sender address**</span></span>
  - <span data-ttu-id="bb1cb-136">**TLS 1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb1cb-136">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="bb1cb-137">**TLS 1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb1cb-137">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="bb1cb-138">**TLS 1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bb1cb-138">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="bb1cb-139">**Numero di messaggi**</span><span class="sxs-lookup"><span data-stu-id="bb1cb-139">**Message count**</span></span>

  <span data-ttu-id="bb1cb-140"><sup>\*</sup> In questa colonna sono riportati sia la percentuale che il numero di messaggi provenienti dal mittente.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-140"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="bb1cb-141">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bb1cb-142">Se si seleziona una riga, i dettagli simili vengono visualizzati in un riquadro a comparsa:</span><span class="sxs-lookup"><span data-stu-id="bb1cb-142">If you select a row, similar details are shown in a flyout:</span></span>

![Riquadro a comparsa dettagli dalla tabella dei dettagli della visualizzazione utilizzo TLS nel rapporto client auth SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="bb1cb-144">Fare clic su **Richiedi report** per ricevere una versione più dettagliata del report in un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-144">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="bb1cb-145">È possibile specificare l'intervallo di date e i destinatari per la ricezione del report.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-145">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="bb1cb-146">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="bb1cb-146">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb1cb-147">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bb1cb-147">Related topics</span></span>

<span data-ttu-id="bb1cb-148">Per informazioni su altre intuizioni nel dashboard del flusso di posta, vedere [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="bb1cb-148">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
