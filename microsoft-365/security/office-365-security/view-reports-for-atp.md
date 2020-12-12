---
title: Visualizzare i report di Defender per Office 365 nel dashboard dei report
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Trovare e utilizzare i report per Microsoft Defender per Office 365 nel centro sicurezza & Compliance.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 82c003478538274be1dd1d2e04816de80d1eae6d
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659454"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a><span data-ttu-id="6cbb5-103">Visualizzare i report di Defender per Office 365 nel dashboard dei report nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="6cbb5-103">View Defender for Office 365 reports in the Reports dashboard in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6cbb5-104">Microsoft Defender per le organizzazioni di Office 365 (ad esempio, abbonamenti Microsoft 365 E5 o Microsoft Defender per Office 365 piano 1 o Microsoft Defender per Office 365 piano 2 componenti aggiuntivi) contengono una serie di rapporti relativi alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-104">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="6cbb5-105">Se si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), è possibile visualizzare i report nel centro sicurezza & Compliance accedendo al  \> **Dashboard** report.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="6cbb5-106">Per accedere direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="6cbb5-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard dei report nel centro sicurezza & Compliance](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a><span data-ttu-id="6cbb5-108">Report tipi di file per Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="6cbb5-108">Defender for Office 365 file types report</span></span>

<span data-ttu-id="6cbb5-109">Il report del **rapporto tipi di file di Defender per Office 365** Visualizza il tipo di file rilevati come dannosi per gli [allegati sicuri](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-109">The **Defender for Office 365 file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="6cbb5-110">La visualizzazione aggregazione del report consente 90 giorni di filtraggio, mentre la visualizzazione dettagli consente solo 10 giorni di filtraggio.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="6cbb5-111">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al  \> **Dashboard** dei report e selezionare **Defender per i tipi di file di Office 365**.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 file types**.</span></span> <span data-ttu-id="6cbb5-112">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="6cbb5-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Widget per i tipi di file di Defender per Office 365 nel dashboard dei report](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="6cbb5-114">Le informazioni contenute in questo report sono disponibili anche nel [rapporto disposizione dei messaggi di Defender per Office 365](#defender-for-office-365-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-114">The information in this report is also available in the [Defender for Office 365 message disposition report](#defender-for-office-365-message-disposition-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="6cbb5-115">Visualizzazione report per il report dei tipi di file del difensore per Office 365</span><span class="sxs-lookup"><span data-stu-id="6cbb5-115">Report view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="6cbb5-116">Sono disponibili le visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-116">The following views are available:</span></span>

- <span data-ttu-id="6cbb5-117">**Visualizzare i dati per: file**: il grafico contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="6cbb5-118">**Allegati di Excel dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="6cbb5-119">**Allegati Flash dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="6cbb5-120">**Allegati PDF dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="6cbb5-121">**Allegati di PowerPoint dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="6cbb5-122">**URL dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="6cbb5-123">**Allegati di Word dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="6cbb5-124">**Allegati eseguibili dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="6cbb5-125">**Altri**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-125">**Others**</span></span>

  <span data-ttu-id="6cbb5-126">Quando si posiziona il puntatore del mouse su un determinato giorno (punto dati), è possibile visualizzare la ripartizione dei tipi di file dannosi rilevati dagli [allegati sicuri](atp-safe-attachments.md) e dalla [protezione antimalware in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Visualizzazione file nel rapporto tipi di file di Defender per Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="6cbb5-128">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="6cbb5-129">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="6cbb5-130">Gli stessi valori del tipo di file che sono visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="6cbb5-131">**Visualizzazione dei dati per: messaggio**: il grafico contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="6cbb5-132">**Blocca accesso**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-132">**Block access**</span></span>
  - <span data-ttu-id="6cbb5-133">**Messaggi sostituiti**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-133">**Messages replaced**</span></span>
  - <span data-ttu-id="6cbb5-134">**Messaggi monitorati**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-134">**Messages monitored**</span></span>
  - <span data-ttu-id="6cbb5-135">**Sostituito dal recapito dinamico della posta elettronica**: per ulteriori informazioni, vedere [Dynamic Delivery in Safe Attachment Policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Visualizzazione messaggio nel rapporto tipi di file di Defender per Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="6cbb5-137">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="6cbb5-138">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="6cbb5-139">Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a><span data-ttu-id="6cbb5-140">Visualizzazione della tabella dei dettagli per il report sui tipi di file del Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="6cbb5-140">Details table view for the Defender for Office 365 file types report</span></span>

<span data-ttu-id="6cbb5-141">Se si fa clic su **Visualizza tabella dettagli**, il rapporto fornisce una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="6cbb5-142">Le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="6cbb5-143">**Visualizzare i dati in base a: file**:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-143">**View data by: File**:</span></span>

  - <span data-ttu-id="6cbb5-144">**Data**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-144">**Date**</span></span>
  - <span data-ttu-id="6cbb5-145">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-145">**Recipient address**</span></span>
  - <span data-ttu-id="6cbb5-146">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-146">**Sender address**</span></span>
  - <span data-ttu-id="6cbb5-147">**ID messaggio**: disponibile nel campo di intestazione **Message-ID** nell'intestazione del messaggio e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="6cbb5-148">Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="6cbb5-149">**File**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-149">**File**</span></span>

  <span data-ttu-id="6cbb5-150">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="6cbb5-151">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="6cbb5-152">Gli stessi valori del tipo di file che sono visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="6cbb5-153">**Visualizzare i dati per: messaggio**:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="6cbb5-154">**Data**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-154">**Date**</span></span>
  - <span data-ttu-id="6cbb5-155">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-155">**Recipient address**</span></span>
  - <span data-ttu-id="6cbb5-156">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-156">**Sender address**</span></span>
  - <span data-ttu-id="6cbb5-157">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-157">**Message ID**</span></span>
  - <span data-ttu-id="6cbb5-158">**File**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-158">**File**</span></span>
  - <span data-ttu-id="6cbb5-159">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-159">**Subject**</span></span>

  <span data-ttu-id="6cbb5-160">Se si fa clic su **filtri**, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="6cbb5-161">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="6cbb5-162">Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="6cbb5-163">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-163">To get back to the reports view, click **View report**.</span></span>

## <a name="defender-for-office-365-message-disposition-report"></a><span data-ttu-id="6cbb5-164">Report disposizione messaggi di Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="6cbb5-164">Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="6cbb5-165">Il rapporto di **disposizione dei messaggi ATP** indica le azioni eseguite per i messaggi di posta elettronica rilevati come contenuti dannosi.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="6cbb5-166">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al  \> **Dashboard** dei report e selezionare **protezione per disposizione dei messaggi di Office 365**.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Defender for Office 365 message disposition**.</span></span> <span data-ttu-id="6cbb5-167">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="6cbb5-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Widget disposizione dei messaggi di Defender per Office 365 nel dashboard dei report](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="6cbb5-169">Le informazioni contenute in questo report sono disponibili anche nel [report dei tipi di file di Defender per Office 365](#defender-for-office-365-file-types-report).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-169">The information in this report is also available in the [Defender for Office 365 file types report](#defender-for-office-365-file-types-report).</span></span>

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="6cbb5-170">Visualizzazione report per il rapporto disposizione messaggi di protezione per Office 365</span><span class="sxs-lookup"><span data-stu-id="6cbb5-170">Report view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="6cbb5-171">Sono disponibili le visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-171">The following views are available:</span></span>

- <span data-ttu-id="6cbb5-172">**Visualizzazione dei dati per: messaggio**: il grafico contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="6cbb5-173">**Blocca accesso**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-173">**Block access**</span></span>
  - <span data-ttu-id="6cbb5-174">**Messaggi sostituiti**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-174">**Messages replaced**</span></span>
  - <span data-ttu-id="6cbb5-175">**Messaggi monitorati**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-175">**Messages monitored**</span></span>
  - <span data-ttu-id="6cbb5-176">**Sostituito dal recapito dinamico della posta elettronica**: per ulteriori informazioni, vedere [Dynamic Delivery in Safe Attachment Policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Visualizzazione messaggio nel rapporto tipi di file di Defender per Office 365](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="6cbb5-178">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="6cbb5-179">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="6cbb5-180">Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="6cbb5-181">**Visualizzare i dati per: file**: il grafico contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="6cbb5-182">**Allegati di Excel dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="6cbb5-183">**Allegati Flash dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="6cbb5-184">**Allegati PDF dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="6cbb5-185">**Allegati di PowerPoint dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="6cbb5-186">**URL dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="6cbb5-187">**Allegati di Word dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="6cbb5-188">**Allegati eseguibili dannosi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="6cbb5-189">**Altri**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-189">**Others**</span></span>

  <span data-ttu-id="6cbb5-190">Quando si posiziona il puntatore del mouse su un determinato giorno (punto dati), è possibile visualizzare la ripartizione dei tipi di file dannosi rilevati dagli [allegati sicuri](atp-safe-attachments.md) e dalla [protezione antimalware in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Visualizzazione file nel rapporto tipi di file di Defender per Office 365](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="6cbb5-192">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="6cbb5-193">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="6cbb5-194">Gli stessi valori del tipo di file che sono visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a><span data-ttu-id="6cbb5-195">Visualizzazione tabella dettagli per il rapporto disposizione messaggi di protezione per Office 365</span><span class="sxs-lookup"><span data-stu-id="6cbb5-195">Details table view for the Defender for Office 365 message disposition report</span></span>

<span data-ttu-id="6cbb5-196">Se si fa clic su **Visualizza tabella dettagli**, il rapporto fornisce una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="6cbb5-197">Le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="6cbb5-198">**Visualizzare i dati per: messaggio**:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="6cbb5-199">**Data**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-199">**Date**</span></span>
  - <span data-ttu-id="6cbb5-200">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-200">**Recipient address**</span></span>
  - <span data-ttu-id="6cbb5-201">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-201">**Sender address**</span></span>
  - <span data-ttu-id="6cbb5-202">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-202">**Message ID**</span></span>
  - <span data-ttu-id="6cbb5-203">**File**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-203">**File**</span></span>
  - <span data-ttu-id="6cbb5-204">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-204">**Subject**</span></span>

  <span data-ttu-id="6cbb5-205">Se si fa clic su **filtri**, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="6cbb5-206">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="6cbb5-207">Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="6cbb5-208">**Visualizzare i dati in base a: file**:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-208">**View data by: File**:</span></span>

  - <span data-ttu-id="6cbb5-209">**Data**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-209">**Date**</span></span>
  - <span data-ttu-id="6cbb5-210">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-210">**Recipient address**</span></span>
  - <span data-ttu-id="6cbb5-211">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-211">**Sender address**</span></span>
  - <span data-ttu-id="6cbb5-212">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-212">**Message ID**</span></span>
  - <span data-ttu-id="6cbb5-213">**File**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-213">**File**</span></span>

  <span data-ttu-id="6cbb5-214">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="6cbb5-215">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="6cbb5-216">Gli stessi valori del tipo di file che sono visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="6cbb5-217">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-217">To get back to the reports view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="6cbb5-218">Rapporto latenza posta</span><span class="sxs-lookup"><span data-stu-id="6cbb5-218">Mail latency report</span></span>

<span data-ttu-id="6cbb5-219">Il **rapporto latenza posta** Mostra una visualizzazione aggregata del recapito della posta e della latenza di detonazione vissuti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-219">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="6cbb5-220">I tempi di recapito della posta nel servizio sono soggetti a numerosi fattori e il tempo di consegna assoluto in secondi non è spesso un buon indicatore del successo o di un problema.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-220">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="6cbb5-221">Un tempo di consegna lento in un giorno può essere considerato un tempo medio per il recapito in un altro giorno o viceversa.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-221">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="6cbb5-222">Il **rapporto latenza posta** cerca di qualificare il recapito dei messaggi in base ai dati statistici relativi ai tempi di consegna osservati di altri messaggi:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-222">The **Mail latency report** tries to qualify message delivery based on statistical data about the observed delivery times of other messages:</span></span>

- <span data-ttu-id="6cbb5-223">**cinquantesimo percentile**: questo è il mezzo per i tempi di consegna dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-223">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="6cbb5-224">Questo valore può essere considerato come un tempo medio per il recapito.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-224">You can consider this value as an average delivery time.</span></span>
- <span data-ttu-id="6cbb5-225">**90 ° percentile**: indica una latenza elevata per il recapito dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-225">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="6cbb5-226">Solo il 10% dei messaggi richiede più tempo di quanto questo valore venga recapitato.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-226">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="6cbb5-227">**99a percentile**: indica la latenza più alta per il recapito dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-227">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="6cbb5-228">La latenza della rete e del client non è inclusa.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-228">Client side and network latency are not included.</span></span>

<span data-ttu-id="6cbb5-229">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al  \> **Dashboard** report e selezionare **rapporto latenza posta**.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-229">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mail latency report**.</span></span> <span data-ttu-id="6cbb5-230">Per passare direttamente al report, aprire <https://protection.office.com/mailLatencyReport?viewid=P50> .</span><span class="sxs-lookup"><span data-stu-id="6cbb5-230">To go directly to the report, open <https://protection.office.com/mailLatencyReport?viewid=P50>.</span></span>

![Widget rapporto latenza posta nel dashboard report](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a><span data-ttu-id="6cbb5-232">Visualizzazione report per il rapporto latenza posta</span><span class="sxs-lookup"><span data-stu-id="6cbb5-232">Report view for the Mail latency report</span></span>

<span data-ttu-id="6cbb5-233">Quando si apre il report, la scheda **cinquantesimo percentile** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-233">When you open the report, the **50th percentiles** tab is selected by default.</span></span>

<span data-ttu-id="6cbb5-234">Per impostazione predefinita, questa visualizzazione contiene un grafico configurato con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-234">By default, this view contains a chart that's configured with the following filters:</span></span>

- <span data-ttu-id="6cbb5-235">**Data**: gli ultimi 7 giorni</span><span class="sxs-lookup"><span data-stu-id="6cbb5-235">**Date**: The last 7 days</span></span>
- <span data-ttu-id="6cbb5-236">**Visualizzazione messaggio**:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-236">**Message View**:</span></span>
  - <span data-ttu-id="6cbb5-237">Messaggi detonati</span><span class="sxs-lookup"><span data-stu-id="6cbb5-237">Detonated messages</span></span>

<span data-ttu-id="6cbb5-238">In questo grafico vengono visualizzati i messaggi organizzati nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-238">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="6cbb5-239">**Latenza del recapito della posta**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-239">**Mail delivery latency**</span></span>
- <span data-ttu-id="6cbb5-240">**Latenza di detonazione**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-240">**Detonation latency**</span></span>

<span data-ttu-id="6cbb5-241">Quando si posiziona il puntatore del mouse su una categoria del grafico, è possibile visualizzare una ripartizione della latenza in ogni categoria.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-241">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![Rapporto latenza posta](../../media/mail-latency-report.png)

<span data-ttu-id="6cbb5-243">Se si fa clic su **filtro** nella visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-243">If you click **Filter** in the report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="6cbb5-244">Tutti i messaggi</span><span class="sxs-lookup"><span data-stu-id="6cbb5-244">All messages</span></span>
- <span data-ttu-id="6cbb5-245">Messaggi che contengono allegati o URL</span><span class="sxs-lookup"><span data-stu-id="6cbb5-245">Messages that contain attachments or URLs</span></span>

<span data-ttu-id="6cbb5-246">Se si fa clic sulla scheda **90 percentile** o sulla scheda **99a percentile** , vengono utilizzati gli stessi filtri predefiniti della visualizzazione **cinquantesimo percentile** .</span><span class="sxs-lookup"><span data-stu-id="6cbb5-246">If you click the **90th percentiles** tab or the **99th percentiles** tab, the same default filters from the **50th percentiles** view are used.</span></span>

### <a name="details-table-view-for-the-mail-latency-report"></a><span data-ttu-id="6cbb5-247">Visualizzazione tabella dettagli per il rapporto latenza posta</span><span class="sxs-lookup"><span data-stu-id="6cbb5-247">Details table view for the Mail latency report</span></span>

<span data-ttu-id="6cbb5-248">Nella visualizzazione tabella dei dettagli vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-248">The following information is shown in the details table view:</span></span>

- <span data-ttu-id="6cbb5-249">**Data**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-249">**Date**</span></span>
- <span data-ttu-id="6cbb5-250">**Percentili**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-250">**Percentiles**</span></span>
- <span data-ttu-id="6cbb5-251">**Numero di messaggi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-251">**Message count**</span></span>
- <span data-ttu-id="6cbb5-252">**Latenza complessiva**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-252">**Overall latency**</span></span>

![Dettagli del rapporto latenza posta](../../media/mail-latency-report-details.png)

<span data-ttu-id="6cbb5-254">La precedente indica che il 14 novembre la latenza media vissuta per tutti i messaggi recapitati e detonati è stata di **108,033** secondi.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-254">The above shows that on November 14 the average latency experienced for all messages delivered and detonated was **108.033** seconds.</span></span>

<span data-ttu-id="6cbb5-255">La tabella Details contiene le stesse informazioni in ogni scheda.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-255">The details table contains the same information on each tab.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="6cbb5-256">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="6cbb5-256">Threat protection status report</span></span>

<span data-ttu-id="6cbb5-257">Il rapporto **sullo stato della protezione dalle minacce** è una singola visualizzazione che raggruppa informazioni su contenuto dannoso e messaggi di posta elettronica dannosi rilevati e bloccati da [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) e Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-257">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="6cbb5-258">Per ulteriori informazioni, vedere [rapporto sullo stato della protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-258">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="6cbb5-259">Report sulla protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="6cbb5-259">URL threat protection report</span></span>

<span data-ttu-id="6cbb5-260">Il **rapporto di protezione** per gli URL fornisce visualizzazioni di riepilogo e di tendenza per le minacce rilevate e le azioni eseguite su clic URL come parte dei [collegamenti sicuri](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-260">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="6cbb5-261">Questo report non displicherà i dati da parte degli utenti a cui è stato applicato il criterio collegamenti sicuri ha l'opzione non **registrare i clic utente** selezionati.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-261">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="6cbb5-262">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al  \> **Dashboard** report e selezionare **rapporto protezione URL**.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-262">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="6cbb5-263">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="6cbb5-263">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widget report di protezione URL nel dashboard report](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="6cbb5-265">Si tratta di un *report di tendenza di protezione*, in cui i dati rappresentano le tendenze di un DataSet più grande.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-265">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="6cbb5-266">Di conseguenza, i dati nella visualizzazione aggregata non sono disponibili in tempo reale qui, ma i dati nella visualizzazione tabella dettagli sono, pertanto è possibile che si verifichi una leggera discrepanza tra le due visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-266">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="6cbb5-267">Visualizzazione report per il report di protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="6cbb5-267">Report view for the URL threat protection report</span></span>

<span data-ttu-id="6cbb5-268">Il report di **protezione dalle minacce URL** contiene due visualizzazioni aggregate aggiornate ogni quattro ore che mostrano i dati per gli ultimi 90 giorni:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-268">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="6cbb5-269">**Azione di protezione clic su URL**: Visualizza il numero di clic URL degli utenti nell'organizzazione e i risultati del clic:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-269">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="6cbb5-270">**Bloccato** (l'utente è stato bloccato dall'esplorazione all'URL)</span><span class="sxs-lookup"><span data-stu-id="6cbb5-270">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="6cbb5-271">**Bloccato e selezionato tramite**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-271">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="6cbb5-272">**Fare clic su di esso durante l'analisi**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-272">**Clicked through during scan**</span></span>

  <span data-ttu-id="6cbb5-273">Un clic indica che l'utente ha fatto clic sulla pagina blocca nel sito Web dannoso (gli amministratori possono disabilitare il clic nei criteri collegamenti sicuri).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-273">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="6cbb5-274">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-274">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="6cbb5-275">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-275">**Start date** and **End date**</span></span>
  - <span data-ttu-id="6cbb5-276">Le azioni di protezione clic disponibili, oltre al valore **consentito** (è stato consentito all'utente di passare all'URL).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-276">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL fare clic su Protection Action View nel rapporto di protezione delle minacce URL](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="6cbb5-278">**URL fare clic su applicazione**: consente di visualizzare il numero di clic URL da applicazioni che supportano collegamenti sicuri:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-278">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="6cbb5-279">**Client di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-279">**Email client**</span></span>
  - <span data-ttu-id="6cbb5-280">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-280">**PowerPoint**</span></span>
  - <span data-ttu-id="6cbb5-281">**Word**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-281">**Word**</span></span>
  - <span data-ttu-id="6cbb5-282">**Excel**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-282">**Excel**</span></span>
  - <span data-ttu-id="6cbb5-283">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-283">**OneNote**</span></span>
  - <span data-ttu-id="6cbb5-284">**Visio**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-284">**Visio**</span></span>
  - <span data-ttu-id="6cbb5-285">**Teams**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-285">**Teams**</span></span>
  - <span data-ttu-id="6cbb5-286">**Altro**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-286">**Other**</span></span>

  <span data-ttu-id="6cbb5-287">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-287">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="6cbb5-288">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-288">**Start date** and **End date**</span></span>
  - <span data-ttu-id="6cbb5-289">Le applicazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-289">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="6cbb5-290">Visualizzazione della tabella dei dettagli per il report sulla protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="6cbb5-290">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="6cbb5-291">Se si fa clic su **Visualizza tabella dettagli**, il rapporto fornisce una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 7 giorni con i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-291">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="6cbb5-292">**Fare clic su tempo**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-292">**Click time**</span></span>
- <span data-ttu-id="6cbb5-293">**Utente**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-293">**User**</span></span>
- <span data-ttu-id="6cbb5-294">**URL**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-294">**URL**</span></span>
- <span data-ttu-id="6cbb5-295">**Azione**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-295">**Action**</span></span>
- <span data-ttu-id="6cbb5-296">**App**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-296">**App**</span></span>

<span data-ttu-id="6cbb5-297">Se si fa clic su **filtri** nella visualizzazione tabella dettagli, è possibile filtrare in base agli stessi criteri della visualizzazione report, nonché ai **domini** o ai **destinatari** separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-297">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="6cbb5-298">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-298">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="6cbb5-299">Report aggiuntivi da visualizzare</span><span class="sxs-lookup"><span data-stu-id="6cbb5-299">Additional reports to view</span></span>

<span data-ttu-id="6cbb5-300">Oltre ai rapporti descritti in questo articolo, sono disponibili diversi altri report, come descritto nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-300">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="6cbb5-301">Report</span><span class="sxs-lookup"><span data-stu-id="6cbb5-301">Report</span></span>|<span data-ttu-id="6cbb5-302">Argomento</span><span class="sxs-lookup"><span data-stu-id="6cbb5-302">Topic</span></span>|
|---|---|
|<span data-ttu-id="6cbb5-303">**Explorer** (Microsoft Defender per Office 365 piano 2) o **rilevamenti in tempo reale** (microsoft Defender per Office 365 piano 1)</span><span class="sxs-lookup"><span data-stu-id="6cbb5-303">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="6cbb5-304">Esplora minacce (e rilevamenti in tempo reale)</span><span class="sxs-lookup"><span data-stu-id="6cbb5-304">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="6cbb5-305">Report di **protezione della posta elettronica**, ad esempio il report mittenti e destinatari principali, il report di posta indesiderata e il rapporto rilevamenti di spam.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-305">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="6cbb5-306">Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="6cbb5-306">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="6cbb5-307">**Rapporti sul flusso di posta**, ad esempio il rapporto di inoltro, il rapporto sullo stato del flusso di messaggi e il report mittenti e destinatari principali.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-307">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="6cbb5-308">Visualizzare i report sul flusso di posta elettronica nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="6cbb5-308">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="6cbb5-309">**Traccia URL per i collegamenti sicuri** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-309">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="6cbb5-310">L'output di questo cmdlet consente di visualizzare i risultati delle azioni relative ai collegamenti sicuri negli ultimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-310">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="6cbb5-311">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="6cbb5-311">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="6cbb5-312">**Risultati del traffico di posta elettronica per EOP e Microsoft Defender per Office 365** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-312">**Mail traffic results for EOP and Microsoft Defender for Office 365** (PowerShell only).</span></span> <span data-ttu-id="6cbb5-313">L'output di questo cmdlet contiene informazioni sul dominio, la data, il tipo di evento, la direzione, l'azione e il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-313">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="6cbb5-314">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="6cbb5-314">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="6cbb5-315">**Report Dettagli posta per i rilevamenti di EOP e Defender per Office 365** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-315">**Mail detail reports for EOP and Defender for Office 365 detections** (PowerShell only).</span></span> <span data-ttu-id="6cbb5-316">L'output di questo cmdlet contiene informazioni dettagliate su file o URL dannosi, tentativi di phishing, rappresentazione e altre potenziali minacce nei messaggi di posta elettronica o nei file.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-316">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="6cbb5-317">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="6cbb5-317">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="6cbb5-318">Quali autorizzazioni sono necessarie per visualizzare i report del difensore per Office 365?</span><span class="sxs-lookup"><span data-stu-id="6cbb5-318">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="6cbb5-319">Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel centro sicurezza & Compliance:</span><span class="sxs-lookup"><span data-stu-id="6cbb5-319">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="6cbb5-320">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-320">**Organization Management**</span></span>
- <span data-ttu-id="6cbb5-321">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-321">**Security Administrator**</span></span>
- <span data-ttu-id="6cbb5-322">**Lettore di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-322">**Security Reader**</span></span>
- <span data-ttu-id="6cbb5-323">**Lettore globale**</span><span class="sxs-lookup"><span data-stu-id="6cbb5-323">**Global Reader**</span></span>

<span data-ttu-id="6cbb5-324">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-324">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="6cbb5-325">**Nota**: l'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro sicurezza & Compliance _e_ le autorizzazioni per altre caratteristiche in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-325">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6cbb5-326">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-326">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="6cbb5-327">Cosa succede se i rapporti non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="6cbb5-327">What if the reports aren't showing data?</span></span>

<span data-ttu-id="6cbb5-328">Se i dati non vengono visualizzati nei report di Defender per Office 365, verificare che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-328">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="6cbb5-329">L'organizzazione deve disporre di criteri per i [collegamenti sicuri](set-up-atp-safe-links-policies.md) e di [criteri degli allegati sicuri](set-up-atp-safe-attachments-policies.md) definiti in modo che il difensore per la protezione di Office 365 sia sul posto.</span><span class="sxs-lookup"><span data-stu-id="6cbb5-329">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="6cbb5-330">Vedere anche [protezione dalla posta indesiderata e anti-malware](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="6cbb5-330">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6cbb5-331">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6cbb5-331">Related topics</span></span>

[<span data-ttu-id="6cbb5-332">Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="6cbb5-332">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="6cbb5-333">Autorizzazioni ruolo (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6cbb5-333">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
