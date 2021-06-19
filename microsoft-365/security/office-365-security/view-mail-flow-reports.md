---
title: Visualizzare i report del flusso di posta nel dashboard report
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui report del flusso di posta disponibili nel dashboard Report nel Centro sicurezza & conformità.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5f2bdb32d2afde3d0d40261cd3ecf30740dc0ccf
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029477"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="32479-103">Visualizzare i report del flusso di posta nel dashboard report nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="32479-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="32479-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="32479-104">**Applies to**</span></span>
- [<span data-ttu-id="32479-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="32479-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="32479-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="32479-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="32479-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="32479-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="32479-108">La maggior parte dei report descritti in questo argomento sono disponibili nell'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="32479-108">The majority of the reports that are described in this topic are available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="32479-109">Per ulteriori informazioni, vedere [Mail flow reports in the new Exchange admin center.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="32479-109">For more information, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span> <span data-ttu-id="32479-110">Il [report delle regole di](view-email-security-reports.md#exchange-transport-rule-report) trasporto di Exchange è disponibile nel portale di Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="32479-110">The [Exchange transport rule report](view-email-security-reports.md#exchange-transport-rule-report) is available in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="32479-111">Oltre ai report del flusso di posta disponibili nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza e conformità di &, nel dashboard report sono disponibili diversi report aggiuntivi sul flusso di posta per monitorare l'organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32479-111">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="32479-112">Se si dispone delle [autorizzazioni necessarie,](#what-permissions-are-needed-to-view-these-reports)è possibile visualizzare questi report nel Centro [sicurezza & conformità](https://protection.office.com) andando a Dashboard  \> **report.**</span><span class="sxs-lookup"><span data-stu-id="32479-112">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="32479-113">Per passare direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="32479-113">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard dei report nel Centro sicurezza & conformità](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="32479-115">Report connettore</span><span class="sxs-lookup"><span data-stu-id="32479-115">Connector report</span></span>

<span data-ttu-id="32479-116">Il **report Connettore** mostra l'attività del flusso di posta sui connettori in ingresso [e](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) in uscita configurati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="32479-116">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="32479-117">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Report connettore.**</span><span class="sxs-lookup"><span data-stu-id="32479-117">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="32479-118">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="32479-118">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget report connettore nel dashboard report](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="32479-120">Visualizzazione report per il report Connettore</span><span class="sxs-lookup"><span data-stu-id="32479-120">Report view for the Connector report</span></span>

<span data-ttu-id="32479-121">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-121">The following charts are available in report view:</span></span>

- <span data-ttu-id="32479-122">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span><span class="sxs-lookup"><span data-stu-id="32479-122">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="32479-123">**Totale**</span><span class="sxs-lookup"><span data-stu-id="32479-123">**Total**</span></span>
  - <span data-ttu-id="32479-124">**Da Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="32479-124">**From the internet without a connector**</span></span>
  - <span data-ttu-id="32479-125">**A Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="32479-125">**To the internet without a connector**</span></span>
  - <span data-ttu-id="32479-126">Un connettore specifico configurato.</span><span class="sxs-lookup"><span data-stu-id="32479-126">A specific connector that you've configured.</span></span>

  <span data-ttu-id="32479-127">Per isolare i dati nel grafico, utilizzare il **controllo Mostra dati** per selezionare una di queste opzioni o Tutto il flusso di **posta.**</span><span class="sxs-lookup"><span data-stu-id="32479-127">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Visualizzare i dati in base al flusso di posta nel report Connettore](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="32479-129">**Visualizzare i dati per: utilizzo di TLS**: Questo grafico mostra la percentuale di utilizzo della versione TLS (Transport Layer Security) per il flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="32479-129">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="32479-130">Per isolare i dati nel grafico, utilizzare il **controllo Mostra dati** per selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-130">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="32479-131">**Tutto il flusso di posta**</span><span class="sxs-lookup"><span data-stu-id="32479-131">**All mail flow**</span></span>
  - <span data-ttu-id="32479-132">**Da Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="32479-132">**From the internet without a connector**</span></span>
  - <span data-ttu-id="32479-133">**A Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="32479-133">**To the internet without a connector**</span></span>
  - <span data-ttu-id="32479-134">Un connettore specifico configurato.</span><span class="sxs-lookup"><span data-stu-id="32479-134">A specific connector that you've configured.</span></span>

  ![Visualizzare i dati in base all'utilizzo di TLS nel report Connettore](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="32479-136">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="32479-136">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="32479-137">Visualizzazione tabella dettagli per il report Connettore</span><span class="sxs-lookup"><span data-stu-id="32479-137">Details table view for the Connector report</span></span>

<span data-ttu-id="32479-138">Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-138">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="32479-139">**Data**</span><span class="sxs-lookup"><span data-stu-id="32479-139">**Date**</span></span>
- <span data-ttu-id="32479-140">**Direzione e nome del connettore**</span><span class="sxs-lookup"><span data-stu-id="32479-140">**Connector direction and name**</span></span>
- <span data-ttu-id="32479-141">**Tipo di connettore**</span><span class="sxs-lookup"><span data-stu-id="32479-141">**Connector type**</span></span>
- <span data-ttu-id="32479-142">**TLS forzato?**: Il **valore True** o **False**.</span><span class="sxs-lookup"><span data-stu-id="32479-142">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="32479-143">**Nessun TLS** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="32479-143">**No TLS** (percentage)</span></span>
- <span data-ttu-id="32479-144">**TLS 1.0** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="32479-144">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="32479-145">**TLS 1.1** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="32479-145">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="32479-146">**TLS 1.2** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="32479-146">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="32479-147">**Volume**: numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="32479-147">**Volume**: The number of messages.</span></span>

<span data-ttu-id="32479-148">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="32479-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="32479-149">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="32479-149">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="32479-150">Report delle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="32479-150">Exchange transport rule report</span></span>

<span data-ttu-id="32479-151">Il **rapporto sulle regole di trasporto** di Exchange mostra l'effetto delle regole del flusso di posta (note anche come regole di trasporto) sui messaggi in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="32479-151">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="32479-152">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Regola di trasporto di Exchange.**</span><span class="sxs-lookup"><span data-stu-id="32479-152">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="32479-153">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="32479-153">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget delle regole di trasporto di Exchange nel dashboard dei report](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="32479-155">Visualizzazione dei report per il report delle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="32479-155">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="32479-156">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-156">The following charts are available in report view:</span></span>

- <span data-ttu-id="32479-157">**Visualizzare i dati per: regole di trasporto di Exchange** \> **Scomporsi per: Direzione**: questo grafico  mostra il numero di **messaggi in** ingresso e in uscita interessati dalle regole di trasporto.</span><span class="sxs-lookup"><span data-stu-id="32479-157">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="32479-158">**Visualizzare i dati per: regole di trasporto di Exchange** \> **Scomporsi per: Gravità**: questo grafico mostra il numero **di** messaggi Di gravità elevata e Gravità media e **Gravità** bassa.</span><span class="sxs-lookup"><span data-stu-id="32479-158">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="32479-159">Il livello di gravità viene impostato come azione nella regola **(** Controlla questa regola con livello di gravità o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="32479-159">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="32479-160">Per ulteriori informazioni, vedere [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="32479-160">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="32479-161">**Visualizzare i dati per: regole di trasporto** \> di Exchange DLP **Scomporsi per: Direzione**: questo grafico  mostra il numero di messaggi **in** ingresso e in uscita interessati dalle regole di trasporto dlp (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="32479-161">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="32479-162">È possibile perfezionare ulteriormente il grafico selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-162">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="32479-163">**Mostra dati per: Tutte le regole di trasporto DLP**</span><span class="sxs-lookup"><span data-stu-id="32479-163">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="32479-164">**Mostra dati per: utenti compromessi**</span><span class="sxs-lookup"><span data-stu-id="32479-164">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="32479-165">**Mostra dati per: Basso volume di contenuto rilevato U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="32479-165">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="32479-166">**Visualizzare i dati per: regole di trasporto** \> di Exchange DLP **Scomporsi per: Direzione**:  questa visualizzazione mostra il numero  di messaggi di gravità alta e media **e** di gravità bassa interessati dalle regole di trasporto DLP.</span><span class="sxs-lookup"><span data-stu-id="32479-166">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="32479-167">È possibile perfezionare ulteriormente il grafico selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-167">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="32479-168">**Mostra dati per: Tutte le regole di trasporto DLP**</span><span class="sxs-lookup"><span data-stu-id="32479-168">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="32479-169">**Mostra dati per: utenti compromessi**</span><span class="sxs-lookup"><span data-stu-id="32479-169">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="32479-170">**Mostra dati per: Basso volume di contenuto rilevato U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="32479-170">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="32479-171">Se si fa **clic su Filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-171">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="32479-172">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="32479-172">**Start date** and **End date**</span></span>
- <span data-ttu-id="32479-173">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="32479-173">Direction values</span></span>
- <span data-ttu-id="32479-174">Valori di gravità</span><span class="sxs-lookup"><span data-stu-id="32479-174">Severity values</span></span>

![Visualizzazione dei report nel report delle regole di trasporto di Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="32479-176">Visualizzazione tabella dettagli per il report sulle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="32479-176">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="32479-177">Se si fa **clic su Visualizza tabella** dettagli , le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="32479-177">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="32479-178">**Visualizzare i dati per: Regole di trasporto di Exchange**:</span><span class="sxs-lookup"><span data-stu-id="32479-178">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="32479-179">**Data**</span><span class="sxs-lookup"><span data-stu-id="32479-179">**Date**</span></span>
  - <span data-ttu-id="32479-180">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="32479-180">**Transport rule**</span></span>
  - <span data-ttu-id="32479-181">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="32479-181">**Subject**</span></span>
  - <span data-ttu-id="32479-182">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="32479-182">**Sender address**</span></span>
  - <span data-ttu-id="32479-183">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="32479-183">**Recipient address**</span></span>
  - <span data-ttu-id="32479-184">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="32479-184">**Severity**</span></span>
  - <span data-ttu-id="32479-185">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="32479-185">**Direction**</span></span>

- <span data-ttu-id="32479-186">**Visualizzare i dati per: regole di trasporto di Exchange DLP**:</span><span class="sxs-lookup"><span data-stu-id="32479-186">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="32479-187">**Data**</span><span class="sxs-lookup"><span data-stu-id="32479-187">**Date**</span></span>
  - <span data-ttu-id="32479-188">**Criterio DLP**</span><span class="sxs-lookup"><span data-stu-id="32479-188">**DLP policy**</span></span>
  - <span data-ttu-id="32479-189">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="32479-189">**Transport rule**</span></span>
  - <span data-ttu-id="32479-190">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="32479-190">**Subject**</span></span>
  - <span data-ttu-id="32479-191">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="32479-191">**Sender address**</span></span>
  - <span data-ttu-id="32479-192">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="32479-192">**Recipient address**</span></span>
  - <span data-ttu-id="32479-193">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="32479-193">**Severity**</span></span>
  - <span data-ttu-id="32479-194">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="32479-194">**Direction**</span></span>

<span data-ttu-id="32479-195">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-195">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="32479-196">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="32479-196">**Start date** and **End date**</span></span>
- <span data-ttu-id="32479-197">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="32479-197">Direction values</span></span>
- <span data-ttu-id="32479-198">Valori di gravità</span><span class="sxs-lookup"><span data-stu-id="32479-198">Severity values</span></span>

<span data-ttu-id="32479-199">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="32479-199">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="32479-200">Rapporto di inoltro</span><span class="sxs-lookup"><span data-stu-id="32479-200">Forwarding report</span></span>

<span data-ttu-id="32479-201">Il **rapporto Inoltro mostra** i messaggi inoltrati automaticamente dall'organizzazione a domini esterni da Exchange Online cassette postali.</span><span class="sxs-lookup"><span data-stu-id="32479-201">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="32479-202">I messaggi inoltrati possono rappresentare un rischio per la sicurezza o la conformità e possono indicare un account compromesso.</span><span class="sxs-lookup"><span data-stu-id="32479-202">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="32479-203">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report  \>  e selezionare Report **di inoltro.**</span><span class="sxs-lookup"><span data-stu-id="32479-203">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="32479-204">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="32479-204">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget Di report di inoltro nel dashboard report](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="32479-206">Visualizzazione report per il report di inoltro</span><span class="sxs-lookup"><span data-stu-id="32479-206">Report view for the Forwarding report</span></span>

<span data-ttu-id="32479-207">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-207">The following charts are available in the report view:</span></span>

- <span data-ttu-id="32479-208">**Mostra dati per: Metodi di inoltro**: Vengono visualizzati i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-208">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="32479-209">**Regola di trasporto**: nota anche come [regole del flusso di posta](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="32479-209">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="32479-210">**Regola cassetta postale**: nota anche come [regole di Posta in arrivo.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="32479-210">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Visualizzazione dei metodi di inoltro nel report di inoltro](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="32479-212">**Show data for: Forwarding domains**: Questa visualizzazione mostra i domini dei destinatari che sono le destinazioni per l'inoltro.</span><span class="sxs-lookup"><span data-stu-id="32479-212">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Visualizzazione domini di inoltro nel report di inoltro](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="32479-214">**Mostra dati per: Server d'inoltro**: Vengono visualizzati i seguenti server d'inoltro:</span><span class="sxs-lookup"><span data-stu-id="32479-214">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="32479-215">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="32479-215">**Transport rule**</span></span>
  - <span data-ttu-id="32479-216">Cassetta postale che contiene la regola di posta in arrivo di inoltro.</span><span class="sxs-lookup"><span data-stu-id="32479-216">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Visualizzazione server d'inoltro nel report di inoltro](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="32479-218">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="32479-218">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="32479-219">Visualizzazione tabella dettagli per il report di inoltro</span><span class="sxs-lookup"><span data-stu-id="32479-219">Details table view for the Forwarding report</span></span>

<span data-ttu-id="32479-220">Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-220">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="32479-221">**Server d'inoltro**: valore **Regola di trasporto** o cassetta postale che contiene la regola di posta in arrivo di inoltro.</span><span class="sxs-lookup"><span data-stu-id="32479-221">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="32479-222">**Tipo di inoltro**: Valore **Regola cassetta postale o** Regola di **trasporto.**</span><span class="sxs-lookup"><span data-stu-id="32479-222">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="32479-223">**Nome del destinatario**</span><span class="sxs-lookup"><span data-stu-id="32479-223">**Recipient name**</span></span>
- <span data-ttu-id="32479-224">**Dominio destinatario**</span><span class="sxs-lookup"><span data-stu-id="32479-224">**Recipient domain**</span></span>
- <span data-ttu-id="32479-225">**Dettagli:** si tratta del valore GUID della regola del flusso di posta o del valore RuleIdentity della regola di Posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="32479-225">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="32479-226">**Numero**</span><span class="sxs-lookup"><span data-stu-id="32479-226">**Count**</span></span>
- <span data-ttu-id="32479-227">**Prima data di inoltro**</span><span class="sxs-lookup"><span data-stu-id="32479-227">**First forward date**</span></span>

<span data-ttu-id="32479-228">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="32479-228">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="32479-229">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="32479-229">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="32479-230">Rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="32479-230">Mailflow status report</span></span>

<span data-ttu-id="32479-231">La **relazione sullo stato del flusso di** posta è simile al [rapporto](#sent-and-received-email-report)Posta inviata e ricevuta, con ulteriori informazioni sulla posta elettronica consentita o bloccata sul perimetro.</span><span class="sxs-lookup"><span data-stu-id="32479-231">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="32479-232">Questo è l'unico report che contiene informazioni sulla protezione perimetrale e mostra la quantità di posta elettronica bloccata prima di essere consentita al servizio per la valutazione da parte di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="32479-232">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="32479-233">È importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.</span><span class="sxs-lookup"><span data-stu-id="32479-233">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="32479-234">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e  \>  selezionare Report stato flusso **di posta**.</span><span class="sxs-lookup"><span data-stu-id="32479-234">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="32479-235">Per passare direttamente alla relazione **sullo stato del flusso di posta,** aprire <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="32479-235">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget rapporto sullo stato del flusso di posta nel dashboard report](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="32479-237">Visualizzazione tipo per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="32479-237">Type view for the Mailflow status report</span></span>

<span data-ttu-id="32479-238">Quando si apre il report, la **scheda Tipo** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="32479-238">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="32479-239">Per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-239">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="32479-240">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="32479-240">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="32479-241">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="32479-241">**Direction**:</span></span>

  - <span data-ttu-id="32479-242">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="32479-242">**Inbound**</span></span>
  - <span data-ttu-id="32479-243">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="32479-243">**Outbound**</span></span>
  - <span data-ttu-id="32479-244">**Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="32479-244">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="32479-245">mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da **In ingresso** e **In uscita)**</span><span class="sxs-lookup"><span data-stu-id="32479-245">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="32479-246">**Digitare**:</span><span class="sxs-lookup"><span data-stu-id="32479-246">**Type**:</span></span>

  - <span data-ttu-id="32479-247">**Posta buona**</span><span class="sxs-lookup"><span data-stu-id="32479-247">**Good mail**</span></span>
  - <span data-ttu-id="32479-248">**Malware**</span><span class="sxs-lookup"><span data-stu-id="32479-248">**Malware**</span></span>
  - <span data-ttu-id="32479-249">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="32479-249">**Spam**</span></span>
  - <span data-ttu-id="32479-250">**Protezione edge**</span><span class="sxs-lookup"><span data-stu-id="32479-250">**Edge protection**</span></span>
  - <span data-ttu-id="32479-251">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="32479-251">**Rule messages**</span></span>
  - <span data-ttu-id="32479-252">**Posta di phishing**</span><span class="sxs-lookup"><span data-stu-id="32479-252">**Phishing email**</span></span>

<span data-ttu-id="32479-253">Il grafico è organizzato in base ai **valori Type.**</span><span class="sxs-lookup"><span data-stu-id="32479-253">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="32479-254">È possibile modificare questi filtri facendo clic **su Filtro** o su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="32479-254">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="32479-255">La tabella dati contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-255">The data table contains the following information:</span></span>

- <span data-ttu-id="32479-256">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="32479-256">**Direction**</span></span>
- <span data-ttu-id="32479-257">**Type**</span><span class="sxs-lookup"><span data-stu-id="32479-257">**Type**</span></span>
- <span data-ttu-id="32479-258">**24 ore**</span><span class="sxs-lookup"><span data-stu-id="32479-258">**24 hours**</span></span>
- <span data-ttu-id="32479-259">**3 giorni**</span><span class="sxs-lookup"><span data-stu-id="32479-259">**3 days**</span></span>
- <span data-ttu-id="32479-260">**7 giorni**</span><span class="sxs-lookup"><span data-stu-id="32479-260">**7 days**</span></span>
- <span data-ttu-id="32479-261">**15 giorni**</span><span class="sxs-lookup"><span data-stu-id="32479-261">**15 days**</span></span>
- <span data-ttu-id="32479-262">**30 giorni**</span><span class="sxs-lookup"><span data-stu-id="32479-262">**30 days**</span></span>

<span data-ttu-id="32479-263">Se si fa **clic su Scegli una categoria per ulteriori dettagli,** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-263">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="32479-264">**Posta elettronica di phishing**: questa selezione consente di visualizzare il [rapporto sullo stato di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="32479-264">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="32479-265">**Malware nella posta elettronica**: questa selezione consente di visualizzare il [rapporto sullo stato di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="32479-265">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="32479-266">**Rilevamenti di posta indesiderata:** questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="32479-266">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="32479-267">**Posta indesiderata bloccata** perimetrali : questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="32479-267">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="32479-268">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="32479-268">**Export**:</span></span>

<span data-ttu-id="32479-269">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="32479-269">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="32479-270">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.</span><span class="sxs-lookup"><span data-stu-id="32479-270">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="32479-271">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="32479-271">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="32479-272">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="32479-272">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione tipo nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="32479-274">Visualizzazione della direzione per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="32479-274">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="32479-275">Se si fa clic **sulla scheda Direzione,** vengono utilizzati gli stessi filtri predefiniti della **visualizzazione** Tipo.</span><span class="sxs-lookup"><span data-stu-id="32479-275">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="32479-276">Il grafico è organizzato in base **ai valori di** Direzione.</span><span class="sxs-lookup"><span data-stu-id="32479-276">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="32479-277">È possibile modificare questi filtri facendo clic **su Filtro** o su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="32479-277">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="32479-278">Vengono utilizzati gli stessi filtri **della** visualizzazione Tipo.</span><span class="sxs-lookup"><span data-stu-id="32479-278">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="32479-279">La tabella dati contiene le stesse informazioni della **visualizzazione Tipo.**</span><span class="sxs-lookup"><span data-stu-id="32479-279">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="32479-280">**L'opzione Scegliere una categoria per ulteriori dettagli** le selezioni e il comportamento disponibili sono gli stessi della visualizzazione **Tipo.**</span><span class="sxs-lookup"><span data-stu-id="32479-280">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="32479-281">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="32479-281">**Export**:</span></span>

<span data-ttu-id="32479-282">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="32479-282">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="32479-283">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.</span><span class="sxs-lookup"><span data-stu-id="32479-283">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="32479-284">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="32479-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="32479-285">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="32479-285">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione direzione nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="32479-287">Visualizzazione imbuto per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="32479-287">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="32479-288">La **visualizzazione Imbuto** mostra come le funzionalità di protezione dalle minacce di posta elettronica di Microsoft filtrano la posta elettronica in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="32479-288">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="32479-289">Fornisce informazioni dettagliate sul conteggio totale della posta elettronica e sul modo in cui le funzionalità di protezione dalle minacce configurate, tra cui protezione perimetrale, antimalware, anti-phishing, protezione da posta indesiderata e anti-spoofing influiscono su questo conteggio.</span><span class="sxs-lookup"><span data-stu-id="32479-289">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="32479-290">Se si fa clic sulla scheda **Imbuto,** per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-290">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="32479-291">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="32479-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="32479-292">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="32479-292">**Direction**:</span></span>

  - <span data-ttu-id="32479-293">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="32479-293">**Inbound**</span></span>
  - <span data-ttu-id="32479-294">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="32479-294">**Outbound**</span></span>
  - <span data-ttu-id="32479-295">**Intra-org:** questo conteggio è per i messaggi inviati all'interno di un tenant; Ad esempio, il mittente abc@domain.com inviato al destinatario xyz@domain.com (conteggiato separatamente da Inbound e Outbound).</span><span class="sxs-lookup"><span data-stu-id="32479-295">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="32479-296">La visualizzazione aggregata e la visualizzazione tabella dati consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="32479-296">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="32479-297">Se si fa **clic su Filtro**, è possibile filtrare sia il grafico che la tabella dati.</span><span class="sxs-lookup"><span data-stu-id="32479-297">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="32479-298">Questo grafico mostra il numero di messaggi di posta elettronica organizzati per:</span><span class="sxs-lookup"><span data-stu-id="32479-298">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="32479-299">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="32479-299">**Total email**</span></span>
- <span data-ttu-id="32479-300">**Posta elettronica dopo la protezione edge**</span><span class="sxs-lookup"><span data-stu-id="32479-300">**Email after edge protection**</span></span>
- <span data-ttu-id="32479-301">**Posta elettronica dopo antimalware, reputazione file, blocco del tipo di file**</span><span class="sxs-lookup"><span data-stu-id="32479-301">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="32479-302">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="32479-302">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="32479-303">**Posta elettronica dopo la posta indesiderata, filtro posta in blocco**</span><span class="sxs-lookup"><span data-stu-id="32479-303">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="32479-304">**Posta elettronica dopo la rappresentazione di dominio e utente**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="32479-304">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="32479-305">**Posta elettronica dopo la detonazione di file e URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="32479-305">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="32479-306">**Email detected as benign after post-delivery protection (URL click time protection)**</span><span class="sxs-lookup"><span data-stu-id="32479-306">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="32479-307"><sup>1</sup> Defender per Office 365 solo</span><span class="sxs-lookup"><span data-stu-id="32479-307"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="32479-308">Per visualizzare il messaggio di posta elettronica filtrato da EOP o Defender per Office 365 separatamente, fare clic sul valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="32479-308">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="32479-309">La tabella dei dati contiene le informazioni seguenti, visualizzate in ordine di data decrescente:</span><span class="sxs-lookup"><span data-stu-id="32479-309">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="32479-310">**Data**</span><span class="sxs-lookup"><span data-stu-id="32479-310">**Date**</span></span>
- <span data-ttu-id="32479-311">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="32479-311">**Total email**</span></span>
- <span data-ttu-id="32479-312">**Protezione edge**</span><span class="sxs-lookup"><span data-stu-id="32479-312">**Edge protection**</span></span>
- <span data-ttu-id="32479-313">**Antimalware, reputazione file, blocco del tipo di file**:</span><span class="sxs-lookup"><span data-stu-id="32479-313">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="32479-314">**Reputazione file:** messaggi filtrati a causa dell'identificazione di un file allegato da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32479-314">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="32479-315">**Blocco del tipo di** file : Messaggi filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="32479-315">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="32479-316">**Anti-phish, reputazione URL, rappresentazione del marchio, anti-spoofing**:</span><span class="sxs-lookup"><span data-stu-id="32479-316">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="32479-317">**Reputazione URL**: Messaggi filtrati a causa dell'identificazione dell'URL da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="32479-317">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="32479-318">**Rappresentazione del marchio**: messaggi filtrati a causa del messaggio proveniente da mittenti noti che rappresentano il marchio.</span><span class="sxs-lookup"><span data-stu-id="32479-318">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="32479-319">**Anti-spoof**: messaggi filtrati a causa del tentativo di spoofing di un dominio a cui appartiene il destinatario o di un dominio di cui il mittente non è proprietario.</span><span class="sxs-lookup"><span data-stu-id="32479-319">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="32479-320">**Protezione da posta indesiderata, filtro posta in blocco**:</span><span class="sxs-lookup"><span data-stu-id="32479-320">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="32479-321">**Filtro posta in blocco**: Messaggi filtrati a causa di un tentativo di recapitare la posta in blocco ai destinatari.</span><span class="sxs-lookup"><span data-stu-id="32479-321">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="32479-322">**Rappresentazione utente e dominio (Defender per Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="32479-322">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="32479-323">**Rappresentazione utente**: messaggi filtrati a causa di un tentativo di rappresentazione di un utente (mittente del messaggio) definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="32479-323">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="32479-324">**Rappresentazione di dominio**: messaggi filtrati a causa di un tentativo di rappresentare un dominio definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="32479-324">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="32479-325">**Detonazione di file e URL (Defender per Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="32479-325">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="32479-326">**Detonazione file:** messaggi filtrati da un criterio Safe allegati.</span><span class="sxs-lookup"><span data-stu-id="32479-326">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="32479-327">**Detonazione URL:** messaggio filtrato in base a un Safe dei collegamenti.</span><span class="sxs-lookup"><span data-stu-id="32479-327">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="32479-328">**Protezione post-recapito e ZAP (ATP) o ZAP (EOP):** ZAP indica l'eliminazione automatica a zero ore.</span><span class="sxs-lookup"><span data-stu-id="32479-328">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="32479-329">Se si seleziona una riga nella tabella dati, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="32479-329">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="32479-330">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="32479-330">**Export**:</span></span>

<span data-ttu-id="32479-331">Dopo aver fatto **clic su** Esporta **in Opzioni,** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-331">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="32479-332">**Riepilogo (con i dati degli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="32479-332">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="32479-333">**Dettagli (con dati degli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="32479-333">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="32479-334">In **Data** scegliere un intervallo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="32479-334">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="32479-335">I dati per i filtri correnti verranno esportati in un .csv file.</span><span class="sxs-lookup"><span data-stu-id="32479-335">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="32479-336">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="32479-336">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="32479-337">Se i dati contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="32479-337">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Visualizzazione Imbuto nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="32479-339">Visualizzazione tecnica per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="32479-339">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="32479-340">La **visualizzazione Tech** è simile alla visualizzazione **Imbuto,** fornendo dettagli più dettagliati per le funzionalità di protezione dalle minacce configurate.</span><span class="sxs-lookup"><span data-stu-id="32479-340">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="32479-341">Dal grafico è possibile vedere come i messaggi vengono categorizzati nelle diverse fasi della protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="32479-341">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="32479-342">Se si fa clic **sulla scheda Visualizzazione tecnica,** per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-342">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="32479-343">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="32479-343">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="32479-344">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="32479-344">**Direction**:</span></span>

  - <span data-ttu-id="32479-345">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="32479-345">**Inbound**</span></span>
  - <span data-ttu-id="32479-346">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="32479-346">**Outbound**</span></span>
  - <span data-ttu-id="32479-347">**Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="32479-347">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="32479-348">mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da in ingresso e in uscita)</span><span class="sxs-lookup"><span data-stu-id="32479-348">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="32479-349">La visualizzazione aggregata e la visualizzazione tabella dati consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="32479-349">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="32479-350">Se si fa **clic su Filtro**, è possibile filtrare sia il grafico che la tabella dati.</span><span class="sxs-lookup"><span data-stu-id="32479-350">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="32479-351">Questo grafico mostra i messaggi organizzati nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-351">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="32479-352">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="32479-352">**Total email**</span></span>
- <span data-ttu-id="32479-353">**Edge allow** e **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="32479-353">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="32479-354">**Non malware,** **Safe allegati,** <sup>\*</sup> **rilevamento motore antimalware** e **messaggi di regola**</span><span class="sxs-lookup"><span data-stu-id="32479-354">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="32479-355">**Not phish,** **DMARC failure,** **Impersonation detection,** **Spoof detection** e **Phish detection**</span><span class="sxs-lookup"><span data-stu-id="32479-355">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="32479-356">**Nessun rilevamento con detonazione URL e** **rilevamento detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="32479-356">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="32479-357">**Non posta indesiderata** e  **posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="32479-357">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="32479-358">**Posta elettronica non dannosa,** **rilevamento Safe** <sup>\*</sup> collegamenti e **ZAP**</span><span class="sxs-lookup"><span data-stu-id="32479-358">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="32479-359"><sup>\*</sup>Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="32479-359"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="32479-360">Quando si passa il mouse su una categoria nel grafico, è possibile visualizzare il numero di messaggi in tale categoria.</span><span class="sxs-lookup"><span data-stu-id="32479-360">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="32479-361">La tabella dei dati contiene le informazioni seguenti, visualizzate in ordine di data decrescente:</span><span class="sxs-lookup"><span data-stu-id="32479-361">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="32479-362">**Data**</span><span class="sxs-lookup"><span data-stu-id="32479-362">**Date**</span></span>
- <span data-ttu-id="32479-363">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="32479-363">**Total email**</span></span>
- <span data-ttu-id="32479-364">**Edge filtrato**</span><span class="sxs-lookup"><span data-stu-id="32479-364">**Edge filtered**</span></span>
- <span data-ttu-id="32479-365">**Motore antimalware, Safe allegati, regola filtrata:**</span><span class="sxs-lookup"><span data-stu-id="32479-365">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="32479-366">**Regola filtrata**: Messaggi filtrati a causa delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="32479-366">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="32479-367">**DMARC, rappresentazione, spoofing, phish filtrato**:</span><span class="sxs-lookup"><span data-stu-id="32479-367">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="32479-368">**DMARC**: Messaggi filtrati a causa dell'errore del messaggio nel controllo di autenticazione DMARC.</span><span class="sxs-lookup"><span data-stu-id="32479-368">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="32479-369">**Rilevamento detonazione URL**</span><span class="sxs-lookup"><span data-stu-id="32479-369">**URL detonation detection**</span></span>
- <span data-ttu-id="32479-370">**Protezione da posta indesiderata filtrata**</span><span class="sxs-lookup"><span data-stu-id="32479-370">**Anti-spam filtered**</span></span>
- <span data-ttu-id="32479-371">**ZAP rimosso**</span><span class="sxs-lookup"><span data-stu-id="32479-371">**ZAP removed**</span></span>
- <span data-ttu-id="32479-372">**Rilevamento da Safe collegamenti**</span><span class="sxs-lookup"><span data-stu-id="32479-372">**Detection by Safe Links**</span></span>

<span data-ttu-id="32479-373">Se si seleziona una riga nella tabella dati, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="32479-373">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="32479-374">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="32479-374">**Export**:</span></span>

<span data-ttu-id="32479-375">Facendo clic **su Esporta,** in **Opzioni** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-375">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="32479-376">**Riepilogo (con i dati degli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="32479-376">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="32479-377">**Dettagli (con dati degli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="32479-377">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="32479-378">In **Data** scegliere un intervallo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="32479-378">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="32479-379">I dati per i filtri correnti verranno esportati in un .csv file.</span><span class="sxs-lookup"><span data-stu-id="32479-379">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="32479-380">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="32479-380">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="32479-381">Se i dati contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="32479-381">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Visualizzazione tecnica nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="32479-383">Rapporto di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="32479-383">Sent and received email report</span></span>

<span data-ttu-id="32479-384">Il **report Posta inviata e** ricevuta è un report intelligente che mostra le informazioni sulla posta elettronica in arrivo e in uscita, inclusi i rilevamenti di posta indesiderata, il malware e la posta elettronica identificata come "buona".</span><span class="sxs-lookup"><span data-stu-id="32479-384">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="32479-385">La differenza tra questo report e la relazione sullo stato [del flusso](#mailflow-status-report) di posta è che non include i dati sui messaggi bloccati dalla protezione perimetrale.</span><span class="sxs-lookup"><span data-stu-id="32479-385">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="32479-386">**Nota:** è importante comprendere che se un messaggio viene inviato a cinque destinatari viene conteggiato come un unico messaggio.</span><span class="sxs-lookup"><span data-stu-id="32479-386">**Note**: It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="32479-387">La visualizzazione aggregata e la visualizzazione dettagli del report consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="32479-387">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="32479-388">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e selezionare Posta elettronica inviata  \>  **e ricevuta.**</span><span class="sxs-lookup"><span data-stu-id="32479-388">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="32479-389">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="32479-389">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget Posta elettronica inviata e ricevuta nel dashboard report](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="32479-391">Visualizzazione report per il report Di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="32479-391">Report view for the Sent and received email report</span></span>

<span data-ttu-id="32479-392">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-392">The following charts are available in the report view:</span></span>

- <span data-ttu-id="32479-393">**Scomporsi per: Tipo**: Il grafico mostra tutte le categorie disponibili:</span><span class="sxs-lookup"><span data-stu-id="32479-393">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="32479-394">**Totale**</span><span class="sxs-lookup"><span data-stu-id="32479-394">**Total**</span></span>
  - <span data-ttu-id="32479-395">**Posta buona**</span><span class="sxs-lookup"><span data-stu-id="32479-395">**Good mail**</span></span>
  - <span data-ttu-id="32479-396">**Malware (antimalware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="32479-396">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="32479-397">**Rilevamenti di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="32479-397">**Spam detections**</span></span>
  - <span data-ttu-id="32479-398">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="32479-398">**Rule messages**</span></span>
  - <span data-ttu-id="32479-399">**Malware avanzato** (Microsoft Defender per Office 365)</span><span class="sxs-lookup"><span data-stu-id="32479-399">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="32479-400">Quando si passa il mouse su un giorno (punto dati) nel grafico, è possibile visualizzare i dettagli per tale giorno.</span><span class="sxs-lookup"><span data-stu-id="32479-400">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Digitare la visualizzazione nel report Posta elettronica inviata e ricevuta](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="32479-402">**Scomporsi per: Direzione**: il grafico mostra **i dati totali,** in **ingresso** **e in** uscita.</span><span class="sxs-lookup"><span data-stu-id="32479-402">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="32479-403">Quando si passa il mouse su un giorno (punto dati) nel grafico, è possibile visualizzare i dettagli per tale giorno.</span><span class="sxs-lookup"><span data-stu-id="32479-403">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Visualizzazione della direzione nel report Posta inviata e ricevuta](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="32479-405">**Drill-down per** \> **Malware (antimalware):** questa selezione consente di accedere al [report Rilevamenti malware.](view-email-security-reports.md#malware-detections-report)</span><span class="sxs-lookup"><span data-stu-id="32479-405">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections report](view-email-security-reports.md#malware-detections-report).</span></span>

- <span data-ttu-id="32479-406">**Drill-down per** \> **Rilevamenti posta indesiderata):** questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="32479-406">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="32479-407">Se si fa **clic su Filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-407">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="32479-408">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="32479-408">**Start date** and **End date**</span></span>
- <span data-ttu-id="32479-409">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="32479-409">Direction values</span></span>
- <span data-ttu-id="32479-410">Valori di tipo</span><span class="sxs-lookup"><span data-stu-id="32479-410">Type values</span></span>

<span data-ttu-id="32479-411">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="32479-411">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="32479-412">Visualizzazione tabella dettagli per il report Posta inviata e ricevuta</span><span class="sxs-lookup"><span data-stu-id="32479-412">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="32479-413">Se si fa **clic su Visualizza tabella dettagli** nella visualizzazione Scomposi **per: Direzione** o Scomparti **per:** Direzione, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-413">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="32479-414">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="32479-414">**Date (UTC)**</span></span>
- <span data-ttu-id="32479-415">**Type**</span><span class="sxs-lookup"><span data-stu-id="32479-415">**Type**</span></span>
- <span data-ttu-id="32479-416">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="32479-416">**Direction**</span></span>
- <span data-ttu-id="32479-417">**Conteggio messaggi**</span><span class="sxs-lookup"><span data-stu-id="32479-417">**Message count**</span></span>

<span data-ttu-id="32479-418">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-418">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="32479-419">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="32479-419">**Start date** and **End date**</span></span>
- <span data-ttu-id="32479-420">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="32479-420">Direction values</span></span>
- <span data-ttu-id="32479-421">Valori di tipo</span><span class="sxs-lookup"><span data-stu-id="32479-421">Type values</span></span>

<span data-ttu-id="32479-422">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="32479-422">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="32479-423">Rapporto Mittenti e destinatari principali</span><span class="sxs-lookup"><span data-stu-id="32479-423">Top senders and recipients report</span></span>

<span data-ttu-id="32479-424">Il **report Mittenti e destinatari** principali è un grafico a torta che mostra i mittenti e i destinatari di posta elettronica principali.</span><span class="sxs-lookup"><span data-stu-id="32479-424">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="32479-425">Per visualizzare il report, aprire il Centro [sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e  \>  selezionare **Mittenti e destinatari principali.**</span><span class="sxs-lookup"><span data-stu-id="32479-425">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="32479-426">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="32479-426">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget Mittenti e destinatari principali nel dashboard dei report](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="32479-428">Visualizzazione report per il rapporto Mittenti principali e destinatari</span><span class="sxs-lookup"><span data-stu-id="32479-428">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="32479-429">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="32479-429">The following charts are available in the report view:</span></span>

- <span data-ttu-id="32479-430">**Mostra i dati per \> i principali mittenti di posta**</span><span class="sxs-lookup"><span data-stu-id="32479-430">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="32479-431">**Visualizzare i dati per \> i destinatari di posta elettronica principali**</span><span class="sxs-lookup"><span data-stu-id="32479-431">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="32479-432">**Visualizzare i dati per \> i destinatari principali della posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="32479-432">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="32479-433">**Mostra dati per \> Principali destinatari di malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="32479-433">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="32479-434">**Visualizzare i dati \> per i destinatari principali di malware (Defender per Office 365)**</span><span class="sxs-lookup"><span data-stu-id="32479-434">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="32479-435">La composizione del grafico a torta cambia in base a queste selezioni.</span><span class="sxs-lookup"><span data-stu-id="32479-435">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="32479-436">Quando si passa il mouse su un cuneo nel grafico a torta, è possibile visualizzare un conteggio dei messaggi inviati o ricevuti.</span><span class="sxs-lookup"><span data-stu-id="32479-436">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="32479-437">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="32479-437">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Grafico a torta nella visualizzazione Report nel report Mittenti e destinatari principali](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="32479-439">Visualizzazione tabella dettagli per il rapporto Mittenti principali e destinatari</span><span class="sxs-lookup"><span data-stu-id="32479-439">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="32479-440">Se si fa **clic su Visualizza tabella** dettagli , le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="32479-440">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="32479-441">**Mostra i dati per \> i principali mittenti di posta**</span><span class="sxs-lookup"><span data-stu-id="32479-441">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="32479-442">**Principali mittenti di posta**</span><span class="sxs-lookup"><span data-stu-id="32479-442">**Top mail senders**</span></span>
  - <span data-ttu-id="32479-443">**Numero**</span><span class="sxs-lookup"><span data-stu-id="32479-443">**Count**</span></span>

- <span data-ttu-id="32479-444">**Visualizzare i dati per \> i destinatari di posta elettronica principali**</span><span class="sxs-lookup"><span data-stu-id="32479-444">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="32479-445">**Destinatari di posta elettronica principali**</span><span class="sxs-lookup"><span data-stu-id="32479-445">**Top mail recipients**</span></span>
  - <span data-ttu-id="32479-446">**Numero**</span><span class="sxs-lookup"><span data-stu-id="32479-446">**Count**</span></span>

- <span data-ttu-id="32479-447">**Visualizzare i dati per \> i destinatari principali della posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="32479-447">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="32479-448">**Principali destinatari di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="32479-448">**Top spam recipients**</span></span>
  - <span data-ttu-id="32479-449">**Numero**</span><span class="sxs-lookup"><span data-stu-id="32479-449">**Count**</span></span>

- <span data-ttu-id="32479-450">**Mostra dati per \> Principali destinatari di malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="32479-450">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="32479-451">**Principali destinatari di malware**</span><span class="sxs-lookup"><span data-stu-id="32479-451">**Top malware recipients**</span></span>
  - <span data-ttu-id="32479-452">**Numero**</span><span class="sxs-lookup"><span data-stu-id="32479-452">**Count**</span></span>

- <span data-ttu-id="32479-453">**Visualizzare i dati \> per i destinatari principali di malware (Defender per Office 365)**</span><span class="sxs-lookup"><span data-stu-id="32479-453">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="32479-454">**Principali destinatari di malware (Defender per Office 365)**</span><span class="sxs-lookup"><span data-stu-id="32479-454">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="32479-455">**Numero**</span><span class="sxs-lookup"><span data-stu-id="32479-455">**Count**</span></span>

<span data-ttu-id="32479-456">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="32479-456">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="32479-457">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="32479-457">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="32479-458">Quali autorizzazioni sono necessarie per visualizzare questi report?</span><span class="sxs-lookup"><span data-stu-id="32479-458">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="32479-459">Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="32479-459">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="32479-460">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="32479-460">**Organization Management**</span></span>
- <span data-ttu-id="32479-461">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="32479-461">**Security Administrator**</span></span>
- <span data-ttu-id="32479-462">**Lettore sicurezza**</span><span class="sxs-lookup"><span data-stu-id="32479-462">**Security Reader**</span></span>
- <span data-ttu-id="32479-463">**Lettore globale**</span><span class="sxs-lookup"><span data-stu-id="32479-463">**Global Reader**</span></span>

<span data-ttu-id="32479-464">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="32479-464">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="32479-465">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32479-465">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="32479-466">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="32479-466">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="32479-467">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="32479-467">Related topics</span></span>

[<span data-ttu-id="32479-468">Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="32479-468">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="32479-469">Approfondimenti sul flusso di posta nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="32479-469">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="32479-470">Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="32479-470">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="32479-471">Visualizzare i report per Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="32479-471">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
