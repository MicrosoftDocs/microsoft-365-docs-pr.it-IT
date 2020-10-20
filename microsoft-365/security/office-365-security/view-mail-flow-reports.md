---
title: Visualizzare i report del flusso di posta nel dashboard dei report
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui rapporti sul flusso di posta disponibili nel dashboard report nel centro sicurezza & Compliance.
ms.custom: ''
ms.openlocfilehash: 801463877db2e022ab84c3187367587c61f71090
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600593"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="d36aa-103">Visualizzare i report sul flusso di posta nel dashboard report nel centro sicurezza & Compliance</span><span class="sxs-lookup"><span data-stu-id="d36aa-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d36aa-104">Oltre ai rapporti sul flusso di posta disponibili nel [Dashboard del flusso](mail-flow-insights-v2.md) di posta elettronica nel centro sicurezza & Compliance, nel dashboard report sono disponibili numerosi rapporti di flusso di posta aggiuntivi che consentono di monitorare l'organizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d36aa-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="d36aa-105">Se si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-these-reports), è possibile visualizzare i report nel [Centro sicurezza & Compliance](https://office.protection.com) accedendo al **Reports** \> **Dashboard**report.</span><span class="sxs-lookup"><span data-stu-id="d36aa-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="d36aa-106">Per accedere direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="d36aa-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard dei report nel centro sicurezza & Compliance](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="d36aa-108">Rapporto connettore</span><span class="sxs-lookup"><span data-stu-id="d36aa-108">Connector report</span></span>

<span data-ttu-id="d36aa-109">Il **rapporto connettore** consente di visualizzare l'attività del flusso di posta sui [connettori in ingresso e in uscita](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) configurati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d36aa-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="d36aa-110">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare il **report del connettore**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="d36aa-111">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="d36aa-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget del rapporto del connettore nel dashboard dei report](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="d36aa-113">Visualizzazione report per il report del connettore</span><span class="sxs-lookup"><span data-stu-id="d36aa-113">Report view for the Connector report</span></span>

<span data-ttu-id="d36aa-114">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="d36aa-115">**Visualizzazione dei dati per: flusso di posta**: questo grafico mostra il numero di messaggi in ingresso e in uscita organizzati da:</span><span class="sxs-lookup"><span data-stu-id="d36aa-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="d36aa-116">**Totale**</span><span class="sxs-lookup"><span data-stu-id="d36aa-116">**Total**</span></span>
  - <span data-ttu-id="d36aa-117">**Da Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="d36aa-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="d36aa-118">**A Internet senza un connettore**</span><span class="sxs-lookup"><span data-stu-id="d36aa-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="d36aa-119">Connettore specifico configurato.</span><span class="sxs-lookup"><span data-stu-id="d36aa-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="d36aa-120">Per isolare i dati nel grafico, utilizzare la casella di controllo **Mostra dati per** selezionare una di queste opzioni o **tutto il flusso di posta**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Visualizzare i dati in base al flusso di posta nel rapporto del connettore](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="d36aa-122">**Visualizzare i dati in base a: utilizzo TLS**: questo grafico mostra la percentuale di utilizzo della versione TLS (Transport Layer Security) per il flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="d36aa-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="d36aa-123">Per isolare i dati nel grafico, utilizzare il controllo **Mostra dati per** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="d36aa-124">**Tutto il flusso di posta**</span><span class="sxs-lookup"><span data-stu-id="d36aa-124">**All mail flow**</span></span>
  - <span data-ttu-id="d36aa-125">**Da Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="d36aa-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="d36aa-126">**A Internet senza un connettore**</span><span class="sxs-lookup"><span data-stu-id="d36aa-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="d36aa-127">Connettore specifico configurato.</span><span class="sxs-lookup"><span data-stu-id="d36aa-127">A specific connector that you've configured.</span></span>

  ![Visualizzare i dati in base all'utilizzo di TLS nel report del connettore](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="d36aa-129">Se si fa clic su **filtri** in una visualizzazione report, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="d36aa-130">Visualizzazione della tabella dei dettagli per il report del connettore</span><span class="sxs-lookup"><span data-stu-id="d36aa-130">Details table view for the Connector report</span></span>

<span data-ttu-id="d36aa-131">Se si fa clic su **Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="d36aa-132">**Data**</span><span class="sxs-lookup"><span data-stu-id="d36aa-132">**Date**</span></span>
- <span data-ttu-id="d36aa-133">**Direzione e nome del connettore**</span><span class="sxs-lookup"><span data-stu-id="d36aa-133">**Connector direction and name**</span></span>
- <span data-ttu-id="d36aa-134">**Tipo di connettore**</span><span class="sxs-lookup"><span data-stu-id="d36aa-134">**Connector type**</span></span>
- <span data-ttu-id="d36aa-135">**TLS forzato**: il valore **true** o **false**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="d36aa-136">**Nessun TLS** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="d36aa-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="d36aa-137">**TLS 1,0** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="d36aa-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="d36aa-138">**TLS 1,1** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="d36aa-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="d36aa-139">**TLS 1,2** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="d36aa-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="d36aa-140">**Volume**: il numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="d36aa-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="d36aa-141">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d36aa-142">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="d36aa-143">Rapporto delle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="d36aa-143">Exchange transport rule report</span></span>

<span data-ttu-id="d36aa-144">Il **rapporto della regola di trasporto di Exchange** indica l'effetto delle regole del flusso di posta (note anche come regole di trasporto) sui messaggi in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d36aa-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="d36aa-145">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **regola di trasporto di Exchange**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="d36aa-146">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="d36aa-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget delle regole di trasporto di Exchange nel dashboard dei report](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="d36aa-148">Visualizzazione report per il rapporto delle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="d36aa-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="d36aa-149">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="d36aa-150">**Visualizzare i dati in base a: regole** \> di trasporto di Exchange **Scomposizione per: direzione**: questo grafico indica il numero di messaggi in **ingresso** e in **uscita** che sono stati interessati dalle regole di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d36aa-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="d36aa-151">**Visualizzare i dati in base a: regole** \> di trasporto di Exchange **Scomposizione in base a: gravità**: questo grafico Visualizza il numero di severità **elevata** e di gravità **media**e messaggi di **gravità insufficienti** .</span><span class="sxs-lookup"><span data-stu-id="d36aa-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="d36aa-152">È possibile impostare il livello di gravità come azione nella regola (**controllare questa regola con livello di gravità** o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="d36aa-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="d36aa-153">Per ulteriori informazioni, vedere [azioni delle regole del flusso di posta in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="d36aa-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="d36aa-154">**Visualizzare i dati in base a: regole di trasporto di Exchange DLP** \> **Scomposizione per: Direction**: questo grafico indica il numero di messaggi in **ingresso** e in **uscita** che sono stati interessati dalle regole di trasporto di prevenzione della perdita di dati (DLP).</span><span class="sxs-lookup"><span data-stu-id="d36aa-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="d36aa-155">È possibile affinare ulteriormente il grafico selezionando le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="d36aa-156">**Mostra dati per: tutte le regole di trasporto DLP**</span><span class="sxs-lookup"><span data-stu-id="d36aa-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="d36aa-157">**Visualizzare i dati per: utenti compromessi**</span><span class="sxs-lookup"><span data-stu-id="d36aa-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="d36aa-158">**Mostra dati per: basso volume di contenuto rilevato US Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="d36aa-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="d36aa-159">**Visualizzare i dati in base a: regole di trasporto di Exchange DLP** \> **Suddividi in base a: Direction**: questa visualizzazione Mostra il numero di gravità **elevata** e di gravità **media**e i messaggi a **bassa severità** che sono stati interessati dalle regole di trasporto DLP.</span><span class="sxs-lookup"><span data-stu-id="d36aa-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="d36aa-160">È possibile affinare ulteriormente il grafico selezionando le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="d36aa-161">**Mostra dati per: tutte le regole di trasporto DLP**</span><span class="sxs-lookup"><span data-stu-id="d36aa-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="d36aa-162">**Visualizzare i dati per: utenti compromessi**</span><span class="sxs-lookup"><span data-stu-id="d36aa-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="d36aa-163">**Mostra dati per: basso volume di contenuto rilevato US Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="d36aa-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="d36aa-164">Se si fa clic su **filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="d36aa-165">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d36aa-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="d36aa-166">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="d36aa-166">Direction values</span></span>
- <span data-ttu-id="d36aa-167">Valori di gravità</span><span class="sxs-lookup"><span data-stu-id="d36aa-167">Severity values</span></span>

![Visualizzazione report nel rapporto delle regole di trasporto di Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="d36aa-169">Visualizzazione della tabella dei dettagli per il rapporto delle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="d36aa-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="d36aa-170">Se si fa clic su **Visualizza tabella dettagli**, le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="d36aa-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d36aa-171">**Visualizzare i dati per: regole di trasporto di Exchange**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="d36aa-172">**Data**</span><span class="sxs-lookup"><span data-stu-id="d36aa-172">**Date**</span></span>
  - <span data-ttu-id="d36aa-173">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="d36aa-173">**Transport rule**</span></span>
  - <span data-ttu-id="d36aa-174">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="d36aa-174">**Subject**</span></span>
  - <span data-ttu-id="d36aa-175">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="d36aa-175">**Sender address**</span></span>
  - <span data-ttu-id="d36aa-176">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="d36aa-176">**Recipient address**</span></span>
  - <span data-ttu-id="d36aa-177">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="d36aa-177">**Severity**</span></span>
  - <span data-ttu-id="d36aa-178">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="d36aa-178">**Direction**</span></span>

- <span data-ttu-id="d36aa-179">**Visualizzare i dati in base a: regole di trasporto di Exchange DLP**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="d36aa-180">**Data**</span><span class="sxs-lookup"><span data-stu-id="d36aa-180">**Date**</span></span>
  - <span data-ttu-id="d36aa-181">**Criteri DLP**</span><span class="sxs-lookup"><span data-stu-id="d36aa-181">**DLP policy**</span></span>
  - <span data-ttu-id="d36aa-182">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="d36aa-182">**Transport rule**</span></span>
  - <span data-ttu-id="d36aa-183">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="d36aa-183">**Subject**</span></span>
  - <span data-ttu-id="d36aa-184">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="d36aa-184">**Sender address**</span></span>
  - <span data-ttu-id="d36aa-185">**Indirizzo del destinatario**</span><span class="sxs-lookup"><span data-stu-id="d36aa-185">**Recipient address**</span></span>
  - <span data-ttu-id="d36aa-186">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="d36aa-186">**Severity**</span></span>
  - <span data-ttu-id="d36aa-187">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="d36aa-187">**Direction**</span></span>

<span data-ttu-id="d36aa-188">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="d36aa-189">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d36aa-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="d36aa-190">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="d36aa-190">Direction values</span></span>
- <span data-ttu-id="d36aa-191">Valori di gravità</span><span class="sxs-lookup"><span data-stu-id="d36aa-191">Severity values</span></span>

<span data-ttu-id="d36aa-192">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="d36aa-193">Report di inoltro</span><span class="sxs-lookup"><span data-stu-id="d36aa-193">Forwarding report</span></span>

<span data-ttu-id="d36aa-194">Il **rapporto di inoltro** Visualizza i messaggi di inoltro automatico dell'organizzazione ai domini esterni dalle cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d36aa-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="d36aa-195">I messaggi inoltrati possono rappresentare un rischio per la sicurezza o la conformità e potrebbero indicare un account compromesso.</span><span class="sxs-lookup"><span data-stu-id="d36aa-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="d36aa-196">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **Inoltra rapporto**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="d36aa-197">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="d36aa-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget del report di inoltro nel dashboard dei report](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="d36aa-199">Visualizzazione report per il report di inoltro</span><span class="sxs-lookup"><span data-stu-id="d36aa-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="d36aa-200">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="d36aa-201">**Mostra dati per: metodi di inoltro**: vengono illustrati i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="d36aa-202">**Regola di trasporto**: nota anche come [regole del flusso di posta](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="d36aa-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="d36aa-203">**Regola della cassetta postale**: nota anche come [regole della posta in arrivo](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="d36aa-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Visualizzazione dei metodi di inoltro nel rapporto di inoltro](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="d36aa-205">**Visualizzare i dati per: inoltrare i domini**: questa visualizzazione Mostra i domini destinatario che rappresentano le destinazioni per l'inoltro.</span><span class="sxs-lookup"><span data-stu-id="d36aa-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Visualizzazione dei domini di inoltro nel rapporto di inoltro](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="d36aa-207">**Mostra dati per: spedizionieri**: sono visualizzati i seguenti spedizionieri:</span><span class="sxs-lookup"><span data-stu-id="d36aa-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="d36aa-208">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="d36aa-208">**Transport rule**</span></span>
  - <span data-ttu-id="d36aa-209">La cassetta postale che contiene la regola di posta in arrivo di inoltro.</span><span class="sxs-lookup"><span data-stu-id="d36aa-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Visualizzazione Inoltratori nel rapporto di inoltro](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="d36aa-211">Se si fa clic su **filtri** in una visualizzazione report, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="d36aa-212">Visualizzazione della tabella dei dettagli per il report di inoltro</span><span class="sxs-lookup"><span data-stu-id="d36aa-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="d36aa-213">Se si fa clic su **Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="d36aa-214">**Forwarders**: la **regola di trasporto** del valore o la cassetta postale che contiene la regola di posta in arrivo di inoltro.</span><span class="sxs-lookup"><span data-stu-id="d36aa-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="d36aa-215">**Tipo di inoltro**: la regola della **cassetta postale** del valore o la **regola di trasporto**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="d36aa-216">**Nome del destinatario**</span><span class="sxs-lookup"><span data-stu-id="d36aa-216">**Recipient name**</span></span>
- <span data-ttu-id="d36aa-217">**Dominio del destinatario**</span><span class="sxs-lookup"><span data-stu-id="d36aa-217">**Recipient domain**</span></span>
- <span data-ttu-id="d36aa-218">**Dettagli**: questo è il valore GUID della regola del flusso di posta oppure il valore RuleIdentity della regola di posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="d36aa-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="d36aa-219">**Numero**</span><span class="sxs-lookup"><span data-stu-id="d36aa-219">**Count**</span></span>
- <span data-ttu-id="d36aa-220">**Prima data di inoltro**</span><span class="sxs-lookup"><span data-stu-id="d36aa-220">**First forward date**</span></span>

<span data-ttu-id="d36aa-221">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d36aa-222">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="d36aa-223">Rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d36aa-223">Mailflow status report</span></span>

<span data-ttu-id="d36aa-224">La **relazione sullo stato del flusso** di posta è simile a quella [inviata e ricevuta](#sent-and-received-email-report), con ulteriori informazioni sulla posta elettronica consentita o bloccata sul server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d36aa-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="d36aa-225">Questo è l'unico report che contiene informazioni sulla protezione dei dati perimetrali e visualizza la quantità di posta elettronica bloccata prima di essere consentita nel servizio per la valutazione da parte di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d36aa-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="d36aa-226">È importante comprendere che se un messaggio viene inviato a cinque destinatari, è necessario contarlo come cinque messaggi diversi e non con un solo messaggio.</span><span class="sxs-lookup"><span data-stu-id="d36aa-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="d36aa-227">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **rapporto stato del flusso**di posta.</span><span class="sxs-lookup"><span data-stu-id="d36aa-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="d36aa-228">Per passare direttamente alla **relazione sullo stato del flusso di posta**, aprire <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="d36aa-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget del rapporto sullo stato del flusso di posta nel dashboard report](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="d36aa-230">Visualizzazione dei tipi per il rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d36aa-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="d36aa-231">Quando si apre il report, la scheda **tipo** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d36aa-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="d36aa-232">Per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="d36aa-233">**Data**: gli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="d36aa-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="d36aa-234">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-234">**Direction**:</span></span>

  - <span data-ttu-id="d36aa-235">**Inbound**</span><span class="sxs-lookup"><span data-stu-id="d36aa-235">**Inbound**</span></span>
  - <span data-ttu-id="d36aa-236">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="d36aa-236">**Outbound**</span></span>
  - <span data-ttu-id="d36aa-237">**Intra-org**: questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="d36aa-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="d36aa-238">sender abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da in **ingresso** e in **uscita**)</span><span class="sxs-lookup"><span data-stu-id="d36aa-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="d36aa-239">**Digitare**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-239">**Type**:</span></span>

  - <span data-ttu-id="d36aa-240">**Posta elettronica buona**</span><span class="sxs-lookup"><span data-stu-id="d36aa-240">**Good mail**</span></span>
  - <span data-ttu-id="d36aa-241">**Malware**</span><span class="sxs-lookup"><span data-stu-id="d36aa-241">**Malware**</span></span>
  - <span data-ttu-id="d36aa-242">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="d36aa-242">**Spam**</span></span>
  - <span data-ttu-id="d36aa-243">**Protezione Edge**</span><span class="sxs-lookup"><span data-stu-id="d36aa-243">**Edge protection**</span></span>
  - <span data-ttu-id="d36aa-244">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="d36aa-244">**Rule messages**</span></span>
  - <span data-ttu-id="d36aa-245">**Posta di phishing**</span><span class="sxs-lookup"><span data-stu-id="d36aa-245">**Phishing email**</span></span>

<span data-ttu-id="d36aa-246">Il grafico è organizzato in base ai valori del **tipo** .</span><span class="sxs-lookup"><span data-stu-id="d36aa-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="d36aa-247">È possibile modificare questi filtri facendo clic su **filtro** o facendo clic su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="d36aa-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="d36aa-248">La tabella dati contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-248">The data table contains the following information:</span></span>

- <span data-ttu-id="d36aa-249">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="d36aa-249">**Direction**</span></span>
- <span data-ttu-id="d36aa-250">**Type**</span><span class="sxs-lookup"><span data-stu-id="d36aa-250">**Type**</span></span>
- <span data-ttu-id="d36aa-251">**24 ore**</span><span class="sxs-lookup"><span data-stu-id="d36aa-251">**24 hours**</span></span>
- <span data-ttu-id="d36aa-252">**3 giorni**</span><span class="sxs-lookup"><span data-stu-id="d36aa-252">**3 days**</span></span>
- <span data-ttu-id="d36aa-253">**7 giorni**</span><span class="sxs-lookup"><span data-stu-id="d36aa-253">**7 days**</span></span>
- <span data-ttu-id="d36aa-254">**15 giorni**</span><span class="sxs-lookup"><span data-stu-id="d36aa-254">**15 days**</span></span>
- <span data-ttu-id="d36aa-255">**30 giorni**</span><span class="sxs-lookup"><span data-stu-id="d36aa-255">**30 days**</span></span>

<span data-ttu-id="d36aa-256">Se si fa clic su **Scegli una categoria per maggiori dettagli**, è possibile selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d36aa-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="d36aa-257">**Messaggio di posta elettronica di phishing**: questa opzione consente di eseguire il [rapporto sullo stato della protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="d36aa-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="d36aa-258">**Malware nella posta elettronica**: questa opzione consente di eseguire il [rapporto sullo stato della protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="d36aa-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="d36aa-259">**Rilevamenti di posta indesiderata**: questa selezione porta al [rapporto rilevamento posta indesiderata](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="d36aa-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="d36aa-260">**Posta indesiderata bloccata da Edge**: questa selezione porta al [rapporto rilevamento posta indesiderata](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="d36aa-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="d36aa-261">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-261">**Export**:</span></span>

<span data-ttu-id="d36aa-262">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="d36aa-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="d36aa-263">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 operazioni di esportazione diverse.</span><span class="sxs-lookup"><span data-stu-id="d36aa-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="d36aa-264">Ogni file CSV esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="d36aa-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="d36aa-265">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati più file CSV.</span><span class="sxs-lookup"><span data-stu-id="d36aa-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="d36aa-266">Visualizzazione dei tipi nel rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d36aa-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="d36aa-267">Visualizzazione direzione per il report sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d36aa-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="d36aa-268">Se si fa clic sulla scheda **direzione** , vengono utilizzati gli stessi filtri predefiniti della visualizzazione **tipo** .</span><span class="sxs-lookup"><span data-stu-id="d36aa-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="d36aa-269">Il grafico è organizzato in base ai valori della **direzione** .</span><span class="sxs-lookup"><span data-stu-id="d36aa-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="d36aa-270">È possibile modificare questi filtri facendo clic su **filtro** o facendo clic su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="d36aa-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="d36aa-271">Vengono utilizzati gli stessi filtri della visualizzazione **tipo** .</span><span class="sxs-lookup"><span data-stu-id="d36aa-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="d36aa-272">La tabella dati contiene le stesse informazioni dalla visualizzazione **tipo** .</span><span class="sxs-lookup"><span data-stu-id="d36aa-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="d36aa-273">**Scegliere una categoria per ulteriori dettagli** le selezioni e il comportamento disponibili sono uguali alla visualizzazione dei **tipi** .</span><span class="sxs-lookup"><span data-stu-id="d36aa-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="d36aa-274">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-274">**Export**:</span></span>

<span data-ttu-id="d36aa-275">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="d36aa-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="d36aa-276">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 operazioni di esportazione diverse.</span><span class="sxs-lookup"><span data-stu-id="d36aa-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="d36aa-277">Ogni file CSV esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="d36aa-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="d36aa-278">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati più file CSV.</span><span class="sxs-lookup"><span data-stu-id="d36aa-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="d36aa-279">Visualizzazione della direzione nel rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d36aa-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="d36aa-280">Visualizzazione imbuto per il report sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d36aa-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="d36aa-281">La visualizzazione **imbuto** Mostra il modo in cui le funzionalità di protezione della posta elettronica di Microsoft filtrano i messaggi di posta elettronica in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d36aa-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="d36aa-282">Fornisce informazioni dettagliate sul numero totale di messaggi di posta elettronica e su come le funzionalità di protezione delle minacce configurate, tra cui protezione Edge, antimalware, anti-phishing, antispam e anti-spoofing, influiscono su questo conteggio.</span><span class="sxs-lookup"><span data-stu-id="d36aa-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="d36aa-283">Se si fa clic sulla scheda **imbuto** , per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="d36aa-284">**Data**: gli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="d36aa-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="d36aa-285">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-285">**Direction**:</span></span>

  - <span data-ttu-id="d36aa-286">**Inbound**</span><span class="sxs-lookup"><span data-stu-id="d36aa-286">**Inbound**</span></span>
  - <span data-ttu-id="d36aa-287">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="d36aa-287">**Outbound**</span></span>
  - <span data-ttu-id="d36aa-288">**Intra-org**: questo conteggio è per i messaggi inviati all'interno di un tenant. vale a dire che il mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da in ingresso e in uscita).</span><span class="sxs-lookup"><span data-stu-id="d36aa-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="d36aa-289">La visualizzazione aggregazione e la vista tabella dati consentono 90 giorni di filtraggio.</span><span class="sxs-lookup"><span data-stu-id="d36aa-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="d36aa-290">Se si fa clic su **filtro**, è possibile filtrare sia il grafico che la tabella dati.</span><span class="sxs-lookup"><span data-stu-id="d36aa-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="d36aa-291">Questo grafico Visualizza il numero di messaggi di posta elettronica organizzati da:</span><span class="sxs-lookup"><span data-stu-id="d36aa-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="d36aa-292">**Numero totale di messaggi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d36aa-292">**Total email**</span></span>
- <span data-ttu-id="d36aa-293">**Posta elettronica dopo la protezione Edge**</span><span class="sxs-lookup"><span data-stu-id="d36aa-293">**Email after edge protection**</span></span>
- <span data-ttu-id="d36aa-294">**Posta elettronica dopo antimalware, reputazione file, blocco di tipi di file**</span><span class="sxs-lookup"><span data-stu-id="d36aa-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="d36aa-295">**Messaggi di posta elettronica dopo l'anti-phishing, la reputazione URL, la rappresentazione del marchio, l'anti-spoofing**</span><span class="sxs-lookup"><span data-stu-id="d36aa-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="d36aa-296">**Messaggi di posta elettronica dopo la protezione dalla posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="d36aa-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="d36aa-297">**Messaggi di posta elettronica dopo la rappresentazione del dominio e dell'utente**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d36aa-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="d36aa-298">**Messaggio di posta elettronica dopo la detonazione di file e URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d36aa-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="d36aa-299">**Messaggi di posta elettronica rilevati come benigni dopo la protezione dopo il recapito (URL click Time Protection)**</span><span class="sxs-lookup"><span data-stu-id="d36aa-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="d36aa-300"><sup>1</sup> Office 365 solo ATP</span><span class="sxs-lookup"><span data-stu-id="d36aa-300"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="d36aa-301">Per visualizzare l'indirizzo di posta elettronica filtrato da EOP o ATP separatamente, fare clic sul valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="d36aa-301">To view the email filtered by EOP or ATP separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="d36aa-302">La tabella dati contiene le informazioni seguenti, visualizzate in ordine di data decrescente:</span><span class="sxs-lookup"><span data-stu-id="d36aa-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="d36aa-303">**Data**</span><span class="sxs-lookup"><span data-stu-id="d36aa-303">**Date**</span></span>
- <span data-ttu-id="d36aa-304">**Numero totale di messaggi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d36aa-304">**Total email**</span></span>
- <span data-ttu-id="d36aa-305">**Protezione Edge**</span><span class="sxs-lookup"><span data-stu-id="d36aa-305">**Edge protection**</span></span> 
- <span data-ttu-id="d36aa-306">**Anti-malware, reputazione dei file, blocco di tipi di file**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="d36aa-307">**Reputazione file**: i messaggi sono stati filtrati a causa dell'identificazione di un file allegato da altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d36aa-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="d36aa-308">**Blocco di tipi di file**: messaggi filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="d36aa-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>      
- <span data-ttu-id="d36aa-309">**Anti-phishing, reputazione URL, rappresentazione di marca, anti-spoofing**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="d36aa-310">**Reputazione URL**: messaggi filtrati a causa dell'identificazione dell'URL da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d36aa-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="d36aa-311">**Rappresentazione del marchio**: i messaggi vengono filtrati a causa del messaggio proveniente da mittenti ben noti.</span><span class="sxs-lookup"><span data-stu-id="d36aa-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="d36aa-312">**Anti-spoofing**: i messaggi vengono filtrati a causa del messaggio che tenta di falsificare un dominio a cui appartiene il destinatario oppure di un dominio che il mittente del messaggio non possiede.</span><span class="sxs-lookup"><span data-stu-id="d36aa-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>  
- <span data-ttu-id="d36aa-313">**Filtro posta indesiderata, messaggi in blocco**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="d36aa-314">**Filtro posta in blocco**: messaggi filtrati a causa di un tentativo di recapitare la posta in blocco ai destinatari.</span><span class="sxs-lookup"><span data-stu-id="d36aa-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span> 
- <span data-ttu-id="d36aa-315">**Rappresentazione di utenti e domini (ATP)**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-315">**User and domain impersonation (ATP)**:</span></span>
  - <span data-ttu-id="d36aa-316">**Rappresentazione utente**: i messaggi sono stati filtrati a causa di un tentativo di rappresentazione di un utente (mittente del messaggio) definito nelle impostazioni di protezione della rappresentazione di un criterio di anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="d36aa-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="d36aa-317">**Rappresentazione del dominio**: i messaggi sono stati filtrati a causa di un tentativo di rappresentare un dominio definito nelle impostazioni di protezione della rappresentazione di un criterio di anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="d36aa-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span> 
- <span data-ttu-id="d36aa-318">**Detonazione di file e URL (ATP)**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-318">**File and URL detonation (ATP)**:</span></span>
  - <span data-ttu-id="d36aa-319">**Detonazione dei file**: messaggi filtrati da un criterio di allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="d36aa-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="d36aa-320">**Detonazione URL**: messaggio filtrato da un criterio collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="d36aa-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>  
- <span data-ttu-id="d36aa-321">**Protezione da post-recapito e zap (ATP) o zap (EOP)**: zap indica lo stato di eliminazione automatica di zero ore.</span><span class="sxs-lookup"><span data-stu-id="d36aa-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="d36aa-322">Se si seleziona una riga nella tabella dati, nel riquadro a comparsa viene visualizzata un'ulteriore scomposizione dei conteggi della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d36aa-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="d36aa-323">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-323">**Export**:</span></span>

<span data-ttu-id="d36aa-324">Dopo aver fatto clic su **Esporta** in **Opzioni**, è possibile selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d36aa-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="d36aa-325">**Riepilogo (con i dati per gli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="d36aa-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="d36aa-326">**Dettagli (con i dati per gli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="d36aa-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="d36aa-327">In **Data**scegliere un intervallo e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="d36aa-328">I dati relativi ai filtri correnti verranno esportati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="d36aa-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="d36aa-329">Ogni file CSV esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="d36aa-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="d36aa-330">Se i dati contengono più di 150.000 righe, verranno creati più file CSV.</span><span class="sxs-lookup"><span data-stu-id="d36aa-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="d36aa-331">Visualizzazione imbuto nel rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d36aa-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="d36aa-332">Visualizzazione tecnologia per il report sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d36aa-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="d36aa-333">La **visualizzazione Tech** è simile alla visualizzazione **imbuto** , fornendo dettagli più granulari per le funzionalità di protezione delle minacce configurate.</span><span class="sxs-lookup"><span data-stu-id="d36aa-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="d36aa-334">Dal grafico, è possibile vedere in che modo i messaggi vengono categorizzati nelle diverse fasi della protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="d36aa-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="d36aa-335">Se si fa clic sulla scheda **Tech View** , per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="d36aa-336">**Data**: gli ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="d36aa-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="d36aa-337">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-337">**Direction**:</span></span>

  - <span data-ttu-id="d36aa-338">**Inbound**</span><span class="sxs-lookup"><span data-stu-id="d36aa-338">**Inbound**</span></span>
  - <span data-ttu-id="d36aa-339">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="d36aa-339">**Outbound**</span></span>
  - <span data-ttu-id="d36aa-340">**Intra-org**: questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="d36aa-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="d36aa-341">sender abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da in ingresso e in uscita)</span><span class="sxs-lookup"><span data-stu-id="d36aa-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="d36aa-342">La visualizzazione aggregazione e la vista tabella dati consentono 90 giorni di filtraggio.</span><span class="sxs-lookup"><span data-stu-id="d36aa-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="d36aa-343">Se si fa clic su **filtro**, è possibile filtrare sia il grafico che la tabella dati.</span><span class="sxs-lookup"><span data-stu-id="d36aa-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="d36aa-344">In questo grafico vengono visualizzati i messaggi organizzati nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="d36aa-345">**Numero totale di messaggi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d36aa-345">**Total email**</span></span>
- <span data-ttu-id="d36aa-346">**Consenti Edge, filtro perimetrale**</span><span class="sxs-lookup"><span data-stu-id="d36aa-346">**Edge allow, edge filtered**</span></span>
- <span data-ttu-id="d36aa-347">**Non malware, rilevamento degli allegati sicuri (ATP), rilevamento del motore antimalware, blocco di regole**</span><span class="sxs-lookup"><span data-stu-id="d36aa-347">**Not malware, Safe attachments detection (ATP), Anti-malware engine detection, rule block**</span></span>
- <span data-ttu-id="d36aa-348">**Not phishing, DMARC failure, rappresentazione Detection, spoofing Detection, phishing detection**</span><span class="sxs-lookup"><span data-stu-id="d36aa-348">**Not phish, DMARC failure, impersonation detection, spoof detection, phish detection**</span></span>
- <span data-ttu-id="d36aa-349">**Nessun rilevamento con detonazione URL, rilevamento di detonazione URL (ATP)**</span><span class="sxs-lookup"><span data-stu-id="d36aa-349">**No detection with URL detonation, URL detonation detection (ATP)**</span></span>
- <span data-ttu-id="d36aa-350">**Non spam, posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="d36aa-350">**Not spam, spam**</span></span>
- <span data-ttu-id="d36aa-351">**Posta elettronica non dannosa, rilevamento collegamenti sicuri (ATP), ZAP**</span><span class="sxs-lookup"><span data-stu-id="d36aa-351">**Non-malicious email, safe links detection (ATP), ZAP**</span></span>

<span data-ttu-id="d36aa-352">Quando si posiziona il puntatore del mouse su una categoria del grafico, è possibile visualizzare il numero di messaggi in quella categoria.</span><span class="sxs-lookup"><span data-stu-id="d36aa-352">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="d36aa-353">La tabella dati contiene le informazioni seguenti, visualizzate in ordine di data decrescente:</span><span class="sxs-lookup"><span data-stu-id="d36aa-353">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="d36aa-354">**Data**</span><span class="sxs-lookup"><span data-stu-id="d36aa-354">**Date**</span></span>
- <span data-ttu-id="d36aa-355">**Numero totale di messaggi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d36aa-355">**Total email**</span></span>
- <span data-ttu-id="d36aa-356">**Filtro perimetrale**</span><span class="sxs-lookup"><span data-stu-id="d36aa-356">**Edge filtered**</span></span>
- <span data-ttu-id="d36aa-357">**Motore antimalware, allegati sicuri, regola filtrata**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-357">**Anti-malware engine, safe attachments, rule filtered**:</span></span>
  - <span data-ttu-id="d36aa-358">**Regola filtrata**: messaggi filtrati a causa delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="d36aa-358">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="d36aa-359">**DMARC, rappresentazione, spoofing, phishing filtrati**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-359">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="d36aa-360">**DMARC**: i messaggi vengono filtrati a causa del mancato controllo dell'autenticazione di DMARC per il messaggio.</span><span class="sxs-lookup"><span data-stu-id="d36aa-360">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span> 
- <span data-ttu-id="d36aa-361">**Rilevamento di detonazione degli URL**</span><span class="sxs-lookup"><span data-stu-id="d36aa-361">**URL detonation detection**</span></span>
- <span data-ttu-id="d36aa-362">**Filtro di protezione da posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="d36aa-362">**Anti-spam filtered**</span></span>
- <span data-ttu-id="d36aa-363">**Rimozione di ZAP**</span><span class="sxs-lookup"><span data-stu-id="d36aa-363">**ZAP removed**</span></span>
- <span data-ttu-id="d36aa-364">**Rilevamento tramite collegamenti sicuri**</span><span class="sxs-lookup"><span data-stu-id="d36aa-364">**Detection by safe links**</span></span>

<span data-ttu-id="d36aa-365">Se si seleziona una riga nella tabella dati, nel riquadro a comparsa viene visualizzata un'ulteriore scomposizione dei conteggi della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d36aa-365">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="d36aa-366">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="d36aa-366">**Export**:</span></span>

<span data-ttu-id="d36aa-367">Quando si fa clic su **Esporta**, in **Opzioni** è possibile selezionare uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="d36aa-367">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="d36aa-368">**Riepilogo (con i dati per gli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="d36aa-368">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="d36aa-369">**Dettagli (con i dati per gli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="d36aa-369">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="d36aa-370">In **Data**scegliere un intervallo e quindi fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-370">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="d36aa-371">I dati relativi ai filtri correnti verranno esportati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="d36aa-371">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="d36aa-372">Ogni file CSV esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="d36aa-372">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="d36aa-373">Se i dati contengono più di 150.000 righe, verranno creati più file CSV.</span><span class="sxs-lookup"><span data-stu-id="d36aa-373">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="d36aa-374">Visualizzazione tecnologia nel rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d36aa-374">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="d36aa-375">Report di posta elettronica inviati e ricevuti</span><span class="sxs-lookup"><span data-stu-id="d36aa-375">Sent and received email report</span></span>

<span data-ttu-id="d36aa-376">Il rapporto **messaggi di posta elettronica inviati e ricevuti** è un report Smart che contiene informazioni sulla posta elettronica in arrivo e in uscita, inclusi i rilevamenti di posta indesiderata, il malware e la posta elettronica identificata come "buona".</span><span class="sxs-lookup"><span data-stu-id="d36aa-376">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="d36aa-377">La differenza tra il report e il [rapporto sullo stato del flusso](#mailflow-status-report) di posta è: questo rapporto non include i dati relativi ai messaggi bloccati dalla protezione Edge. È importante comprendere che se un messaggio viene inviato a cinque destinatari, è necessario contarlo come un solo messaggio.</span><span class="sxs-lookup"><span data-stu-id="d36aa-377">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="d36aa-378">La visualizzazione aggregazione e la visualizzazione dettagli del rapporto consentono 90 giorni di filtraggio.</span><span class="sxs-lookup"><span data-stu-id="d36aa-378">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="d36aa-379">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **invio e ricezione della posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-379">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="d36aa-380">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="d36aa-380">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget messaggi di posta elettronica inviati e ricevuti nel dashboard report](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="d36aa-382">Visualizzazione report per il report di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="d36aa-382">Report view for the Sent and received email report</span></span>

<span data-ttu-id="d36aa-383">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-383">The following charts are available in the report view:</span></span>

- <span data-ttu-id="d36aa-384">**Scomposizione per: tipo**: il grafico Visualizza tutte le categorie disponibili:</span><span class="sxs-lookup"><span data-stu-id="d36aa-384">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="d36aa-385">**Totale**</span><span class="sxs-lookup"><span data-stu-id="d36aa-385">**Total**</span></span>
  - <span data-ttu-id="d36aa-386">**Posta elettronica buona**</span><span class="sxs-lookup"><span data-stu-id="d36aa-386">**Good mail**</span></span>
  - <span data-ttu-id="d36aa-387">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="d36aa-387">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="d36aa-388">**Rilevamenti di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="d36aa-388">**Spam detections**</span></span>
  - <span data-ttu-id="d36aa-389">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="d36aa-389">**Rule messages**</span></span>
  - <span data-ttu-id="d36aa-390">**Malware avanzato** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="d36aa-390">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="d36aa-391">Quando si posiziona il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile visualizzare i dettagli relativi a quel giorno.</span><span class="sxs-lookup"><span data-stu-id="d36aa-391">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Visualizzazione dei tipi nel rapporto posta elettronica inviata e ricevuta](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="d36aa-393">**Suddividi in base a: Direction**: il grafico Visualizza i dati **totali**, in **ingresso**e in **uscita** .</span><span class="sxs-lookup"><span data-stu-id="d36aa-393">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="d36aa-394">Quando si posiziona il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile visualizzare i dettagli relativi a quel giorno.</span><span class="sxs-lookup"><span data-stu-id="d36aa-394">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Visualizzazione direzione nel rapporto posta elettronica inviata e ricevuta](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="d36aa-396">**Drill-down** \> **Malware (anti-malware)**: questa selezione consente di rilevare i [rilevamenti di malware nel rapporto di posta elettronica](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="d36aa-396">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="d36aa-397">**Drill-down** \> **Rilevamenti di posta indesiderata)**: questa selezione porta al [rapporto rilevamento posta indesiderata](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="d36aa-397">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="d36aa-398">Se si fa clic su **filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-398">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="d36aa-399">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d36aa-399">**Start date** and **End date**</span></span>
- <span data-ttu-id="d36aa-400">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="d36aa-400">Direction values</span></span>
- <span data-ttu-id="d36aa-401">Valori dei tipi</span><span class="sxs-lookup"><span data-stu-id="d36aa-401">Type values</span></span>

<span data-ttu-id="d36aa-402">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-402">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="d36aa-403">Visualizzazione della tabella dei dettagli per il report di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="d36aa-403">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="d36aa-404">Se si fa clic su **Visualizza tabella dettagli** nella visualizzazione **scomposizione per: direzione** o **scomposizione per: direzione** , vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-404">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="d36aa-405">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="d36aa-405">**Date (UTC)**</span></span>
- <span data-ttu-id="d36aa-406">**Type**</span><span class="sxs-lookup"><span data-stu-id="d36aa-406">**Type**</span></span>
- <span data-ttu-id="d36aa-407">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="d36aa-407">**Direction**</span></span>
- <span data-ttu-id="d36aa-408">**Numero di messaggi**</span><span class="sxs-lookup"><span data-stu-id="d36aa-408">**Message count**</span></span>

<span data-ttu-id="d36aa-409">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-409">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="d36aa-410">Data di **inizio** e **Data di fine**</span><span class="sxs-lookup"><span data-stu-id="d36aa-410">**Start date** and **End date**</span></span>
- <span data-ttu-id="d36aa-411">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="d36aa-411">Direction values</span></span>
- <span data-ttu-id="d36aa-412">Valori dei tipi</span><span class="sxs-lookup"><span data-stu-id="d36aa-412">Type values</span></span>

<span data-ttu-id="d36aa-413">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-413">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="d36aa-414">Report mittenti e destinatari principali</span><span class="sxs-lookup"><span data-stu-id="d36aa-414">Top senders and recipients report</span></span>

<span data-ttu-id="d36aa-415">Il report **mittenti e destinatari principali** è un grafico a torta che mostra i mittenti e i destinatari di posta elettronica principali.</span><span class="sxs-lookup"><span data-stu-id="d36aa-415">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="d36aa-416">Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare i **mittenti e i destinatari principali**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-416">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="d36aa-417">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="d36aa-417">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget Top Senders and Recipients nel dashboard report](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="d36aa-419">Visualizzazione report per i principali mittenti e report dei destinatari</span><span class="sxs-lookup"><span data-stu-id="d36aa-419">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="d36aa-420">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-420">The following charts are available in the report view:</span></span>

- <span data-ttu-id="d36aa-421">**Visualizzare i dati per i \> mittenti di posta principali**</span><span class="sxs-lookup"><span data-stu-id="d36aa-421">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="d36aa-422">**Visualizzare i dati per i \> destinatari di posta elettronica principali**</span><span class="sxs-lookup"><span data-stu-id="d36aa-422">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="d36aa-423">**Visualizzare i dati per i \> destinatari di posta indesiderata principali**</span><span class="sxs-lookup"><span data-stu-id="d36aa-423">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="d36aa-424">**Visualizzare i dati per \> Destinatari principali di malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="d36aa-424">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="d36aa-425">**Visualizzare i dati per \> Top malware Recipients (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="d36aa-425">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="d36aa-426">La composizione del grafico a torta cambia in base a queste selezioni.</span><span class="sxs-lookup"><span data-stu-id="d36aa-426">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="d36aa-427">Quando si posiziona il puntatore del mouse su un cuneo nel grafico a torta, è possibile visualizzare il numero di messaggi inviati o ricevuti.</span><span class="sxs-lookup"><span data-stu-id="d36aa-427">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="d36aa-428">Se si fa clic su **filtri** in una visualizzazione report, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-428">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Grafico a torta nella visualizzazione report nel report mittenti e destinatari principali](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="d36aa-430">Visualizzazione della tabella Details per i mittenti principali e il report dei destinatari</span><span class="sxs-lookup"><span data-stu-id="d36aa-430">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="d36aa-431">Se si fa clic su **Visualizza tabella dettagli**, le informazioni visualizzate dipendono dal grafico che si sta esaminando:</span><span class="sxs-lookup"><span data-stu-id="d36aa-431">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d36aa-432">**Visualizzare i dati per i \> mittenti di posta principali**</span><span class="sxs-lookup"><span data-stu-id="d36aa-432">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="d36aa-433">**Mittenti di posta principali**</span><span class="sxs-lookup"><span data-stu-id="d36aa-433">**Top mail senders**</span></span>
  - <span data-ttu-id="d36aa-434">**Numero**</span><span class="sxs-lookup"><span data-stu-id="d36aa-434">**Count**</span></span>

- <span data-ttu-id="d36aa-435">**Visualizzare i dati per i \> destinatari di posta elettronica principali**</span><span class="sxs-lookup"><span data-stu-id="d36aa-435">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="d36aa-436">**Destinatari della posta principale**</span><span class="sxs-lookup"><span data-stu-id="d36aa-436">**Top mail recipients**</span></span>
  - <span data-ttu-id="d36aa-437">**Numero**</span><span class="sxs-lookup"><span data-stu-id="d36aa-437">**Count**</span></span>

- <span data-ttu-id="d36aa-438">**Visualizzare i dati per i \> destinatari di posta indesiderata principali**</span><span class="sxs-lookup"><span data-stu-id="d36aa-438">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="d36aa-439">**Destinatari principali di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="d36aa-439">**Top spam recipients**</span></span>
  - <span data-ttu-id="d36aa-440">**Numero**</span><span class="sxs-lookup"><span data-stu-id="d36aa-440">**Count**</span></span>

- <span data-ttu-id="d36aa-441">**Visualizzare i dati per \> Destinatari principali di malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="d36aa-441">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="d36aa-442">**Destinatari principali di malware**</span><span class="sxs-lookup"><span data-stu-id="d36aa-442">**Top malware recipients**</span></span>
  - <span data-ttu-id="d36aa-443">**Numero**</span><span class="sxs-lookup"><span data-stu-id="d36aa-443">**Count**</span></span>

- <span data-ttu-id="d36aa-444">**Visualizzare i dati per \> Top malware Recipients (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="d36aa-444">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="d36aa-445">**Destinatari principali di malware (ATP)**</span><span class="sxs-lookup"><span data-stu-id="d36aa-445">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="d36aa-446">**Numero**</span><span class="sxs-lookup"><span data-stu-id="d36aa-446">**Count**</span></span>

<span data-ttu-id="d36aa-447">Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-447">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d36aa-448">Per tornare alla visualizzazione report, fare clic su **Visualizza report**.</span><span class="sxs-lookup"><span data-stu-id="d36aa-448">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="d36aa-449">Quali autorizzazioni sono necessarie per visualizzare i rapporti?</span><span class="sxs-lookup"><span data-stu-id="d36aa-449">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="d36aa-450">Per visualizzare e utilizzare i report, è necessario essere membri del gruppo di ruoli specificato nel centro sicurezza & conformità **e** in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d36aa-450">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="d36aa-451">Nel centro sicurezza & conformità è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-451">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="d36aa-452">-Organization Management-Security Administrator (è possibile farlo anche nell'interfaccia di [amministrazione di Azure Active Directory](https://aad.portal.azure.com) -Security Reader</span><span class="sxs-lookup"><span data-stu-id="d36aa-452">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="d36aa-453">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="d36aa-453">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="d36aa-454">In Exchange Online, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="d36aa-454">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="d36aa-455">-Gestione organizzazione-solo visualizzazione organizzazione-destinatari di sola visualizzazione-gestione della conformità</span><span class="sxs-lookup"><span data-stu-id="d36aa-455">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="d36aa-456">Per ulteriori informazioni, vedere [autorizzazioni in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) e [gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="d36aa-456">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d36aa-457">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d36aa-457">Related topics</span></span>

[<span data-ttu-id="d36aa-458">Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="d36aa-458">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="d36aa-459">Approfondimenti sul flusso di posta nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="d36aa-459">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="d36aa-460">Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="d36aa-460">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="d36aa-461">Visualizzare i report per Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d36aa-461">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
