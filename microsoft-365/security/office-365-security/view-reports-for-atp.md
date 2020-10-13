---
title: Visualizzare i report per Advanced Threat Protection
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
description: Trovare e utilizzare i report per Office 365 Advanced Threat Protection nel centro sicurezza e &amp; conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e2bb4b0248294589b3e6e7a1a095e4f63d47d8e2
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446300"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="d4e31-103">Visualizzare i report per Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d4e31-103">View reports for Office 365 Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d4e31-104">Le organizzazioni di Office 365 Advanced Threat Protection (ATP) (ad esempio, gli abbonamenti Microsoft 365 E5 o i componenti aggiuntivi ATP Plan 1 o ATP Plan 2) contengono una serie di report relativi alla sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d4e31-104">Office 365 Advanced Threat Protection (ATP) organizations (for example, Microsoft 365 E5 subscriptions or ATP Plan 1 or ATP Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="d4e31-105">Se si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-the-atp-reports), è possibile visualizzare i report nel centro sicurezza & Compliance accedendo al **Reports** \> **Dashboard**report.</span><span class="sxs-lookup"><span data-stu-id="d4e31-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="d4e31-106">Per accedere direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="d4e31-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard dei report nel centro sicurezza & Compliance](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a><span data-ttu-id="d4e31-108">Report sui tipi di file di protezione avanzata delle minacce</span><span class="sxs-lookup"><span data-stu-id="d4e31-108">Advanced Threat Protection file types report</span></span>

<span data-ttu-id="d4e31-109">Il rapporto **report sui tipi di file di protezione avanzata delle minacce** indica il tipo di file che sono stati rilevati come dannosi dagli [allegati sicuri](atp-safe-attachments.md).</span><span class="sxs-lookup"><span data-stu-id="d4e31-109">The **Advanced Threat Protection file types report** report shows you the type of files detected as malicious by [Safe Attachments](atp-safe-attachments.md).</span></span>

 <span data-ttu-id="d4e31-110">La visualizzazione aggregazione del report consente 90 giorni di filtraggio, mentre la visualizzazione dettagli consente solo 10 giorni di filtraggio.</span><span class="sxs-lookup"><span data-stu-id="d4e31-110">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for 10 days of filtering.</span></span>

<span data-ttu-id="d4e31-111">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **tipi di file ATP di Office**.</span><span class="sxs-lookup"><span data-stu-id="d4e31-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP file types**.</span></span> <span data-ttu-id="d4e31-112">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ATPFileReport> .</span><span class="sxs-lookup"><span data-stu-id="d4e31-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPFileReport>.</span></span>

![Widget tipi di file ATP di Office nel dashboard dei report](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> <span data-ttu-id="d4e31-114">Le informazioni contenute in questo report sono disponibili anche nel [report Advanced Threat Protection Message Disposition](#advanced-threat-protection-message-disposition-report).</span><span class="sxs-lookup"><span data-stu-id="d4e31-114">The information in this report is also available in the [Advanced Threat Protection message disposition report](#advanced-threat-protection-message-disposition-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="d4e31-115">Visualizzazione report per il rapporto tipi di file di protezione avanzata dalle minacce</span><span class="sxs-lookup"><span data-stu-id="d4e31-115">Report view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="d4e31-116">Sono disponibili le visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-116">The following views are available:</span></span>

- <span data-ttu-id="d4e31-117">**Visualizzare i dati per: file**: il grafico contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-117">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="d4e31-118">**Allegati di Excel dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-118">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="d4e31-119">**Allegati Flash dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-119">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="d4e31-120">**Allegati PDF dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-120">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="d4e31-121">**Allegati di PowerPoint dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-121">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="d4e31-122">**URL dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-122">**Malicious URLs**</span></span>
  - <span data-ttu-id="d4e31-123">**Allegati di Word dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-123">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="d4e31-124">**Allegati eseguibili dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-124">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="d4e31-125">**Altri**</span><span class="sxs-lookup"><span data-stu-id="d4e31-125">**Others**</span></span>

  <span data-ttu-id="d4e31-126">Quando si posiziona il puntatore del mouse su un determinato giorno (punto dati), è possibile visualizzare la ripartizione dei tipi di file dannosi rilevati dagli [allegati sicuri](atp-safe-attachments.md) e dalla [protezione antimalware in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="d4e31-126">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Visualizzazione file nel rapporto tipi di file ATP](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="d4e31-128">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-128">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d4e31-129">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d4e31-129">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d4e31-130">Gli stessi valori del tipo di file che sono visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="d4e31-130">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="d4e31-131">**Visualizzazione dei dati per: messaggio**: il grafico contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-131">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="d4e31-132">**Blocca accesso**</span><span class="sxs-lookup"><span data-stu-id="d4e31-132">**Block access**</span></span>
  - <span data-ttu-id="d4e31-133">**Messaggi sostituiti**</span><span class="sxs-lookup"><span data-stu-id="d4e31-133">**Messages replaced**</span></span>
  - <span data-ttu-id="d4e31-134">**Messaggi monitorati**</span><span class="sxs-lookup"><span data-stu-id="d4e31-134">**Messages monitored**</span></span>
  - <span data-ttu-id="d4e31-135">**Sostituito dal recapito dinamico della posta elettronica**: per ulteriori informazioni, vedere [Dynamic Delivery in Safe Attachment Policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="d4e31-135">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Visualizzazione dei messaggi nel rapporto tipi di file ATP](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="d4e31-137">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-137">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d4e31-138">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d4e31-138">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d4e31-139">Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.</span><span class="sxs-lookup"><span data-stu-id="d4e31-139">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a><span data-ttu-id="d4e31-140">Visualizzazione tabella dettagli per il rapporto tipi di file di protezione avanzata dalle minacce</span><span class="sxs-lookup"><span data-stu-id="d4e31-140">Details table view for the Advanced Threat Protection file types report</span></span>

<span data-ttu-id="d4e31-141">Se si fa clic su **Visualizza tabella dettagli**, il rapporto fornisce una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="d4e31-141">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="d4e31-142">Le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="d4e31-142">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d4e31-143">**Visualizzare i dati in base a: file**:</span><span class="sxs-lookup"><span data-stu-id="d4e31-143">**View data by: File**:</span></span>

  - <span data-ttu-id="d4e31-144">**Data**</span><span class="sxs-lookup"><span data-stu-id="d4e31-144">**Date**</span></span>
  - <span data-ttu-id="d4e31-145">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="d4e31-145">**Recipient address**</span></span>
  - <span data-ttu-id="d4e31-146">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="d4e31-146">**Sender address**</span></span>
  - <span data-ttu-id="d4e31-147">**ID messaggio**: disponibile nel campo di intestazione **Message-ID** nell'intestazione del messaggio e deve essere univoco.</span><span class="sxs-lookup"><span data-stu-id="d4e31-147">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="d4e31-148">Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).</span><span class="sxs-lookup"><span data-stu-id="d4e31-148">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  - <span data-ttu-id="d4e31-149">**File**</span><span class="sxs-lookup"><span data-stu-id="d4e31-149">**File**</span></span>

  <span data-ttu-id="d4e31-150">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-150">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d4e31-151">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d4e31-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d4e31-152">Gli stessi valori del tipo di file che sono visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="d4e31-152">The same file type values that are visible in the chart.</span></span>

- <span data-ttu-id="d4e31-153">**Visualizzare i dati per: messaggio**:</span><span class="sxs-lookup"><span data-stu-id="d4e31-153">**View data by: Message**:</span></span>

  - <span data-ttu-id="d4e31-154">**Data**</span><span class="sxs-lookup"><span data-stu-id="d4e31-154">**Date**</span></span>
  - <span data-ttu-id="d4e31-155">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="d4e31-155">**Recipient address**</span></span>
  - <span data-ttu-id="d4e31-156">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="d4e31-156">**Sender address**</span></span>
  - <span data-ttu-id="d4e31-157">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="d4e31-157">**Message ID**</span></span>
  - <span data-ttu-id="d4e31-158">**File**</span><span class="sxs-lookup"><span data-stu-id="d4e31-158">**File**</span></span>
  - <span data-ttu-id="d4e31-159">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="d4e31-159">**Subject**</span></span>

  <span data-ttu-id="d4e31-160">Se si fa clic su **filtri**, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-160">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="d4e31-161">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d4e31-161">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d4e31-162">Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.</span><span class="sxs-lookup"><span data-stu-id="d4e31-162">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

<span data-ttu-id="d4e31-163">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="d4e31-163">To get back to the reports view, click **View report**.</span></span>

## <a name="advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="d4e31-164">Report eliminazione messaggi di protezione avanzata delle minacce</span><span class="sxs-lookup"><span data-stu-id="d4e31-164">Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="d4e31-165">Il rapporto di **disposizione dei messaggi ATP** indica le azioni eseguite per i messaggi di posta elettronica rilevati come contenuti dannosi.</span><span class="sxs-lookup"><span data-stu-id="d4e31-165">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span>

<span data-ttu-id="d4e31-166">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** report e selezionare **disposizione dei messaggi ATP di Office**.</span><span class="sxs-lookup"><span data-stu-id="d4e31-166">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Office ATP message disposition**.</span></span> <span data-ttu-id="d4e31-167">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ATPMessageReport> .</span><span class="sxs-lookup"><span data-stu-id="d4e31-167">To go directly to the report, open <https://protection.office.com/reportv2?id=ATPMessageReport>.</span></span>

![Widget disposizione dei messaggi ATP di Office 365 nel dashboard report](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> <span data-ttu-id="d4e31-169">Le informazioni contenute in questo report sono disponibili anche nel [rapporto sui tipi di file di protezione avanzata dalle minacce](#advanced-threat-protection-file-types-report).</span><span class="sxs-lookup"><span data-stu-id="d4e31-169">The information in this report is also available in the [Advanced Threat Protection file types report](#advanced-threat-protection-file-types-report).</span></span>

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="d4e31-170">Visualizzazione report per il rapporto di disposizione dei messaggi per la protezione avanzata dalle minacce</span><span class="sxs-lookup"><span data-stu-id="d4e31-170">Report view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="d4e31-171">Sono disponibili le visualizzazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-171">The following views are available:</span></span>

- <span data-ttu-id="d4e31-172">**Visualizzazione dei dati per: messaggio**: il grafico contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-172">**View data by: Message**: The chart contains the following information:</span></span>

  - <span data-ttu-id="d4e31-173">**Blocca accesso**</span><span class="sxs-lookup"><span data-stu-id="d4e31-173">**Block access**</span></span>
  - <span data-ttu-id="d4e31-174">**Messaggi sostituiti**</span><span class="sxs-lookup"><span data-stu-id="d4e31-174">**Messages replaced**</span></span>
  - <span data-ttu-id="d4e31-175">**Messaggi monitorati**</span><span class="sxs-lookup"><span data-stu-id="d4e31-175">**Messages monitored**</span></span>
  - <span data-ttu-id="d4e31-176">**Sostituito dal recapito dinamico della posta elettronica**: per ulteriori informazioni, vedere [Dynamic Delivery in Safe Attachment Policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span><span class="sxs-lookup"><span data-stu-id="d4e31-176">**Replaced by Dynamic Email Delivery**: For more information, see [Dynamic Delivery in Safe Attachments policies](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).</span></span>

  ![Visualizzazione dei messaggi nel rapporto tipi di file ATP](../../media/atp-file-types-report-message-view.png)

  <span data-ttu-id="d4e31-178">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-178">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d4e31-179">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d4e31-179">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d4e31-180">Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.</span><span class="sxs-lookup"><span data-stu-id="d4e31-180">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="d4e31-181">**Visualizzare i dati per: file**: il grafico contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-181">**View data by: File**: The chart contains the following information:</span></span>

  - <span data-ttu-id="d4e31-182">**Allegati di Excel dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-182">**Malicious Excel attachments**</span></span>
  - <span data-ttu-id="d4e31-183">**Allegati Flash dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-183">**Malicious Flash attachments**</span></span>
  - <span data-ttu-id="d4e31-184">**Allegati PDF dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-184">**Malicious PDF attachments**</span></span>
  - <span data-ttu-id="d4e31-185">**Allegati di PowerPoint dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-185">**Malicious PowerPoint attachments**</span></span>
  - <span data-ttu-id="d4e31-186">**URL dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-186">**Malicious URLs**</span></span>
  - <span data-ttu-id="d4e31-187">**Allegati di Word dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-187">**Malicious Word attachments**</span></span>
  - <span data-ttu-id="d4e31-188">**Allegati eseguibili dannosi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-188">**Malicious executable attachments**</span></span>
  - <span data-ttu-id="d4e31-189">**Altri**</span><span class="sxs-lookup"><span data-stu-id="d4e31-189">**Others**</span></span>

  <span data-ttu-id="d4e31-190">Quando si posiziona il puntatore del mouse su un determinato giorno (punto dati), è possibile visualizzare la ripartizione dei tipi di file dannosi rilevati dagli [allegati sicuri](atp-safe-attachments.md) e dalla [protezione antimalware in EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="d4e31-190">When you hover over a particular day (data point), you can see the breakdown of types of malicious files that were detected by [Safe Attachments](atp-safe-attachments.md) and [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

  ![Visualizzazione file nel rapporto tipi di file ATP](../../media/atp-file-types-report-file-view.png)

  <span data-ttu-id="d4e31-192">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-192">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d4e31-193">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d4e31-193">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d4e31-194">Gli stessi valori del tipo di file che sono visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="d4e31-194">The same file type values that are visible in the chart.</span></span>

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a><span data-ttu-id="d4e31-195">Visualizzazione della tabella Details per il rapporto disposizione dei messaggi per la protezione avanzata dalle minacce</span><span class="sxs-lookup"><span data-stu-id="d4e31-195">Details table view for the Advanced Threat Protection message disposition report</span></span>

<span data-ttu-id="d4e31-196">Se si fa clic su **Visualizza tabella dettagli**, il rapporto fornisce una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 10 giorni.</span><span class="sxs-lookup"><span data-stu-id="d4e31-196">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 10 days.</span></span> <span data-ttu-id="d4e31-197">Le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="d4e31-197">The information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d4e31-198">**Visualizzare i dati per: messaggio**:</span><span class="sxs-lookup"><span data-stu-id="d4e31-198">**View data by: Message**:</span></span>

  - <span data-ttu-id="d4e31-199">**Data**</span><span class="sxs-lookup"><span data-stu-id="d4e31-199">**Date**</span></span>
  - <span data-ttu-id="d4e31-200">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="d4e31-200">**Recipient address**</span></span>
  - <span data-ttu-id="d4e31-201">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="d4e31-201">**Sender address**</span></span>
  - <span data-ttu-id="d4e31-202">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="d4e31-202">**Message ID**</span></span>
  - <span data-ttu-id="d4e31-203">**File**</span><span class="sxs-lookup"><span data-stu-id="d4e31-203">**File**</span></span>
  - <span data-ttu-id="d4e31-204">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="d4e31-204">**Subject**</span></span>

  <span data-ttu-id="d4e31-205">Se si fa clic su **filtri**, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-205">If you click **Filters**, you can modify the results with the following filters:</span></span>

  - <span data-ttu-id="d4e31-206">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d4e31-206">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d4e31-207">Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.</span><span class="sxs-lookup"><span data-stu-id="d4e31-207">The same message disposition values that are available in the chart, and the additional **Messages passed** value.</span></span>

- <span data-ttu-id="d4e31-208">**Visualizzare i dati in base a: file**:</span><span class="sxs-lookup"><span data-stu-id="d4e31-208">**View data by: File**:</span></span>

  - <span data-ttu-id="d4e31-209">**Data**</span><span class="sxs-lookup"><span data-stu-id="d4e31-209">**Date**</span></span>
  - <span data-ttu-id="d4e31-210">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="d4e31-210">**Recipient address**</span></span>
  - <span data-ttu-id="d4e31-211">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="d4e31-211">**Sender address**</span></span>
  - <span data-ttu-id="d4e31-212">**ID messaggio**</span><span class="sxs-lookup"><span data-stu-id="d4e31-212">**Message ID**</span></span>
  - <span data-ttu-id="d4e31-213">**File**</span><span class="sxs-lookup"><span data-stu-id="d4e31-213">**File**</span></span>

  <span data-ttu-id="d4e31-214">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-214">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d4e31-215">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d4e31-215">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d4e31-216">Gli stessi valori del tipo di file che sono visibili nel grafico.</span><span class="sxs-lookup"><span data-stu-id="d4e31-216">The same file type values that are visible in the chart.</span></span>

<span data-ttu-id="d4e31-217">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="d4e31-217">To get back to the reports view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="d4e31-218">Report dello stato di protezione dalle minacce</span><span class="sxs-lookup"><span data-stu-id="d4e31-218">Threat protection status report</span></span>

<span data-ttu-id="d4e31-219">Il rapporto **sullo stato della protezione dalle minacce** è una singola visualizzazione che raggruppa informazioni su contenuto dannoso e messaggi di posta elettronica dannosi rilevati e bloccati da [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) e Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="d4e31-219">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Office 365 ATP.</span></span> <span data-ttu-id="d4e31-220">Per ulteriori informazioni, vedere [rapporto sullo stato della protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="d4e31-220">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="d4e31-221">Report sulla protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="d4e31-221">URL threat protection report</span></span>

<span data-ttu-id="d4e31-222">Il **rapporto di protezione** per gli URL fornisce visualizzazioni di riepilogo e di tendenza per le minacce rilevate e le azioni eseguite su clic URL come parte dei [collegamenti sicuri](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="d4e31-222">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="d4e31-223">Questo report non displicherà i dati da parte degli utenti a cui è stato applicato il criterio collegamenti sicuri ha l'opzione non **registrare i clic utente** selezionati.</span><span class="sxs-lookup"><span data-stu-id="d4e31-223">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="d4e31-224">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** report e selezionare **rapporto protezione URL**.</span><span class="sxs-lookup"><span data-stu-id="d4e31-224">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **URL protection report**.</span></span> <span data-ttu-id="d4e31-225">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=URLProtectionActionReport> .</span><span class="sxs-lookup"><span data-stu-id="d4e31-225">To go directly to the report, open <https://protection.office.com/reportv2?id=URLProtectionActionReport>.</span></span>

![Widget report di protezione URL nel dashboard report](../../media/url-protection-report-widget.png)

> [!NOTE]
> <span data-ttu-id="d4e31-227">Si tratta di un *report di tendenza di protezione*, in cui i dati rappresentano le tendenze di un DataSet più grande.</span><span class="sxs-lookup"><span data-stu-id="d4e31-227">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="d4e31-228">Di conseguenza, i dati nella visualizzazione aggregata non sono disponibili in tempo reale qui, ma i dati nella visualizzazione tabella dettagli sono, pertanto è possibile che si verifichi una leggera discrepanza tra le due visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="d4e31-228">As a result, the data in the aggregate view is not available in real time here, but the data in the details table view is, so you may see a slight discrepancy between the two views.</span></span>

### <a name="report-view-for-the-url-threat-protection-report"></a><span data-ttu-id="d4e31-229">Visualizzazione report per il report di protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="d4e31-229">Report view for the URL threat protection report</span></span>

<span data-ttu-id="d4e31-230">Il report di **protezione dalle minacce URL** contiene due visualizzazioni aggregate aggiornate ogni quattro ore che mostrano i dati per gli ultimi 90 giorni:</span><span class="sxs-lookup"><span data-stu-id="d4e31-230">The **URL threat protection** report has two aggregated views that are refreshed once every four hours that shows data for the last 90 days:</span></span>

- <span data-ttu-id="d4e31-231">**Azione di protezione clic su URL**: Visualizza il numero di clic URL degli utenti nell'organizzazione e i risultati del clic:</span><span class="sxs-lookup"><span data-stu-id="d4e31-231">**URL click protection action**: Shows the number of URL clicks by users in the organization and the results of the click:</span></span>

  - <span data-ttu-id="d4e31-232">**Bloccato** (l'utente è stato bloccato dall'esplorazione all'URL)</span><span class="sxs-lookup"><span data-stu-id="d4e31-232">**Blocked** (the user was blocked from navigating to the URL)</span></span>
  - <span data-ttu-id="d4e31-233">**Bloccato e selezionato tramite**</span><span class="sxs-lookup"><span data-stu-id="d4e31-233">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="d4e31-234">**Fare clic su di esso durante l'analisi**</span><span class="sxs-lookup"><span data-stu-id="d4e31-234">**Clicked through during scan**</span></span>

  <span data-ttu-id="d4e31-235">Un clic indica che l'utente ha fatto clic sulla pagina blocca nel sito Web dannoso (gli amministratori possono disabilitare il clic nei criteri collegamenti sicuri).</span><span class="sxs-lookup"><span data-stu-id="d4e31-235">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

  <span data-ttu-id="d4e31-236">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-236">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d4e31-237">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d4e31-237">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d4e31-238">Le azioni di protezione clic disponibili, oltre al valore **consentito** (è stato consentito all'utente di passare all'URL).</span><span class="sxs-lookup"><span data-stu-id="d4e31-238">The available click protection actions, plus the value **Allowed** (the user was allowed to navigate to the URL).</span></span>

  ![URL fare clic su Protection Action View nel rapporto di protezione delle minacce URL](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- <span data-ttu-id="d4e31-240">**URL fare clic su applicazione**: consente di visualizzare il numero di clic URL da applicazioni che supportano collegamenti sicuri:</span><span class="sxs-lookup"><span data-stu-id="d4e31-240">**URL click by application**: Shows the number of URL clicks by applications that support Safe Links:</span></span>

  - <span data-ttu-id="d4e31-241">**Client di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d4e31-241">**Email client**</span></span>
  - <span data-ttu-id="d4e31-242">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="d4e31-242">**PowerPoint**</span></span>
  - <span data-ttu-id="d4e31-243">**Word**</span><span class="sxs-lookup"><span data-stu-id="d4e31-243">**Word**</span></span>
  - <span data-ttu-id="d4e31-244">**Excel**</span><span class="sxs-lookup"><span data-stu-id="d4e31-244">**Excel**</span></span>
  - <span data-ttu-id="d4e31-245">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="d4e31-245">**OneNote**</span></span>
  - <span data-ttu-id="d4e31-246">**Visio**</span><span class="sxs-lookup"><span data-stu-id="d4e31-246">**Visio**</span></span>
  - <span data-ttu-id="d4e31-247">**Teams**</span><span class="sxs-lookup"><span data-stu-id="d4e31-247">**Teams**</span></span>
  - <span data-ttu-id="d4e31-248">**Altro**</span><span class="sxs-lookup"><span data-stu-id="d4e31-248">**Other**</span></span>

  <span data-ttu-id="d4e31-249">Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-249">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="d4e31-250">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d4e31-250">**Start date** and **End date**</span></span>
  - <span data-ttu-id="d4e31-251">Le applicazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="d4e31-251">The available applications.</span></span>

### <a name="details-table-view-for-the-url-threat-protection-report"></a><span data-ttu-id="d4e31-252">Visualizzazione della tabella dei dettagli per il report sulla protezione dalle minacce URL</span><span class="sxs-lookup"><span data-stu-id="d4e31-252">Details table view for the URL threat protection report</span></span>

<span data-ttu-id="d4e31-253">Se si fa clic su **Visualizza tabella dettagli**, il rapporto fornisce una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 7 giorni con i seguenti dettagli:</span><span class="sxs-lookup"><span data-stu-id="d4e31-253">If you click **View details table**, the report provides a near-real-time view of all clicks that happen within the organization for the last 7 days with the following details:</span></span>

- <span data-ttu-id="d4e31-254">**Fare clic su tempo**</span><span class="sxs-lookup"><span data-stu-id="d4e31-254">**Click time**</span></span>
- <span data-ttu-id="d4e31-255">**Utente**</span><span class="sxs-lookup"><span data-stu-id="d4e31-255">**User**</span></span>
- <span data-ttu-id="d4e31-256">**URL**</span><span class="sxs-lookup"><span data-stu-id="d4e31-256">**URL**</span></span>
- <span data-ttu-id="d4e31-257">**Azione**</span><span class="sxs-lookup"><span data-stu-id="d4e31-257">**Action**</span></span>
- <span data-ttu-id="d4e31-258">**App**</span><span class="sxs-lookup"><span data-stu-id="d4e31-258">**App**</span></span>

<span data-ttu-id="d4e31-259">Se si fa clic su **filtri** nella visualizzazione tabella dettagli, è possibile filtrare in base agli stessi criteri della visualizzazione report, nonché ai **domini** o ai **destinatari** separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="d4e31-259">If you click **Filters** in the details table view, you can filter by the same criteria as in the report view, and also by **Domains** or **Recipients** separated by commas.</span></span>

<span data-ttu-id="d4e31-260">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="d4e31-260">To get back to the reports view, click **View report**.</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="d4e31-261">Report aggiuntivi da visualizzare</span><span class="sxs-lookup"><span data-stu-id="d4e31-261">Additional reports to view</span></span>

<span data-ttu-id="d4e31-262">Oltre ai report ATP descritti in questo argomento, sono disponibili diversi altri report, come descritto nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="d4e31-262">In addition to the ATP reports described in this topic, several other reports are available, as described in the following table:</span></span>

****

|<span data-ttu-id="d4e31-263">Report</span><span class="sxs-lookup"><span data-stu-id="d4e31-263">Report</span></span>|<span data-ttu-id="d4e31-264">Argomento</span><span class="sxs-lookup"><span data-stu-id="d4e31-264">Topic</span></span>|
|---|---|
|<span data-ttu-id="d4e31-265">**Explorer** (ATP piano 2) o **rilevamenti in tempo reale** (ATP piano 1)</span><span class="sxs-lookup"><span data-stu-id="d4e31-265">**Explorer** (ATP Plan 2) or **real-time detections** (ATP Plan 1)</span></span>|[<span data-ttu-id="d4e31-266">Esplora minacce (e rilevamenti in tempo reale)</span><span class="sxs-lookup"><span data-stu-id="d4e31-266">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="d4e31-267">Report di **protezione della posta elettronica**, ad esempio il report mittenti e destinatari principali, il report di posta indesiderata e il rapporto rilevamenti di spam.</span><span class="sxs-lookup"><span data-stu-id="d4e31-267">**Email security reports**, such as the Top senders and recipients report, the Spoof mail report, and the Spam detections report.</span></span>|[<span data-ttu-id="d4e31-268">Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="d4e31-268">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="d4e31-269">**Rapporti sul flusso di posta**, ad esempio il rapporto di inoltro, il rapporto sullo stato del flusso di messaggi e il report mittenti e destinatari principali.</span><span class="sxs-lookup"><span data-stu-id="d4e31-269">**Mail flow reports**, such as the Forwarding report, the Mailflow status report, and the Top senders and recipients report.</span></span>|[<span data-ttu-id="d4e31-270">Visualizzare i report sul flusso di posta elettronica nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="d4e31-270">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)|
|<span data-ttu-id="d4e31-271">**Traccia URL per i collegamenti sicuri** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="d4e31-271">**URL trace for Safe Links** (PowerShell only).</span></span> <span data-ttu-id="d4e31-272">L'output di questo cmdlet consente di visualizzare i risultati delle azioni relative ai collegamenti sicuri negli ultimi sette giorni.</span><span class="sxs-lookup"><span data-stu-id="d4e31-272">The output of this cmdlet shows you the results of Safe Links actions over the past seven days.</span></span>|[<span data-ttu-id="d4e31-273">Get-UrlTrace</span><span class="sxs-lookup"><span data-stu-id="d4e31-273">Get-UrlTrace</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|<span data-ttu-id="d4e31-274">**Risultati del traffico di posta elettronica per EOP e ATP** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="d4e31-274">**Mail traffic results for EOP and ATP** (PowerShell only).</span></span> <span data-ttu-id="d4e31-275">L'output di questo cmdlet contiene informazioni sul dominio, la data, il tipo di evento, la direzione, l'azione e il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="d4e31-275">The output of this cmdlet contains information about Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>|[<span data-ttu-id="d4e31-276">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="d4e31-276">Get-MailTrafficATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|<span data-ttu-id="d4e31-277">**Report Dettagli posta per i rilevamenti di EOP e ATP** (solo PowerShell).</span><span class="sxs-lookup"><span data-stu-id="d4e31-277">**Mail detail reports for EOP and ATP detections** (PowerShell only).</span></span> <span data-ttu-id="d4e31-278">L'output di questo cmdlet contiene informazioni dettagliate su file o URL dannosi, tentativi di phishing, rappresentazione e altre potenziali minacce nei messaggi di posta elettronica o nei file.</span><span class="sxs-lookup"><span data-stu-id="d4e31-278">The output of this cmdlet contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>|[<span data-ttu-id="d4e31-279">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="d4e31-279">Get-MailDetailATPReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="d4e31-280">Quali autorizzazioni sono necessarie per visualizzare i report ATP?</span><span class="sxs-lookup"><span data-stu-id="d4e31-280">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="d4e31-281">Per visualizzare e utilizzare i report descritti in questo argomento, **è necessario che sia assegnato un ruolo appropriato per il &amp; Centro sicurezza e l'interfaccia di amministrazione di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="d4e31-281">In order to view and use the reports described in this topic, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="d4e31-282">Per il Centro sicurezza & conformità, è necessario che sia assegnato uno dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-282">For the Security & Compliance Center, you must have one of the following roles assigned:</span></span>

  - <span data-ttu-id="d4e31-283">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="d4e31-283">Organization Management</span></span>
  - <span data-ttu-id="d4e31-284">Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="d4e31-284">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="d4e31-285">Operatore di sicurezza (che può essere assegnato nell'interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))</span><span class="sxs-lookup"><span data-stu-id="d4e31-285">Security Operator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
  - <span data-ttu-id="d4e31-286">Ruolo con autorizzazioni di lettura per la sicurezza</span><span class="sxs-lookup"><span data-stu-id="d4e31-286">Security Reader</span></span>

- <span data-ttu-id="d4e31-287">Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span><span class="sxs-lookup"><span data-stu-id="d4e31-287">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):</span></span>

  - <span data-ttu-id="d4e31-288">Gestione organizzazione</span><span class="sxs-lookup"><span data-stu-id="d4e31-288">Organization Management</span></span>
  - <span data-ttu-id="d4e31-289">Gestione organizzazione in sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="d4e31-289">View-only Organization Management</span></span>
  - <span data-ttu-id="d4e31-290">Ruolo Destinatari di sola lettura</span><span class="sxs-lookup"><span data-stu-id="d4e31-290">View-Only Recipients role</span></span>
  - <span data-ttu-id="d4e31-291">Gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="d4e31-291">Compliance Management</span></span>

<span data-ttu-id="d4e31-292">Per altre informazioni, vedere le risorse seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4e31-292">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="d4e31-293">Autorizzazioni nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="d4e31-293">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="d4e31-294">Autorizzazioni funzionalità in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d4e31-294">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="d4e31-295">Cosa succede se i rapporti non mostrano dati?</span><span class="sxs-lookup"><span data-stu-id="d4e31-295">What if the reports aren't showing data?</span></span>

<span data-ttu-id="d4e31-296">Se i dati non vengono visualizzati nei rapporti ATP, verificare che i criteri siano configurati correttamente.</span><span class="sxs-lookup"><span data-stu-id="d4e31-296">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="d4e31-297">L'organizzazione deve disporre di criteri per i [collegamenti sicuri](set-up-atp-safe-links-policies.md) e di [criteri degli allegati sicuri](set-up-atp-safe-attachments-policies.md) definiti in modo che la protezione ATP sia sul posto.</span><span class="sxs-lookup"><span data-stu-id="d4e31-297">Your organization must have [Safe Links policies](set-up-atp-safe-links-policies.md) and [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="d4e31-298">Vedere anche [protezione dalla posta indesiderata e anti-malware](anti-spam-and-anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="d4e31-298">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d4e31-299">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d4e31-299">Related topics</span></span>

[<span data-ttu-id="d4e31-300">Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="d4e31-300">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="d4e31-301">Autorizzazioni ruolo (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d4e31-301">Role permissions (Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
