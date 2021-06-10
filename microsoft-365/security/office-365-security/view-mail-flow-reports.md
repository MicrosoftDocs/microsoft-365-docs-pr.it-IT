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
ms.openlocfilehash: 38beac44af191a027db722ade25ca7fd0e505d9b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245673"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="76a79-103">Visualizzare i report del flusso di posta nel dashboard report nel Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="76a79-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="76a79-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="76a79-104">**Applies to**</span></span>
- [<span data-ttu-id="76a79-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="76a79-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="76a79-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="76a79-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="76a79-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76a79-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="76a79-108">Oltre ai report del flusso di posta disponibili nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza e conformità di &, nel dashboard report sono disponibili diversi report aggiuntivi sul flusso di posta che consentono di monitorare l'organizzazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76a79-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="76a79-109">Se si dispone delle [autorizzazioni necessarie,](#what-permissions-are-needed-to-view-these-reports)è possibile visualizzare questi report nel Centro [sicurezza & conformità](https://protection.office.com) andando a Dashboard  \> **report.**</span><span class="sxs-lookup"><span data-stu-id="76a79-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="76a79-110">Per passare direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="76a79-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Dashboard dei report nel Centro sicurezza & conformità](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="76a79-112">Report connettore</span><span class="sxs-lookup"><span data-stu-id="76a79-112">Connector report</span></span>

<span data-ttu-id="76a79-113">Il **report Connettore** mostra l'attività del flusso di posta sui connettori in ingresso [e](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) in uscita configurati per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="76a79-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="76a79-114">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Report connettore.**</span><span class="sxs-lookup"><span data-stu-id="76a79-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="76a79-115">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="76a79-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget report connettore nel dashboard report](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="76a79-117">Visualizzazione report per il report Connettore</span><span class="sxs-lookup"><span data-stu-id="76a79-117">Report view for the Connector report</span></span>

<span data-ttu-id="76a79-118">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="76a79-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span><span class="sxs-lookup"><span data-stu-id="76a79-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="76a79-120">**Totale**</span><span class="sxs-lookup"><span data-stu-id="76a79-120">**Total**</span></span>
  - <span data-ttu-id="76a79-121">**Da Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="76a79-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="76a79-122">**A Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="76a79-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="76a79-123">Un connettore specifico configurato.</span><span class="sxs-lookup"><span data-stu-id="76a79-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="76a79-124">Per isolare i dati nel grafico, utilizzare il **controllo Mostra dati** per selezionare una di queste opzioni o Tutto il flusso di **posta.**</span><span class="sxs-lookup"><span data-stu-id="76a79-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Visualizzare i dati in base al flusso di posta nel report Connettore](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="76a79-126">**Visualizzare i dati per: utilizzo di TLS**: Questo grafico mostra la percentuale di utilizzo della versione TLS (Transport Layer Security) per il flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="76a79-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="76a79-127">Per isolare i dati nel grafico, utilizzare il **controllo Mostra dati** per selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="76a79-128">**Tutto il flusso di posta**</span><span class="sxs-lookup"><span data-stu-id="76a79-128">**All mail flow**</span></span>
  - <span data-ttu-id="76a79-129">**Da Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="76a79-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="76a79-130">**A Internet senza connettore**</span><span class="sxs-lookup"><span data-stu-id="76a79-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="76a79-131">Un connettore specifico configurato.</span><span class="sxs-lookup"><span data-stu-id="76a79-131">A specific connector that you've configured.</span></span>

  ![Visualizzare i dati in base all'utilizzo di TLS nel report Connettore](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="76a79-133">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="76a79-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="76a79-134">Visualizzazione tabella dettagli per il report Connettore</span><span class="sxs-lookup"><span data-stu-id="76a79-134">Details table view for the Connector report</span></span>

<span data-ttu-id="76a79-135">Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="76a79-136">**Data**</span><span class="sxs-lookup"><span data-stu-id="76a79-136">**Date**</span></span>
- <span data-ttu-id="76a79-137">**Direzione e nome del connettore**</span><span class="sxs-lookup"><span data-stu-id="76a79-137">**Connector direction and name**</span></span>
- <span data-ttu-id="76a79-138">**Tipo di connettore**</span><span class="sxs-lookup"><span data-stu-id="76a79-138">**Connector type**</span></span>
- <span data-ttu-id="76a79-139">**TLS forzato?**: Il **valore True** o **False**.</span><span class="sxs-lookup"><span data-stu-id="76a79-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="76a79-140">**Nessun TLS** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="76a79-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="76a79-141">**TLS 1.0** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="76a79-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="76a79-142">**TLS 1.1** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="76a79-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="76a79-143">**TLS 1.2** (percentuale)</span><span class="sxs-lookup"><span data-stu-id="76a79-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="76a79-144">**Volume**: numero di messaggi.</span><span class="sxs-lookup"><span data-stu-id="76a79-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="76a79-145">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="76a79-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="76a79-146">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="76a79-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="76a79-147">Exchange delle regole di trasporto</span><span class="sxs-lookup"><span data-stu-id="76a79-147">Exchange transport rule report</span></span>

<span data-ttu-id="76a79-148">Il Exchange delle **regole** di trasporto mostra l'effetto delle regole del flusso di posta (note anche come regole di trasporto) sui messaggi in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="76a79-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="76a79-149">Per visualizzare il report, aprire il Centro [sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e selezionare Exchange  \>  Regola di **trasporto**.</span><span class="sxs-lookup"><span data-stu-id="76a79-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="76a79-150">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="76a79-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Exchange della regola di trasporto nel dashboard report](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="76a79-152">Visualizzazione report per il report Exchange regola di trasporto</span><span class="sxs-lookup"><span data-stu-id="76a79-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="76a79-153">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="76a79-154">**Visualizzare i dati per: Exchange di trasporto** \> **Scomporsi per: Direzione**: questo grafico  mostra il numero di **messaggi in** ingresso e in uscita interessati dalle regole di trasporto.</span><span class="sxs-lookup"><span data-stu-id="76a79-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="76a79-155">**Visualizzare i dati per: Exchange di trasporto** \> **Scomporsi per: Gravità**: questo grafico mostra il numero **di** messaggi Di gravità elevata e Gravità media e **Gravità** bassa.</span><span class="sxs-lookup"><span data-stu-id="76a79-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="76a79-156">Il livello di gravità viene impostato come azione nella regola **(** Controlla questa regola con livello di gravità o _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="76a79-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="76a79-157">Per ulteriori informazioni, vedere [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="76a79-157">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="76a79-158">**Visualizzare i dati in base a: DLP Exchange trasporto** \> **Scomporsi per: Direzione**: questo grafico  mostra il numero di messaggi **in** ingresso e in uscita interessati dalle regole di trasporto dlp (Data Loss Prevention).</span><span class="sxs-lookup"><span data-stu-id="76a79-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="76a79-159">È possibile perfezionare ulteriormente il grafico selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="76a79-160">**Mostra dati per: Tutte le regole di trasporto DLP**</span><span class="sxs-lookup"><span data-stu-id="76a79-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="76a79-161">**Mostra dati per: utenti compromessi**</span><span class="sxs-lookup"><span data-stu-id="76a79-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="76a79-162">**Mostra dati per: Basso volume di contenuto rilevato U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="76a79-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="76a79-163">**Visualizzare i dati in base a: DLP Exchange trasporto** \> **Scomporsi per: Direzione**:  questa visualizzazione mostra il numero  di messaggi di gravità alta e media **e** di gravità bassa interessati dalle regole di trasporto DLP.</span><span class="sxs-lookup"><span data-stu-id="76a79-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="76a79-164">È possibile perfezionare ulteriormente il grafico selezionando una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="76a79-165">**Mostra dati per: Tutte le regole di trasporto DLP**</span><span class="sxs-lookup"><span data-stu-id="76a79-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="76a79-166">**Mostra dati per: utenti compromessi**</span><span class="sxs-lookup"><span data-stu-id="76a79-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="76a79-167">**Mostra dati per: Basso volume di contenuto rilevato U.S. Patriot Act**</span><span class="sxs-lookup"><span data-stu-id="76a79-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="76a79-168">Se si fa **clic su Filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="76a79-169">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="76a79-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="76a79-170">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="76a79-170">Direction values</span></span>
- <span data-ttu-id="76a79-171">Valori di gravità</span><span class="sxs-lookup"><span data-stu-id="76a79-171">Severity values</span></span>

![Visualizzazione report nel report delle regole Exchange trasporto](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="76a79-173">Visualizzazione tabella dettagli per il report Exchange regole di trasporto</span><span class="sxs-lookup"><span data-stu-id="76a79-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="76a79-174">Se si fa **clic su Visualizza tabella** dettagli , le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="76a79-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="76a79-175">**Visualizzare i dati per: Exchange di trasporto**:</span><span class="sxs-lookup"><span data-stu-id="76a79-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="76a79-176">**Data**</span><span class="sxs-lookup"><span data-stu-id="76a79-176">**Date**</span></span>
  - <span data-ttu-id="76a79-177">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="76a79-177">**Transport rule**</span></span>
  - <span data-ttu-id="76a79-178">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="76a79-178">**Subject**</span></span>
  - <span data-ttu-id="76a79-179">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="76a79-179">**Sender address**</span></span>
  - <span data-ttu-id="76a79-180">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="76a79-180">**Recipient address**</span></span>
  - <span data-ttu-id="76a79-181">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="76a79-181">**Severity**</span></span>
  - <span data-ttu-id="76a79-182">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="76a79-182">**Direction**</span></span>

- <span data-ttu-id="76a79-183">**Visualizzare i dati per: DLP Exchange di trasporto**:</span><span class="sxs-lookup"><span data-stu-id="76a79-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="76a79-184">**Data**</span><span class="sxs-lookup"><span data-stu-id="76a79-184">**Date**</span></span>
  - <span data-ttu-id="76a79-185">**Criterio DLP**</span><span class="sxs-lookup"><span data-stu-id="76a79-185">**DLP policy**</span></span>
  - <span data-ttu-id="76a79-186">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="76a79-186">**Transport rule**</span></span>
  - <span data-ttu-id="76a79-187">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="76a79-187">**Subject**</span></span>
  - <span data-ttu-id="76a79-188">**Indirizzo del mittente**</span><span class="sxs-lookup"><span data-stu-id="76a79-188">**Sender address**</span></span>
  - <span data-ttu-id="76a79-189">**Indirizzo destinatario**</span><span class="sxs-lookup"><span data-stu-id="76a79-189">**Recipient address**</span></span>
  - <span data-ttu-id="76a79-190">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="76a79-190">**Severity**</span></span>
  - <span data-ttu-id="76a79-191">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="76a79-191">**Direction**</span></span>

<span data-ttu-id="76a79-192">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="76a79-193">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="76a79-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="76a79-194">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="76a79-194">Direction values</span></span>
- <span data-ttu-id="76a79-195">Valori di gravità</span><span class="sxs-lookup"><span data-stu-id="76a79-195">Severity values</span></span>

<span data-ttu-id="76a79-196">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="76a79-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="76a79-197">Rapporto di inoltro</span><span class="sxs-lookup"><span data-stu-id="76a79-197">Forwarding report</span></span>

<span data-ttu-id="76a79-198">Il **rapporto Inoltro mostra** i messaggi inoltrati automaticamente dall'organizzazione a domini esterni da Exchange Online cassette postali.</span><span class="sxs-lookup"><span data-stu-id="76a79-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="76a79-199">I messaggi inoltrati possono rappresentare un rischio per la sicurezza o la conformità e possono indicare un account compromesso.</span><span class="sxs-lookup"><span data-stu-id="76a79-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="76a79-200">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report  \>  e selezionare Report **di inoltro.**</span><span class="sxs-lookup"><span data-stu-id="76a79-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="76a79-201">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="76a79-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget Di report di inoltro nel dashboard report](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="76a79-203">Visualizzazione report per il report di inoltro</span><span class="sxs-lookup"><span data-stu-id="76a79-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="76a79-204">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="76a79-205">**Mostra dati per: Metodi di inoltro**: Vengono visualizzati i metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="76a79-206">**Regola di trasporto**: nota anche come [regole del flusso di posta](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="76a79-206">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="76a79-207">**Regola cassetta postale**: nota anche come [regole di Posta in arrivo.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="76a79-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Visualizzazione dei metodi di inoltro nel report di inoltro](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="76a79-209">**Show data for: Forwarding domains**: Questa visualizzazione mostra i domini dei destinatari che sono le destinazioni per l'inoltro.</span><span class="sxs-lookup"><span data-stu-id="76a79-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Visualizzazione domini di inoltro nel report di inoltro](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="76a79-211">**Mostra dati per: Server d'inoltro**: Vengono visualizzati i seguenti server d'inoltro:</span><span class="sxs-lookup"><span data-stu-id="76a79-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="76a79-212">**Regola di trasporto**</span><span class="sxs-lookup"><span data-stu-id="76a79-212">**Transport rule**</span></span>
  - <span data-ttu-id="76a79-213">Cassetta postale che contiene la regola di posta in arrivo di inoltro.</span><span class="sxs-lookup"><span data-stu-id="76a79-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Visualizzazione server d'inoltro nel report di inoltro](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="76a79-215">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="76a79-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="76a79-216">Visualizzazione tabella dettagli per il report di inoltro</span><span class="sxs-lookup"><span data-stu-id="76a79-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="76a79-217">Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="76a79-218">**Server d'inoltro**: valore **Regola di trasporto** o cassetta postale che contiene la regola di posta in arrivo di inoltro.</span><span class="sxs-lookup"><span data-stu-id="76a79-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="76a79-219">**Tipo di inoltro**: Valore **Regola cassetta postale o** Regola di **trasporto.**</span><span class="sxs-lookup"><span data-stu-id="76a79-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="76a79-220">**Nome del destinatario**</span><span class="sxs-lookup"><span data-stu-id="76a79-220">**Recipient name**</span></span>
- <span data-ttu-id="76a79-221">**Dominio destinatario**</span><span class="sxs-lookup"><span data-stu-id="76a79-221">**Recipient domain**</span></span>
- <span data-ttu-id="76a79-222">**Dettagli:** si tratta del valore GUID della regola del flusso di posta o del valore RuleIdentity della regola di Posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="76a79-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="76a79-223">**Numero**</span><span class="sxs-lookup"><span data-stu-id="76a79-223">**Count**</span></span>
- <span data-ttu-id="76a79-224">**Prima data di inoltro**</span><span class="sxs-lookup"><span data-stu-id="76a79-224">**First forward date**</span></span>

<span data-ttu-id="76a79-225">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="76a79-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="76a79-226">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="76a79-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="76a79-227">Rapporto sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="76a79-227">Mailflow status report</span></span>

<span data-ttu-id="76a79-228">La **relazione sullo stato del flusso di** posta è simile al [rapporto](#sent-and-received-email-report)Posta inviata e ricevuta, con ulteriori informazioni sulla posta elettronica consentita o bloccata sul perimetro.</span><span class="sxs-lookup"><span data-stu-id="76a79-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="76a79-229">Questo è l'unico report che contiene informazioni sulla protezione perimetrale e mostra la quantità di posta elettronica bloccata prima di essere consentita al servizio per la valutazione da parte di Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="76a79-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="76a79-230">È importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.</span><span class="sxs-lookup"><span data-stu-id="76a79-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="76a79-231">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e  \>  selezionare Report stato flusso **di posta**.</span><span class="sxs-lookup"><span data-stu-id="76a79-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="76a79-232">Per passare direttamente alla relazione **sullo stato del flusso di posta,** aprire <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="76a79-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget rapporto sullo stato del flusso di posta nel dashboard report](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="76a79-234">Visualizzazione tipo per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="76a79-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="76a79-235">Quando si apre il report, la **scheda Tipo** è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="76a79-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="76a79-236">Per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="76a79-237">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="76a79-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="76a79-238">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="76a79-238">**Direction**:</span></span>

  - <span data-ttu-id="76a79-239">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="76a79-239">**Inbound**</span></span>
  - <span data-ttu-id="76a79-240">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="76a79-240">**Outbound**</span></span>
  - <span data-ttu-id="76a79-241">**Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="76a79-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="76a79-242">mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da **In ingresso** e **In uscita)**</span><span class="sxs-lookup"><span data-stu-id="76a79-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="76a79-243">**Digitare**:</span><span class="sxs-lookup"><span data-stu-id="76a79-243">**Type**:</span></span>

  - <span data-ttu-id="76a79-244">**Posta buona**</span><span class="sxs-lookup"><span data-stu-id="76a79-244">**Good mail**</span></span>
  - <span data-ttu-id="76a79-245">**Malware**</span><span class="sxs-lookup"><span data-stu-id="76a79-245">**Malware**</span></span>
  - <span data-ttu-id="76a79-246">**Posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="76a79-246">**Spam**</span></span>
  - <span data-ttu-id="76a79-247">**Protezione edge**</span><span class="sxs-lookup"><span data-stu-id="76a79-247">**Edge protection**</span></span>
  - <span data-ttu-id="76a79-248">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="76a79-248">**Rule messages**</span></span>
  - <span data-ttu-id="76a79-249">**Posta di phishing**</span><span class="sxs-lookup"><span data-stu-id="76a79-249">**Phishing email**</span></span>

<span data-ttu-id="76a79-250">Il grafico è organizzato in base ai **valori Type.**</span><span class="sxs-lookup"><span data-stu-id="76a79-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="76a79-251">È possibile modificare questi filtri facendo clic **su Filtro** o su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="76a79-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="76a79-252">La tabella dati contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-252">The data table contains the following information:</span></span>

- <span data-ttu-id="76a79-253">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="76a79-253">**Direction**</span></span>
- <span data-ttu-id="76a79-254">**Type**</span><span class="sxs-lookup"><span data-stu-id="76a79-254">**Type**</span></span>
- <span data-ttu-id="76a79-255">**24 ore**</span><span class="sxs-lookup"><span data-stu-id="76a79-255">**24 hours**</span></span>
- <span data-ttu-id="76a79-256">**3 giorni**</span><span class="sxs-lookup"><span data-stu-id="76a79-256">**3 days**</span></span>
- <span data-ttu-id="76a79-257">**7 giorni**</span><span class="sxs-lookup"><span data-stu-id="76a79-257">**7 days**</span></span>
- <span data-ttu-id="76a79-258">**15 giorni**</span><span class="sxs-lookup"><span data-stu-id="76a79-258">**15 days**</span></span>
- <span data-ttu-id="76a79-259">**30 giorni**</span><span class="sxs-lookup"><span data-stu-id="76a79-259">**30 days**</span></span>

<span data-ttu-id="76a79-260">Se si fa **clic su Scegli una categoria per ulteriori dettagli,** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="76a79-261">**Posta elettronica di phishing**: questa selezione consente di visualizzare il [rapporto sullo stato di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="76a79-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="76a79-262">**Malware nella posta elettronica**: questa selezione consente di visualizzare il [rapporto sullo stato di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="76a79-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="76a79-263">**Rilevamenti di posta indesiderata:** questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="76a79-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="76a79-264">**Posta indesiderata bloccata** perimetrali : questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="76a79-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="76a79-265">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="76a79-265">**Export**:</span></span>

<span data-ttu-id="76a79-266">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="76a79-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="76a79-267">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.</span><span class="sxs-lookup"><span data-stu-id="76a79-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="76a79-268">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="76a79-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="76a79-269">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="76a79-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione tipo nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="76a79-271">Visualizzazione della direzione per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="76a79-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="76a79-272">Se si fa clic **sulla scheda Direzione,** vengono utilizzati gli stessi filtri predefiniti della **visualizzazione** Tipo.</span><span class="sxs-lookup"><span data-stu-id="76a79-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="76a79-273">Il grafico è organizzato in base **ai valori di** Direzione.</span><span class="sxs-lookup"><span data-stu-id="76a79-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="76a79-274">È possibile modificare questi filtri facendo clic **su Filtro** o su un valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="76a79-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="76a79-275">Vengono utilizzati gli stessi filtri **della** visualizzazione Tipo.</span><span class="sxs-lookup"><span data-stu-id="76a79-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="76a79-276">La tabella dati contiene le stesse informazioni della **visualizzazione Tipo.**</span><span class="sxs-lookup"><span data-stu-id="76a79-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="76a79-277">**L'opzione Scegliere una categoria per ulteriori dettagli** le selezioni e il comportamento disponibili sono gli stessi della visualizzazione **Tipo.**</span><span class="sxs-lookup"><span data-stu-id="76a79-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="76a79-278">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="76a79-278">**Export**:</span></span>

<span data-ttu-id="76a79-279">Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno.</span><span class="sxs-lookup"><span data-stu-id="76a79-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="76a79-280">Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.</span><span class="sxs-lookup"><span data-stu-id="76a79-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="76a79-281">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="76a79-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="76a79-282">Se i dati di quel giorno contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="76a79-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Visualizzazione direzione nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="76a79-284">Visualizzazione imbuto per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="76a79-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="76a79-285">La **visualizzazione Imbuto** mostra come le funzionalità di protezione dalle minacce di posta elettronica di Microsoft filtrano la posta elettronica in arrivo e in uscita nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="76a79-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="76a79-286">Fornisce informazioni dettagliate sul conteggio totale della posta elettronica e sul modo in cui le funzionalità di protezione dalle minacce configurate, tra cui protezione perimetrale, antimalware, anti-phishing, protezione da posta indesiderata e anti-spoofing influiscono su questo conteggio.</span><span class="sxs-lookup"><span data-stu-id="76a79-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="76a79-287">Se si fa clic sulla scheda **Imbuto,** per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="76a79-288">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="76a79-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="76a79-289">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="76a79-289">**Direction**:</span></span>

  - <span data-ttu-id="76a79-290">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="76a79-290">**Inbound**</span></span>
  - <span data-ttu-id="76a79-291">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="76a79-291">**Outbound**</span></span>
  - <span data-ttu-id="76a79-292">**Intra-org:** questo conteggio è per i messaggi inviati all'interno di un tenant; Ad esempio, il mittente abc@domain.com inviato al destinatario xyz@domain.com (conteggiato separatamente da Inbound e Outbound).</span><span class="sxs-lookup"><span data-stu-id="76a79-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="76a79-293">La visualizzazione aggregata e la visualizzazione tabella dati consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="76a79-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="76a79-294">Se si fa **clic su Filtro**, è possibile filtrare sia il grafico che la tabella dati.</span><span class="sxs-lookup"><span data-stu-id="76a79-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="76a79-295">Questo grafico mostra il numero di messaggi di posta elettronica organizzati per:</span><span class="sxs-lookup"><span data-stu-id="76a79-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="76a79-296">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="76a79-296">**Total email**</span></span>
- <span data-ttu-id="76a79-297">**Posta elettronica dopo la protezione edge**</span><span class="sxs-lookup"><span data-stu-id="76a79-297">**Email after edge protection**</span></span>
- <span data-ttu-id="76a79-298">**Posta elettronica dopo antimalware, reputazione file, blocco del tipo di file**</span><span class="sxs-lookup"><span data-stu-id="76a79-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="76a79-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="76a79-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="76a79-300">**Posta elettronica dopo la posta indesiderata, filtro posta in blocco**</span><span class="sxs-lookup"><span data-stu-id="76a79-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="76a79-301">**Posta elettronica dopo la rappresentazione di dominio e utente**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="76a79-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="76a79-302">**Posta elettronica dopo la detonazione di file e URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="76a79-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="76a79-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span><span class="sxs-lookup"><span data-stu-id="76a79-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="76a79-304"><sup>1</sup> Defender per Office 365 solo</span><span class="sxs-lookup"><span data-stu-id="76a79-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="76a79-305">Per visualizzare il messaggio di posta elettronica filtrato da EOP o Defender per Office 365 separatamente, fare clic sul valore nella legenda del grafico.</span><span class="sxs-lookup"><span data-stu-id="76a79-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="76a79-306">La tabella dei dati contiene le informazioni seguenti, visualizzate in ordine di data decrescente:</span><span class="sxs-lookup"><span data-stu-id="76a79-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="76a79-307">**Data**</span><span class="sxs-lookup"><span data-stu-id="76a79-307">**Date**</span></span>
- <span data-ttu-id="76a79-308">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="76a79-308">**Total email**</span></span>
- <span data-ttu-id="76a79-309">**Protezione edge**</span><span class="sxs-lookup"><span data-stu-id="76a79-309">**Edge protection**</span></span>
- <span data-ttu-id="76a79-310">**Antimalware, reputazione file, blocco del tipo di file**:</span><span class="sxs-lookup"><span data-stu-id="76a79-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="76a79-311">**Reputazione file:** messaggi filtrati a causa dell'identificazione di un file allegato da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="76a79-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="76a79-312">**Blocco del tipo di** file : Messaggi filtrati a causa del tipo di file dannoso identificato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="76a79-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="76a79-313">**Anti-phish, reputazione URL, rappresentazione del marchio, anti-spoofing**:</span><span class="sxs-lookup"><span data-stu-id="76a79-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="76a79-314">**Reputazione URL**: Messaggi filtrati a causa dell'identificazione dell'URL da parte di altri clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="76a79-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="76a79-315">**Rappresentazione del marchio**: messaggi filtrati a causa del messaggio proveniente da mittenti noti che rappresentano il marchio.</span><span class="sxs-lookup"><span data-stu-id="76a79-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="76a79-316">**Anti-spoof**: messaggi filtrati a causa del tentativo di spoofing di un dominio a cui appartiene il destinatario o di un dominio di cui il mittente non è proprietario.</span><span class="sxs-lookup"><span data-stu-id="76a79-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="76a79-317">**Protezione da posta indesiderata, filtro posta in blocco**:</span><span class="sxs-lookup"><span data-stu-id="76a79-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="76a79-318">**Filtro posta in blocco**: Messaggi filtrati a causa di un tentativo di recapitare la posta in blocco ai destinatari.</span><span class="sxs-lookup"><span data-stu-id="76a79-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="76a79-319">**Rappresentazione utente e dominio (Defender per Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="76a79-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="76a79-320">**Rappresentazione utente**: messaggi filtrati a causa di un tentativo di rappresentazione di un utente (mittente del messaggio) definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="76a79-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="76a79-321">**Rappresentazione di dominio**: messaggi filtrati a causa di un tentativo di rappresentare un dominio definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="76a79-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="76a79-322">**Detonazione di file e URL (Defender per Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="76a79-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="76a79-323">**Detonazione file:** messaggi filtrati in base a un criterio Allegati sicuri.</span><span class="sxs-lookup"><span data-stu-id="76a79-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="76a79-324">**Detonazione URL:** messaggio filtrato in base a un criterio collegamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="76a79-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="76a79-325">**Protezione post-recapito e ZAP (ATP) o ZAP (EOP):** ZAP indica l'eliminazione automatica a zero ore.</span><span class="sxs-lookup"><span data-stu-id="76a79-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="76a79-326">Se si seleziona una riga nella tabella dati, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="76a79-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="76a79-327">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="76a79-327">**Export**:</span></span>

<span data-ttu-id="76a79-328">Dopo aver fatto **clic su** Esporta **in Opzioni,** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="76a79-329">**Riepilogo (con i dati degli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="76a79-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="76a79-330">**Dettagli (con dati degli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="76a79-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="76a79-331">In **Data** scegliere un intervallo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="76a79-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="76a79-332">I dati per i filtri correnti verranno esportati in un .csv file.</span><span class="sxs-lookup"><span data-stu-id="76a79-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="76a79-333">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="76a79-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="76a79-334">Se i dati contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="76a79-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Visualizzazione Imbuto nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="76a79-336">Visualizzazione tecnica per la relazione sullo stato del flusso di posta</span><span class="sxs-lookup"><span data-stu-id="76a79-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="76a79-337">La **visualizzazione Tech** è simile alla visualizzazione **Imbuto,** fornendo dettagli più dettagliati per le funzionalità di protezione dalle minacce configurate.</span><span class="sxs-lookup"><span data-stu-id="76a79-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="76a79-338">Dal grafico è possibile vedere come i messaggi vengono categorizzati nelle diverse fasi della protezione dalle minacce.</span><span class="sxs-lookup"><span data-stu-id="76a79-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="76a79-339">Se si fa clic **sulla scheda Visualizzazione tecnica,** per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="76a79-340">**Date**: Ultimi 7 giorni.</span><span class="sxs-lookup"><span data-stu-id="76a79-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="76a79-341">**Direzione**:</span><span class="sxs-lookup"><span data-stu-id="76a79-341">**Direction**:</span></span>

  - <span data-ttu-id="76a79-342">**In ingresso**</span><span class="sxs-lookup"><span data-stu-id="76a79-342">**Inbound**</span></span>
  - <span data-ttu-id="76a79-343">**In uscita**</span><span class="sxs-lookup"><span data-stu-id="76a79-343">**Outbound**</span></span>
  - <span data-ttu-id="76a79-344">**Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio</span><span class="sxs-lookup"><span data-stu-id="76a79-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="76a79-345">mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da in ingresso e in uscita)</span><span class="sxs-lookup"><span data-stu-id="76a79-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="76a79-346">La visualizzazione aggregata e la visualizzazione tabella dati consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="76a79-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="76a79-347">Se si fa **clic su Filtro**, è possibile filtrare sia il grafico che la tabella dati.</span><span class="sxs-lookup"><span data-stu-id="76a79-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="76a79-348">Questo grafico mostra i messaggi organizzati nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="76a79-349">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="76a79-349">**Total email**</span></span>
- <span data-ttu-id="76a79-350">**Edge allow** e **Edge filtered**</span><span class="sxs-lookup"><span data-stu-id="76a79-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="76a79-351">**Non malware,** **Rilevamento allegati sicuri,** <sup>\*</sup> Rilevamento motore **antimalware** e **Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="76a79-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="76a79-352">**Not phish,** **DMARC failure,** **Impersonation detection,** **Spoof detection** e **Phish detection**</span><span class="sxs-lookup"><span data-stu-id="76a79-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="76a79-353">**Nessun rilevamento con detonazione URL e** **rilevamento detonazione URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="76a79-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="76a79-354">**Non posta indesiderata** e  **posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="76a79-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="76a79-355">**Posta elettronica non dannosa,** **rilevamento collegamenti sicuri** e <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="76a79-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="76a79-356"><sup>\*</sup>Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="76a79-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="76a79-357">Quando si passa il mouse su una categoria nel grafico, è possibile visualizzare il numero di messaggi in tale categoria.</span><span class="sxs-lookup"><span data-stu-id="76a79-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="76a79-358">La tabella dei dati contiene le informazioni seguenti, visualizzate in ordine di data decrescente:</span><span class="sxs-lookup"><span data-stu-id="76a79-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="76a79-359">**Data**</span><span class="sxs-lookup"><span data-stu-id="76a79-359">**Date**</span></span>
- <span data-ttu-id="76a79-360">**Totale posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="76a79-360">**Total email**</span></span>
- <span data-ttu-id="76a79-361">**Edge filtrato**</span><span class="sxs-lookup"><span data-stu-id="76a79-361">**Edge filtered**</span></span>
- <span data-ttu-id="76a79-362">**Motore antimalware, Allegati sicuri, regola filtrata:**</span><span class="sxs-lookup"><span data-stu-id="76a79-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="76a79-363">**Regola filtrata**: Messaggi filtrati a causa delle regole del flusso di posta (note anche come regole di trasporto).</span><span class="sxs-lookup"><span data-stu-id="76a79-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="76a79-364">**DMARC, rappresentazione, spoofing, phish filtrato**:</span><span class="sxs-lookup"><span data-stu-id="76a79-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="76a79-365">**DMARC**: Messaggi filtrati a causa dell'errore del messaggio nel controllo di autenticazione DMARC.</span><span class="sxs-lookup"><span data-stu-id="76a79-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="76a79-366">**Rilevamento detonazione URL**</span><span class="sxs-lookup"><span data-stu-id="76a79-366">**URL detonation detection**</span></span>
- <span data-ttu-id="76a79-367">**Protezione da posta indesiderata filtrata**</span><span class="sxs-lookup"><span data-stu-id="76a79-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="76a79-368">**ZAP rimosso**</span><span class="sxs-lookup"><span data-stu-id="76a79-368">**ZAP removed**</span></span>
- <span data-ttu-id="76a79-369">**Rilevamento tramite collegamenti sicuri**</span><span class="sxs-lookup"><span data-stu-id="76a79-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="76a79-370">Se si seleziona una riga nella tabella dati, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="76a79-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="76a79-371">**Esporta**:</span><span class="sxs-lookup"><span data-stu-id="76a79-371">**Export**:</span></span>

<span data-ttu-id="76a79-372">Facendo clic **su Esporta,** in **Opzioni** è possibile selezionare uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="76a79-373">**Riepilogo (con i dati degli ultimi 90 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="76a79-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="76a79-374">**Dettagli (con dati degli ultimi 30 giorni al massimo)**</span><span class="sxs-lookup"><span data-stu-id="76a79-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="76a79-375">In **Data** scegliere un intervallo e quindi fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="76a79-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="76a79-376">I dati per i filtri correnti verranno esportati in un .csv file.</span><span class="sxs-lookup"><span data-stu-id="76a79-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="76a79-377">Ogni file .csv esportato è limitato a 150.000 righe.</span><span class="sxs-lookup"><span data-stu-id="76a79-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="76a79-378">Se i dati contengono più di 150.000 righe, verranno creati .csv file.</span><span class="sxs-lookup"><span data-stu-id="76a79-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Visualizzazione tecnica nella relazione sullo stato del flusso di posta](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="76a79-380">Rapporto di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="76a79-380">Sent and received email report</span></span>

<span data-ttu-id="76a79-381">Il **report Posta inviata e** ricevuta è un report intelligente che mostra le informazioni sulla posta elettronica in arrivo e in uscita, inclusi i rilevamenti di posta indesiderata, il malware e la posta elettronica identificata come "buona".</span><span class="sxs-lookup"><span data-stu-id="76a79-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="76a79-382">La differenza tra questo report e la relazione sullo stato [del flusso](#mailflow-status-report) di posta è che non include i dati sui messaggi bloccati dalla protezione perimetrale. È importante comprendere che se un messaggio viene inviato a cinque destinatari viene conteggiato come un unico messaggio.</span><span class="sxs-lookup"><span data-stu-id="76a79-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="76a79-383">La visualizzazione aggregata e la visualizzazione dettagli del report consentono 90 giorni di filtro.</span><span class="sxs-lookup"><span data-stu-id="76a79-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="76a79-384">Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e selezionare Posta elettronica inviata  \>  **e ricevuta.**</span><span class="sxs-lookup"><span data-stu-id="76a79-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="76a79-385">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="76a79-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget Posta elettronica inviata e ricevuta nel dashboard report](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="76a79-387">Visualizzazione report per il report Di posta elettronica inviato e ricevuto</span><span class="sxs-lookup"><span data-stu-id="76a79-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="76a79-388">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="76a79-389">**Scomporsi per: Tipo**: Il grafico mostra tutte le categorie disponibili:</span><span class="sxs-lookup"><span data-stu-id="76a79-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="76a79-390">**Totale**</span><span class="sxs-lookup"><span data-stu-id="76a79-390">**Total**</span></span>
  - <span data-ttu-id="76a79-391">**Posta buona**</span><span class="sxs-lookup"><span data-stu-id="76a79-391">**Good mail**</span></span>
  - <span data-ttu-id="76a79-392">**Malware (antimalware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="76a79-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="76a79-393">**Rilevamenti di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="76a79-393">**Spam detections**</span></span>
  - <span data-ttu-id="76a79-394">**Messaggi delle regole**</span><span class="sxs-lookup"><span data-stu-id="76a79-394">**Rule messages**</span></span>
  - <span data-ttu-id="76a79-395">**Malware avanzato** (Microsoft Defender per Office 365)</span><span class="sxs-lookup"><span data-stu-id="76a79-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="76a79-396">Quando si passa il mouse su un giorno (punto dati) nel grafico, è possibile visualizzare i dettagli per tale giorno.</span><span class="sxs-lookup"><span data-stu-id="76a79-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Digitare la visualizzazione nel report Posta elettronica inviata e ricevuta](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="76a79-398">**Scomporsi per: Direzione**: il grafico mostra **i dati totali,** in **ingresso** **e in** uscita.</span><span class="sxs-lookup"><span data-stu-id="76a79-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="76a79-399">Quando si passa il mouse su un giorno (punto dati) nel grafico, è possibile visualizzare i dettagli per tale giorno.</span><span class="sxs-lookup"><span data-stu-id="76a79-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Visualizzazione della direzione nel report Posta inviata e ricevuta](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="76a79-401">**Drill-down per** \> **Malware (antimalware):** questa selezione consente di accedere ai rilevamenti [di malware nel report di posta elettronica.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="76a79-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="76a79-402">**Drill-down per** \> **Rilevamenti posta indesiderata):** questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="76a79-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="76a79-403">Se si fa **clic su Filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="76a79-404">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="76a79-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="76a79-405">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="76a79-405">Direction values</span></span>
- <span data-ttu-id="76a79-406">Valori di tipo</span><span class="sxs-lookup"><span data-stu-id="76a79-406">Type values</span></span>

<span data-ttu-id="76a79-407">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="76a79-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="76a79-408">Visualizzazione tabella dettagli per il report Posta inviata e ricevuta</span><span class="sxs-lookup"><span data-stu-id="76a79-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="76a79-409">Se si fa **clic su Visualizza tabella dettagli** nella visualizzazione Scomposi **per: Direzione** o Scomparti **per:** Direzione, vengono visualizzate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="76a79-410">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="76a79-410">**Date (UTC)**</span></span>
- <span data-ttu-id="76a79-411">**Type**</span><span class="sxs-lookup"><span data-stu-id="76a79-411">**Type**</span></span>
- <span data-ttu-id="76a79-412">**Direzione**</span><span class="sxs-lookup"><span data-stu-id="76a79-412">**Direction**</span></span>
- <span data-ttu-id="76a79-413">**Conteggio messaggi**</span><span class="sxs-lookup"><span data-stu-id="76a79-413">**Message count**</span></span>

<span data-ttu-id="76a79-414">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="76a79-415">**Data di inizio** e **Data fine**</span><span class="sxs-lookup"><span data-stu-id="76a79-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="76a79-416">Valori di direzione</span><span class="sxs-lookup"><span data-stu-id="76a79-416">Direction values</span></span>
- <span data-ttu-id="76a79-417">Valori di tipo</span><span class="sxs-lookup"><span data-stu-id="76a79-417">Type values</span></span>

<span data-ttu-id="76a79-418">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="76a79-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="76a79-419">Rapporto Mittenti e destinatari principali</span><span class="sxs-lookup"><span data-stu-id="76a79-419">Top senders and recipients report</span></span>

<span data-ttu-id="76a79-420">Il **report Mittenti e destinatari** principali è un grafico a torta che mostra i mittenti e i destinatari di posta elettronica principali.</span><span class="sxs-lookup"><span data-stu-id="76a79-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="76a79-421">Per visualizzare il report, aprire il Centro [sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e  \>  selezionare **Mittenti e destinatari principali.**</span><span class="sxs-lookup"><span data-stu-id="76a79-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="76a79-422">Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="76a79-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget Mittenti e destinatari principali nel dashboard dei report](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="76a79-424">Visualizzazione report per il rapporto Mittenti principali e destinatari</span><span class="sxs-lookup"><span data-stu-id="76a79-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="76a79-425">Nella visualizzazione report sono disponibili i grafici seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a79-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="76a79-426">**Mostra i dati per \> i principali mittenti di posta**</span><span class="sxs-lookup"><span data-stu-id="76a79-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="76a79-427">**Visualizzare i dati per \> i destinatari di posta elettronica principali**</span><span class="sxs-lookup"><span data-stu-id="76a79-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="76a79-428">**Visualizzare i dati per \> i destinatari principali della posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="76a79-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="76a79-429">**Mostra dati per \> Principali destinatari di malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="76a79-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="76a79-430">**Visualizzare i dati \> per i destinatari principali di malware (Defender per Office 365)**</span><span class="sxs-lookup"><span data-stu-id="76a79-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="76a79-431">La composizione del grafico a torta cambia in base a queste selezioni.</span><span class="sxs-lookup"><span data-stu-id="76a79-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="76a79-432">Quando si passa il mouse su un cuneo nel grafico a torta, è possibile visualizzare un conteggio dei messaggi inviati o ricevuti.</span><span class="sxs-lookup"><span data-stu-id="76a79-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="76a79-433">Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="76a79-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Grafico a torta nella visualizzazione Report nel report Mittenti e destinatari principali](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="76a79-435">Visualizzazione tabella dettagli per il rapporto Mittenti principali e destinatari</span><span class="sxs-lookup"><span data-stu-id="76a79-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="76a79-436">Se si fa **clic su Visualizza tabella** dettagli , le informazioni visualizzate dipendono dal grafico visualizzato:</span><span class="sxs-lookup"><span data-stu-id="76a79-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="76a79-437">**Mostra i dati per \> i principali mittenti di posta**</span><span class="sxs-lookup"><span data-stu-id="76a79-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="76a79-438">**Principali mittenti di posta**</span><span class="sxs-lookup"><span data-stu-id="76a79-438">**Top mail senders**</span></span>
  - <span data-ttu-id="76a79-439">**Numero**</span><span class="sxs-lookup"><span data-stu-id="76a79-439">**Count**</span></span>

- <span data-ttu-id="76a79-440">**Visualizzare i dati per \> i destinatari di posta elettronica principali**</span><span class="sxs-lookup"><span data-stu-id="76a79-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="76a79-441">**Destinatari di posta elettronica principali**</span><span class="sxs-lookup"><span data-stu-id="76a79-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="76a79-442">**Numero**</span><span class="sxs-lookup"><span data-stu-id="76a79-442">**Count**</span></span>

- <span data-ttu-id="76a79-443">**Visualizzare i dati per \> i destinatari principali della posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="76a79-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="76a79-444">**Principali destinatari di posta indesiderata**</span><span class="sxs-lookup"><span data-stu-id="76a79-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="76a79-445">**Numero**</span><span class="sxs-lookup"><span data-stu-id="76a79-445">**Count**</span></span>

- <span data-ttu-id="76a79-446">**Mostra dati per \> Principali destinatari di malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="76a79-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="76a79-447">**Principali destinatari di malware**</span><span class="sxs-lookup"><span data-stu-id="76a79-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="76a79-448">**Numero**</span><span class="sxs-lookup"><span data-stu-id="76a79-448">**Count**</span></span>

- <span data-ttu-id="76a79-449">**Visualizzare i dati \> per i destinatari principali di malware (Defender per Office 365)**</span><span class="sxs-lookup"><span data-stu-id="76a79-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="76a79-450">**Principali destinatari di malware (Defender per Office 365)**</span><span class="sxs-lookup"><span data-stu-id="76a79-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="76a79-451">**Numero**</span><span class="sxs-lookup"><span data-stu-id="76a79-451">**Count**</span></span>

<span data-ttu-id="76a79-452">Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**</span><span class="sxs-lookup"><span data-stu-id="76a79-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="76a79-453">Per tornare alla visualizzazione report, fare clic su **Visualizza report.**</span><span class="sxs-lookup"><span data-stu-id="76a79-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="76a79-454">Quali autorizzazioni sono necessarie per visualizzare questi report?</span><span class="sxs-lookup"><span data-stu-id="76a79-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="76a79-455">Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel Centro sicurezza & conformità:</span><span class="sxs-lookup"><span data-stu-id="76a79-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="76a79-456">**Gestione organizzazione**</span><span class="sxs-lookup"><span data-stu-id="76a79-456">**Organization Management**</span></span>
- <span data-ttu-id="76a79-457">**Amministratore della sicurezza**</span><span class="sxs-lookup"><span data-stu-id="76a79-457">**Security Administrator**</span></span>
- <span data-ttu-id="76a79-458">**Lettore sicurezza**</span><span class="sxs-lookup"><span data-stu-id="76a79-458">**Security Reader**</span></span>
- <span data-ttu-id="76a79-459">**Lettore globale**</span><span class="sxs-lookup"><span data-stu-id="76a79-459">**Global Reader**</span></span>

<span data-ttu-id="76a79-460">Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="76a79-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="76a79-461">L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76a79-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="76a79-462">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="76a79-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="76a79-463">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="76a79-463">Related topics</span></span>

[<span data-ttu-id="76a79-464">Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="76a79-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="76a79-465">Approfondimenti sul flusso di posta nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="76a79-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="76a79-466">Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="76a79-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="76a79-467">Visualizzare i report per Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="76a79-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
