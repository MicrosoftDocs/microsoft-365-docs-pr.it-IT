---
title: Visualizzare i report per Advanced Threat Protection
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Trovare e utilizzare i report per Office 365 Advanced Threat Protection nel centro sicurezza e &amp; conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16fef101f722a23b3a64d91c85c2f946c67036f0
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328035"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="ba8a8-103">Visualizzare i report per Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ba8a8-103">View reports for Office 365 Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ba8a8-104">Le organizzazioni di Office 365 Advanced Threat Protection (ATP) (ad esempio, gli abbonamenti Microsoft 365 E5 o i componenti aggiuntivi ATP Plan 1 o ATP Plan 2) contengono una serie di report relativi alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-104">Office 365 Advanced Threat Protection (ATP) organizations (for example, Microsoft 365 E5 subscriptions or ATP Plan 1 or ATP Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="ba8a8-105">Se si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-the-atp-reports), è possibile visualizzare i report nel centro sicurezza & Compliance accedendo al **Reports** \> **Dashboard**report.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="ba8a8-106">Per accedere direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="ba8a8-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard dei report nel centro sicurezza & Compliance](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a><span data-ttu-id="ba8a8-108">Report sui tipi di file di protezione avanzata delle minacce</span><span class="sxs-lookup"><span data-stu-id="ba8a8-108">Advanced Threat Protection file types report</span></span>

<span data-ttu-id="ba8a8-109">Il rapporto **report sui tipi di file di protezione avanzata delle minacce** indica il tipo di file che sono stati rilevati come dannosi dagli [allegati sicuri](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-109">The **Advanced Threat Protection file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="ba8a8-110">La visualizzazione aggregazione del report consente 90 giorni di filtraggio, mentre la visualizzazione dettagli consente solo 10 giorni di filtraggio.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="ba8a8-111">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **tipi di file ATP di Office**.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP file types**.</span></span> <span data-ttu-id="ba8a8-112">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="ba8a8-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Widget tipi di file ATP di Office nel dashboard dei report](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="ba8a8-114">Le informazioni contenute in questo report sono disponibili anche nel [report Advanced Threat Protection Message Disposition](#advanced-threat-protection-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-114">The information in this report is also available in the [Advanced Threat Protection message disposition report](#advanced-threat-protection-message-disposition-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="ba8a8-115">Visualizzazione report per il rapporto tipi di file di protezione avanzata dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ba8a8-115">Report view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="ba8a8-116">Sono disponibili le visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-116">The following views are available:</span></span>

- <span data-ttu-id="ba8a8-117">**Visualizzare i dati per: file**: il grafico contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="ba8a8-118">**Allegati di Excel dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="ba8a8-119">**Allegati Flash dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="ba8a8-120">**Allegati PDF dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="ba8a8-121">**Allegati di PowerPoint dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="ba8a8-122">**URL dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="ba8a8-123">**Allegati di Word dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="ba8a8-124">**Allegati eseguibili dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="ba8a8-125">**Altri**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-125">**Others**</span></span>

  <span data-ttu-id="ba8a8-126">Quando si posiziona il puntatore del mouse su un determinato giorno (punto dati), è possibile visualizzare la ripartizione dei tipi di file dannosi rilevati dagli [allegati sicuri](atp-safe-attachments.md) e dalla [protezione antimalware in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Visualizzazione file nel rapporto tipi di file ATP](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="ba8a8-128">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ba8a8-129">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ba8a8-130">Gli stessi valori del tipo di file che sono visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="ba8a8-131">**Visualizzazione dei dati per: messaggio**: il grafico contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="ba8a8-132">**Blocca accesso**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-132">**Block access**</span></span>
  - <span data-ttu-id="ba8a8-133">**Messaggi sostituiti**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-133">**Messages replaced**</span></span>
  - <span data-ttu-id="ba8a8-134">**Messaggi monitorati**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-134">**Messages monitored**</span></span>
  - <span data-ttu-id="ba8a8-135">**Sostituito dal recapito dinamico della posta elettronica**: per ulteriori informazioni, vedere [Dynamic Delivery in Safe Attachment Policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Visualizzazione dei messaggi nel rapporto tipi di file ATP](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="ba8a8-137">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ba8a8-138">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ba8a8-139">Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="ba8a8-140">Visualizzazione tabella dettagli per il rapporto tipi di file di protezione avanzata dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ba8a8-140">Details table view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="ba8a8-141">Se si fa clic su **Visualizza tabella dettagli**, il rapporto fornisce una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="ba8a8-142">Le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ba8a8-143">**Visualizzare i dati in base a: file**:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-143">**View data by: File**:</span></span>

  - <span data-ttu-id="ba8a8-144">**Data**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-144">**Date**</span></span>
  - <span data-ttu-id="ba8a8-145">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-145">**Recipient address**</span></span>
  - <span data-ttu-id="ba8a8-146">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-146">**Sender address**</span></span>
  - <span data-ttu-id="ba8a8-147">**ID messaggio**: disponibile nel campo di intestazione **Message-ID** nell'intestazione del messaggio e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="ba8a8-148">Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="ba8a8-149">**File**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-149">**File**</span></span>

  <span data-ttu-id="ba8a8-150">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ba8a8-151">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ba8a8-152">Gli stessi valori del tipo di file che sono visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="ba8a8-153">**Visualizzare i dati per: messaggio**:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="ba8a8-154">**Data**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-154">**Date**</span></span>
  - <span data-ttu-id="ba8a8-155">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-155">**Recipient address**</span></span>
  - <span data-ttu-id="ba8a8-156">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-156">**Sender address**</span></span>
  - <span data-ttu-id="ba8a8-157">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-157">**Message ID**</span></span>
  - <span data-ttu-id="ba8a8-158">**File**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-158">**File**</span></span>
  - <span data-ttu-id="ba8a8-159">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-159">**Subject**</span></span>

  <span data-ttu-id="ba8a8-160">Se si fa clic su **filtri**, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="ba8a8-161">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ba8a8-162">Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="ba8a8-163">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-163">To get back to the reports view, click **View report**.</span></span>

## <a name="advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="ba8a8-164">Report eliminazione messaggi di protezione avanzata delle minacce</span><span class="sxs-lookup"><span data-stu-id="ba8a8-164">Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="ba8a8-165">Il rapporto di **disposizione dei messaggi ATP** indica le azioni eseguite per i messaggi di posta elettronica rilevati come contenuti dannosi.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="ba8a8-166">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** report e selezionare **disposizione dei messaggi ATP di Office**.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP message disposition**.</span></span> <span data-ttu-id="ba8a8-167">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="ba8a8-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Widget disposizione dei messaggi ATP di Office 365 nel dashboard report](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="ba8a8-169">Le informazioni contenute in questo report sono disponibili anche nel [rapporto sui tipi di file di protezione avanzata dalle minacce](#advanced-threat-protection-file-types-report).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-169">The information in this report is also available in the [Advanced Threat Protection file types report](#advanced-threat-protection-file-types-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="ba8a8-170">Visualizzazione report per il rapporto di disposizione dei messaggi per la protezione avanzata dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ba8a8-170">Report view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="ba8a8-171">Sono disponibili le visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-171">The following views are available:</span></span>

- <span data-ttu-id="ba8a8-172">**Visualizzazione dei dati per: messaggio**: il grafico contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="ba8a8-173">**Blocca accesso**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-173">**Block access**</span></span>
  - <span data-ttu-id="ba8a8-174">**Messaggi sostituiti**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-174">**Messages replaced**</span></span>
  - <span data-ttu-id="ba8a8-175">**Messaggi monitorati**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-175">**Messages monitored**</span></span>
  - <span data-ttu-id="ba8a8-176">**Sostituito dal recapito dinamico della posta elettronica**: per ulteriori informazioni, vedere [Dynamic Delivery in Safe Attachment Policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Visualizzazione dei messaggi nel rapporto tipi di file ATP](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="ba8a8-178">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ba8a8-179">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ba8a8-180">Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="ba8a8-181">**Visualizzare i dati per: file**: il grafico contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="ba8a8-182">**Allegati di Excel dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="ba8a8-183">**Allegati Flash dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="ba8a8-184">**Allegati PDF dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="ba8a8-185">**Allegati di PowerPoint dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="ba8a8-186">**URL dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="ba8a8-187">**Allegati di Word dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="ba8a8-188">**Allegati eseguibili dannosi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="ba8a8-189">**Altri**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-189">**Others**</span></span>

  <span data-ttu-id="ba8a8-190">Quando si posiziona il puntatore del mouse su un determinato giorno (punto dati), è possibile visualizzare la ripartizione dei tipi di file dannosi rilevati dagli [allegati sicuri](atp-safe-attachments.md) e dalla [protezione antimalware in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Visualizzazione file nel rapporto tipi di file ATP](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="ba8a8-192">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ba8a8-193">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ba8a8-194">Gli stessi valori del tipo di file che sono visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="ba8a8-195">Visualizzazione della tabella Details per il rapporto disposizione dei messaggi per la protezione avanzata dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ba8a8-195">Details table view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="ba8a8-196">Se si fa clic su **Visualizza tabella dettagli**, il rapporto fornisce una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="ba8a8-197">Le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="ba8a8-198">**Visualizzare i dati per: messaggio**:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="ba8a8-199">**Data**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-199">**Date**</span></span>
  - <span data-ttu-id="ba8a8-200">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-200">**Recipient address**</span></span>
  - <span data-ttu-id="ba8a8-201">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-201">**Sender address**</span></span>
  - <span data-ttu-id="ba8a8-202">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-202">**Message ID**</span></span>
  - <span data-ttu-id="ba8a8-203">**File**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-203">**File**</span></span>
  - <span data-ttu-id="ba8a8-204">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-204">**Subject**</span></span>

  <span data-ttu-id="ba8a8-205">Se si fa clic su **filtri**, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="ba8a8-206">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ba8a8-207">Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="ba8a8-208">**Visualizzare i dati in base a: file**:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-208">**View data by: File**:</span></span>

  - <span data-ttu-id="ba8a8-209">**Data**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-209">**Date**</span></span>
  - <span data-ttu-id="ba8a8-210">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-210">**Recipient address**</span></span>
  - <span data-ttu-id="ba8a8-211">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-211">**Sender address**</span></span>
  - <span data-ttu-id="ba8a8-212">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-212">**Message ID**</span></span>
  - <span data-ttu-id="ba8a8-213">**File**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-213">**File**</span></span>

  <span data-ttu-id="ba8a8-214">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ba8a8-215">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ba8a8-216">Gli stessi valori del tipo di file che sono visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="ba8a8-217">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="ba8a8-218">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="ba8a8-218">Threat protection status report</span></span>

<span data-ttu-id="ba8a8-219">Il rapporto **sullo stato della protezione dalle minacce** è una singola visualizzazione che raggruppa informazioni su contenuto dannoso e messaggi di posta elettronica dannosi rilevati e bloccati da [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) e Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Office 365 ATP.</span></span> <span data-ttu-id="ba8a8-220">Per ulteriori informazioni, vedere [rapporto sullo stato della protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="ba8a8-221">Report sulla protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="ba8a8-221">URL threat protection report</span></span>

<span data-ttu-id="ba8a8-222">Il **rapporto di protezione** per gli URL fornisce visualizzazioni di riepilogo e di tendenza per le minacce rilevate e le azioni eseguite su clic URL come parte dei [collegamenti sicuri](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="ba8a8-223">Questo report non displicherà i dati da parte degli utenti a cui è stato applicato il criterio collegamenti sicuri ha l'opzione non **registrare i clic utente** selezionati.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="ba8a8-224">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** report e selezionare **rapporto protezione URL**.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="ba8a8-225">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="ba8a8-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widget report di protezione URL nel dashboard report](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="ba8a8-227">Si tratta di un *report di tendenza di protezione*, in cui i dati rappresentano le tendenze di un DataSet più grande.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-227">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="ba8a8-228">Di conseguenza, i dati nella visualizzazione aggregata non sono disponibili in tempo reale qui, ma i dati nella visualizzazione tabella dettagli sono, pertanto è possibile che si verifichi una leggera discrepanza tra le due visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="ba8a8-229">Visualizzazione report per il report di protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="ba8a8-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="ba8a8-230">Il report di **protezione dalle minacce URL** contiene due visualizzazioni aggregate aggiornate ogni quattro ore che mostrano i dati per gli ultimi 90 giorni:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="ba8a8-231">**Azione di protezione clic su URL**: Visualizza il numero di clic URL degli utenti nell'organizzazione e i risultati del clic:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-231">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="ba8a8-232">**Bloccato** (l'utente è stato bloccato dall'esplorazione all'URL)</span><span class="sxs-lookup"><span data-stu-id="ba8a8-232">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="ba8a8-233">**Bloccato e selezionato tramite**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="ba8a8-234">**Fare clic su di esso durante l'analisi**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="ba8a8-235">Un clic indica che l'utente ha fatto clic sulla pagina blocca nel sito Web dannoso (gli amministratori possono disabilitare il clic nei criteri collegamenti sicuri).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="ba8a8-236">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-236">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ba8a8-237">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ba8a8-238">Le azioni di protezione clic disponibili, oltre al valore **consentito** (è stato consentito all'utente di passare all'URL).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-238">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL fare clic su Protection Action View nel rapporto di protezione delle minacce URL](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="ba8a8-240">**URL fare clic su applicazione**: consente di visualizzare il numero di clic URL da applicazioni che supportano collegamenti sicuri:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-240">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="ba8a8-241">**Client di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-241">**Email client**</span></span>
  - <span data-ttu-id="ba8a8-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-242">**PowerPoint**</span></span>
  - <span data-ttu-id="ba8a8-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-243">**Word**</span></span>
  - <span data-ttu-id="ba8a8-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-244">**Excel**</span></span>
  - <span data-ttu-id="ba8a8-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-245">**OneNote**</span></span>
  - <span data-ttu-id="ba8a8-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-246">**Visio**</span></span>
  - <span data-ttu-id="ba8a8-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-247">**Teams**</span></span>
  - <span data-ttu-id="ba8a8-248">**Altro**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-248">**Other**</span></span>

  <span data-ttu-id="ba8a8-249">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-249">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="ba8a8-250">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="ba8a8-251">Le applicazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="ba8a8-252">Visualizzazione della tabella dei dettagli per il report sulla protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="ba8a8-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="ba8a8-253">Se si fa clic su **Visualizza tabella dettagli**, il rapporto fornisce una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 7 giorni con i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-253">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="ba8a8-254">**Fare clic su tempo**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-254">**Click time**</span></span>
- <span data-ttu-id="ba8a8-255">**Utente**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-255">**User**</span></span>
- <span data-ttu-id="ba8a8-256">**URL**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-256">**URL**</span></span>
- <span data-ttu-id="ba8a8-257">**Azione**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-257">**Action**</span></span>
- <span data-ttu-id="ba8a8-258">**App**</span><span class="sxs-lookup"><span data-stu-id="ba8a8-258">**App**</span></span>

<span data-ttu-id="ba8a8-259">Se si fa clic su **filtri** nella visualizzazione tabella dettagli, è possibile filtrare in base agli stessi criteri della visualizzazione report, nonché ai **domini** o ai **destinatari** separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="ba8a8-260">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="ba8a8-261">Report aggiuntivi da visualizzare</span><span class="sxs-lookup"><span data-stu-id="ba8a8-261">Additional reports to view</span></span>

<span data-ttu-id="ba8a8-262">Oltre ai report ATP descritti in questo argomento, sono disponibili diversi altri report, come descritto nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-262">In addition to the ATP reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="ba8a8-263">Report</span><span class="sxs-lookup"><span data-stu-id="ba8a8-263">Report</span></span>|<span data-ttu-id="ba8a8-264">Argomento</span><span class="sxs-lookup"><span data-stu-id="ba8a8-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="ba8a8-265">**Explorer** (ATP piano 2) o **rilevamenti in tempo reale** (ATP piano 1)</span><span class="sxs-lookup"><span data-stu-id="ba8a8-265">**Explorer** (ATP Plan 2) or **real-time detections** (ATP Plan 1)</span></span>|[<span data-ttu-id="ba8a8-266">Esplora minacce (e rilevamenti in tempo reale)</span><span class="sxs-lookup"><span data-stu-id="ba8a8-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="ba8a8-267">Report di **protezione della posta elettronica**, ad esempio il report mittenti e destinatari principali, il report di posta indesiderata e il rapporto rilevamenti di spam.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-267">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="ba8a8-268">Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="ba8a8-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="ba8a8-269">**Rapporti sul flusso di posta**, ad esempio il rapporto di inoltro, il rapporto sullo stato del flusso di messaggi e il report mittenti e destinatari principali.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-269">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="ba8a8-270">Visualizzare i report sul flusso di posta elettronica nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="ba8a8-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="ba8a8-271">**Traccia URL per i collegamenti sicuri** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-271">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="ba8a8-272">L'output di questo cmdlet consente di visualizzare i risultati delle azioni relative ai collegamenti sicuri negli ultimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-272">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="ba8a8-273">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="ba8a8-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="ba8a8-274">**Risultati del traffico di posta elettronica per EOP e ATP** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-274">**Mail traffic results for EOP and ATP** (PowerShell only).</span></span> <span data-ttu-id="ba8a8-275">L'output di questo cmdlet contiene informazioni sul dominio, la data, il tipo di evento, la direzione, l'azione e il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="ba8a8-276">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="ba8a8-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="ba8a8-277">**Report Dettagli posta per i rilevamenti di EOP e ATP** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-277">**Mail detail reports for EOP and ATP detections** (PowerShell only).</span></span> <span data-ttu-id="ba8a8-278">L'output di questo cmdlet contiene informazioni dettagliate su file o URL dannosi, tentativi di phishing, rappresentazione e altre potenziali minacce nei messaggi di posta elettronica o nei file.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="ba8a8-279">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="ba8a8-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="ba8a8-280">Quali autorizzazioni sono necessarie per visualizzare i report ATP?</span><span class="sxs-lookup"><span data-stu-id="ba8a8-280">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="ba8a8-281">Per visualizzare e utilizzare i report descritti in questo argomento, **è necessario che sia assegnato un ruolo appropriato per il &amp; Centro sicurezza e l'interfaccia di amministrazione di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="ba8a8-282">Per il Centro sicurezza & conformità, è necessario che sia assegnato uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="ba8a8-283">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="ba8a8-283">Organization Management</span></span>
  - <span data-ttu-id="ba8a8-284">Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="ba8a8-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="ba8a8-285">Operatore di sicurezza (che può essere assegnato nell'interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="ba8a8-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="ba8a8-286">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="ba8a8-286">Security Reader</span></span>

- <span data-ttu-id="ba8a8-287">Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="ba8a8-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="ba8a8-288">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="ba8a8-288">Organization Management</span></span>
  - <span data-ttu-id="ba8a8-289">Gestione organizzazione in sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="ba8a8-289">View-only Organization Management</span></span>
  - <span data-ttu-id="ba8a8-290">Ruolo Destinatari di sola lettura</span><span class="sxs-lookup"><span data-stu-id="ba8a8-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="ba8a8-291">Gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="ba8a8-291">Compliance Management</span></span>

<span data-ttu-id="ba8a8-292">Per altre informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba8a8-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="ba8a8-293">Autorizzazioni nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="ba8a8-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="ba8a8-294">Autorizzazioni funzionalità in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ba8a8-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="ba8a8-295">Cosa succede se i rapporti non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="ba8a8-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="ba8a8-296">Se i dati non vengono visualizzati nei rapporti ATP, verificare che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-296">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="ba8a8-297">L'organizzazione deve disporre di criteri per i [collegamenti sicuri](set-up-atp-safe-links-policies.md) e di [criteri degli allegati sicuri](set-up-atp-safe-attachments-policies.md) definiti in modo che la protezione ATP sia sul posto.</span><span class="sxs-lookup"><span data-stu-id="ba8a8-297">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="ba8a8-298">Vedere anche [protezione dalla posta indesiderata e anti-malware](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="ba8a8-298">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ba8a8-299">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ba8a8-299">Related topics</span></span>

[<span data-ttu-id="ba8a8-300">Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="ba8a8-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="ba8a8-301">Autorizzazioni ruolo (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ba8a8-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
