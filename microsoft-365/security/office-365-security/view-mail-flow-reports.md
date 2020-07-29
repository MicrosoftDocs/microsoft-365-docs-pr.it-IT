---
title: Visualizzare i report sul flusso di posta nel Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Informazioni su come trovare e utilizzare i rapporti sulla sicurezza del flusso di posta per l'organizzazione. I report del flusso di posta sono disponibili nel centro sicurezza & conformità.
ms.custom: ''
ms.openlocfilehash: e891d9373b169dc01cfd89f114e31b23e1bd8480
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434180"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a><span data-ttu-id="3217d-104">Visualizzare i report sul flusso di posta nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="3217d-104">View mail flow reports in the Security & Compliance Center</span></span>

<span data-ttu-id="3217d-105">Oltre alle informazioni sul [flusso di posta](mail-flow-insights-v2.md) disponibili nel centro sicurezza & conformità, sono disponibili una serie di rapporti sul flusso di posta per facilitare il monitoraggio dell'organizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3217d-105">In addition to the [Mail flow insights](mail-flow-insights-v2.md) that are available in the Security & Compliance Center, a variety of mail flow reports are also available to help you monitor your Microsoft 365 organization.</span></span> <span data-ttu-id="3217d-106">Se si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-these-reports), è possibile visualizzare i report nel centro sicurezza & Compliance <https://office.protection.com> accedendo al dashboard **report** \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="3217d-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center at <https://office.protection.com> by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="3217d-107">Per accedere direttamente al dashboard dei report, aprire <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="3217d-107">To go directly to the reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Dashboard dei report nel centro sicurezza & Compliance](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="3217d-109">Rapporto connettore</span><span class="sxs-lookup"><span data-stu-id="3217d-109">Connector report</span></span>

<span data-ttu-id="3217d-110">Il **rapporto connettore** consente di visualizzare l'attività del flusso di posta sui [connettori in ingresso e in uscita](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) configurati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3217d-110">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="3217d-111">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare il **report del connettore**.</span><span class="sxs-lookup"><span data-stu-id="3217d-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="3217d-112">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="3217d-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget del rapporto del connettore nel dashboard dei report](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="3217d-114">Visualizzazione report per il report del connettore</span><span class="sxs-lookup"><span data-stu-id="3217d-114">Report view for the Connector report</span></span>

<span data-ttu-id="3217d-115">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-115">The following charts are available in report view:</span></span>

- <span data-ttu-id="3217d-116">**Visualizzazione dei dati per: flusso di posta**: questo grafico mostra il numero di messaggi in ingresso e in uscita organizzati da:</span><span class="sxs-lookup"><span data-stu-id="3217d-116">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="3217d-117">**Totale**</span><span class="sxs-lookup"><span data-stu-id="3217d-117">**Total**</span></span>
  - <span data-ttu-id="3217d-118">**Da Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="3217d-118">**From the internet without a connector**</span></span>
  - <span data-ttu-id="3217d-119">**A Internet senza un connettore**</span><span class="sxs-lookup"><span data-stu-id="3217d-119">**To the internet without a connector**</span></span>
  - <span data-ttu-id="3217d-120">Connettore specifico configurato.</span><span class="sxs-lookup"><span data-stu-id="3217d-120">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="3217d-121">Per isolare i dati nel grafico, utilizzare la casella di controllo **Mostra dati per** selezionare una di queste opzioni o **tutto il flusso di posta**.</span><span class="sxs-lookup"><span data-stu-id="3217d-121">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Visualizzare i dati in base al flusso di posta nel rapporto del connettore](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="3217d-123">**Visualizzare i dati in base a: utilizzo TLS**: questo grafico mostra la percentuale di utilizzo della versione TLS (Transport Layer Security) per il flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="3217d-123">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="3217d-124">Per isolare i dati nel grafico, utilizzare il controllo **Mostra dati per** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-124">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="3217d-125">**Tutto il flusso di posta**</span><span class="sxs-lookup"><span data-stu-id="3217d-125">**All mail flow**</span></span>
  - <span data-ttu-id="3217d-126">**Da Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="3217d-126">**From the internet without a connector**</span></span>
  - <span data-ttu-id="3217d-127">**A Internet senza un connettore**</span><span class="sxs-lookup"><span data-stu-id="3217d-127">**To the internet without a connector**</span></span>
  - <span data-ttu-id="3217d-128">Connettore specifico configurato.</span><span class="sxs-lookup"><span data-stu-id="3217d-128">A specific connector that you've configured.</span></span>

  ![Visualizzare i dati in base all'utilizzo di TLS nel report del connettore](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="3217d-130">Se si fa clic su **filtri** in una visualizzazione report, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="3217d-130">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="3217d-131">Visualizzazione della tabella dei dettagli per il report del connettore</span><span class="sxs-lookup"><span data-stu-id="3217d-131">Details table view for the Connector report</span></span>

<span data-ttu-id="3217d-132">Se si fa clic su **Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-132">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="3217d-133">**Data**</span><span class="sxs-lookup"><span data-stu-id="3217d-133">**Date**</span></span>
- <span data-ttu-id="3217d-134">**Direzione e nome del connettore**</span><span class="sxs-lookup"><span data-stu-id="3217d-134">**Connector direction and name**</span></span>
- <span data-ttu-id="3217d-135">**Tipo di connettore**</span><span class="sxs-lookup"><span data-stu-id="3217d-135">**Connector type**</span></span>
- <span data-ttu-id="3217d-136">**TLS forzato**: il valore **true** o **false**.</span><span class="sxs-lookup"><span data-stu-id="3217d-136">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="3217d-137">**Nessun TLS** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="3217d-137">**No TLS** (percentage)</span></span>
- <span data-ttu-id="3217d-138">**TLS 1,0** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="3217d-138">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="3217d-139">**TLS 1,1** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="3217d-139">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="3217d-140">**TLS 1,2** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="3217d-140">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="3217d-141">**Volume**: il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="3217d-141">**Volume**: The number of messages.</span></span>

<span data-ttu-id="3217d-142">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="3217d-142">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="3217d-143">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="3217d-143">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="3217d-144">Rapporto delle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="3217d-144">Exchange transport rule report</span></span>

<span data-ttu-id="3217d-145">Il **rapporto della regola di trasporto di Exchange** indica l'effetto delle regole del flusso di posta (note anche come regole di trasporto) sui messaggi in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3217d-145">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="3217d-146">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **regola di trasporto di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="3217d-146">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="3217d-147">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="3217d-147">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget delle regole di trasporto di Exchange nel dashboard dei report](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="3217d-149">Visualizzazione report per il rapporto delle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="3217d-149">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="3217d-150">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-150">The following charts are available in report view:</span></span>

- <span data-ttu-id="3217d-151">**Visualizzare i dati in base a: regole** \> di trasporto di Exchange **Scomposizione per: direzione**: questo grafico indica il numero di messaggi in **ingresso** e in **uscita** che sono stati interessati dalle regole di trasporto.</span><span class="sxs-lookup"><span data-stu-id="3217d-151">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="3217d-152">**Visualizzare i dati in base a: regole** \> di trasporto di Exchange **Scomposizione in base a: gravità**: questo grafico Visualizza il numero di severità **elevata** e di gravità **media**e messaggi di **gravità insufficienti** .</span><span class="sxs-lookup"><span data-stu-id="3217d-152">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="3217d-153">È possibile impostare il livello di gravità come azione nella regola (**controllare questa regola con livello di gravità** o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="3217d-153">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="3217d-154">Per ulteriori informazioni, vedere [azioni delle regole del flusso di posta in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="3217d-154">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="3217d-155">**Visualizzare i dati in base a: regole di trasporto di Exchange DLP** \> **Scomposizione per: Direction**: questo grafico indica il numero di messaggi in **ingresso** e in **uscita** che sono stati interessati dalle regole di trasporto di prevenzione della perdita di dati (DLP).</span><span class="sxs-lookup"><span data-stu-id="3217d-155">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="3217d-156">È possibile affinare ulteriormente il grafico selezionando le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-156">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="3217d-157">**Mostra dati per: tutte le regole di trasporto DLP**</span><span class="sxs-lookup"><span data-stu-id="3217d-157">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="3217d-158">**Visualizzare i dati per: utenti compromessi**</span><span class="sxs-lookup"><span data-stu-id="3217d-158">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="3217d-159">**Mostra dati per: basso volume di contenuto rilevato US Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="3217d-159">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="3217d-160">**Visualizzare i dati in base a: regole di trasporto di Exchange DLP** \> **Suddividi in base a: Direction**: questa visualizzazione Mostra il numero di gravità **elevata** e di gravità **media**e i messaggi a **bassa severità** che sono stati interessati dalle regole di trasporto DLP.</span><span class="sxs-lookup"><span data-stu-id="3217d-160">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="3217d-161">È possibile affinare ulteriormente il grafico selezionando le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-161">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="3217d-162">**Mostra dati per: tutte le regole di trasporto DLP**</span><span class="sxs-lookup"><span data-stu-id="3217d-162">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="3217d-163">**Visualizzare i dati per: utenti compromessi**</span><span class="sxs-lookup"><span data-stu-id="3217d-163">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="3217d-164">**Mostra dati per: basso volume di contenuto rilevato US Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="3217d-164">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="3217d-165">Se si fa clic su **filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-165">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="3217d-166">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="3217d-166">**Start date** and **End date**</span></span>
- <span data-ttu-id="3217d-167">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="3217d-167">Direction values</span></span>
- <span data-ttu-id="3217d-168">Valori di gravità</span><span class="sxs-lookup"><span data-stu-id="3217d-168">Severity values</span></span>

![Visualizzazione report nel rapporto delle regole di trasporto di Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="3217d-170">Visualizzazione della tabella dei dettagli per il rapporto delle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="3217d-170">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="3217d-171">Se si fa clic su **Visualizza tabella dettagli**, le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="3217d-171">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="3217d-172">**Visualizzare i dati per: regole di trasporto di Exchange**:</span><span class="sxs-lookup"><span data-stu-id="3217d-172">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="3217d-173">**Data**</span><span class="sxs-lookup"><span data-stu-id="3217d-173">**Date**</span></span>
  - <span data-ttu-id="3217d-174">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="3217d-174">**Transport rule**</span></span>
  - <span data-ttu-id="3217d-175">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="3217d-175">**Subject**</span></span>
  - <span data-ttu-id="3217d-176">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="3217d-176">**Sender address**</span></span>
  - <span data-ttu-id="3217d-177">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="3217d-177">**Recipient address**</span></span>
  - <span data-ttu-id="3217d-178">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="3217d-178">**Severity**</span></span>
  - <span data-ttu-id="3217d-179">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="3217d-179">**Direction**</span></span>

- <span data-ttu-id="3217d-180">**Visualizzare i dati in base a: regole di trasporto di Exchange DLP**:</span><span class="sxs-lookup"><span data-stu-id="3217d-180">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="3217d-181">**Data**</span><span class="sxs-lookup"><span data-stu-id="3217d-181">**Date**</span></span>
  - <span data-ttu-id="3217d-182">**Criteri DLP**</span><span class="sxs-lookup"><span data-stu-id="3217d-182">**DLP policy**</span></span>
  - <span data-ttu-id="3217d-183">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="3217d-183">**Transport rule**</span></span>
  - <span data-ttu-id="3217d-184">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="3217d-184">**Subject**</span></span>
  - <span data-ttu-id="3217d-185">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="3217d-185">**Sender address**</span></span>
  - <span data-ttu-id="3217d-186">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="3217d-186">**Recipient address**</span></span>
  - <span data-ttu-id="3217d-187">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="3217d-187">**Severity**</span></span>
  - <span data-ttu-id="3217d-188">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="3217d-188">**Direction**</span></span>

<span data-ttu-id="3217d-189">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-189">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="3217d-190">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="3217d-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="3217d-191">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="3217d-191">Direction values</span></span>
- <span data-ttu-id="3217d-192">Valori di gravità</span><span class="sxs-lookup"><span data-stu-id="3217d-192">Severity values</span></span>

<span data-ttu-id="3217d-193">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="3217d-193">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="3217d-194">Report di inoltro</span><span class="sxs-lookup"><span data-stu-id="3217d-194">Forwarding report</span></span>

<span data-ttu-id="3217d-195">Il **rapporto di inoltro** Visualizza i messaggi di inoltro automatico dell'organizzazione ai domini esterni dalle cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3217d-195">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="3217d-196">I messaggi inoltrati possono rappresentare un rischio per la sicurezza o la conformità e potrebbero indicare un account compromesso.</span><span class="sxs-lookup"><span data-stu-id="3217d-196">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="3217d-197">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **Inoltra rapporto**.</span><span class="sxs-lookup"><span data-stu-id="3217d-197">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="3217d-198">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="3217d-198">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget del report di inoltro nel dashboard dei report](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="3217d-200">Visualizzazione report per il report di inoltro</span><span class="sxs-lookup"><span data-stu-id="3217d-200">Report view for the Forwarding report</span></span>

<span data-ttu-id="3217d-201">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-201">The following charts are available in the report view:</span></span>

- <span data-ttu-id="3217d-202">**Mostra dati per: metodi di inoltro**: vengono illustrati i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-202">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="3217d-203">**Regola di trasporto**: nota anche come [regole del flusso di posta](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="3217d-203">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="3217d-204">**Regola della cassetta postale**: nota anche come [regole della posta in arrivo](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="3217d-204">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Visualizzazione dei metodi di inoltro nel rapporto di inoltro](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="3217d-206">**Visualizzare i dati per: inoltrare i domini**: questa visualizzazione Mostra i domini destinatario che rappresentano le destinazioni per l'inoltro.</span><span class="sxs-lookup"><span data-stu-id="3217d-206">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Visualizzazione dei domini di inoltro nel rapporto di inoltro](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="3217d-208">**Mostra dati per: spedizionieri**: sono visualizzati i seguenti spedizionieri:</span><span class="sxs-lookup"><span data-stu-id="3217d-208">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="3217d-209">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="3217d-209">**Transport rule**</span></span>
  - <span data-ttu-id="3217d-210">La cassetta postale che contiene la regola di posta in arrivo di inoltro.</span><span class="sxs-lookup"><span data-stu-id="3217d-210">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Visualizzazione Inoltratori nel rapporto di inoltro](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="3217d-212">Se si fa clic su **filtri** in una visualizzazione report, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="3217d-212">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="3217d-213">Visualizzazione della tabella dei dettagli per il report di inoltro</span><span class="sxs-lookup"><span data-stu-id="3217d-213">Details table view for the Forwarding report</span></span>

<span data-ttu-id="3217d-214">Se si fa clic su **Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-214">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="3217d-215">**Forwarders**: la **regola di trasporto** del valore o la cassetta postale che contiene la regola di posta in arrivo di inoltro.</span><span class="sxs-lookup"><span data-stu-id="3217d-215">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="3217d-216">**Tipo di inoltro**: la regola della **cassetta postale** del valore o la **regola di trasporto**.</span><span class="sxs-lookup"><span data-stu-id="3217d-216">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="3217d-217">**Nome del destinatario**</span><span class="sxs-lookup"><span data-stu-id="3217d-217">**Recipient name**</span></span>
- <span data-ttu-id="3217d-218">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="3217d-218">**Recipient domain**</span></span>
- <span data-ttu-id="3217d-219">**Dettagli**: questo è il valore GUID della regola del flusso di posta oppure il valore RuleIdentity della regola di posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="3217d-219">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="3217d-220">**Numero**</span><span class="sxs-lookup"><span data-stu-id="3217d-220">**Count**</span></span>
- <span data-ttu-id="3217d-221">**Prima data di inoltro**</span><span class="sxs-lookup"><span data-stu-id="3217d-221">**First forward date**</span></span>

<span data-ttu-id="3217d-222">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="3217d-222">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="3217d-223">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="3217d-223">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="3217d-224">Rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="3217d-224">Mailflow status report</span></span>

<span data-ttu-id="3217d-225">La **relazione sullo stato del flusso** di posta è simile a quella [inviata e ricevuta](#sent-and-received-email-report), con ulteriori informazioni sulla posta elettronica consentita o bloccata sul server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="3217d-225">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="3217d-226">Questo è l'unico report che contiene informazioni sulla protezione dei dati perimetrali e visualizza la quantità di posta elettronica bloccata prima di essere consentita nel servizio per la valutazione da parte di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="3217d-226">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="3217d-227">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **rapporto stato del flusso**di posta.</span><span class="sxs-lookup"><span data-stu-id="3217d-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="3217d-228">Per passare direttamente alla **relazione sullo stato del flusso di posta**, aprire <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="3217d-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget del rapporto sullo stato del flusso di posta nel dashboard report](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="3217d-230">Visualizzazione dei tipi per il rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="3217d-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="3217d-231">Quando si apre il report, la scheda **tipo** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="3217d-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="3217d-232">Per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="3217d-233">**Data**: gli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="3217d-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="3217d-234">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="3217d-234">**Direction**:</span></span>

  - <span data-ttu-id="3217d-235">**Inbound**</span><span class="sxs-lookup"><span data-stu-id="3217d-235">**Inbound**</span></span>
  - <span data-ttu-id="3217d-236">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="3217d-236">**Outbound**</span></span>
  - <span data-ttu-id="3217d-237">**Intra-org** (conteggiati separatamente da in **ingresso** e in **uscita**)</span><span class="sxs-lookup"><span data-stu-id="3217d-237">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="3217d-238">**Digitare**:</span><span class="sxs-lookup"><span data-stu-id="3217d-238">**Type**:</span></span>

  - <span data-ttu-id="3217d-239">**Posta elettronica buona**</span><span class="sxs-lookup"><span data-stu-id="3217d-239">**Good mail**</span></span>
  - <span data-ttu-id="3217d-240">**Malware**</span><span class="sxs-lookup"><span data-stu-id="3217d-240">**Malware**</span></span>
  - <span data-ttu-id="3217d-241">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="3217d-241">**Spam**</span></span>
  - <span data-ttu-id="3217d-242">**Protezione Edge**</span><span class="sxs-lookup"><span data-stu-id="3217d-242">**Edge protection**</span></span>
  - <span data-ttu-id="3217d-243">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="3217d-243">**Rule messages**</span></span>
  - <span data-ttu-id="3217d-244">**Posta di phishing**</span><span class="sxs-lookup"><span data-stu-id="3217d-244">**Phishing email**</span></span>

<span data-ttu-id="3217d-245">Il grafico è organizzato in base ai valori del **tipo** .</span><span class="sxs-lookup"><span data-stu-id="3217d-245">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="3217d-246">È possibile modificare questi filtri facendo clic su **filtro** o facendo clic su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="3217d-246">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="3217d-247">La tabella dati contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-247">The data table contains the following information:</span></span>

- <span data-ttu-id="3217d-248">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="3217d-248">**Direction**</span></span>
- <span data-ttu-id="3217d-249">**Type**</span><span class="sxs-lookup"><span data-stu-id="3217d-249">**Type**</span></span>
- <span data-ttu-id="3217d-250">**24 ore**</span><span class="sxs-lookup"><span data-stu-id="3217d-250">**24 hours**</span></span>
- <span data-ttu-id="3217d-251">**3 giorni**</span><span class="sxs-lookup"><span data-stu-id="3217d-251">**3 days**</span></span>
- <span data-ttu-id="3217d-252">**7 giorni**</span><span class="sxs-lookup"><span data-stu-id="3217d-252">**7 days**</span></span>
- <span data-ttu-id="3217d-253">**15 giorni**</span><span class="sxs-lookup"><span data-stu-id="3217d-253">**15 days**</span></span>
- <span data-ttu-id="3217d-254">**30 giorni**</span><span class="sxs-lookup"><span data-stu-id="3217d-254">**30 days**</span></span>

<span data-ttu-id="3217d-255">Se si fa clic su **Scegli una categoria per maggiori dettagli**, è possibile selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3217d-255">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="3217d-256">**Messaggio di posta elettronica di phishing**: questa opzione consente di eseguire il [rapporto sullo stato della protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="3217d-256">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="3217d-257">**Malware nella posta elettronica**: questa opzione consente di eseguire il [rapporto sullo stato della protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="3217d-257">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="3217d-258">**Rilevamenti di posta indesiderata**: questa selezione porta al [rapporto rilevamento posta indesiderata](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="3217d-258">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="3217d-259">**Posta indesiderata bloccata da Edge**: questa selezione porta al [rapporto rilevamento posta indesiderata](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="3217d-259">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="3217d-260">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="3217d-260">**Export**:</span></span>

<span data-ttu-id="3217d-261">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="3217d-261">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="3217d-262">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 operazioni di esportazione diverse.</span><span class="sxs-lookup"><span data-stu-id="3217d-262">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="3217d-263">Ogni file CSV esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="3217d-263">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="3217d-264">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati più file CSV.</span><span class="sxs-lookup"><span data-stu-id="3217d-264">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="3217d-265">Visualizzazione dei tipi nel rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="3217d-265">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="3217d-266">Visualizzazione direzione per il report sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="3217d-266">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="3217d-267">Se si fa clic sulla scheda **direzione** , vengono utilizzati gli stessi filtri predefiniti della visualizzazione **tipo** .</span><span class="sxs-lookup"><span data-stu-id="3217d-267">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="3217d-268">Il grafico è organizzato in base ai valori della **direzione** .</span><span class="sxs-lookup"><span data-stu-id="3217d-268">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="3217d-269">È possibile modificare questi filtri facendo clic su **filtro** o facendo clic su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="3217d-269">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="3217d-270">Vengono utilizzati gli stessi filtri della visualizzazione **tipo** .</span><span class="sxs-lookup"><span data-stu-id="3217d-270">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="3217d-271">La tabella dati contiene le stesse informazioni dalla visualizzazione **tipo** .</span><span class="sxs-lookup"><span data-stu-id="3217d-271">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="3217d-272">**Scegliere una categoria per ulteriori dettagli** le selezioni e il comportamento disponibili sono uguali alla visualizzazione dei **tipi** .</span><span class="sxs-lookup"><span data-stu-id="3217d-272">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="3217d-273">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="3217d-273">**Export**:</span></span>

<span data-ttu-id="3217d-274">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="3217d-274">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="3217d-275">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 operazioni di esportazione diverse.</span><span class="sxs-lookup"><span data-stu-id="3217d-275">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="3217d-276">Ogni file CSV esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="3217d-276">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="3217d-277">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati più file CSV.</span><span class="sxs-lookup"><span data-stu-id="3217d-277">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="3217d-278">Visualizzazione della direzione nel rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="3217d-278">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="3217d-279">Report di posta elettronica inviati e ricevuti</span><span class="sxs-lookup"><span data-stu-id="3217d-279">Sent and received email report</span></span>

<span data-ttu-id="3217d-280">Il rapporto **messaggi di posta elettronica inviati e ricevuti** è un report Smart che contiene informazioni sulla posta elettronica in arrivo e in uscita, inclusi i rilevamenti di posta indesiderata, il malware e la posta elettronica identificata come "buona".</span><span class="sxs-lookup"><span data-stu-id="3217d-280">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="3217d-281">La differenza tra il report e il [rapporto sullo stato del flusso](#mailflow-status-report) di posta è: questo rapporto non include i dati relativi ai messaggi bloccati dalla protezione Edge.</span><span class="sxs-lookup"><span data-stu-id="3217d-281">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="3217d-282">La visualizzazione aggregazione e la visualizzazione dettagli del rapporto consentono 90 giorni di filtraggio.</span><span class="sxs-lookup"><span data-stu-id="3217d-282">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="3217d-283">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **invio e ricezione della posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="3217d-283">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="3217d-284">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="3217d-284">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget messaggi di posta elettronica inviati e ricevuti nel dashboard report](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="3217d-286">Visualizzazione report per il report di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="3217d-286">Report view for the Sent and received email report</span></span>

<span data-ttu-id="3217d-287">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-287">The following charts are available in the report view:</span></span>

- <span data-ttu-id="3217d-288">**Scomposizione per: tipo**: il grafico Visualizza tutte le categorie disponibili:</span><span class="sxs-lookup"><span data-stu-id="3217d-288">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="3217d-289">**Totale**</span><span class="sxs-lookup"><span data-stu-id="3217d-289">**Total**</span></span>
  - <span data-ttu-id="3217d-290">**Posta elettronica buona**</span><span class="sxs-lookup"><span data-stu-id="3217d-290">**Good mail**</span></span>
  - <span data-ttu-id="3217d-291">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="3217d-291">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="3217d-292">**Rilevamenti di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="3217d-292">**Spam detections**</span></span>
  - <span data-ttu-id="3217d-293">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="3217d-293">**Rule messages**</span></span>
  - <span data-ttu-id="3217d-294">**Malware avanzato** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="3217d-294">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="3217d-295">Quando si posiziona il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile visualizzare i dettagli relativi a quel giorno.</span><span class="sxs-lookup"><span data-stu-id="3217d-295">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Visualizzazione dei tipi nel rapporto posta elettronica inviata e ricevuta](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="3217d-297">**Suddividi in base a: Direction**: il grafico Visualizza i dati **totali**, in **ingresso**e in **uscita** .</span><span class="sxs-lookup"><span data-stu-id="3217d-297">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="3217d-298">Quando si posiziona il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile visualizzare i dettagli relativi a quel giorno.</span><span class="sxs-lookup"><span data-stu-id="3217d-298">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Visualizzazione direzione nel rapporto posta elettronica inviata e ricevuta](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="3217d-300">**Drill-down** \> **Malware (anti-malware)**: questa selezione consente di rilevare i [rilevamenti di malware nel rapporto di posta elettronica](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="3217d-300">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="3217d-301">**Drill-down** \> **Rilevamenti di posta indesiderata)**: questa selezione porta al [rapporto rilevamento posta indesiderata](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="3217d-301">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="3217d-302">Se si fa clic su **filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-302">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="3217d-303">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="3217d-303">**Start date** and **End date**</span></span>
- <span data-ttu-id="3217d-304">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="3217d-304">Direction values</span></span>
- <span data-ttu-id="3217d-305">Valori dei tipi</span><span class="sxs-lookup"><span data-stu-id="3217d-305">Type values</span></span>

<span data-ttu-id="3217d-306">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="3217d-306">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="3217d-307">Visualizzazione della tabella dei dettagli per il report di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="3217d-307">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="3217d-308">Se si fa clic su **Visualizza tabella dettagli** nella visualizzazione **scomposizione per: direzione** o **scomposizione per: direzione** , vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-308">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="3217d-309">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="3217d-309">**Date (UTC)**</span></span>
- <span data-ttu-id="3217d-310">**Type**</span><span class="sxs-lookup"><span data-stu-id="3217d-310">**Type**</span></span>
- <span data-ttu-id="3217d-311">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="3217d-311">**Direction**</span></span>
- <span data-ttu-id="3217d-312">**Numero di messaggi**</span><span class="sxs-lookup"><span data-stu-id="3217d-312">**Message count**</span></span>

<span data-ttu-id="3217d-313">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-313">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="3217d-314">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="3217d-314">**Start date** and **End date**</span></span>
- <span data-ttu-id="3217d-315">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="3217d-315">Direction values</span></span>
- <span data-ttu-id="3217d-316">Valori dei tipi</span><span class="sxs-lookup"><span data-stu-id="3217d-316">Type values</span></span>

<span data-ttu-id="3217d-317">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="3217d-317">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="3217d-318">Report mittenti e destinatari principali</span><span class="sxs-lookup"><span data-stu-id="3217d-318">Top senders and recipients report</span></span>

<span data-ttu-id="3217d-319">Il report **mittenti e destinatari principali** è un grafico a torta che mostra i mittenti e i destinatari di posta elettronica principali.</span><span class="sxs-lookup"><span data-stu-id="3217d-319">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="3217d-320">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare i **mittenti e i destinatari principali**.</span><span class="sxs-lookup"><span data-stu-id="3217d-320">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="3217d-321">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="3217d-321">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget Top Senders and Recipients nel dashboard report](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="3217d-323">Visualizzazione report per i principali mittenti e report dei destinatari</span><span class="sxs-lookup"><span data-stu-id="3217d-323">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="3217d-324">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-324">The following charts are available in the report view:</span></span>

- <span data-ttu-id="3217d-325">**Visualizzare i dati per i \> mittenti di posta principali**</span><span class="sxs-lookup"><span data-stu-id="3217d-325">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="3217d-326">**Visualizzare i dati per i \> destinatari di posta elettronica principali**</span><span class="sxs-lookup"><span data-stu-id="3217d-326">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="3217d-327">**Visualizzare i dati per i \> destinatari di posta indesiderata principali**</span><span class="sxs-lookup"><span data-stu-id="3217d-327">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="3217d-328">**Visualizzare i dati per \> Destinatari principali di malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="3217d-328">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="3217d-329">**Visualizzare i dati per \> Top malware Recipients (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="3217d-329">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="3217d-330">La composizione del grafico a torta cambia in base a queste selezioni.</span><span class="sxs-lookup"><span data-stu-id="3217d-330">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="3217d-331">Quando si posiziona il puntatore del mouse su un cuneo nel grafico a torta, è possibile visualizzare il numero di messaggi inviati o ricevuti.</span><span class="sxs-lookup"><span data-stu-id="3217d-331">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="3217d-332">Se si fa clic su **filtri** in una visualizzazione report, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="3217d-332">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Grafico a torta nella visualizzazione report nel report mittenti e destinatari principali](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="3217d-334">Visualizzazione della tabella Details per i mittenti principali e il report dei destinatari</span><span class="sxs-lookup"><span data-stu-id="3217d-334">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="3217d-335">Se si fa clic su **Visualizza tabella dettagli**, le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="3217d-335">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="3217d-336">**Visualizzare i dati per i \> mittenti di posta principali**</span><span class="sxs-lookup"><span data-stu-id="3217d-336">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="3217d-337">**Mittenti di posta principali**</span><span class="sxs-lookup"><span data-stu-id="3217d-337">**Top mail senders**</span></span>
  - <span data-ttu-id="3217d-338">**Numero**</span><span class="sxs-lookup"><span data-stu-id="3217d-338">**Count**</span></span>

- <span data-ttu-id="3217d-339">**Visualizzare i dati per i \> destinatari di posta elettronica principali**</span><span class="sxs-lookup"><span data-stu-id="3217d-339">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="3217d-340">**Destinatari della posta principale**</span><span class="sxs-lookup"><span data-stu-id="3217d-340">**Top mail recipients**</span></span>
  - <span data-ttu-id="3217d-341">**Numero**</span><span class="sxs-lookup"><span data-stu-id="3217d-341">**Count**</span></span>

- <span data-ttu-id="3217d-342">**Visualizzare i dati per i \> destinatari di posta indesiderata principali**</span><span class="sxs-lookup"><span data-stu-id="3217d-342">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="3217d-343">**Destinatari principali di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="3217d-343">**Top spam recipients**</span></span>
  - <span data-ttu-id="3217d-344">**Numero**</span><span class="sxs-lookup"><span data-stu-id="3217d-344">**Count**</span></span>

- <span data-ttu-id="3217d-345">**Visualizzare i dati per \> Destinatari principali di malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="3217d-345">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="3217d-346">**Destinatari principali di malware**</span><span class="sxs-lookup"><span data-stu-id="3217d-346">**Top malware recipients**</span></span>
  - <span data-ttu-id="3217d-347">**Numero**</span><span class="sxs-lookup"><span data-stu-id="3217d-347">**Count**</span></span>

- <span data-ttu-id="3217d-348">**Visualizzare i dati per \> Top malware Recipients (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="3217d-348">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="3217d-349">**Destinatari principali di malware (ATP)**</span><span class="sxs-lookup"><span data-stu-id="3217d-349">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="3217d-350">**Numero**</span><span class="sxs-lookup"><span data-stu-id="3217d-350">**Count**</span></span>

<span data-ttu-id="3217d-351">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="3217d-351">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="3217d-352">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="3217d-352">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="3217d-353">Quali autorizzazioni sono necessarie per visualizzare i rapporti?</span><span class="sxs-lookup"><span data-stu-id="3217d-353">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="3217d-354">Per visualizzare e utilizzare i report, è necessario essere membri del gruppo di ruoli specificato nel centro sicurezza & conformità **e** in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3217d-354">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="3217d-355">Nel centro sicurezza & conformità è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-355">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="3217d-356">-Gestione dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3217d-356">-Organization Management</span></span>

  <span data-ttu-id="3217d-357">-Security Administrator (è possibile eseguire questa operazione anche nell'interfaccia di [amministrazione di Azure Active Directory](https://aad.portal.azure.com) -Security Reader</span><span class="sxs-lookup"><span data-stu-id="3217d-357">-Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="3217d-358">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="3217d-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="3217d-359">In Exchange Online, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="3217d-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="3217d-360">-Gestione dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="3217d-360">-Organization Management</span></span>

  <span data-ttu-id="3217d-361">Gestione dell'organizzazione in sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="3217d-361">-View-only Organization Management</span></span>

  <span data-ttu-id="3217d-362">-Destinatari di sola visualizzazione</span><span class="sxs-lookup"><span data-stu-id="3217d-362">-View-Only Recipients</span></span>

  <span data-ttu-id="3217d-363">-Compliance Management</span><span class="sxs-lookup"><span data-stu-id="3217d-363">-Compliance Management</span></span>

<span data-ttu-id="3217d-364">Per ulteriori informazioni, vedere [autorizzazioni in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) e [gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="3217d-364">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3217d-365">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="3217d-365">Related topics</span></span>

[<span data-ttu-id="3217d-366">Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="3217d-366">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="3217d-367">Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="3217d-367">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)
