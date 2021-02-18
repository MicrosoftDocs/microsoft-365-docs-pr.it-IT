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
ms.openlocfilehash: dbbec056203ad816d37f5451115d2c7d172eee92
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286718"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="d7ff8-103">Visualizzare i report del flusso di posta nel dashboard report nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="d7ff8-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d7ff8-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-104">**Applies to**</span></span>
- [<span data-ttu-id="d7ff8-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d7ff8-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d7ff8-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="d7ff8-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d7ff8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7ff8-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="d7ff8-108">Oltre ai report del flusso di posta disponibili nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza & conformità, nel dashboard dei report sono disponibili diversi report aggiuntivi sul flusso di posta per monitorare l'organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="d7ff8-109">Se si dispone delle [autorizzazioni necessarie,](#what-permissions-are-needed-to-view-these-reports)è possibile visualizzare questi report nel Centro [sicurezza & conformità](https://protection.office.com) selezionando Dashboard  \> **report.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="d7ff8-110">Per passare direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="d7ff8-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard report nel Centro sicurezza & conformità](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="d7ff8-112">Rapporto connettore</span><span class="sxs-lookup"><span data-stu-id="d7ff8-112">Connector report</span></span>

<span data-ttu-id="d7ff8-113">Il **rapporto Connettore** mostra l'attività del flusso di posta sui connettori [in](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) ingresso e in uscita configurati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="d7ff8-114">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **al** \> **dashboard dei report** e selezionare il **report Connettore.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="d7ff8-115">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="d7ff8-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget report connettore nel dashboard report](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="d7ff8-117">Visualizzazione rapporto per il report connettore</span><span class="sxs-lookup"><span data-stu-id="d7ff8-117">Report view for the Connector report</span></span>

<span data-ttu-id="d7ff8-118">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="d7ff8-119">**Visualizzare i dati per: Flusso di posta**: questo grafico mostra il numero di messaggi in ingresso e in uscita organizzati per:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="d7ff8-120">**Totale**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-120">**Total**</span></span>
  - <span data-ttu-id="d7ff8-121">**Da Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="d7ff8-122">**A Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="d7ff8-123">Un connettore specifico configurato.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="d7ff8-124">Per isolare i dati nel grafico, utilizzare il controllo Mostra **dati** per selezionare una di queste opzioni o **Tutto il flusso di posta.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Visualizzare i dati in base al flusso di posta nel report del connettore](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="d7ff8-126">**Visualizzare i dati in base all'utilizzo di TLS:** questo grafico mostra la percentuale di utilizzo della versione TLS (Transport Layer Security) per il flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="d7ff8-127">Per isolare i dati nel grafico, utilizzare il **controllo Mostra dati** per selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="d7ff8-128">**Tutto il flusso di posta**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-128">**All mail flow**</span></span>
  - <span data-ttu-id="d7ff8-129">**Da Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="d7ff8-130">**A Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="d7ff8-131">Un connettore specifico configurato.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-131">A specific connector that you've configured.</span></span>

  ![Visualizzare i dati in base all'utilizzo di TLS nel report del connettore](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="d7ff8-133">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="d7ff8-134">Visualizzazione della tabella dei dettagli per il report connettore</span><span class="sxs-lookup"><span data-stu-id="d7ff8-134">Details table view for the Connector report</span></span>

<span data-ttu-id="d7ff8-135">Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="d7ff8-136">**Data**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-136">**Date**</span></span>
- <span data-ttu-id="d7ff8-137">**Direzione e nome del connettore**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-137">**Connector direction and name**</span></span>
- <span data-ttu-id="d7ff8-138">**Tipo di connettore**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-138">**Connector type**</span></span>
- <span data-ttu-id="d7ff8-139">**TLS forzato?**: Il **valore True** o **False.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="d7ff8-140">**Nessun TLS** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="d7ff8-141">**TLS 1,0** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="d7ff8-142">**TLS 1.1** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="d7ff8-143">**TLS 1,2** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="d7ff8-144">**Volume**: numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="d7ff8-145">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d7ff8-146">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="d7ff8-147">Rapporto delle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="d7ff8-147">Exchange transport rule report</span></span>

<span data-ttu-id="d7ff8-148">Il **rapporto sulle regole di trasporto** di Exchange mostra l'effetto delle regole del flusso di posta (note anche come regole di trasporto) sui messaggi in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="d7ff8-149">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **al** \> **dashboard dei** report e selezionare la regola di trasporto **di Exchange.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="d7ff8-150">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="d7ff8-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget della regola di trasporto di Exchange nel dashboard dei rapporti](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="d7ff8-152">Visualizzazione rapporto per il rapporto delle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="d7ff8-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="d7ff8-153">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="d7ff8-154">**Visualizzare i dati per: regole di trasporto di Exchange** \> **Scomporsi per: Direzione:** questo grafico  mostra il numero di **messaggi in** ingresso e in uscita interessati dalle regole di trasporto.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="d7ff8-155">**Visualizzare i dati per: regole di trasporto di Exchange** \> **Scomporsi per: Gravità:** questo  grafico mostra il numero  di messaggi di gravità alta e media **e** bassa.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="d7ff8-156">Il livello di gravità viene impostato come azione nella regola **(** Controlla questa regola con livello di gravità o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="d7ff8-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="d7ff8-157">Per ulteriori informazioni, vedere Azioni delle regole [del flusso di posta in Exchange Online.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-157">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="d7ff8-158">**Visualizzare i dati da: regole di trasporto di Exchange DLP** \> **Scomporsi per: Direzione:** questo grafico  mostra il numero di messaggi **in** ingresso e in uscita interessati dalle regole di trasporto di prevenzione della perdita di dati (DLP).</span><span class="sxs-lookup"><span data-stu-id="d7ff8-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="d7ff8-159">È possibile perfezionare ulteriormente il grafico selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="d7ff8-160">**Mostra dati per: Tutte le regole di trasporto DLP**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="d7ff8-161">**Mostrare i dati per: utenti compromessi**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="d7ff8-162">**Mostra dati per: Basso volume di contenuto rilevato U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="d7ff8-163">**Visualizzare i dati da: regole di trasporto di Exchange DLP** \> **Scomporsi per: Direzione:** questa visualizzazione mostra il numero  di messaggi di gravità alta e media e di gravità bassa interessati dalle regole di trasporto DLP. </span><span class="sxs-lookup"><span data-stu-id="d7ff8-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="d7ff8-164">È possibile perfezionare ulteriormente il grafico selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="d7ff8-165">**Mostra dati per: Tutte le regole di trasporto DLP**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="d7ff8-166">**Mostrare i dati per: utenti compromessi**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="d7ff8-167">**Mostra dati per: Basso volume di contenuto rilevato U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="d7ff8-168">Se si fa **clic su Filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="d7ff8-169">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="d7ff8-170">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="d7ff8-170">Direction values</span></span>
- <span data-ttu-id="d7ff8-171">Valori di gravità</span><span class="sxs-lookup"><span data-stu-id="d7ff8-171">Severity values</span></span>

![Visualizzazione rapporto nel rapporto delle regole di trasporto di Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="d7ff8-173">Visualizzazione della tabella dei dettagli per il rapporto sulle regole di trasporto di Exchange</span><span class="sxs-lookup"><span data-stu-id="d7ff8-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="d7ff8-174">Se si **fa clic su Visualizza tabella dettagli,** le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d7ff8-175">**Visualizzare i dati in base a: Regole di trasporto di Exchange:**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="d7ff8-176">**Data**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-176">**Date**</span></span>
  - <span data-ttu-id="d7ff8-177">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-177">**Transport rule**</span></span>
  - <span data-ttu-id="d7ff8-178">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-178">**Subject**</span></span>
  - <span data-ttu-id="d7ff8-179">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-179">**Sender address**</span></span>
  - <span data-ttu-id="d7ff8-180">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-180">**Recipient address**</span></span>
  - <span data-ttu-id="d7ff8-181">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-181">**Severity**</span></span>
  - <span data-ttu-id="d7ff8-182">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-182">**Direction**</span></span>

- <span data-ttu-id="d7ff8-183">**Visualizzare i dati per: regole di trasporto dlp di Exchange:**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="d7ff8-184">**Data**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-184">**Date**</span></span>
  - <span data-ttu-id="d7ff8-185">**Criteri DLP**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-185">**DLP policy**</span></span>
  - <span data-ttu-id="d7ff8-186">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-186">**Transport rule**</span></span>
  - <span data-ttu-id="d7ff8-187">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-187">**Subject**</span></span>
  - <span data-ttu-id="d7ff8-188">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-188">**Sender address**</span></span>
  - <span data-ttu-id="d7ff8-189">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-189">**Recipient address**</span></span>
  - <span data-ttu-id="d7ff8-190">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-190">**Severity**</span></span>
  - <span data-ttu-id="d7ff8-191">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-191">**Direction**</span></span>

<span data-ttu-id="d7ff8-192">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="d7ff8-193">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="d7ff8-194">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="d7ff8-194">Direction values</span></span>
- <span data-ttu-id="d7ff8-195">Valori di gravità</span><span class="sxs-lookup"><span data-stu-id="d7ff8-195">Severity values</span></span>

<span data-ttu-id="d7ff8-196">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="d7ff8-197">Rapporto di inoltro</span><span class="sxs-lookup"><span data-stu-id="d7ff8-197">Forwarding report</span></span>

<span data-ttu-id="d7ff8-198">Il **rapporto di inoltro** mostra i messaggi inoltrati automaticamente dall'organizzazione ai domini esterni dalle cassette postali di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="d7ff8-199">I messaggi inoltrati possono rappresentare un rischio per la sicurezza o la conformità e possono indicare un account compromesso.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="d7ff8-200">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare al dashboard dei report  \>  e selezionare Report **di inoltro.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="d7ff8-201">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="d7ff8-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget di report di inoltro nel dashboard report](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="d7ff8-203">Visualizzazione report per il report di inoltro</span><span class="sxs-lookup"><span data-stu-id="d7ff8-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="d7ff8-204">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="d7ff8-205">**Mostra dati per: Metodi di inoltro**: Vengono visualizzati i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="d7ff8-206">**Regola di trasporto**: nota anche come [regole del flusso di posta.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-206">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="d7ff8-207">**Regola cassetta postale**: nota anche come [regole di Posta in arrivo.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Visualizzazione dei metodi di inoltro nel report di inoltro](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="d7ff8-209">**Mostra i dati per: Domini di inoltro**: questa visualizzazione mostra i domini dei destinatari che sono le destinazioni per l'inoltro.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Visualizzazione dei domini di inoltro nel rapporto di inoltro](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="d7ff8-211">**Mostra dati per: Server d'inoltro**: Vengono visualizzati i seguenti server d'inoltro:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="d7ff8-212">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-212">**Transport rule**</span></span>
  - <span data-ttu-id="d7ff8-213">La cassetta postale che contiene la regola di inoltro della posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Visualizzazione server d'inoltro nel report di inoltro](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="d7ff8-215">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="d7ff8-216">Visualizzazione tabella dettagli per il report di inoltro</span><span class="sxs-lookup"><span data-stu-id="d7ff8-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="d7ff8-217">Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="d7ff8-218">**Server d'inoltro**: il valore **della regola di trasporto** o della cassetta postale che contiene la regola di inoltro posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="d7ff8-219">**Tipo di inoltro:** il valore **della regola cassetta postale o** della regola di **trasporto.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="d7ff8-220">**Nome del destinatario**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-220">**Recipient name**</span></span>
- <span data-ttu-id="d7ff8-221">**Dominio destinatario**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-221">**Recipient domain**</span></span>
- <span data-ttu-id="d7ff8-222">**Dettagli:** si tratta del valore GUID della regola del flusso di posta o del valore RuleIdentity della regola di Posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="d7ff8-223">**Numero**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-223">**Count**</span></span>
- <span data-ttu-id="d7ff8-224">**First forward date**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-224">**First forward date**</span></span>

<span data-ttu-id="d7ff8-225">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d7ff8-226">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="d7ff8-227">Rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d7ff8-227">Mailflow status report</span></span>

<span data-ttu-id="d7ff8-228">La **relazione sullo stato del** flusso di posta è simile a quella inviata e ricevuta, con ulteriori informazioni sulla posta elettronica consentita o bloccata sul perimetro. [](#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="d7ff8-229">Questo è l'unico report che contiene informazioni sulla protezione perimetrale e mostra la quantità di posta elettronica bloccata prima di essere consentita nel servizio per la valutazione da parte di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="d7ff8-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="d7ff8-230">È importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="d7ff8-231">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare al dashboard dei report e selezionare Report sullo stato del flusso  \>  **di posta.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="d7ff8-232">Per passare direttamente alla relazione sullo stato **del flusso di posta,** aprire <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="d7ff8-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget relazioni sullo stato del flusso di posta nel dashboard report](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="d7ff8-234">Visualizzazione tipo per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d7ff8-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="d7ff8-235">Quando si apre il report, la **scheda Tipo** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="d7ff8-236">Per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="d7ff8-237">**Data**: ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="d7ff8-238">**Direzione:**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-238">**Direction**:</span></span>

  - <span data-ttu-id="d7ff8-239">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-239">**Inbound**</span></span>
  - <span data-ttu-id="d7ff8-240">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-240">**Outbound**</span></span>
  - <span data-ttu-id="d7ff8-241">**Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="d7ff8-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="d7ff8-242">mittente abc@domain.com inviati al destinatario xyz@domain.com (conteggiati separatamente da **in ingresso** e in **uscita)**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="d7ff8-243">**Digitare**:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-243">**Type**:</span></span>

  - <span data-ttu-id="d7ff8-244">**Posta buona**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-244">**Good mail**</span></span>
  - <span data-ttu-id="d7ff8-245">**Malware**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-245">**Malware**</span></span>
  - <span data-ttu-id="d7ff8-246">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-246">**Spam**</span></span>
  - <span data-ttu-id="d7ff8-247">**Protezione edge**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-247">**Edge protection**</span></span>
  - <span data-ttu-id="d7ff8-248">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-248">**Rule messages**</span></span>
  - <span data-ttu-id="d7ff8-249">**Posta di phishing**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-249">**Phishing email**</span></span>

<span data-ttu-id="d7ff8-250">Il grafico è organizzato in base ai **valori type.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="d7ff8-251">È possibile modificare questi filtri facendo clic **su Filtro** o su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="d7ff8-252">La tabella dati contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-252">The data table contains the following information:</span></span>

- <span data-ttu-id="d7ff8-253">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-253">**Direction**</span></span>
- <span data-ttu-id="d7ff8-254">**Type**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-254">**Type**</span></span>
- <span data-ttu-id="d7ff8-255">**24 ore**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-255">**24 hours**</span></span>
- <span data-ttu-id="d7ff8-256">**3 giorni**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-256">**3 days**</span></span>
- <span data-ttu-id="d7ff8-257">**7 giorni**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-257">**7 days**</span></span>
- <span data-ttu-id="d7ff8-258">**15 giorni**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-258">**15 days**</span></span>
- <span data-ttu-id="d7ff8-259">**30 giorni**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-259">**30 days**</span></span>

<span data-ttu-id="d7ff8-260">Se si fa **clic su Scegli una categoria per ulteriori dettagli,** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="d7ff8-261">**Posta elettronica di phishing:** questa selezione consente di visualizzare il rapporto sullo stato [di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="d7ff8-262">**Malware nella posta elettronica:** questa selezione consente di visualizzare il rapporto sullo stato [di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="d7ff8-263">**Rilevamenti posta indesiderata:** questa selezione consente di accedere al [rapporto Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="d7ff8-264">**Posta indesiderata bloccata** di Edge: questa selezione consente di accedere al [rapporto Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="d7ff8-265">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-265">**Export**:</span></span>

<span data-ttu-id="d7ff8-266">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="d7ff8-267">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="d7ff8-268">Ogni file CSV esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="d7ff8-269">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati più file CSV.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="d7ff8-270">Visualizzazione Tipo nella relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d7ff8-270">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="d7ff8-271">Visualizzazione della direzione per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d7ff8-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="d7ff8-272">Se si fa clic **sulla scheda Direzione,** vengono utilizzati gli stessi filtri predefiniti della **visualizzazione** Tipo.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="d7ff8-273">Il grafico è organizzato in base **ai valori di** direzione.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="d7ff8-274">È possibile modificare questi filtri facendo clic **su Filtro** o su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="d7ff8-275">Vengono utilizzati gli stessi filtri **della visualizzazione** Tipo.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="d7ff8-276">La tabella dati contiene le stesse informazioni della **visualizzazione Tipo.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="d7ff8-277">**L'opzione Scegli una categoria per ulteriori** dettagli sulle selezioni e sul comportamento disponibili è la stessa della visualizzazione **Tipo.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="d7ff8-278">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-278">**Export**:</span></span>

<span data-ttu-id="d7ff8-279">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="d7ff8-280">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="d7ff8-281">Ogni file CSV esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="d7ff8-282">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati più file CSV.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="d7ff8-283">Visualizzazione direzione nella relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d7ff8-283">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="d7ff8-284">Visualizzazione Imbuto per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d7ff8-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="d7ff8-285">La **visualizzazione Imbuto** mostra il modo in cui le funzionalità di protezione dalle minacce alla posta elettronica di Microsoft filtrano la posta elettronica in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="d7ff8-286">Fornisce informazioni dettagliate sul conteggio totale della posta elettronica e sul modo in cui le funzionalità di protezione dalle minacce configurate, tra cui la protezione perimetrale, l'antimalware, l'anti-phishing, la protezione da posta indesiderata e l'anti-spoofing influiscono su questo conteggio.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="d7ff8-287">Se si fa clic **sulla** scheda Imbuto, per impostazione predefinita questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="d7ff8-288">**Data**: ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="d7ff8-289">**Direzione:**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-289">**Direction**:</span></span>

  - <span data-ttu-id="d7ff8-290">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-290">**Inbound**</span></span>
  - <span data-ttu-id="d7ff8-291">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-291">**Outbound**</span></span>
  - <span data-ttu-id="d7ff8-292">**Intra-org:** questo conteggio è per i messaggi inviati all'interno di un tenant; Ad esempio, il mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da in ingresso e in uscita).</span><span class="sxs-lookup"><span data-stu-id="d7ff8-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="d7ff8-293">La visualizzazione aggregata e la visualizzazione tabella dati consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="d7ff8-294">Se si fa **clic su Filtro,** è possibile filtrare sia il grafico che la tabella dati.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="d7ff8-295">Questo grafico mostra il numero di messaggi di posta elettronica organizzati per:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="d7ff8-296">**Totale messaggi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-296">**Total email**</span></span>
- <span data-ttu-id="d7ff8-297">**Posta elettronica dopo la protezione perimetrale**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-297">**Email after edge protection**</span></span>
- <span data-ttu-id="d7ff8-298">**Posta elettronica dopo antimalware, reputazione file, blocco del tipo di file**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="d7ff8-299">**Posta elettronica dopo anti-phish, reputazione URL, rappresentazione del marchio, anti-spoofing**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="d7ff8-300">**Posta elettronica dopo la posta indesiderata, filtro posta in blocco**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="d7ff8-301">**Posta elettronica dopo la rappresentazione di utenti e domini**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d7ff8-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="d7ff8-302">**Posta elettronica dopo la detonazione di file e URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d7ff8-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="d7ff8-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="d7ff8-304"><sup>1</sup> Defender solo per Office 365</span><span class="sxs-lookup"><span data-stu-id="d7ff8-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="d7ff8-305">Per visualizzare separatamente la posta elettronica filtrata da EOP o Defender per Office 365, fare clic sul valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="d7ff8-306">La tabella dati contiene le informazioni seguenti, visualizzate in ordine decrescente:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="d7ff8-307">**Data**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-307">**Date**</span></span>
- <span data-ttu-id="d7ff8-308">**Totale messaggi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-308">**Total email**</span></span>
- <span data-ttu-id="d7ff8-309">**Protezione edge**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-309">**Edge protection**</span></span>
- <span data-ttu-id="d7ff8-310">**Antimalware, reputazione file, blocco del tipo di file:**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="d7ff8-311">**Reputazione file:** messaggi filtrati a causa dell'identificazione di un file allegato da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="d7ff8-312">**Blocco del tipo di file:** messaggi filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="d7ff8-313">**Anti-phish, reputazione URL, rappresentazione del marchio, anti-spoofing:**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="d7ff8-314">**Reputazione URL:** messaggi filtrati a causa dell'identificazione dell'URL da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="d7ff8-315">**Rappresentazione del marchio**: messaggi filtrati a causa del messaggio proveniente da mittenti noti che rappresentano il marchio.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="d7ff8-316">**Anti-spoofing**: messaggi filtrati a causa del messaggio che tenta di effettuare lo spoofing di un dominio a cui appartiene il destinatario o di un dominio di cui il mittente non è proprietario.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="d7ff8-317">**Protezione da posta indesiderata, filtro posta inviata in blocco:**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="d7ff8-318">**Filtro posta inviata in blocco**: messaggi filtrati a causa di un tentativo di recapitare la posta inviata in blocco ai destinatari.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="d7ff8-319">**Rappresentazione di utenti e domini (Defender per Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="d7ff8-320">**Rappresentazione utente**: messaggi filtrati a causa di un tentativo di imitare un utente (mittente del messaggio) definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="d7ff8-321">**Rappresentazione del dominio**: messaggi filtrati a causa di un tentativo di rappresentare un dominio definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="d7ff8-322">**Detonazione di file e URL (Defender per Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="d7ff8-323">**Detonazione file:** messaggi filtrati in base a un criterio Allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="d7ff8-324">**Detonazione URL:** messaggio filtrato in base a un criterio Collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="d7ff8-325">**Protezione post-recapito e ZAP (ATP) o ZAP (EOP):** ZAP indica l'eliminazione automatica di zero ore.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="d7ff8-326">Se si seleziona una riga nella tabella di dati, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="d7ff8-327">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-327">**Export**:</span></span>

<span data-ttu-id="d7ff8-328">Dopo aver fatto **clic su Esporta** in **Opzioni,** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="d7ff8-329">**Riepilogo (con i dati degli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="d7ff8-330">**Dettagli (con i dati degli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="d7ff8-331">In **Data** scegliere un intervallo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="d7ff8-332">I dati per i filtri correnti verranno esportati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="d7ff8-333">Ogni file CSV esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="d7ff8-334">Se i dati contengono più di 150.000 righe, verranno creati più file CSV.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="d7ff8-335">Visualizzazione Imbuto nella relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d7ff8-335">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="d7ff8-336">Visualizzazione tecnica per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d7ff8-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="d7ff8-337">La **visualizzazione Tech è** simile alla visualizzazione **Imbuto,** fornendo dettagli più dettagliati per le funzionalità di protezione dalle minacce configurate.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="d7ff8-338">Dal grafico è possibile vedere in che modo i messaggi vengono categorizzati nelle diverse fasi della protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="d7ff8-339">Se si fa clic **sulla scheda Visualizzazione tecnica,** per impostazione predefinita questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="d7ff8-340">**Data**: ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="d7ff8-341">**Direzione:**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-341">**Direction**:</span></span>

  - <span data-ttu-id="d7ff8-342">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-342">**Inbound**</span></span>
  - <span data-ttu-id="d7ff8-343">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-343">**Outbound**</span></span>
  - <span data-ttu-id="d7ff8-344">**Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="d7ff8-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="d7ff8-345">mittente abc@domain.com inviati al destinatario xyz@domain.com (conteggiati separatamente da in ingresso e in uscita)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="d7ff8-346">La visualizzazione aggregata e la visualizzazione tabella dati consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="d7ff8-347">Se si fa **clic su Filtro,** è possibile filtrare sia il grafico che la tabella dati.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="d7ff8-348">Questo grafico mostra i messaggi organizzati nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="d7ff8-349">**Totale messaggi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-349">**Total email**</span></span>
- <span data-ttu-id="d7ff8-350">**Edge allow** e **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="d7ff8-351">**Non malware,** **rilevamento allegati sicuri,** <sup>\*</sup> rilevamento del motore **antimalware** e messaggi **delle regole**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="d7ff8-352">**Not phish,** **DMARC failure,** **Impersonation detection,** **Spoof detection**, and **Phish detection**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="d7ff8-353">**Nessun rilevamento con detonazione URL e** **rilevamento detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="d7ff8-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="d7ff8-354">**Non posta indesiderata** e  **posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="d7ff8-355">**Posta elettronica non dannosa,** **rilevamento collegamenti sicuri** e <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="d7ff8-356"><sup>\*</sup> Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="d7ff8-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="d7ff8-357">Quando si passa il mouse su una categoria nel grafico, è possibile visualizzare il numero di messaggi in tale categoria.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="d7ff8-358">La tabella dati contiene le informazioni seguenti, visualizzate in ordine decrescente:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="d7ff8-359">**Data**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-359">**Date**</span></span>
- <span data-ttu-id="d7ff8-360">**Totale messaggi di posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-360">**Total email**</span></span>
- <span data-ttu-id="d7ff8-361">**Edge filtrato**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-361">**Edge filtered**</span></span>
- <span data-ttu-id="d7ff8-362">**Motore antimalware, Allegati sicuri, regola filtrata:**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="d7ff8-363">**Regola filtrata:** messaggi filtrati a causa delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="d7ff8-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="d7ff8-364">**DMARC, rappresentazione, spoofing, phish filtrato:**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="d7ff8-365">**DMARC**: messaggi filtrati a causa del mancato controllo dell'autenticazione DMARC da parte del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="d7ff8-366">**Rilevamento detonazione URL**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-366">**URL detonation detection**</span></span>
- <span data-ttu-id="d7ff8-367">**Protezione da posta indesiderata filtrata**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="d7ff8-368">**ZAP rimosso**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-368">**ZAP removed**</span></span>
- <span data-ttu-id="d7ff8-369">**Rilevamento tramite collegamenti sicuri**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="d7ff8-370">Se si seleziona una riga nella tabella di dati, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="d7ff8-371">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-371">**Export**:</span></span>

<span data-ttu-id="d7ff8-372">Facendo clic **su Esporta,** **in Opzioni** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="d7ff8-373">**Riepilogo (con i dati degli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="d7ff8-374">**Dettagli (con i dati degli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="d7ff8-375">In **Data** scegliere un intervallo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="d7ff8-376">I dati per i filtri correnti verranno esportati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="d7ff8-377">Ogni file CSV esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="d7ff8-378">Se i dati contengono più di 150.000 righe, verranno creati più file CSV.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="d7ff8-379">Visualizzazione Tecnica nella relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="d7ff8-379">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="d7ff8-380">Rapporto di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="d7ff8-380">Sent and received email report</span></span>

<span data-ttu-id="d7ff8-381">Il **rapporto posta elettronica** inviata e ricevuta è un report intelligente che mostra le informazioni sulla posta elettronica in arrivo e in uscita, inclusi i rilevamenti di posta indesiderata, il malware e la posta elettronica identificata come "buona".</span><span class="sxs-lookup"><span data-stu-id="d7ff8-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="d7ff8-382">La differenza tra questo rapporto e la relazione sullo stato [del](#mailflow-status-report) flusso di posta è che questo rapporto non include i dati sui messaggi bloccati dalla protezione perimetrale. È importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come un unico messaggio.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="d7ff8-383">La visualizzazione aggregata e la visualizzazione dettagli del report consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="d7ff8-384">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare al dashboard dei report e selezionare Posta elettronica inviata  \>  **e ricevuta.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="d7ff8-385">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="d7ff8-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget Posta elettronica inviata e ricevuta nel dashboard report](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="d7ff8-387">Visualizzazione report per il rapporto di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="d7ff8-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="d7ff8-388">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="d7ff8-389">**Scomporsi per: Tipo**: il grafico mostra tutte le categorie disponibili:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="d7ff8-390">**Totale**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-390">**Total**</span></span>
  - <span data-ttu-id="d7ff8-391">**Posta buona**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-391">**Good mail**</span></span>
  - <span data-ttu-id="d7ff8-392">**Malware (antimalware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="d7ff8-393">**Rilevamenti di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-393">**Spam detections**</span></span>
  - <span data-ttu-id="d7ff8-394">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-394">**Rule messages**</span></span>
  - <span data-ttu-id="d7ff8-395">**Malware avanzato** (Microsoft Defender per Office 365)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="d7ff8-396">Quando si passa il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile visualizzare i dettagli relativi a tale giorno.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Visualizzazione tipo nel report Posta inviata e ricevuta](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="d7ff8-398">**Scomporsi per: Direzione:** il grafico mostra **i dati totali,** **in ingresso** **e in** uscita.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="d7ff8-399">Quando si passa il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile visualizzare i dettagli relativi a tale giorno.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Visualizzazione della direzione nel report Posta inviata e ricevuta](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="d7ff8-401">**Drill-down per** \> **Malware (antimalware):** questa selezione consente di accedere ai rilevamenti [di malware nel report di posta elettronica.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="d7ff8-402">**Drill-down per** \> **Rilevamenti posta indesiderata):** questa selezione consente di accedere al [rapporto Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="d7ff8-403">Se si fa **clic su Filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="d7ff8-404">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="d7ff8-405">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="d7ff8-405">Direction values</span></span>
- <span data-ttu-id="d7ff8-406">Valori di tipo</span><span class="sxs-lookup"><span data-stu-id="d7ff8-406">Type values</span></span>

<span data-ttu-id="d7ff8-407">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="d7ff8-408">Visualizzazione della tabella dei dettagli per il rapporto di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="d7ff8-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="d7ff8-409">Se si fa **clic su Visualizza tabella** dettagli nella visualizzazione Scomposi **per: Direzione** o Scomposi **per: Direzione,** vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="d7ff8-410">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-410">**Date (UTC)**</span></span>
- <span data-ttu-id="d7ff8-411">**Type**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-411">**Type**</span></span>
- <span data-ttu-id="d7ff8-412">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-412">**Direction**</span></span>
- <span data-ttu-id="d7ff8-413">**Numero messaggi**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-413">**Message count**</span></span>

<span data-ttu-id="d7ff8-414">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="d7ff8-415">**Data di inizio** **e data di fine**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="d7ff8-416">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="d7ff8-416">Direction values</span></span>
- <span data-ttu-id="d7ff8-417">Valori di tipo</span><span class="sxs-lookup"><span data-stu-id="d7ff8-417">Type values</span></span>

<span data-ttu-id="d7ff8-418">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="d7ff8-419">Rapporto Mittenti e destinatari principali</span><span class="sxs-lookup"><span data-stu-id="d7ff8-419">Top senders and recipients report</span></span>

<span data-ttu-id="d7ff8-420">Il **rapporto Mittenti e destinatari** principali è un grafico a torta che mostra i mittenti e i destinatari di posta elettronica principali.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="d7ff8-421">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare al dashboard dei report e selezionare  \>  **Mittenti e destinatari principali.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="d7ff8-422">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="d7ff8-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget Mittenti e destinatari principali nel dashboard report](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="d7ff8-424">Visualizzazione rapporto per il rapporto Mittenti principali e destinatari</span><span class="sxs-lookup"><span data-stu-id="d7ff8-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="d7ff8-425">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="d7ff8-426">**Visualizzare i dati per \> i mittenti di posta principali**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="d7ff8-427">**Visualizzare i dati per \> i destinatari di posta principali**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="d7ff8-428">**Visualizzare i dati per \> i destinatari principali della posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="d7ff8-429">**Mostra dati per \> Principali destinatari di malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="d7ff8-430">**Visualizzare i dati \> per i principali destinatari di malware (Defender per Office 365)**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="d7ff8-431">La composizione del grafico a torta cambia in base a queste selezioni.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="d7ff8-432">Quando si passa il mouse su un cuneo nel grafico a torta, è possibile visualizzare un conteggio dei messaggi inviati o ricevuti.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="d7ff8-433">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Grafico a torta nella visualizzazione Report nel report Mittenti e destinatari principali](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="d7ff8-435">Visualizzazione tabella dettagli per il rapporto Mittenti principali e destinatari</span><span class="sxs-lookup"><span data-stu-id="d7ff8-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="d7ff8-436">Se si **fa clic su Visualizza tabella dettagli,** le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="d7ff8-437">**Visualizzare i dati per \> i mittenti di posta principali**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="d7ff8-438">**Principali mittenti di posta**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-438">**Top mail senders**</span></span>
  - <span data-ttu-id="d7ff8-439">**Numero**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-439">**Count**</span></span>

- <span data-ttu-id="d7ff8-440">**Visualizzare i dati per \> i destinatari di posta principali**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="d7ff8-441">**Destinatari di posta elettronica principali**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="d7ff8-442">**Numero**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-442">**Count**</span></span>

- <span data-ttu-id="d7ff8-443">**Visualizzare i dati per \> i destinatari principali della posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="d7ff8-444">**Destinatari di posta indesiderata principali**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="d7ff8-445">**Numero**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-445">**Count**</span></span>

- <span data-ttu-id="d7ff8-446">**Mostra dati per \> Principali destinatari di malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="d7ff8-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="d7ff8-447">**Principali destinatari di malware**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="d7ff8-448">**Numero**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-448">**Count**</span></span>

- <span data-ttu-id="d7ff8-449">**Visualizzare i dati \> per i principali destinatari di malware (Defender per Office 365)**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="d7ff8-450">**Principali destinatari di malware (Defender per Office 365)**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="d7ff8-451">**Numero**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-451">**Count**</span></span>

<span data-ttu-id="d7ff8-452">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di inizio **e** Data **di fine.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="d7ff8-453">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="d7ff8-454">Quali autorizzazioni sono necessarie per visualizzare questi report?</span><span class="sxs-lookup"><span data-stu-id="d7ff8-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="d7ff8-455">Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="d7ff8-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="d7ff8-456">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-456">**Organization Management**</span></span>
- <span data-ttu-id="d7ff8-457">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-457">**Security Administrator**</span></span>
- <span data-ttu-id="d7ff8-458">**Lettore di sicurezza**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-458">**Security Reader**</span></span>
- <span data-ttu-id="d7ff8-459">**Lettore globale**</span><span class="sxs-lookup"><span data-stu-id="d7ff8-459">**Global Reader**</span></span>

<span data-ttu-id="d7ff8-460">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d7ff8-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d7ff8-461">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d7ff8-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="d7ff8-462">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d7ff8-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d7ff8-463">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d7ff8-463">Related topics</span></span>

[<span data-ttu-id="d7ff8-464">Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="d7ff8-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="d7ff8-465">Approfondimenti sul flusso di posta nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="d7ff8-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="d7ff8-466">Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="d7ff8-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="d7ff8-467">Visualizzare i report per Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="d7ff8-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
