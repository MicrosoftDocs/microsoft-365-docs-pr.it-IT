---
title: Informazioni dettagliate e report dei client di autenticazione SMTP nel dashboard del flusso di posta
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
description: Gli amministratori possono imparare a usare le informazioni dettagliate e il report di autenticazione SMTP nel dashboard del flusso di posta nel Centro sicurezza & conformità per monitorare i mittenti di posta elettronica nell'organizzazione che utilizzano SMTP autenticato (SMTP AUTH) per inviare messaggi di posta elettronica.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3476ee2f9388245fb105a0910fa7b7d11ec3aeee
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150244"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a><span data-ttu-id="38788-103">Informazioni dettagliate e report dei client di autenticazione SMTP nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="38788-103">SMTP Auth clients insight and report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="38788-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="38788-104">**Applies to**</span></span>
- [<span data-ttu-id="38788-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="38788-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="38788-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="38788-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="38788-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38788-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="38788-108">Le informazioni dettagliate sui client di autenticazione **SMTP** nel [dashboard](mail-flow-insights-v2.md) del flusso di posta e nel report dei client di autenticazione [SMTP](#smtp-auth-clients-report) associati nel Centro sicurezza [&](https://protection.office.com) conformità evidenziano l'uso del protocollo di invio al client SMTP AUTH da parte degli utenti o degli account di sistema nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38788-108">The **SMTP Auth clients** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) and the associated [SMTP Auth clients report](#smtp-auth-clients-report) in the [Security & Compliance Center](https://protection.office.com) highlight the use of the SMTP AUTH client submission protocol by users or system accounts in your organization.</span></span> <span data-ttu-id="38788-109">Questo protocollo legacy (che usa l'endpoint smtp.office365.com) offre solo l'autenticazione di base ed è soggetto all'uso da parte di account compromessi per inviare posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="38788-109">This legacy protocol (which uses the endpoint smtp.office365.com) only offers Basic authentication, and is susceptible to being used by compromised accounts to send email.</span></span> <span data-ttu-id="38788-110">Le informazioni dettagliate e il report consentono di verificare la presenza di attività insolite per gli invii di posta elettronica SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="38788-110">The insight and report allow you to check for unusual activity for SMTP AUTH email submissions.</span></span> <span data-ttu-id="38788-111">Vengono inoltre mostrati i dati sull'utilizzo di TLS per client o dispositivi che utilizzano SMTP AUTH.</span><span class="sxs-lookup"><span data-stu-id="38788-111">It also shows the TLS usage data for clients or devices using SMTP AUTH.</span></span>

<span data-ttu-id="38788-112">Il widget indica il numero di utenti o account di servizio che hanno utilizzato il protocollo di autenticazione SMTP negli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="38788-112">The widget indicates the number of users or service accounts that have used the SMTP Auth protocol in the last 7 days.</span></span>

![Widget Client di autenticazione SMTP nel dashboard del flusso di posta nel Centro sicurezza & conformità](../../media/mfi-smtp-auth-clients-report-widget.png)

<span data-ttu-id="38788-114">Se si fa clic sul numero di messaggi nel widget, viene visualizzato un riquadro a comparsa **client di autenticazione SMTP.**</span><span class="sxs-lookup"><span data-stu-id="38788-114">If you click the number of messages on the widget, an **SMTP Auth clients** flyout appears.</span></span> <span data-ttu-id="38788-115">Il riquadro a comparsa offre una visualizzazione aggregata dell'utilizzo di TLS e dei volumi dell'ultima settimana.</span><span class="sxs-lookup"><span data-stu-id="38788-115">The flyout provides an aggregated view of the TLS usage and volumes for the last week.</span></span>

![Riquadro a comparsa Dettagli dopo aver fatto clic sul widget Client di autenticazione SMTP nel dashboard del flusso di posta](../../media/mfi-smtp-auth-clients-report-details.png)

<span data-ttu-id="38788-117">È possibile fare clic sul collegamento al rapporto dei client di autenticazione **SMTP** per passare al report dei client di autenticazione SMTP, come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="38788-117">You can click the **SMTP Auth clients report** link to go to the SMTP Auth clients report as described in the next section.</span></span>

## <a name="smtp-auth-clients-report"></a><span data-ttu-id="38788-118">Report sui client di autenticazione SMTP</span><span class="sxs-lookup"><span data-stu-id="38788-118">SMTP Auth clients report</span></span>

### <a name="report-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="38788-119">Visualizzazione rapporto per il report dei client di autenticazione SMTP</span><span class="sxs-lookup"><span data-stu-id="38788-119">Report view for the SMTP Auth clients report</span></span>

<span data-ttu-id="38788-120">Per impostazione predefinita, il report mostra i dati degli ultimi 7 giorni, ma i dati sono disponibili per gli ultimi 90 giorni.</span><span class="sxs-lookup"><span data-stu-id="38788-120">By default, the report shows data for the last 7 days, but data is available for the last 90 days.</span></span>

<span data-ttu-id="38788-121">La sezione panoramica contiene i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="38788-121">The overview section contains the following charts:</span></span>

- <span data-ttu-id="38788-122">**Visualizzare i dati per:** Volume di invio: per impostazione predefinita, il grafico mostra il numero di messaggi del client di autenticazione SMTP inviati da tutti i domini ( Mostra dati **per:** Tutti i domini mittente è selezionato per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="38788-122">**View data by: Sending volume**: By default, the chart shows the number of SMTP Auth client messages that were sent from all domains (**Show data for: All sender domains** is selected by default).</span></span> <span data-ttu-id="38788-123">È possibile filtrare i risultati in un dominio del mittente specifico facendo clic su Mostra dati **per** e selezionando il dominio del mittente nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="38788-123">You can filter the results to a specific sender domain by clicking **Show data for** and selecting the sender domain from the dropdown list.</span></span> <span data-ttu-id="38788-124">Se si passa il mouse su un punto dati specifico (giorno), viene visualizzato il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="38788-124">If you hover a specific data point (day), the number of messages is shown.</span></span>

  ![Invio della visualizzazione volume nel report dei client di autenticazione SMTP nel Centro sicurezza & conformità](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- <span data-ttu-id="38788-126">**Visualizzare i dati in base a:** Utilizzo TLS : il grafico mostra la percentuale di utilizzo di TLS per tutti i messaggi del client di autenticazione SMTP durante il periodo di tempo selezionato.</span><span class="sxs-lookup"><span data-stu-id="38788-126">**View data by: TLS Usage**: The chart shows the percentage of TLS usage for all SMTP Auth client messages during the selected time period.</span></span> <span data-ttu-id="38788-127">Questo grafico consente di identificare ed eseguire azioni su utenti e account di sistema che usano ancora versioni precedenti di TLS.</span><span class="sxs-lookup"><span data-stu-id="38788-127">This chart allows you to identify and take action on users and system accounts that are still using older versions of TLS.</span></span>

  ![Visualizzazione utilizzo TLS nel report dei client di autenticazione SMTP nel Centro sicurezza & conformità](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

<span data-ttu-id="38788-129">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="38788-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="38788-130">Fare **clic su Richiedi rapporto** per ricevere una versione più dettagliata del rapporto in un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="38788-130">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="38788-131">È possibile specificare l'intervallo di date e i destinatari per ricevere il rapporto.</span><span class="sxs-lookup"><span data-stu-id="38788-131">You can specify the date range and the recipients to receive the report.</span></span>

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a><span data-ttu-id="38788-132">Visualizzazione della tabella dei dettagli per il report dei client di autenticazione SMTP</span><span class="sxs-lookup"><span data-stu-id="38788-132">Details table view for the SMTP Auth clients report</span></span>

<span data-ttu-id="38788-133">Se si **fa clic su Visualizza tabella dettagli,** le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="38788-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="38788-134">**Visualizzare i dati in base a: Volume** di invio: in una tabella vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38788-134">**View data by: Sending volume**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="38788-135">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="38788-135">**Sender address**</span></span>
  - <span data-ttu-id="38788-136">**Numero messaggi**</span><span class="sxs-lookup"><span data-stu-id="38788-136">**Message count**</span></span>

  <span data-ttu-id="38788-137">Se si seleziona una riga, gli stessi dettagli vengono visualizzati in un riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="38788-137">If you select a row, the same details are shown in a flyout.</span></span>

- <span data-ttu-id="38788-138">**Visualizzare i dati in base a: Utilizzo TLS**: in una tabella vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="38788-138">**View data by: TLS Usage**: The following information is shown in a table:</span></span>

  - <span data-ttu-id="38788-139">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="38788-139">**Sender address**</span></span>
  - <span data-ttu-id="38788-140">**TLS1.0%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38788-140">**TLS1.0%**<sup>\*</sup></span></span>
  - <span data-ttu-id="38788-141">**TLS1.1%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38788-141">**TLS1.1%**<sup>\*</sup></span></span>
  - <span data-ttu-id="38788-142">**TLS1.2%**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="38788-142">**TLS1.2%**<sup>\*</sup></span></span>
  - <span data-ttu-id="38788-143">**Numero messaggi**</span><span class="sxs-lookup"><span data-stu-id="38788-143">**Message count**</span></span>

  <span data-ttu-id="38788-144"><sup>\*</sup> Questa colonna mostra sia la percentuale che il numero di messaggi provenienti dal mittente.</span><span class="sxs-lookup"><span data-stu-id="38788-144"><sup>\*</sup> This column shows both the percentage and number of messages from the sender.</span></span>

<span data-ttu-id="38788-145">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="38788-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="38788-146">Se si seleziona una riga, dettagli simili vengono visualizzati in un riquadro a comparsa:</span><span class="sxs-lookup"><span data-stu-id="38788-146">If you select a row, similar details are shown in a flyout:</span></span>

![Riquadro a comparsa Dettagli dalla tabella dei dettagli della visualizzazione di utilizzo tls nel report dei client di autenticazione SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

<span data-ttu-id="38788-148">Fare **clic su Richiedi rapporto** per ricevere una versione più dettagliata del rapporto in un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="38788-148">Click **Request report** to receive a more detailed version of the report in an email message.</span></span> <span data-ttu-id="38788-149">È possibile specificare l'intervallo di date e i destinatari per ricevere il rapporto.</span><span class="sxs-lookup"><span data-stu-id="38788-149">You can specify the date range and the recipients to receive the report.</span></span>

<span data-ttu-id="38788-150">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="38788-150">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="38788-151">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="38788-151">Related topics</span></span>

<span data-ttu-id="38788-152">Per informazioni su altre informazioni dettagliate nel dashboard del flusso di posta, vedere Informazioni dettagliate sul flusso di posta [nel Centro sicurezza & conformità.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="38788-152">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
